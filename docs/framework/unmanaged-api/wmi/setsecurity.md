---
title: "SetSecurity 関数 (アンマネージ API リファレンス)"
description: "SetSecurity 関数では、現在のスレッドの偽装トークンを取得します。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SetSecurity
helpviewer_keywords: SetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4fd7ccb0cfb25773da7e489f9ce4d6332b80a616
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="setsecurity-function"></a><span data-ttu-id="42346-103">SetSecurity 関数</span><span class="sxs-lookup"><span data-stu-id="42346-103">SetSecurity function</span></span>
<span data-ttu-id="42346-104">現在のスレッドに関連付けられている権限借用トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="42346-104">Retrieves the impersonation token associated with the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="42346-105">構文</span><span class="sxs-lookup"><span data-stu-id="42346-105">Syntax</span></span>  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a><span data-ttu-id="42346-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42346-106">Parameters</span></span>

<span data-ttu-id="42346-107">`pNeedToReset`[out]ポインターを含む、関数から制御が戻るとき、`boolean`を呼び出してトークンをリセットするかどうかを示す、 [ResetSecurity](resetsecurity.md)関数。</span><span class="sxs-lookup"><span data-stu-id="42346-107">`pNeedToReset` [out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>  

`token`  
<span data-ttu-id="42346-108">[out]関数から制御が戻るときに、現在のスレッドに関連付けられている権限借用トークンのハンドルへのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="42346-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="42346-109">その値を指定できます`null`かどうかは、現在のスレッドに関連付けられているトークンはありません。</span><span class="sxs-lookup"><span data-stu-id="42346-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="42346-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="42346-110">Return value</span></span>

<span data-ttu-id="42346-111">関数が成功した場合、戻り値は`S_OK`(0) です。</span><span class="sxs-lookup"><span data-stu-id="42346-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="42346-112">関数が失敗した場合、戻り値がゼロ以外のエラー コードです。</span><span class="sxs-lookup"><span data-stu-id="42346-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="42346-113">拡張エラー情報を取得する呼び出し、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="42346-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="42346-114">要件</span><span class="sxs-lookup"><span data-stu-id="42346-114">Requirements</span></span>  
 <span data-ttu-id="42346-115">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="42346-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42346-116">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="42346-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="42346-117">**.NET framework のバージョン:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42346-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42346-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="42346-118">See also</span></span>  
[<span data-ttu-id="42346-119">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="42346-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)