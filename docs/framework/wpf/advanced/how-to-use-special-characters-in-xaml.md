---
title: 'Gewusst wie: Verwenden von Sonderzeichen in XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: c593ca094487e8f7016b02870026321fbcb9a7c3
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34256185"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Gewusst wie: Verwenden von Sonderzeichen in XAML
Markupdateien, die in erstellt werden [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] werden automatisch gespeichert, der [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8-Dateiformat, was bedeutet, dass die meisten Sonderzeichen wie z. B. Akzente, richtig codiert sind. Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden. Führen Sie die folgende Sonderzeichen enthalten die [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard zum Codieren.  
  
 Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:  
  
|Zeichen|Syntax|Beschreibung|  
|---------------|------------|-----------------|  
|<|`&lt;`|Kleiner als-Zeichen.|  
|>|`&gt;`|Größer als-Zeichen|  
|&|`&amp;`|Und-Zeichen (&)|  
|"|`&quot;`|Doppeltes Anführungszeichen|  
  
> [!NOTE]
>  Wenn Erstellung einer Markupdatei mit einem Text-Editor, z. B. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Editor, müssen Sie die Datei im Speichern der [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] Dateiformat um beizubehalten UTF-8 codiert Sonderzeichen enthalten.  
  
 Das folgende Beispiel zeigt, wie Sie Sonderzeichen im Text beim Erstellen von Markup verwenden können.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
