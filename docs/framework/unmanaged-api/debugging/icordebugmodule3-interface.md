---
title: "ICorDebugModule3 インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule3
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugModule3
helpviewer_keywords: ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f6ef8314329aba60d8c23c6f00725192d83961ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="3edaf-102">ICorDebugModule3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3edaf-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="3edaf-103">動的モジュールのシンボル リーダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3edaf-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3edaf-104">構文</span><span class="sxs-lookup"><span data-stu-id="3edaf-104">Syntax</span></span>  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3edaf-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3edaf-105">Methods</span></span>  
  
|<span data-ttu-id="3edaf-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="3edaf-106">Method</span></span>|<span data-ttu-id="3edaf-107">説明</span><span class="sxs-lookup"><span data-stu-id="3edaf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3edaf-108">Icordebugmodule 3::createreaderforinmemorysymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="3edaf-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="3edaf-109">シンボル リーダーの作成 (通常[ISymUnmanagedReader インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) の動的モジュール。</span><span class="sxs-lookup"><span data-stu-id="3edaf-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3edaf-110">コメント</span><span class="sxs-lookup"><span data-stu-id="3edaf-110">Remarks</span></span>  
 <span data-ttu-id="3edaf-111">このインターフェイスは、"ICorDebugModule"および"ICorDebugModule2"インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="3edaf-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3edaf-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3edaf-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3edaf-113">要件</span><span class="sxs-lookup"><span data-stu-id="3edaf-113">Requirements</span></span>  
 <span data-ttu-id="3edaf-114">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="3edaf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3edaf-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3edaf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3edaf-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3edaf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3edaf-117">**.NET framework のバージョン:**4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3edaf-117">**.NET Framework Versions:**4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3edaf-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3edaf-118">See Also</span></span>  
 [<span data-ttu-id="3edaf-119">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3edaf-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="3edaf-120">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3edaf-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="3edaf-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3edaf-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)