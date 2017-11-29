---
title: "IMetaDataAssemblyImport::EnumFiles メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumFiles
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dfe8f1c9080a963458f6dc429475a1fd0407bb2e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="8a7c3-102">IMetaDataAssemblyImport::EnumFiles メソッド</span><span class="sxs-lookup"><span data-stu-id="8a7c3-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="8a7c3-103">現在のアセンブリ マニフェストで参照されるファイルを列挙します。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a7c3-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a7c3-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a7c3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a7c3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8a7c3-106">[入力、出力].列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8a7c3-107">これには、このメソッドの最初の呼び出しに対して null 値があります。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="8a7c3-108">[out]配列の格納に使用される、`mdFile`メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8a7c3-109">[in]最大数`mdFile`に配置できるトークン`rFiles`です。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8a7c3-110">[out]数`mdFile`にトークンが実際に配置されます`rFiles`です。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a7c3-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="8a7c3-111">Return Value</span></span>  
  
|<span data-ttu-id="8a7c3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a7c3-112">HRESULT</span></span>|<span data-ttu-id="8a7c3-113">説明</span><span class="sxs-lookup"><span data-stu-id="8a7c3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8a7c3-114">`EnumFiles`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8a7c3-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="8a7c3-116">この場合、`pcTokens`は 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a7c3-117">要件</span><span class="sxs-lookup"><span data-stu-id="8a7c3-117">Requirements</span></span>  
 <span data-ttu-id="8a7c3-118">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="8a7c3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a7c3-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8a7c3-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a7c3-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="8a7c3-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a7c3-121">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a7c3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a7c3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a7c3-122">See Also</span></span>  
 [<span data-ttu-id="8a7c3-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a7c3-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)