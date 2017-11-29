---
title: "COR_PRF_FINALIZER_FLAGS 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FINALIZER_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FINALIZER_FLAGS
helpviewer_keywords: COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 63707ca18be29555919264f9aa3a0f143efdd374
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="cbae8-102">COR_PRF_FINALIZER_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="cbae8-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="cbae8-103">オブジェクトのファイナライザーを記述します。</span><span class="sxs-lookup"><span data-stu-id="cbae8-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbae8-104">構文</span><span class="sxs-lookup"><span data-stu-id="cbae8-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="cbae8-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="cbae8-105">Members</span></span>  
  
|<span data-ttu-id="cbae8-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="cbae8-106">Member</span></span>|<span data-ttu-id="cbae8-107">説明</span><span class="sxs-lookup"><span data-stu-id="cbae8-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="cbae8-108">ファイナライザーが重要です。</span><span class="sxs-lookup"><span data-stu-id="cbae8-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbae8-109">コメント</span><span class="sxs-lookup"><span data-stu-id="cbae8-109">Remarks</span></span>  
 <span data-ttu-id="cbae8-110">`COR_PRF_FINALIZER_FLAGS`列挙型を使用して、 [icorprofilercallback 2::finalizeableobjectqueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)オブジェクトのファイナライザーを記述するメソッド。</span><span class="sxs-lookup"><span data-stu-id="cbae8-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbae8-111">要件</span><span class="sxs-lookup"><span data-stu-id="cbae8-111">Requirements</span></span>  
 <span data-ttu-id="cbae8-112">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="cbae8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbae8-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cbae8-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cbae8-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbae8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbae8-115">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbae8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbae8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbae8-116">See Also</span></span>  
 [<span data-ttu-id="cbae8-117">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="cbae8-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)