---
title: "ICorDebugRegisterSet2::GetRegisters メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2.GetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f9deccff09c255b339a22af711906baf23d7df9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="ef26b-102">ICorDebugRegisterSet2::GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="ef26b-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="ef26b-103">(コードが現在実行されているプラットフォーム) の各レジスタの値を取得、特定のビット マスクによって指定されています。</span><span class="sxs-lookup"><span data-stu-id="ef26b-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef26b-104">構文</span><span class="sxs-lookup"><span data-stu-id="ef26b-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef26b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef26b-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="ef26b-106">[in]サイズをバイト単位での`mask`配列。</span><span class="sxs-lookup"><span data-stu-id="ef26b-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="ef26b-107">[in]バイトの配列を各ビットは、レジスタに対応します。</span><span class="sxs-lookup"><span data-stu-id="ef26b-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="ef26b-108">ビットが 1 の場合は、対応するレジスタの値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="ef26b-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="ef26b-109">[in]取得するレジスタの値の数。</span><span class="sxs-lookup"><span data-stu-id="ef26b-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="ef26b-110">[out]配列`CORDB_REGISTER`レジスタの値を受け取る各のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ef26b-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef26b-111">コメント</span><span class="sxs-lookup"><span data-stu-id="ef26b-111">Remarks</span></span>  
 <span data-ttu-id="ef26b-112">`GetRegisters`マスクで指定されているレジスタからの値の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="ef26b-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="ef26b-113">配列にいるマスク ビットが設定されていないレジスタの値が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="ef26b-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="ef26b-114">したがってのサイズ、`regBuffer`配列は、マスク内の 1 の数と等しくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef26b-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="ef26b-115">場合の値`regCount`のセットからマスク、大きい番号のレジスタの値によって示されるレジスタの数は切り捨てられますが、小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="ef26b-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="ef26b-116">場合`regCount`が大きすぎるため、未使用`regBuffer`要素は変更できません。</span><span class="sxs-lookup"><span data-stu-id="ef26b-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="ef26b-117">使用できないレジスタがマスクで示されている場合は、そのレジスタの中間の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="ef26b-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="ef26b-118">`ICorDebugRegisterSet2::GetRegisters`メソッドが 64 を超えるレジスタである必要がプラットフォームに必要です。</span><span class="sxs-lookup"><span data-stu-id="ef26b-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="ef26b-119">たとえば、IA64 が 128 の汎用レジスタと 128 の浮動小数点レジスタ ビット マスク内の 64 ビットを超える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef26b-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="ef26b-120">X86 などのプラットフォームの場合と同様に、64 を超えるレジスタを持っていない場合、`GetRegisters`メソッドは実際には、バイト、変換、`mask`バイトの配列、`ULONG64`しを呼び出して、 [ICorDebugRegisterSet:。GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)を受け取るメソッド、`ULONG64`マスク。</span><span class="sxs-lookup"><span data-stu-id="ef26b-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef26b-121">要件</span><span class="sxs-lookup"><span data-stu-id="ef26b-121">Requirements</span></span>  
 <span data-ttu-id="ef26b-122">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="ef26b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef26b-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef26b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef26b-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef26b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef26b-125">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef26b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef26b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef26b-126">See Also</span></span>  
 [<span data-ttu-id="ef26b-127">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ef26b-127">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="ef26b-128">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ef26b-128">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)