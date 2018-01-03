---
title: "クイック スタート - 分岐とループ - C# ガイド"
description: "分岐とループに関するこのクイック スタートでは、C# のコードを記述して、この言語における、ステートメントを繰り返し実行するための条件付き分岐とループに対応している構文について学習します。"
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 7954475616b122f8bb96ad00d05b476b3beeb52c
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2017
---
# <a name="branches-and-loops"></a><span data-ttu-id="f734e-103">分岐とループ</span><span class="sxs-lookup"><span data-stu-id="f734e-103">Branches and loops</span></span>

<span data-ttu-id="f734e-104">このクイック スタートでは、変数を調べてその変数に基づいて実行パスを変更するコードの記述方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f734e-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="f734e-105">C# コードを記述し、コードをコンパイルおよび実行して結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="f734e-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="f734e-106">このクイック スタートでは、C# における分岐構造とループ構造を確認する一連のレッスンを行います。</span><span class="sxs-lookup"><span data-stu-id="f734e-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="f734e-107">これらのレッスンでは、C# 言語の基本を説明します。</span><span class="sxs-lookup"><span data-stu-id="f734e-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="f734e-108">このクイック スタートでは、開発用に使用できるマシンがあることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="f734e-109">Mac、PC、または Linux 上でローカルの開発環境を設定する手順については、.NET の [10 分でわかる概要](https://www.microsoft.com/net/core)に関するトピックに記載されています。</span><span class="sxs-lookup"><span data-stu-id="f734e-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="f734e-110">使用するコマンドの概要を手短に確認するには、[ローカルでのクイック スタートの概要](local-environment.md)と詳細へのリンクをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f734e-110">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="f734e-111">`if` ステートメントを使用した条件判定</span><span class="sxs-lookup"><span data-stu-id="f734e-111">Make decisions using the `if` statement</span></span>

<span data-ttu-id="f734e-112">「**branches-quickstart**」という名前のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f734e-112">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="f734e-113">それを現在のディレクトリとし、`dotnet new console -n BranchesAndLoops -o .` を実行します。</span><span class="sxs-lookup"><span data-stu-id="f734e-113">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="f734e-114">このコマンドによって、現在のディレクトリに新しい .NET Core コンソール アプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f734e-114">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="f734e-115">お好みのエディターで **Program.cs** を開き、`Console.Writeline("Hello World!");` の行を次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f734e-115">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="f734e-116">コンソール ウィンドウで「`dotnet run`」を入力し、このコードを試します。</span><span class="sxs-lookup"><span data-stu-id="f734e-116">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="f734e-117">"答えは 10 を超えています" というメッセージが</span><span class="sxs-lookup"><span data-stu-id="f734e-117">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="f734e-118">コンソールに出力されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f734e-118">printed to your console.</span></span>

<span data-ttu-id="f734e-119">合計が 10 未満になるように `b` の宣言を変更します。</span><span class="sxs-lookup"><span data-stu-id="f734e-119">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="f734e-120">もう一度「`dotnet run`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="f734e-120">Type `dotnet run` again.</span></span> <span data-ttu-id="f734e-121">計算結果が 10 未満であるため、何も出力されません。</span><span class="sxs-lookup"><span data-stu-id="f734e-121">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="f734e-122">判定中の**条件**が false になっています。</span><span class="sxs-lookup"><span data-stu-id="f734e-122">The **condition** you're testing is false.</span></span> <span data-ttu-id="f734e-123">`if` ステートメントの考えられる分岐の 1 つである true 分岐のみを記述したため、実行すべきコードがありません。</span><span class="sxs-lookup"><span data-stu-id="f734e-123">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="f734e-124">C# (または何らかのプログラミング言語) について詳しく学習するに従い、コードを記述する際にミスをすることもあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="f734e-124">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="f734e-125">コンパイラは、エラーを発見して報告します。</span><span class="sxs-lookup"><span data-stu-id="f734e-125">The compiler will find and report the errors.</span></span> <span data-ttu-id="f734e-126">エラーの出力とそのエラーを生成したコードをよく確認してください。</span><span class="sxs-lookup"><span data-stu-id="f734e-126">Look closely at the error output and the code that generated the error.</span></span> <span data-ttu-id="f734e-127">通常、コンパイラ エラーは問題を発見するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f734e-127">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="f734e-128">この最初のサンプルは、`if` とブール型の機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-128">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="f734e-129">*ブール値*は、`true` または `false` という 2 つの値のいずれかを持つことができる変数です。</span><span class="sxs-lookup"><span data-stu-id="f734e-129">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="f734e-130">C# ではブール変数の専用の型として `bool` を定義しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-130">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="f734e-131">`if` ステートメントは、`bool` の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="f734e-131">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="f734e-132">値が `true` の場合、`if` に続くステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="f734e-132">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="f734e-133">それ以外の場合はスキップします。</span><span class="sxs-lookup"><span data-stu-id="f734e-133">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="f734e-134">条件を確認してその条件に基づいてステートメントを実行するというこのプロセスは非常に機能的です。</span><span class="sxs-lookup"><span data-stu-id="f734e-134">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="f734e-135">if と else を組み合わせた使用</span><span class="sxs-lookup"><span data-stu-id="f734e-135">Make if and else work together</span></span>

