---
title: "ICorDebugProcess5::EnumerateGCReferences メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateGCReferences
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f517415412c93b009df81fc9a7f524449eb82a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="9f18a-102">ICorDebugProcess5::EnumerateGCReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="9f18a-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="9f18a-103">プロセスでガベージ コレクトされるすべてのオブジェクトの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f18a-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f18a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f18a-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f18a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f18a-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="9f18a-106">[in]弱い参照は、列挙するもあるかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="9f18a-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="9f18a-107">場合`enumerateWeakReferences`は`true`、`ppEnum`列挙子には、強力な参照および弱い参照の両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f18a-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="9f18a-108">場合`enumerateWeakReferences`は`false`、列挙子には、強力な参照のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f18a-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="9f18a-109">[out]アドレスへのポインター、 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)つまりする列挙子オブジェクトのガベージ コレクションします。</span><span class="sxs-lookup"><span data-stu-id="9f18a-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f18a-110">コメント</span><span class="sxs-lookup"><span data-stu-id="9f18a-110">Remarks</span></span>  
 <span data-ttu-id="9f18a-111">このメソッドは、プロセスでマネージ オブジェクトに対して完全ルート チェーンを決定する方法を提供し、オブジェクトが生きて理由を判断するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f18a-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f18a-112">要件</span><span class="sxs-lookup"><span data-stu-id="9f18a-112">Requirements</span></span>  
 <span data-ttu-id="9f18a-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="9f18a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f18a-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f18a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f18a-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f18a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f18a-116">**.NET framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f18a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f18a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f18a-117">See Also</span></span>  
 [<span data-ttu-id="9f18a-118">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f18a-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="9f18a-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f18a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)