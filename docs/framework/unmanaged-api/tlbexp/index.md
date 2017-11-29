---
title: "Tlbexp ヘルパー関数 (アンマネージ API リファレンス)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5d0a0b08be725a50442a3db9f9942bceea7cf8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="56c2e-102">Tlbexp ヘルパー関数 (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="56c2e-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="56c2e-103">[タイプ ライブラリ エクスポーター ツール](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)(Tlbexp.exe) が TlbRef.dll をという名前のダイナミック リンク ライブラリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="56c2e-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="56c2e-104">この DLL には、2 つのヘルパー関数とエクスポーター ツールが、アセンブリをタイプ ライブラリへの変換処理中に使用するインターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="56c2e-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56c2e-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="56c2e-105">In This Section</span></span>  
 [<span data-ttu-id="56c2e-106">GetTypeLibInfo 関数</span><span class="sxs-lookup"><span data-stu-id="56c2e-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="56c2e-107">タイプ ライブラリのローカライズとオペレーティング システムの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="56c2e-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="56c2e-108">LoadTypeLibWithResolver 関数</span><span class="sxs-lookup"><span data-stu-id="56c2e-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="56c2e-109">実装を使用して、タイプ ライブラリを読み込み、 [ITypeLibResolver インターフェイス](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)いずれかを解決するのには、タイプ ライブラリを参照します。</span><span class="sxs-lookup"><span data-stu-id="56c2e-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="56c2e-110">ITypeLibResolver インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56c2e-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="56c2e-111">提供、 [ResolveTypeLib メソッド](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md)、タイプ ライブラリの完全修飾パスが返されます。</span><span class="sxs-lookup"><span data-stu-id="56c2e-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>