<span data-ttu-id="f734e-136">true 分岐と false 分岐で別々のコードを実行するには、条件が false のときに実行する `else` 分岐を作成します。</span><span class="sxs-lookup"><span data-stu-id="f734e-136">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="f734e-137">これを試してみます。</span><span class="sxs-lookup"><span data-stu-id="f734e-137">Try this.</span></span> <span data-ttu-id="f734e-138">次のコードの最後の 2 行を `Main` メソッドに追加します (最初の 4 行は既にあるはずです)。</span><span class="sxs-lookup"><span data-stu-id="f734e-138">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="f734e-139">`else` キーワードに続くステートメントは、判定中の条件が `false` のときにのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="f734e-139">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="f734e-140">`if` と `else` をブール条件と組み合わせれば、`true` と `false` の条件を両方処理するのに必要な機能がすべて整います。</span><span class="sxs-lookup"><span data-stu-id="f734e-140">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f734e-141">`if` と `else` のステートメント内にあるインデントは、人が読みやすいようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="f734e-141">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="f734e-142">C# 言語はインデントや空白文字を重要なものとして扱いません。</span><span class="sxs-lookup"><span data-stu-id="f734e-142">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="f734e-143">`if` や `else` のキーワードに続くステートメントは、条件に基づいて実行されます。</span><span class="sxs-lookup"><span data-stu-id="f734e-143">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="f734e-144">このクイック スタートのすべてのサンプルでは、一般的な記述方法に従い、ステートメントの制御フローに基づいて行にインデントを挿入しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-144">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="f734e-145">インデントは重要ではないため、条件に基づいて実行するブロック内に 1 つ以上のステートメントがある場合には、`{` と `}` を使用して示します。</span><span class="sxs-lookup"><span data-stu-id="f734e-145">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="f734e-146">通常、C# プログラマーは `if` と `else` の句にはこの中かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="f734e-146">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="f734e-147">次の例は、さきほど作成したものと同じ内容です。</span><span class="sxs-lookup"><span data-stu-id="f734e-147">The following example is the same as the one you just created.</span></span> <span data-ttu-id="f734e-148">上のコードを、次のコードに一致するように変更します。</span><span class="sxs-lookup"><span data-stu-id="f734e-148">Modify your code above to match the following code:</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> <span data-ttu-id="f734e-149">このクイック スタートの残りの箇所では、一般に認められている記述方法に従って、すべてのコード サンプルで中かっこを使用しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-149">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="f734e-150">さらに複雑な条件を判定できます。</span><span class="sxs-lookup"><span data-stu-id="f734e-150">You can test more complicated conditions.</span></span> <span data-ttu-id="f734e-151">`Main` メソッド内でこれまでに記述したコードの下に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f734e-151">Add the following code in your `Main` method after the code you've written so far:</span></span>

```csharp
    int c = 4;
    if ((a + b + c > 10) && (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not greater than the second");
}
```

