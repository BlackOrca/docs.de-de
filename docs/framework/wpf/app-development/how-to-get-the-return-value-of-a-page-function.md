---
title: 'Gewusst wie: Abrufen des Rückgabewerts einer Seitenfunktion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- functions [WPF], getting return values of
- page functions [WPF], getting return values of
- return values of page functions [WPF]
- getting [WPF], return values of page functions
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
ms.openlocfilehash: 2994a0fd7a192716a829c8290f030788da74cec5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545268"
---
# <a name="how-to-get-the-return-value-of-a-page-function"></a>Gewusst wie: Abrufen des Rückgabewerts einer Seitenfunktion
In diesem Beispiel wird gezeigt, wie das Ergebnis, das von einer Seitenfunktion zurückgegeben wird, abgerufen wird.  
  
## <a name="example"></a>Beispiel  
 Zum Abrufen des Ergebnisses, das von einer Seitenfunktion zurückgegeben wird, müssen Sie behandeln <xref:System.Windows.Navigation.PageFunction%601.Return> der Seite "-Funktion, die Sie aufrufen.  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Navigation.PageFunction%601>
