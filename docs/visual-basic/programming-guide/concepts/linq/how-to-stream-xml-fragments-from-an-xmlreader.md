---
title: 'Vorgehensweise: Stream XML-Fragmenten aus einem XmlReader (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
ms.openlocfilehash: 38a81e83421dffc997a2cbfd6d0996da5ece18d1
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332700"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a>Vorgehensweise: Stream XML-Fragmenten aus einem XmlReader (Visual Basic)
Wenn Sie große XML-Dateien verarbeiten müssen, kann u. U. nicht die gesamte XML-Struktur in den Arbeitsspeicher geladen werden. In diesem Thema wird gezeigt, wie mit einem <xref:System.Xml.XmlReader> Fragmente gestreamt werden können.  
  
 Eine der effektivsten Möglichkeiten, einen <xref:System.Xml.XmlReader> zum Lesen von <xref:System.Xml.Linq.XElement>-Objekten zu verwenden, besteht darin, eine eigene benutzerdefinierte Achsenmethode zu schreiben. Achsenmethoden geben in der Regel eine Auflistung, z. B. die <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> zurück, wie dies im Beispiel in diesem Thema dargestellt ist. Nachdem Sie in der benutzerdefinierten Achsenmethode durch Aufrufen der <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode das XML-Fragment erstellt haben, geben Sie die Auflistung mit `yield return` zurück. Auf diese Weise versehen Sie Ihre benutzerdefinierte Achsenmethode mit der Semantik für eine verzögerte Ausführung.  
  
 Wenn Sie eine XML-Struktur auf der Grundlage eines <xref:System.Xml.XmlReader>-Objekts erstellen, muss der <xref:System.Xml.XmlReader> auf einem Element positioniert sein. Die <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode gibt erst dann einen Wert zurück, wenn sie das Endtag des Elements gelesen hat.  
  
 Wenn Sie eine Teilstruktur erstellen möchten, können Sie einen <xref:System.Xml.XmlReader> instanziieren, den Reader auf dem Knoten positionieren, der in eine <xref:System.Xml.Linq.XElement>-Struktur umgewandelt werden soll, und dann das <xref:System.Xml.Linq.XElement>-Objekt erstellen.  
  
 Das Thema [Vorgehensweise: Stream XML-Fragmenten mit Zugriff auf Headerinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) enthält Informationen und ein Beispiel dazu, wie komplexere Dokumente gestreamt.  
  
 Im Thema [How to: Perform Streaming Transform der Large XML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) enthält ein Beispiel mit LINQ to XML extrem große XML-Dokumenten zu transformieren, Beibehaltung einer geringen speicherbeanspruchung.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel erstellt eine benutzerdefinierte Achsenmethode. Zum Abfragen kann eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage verwendet werden. Die benutzerdefinierte Achsenmethode `StreamRootChildDoc` eignet sich vor allem zum Lesen eines Dokuments, das ein sich wiederholendes `Child`-Element enthält.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim markup = "<Root>" &  
                     "  <Child Key=""01"">" &  
                     "    <GrandChild>aaa</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""02"">" &  
                     "    <GrandChild>bbb</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""03"">" &  
                     "    <GrandChild>ccc</GrandChild>" &  
                     "  </Child>" &  
                     "</Root>"  
  
        Dim grandChildData =  
             From el In New StreamRootChildDoc(New IO.StringReader(markup))  
             Where CInt(el.@Key) > 1  
             Select el.<GrandChild>.Value  
  
        For Each s In grandChildData  
            Console.WriteLine(s)  
        Next  
    End Sub  
End Module  
  
Public Class StreamRootChildDoc  
    Implements IEnumerable(Of XElement)  
  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamChildEnumerator(_stringReader)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamChildEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _reader As Xml.XmlReader  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        While _reader.Read()  
            Select Case _reader.NodeType  
                Case Xml.XmlNodeType.Element  
                    Dim el = TryCast(XElement.ReadFrom(_reader), XElement)  
                    If el IsNot Nothing Then  
                        _current = el  
                        Return True  
                    End If  
            End Select  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
bbb  
ccc  
```  
  
 In diesem Beispiel ist das Quelldokument sehr klein. Dieses Beispiel würde aber auch dann wenig Speicher beanspruchen, wenn das Quelldokument Millionen `Child`-Elemente enthielte.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Implementieren von IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)  
 [Analysieren von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
