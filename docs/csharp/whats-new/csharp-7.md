---
title: "C# 7 の新機能 - C# ガイド"
description: "C# 言語の次期バージョン 7 で導入される新機能の概要を示します。"
keywords: "C#, .NET, .NET Core, 最新機能, 新機能"
author: BillWagner
ms.author: wiwagn
ms.date: 12/21/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 3f3598fce5abeb67b772f51ed6f93e6ada4c92d0
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2017
---
# <a name="whats-new-in-c-7"></a><span data-ttu-id="a7f2b-104">C# 7 の新機能</span><span class="sxs-lookup"><span data-stu-id="a7f2b-104">What's new in C# 7</span></span>

<span data-ttu-id="a7f2b-105">C# 7 では、C# 言語に多くの新機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-105">C# 7 adds a number of new features to the C# language:</span></span>
* [<span data-ttu-id="a7f2b-106">`out` 変数</span><span class="sxs-lookup"><span data-stu-id="a7f2b-106">`out` variables</span></span>](#out-variables)
    - <span data-ttu-id="a7f2b-107">`out` の値は、それが使用されるメソッドの引数としてインラインで宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-107">You can declare `out` values inline as arguments to the method where they are used.</span></span>
* [<span data-ttu-id="a7f2b-108">タプル</span><span class="sxs-lookup"><span data-stu-id="a7f2b-108">Tuples</span></span>](#tuples)
    - <span data-ttu-id="a7f2b-109">複数のパブリック フィールドを含む、軽量で名前のない型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-109">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="a7f2b-110">コンパイラおよび IDE ツールでは、このような型のセマンティクスが認識されます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-110">Compilers and IDE tools understand the semantics of these types.</span></span>
* [<span data-ttu-id="a7f2b-111">破棄</span><span class="sxs-lookup"><span data-stu-id="a7f2b-111">Discards</span></span>](#discards)
    - <span data-ttu-id="a7f2b-112">破棄は、割り当てられた値を考慮しない場合に割り当てで使用された、一時的な書き込み専用の値です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-112">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="a7f2b-113">タプルおよびユーザー定義の型を分解する場合や、メソッドを `out` パラメーターを使用して呼び出す場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-113">They are particularly useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
* [<span data-ttu-id="a7f2b-114">パターン一致</span><span class="sxs-lookup"><span data-stu-id="a7f2b-114">Pattern Matching</span></span>](#pattern-matching)
    - <span data-ttu-id="a7f2b-115">これらの型のメンバーの任意の型と値に基づいて、分岐ロジックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-115">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
* [<span data-ttu-id="a7f2b-116">`ref` ローカル変数と戻り値</span><span class="sxs-lookup"><span data-stu-id="a7f2b-116">`ref` locals and returns</span></span>](#ref-locals-and-returns)
    - <span data-ttu-id="a7f2b-117">メソッド引数とローカル変数は、他のストレージへの参照になります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-117">Method arguments and local variables can be references to other storage.</span></span>
* [<span data-ttu-id="a7f2b-118">ローカル関数</span><span class="sxs-lookup"><span data-stu-id="a7f2b-118">Local Functions</span></span>](#local-functions)
    - <span data-ttu-id="a7f2b-119">関数を他の関数の中に入れ子にして、関数のスコープと可視性を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-119">You can nest functions inside other functions to limit their scope and visibility.</span></span>
* [<span data-ttu-id="a7f2b-120">式形式のメンバーの追加</span><span class="sxs-lookup"><span data-stu-id="a7f2b-120">More expression-bodied members</span></span>](#more-expression-bodied-members)
    - <span data-ttu-id="a7f2b-121">式を使用して作成できるメンバーが増加しました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-121">The list of members that can be authored using expressions has grown.</span></span>
* [<span data-ttu-id="a7f2b-122">`throw` 式</span><span class="sxs-lookup"><span data-stu-id="a7f2b-122">`throw` Expressions</span></span>](#throw-expressions)
    - <span data-ttu-id="a7f2b-123">`throw` がステートメントだったためにこれまで許可されなかったコード コンストラクトで例外をスローできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-123">You can throw exceptions in code constructs that previously were not allowed because `throw` was a statement.</span></span> 
* [<span data-ttu-id="a7f2b-124">一般化された async の戻り値の型</span><span class="sxs-lookup"><span data-stu-id="a7f2b-124">Generalized async return types</span></span>](#generalized-async-return-types)
    - <span data-ttu-id="a7f2b-125">`async` 修飾子を使って宣言したメソッドは、`Task` と `Task<T>` に加えて他の型を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-125">Methods declared with the `async` modifier can return other types in addition to `Task` and `Task<T>`.</span></span>
* [<span data-ttu-id="a7f2b-126">数値リテラルの構文の改善</span><span class="sxs-lookup"><span data-stu-id="a7f2b-126">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
    - <span data-ttu-id="a7f2b-127">新しいトークンにより、数値定数の読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-127">New tokens improve readability for numeric constants.</span></span>

<span data-ttu-id="a7f2b-128">このトピックの残りの部分では、各機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-128">The remainder of this topic discusses each of the features.</span></span> <span data-ttu-id="a7f2b-129">機能ごとに、その背後にある論拠のほか、</span><span class="sxs-lookup"><span data-stu-id="a7f2b-129">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="a7f2b-130">構文についても説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-130">You'll learn the syntax.</span></span> <span data-ttu-id="a7f2b-131">また、新機能の使用により、開発者としての生産性が向上するサンプル シナリオもいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-131">You'll see some sample scenarios where using the new feature will make you more productive as a developer.</span></span> 

## <a name="out-variables"></a><span data-ttu-id="a7f2b-132">`out` 変数</span><span class="sxs-lookup"><span data-stu-id="a7f2b-132">`out` variables</span></span>

<span data-ttu-id="a7f2b-133">`out` パラメーターをサポートする既存の構文は、このバージョンで改良されました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-133">The existing syntax that supports `out` parameters has been improved in this version.</span></span>  

<span data-ttu-id="a7f2b-134">以前は、out 変数の宣言とその初期化を 2 つの異なるステートメントに分離する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-134">Previously, you would need to separate the declaration of the out variable and its initialization into two different statements:</span></span>

[!code-csharp[OutVariableOldStyle](../../../samples/snippets/csharp/new-in-7/program.cs#03_OutVariableOldStyle "classic out variable declaration")]

<span data-ttu-id="a7f2b-135">現在は、別の宣言ステートメントを記述するのではなく、メソッド呼び出しの引数リストで `out` 変数を宣言できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-135">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#01_OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="a7f2b-136">上記のように、わかりやすくするために `out` 変数の型を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-136">You may want to specify the type of the `out` variable for clarity, as shown above.</span></span> <span data-ttu-id="a7f2b-137">ただし、この言語では、次のように暗黙的に型指定されたローカル変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-137">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#02_OutVarVariableDeclarations "Implicitly typed Out variable")]

* <span data-ttu-id="a7f2b-138">コードが読みやすくなる。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-138">The code is easier to read.</span></span> 
    - <span data-ttu-id="a7f2b-139">out 変数は、使用する場所で宣言します。その場所より上にある別の行で宣言しません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-139">You declare the out variable where you use it, not on another line above.</span></span>
* <span data-ttu-id="a7f2b-140">初期値を割り当てる必要がない。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-140">No need to assign an initial value.</span></span>
    - <span data-ttu-id="a7f2b-141">`out` 変数は、メソッド呼び出し内の使用場所で宣言することにより、割り当てる前に誤って使用することがなくなります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-141">By declaring the `out` variable where it is used in a method call, you can't accidentally use it before it is assigned.</span></span>

<span data-ttu-id="a7f2b-142">この機能の最も一般的な用途は `Try` パターンになります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-142">The most common use for this feature will be the `Try` pattern.</span></span> <span data-ttu-id="a7f2b-143">このパターンでは、メソッドは、成功または失敗を示す `bool` と、メソッドが成功した場合に結果を提供する `out` 変数を返します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-143">In this pattern, a method returns a `bool` indicating success or failure and an `out` variable that provides the result if the method succeeds.</span></span>

<span data-ttu-id="a7f2b-144">`out` 変数の宣言を使用すると、宣言された変数は if ステートメントの外側のスコープに "リーク" されます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-144">When using the `out` variable declaration, the declared variable "leaks" into the outer scope of the if statement.</span></span> <span data-ttu-id="a7f2b-145">これにより、その後はこの変数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-145">This allows you to use the variable afterwards:</span></span>

```csharp
if (!int.TryParse(input, out int result))
{    
    return null;
}

return result;
```

## <a name="tuples"></a><span data-ttu-id="a7f2b-146">タプル</span><span class="sxs-lookup"><span data-stu-id="a7f2b-146">Tuples</span></span>

> [!NOTE]
> <span data-ttu-id="a7f2b-147">新しいタプル機能を使用するには、<xref:System.ValueTuple> 型が必要です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-147">The new tuples features require the <xref:System.ValueTuple> types.</span></span>
> <span data-ttu-id="a7f2b-148">型が含まれていないプラットフォームで使用する場合は、NuGet パッケージ [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-148">You must add the NuGet package [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) in order to use it on platforms that do not include the types.</span></span>
>
> <span data-ttu-id="a7f2b-149">これは、フレームワークで提供される型に依存するその他の言語機能に似ています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-149">This is similar to other language features that rely on types delivered in the framework.</span></span> <span data-ttu-id="a7f2b-150">たとえば、`INotifyCompletion` インターフェイスに依存する `async` や `await`、`IEnumerable<T>` に依存する LINQ などがあります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-150">Example include `async` and `await` relying on the `INotifyCompletion` interface, and LINQ relying on `IEnumerable<T>`.</span></span> <span data-ttu-id="a7f2b-151">ただし、.NET がプラットフォームにさらに依存しなくなりつつあるため、配信メカニズムもそれに応じて変わりつつあります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-151">However, the delivery mechanism is changing as .NET is becoming more platform independent.</span></span> <span data-ttu-id="a7f2b-152">.NET Framework が、言語コンパイラと同じ周期で配布されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-152">The .NET Framework may not always ship on the same cadence as the language compiler.</span></span> <span data-ttu-id="a7f2b-153">新しい言語機能が新しい型に依存する場合、それらの型は、言語機能の配布時に NuGet パッケージとして入手できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-153">When new language features rely on new types, those types will be available as NuGet packages when the language features ship.</span></span> <span data-ttu-id="a7f2b-154">これらの新しい型は .NET 標準 API に追加され、フレームワークの一部として配信されるため、NuGet パッケージは必要なくなります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-154">As these new types get added to the .NET Standard API and delivered as part of the framework, the NuGet package requirement will be removed.</span></span>

<span data-ttu-id="a7f2b-155">C# には、設計の意図を説明するために使用される、クラスと構造体の豊富な構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-155">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="a7f2b-156">ところが、場合によっては、その豊富な構文を使用するために、余分な作業が必要になることがあります。この場合、メリットはごくわずかです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-156">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="a7f2b-157">複数のデータ要素を含む単純な構造を必要とするメソッドを記述することはよくあります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-157">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="a7f2b-158">このようなシナリオをサポートするために、C# には "*タプル*" が追加されました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-158">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="a7f2b-159">タプルとは、データ メンバーを表す複数のフィールドを含む軽量なデータ構造です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-159">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span>
<span data-ttu-id="a7f2b-160">フィールドは検証されず、独自のメソッドを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-160">The fields are not validated, and you cannot define your own methods</span></span>

> [!NOTE]
> <span data-ttu-id="a7f2b-161">タプルは C# 7 より前で使用できましたが、効率的でなく、言語サポートがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-161">Tuples were available before C# 7, but they were inefficient and had no language support.</span></span>
> <span data-ttu-id="a7f2b-162">これは、タプル要素が `Item1` や `Item2` などとしてのみ参照できることを意味しました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-162">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="a7f2b-163">C# 7 では、タプルの言語サポートが導入されたことで、新しい、より効率的なタプル型を使用するフィールドのセマンティック名が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-163">C# 7 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="a7f2b-164">タプルを作成するには、各メンバーを値に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-164">You can create a tuple by assigning each member to a value:</span></span>

[!code-csharp[UnnamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#04_UnnamedTuple "Unnamed tuple")]

<span data-ttu-id="a7f2b-165">その割り当てによってメンバーが `Item1` と `Item2` のタプルが作成され、<xref:System.Tuple> と同じようにして使用できるようになります。構文を変更してタプルの各メンバーにセマンティック名を提供するタプルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-165">That assignment creates a tuple whose members are `Item1` and `Item2`, which you can use in the same way as <xref:System.Tuple> You can change the syntax to create a tuple that provides semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#05_NamedTuple "Named tuple")]

<span data-ttu-id="a7f2b-166">`namedLetters` タプルには、`Alpha` と `Beta` と呼ばれるフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-166">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="a7f2b-167">これらの名前は、コンパイル時にのみ存在し、実行時にリフレクションを使用してタプルを検査するときなどには保持されません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-167">Those names exist only at compile time and are not preserved for example when inspecting the tuple using reflection at runtime.</span></span>

<span data-ttu-id="a7f2b-168">タプルの割り当てでは、代入の右辺でフィールドの名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-168">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#06_ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="a7f2b-169">代入の左辺と右辺の両方でフィールドの名前を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-169">You can specify names for the fields on both the left and right-hand side of the assignment:</span></span>

[!code-csharp[NamedTupleConflict](../../../samples/snippets/csharp/new-in-7/program.cs#07_NamedTupleConflict "Named tuple conflict")]

<span data-ttu-id="a7f2b-170">上記の行では、警告 `CS8123` が生成されます。これは、代入の右辺にある名前 (`Alpha` と `Beta`) が左辺にある名前 (`First` と `Second`) と競合するために無視されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-170">The line above generates a warning, `CS8123`, telling you that the names on the right side of the assignment, `Alpha` and `Beta` are ignored because they conflict with the names on the left side, `First` and `Second`.</span></span>

<span data-ttu-id="a7f2b-171">上の例では、タプルを宣言する基本的な構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-171">The examples above show the basic syntax to declare tuples.</span></span> <span data-ttu-id="a7f2b-172">タプルは、`private` メソッドと `internal` メソッドの戻り値の型として最も有用です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-172">Tuples are most useful as return types for `private` and `internal` methods.</span></span> <span data-ttu-id="a7f2b-173">タプルには、これらのメソッドが複数の不連続値を返すための簡単な構文が用意されています。そのため、返される型を定義する `class` または `struct` を作成するという手間を省くことができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-173">Tuples provide a simple syntax for those methods to return multiple discrete values: You save the work of authoring a `class` or a `struct` that defines the type returned.</span></span> <span data-ttu-id="a7f2b-174">新しい型を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-174">There is no need for creating a new type.</span></span>

<span data-ttu-id="a7f2b-175">タプルの作成は、より効率的かつ生産的です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-175">Creating a tuple is more efficient and more productive.</span></span>
<span data-ttu-id="a7f2b-176">タプルは、複数の値を保持するデータ構造を定義するための、よりシンプルで軽量な構文です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-176">It is a simpler, lightweight syntax to define a data structure that carries more than one value.</span></span> <span data-ttu-id="a7f2b-177">次の例のメソッドは、整数のシーケンス内で見つかった最小値と最大値を返します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-177">The example method below returns the minimum and maximum values found in a sequence of integers:</span></span>

[!code-csharp[TupleReturningMethod](../../../samples/snippets/csharp/new-in-7/program.cs#08_TupleReturningMethod "Tuple returning method")]

<span data-ttu-id="a7f2b-178">このようにタプルを使用すると、いくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-178">Using tuples in this way offers several advantages:</span></span>

* <span data-ttu-id="a7f2b-179">返される型を定義する `class` または `struct` を作成する手間がかからない。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-179">You save the work of authoring a `class` or a `struct` that defines the type returned.</span></span> 
* <span data-ttu-id="a7f2b-180">新しい型を作成する必要がない。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-180">You do not need to create new type.</span></span>
* <span data-ttu-id="a7f2b-181">言語の拡張により、<xref:System.Tuple.Create``1(``0)> メソッドを呼び出す必要がなくなる。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-181">The language enhancements removes the need to call the <xref:System.Tuple.Create``1(``0)> methods.</span></span>

<span data-ttu-id="a7f2b-182">メソッドの宣言では、返されるタプルのフィールドに名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-182">The declaration for the method provides the names for the fields of the tuple that is returned.</span></span> <span data-ttu-id="a7f2b-183">このメソッドを呼び出した場合の戻り値は、`Max` と `Min` というフィールドを含むタプルです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-183">When you call the method, the return value is a tuple whose fields are `Max` and `Min`:</span></span>

[!code-csharp[CallingTupleMethod](../../../samples/snippets/csharp/new-in-7/program.cs#09_CallingTupleMethod "Calling a tuple returning method")]

<span data-ttu-id="a7f2b-184">状況によっては、メソッドから返されたタプルのメンバーをばらすことが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-184">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="a7f2b-185">そのためには、タプル内のそれぞれの値に対して別個の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-185">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="a7f2b-186">この操作は、タプルの "*分解*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-186">This is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](../../../samples/snippets/csharp/new-in-7/program.cs#10_CallingWithDeconstructor "Deconstructing a tuple")]

<!-- Add wildcards here, if they are in C# 7
-->

<span data-ttu-id="a7f2b-187">.NET でも任意の型に同様の分解を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-187">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="a7f2b-188">そのためには、`Deconstruct` メソッドをクラスのメンバーとして記述します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-188">This is done by writing a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="a7f2b-189">その `Deconstruct` メソッドは、抽出する各プロパティ用に一連の `out` 引数を提供します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-189">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="a7f2b-190">次の `Point` クラスを考えてみましょう。このクラスは、`X` 座標と `Y` 座標を抽出するデコンストラクター メソッドを指定しています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-190">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](../../../samples/snippets/csharp/new-in-7/point.cs#11_PointWithDeconstruction "Point with deconstruction method")]
 
<span data-ttu-id="a7f2b-191">`Point` にタプルを割り当てることで、個々のフィールドを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-191">You can extract the individual fields by assigning a tuple to a `Point`:</span></span>

[!code-csharp[DeconstructPoint](../../../samples/snippets/csharp/new-in-7/program.cs#12_DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="a7f2b-192">`Deconstruct` メソッドで定義された名前に制約されません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-192">You are not bound by the names defined in the `Deconstruct` method.</span></span> <span data-ttu-id="a7f2b-193">割り当ての一環として、抽出変数の名前を変更してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-193">You can rename the extract variables as part of the assignment:</span></span>  

[!code-csharp[DeconstructNames](../../../samples/snippets/csharp/new-in-7/program.cs#13_DeconstructNames "Deconstruct with new names")]

<span data-ttu-id="a7f2b-194">タプルの詳細については、[タプルのトピック](../tuples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-194">You can learn more in depth about tuples in the [tuples topic](../tuples.md).</span></span>

## <a name="discards"></a><span data-ttu-id="a7f2b-195">破棄</span><span class="sxs-lookup"><span data-stu-id="a7f2b-195">Discards</span></span>

<span data-ttu-id="a7f2b-196">`out` パラメーターを使用してタプルを分解したりメソッドを呼び出したりする場合に、使用する予定がなく、考慮にも入れない値の変数の定義を強制されることが多くあります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-196">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="a7f2b-197">C# ではこのシナリオを処理するために*破棄*のサポートを追加しています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-197">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="a7f2b-198">破棄は名前が `_` (アンダースコア (_) 文字) の書き込み専用の変数で、破棄するすべての値をこの 1 つの変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-198">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="a7f2b-199">破棄は未割り当ての変数に似ています。代入ステートメントとは異なり、破棄はコードで使用できません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-199">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="a7f2b-200">次のシナリオでは破棄はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-200">Discards are supported in the following scenarios:</span></span>

* <span data-ttu-id="a7f2b-201">タプルまたはユーザー定義の型を分解する場合。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-201">When deconstructing tuples or user-defined types.</span></span>

* <span data-ttu-id="a7f2b-202">[out](../language-reference/keywords/out.md) パラメーターを使用してメソッドを呼び出す場合。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-202">When calling methods with [out](../language-reference/keywords/out.md) parameters.</span></span>

* <span data-ttu-id="a7f2b-203">[is](../language-reference/keywords/is.md) および [switch](../language-reference/keywords/switch.md) ステートメントによるパターン マッチング操作。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-203">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>

* <span data-ttu-id="a7f2b-204">割り当ての値を破棄として明示的に識別する必要がある場合の、スタンドアロン識別子。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-204">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="a7f2b-205">次の例は、ある都市の 2 つの異なる年度のデータを含む 6 つのタプルを戻す `QueryCityDataForYears` メソッドを定義しています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-205">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains a data for a city for two different years.</span></span> <span data-ttu-id="a7f2b-206">この例のメソッド呼び出しでは、メソッドによって戻された 2 つの人口の値のみが考慮されているため、タプルの残りの値はタプルの分解時に破棄として扱われます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-206">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](../../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="a7f2b-207">詳細については、[破棄](../discards.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-207">For more information, see [Discards](../discards.md).</span></span>
 
## <a name="pattern-matching"></a><span data-ttu-id="a7f2b-208">パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="a7f2b-208">Pattern matching</span></span>

<span data-ttu-id="a7f2b-209">"*パターン マッチング*" は、オブジェクトの型以外のプロパティでメソッドのディスパッチを実装できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-209">*Pattern matching* is a feature that allows you to implement method dispatch on properties other than the type of an object.</span></span> <span data-ttu-id="a7f2b-210">オブジェクトの型に基づいたメソッドのディスパッチに慣れている方も多いはずです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-210">You're probably already familiar with method dispatch based on the type of an object.</span></span> <span data-ttu-id="a7f2b-211">オブジェクト指向プログラミングでは、仮想メソッドとオーバーライド メソッドには、オブジェクトの型に基づくメソッドのディスパッチを実装するための言語構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-211">In Object Oriented programming, virtual and override methods provide language syntax to implement method dispatching based on an object's type.</span></span> <span data-ttu-id="a7f2b-212">基底クラスと派生クラスは異なる実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-212">Base and Derived classes provide different implementations.</span></span> <span data-ttu-id="a7f2b-213">パターン マッチング式により、この概念が拡張されたため、継承階層を介して関連していない型やデータ要素に同様のディスパッチ パターンを簡単に実装できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-213">Pattern matching expressions extend this concept so that you can easily implement similar dispatch patterns for types and data elements that are not related through an inheritance hierarchy.</span></span> 

<span data-ttu-id="a7f2b-214">パターン マッチングでは、`is` 式と `switch` 式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-214">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="a7f2b-215">どちらの式でも、オブジェクトとそのプロパティを検査して、そのオブジェクトが必要なパターンを満たしているかどうかを判定できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-215">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="a7f2b-216">パターンに追加の規則を指定するには、`when` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-216">You use the `when` keyword to specify additional rules to the pattern.</span></span>

### <a name="is-expression"></a><span data-ttu-id="a7f2b-217">`is` 式</span><span class="sxs-lookup"><span data-stu-id="a7f2b-217">`is` expression</span></span>

<span data-ttu-id="a7f2b-218">`is` パターン式を使用すると、使い慣れた `is` 演算子を拡張して、その型を超えてオブジェクトを照会できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-218">The `is` pattern expression extends the familiar `is` operator to query an object beyond its type.</span></span>

<span data-ttu-id="a7f2b-219">では、簡単なシナリオから始めましょう。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-219">Let's start with a simple scenario.</span></span> <span data-ttu-id="a7f2b-220">ここでは、関連付けられていない型を操作するアルゴリズムをパターン マッチング式で簡単にする方法を示すために、いくつかの機能をこのシナリオに追加します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-220">We'll add capabilities to this scenario that demonstrate how pattern matching expressions make algorithms that work with unrelated types easy.</span></span> <span data-ttu-id="a7f2b-221">まず、サイコロの出目の合計を計算するメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-221">We'll start with a method that computes the sum of a number of die rolls:</span></span>

[!code-csharp[SumDieRolls](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#14_SumDieRolls "Sum die rolls")]

<span data-ttu-id="a7f2b-222">複数のサイコロを使った場合はそれぞれの出目の合計を求める必要があることがすぐにわかります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-222">You might quickly find that you need to find the sum of die rolls where some of the rolls are made with multiple dice (dice is the plural of die).</span></span> <span data-ttu-id="a7f2b-223">入力シーケンスの一部は、単一の数字ではなく複数の結果になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-223">Part of the input sequence may be multiple results instead of a single number:</span></span>

[!code-csharp[SumDieRollsWithGroups](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#15_SumDieRollsWithGroups "Sum die rolls with groups")]

<span data-ttu-id="a7f2b-224">このシナリオでは、`is` パターン式が非常にうまく機能します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-224">The `is` pattern expression works quite well in this scenario.</span></span> <span data-ttu-id="a7f2b-225">型のチェックの一環として、変数の初期化を記述します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-225">As part of checking the type, you write a variable initialization.</span></span> <span data-ttu-id="a7f2b-226">これにより、検証されたランタイム型の新しい変数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-226">This creates a new variable of the validated runtime type.</span></span>

<span data-ttu-id="a7f2b-227">これらのシナリオをさらに拡張していくと、さらに多くの `if` ステートメントと `else if` ステートメントを作成することになります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-227">As you keep extending these scenarios, you may find that you build more `if` and `else if` statements.</span></span> <span data-ttu-id="a7f2b-228">それが扱いにくくなったら、`switch` パターン式に切り替えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-228">Once that becomes unwieldy, you'll likely want to switch to `switch` pattern expressions.</span></span>

### <a name="switch-statement-updates"></a><span data-ttu-id="a7f2b-229">`switch` ステートメントの更新</span><span class="sxs-lookup"><span data-stu-id="a7f2b-229">`switch` statement updates</span></span>

<span data-ttu-id="a7f2b-230">"*一致式*" には、既に C# 言語に含まれている `switch` ステートメントに基づいた、使い慣れた構文があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-230">The *match expression* has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="a7f2b-231">ここで、新しいケースを追加する前に、一致式を使用するように既存のコードを変換してみましょう。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-231">Let's translate the existing code to use a match expression before adding new cases:</span></span> 

[!code-csharp[SumUsingSwitch](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#16_SumUsingSwitch "Sum using switch")]

<span data-ttu-id="a7f2b-232">一致式の構文は `is` 式の構文とは若干異なり、型と変数を `case` 式の先頭で宣言します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-232">The match expressions have a slightly different syntax than the `is` expressions, where you declare the type and variable at the beginning of the `case` expression.</span></span>

<span data-ttu-id="a7f2b-233">一致式では定数もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-233">The match expressions also support constants.</span></span> <span data-ttu-id="a7f2b-234">これにより、単純なケースが取り除かれるため、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-234">This can save time by factoring out simple cases:</span></span>

[!code-csharp[SwitchWithConstants](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#17_SwitchWithConstants "Switch with constants")]

<span data-ttu-id="a7f2b-235">上のコードでは、`int` の特殊なケースとして `0` のケース、入力がない場合の特殊なケースとして `null` のケースが追加されています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-235">The code above adds cases for `0` as a special case of `int`, and `null` as a special case when there is no input.</span></span> <span data-ttu-id="a7f2b-236">これは、switch パターン式の重要な新機能の 1 つを示しています。ここでは、`case` 式の順序が重要になります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-236">This demonstrates one important new feature in switch pattern expressions: the order of the `case` expressions now matters.</span></span> <span data-ttu-id="a7f2b-237">`0` のケースは、一般的な `int` のケースの前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-237">The `0` case must appear before the general `int` case.</span></span> <span data-ttu-id="a7f2b-238">そうしないと、一致する最初のパターンは、値が `0` であっても `int` のケースになります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-238">Otherwise, the first pattern to match would be the `int` case, even when the value is `0`.</span></span> <span data-ttu-id="a7f2b-239">後のケースが先に処理されるように一致式の順序を誤って指定すると、コンパイラはそこにフラグを設定し、エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-239">If you accidentally order match expressions such that a later case has already been handled, the compiler will flag that and generate an error.</span></span>

<span data-ttu-id="a7f2b-240">これと同じ動作により、空の入力シーケンスに対する特殊なケースにも対応できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-240">This same behavior enables the special case for an empty input sequence.</span></span>
<span data-ttu-id="a7f2b-241">このコードから、要素を持つ `IEnumerable` 項目のケースは一般的な `IEnumerable` ケースの前に配置する必要があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-241">You can see that the case for an `IEnumerable` item that has elements must appear before the general `IEnumerable` case.</span></span>

<span data-ttu-id="a7f2b-242">このバージョンでは、`default` ケースも追加されています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-242">This version has also added a `default` case.</span></span> <span data-ttu-id="a7f2b-243">`default` ケースは、常に最後に評価されます。ソース内で記述される順序は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-243">The `default` case is always evaluated last, regardless of the order it appears in the source.</span></span> <span data-ttu-id="a7f2b-244">そのため、慣習として、`default` ケースを最後に配置します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-244">For that reason, convention is to put the `default` case last.</span></span>

<span data-ttu-id="a7f2b-245">最後に、新しいスタイルのサイコロ用に最後の `case` を追加しましょう。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-245">Finally, let's add one last `case` for a new style of die.</span></span> <span data-ttu-id="a7f2b-246">ゲームによっては、より広範な数字を表すためにパーセンタイル ダイスが使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-246">Some games use percentile dice to represent larger ranges of numbers.</span></span> 

> [!NOTE]
> <span data-ttu-id="a7f2b-247">10 面のパーセンタイル ダイスを 2 つ使用すると、0 から 99 までのすべての数字を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-247">Two 10-sided percentile dice can represent every number from 0 through 99.</span></span> <span data-ttu-id="a7f2b-248">1 つのサイコロの面には、`00`、`10`、`20`、`90` のようなラベルが付けられています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-248">One die has sides labelled `00`, `10`, `20`, ... `90`.</span></span> <span data-ttu-id="a7f2b-249">もう 1 つのサイコロの面には、`0`、`1`、`2`、`9` のようなラベルが付けられています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-249">The other die has sides labeled `0`, `1`, `2`, ... `9`.</span></span> <span data-ttu-id="a7f2b-250">2 つのサイコロの数字を加算すると、0 から 99 までのすべての数字を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-250">Add the two die values together and you can get every number from 0 through 99.</span></span>

<span data-ttu-id="a7f2b-251">この種類のサイコロをコレクションに追加するには、まずパーセンタイル ダイスを表す型を定義します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-251">To add this kind of die to your collection, first define a type to represent the percentile dice.</span></span> <span data-ttu-id="a7f2b-252">`TensDigit` プロパティは値 `0`、`10`、`20` を、最大 `90` まで格納します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-252">The `TensDigit` property stores values `0`, `10`, `20`, up to `90`:</span></span>

[!code-csharp[18_PercentileDice](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#18_PercentileDice "Percentile Die type")]

<span data-ttu-id="a7f2b-253">次に、新しい型の `case` 一致式を追加します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-253">Then, add a `case` match expression for the new type:</span></span>

[!code-csharp[SwitchWithNewTypes](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#19_SwitchWithNewTypes "Include Percentile Die type")]

<span data-ttu-id="a7f2b-254">パターン マッチング式の新しい構文を使用すると、オブジェクトの型やその他のプロパティに基づいたディスパッチ アルゴリズムを、明確かつ簡潔な構文を使用して簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-254">The new syntax for pattern matching expressions makes it easier to create dispatch algorithms based on an object's type, or other properties, using a clear and concise syntax.</span></span> <span data-ttu-id="a7f2b-255">パターン マッチング式は、継承によって関連付けられていないデータ型に対してこれらのコンストラクトを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-255">Pattern matching expressions enable these constructs on data types that are unrelated by inheritance.</span></span>

<span data-ttu-id="a7f2b-256">パターン マッチングの詳細については、[C# のパターン マッチング](../pattern-matching.md)に特化したトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-256">You can learn more about pattern matching in the topic dedicated to [pattern matching in C#](../pattern-matching.md).</span></span>

## <a name="ref-locals-and-returns"></a><span data-ttu-id="a7f2b-257">ref ローカル変数と戻り値</span><span class="sxs-lookup"><span data-stu-id="a7f2b-257">Ref locals and returns</span></span>

<span data-ttu-id="a7f2b-258">この機能により、他の場所に定義されている変数への参照を使用したり返したりするアルゴリズムが実現します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-258">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="a7f2b-259">1 つの例として、大規模なマトリックスを使用していて、特定の特性を持つ 1 つの場所を探します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-259">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="a7f2b-260">1 つのメソッドでは、マトリックス内の単一の場所に 2 つのインデックスが返されます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-260">One method would return the two indices for a single location in the matrix:</span></span>

[!code-csharp[FindReturningIndices](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#20_FindReturningIndices "Find returning indices")]

<span data-ttu-id="a7f2b-261">このコードには多くの問題があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-261">There are many issues with this code.</span></span> <span data-ttu-id="a7f2b-262">まず、これは、タプルを返すパブリック メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-262">First of all, it's a public method that's returning a tuple.</span></span> <span data-ttu-id="a7f2b-263">この言語ではこれがサポートされていますが、パブリック API にはユーザー定義型 (クラスまたは構造体) をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-263">The language supports this, but user defined types (either classes or structs) are preferred for public APIs.</span></span>

<span data-ttu-id="a7f2b-264">2 つ目に、このメソッドは、マトリックスの項目のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-264">Second, this method is returning the indices to the item in the matrix.</span></span>
<span data-ttu-id="a7f2b-265">そのため、呼び出し元は、これらのインデックスを使用してマトリックスを逆参照し、1 つの要素を変更するコードを記述することになります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-265">That leads callers to write code that uses those indices to dereference the matrix and modify a single element:</span></span>

[!code-csharp[UpdateItemFromIndices](../../../samples/snippets/csharp/new-in-7/program.cs#21_UpdateItemFromIndices "Update Item From Indices")]

<span data-ttu-id="a7f2b-266">それよりも、変更するマトリックス内の要素への "*参照*" を返すメソッドを記述することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-266">You'd rather write a method that returns a *reference* to the element of the matrix that you want to change.</span></span> <span data-ttu-id="a7f2b-267">これを実現するには、アンセーフ コードを使用し、前のバージョンの `int` へのポインターを返す方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-267">You could only accomplish this by using unsafe code and returning a pointer to an `int` in previous versions.</span></span>

<span data-ttu-id="a7f2b-268">それでは、一連の変更を確認しながら、ref ローカル変数の機能と、内部ストレージへの参照を返すメソッドの作成方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-268">Let's walk through a series of changes to demonstrate the ref local feature and show how to create a method that returns a reference to internal storage.</span></span>
<span data-ttu-id="a7f2b-269">その過程で、ref 戻り値および ref ローカル変数の機能の誤用を防ぐための規則についても説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-269">Along the way, you'll learn the rules of the ref return and ref local feature that protects you from accidentally misusing it.</span></span>

<span data-ttu-id="a7f2b-270">まず、タプルの代わりに `ref int` を返すように `Find` メソッドの宣言を変更します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-270">Start by modifying the `Find` method declaration so that it returns a `ref int` instead of a tuple.</span></span> <span data-ttu-id="a7f2b-271">次に、2 つのインデックスの代わりに、マトリックスに格納されている値を返すように、return ステートメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-271">Then, modify the return statement so it returns the value stored in the matrix instead of the two indices:</span></span>

```csharp
// Note that this won't compile. 
// Method declaration indicates ref return,
// but return statement specifies a value return.
public static ref int Find2(int[,] matrix, Func<int, bool> predicate)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
        for (int j = 0; j < matrix.GetLength(1); j++)
            if (predicate(matrix[i, j]))
                return matrix[i, j];
    throw new InvalidOperationException("Not found");
}
```

<span data-ttu-id="a7f2b-272">メソッドが `ref` 変数を返すことを宣言する際に、それぞれの return ステートメントに `ref` キーワードも追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-272">When you declare that a method returns a `ref` variable, you must also add the `ref` keyword to each return statement.</span></span> <span data-ttu-id="a7f2b-273">これは、参照渡しを示します。これにより、後でコードを読む開発者にも、そのメソッドが参照渡しで返すことがわかります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-273">That indicates return by reference, and helps developers reading the code later remember that the method returns by reference:</span></span>

[!code-csharp[FindReturningRef](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#22_FindReturningRef "Find returning by reference")]

<span data-ttu-id="a7f2b-274">このメソッドはマトリックス内の整数値への参照を返すため、呼び出される場所を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-274">Now that the method returns a reference to the integer value in the matrix, you need to modify where it's called.</span></span>  <span data-ttu-id="a7f2b-275">`var` 宣言は、`valItem` がタプルではなく `int` であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-275">The `var` declaration means that `valItem` is now an `int` rather than a tuple:</span></span>

[!code-csharp[AssignRefReturnToValue](../../../samples/snippets/csharp/new-in-7/program.cs#23_AssignRefReturnToValue "Assign ref return to value")]

<span data-ttu-id="a7f2b-276">上記の例の 2 番目の `WriteLine` ステートメントで出力される値は `42` であり、`24` ではありません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-276">The second `WriteLine` statement in the example above prints out the value `42`, not `24`.</span></span> <span data-ttu-id="a7f2b-277">変数 `valItem` は、`int` であり、`ref int` ではありません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-277">The variable `valItem` is an `int`, not a `ref int`.</span></span> <span data-ttu-id="a7f2b-278">`var` キーワードを使用すると、コンパイラは、型を指定できますが、`ref` 修飾子を暗黙的に追加しません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-278">The `var` keyword enables the compiler to specify the type, but will not implicitly add the `ref` modifier.</span></span> <span data-ttu-id="a7f2b-279">代わりに、`ref return` によって参照される値が代入の左辺にある変数に "*コピー*" されます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-279">Instead, the value referred to by the `ref return` is *copied* to the variable on the left-hand side of the assignment.</span></span> <span data-ttu-id="a7f2b-280">この変数は `ref` ローカル変数ではありません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-280">The variable is not a `ref` local.</span></span>

<span data-ttu-id="a7f2b-281">目的の結果を得るために、`ref` 修飾子をローカル変数の宣言に追加して、戻り値が参照の場合に変数が参照になるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-281">In order to get the result you want, you need to add the `ref` modifier to the local variable declaration to make the variable a reference when the return value is a reference:</span></span>

[!code-csharp[AssignRefReturn](../../../samples/snippets/csharp/new-in-7/program.cs#24_AssignRefReturn "Assign ref return")]

<span data-ttu-id="a7f2b-282">上記の例の 2 番目の `WriteLine` ステートメントは、値 `24` を出力します。これは、マトリックスのストレージが変更されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-282">Now, the second `WriteLine` statement in the example above will print out the value `24`, indicating that the storage in the matrix has been modified.</span></span> <span data-ttu-id="a7f2b-283">ローカル変数は `ref` 修飾子で宣言されており、`ref` 戻り値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-283">The local variable has been declared with the `ref` modifier, and it will take a `ref` return.</span></span> <span data-ttu-id="a7f2b-284">`ref` 変数は宣言時に初期化する必要があります。宣言と初期化を分けることはできません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-284">You must initialize a `ref` variable when it is declared, you cannot split the declaration and the initialization.</span></span>

<span data-ttu-id="a7f2b-285">C# 言語には、これ以外に、`ref` ローカル変数と戻り値の誤用を防ぐ規則が 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-285">The C# language has three other rules that protect you from misusing the `ref` locals and returns:</span></span>

* <span data-ttu-id="a7f2b-286">標準的なメソッドの戻り値を `ref` ローカル変数に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-286">You cannot assign a standard method return value to a `ref` local variable.</span></span>
    - <span data-ttu-id="a7f2b-287">したがって、`ref int i = sequence.Count();` のようなステートメントは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-287">That disallows statements like `ref int i = sequence.Count();`</span></span>
* <span data-ttu-id="a7f2b-288">有効期間がメソッドの実行期間を超えない変数に `ref` を返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-288">You cannot return a `ref` to a variable whose lifetime does not extend beyond the execution of the method.</span></span>
    - <span data-ttu-id="a7f2b-289">つまり、ローカル変数または類似のスコープの変数への参照を返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-289">That means you cannot return a reference to a local variable or a variable with a similar scope.</span></span>
* <span data-ttu-id="a7f2b-290">`ref` ローカル変数と戻り値は、非同期メソッドと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-290">`ref` locals and returns can't be used with async methods.</span></span>
    - <span data-ttu-id="a7f2b-291">コンパイラは、非同期メソッドが戻るときに、参照先の変数が、最終的な値に設定されているかどうかを認識できません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-291">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="a7f2b-292">ref ローカル変数および ref 戻り値の追加により、値のコピーを回避したり、逆参照操作を複数回実行したりすることで、より効率的なアルゴリズムを実現できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-292">The addition of ref locals and ref returns enable algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span> 

## <a name="local-functions"></a><span data-ttu-id="a7f2b-293">ローカル関数</span><span class="sxs-lookup"><span data-stu-id="a7f2b-293">Local functions</span></span>

<span data-ttu-id="a7f2b-294">クラスの多くの設計には、1 つの場所からのみ呼び出されるメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-294">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="a7f2b-295">このような追加のプライベート メソッドを使用することで、各メソッドのサイズを小さくし、その焦点を絞ることができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-295">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="a7f2b-296">ただし、このプライベート メソッドにより、初めてクラスを読むときに理解しにくくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-296">However, they can make it harder to understand a class when reading it the first time.</span></span> <span data-ttu-id="a7f2b-297">これらのメソッドは、単一の呼び出し元の場所のコンテキストの外部でも理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-297">These methods must be understood outside of the context of the single calling location.</span></span>

<span data-ttu-id="a7f2b-298">そのような設計では、"*ローカル関数*" を使用すると、別のメソッドのコンテキスト内でメソッドを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-298">For those designs, *local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="a7f2b-299">これにより、クラスを読むときに、ローカル メソッドが、それが宣言されているコンテキストからのみ呼び出されることを容易に理解できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-299">This makes it easier for readers of the class to see that the local method is only called from the context in which is it declared.</span></span>

<span data-ttu-id="a7f2b-300">ローカル関数には、パブリック反復子メソッドとパブリック非同期メソッドという 2 つの非常に一般的なユース ケースがあります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-300">There are two very common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="a7f2b-301">どちらの種類のメソッドも、プログラマーが期待するよりも遅くエラーを報告するコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-301">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="a7f2b-302">反復子メソッドの場合、例外が検出されるのは、返されたシーケンスを列挙するコードを呼び出した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-302">In the case of iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="a7f2b-303">非同期メソッドの場合、例外が検出されるのは、返された `Task` が待機状態になったときのみです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-303">In the case of async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span>

<span data-ttu-id="a7f2b-304">それでは、反復子メソッドから見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-304">Let's start with an iterator method:</span></span>

[!code-csharp[IteratorMethod](../../../samples/snippets/csharp/new-in-7/Iterator.cs#25_IteratorMethod "Iterator method")]

<span data-ttu-id="a7f2b-305">下のコードでは、不適切な方法で反復子メソッドを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-305">Examine the code below that calls the iterator method incorrectly:</span></span>

[!code-csharp[CallIteratorMethod](../../../samples/snippets/csharp/new-in-7/program.cs#26_CallIteratorMethod "Call iterator method")]

<span data-ttu-id="a7f2b-306">例外は、`resultSet` が作成されたときではなく、`resultSet` が反復処理されたときにスローされます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-306">The exception is thrown when `resultSet` is iterated, not when `resultSet` is created.</span></span>
<span data-ttu-id="a7f2b-307">ここに示した例では、ほとんどの開発者が問題を迅速に診断できるでしょう。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-307">In this contained example, most developers could quickly diagnose the problem.</span></span> <span data-ttu-id="a7f2b-308">ところが、より大きなコードベースでは、多くの場合、反復子を作成するコードが結果を列挙するコードの近くにあるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-308">However, in larger codebases, the code that creates an iterator often isn't as close to the code that enumerates the result.</span></span> <span data-ttu-id="a7f2b-309">パブリック メソッドですべての引数を検証し、プライベート メソッドで列挙型を生成するように、コードをリファクタリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-309">You can refactor the code so that the public method validates all arguments, and a private method generates the enumeration:</span></span>

[!code-csharp[IteratorMethodRefactored](../../../samples/snippets/csharp/new-in-7/Iterator.cs#27_IteratorMethodRefactored "Iterator method refactored")]

<span data-ttu-id="a7f2b-310">このリファクタリングしたバージョンでは、例外が即座にスローされます。これは、パブリック メソッドが反復子メソッドではないためです。つまり、`yield return` 構文を使用するのは、プライベート メソッドのみです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-310">This refactored version will throw exceptions immediately because the public method is not an iterator method; only the private method uses the `yield return` syntax.</span></span> <span data-ttu-id="a7f2b-311">ただし、このリファクタリングには潜在的な問題があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-311">However, there are potential problems with this refactoring.</span></span> <span data-ttu-id="a7f2b-312">プライベート メソッドは、パブリック インターフェイス メソッドからのみ呼び出す必要があります。そうしないと、すべての引数の検証がスキップされるためです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-312">The private method should only be called from the public interface method, because otherwise all argument validation is skipped.</span></span>
<span data-ttu-id="a7f2b-313">クラスを読む開発者がこの事実を発見するには、クラス全体を読み、`alphabetSubsetImplementation` メソッドへの他の参照を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-313">Readers of the class must discover this fact by reading the entire class and searching for any other references to the `alphabetSubsetImplementation` method.</span></span>

<span data-ttu-id="a7f2b-314">`alphabetSubsetImplementation` をパブリック API メソッド内のローカル関数として宣言することで、この設計の意図をより明確にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-314">You can make that design intent more clear by declaring the `alphabetSubsetImplementation` as a local function inside the public API method:</span></span>

[!code-csharp[22_IteratorMethodLocal](../../../samples/snippets/csharp/new-in-7/Iterator.cs#28_IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="a7f2b-315">上記のバージョンでは、ローカル メソッドが外部メソッドのコンテキストでのみ参照されることが明確になっています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-315">The version above makes it clear that the local method is referenced only in the context of the outer method.</span></span> <span data-ttu-id="a7f2b-316">また、ローカル関数の規則により、開発者が誤ってクラス内の別の場所からローカル関数を呼び出して、引数の検証をバイパスできないようになっています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-316">The rules for local functions also ensure that a developer can't accidentally call the local function from another location in the class and bypass the argument validation.</span></span>

<span data-ttu-id="a7f2b-317">同じ手法を `async` メソッドで使用すると、引数の検証で発生する例外が非同期操作の開始前にスローされることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-317">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

> [!NOTE]
> <span data-ttu-id="a7f2b-318">ローカル関数によってサポートされる設計の中には、"*ラムダ式*" を使用して実現できるものもあります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-318">Some of the designs that are supported by local functions could also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="a7f2b-319">興味のある方は、[その違いの詳細を確認してください](../local-functions-vs-lambdas.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-319">Those interested can [read more about the differences](../local-functions-vs-lambdas.md)</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="a7f2b-320">式形式のメンバーの追加</span><span class="sxs-lookup"><span data-stu-id="a7f2b-320">More expression-bodied members</span></span>

<span data-ttu-id="a7f2b-321">C# 6 では、メンバー関数の[式形式のメンバー](csharp-6.md#expression-bodied-function-members)と読み取り専用プロパティが導入されました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-321">C# 6 introduced [expression-bodied members](csharp-6.md#expression-bodied-function-members) for member functions, and read-only properties.</span></span> <span data-ttu-id="a7f2b-322">C# 7 では、式として実装できる許可されたメンバーが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-322">C# 7 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="a7f2b-323">C# 7 では、"*コンストラクター*"、"*ファイナライザー*"、`get` アクセサー、および `set` アクセサーを "*プロパティ*" と "*インデクサー*" に実装できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-323">In C# 7, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="a7f2b-324">それぞれの例を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-324">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](../../../samples/snippets/csharp/new-in-7/expressionmembers.cs#36_ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="a7f2b-325">この例ではファイナライザーは必要ありませんが、その構文を紹介するために示しています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-325">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="a7f2b-326">アンマネージ リソースを解放する必要がない限り、クラスにファイナライザーを実装しないでください。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-326">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="a7f2b-327">また、アンマネージ リソースを直接管理する代わりに、<xref:System.Runtime.InteropServices.SafeHandle> クラスの使用を検討する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-327">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="a7f2b-328">式形式のメンバーに関するこのような新しい場所は、C# 言語にとって重要なマイルストーンを表します。これらの機能は、オープンソースの [Roslyn](https://github.com/dotnet/Roslyn) プロジェクトに従事しているコミュニティ メンバーによって実装されました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-328">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="a7f2b-329">throw 式</span><span class="sxs-lookup"><span data-stu-id="a7f2b-329">Throw expressions</span></span>

<span data-ttu-id="a7f2b-330">C# では、`throw` は常にステートメントでした。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-330">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="a7f2b-331">`throw` は式ではなくステートメントであるため、使用できない C# コンストラクトがありました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-331">Because `throw` is a statement, not an expression, there were C# constructs where you could not use it.</span></span> <span data-ttu-id="a7f2b-332">これには、条件式、null 結合式、および一部のラムダ式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-332">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="a7f2b-333">式形式のメンバーが追加されたことにより、さらに多くの場所で `throw` 式が役に立つようになりました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-333">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="a7f2b-334">C# 7 では、このようなコンストラクトを記述できるように、"*throw 式*" が導入されています。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-334">So that you can write any of these constructs, C# 7 introduces *throw expressions*.</span></span>

<span data-ttu-id="a7f2b-335">その構文は、`throw` ステートメントに常に使用してきた構文と同じです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-335">The syntax is the same as you've always used for `throw` statements.</span></span> <span data-ttu-id="a7f2b-336">唯一の違いは、条件式などの新しい場所に配置できるようになったことです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-336">The only difference is that now you can place them in new locations, such as in a conditional expression:</span></span>

[!code-csharp[Throw_ExpressionExample](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#37_Throw_ExpressionExample "conditional throw expressions")]

<span data-ttu-id="a7f2b-337">この機能により、初期化式で throw 式を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-337">This features enables using throw expressions in initialization expressions:</span></span>

[!code-csharp[ThrowInInitialization](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#38_ThrowInInitialization "conditional throw expressions")]

<span data-ttu-id="a7f2b-338">以前は、これらの初期化は、コンストラクターの本体に throw ステートメントを使用して、コンストラクター内で行う必要がありました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-338">Previously, those initializations would need to be in a constructor, with the throw statements in the body of the constructor:</span></span>


[!code-csharp[ThrowInConstructor](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#39_ThrowInConstructor "throw statements")]

> [!NOTE]
> <span data-ttu-id="a7f2b-339">前述のコンストラクトのどちらにおいても、オブジェクトの構築中に例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-339">Both of the preceding constructs will cause exceptions to be thrown during the construction of an object.</span></span> <span data-ttu-id="a7f2b-340">多くの場合、これらの例外から回復するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-340">Those are often difficult to recover from.</span></span>
> <span data-ttu-id="a7f2b-341">そのため、構築中に例外をスローする設計は推奨しません。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-341">For that reason, designs that throw exceptions during construction are discouraged.</span></span>

## <a name="generalized-async-return-types"></a><span data-ttu-id="a7f2b-342">一般化された async の戻り値の型</span><span class="sxs-lookup"><span data-stu-id="a7f2b-342">Generalized async return types</span></span>

<span data-ttu-id="a7f2b-343">非同期メソッドから `Task` オブジェクトを返すと、特定のパスでパフォーマンスのボトルネックが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-343">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="a7f2b-344">`Task` は参照型です。したがって、これを使うことは、オブジェクトを割り当てることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-344">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="a7f2b-345">`async` 修飾子で宣言されたメソッドがキャッシュされた結果を返すか、同期的に完了する場合、追加の割り当ては、コードのパフォーマンスが重要なセクションにおいて大きな時間コストにつながります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-345">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="a7f2b-346">厳密なループ処理でこのような割り当てが発生した場合、非常にコストがかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-346">It can become very costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="a7f2b-347">新しい言語機能は、非同期メソッドが、`Task`、`Task<T>`、`void` に加えて他の型を返す可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-347">The new language feature means that async methods may return other types in addition to `Task`, `Task<T>` and `void`.</span></span> <span data-ttu-id="a7f2b-348">返される型は引き続き非同期パターンを満たす必要があります。つまり、`GetAwaiter` メソッドはアクセス可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-348">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="a7f2b-349">1 つの具体的な例として、この新しい言語機能を使用するために .NET Framework に `ValueTask` 型が追加されました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-349">As one concrete example, the `ValueTask` type has been added to the .NET framework to make use of this new language feature:</span></span> 

[!code-csharp[UsingValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#30_UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="a7f2b-350"><xref:System.Threading.Tasks.ValueTask%601> 型を使用するには、NuGet パッケージ [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-350">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="a7f2b-351">単純な最適化では、これまで `Task` が使用されていた場所に `ValueTask` を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-351">A simple optimization would be to use `ValueTask` in places where `Task` would be used before.</span></span> <span data-ttu-id="a7f2b-352">ただし、手動で追加の最適化を実行する場合は、非同期処理の結果をキャッシュし、その結果を以降の呼び出しで再利用できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-352">However, if you want to perform extra optimizations by hand, you can cache results from async work and reuse the result in subsequent calls.</span></span> <span data-ttu-id="a7f2b-353">`ValueTask` 構造体には `Task` パラメーターを持つコンストラクターがあるため、既存の非同期メソッドの戻り値から `ValueTask` を構築できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-353">The `ValueTask` struct has a constructor with a `Task` parameter so that you can construct a `ValueTask` from the return value of any existing async method:</span></span>

[!code-csharp[AsyncOptimizedValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#31_AsyncOptimizedValueTask "Return async result or cached value")]
 
<span data-ttu-id="a7f2b-354">すべてのパフォーマンスに関する推奨事項と同様に、コードに大規模な変更を加える前に、両方のバージョンのベンチマークを計測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-354">As with all performance recommendations, you should benchmark both versions before making large scale changes to your code.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="a7f2b-355">数値リテラルの構文の改善</span><span class="sxs-lookup"><span data-stu-id="a7f2b-355">Numeric literal syntax improvements</span></span>

<span data-ttu-id="a7f2b-356">数値定数を読み間違えると、コードを初めて読むときにコードを理解するのが難しくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-356">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="a7f2b-357">これは、数値がビット マスクや数値以外の記号として使用されている場合にありがちなことです。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-357">This often occurs when those numbers are used as bit masks or other symbolic rather than numeric values.</span></span> <span data-ttu-id="a7f2b-358">C# 7 では、使用目的に応じて最も読みやすい形式で簡単に数値を記述しできるように、"*バイナリ リテラル*" と "*桁区切り文字*" という 2 つの新機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-358">C# 7 includes two new features to make it easier to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="a7f2b-359">ビット マスクを作成しているときや、数値をバイナリで表現するとコードが最も読みやすくなる場合は、数字をバイナリで記述します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-359">For those times when you are creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[BinaryConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#32_BinaryConstants "Binary constants")]

<span data-ttu-id="a7f2b-360">定数の先頭にある `0b` は、数値が 2 進数として記述されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-360">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span>

<span data-ttu-id="a7f2b-361">バイナリ数値は非常に長くなる場合があるため、ビット パターンが見やすくなるように、桁区切り記号として `_` が導入されました。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-361">Binary numbers can get very long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator:</span></span>

[!code-csharp[ThousandSeparators](../../../samples/snippets/csharp/new-in-7/Program.cs#33_ThousandSeparators "Thousands separators")]

<span data-ttu-id="a7f2b-362">桁区切り記号は定数のどこにでも置くことができます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-362">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="a7f2b-363">10 進数の場合は、3 桁の区切り記号として使用するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-363">For base 10 numbers, it would be common to use it as a thousands separator:</span></span>

[!code-csharp[LargeIntegers](../../../samples/snippets/csharp/new-in-7/Program.cs#34_LargeIntegers "Large integer")]

<span data-ttu-id="a7f2b-364">桁区切り記号は、`decimal` 型、`float` 型、`double` 型でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-364">The digit separator can be used with `decimal`, `float` and `double` types as well:</span></span>

[!code-csharp[OtherConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#35_OtherConstants "non-integral constants")]

<span data-ttu-id="a7f2b-365">これらをまとめると、数値定数をさらに見やすい状態で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a7f2b-365">Taken together, you can declare numeric constants with much more readability.</span></span>