<span data-ttu-id="f734e-152">`&&` は "and" (および) を表します。</span><span class="sxs-lookup"><span data-stu-id="f734e-152">The `&&` represents "and".</span></span> <span data-ttu-id="f734e-153">これは、true 分岐でステートメントを実行するには、両方の条件が true になる必要があることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-153">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="f734e-154">また、これらの例では、ステートメントが `{` と `}` で囲まれていれば、各条件分岐に複数のステートメントを持つことができることを示しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-154">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="f734e-155">`||` を使用して "or" (または) を表すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f734e-155">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="f734e-156">これまでに記述したコードの下に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f734e-156">Add the following code after what you've written so far:</span></span>

```csharp
if ((a + b + c > 10) || (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not greater than the second");
}
```

<span data-ttu-id="f734e-157">最初の手順が完了しました。</span><span class="sxs-lookup"><span data-stu-id="f734e-157">You've finished the first step.</span></span> <span data-ttu-id="f734e-158">次のセクションを開始する前に、現在のコードを別のメソッドに移動してみましょう。</span><span class="sxs-lookup"><span data-stu-id="f734e-158">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="f734e-159">移動しておくと、新しい例で作業を開始するときに楽になります。</span><span class="sxs-lookup"><span data-stu-id="f734e-159">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="f734e-160">`Main` メソッドの名前を `ExploreIf` に変更し、`ExploreIf` を呼び出す新しい `Main` メソッドを記述します。</span><span class="sxs-lookup"><span data-stu-id="f734e-160">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="f734e-161">完成したコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f734e-161">When you have finished, your code should look like this:</span></span>

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }            
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

<span data-ttu-id="f734e-162">`ExploreIf()` の呼び出しをコメント アウトします。</span><span class="sxs-lookup"><span data-stu-id="f734e-162">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="f734e-163">こうしておくと、このセクションの作業を進めるにあたって出力がすっきりします。</span><span class="sxs-lookup"><span data-stu-id="f734e-163">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="f734e-164">C# では、`//` の後ろが**コメント**になります。</span><span class="sxs-lookup"><span data-stu-id="f734e-164">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="f734e-165">コードとしては実行せずにソース コード内に残したい任意のテキストを、コメントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f734e-165">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="f734e-166">コンパイラは、コメントから実行可能コードを生成しません。</span><span class="sxs-lookup"><span data-stu-id="f734e-166">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="f734e-167">ループを使用した処理の繰り返し</span><span class="sxs-lookup"><span data-stu-id="f734e-167">Use loops to repeat operations</span></span>

<span data-ttu-id="f734e-168">このセクションでは**ループ**を使用してステートメントを繰り返し実行します。</span><span class="sxs-lookup"><span data-stu-id="f734e-168">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="f734e-169">`Main` メソッド内で次のコードを試してください。</span><span class="sxs-lookup"><span data-stu-id="f734e-169">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="f734e-170">`while` ステートメントは、条件を確認して `while` に続くステートメントまたはステートメント ブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="f734e-170">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="f734e-171">条件が false になるまで、条件の確認とステートメントの実行を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f734e-171">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="f734e-172">この例では、もう 1 つ新しい演算子が使用されています。</span><span class="sxs-lookup"><span data-stu-id="f734e-172">There's one other new operator in this example.</span></span> <span data-ttu-id="f734e-173">`counter` 変数のあとにある `++` は、**インクリメント**演算子です。</span><span class="sxs-lookup"><span data-stu-id="f734e-173">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="f734e-174">`counter` の値に 1 を足し、その値を `counter` 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="f734e-174">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f734e-175">コードを実行したときに `while` のループ条件が false に切り替わることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f734e-175">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="f734e-176">それ以外の場合は、プログラムが終了することのない**無限ループ**を作成します。</span><span class="sxs-lookup"><span data-stu-id="f734e-176">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="f734e-177">**CTRL-C** またはその他の方法でプログラムを強制的に終了する必要があるため、このサンプルでは実践しません。</span><span class="sxs-lookup"><span data-stu-id="f734e-177">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="f734e-178">`while` ループは、条件を判定してから `while` に続くコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="f734e-178">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="f734e-179">`do` ... `while` ループは、最初にコードを実行してからその条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="f734e-179">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="f734e-180">do while ループを次のコードで示します。</span><span class="sxs-lookup"><span data-stu-id="f734e-180">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="f734e-181">この `do` ループと先述の `while` ループの出力は同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="f734e-181">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="f734e-182">for ループの処理</span><span class="sxs-lookup"><span data-stu-id="f734e-182">Work with the for loop</span></span>

