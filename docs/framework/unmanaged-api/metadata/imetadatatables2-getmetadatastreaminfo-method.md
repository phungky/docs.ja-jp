---
title: "IMetaDataTables2::GetMetaDataStreamInfo メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables2.GetMetaDataStreamInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1631ae8398a8daa910931ff705440a2be0cf21b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="70ca8-102">IMetaDataTables2::GetMetaDataStreamInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="70ca8-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="70ca8-103">名前、サイズ、および指定したインデックス位置にあるメタデータ ストリームの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="70ca8-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70ca8-104">構文</span><span class="sxs-lookup"><span data-stu-id="70ca8-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70ca8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70ca8-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="70ca8-106">[in]要求されたメタデータ ストリームのインデックス。</span><span class="sxs-lookup"><span data-stu-id="70ca8-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="70ca8-107">[out]ストリームの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="70ca8-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="70ca8-108">[out]メタデータ ストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="70ca8-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="70ca8-109">[out]サイズをバイト単位での`ppv`します。</span><span class="sxs-lookup"><span data-stu-id="70ca8-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70ca8-110">要件</span><span class="sxs-lookup"><span data-stu-id="70ca8-110">Requirements</span></span>  
 <span data-ttu-id="70ca8-111">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="70ca8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70ca8-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="70ca8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70ca8-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="70ca8-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70ca8-114">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70ca8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ca8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="70ca8-115">See Also</span></span>  
 [<span data-ttu-id="70ca8-116">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70ca8-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [<span data-ttu-id="70ca8-117">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70ca8-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)