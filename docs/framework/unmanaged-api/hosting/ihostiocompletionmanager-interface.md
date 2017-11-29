---
title: "IHostIoCompletionManager インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager
helpviewer_keywords: IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 847d4c3aa3e3da94b4aac4679ada047577379f82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="a5683-102">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5683-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="a5683-103">共通言語ランタイム (CLR) にホストによって提供される I/O 完了ポートとやり取りできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5683-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5683-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-104">Methods</span></span>  
  
|<span data-ttu-id="a5683-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-105">Method</span></span>|<span data-ttu-id="a5683-106">説明</span><span class="sxs-lookup"><span data-stu-id="a5683-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5683-107">Bind メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="a5683-108">I/O 完了ポートへのハンドルにバインドします。</span><span class="sxs-lookup"><span data-stu-id="a5683-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="a5683-109">CloseIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="a5683-110">事前に呼び出したを介して作成されたポートを閉じる`CreateIoCompletionPort`です。</span><span class="sxs-lookup"><span data-stu-id="a5683-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="a5683-111">CreateIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="a5683-112">要求のホストが新しい I/O 完了ポートを作成することです。</span><span class="sxs-lookup"><span data-stu-id="a5683-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="a5683-113">GetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="a5683-114">現在の要求を処理していない I/O 完了スレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5683-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="a5683-115">GetHostOverlappedSize メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="a5683-116">ホストが、I/O 要求に追加しようとしています。 カスタム データのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="a5683-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="a5683-117">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="a5683-118">I/O 要求を処理するには、ホストが割り当てることができますのスレッドの最大数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5683-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="a5683-119">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="a5683-120">I/O 要求を処理するには、ホストが提供するスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5683-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="a5683-121">InitializeHostOverlapped メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="a5683-122">I/O 要求についてカスタム データを初期化するために営業案件にホストを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5683-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="a5683-123">SetCLRIoCompletionManager メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="a5683-124">により、ホストへのインターフェイス ポインターで、 [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)インスタンスの CLR によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="a5683-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="a5683-125">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="a5683-126">I/O 要求を処理するため、ホストに割り当てるスレッドの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="a5683-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="a5683-127">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="a5683-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="a5683-128">I/O 完了をホストに割り当てる必要があるスレッドの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="a5683-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5683-129">コメント</span><span class="sxs-lookup"><span data-stu-id="a5683-129">Remarks</span></span>  
 <span data-ttu-id="a5683-130">`IHostIoCompletionManager`対応する、 `ICLRIoCompletionManager` CLR によって実装されるインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a5683-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="a5683-131">CLR のメソッドを呼び出します`IHostIoCompletionManager`ハンドルをホストが提供して、ホストのメソッドを呼び出して、ポートにバインドする`ICLRIoCompletionManager`I/O 要求の完了を報告します。</span><span class="sxs-lookup"><span data-stu-id="a5683-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5683-132">要件</span><span class="sxs-lookup"><span data-stu-id="a5683-132">Requirements</span></span>  
 <span data-ttu-id="a5683-133">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="a5683-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5683-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a5683-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5683-135">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5683-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5683-136">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5683-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5683-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5683-137">See Also</span></span>  
 [<span data-ttu-id="a5683-138">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5683-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)