<span data-ttu-id="f734e-183">C# では **for** ループがよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="f734e-183">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="f734e-184">Main() メソッドで次のコードを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="f734e-184">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="f734e-185">このループは、既に使用した `while` ループや `do` ループと同じ機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="f734e-185">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="f734e-186">`for` ステートメントは 3 つの部分に分かれてその機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="f734e-186">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="f734e-187">最初の部分は、**for 初期化子**です。`for index = 0;` は、`index` がループ変数であることを宣言し、その初期値を `0` に設定しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-187">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="f734e-188">2 つ目の部分は、**for 条件**です。`index < 10` は、counter の値が 10 未満である間は `for` ループが実行され続けることを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-188">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="f734e-189">最後の部分は、**for 反復子**です。`index++` は、`for` ステートメントに続くブロックを実行したあとにループ変数を変更する方法を指定しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-189">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="f734e-190">ここでは、ブロックが実行されるごとに `index` が 1 ずつ増加するよう指定しています。</span><span class="sxs-lookup"><span data-stu-id="f734e-190">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="f734e-191">ご自身でこれを実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="f734e-191">Experiment with these yourself.</span></span> <span data-ttu-id="f734e-192">以下をそれぞれ試してみます。</span><span class="sxs-lookup"><span data-stu-id="f734e-192">Try each of the following:</span></span>

- <span data-ttu-id="f734e-193">初期化子を変更して別の値で開始する。</span><span class="sxs-lookup"><span data-stu-id="f734e-193">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="f734e-194">条件を変更して別の値で停止する。</span><span class="sxs-lookup"><span data-stu-id="f734e-194">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="f734e-195">完了したら次に進み、学習したことを使用して自分でいくつかのコードを記述してみましょう。</span><span class="sxs-lookup"><span data-stu-id="f734e-195">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="f734e-196">分岐とループの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="f734e-196">Combine branches and loops</span></span>

<span data-ttu-id="f734e-197">C# 言語における `if` ステートメントとループ構造を見てきました。では、1 から 20 の整数のうち 3 で割り切れる数の合計を求める C# コードを記述できるか確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="f734e-197">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="f734e-198">次にいくつかヒントを示します。</span><span class="sxs-lookup"><span data-stu-id="f734e-198">Here are a few hints:</span></span>

- <span data-ttu-id="f734e-199">`%` 演算子は、除算演算の剰余を算出します。</span><span class="sxs-lookup"><span data-stu-id="f734e-199">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="f734e-200">`if` ステートメントは、数を合計に入れるべきかどうか確認する条件を作ります。</span><span class="sxs-lookup"><span data-stu-id="f734e-200">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="f734e-201">`for` ループは、1 から 20 までのすべての数を 1 つずつ確認する一連の手順を繰り返すのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f734e-201">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="f734e-202">ご自身で試してみてください。</span><span class="sxs-lookup"><span data-stu-id="f734e-202">Try it yourself.</span></span> <span data-ttu-id="f734e-203">そして自分がとった方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f734e-203">Then check how you did.</span></span> <span data-ttu-id="f734e-204">答えは 63 になるはずです。</span><span class="sxs-lookup"><span data-stu-id="f734e-204">You should get 63 for an answer.</span></span> <span data-ttu-id="f734e-205">[GitHub で完成版のコードを表示する](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54)と、考えられる答えの 1 つを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f734e-205">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="f734e-206">これで "分岐とループ" に関するクイック スタートは終了です。</span><span class="sxs-lookup"><span data-stu-id="f734e-206">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="f734e-207">続けて独自の開発環境で[配列とコレクション](arrays-and-collections.md)のクイック スタートに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="f734e-207">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="f734e-208">次のトピックでこれらの概念の詳細を学習できます。</span><span class="sxs-lookup"><span data-stu-id="f734e-208">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="f734e-209">[if と else ステートメント](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="f734e-209">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="f734e-210">[while ステートメント](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="f734e-210">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="f734e-211">[do ステートメント](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="f734e-211">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="f734e-212">for ステートメント</span><span class="sxs-lookup"><span data-stu-id="f734e-212">For statement</span></span>](../language-reference/keywords/for.md)   