---
title: "IMetaDataTables インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables
helpviewer_keywords: IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c89d615fbeeff4a60eb386d58c573ee7905f538d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="1a270-102">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a270-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="1a270-103">テーブル内のメタデータ情報の格納と取得のためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1a270-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a270-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-104">Methods</span></span>  
  
|<span data-ttu-id="1a270-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-105">Method</span></span>|<span data-ttu-id="1a270-106">説明</span><span class="sxs-lookup"><span data-stu-id="1a270-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a270-107">GetBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="1a270-108">指定された列インデックスにあるバイナリ ラージ オブジェクト (BLOB) へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="1a270-109">GetBlobHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="1a270-110">BLOB ヒープのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="1a270-111">GetCodedTokenInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="1a270-112">指定した行のインデックスに関連付けられているトークンの配列へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="1a270-113">GetColumn メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="1a270-114">指定したテーブルのインデックスにある表で、指定された列インデックスの列に含まれる値へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="1a270-115">GetColumnInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="1a270-116">指定されたテーブルで指定された列に関するデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="1a270-117">GetGuid メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="1a270-118">指定したインデックス位置の行から GUID を取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="1a270-119">GetGuidHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="1a270-120">GUID ヒープのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="1a270-121">GetNextBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="1a270-122">テーブル内には、次の BLOB のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="1a270-123">GetNextGuid メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="1a270-124">現在のテーブルの列には、次の GUID 値のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="1a270-125">GetNextString メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="1a270-126">現在のテーブルの列には、次の文字列のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="1a270-127">GetNextUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="1a270-128">現在のテーブルの列に [次へ] ハード コーディングされた文字列を含む行のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="1a270-129">GetNumTables メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="1a270-130">現在のスコープ内のテーブルの数を取得`IMetaDataTables`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1a270-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="1a270-131">GetRow メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="1a270-132">指定したテーブルのインデックスにある表で、指定した行のインデックス行を取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="1a270-133">GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="1a270-134">現在参照スコープ内のテーブル列から、指定したインデックス位置文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="1a270-135">GetStringHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="1a270-136">文字列ヒープのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="1a270-137">GetTableIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="1a270-138">指定したトークンによって参照されるテーブルのインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="1a270-139">GetTableInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="1a270-140">指定したテーブル インデックスの名前、行のサイズ、行の数、列の数、およびテーブルのキー列のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="1a270-141">GetUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="1a270-142">現在のスコープ内の文字列の列で指定したインデックス位置には、ハード コーディングされた文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="1a270-143">GetUserStringHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="1a270-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="1a270-144">ユーザー文字列ヒープのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a270-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a270-145">要件</span><span class="sxs-lookup"><span data-stu-id="1a270-145">Requirements</span></span>  
 <span data-ttu-id="1a270-146">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="1a270-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a270-147">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1a270-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a270-148">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="1a270-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a270-149">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a270-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a270-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a270-150">See Also</span></span>  
 [<span data-ttu-id="1a270-151">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a270-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="1a270-152">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a270-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)