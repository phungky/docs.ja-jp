---
title: "ICLRRuntimeHost::GetCurrentAppDomainId メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCurrentAppDomainId
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 001a467536c899c3849b5689e65bdaf404beab75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="d73e9-102">ICLRRuntimeHost::GetCurrentAppDomainId メソッド</span><span class="sxs-lookup"><span data-stu-id="d73e9-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="d73e9-103">数値識別子を取得、<xref:System.AppDomain>が現在実行されています。</span><span class="sxs-lookup"><span data-stu-id="d73e9-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d73e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="d73e9-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d73e9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d73e9-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="d73e9-106">[out]数値識別子、<xref:System.AppDomain>が現在実行されています。</span><span class="sxs-lookup"><span data-stu-id="d73e9-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d73e9-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d73e9-107">Return Value</span></span>  
  
|<span data-ttu-id="d73e9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d73e9-108">HRESULT</span></span>|<span data-ttu-id="d73e9-109">説明</span><span class="sxs-lookup"><span data-stu-id="d73e9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d73e9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d73e9-110">S_OK</span></span>|<span data-ttu-id="d73e9-111">`GetCurrentAppDomainId`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d73e9-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="d73e9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d73e9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d73e9-113">共通言語ランタイム (CLR) が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="d73e9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d73e9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d73e9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d73e9-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="d73e9-115">The call timed out.</span></span>|  
|<span data-ttu-id="d73e9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d73e9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d73e9-117">呼び出し元は、ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d73e9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d73e9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d73e9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d73e9-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d73e9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d73e9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d73e9-120">E_FAIL</span></span>|<span data-ttu-id="d73e9-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d73e9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d73e9-122">メソッドには、E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d73e9-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d73e9-123">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="d73e9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d73e9-124">コメント</span><span class="sxs-lookup"><span data-stu-id="d73e9-124">Remarks</span></span>  
 <span data-ttu-id="d73e9-125">`pdwAppDomainId`パラメーターがの値に設定されている、<xref:System.AppDomain.Id%2A>のプロパティ、<xref:System.AppDomain>現在のスレッドが実行中にします。</span><span class="sxs-lookup"><span data-stu-id="d73e9-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d73e9-126">要件</span><span class="sxs-lookup"><span data-stu-id="d73e9-126">Requirements</span></span>  
 <span data-ttu-id="d73e9-127">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="d73e9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d73e9-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d73e9-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d73e9-129">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="d73e9-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d73e9-130">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d73e9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d73e9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d73e9-131">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="d73e9-132">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d73e9-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)