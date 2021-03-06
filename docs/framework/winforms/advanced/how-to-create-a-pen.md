---
title: '方法 : ペンを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: aff1771af12a9f59127a9f21f4b692d6214c457d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520979"
---
# <a name="how-to-create-a-pen"></a>方法 : ペンを作成する
この例で作成、<xref:System.Drawing.Pen>オブジェクト。  
  
## <a name="example"></a>例  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 などのシステム リソースを消費しているオブジェクトを使用して完了したら<xref:System.Drawing.Pen>オブジェクトを呼び出す必要があります<xref:System.Drawing.Pen.Dispose%2A>にします。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Drawing.Pen>  
 [グラフィックス プログラミングについて](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [GDI+ でのペン、直線、および四角形](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
