---
title: "最新の web アプリケーションの特性"
description: "ASP.NET Core と Azure での最新の Web アプリケーションを設計 |最新の web アプリケーションの特性"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 9ff9380b318457a842dec4e41b9b74dcddcda3d3
ms.sourcegitcommit: 882e02b086d7cb9c75f748494cf7a8d3377c5874
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2017
---
# <a name="characteristics-of-modern-web-applications"></a><span data-ttu-id="49aa5-103">最新の Web アプリケーションの特性</span><span class="sxs-lookup"><span data-stu-id="49aa5-103">Characteristics of Modern Web Applications</span></span>

> <span data-ttu-id="49aa5-104">"…</span><span class="sxs-lookup"><span data-stu-id="49aa5-104">"…</span></span> <span data-ttu-id="49aa5-105">適切な設計は、機能には、安価です。</span><span class="sxs-lookup"><span data-stu-id="49aa5-105">with proper design, the features come cheaply.</span></span> <span data-ttu-id="49aa5-106">このアプローチは骨の折れるを成功させるのには続行されます。"</span><span class="sxs-lookup"><span data-stu-id="49aa5-106">This approach is arduous, but continues to succeed."</span></span>  
> <span data-ttu-id="49aa5-107">_\-Dennis Ritchie_</span><span class="sxs-lookup"><span data-stu-id="49aa5-107">_\- Dennis Ritchie_</span></span>

## <a name="summary"></a><span data-ttu-id="49aa5-108">概要</span><span class="sxs-lookup"><span data-stu-id="49aa5-108">Summary</span></span>

<span data-ttu-id="49aa5-109">最新の web アプリケーションは、上位のユーザーの期待とこれまでよりも大きい要求があります。</span><span class="sxs-lookup"><span data-stu-id="49aa5-109">Modern web applications have higher user expectations and greater demands than ever before.</span></span> <span data-ttu-id="49aa5-110">現在の web アプリケーションが使用可能な 24/7 からほぼすべてのデバイスから使用できるようにし、どこにあっても、または画面のサイズが必要です。</span><span class="sxs-lookup"><span data-stu-id="49aa5-110">Today's web apps are expected to be available 24/7 from anywhere in the world, and usable from virtually any device or screen size.</span></span> <span data-ttu-id="49aa5-111">Web アプリケーションは、セキュリティで保護された、柔軟性が高く、およびオンデマンドの急激な増加に対応できる拡張性にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49aa5-111">Web applications must be secure, flexible, and scalable to meet spikes in demand.</span></span> <span data-ttu-id="49aa5-112">ますます、複雑なシナリオは、JavaScript を使用して、web Api 経由で効率的に通信するクライアント上に構築された豊富なユーザー エクスペリエンスで処理される必要があります。</span><span class="sxs-lookup"><span data-stu-id="49aa5-112">Increasingly, complex scenarios should be handled by rich user experiences built on the client using JavaScript, and communicating efficiently through web APIs.</span></span>

<span data-ttu-id="49aa5-113">ASP.NET Core は、最新の web アプリケーションとクラウド ベースのホスティング シナリオに最適です。</span><span class="sxs-lookup"><span data-stu-id="49aa5-113">ASP.NET Core is optimized for modern web applications and cloud-based hosting scenarios.</span></span> <span data-ttu-id="49aa5-114">そのモジュール形式デザインは、実際に使用される、アプリケーションのセキュリティとホストのリソース要件を削減しながらパフォーマンスを向上させる機能のみに依存するアプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-114">Its modular design enables applications to depend on only those features they actually use, improving application security and performance while reducing hosting resource requirements.</span></span>

## <a name="reference-application-eshoponweb"></a><span data-ttu-id="49aa5-115">アプリケーションを参照: eShopOnWeb</span><span class="sxs-lookup"><span data-stu-id="49aa5-115">Reference Application: eShopOnWeb</span></span>

<span data-ttu-id="49aa5-116">このガイドには、参照アプリケーションが含まれています。 *eShopOnWeb*、いくつかの原則と推奨事項を示しています。</span><span class="sxs-lookup"><span data-stu-id="49aa5-116">This guidance includes a reference application, *eShopOnWeb*, that demonstrates some of the principles and recommendations.</span></span> <span data-ttu-id="49aa5-117">アプリケーションは、シャツ、コーヒーマグ、およびその他のマーケティングの項目のカタログからの参照をサポートする単純なオンライン ストアです。</span><span class="sxs-lookup"><span data-stu-id="49aa5-117">The application is a simple online store which supports browsing through a catalog of shirts, coffee mugs, and other marketing items.</span></span> <span data-ttu-id="49aa5-118">参照アプリケーションは理解しやすくために意図的に単純です。</span><span class="sxs-lookup"><span data-stu-id="49aa5-118">The reference application is deliberately simple in order to make it easy to understand.</span></span>

<span data-ttu-id="49aa5-119">**図 2-1。**</span><span class="sxs-lookup"><span data-stu-id="49aa5-119">**Figure 2-1.**</span></span> <span data-ttu-id="49aa5-120">eShopOnWeb</span><span class="sxs-lookup"><span data-stu-id="49aa5-120">eShopOnWeb</span></span>

![](./media/image2-1.png)

> ### <a name="reference-application"></a><span data-ttu-id="49aa5-121">アプリケーションの参照</span><span class="sxs-lookup"><span data-stu-id="49aa5-121">Reference Application</span></span>
> - <span data-ttu-id="49aa5-122">**eShopOnWeb**</span><span class="sxs-lookup"><span data-stu-id="49aa5-122">**eShopOnWeb**</span></span>  
> <span data-ttu-id="49aa5-123"><https://github.com/dotnet/eShopOnWeb></span><span class="sxs-lookup"><span data-stu-id="49aa5-123"><https://github.com/dotnet/eShopOnWeb></span></span>

## <a name="cloud-hosted-and-scalable"></a><span data-ttu-id="49aa5-124">クラウドでホストされると拡張性</span><span class="sxs-lookup"><span data-stu-id="49aa5-124">Cloud-Hosted and Scalable</span></span>

<span data-ttu-id="49aa5-125">ASP.NET Core は、メモリ不足と高いスループットになっているため、クラウド (パブリック クラウド、プライベート クラウド、クラウド) に最適です。</span><span class="sxs-lookup"><span data-stu-id="49aa5-125">ASP.NET Core is optimized for the cloud (public cloud, private cloud, any cloud) because it is low-memory and high-throughput.</span></span> <span data-ttu-id="49aa5-126">ASP.NET Core アプリケーションのより小さなフット プリントは、複数の同一のハードウェア上でそれらをホストすることができ、支払-として-するを使用して、クラウド サービスのホスティングを移動するときにより少ないリソースの支払いを意味します。</span><span class="sxs-lookup"><span data-stu-id="49aa5-126">The smaller footprint of ASP.NET Core applications means you can host more of them on the same hardware, and you pay for fewer resources when using pay-as-you go cloud hosting services.</span></span> <span data-ttu-id="49aa5-127">高いスループットでは、さらにサーバーとホスティング インフラストラクチャに投資する必要性が低く、同じハードウェアを指定したアプリケーションからより多くの顧客を提供することができますを意味します。</span><span class="sxs-lookup"><span data-stu-id="49aa5-127">The higher-throughput means you can serve more customers from an application given the same hardware, further reducing the need to invest in servers and hosting infrastructure.</span></span>

## <a name="cross-platform"></a><span data-ttu-id="49aa5-128">クロス プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="49aa5-128">Cross Platform</span></span>

<span data-ttu-id="49aa5-129">ASP.NET Core は、プラットフォーム間で Linux MacOS と Windows 上で実行できます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-129">ASP.NET Core is cross-platform, and can run on Linux and MacOS as well as Windows.</span></span> <span data-ttu-id="49aa5-130">これは、開発と ASP.NET Core でビルドされたアプリの展開の両方の多くの新しいオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-130">This opens up many new options for both development and deployment of apps built with ASP.NET Core.</span></span> <span data-ttu-id="49aa5-131">Docker コンテナーは、通常 Linux を現在実行して、ASP.NET Core アプリケーションの利点を活用することをホストできる[コンテナーおよび microservices](../microservices-architecture)です。</span><span class="sxs-lookup"><span data-stu-id="49aa5-131">Docker containers, which typically run Linux today, can host ASP.NET Core applications, allowing them to take advantage of the benefits of [containers and microservices](../microservices-architecture).</span></span>

## <a name="modular-and-loosely-coupled"></a><span data-ttu-id="49aa5-132">モジュール化し、疎結合</span><span class="sxs-lookup"><span data-stu-id="49aa5-132">Modular and Loosely Coupled</span></span>

<span data-ttu-id="49aa5-133">NuGet パッケージは、.NET Core で捉えるおよび ASP.NET Core アプリケーションは NuGet で多くのライブラリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-133">NuGet packages are first-class citizens in .NET Core, and ASP.NET Core apps are composed of many libraries through NuGet.</span></span> <span data-ttu-id="49aa5-134">この細分性の機能により、アプリはのみに依存し、実際には、必要な領域の低減、フット プリントとセキュリティの脆弱性の機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="49aa5-134">This granularity of functionality helps ensure apps only depend on and deploy functionality they actually require, reducing their footprint and security vulnerability surface area.</span></span>

<span data-ttu-id="49aa5-135">ASP.NET Core は、内部的とアプリケーション レベルの両方も完全に依存関係の挿入をサポートします。</span><span class="sxs-lookup"><span data-stu-id="49aa5-135">ASP.NET Core also fully supports dependency injection, both internally and at the application level.</span></span> <span data-ttu-id="49aa5-136">インターフェイスは、スワップ アウトでき、必要に応じて、複数の実装であることができます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-136">Interfaces can have multiple implementations that can be swapped out as needed.</span></span> <span data-ttu-id="49aa5-137">依存関係の挿入は、やすく拡張、保守、およびテストするために、これらのインターフェイスに疎結合にアプリがします。</span><span class="sxs-lookup"><span data-stu-id="49aa5-137">Dependency injection allows apps to loosely couple to those interfaces, making them easier to extend, maintain, and test.</span></span>

## <a name="easily-tested-with-automated-tests"></a><span data-ttu-id="49aa5-138">自動テストを簡単にテスト</span><span class="sxs-lookup"><span data-stu-id="49aa5-138">Easily Tested with Automated Tests</span></span>

<span data-ttu-id="49aa5-139">ASP.NET Core アプリケーションが単体テストをサポートし、疎結合との依存関係挿入できるサポート簡単にテスト目的での偽の実装とインフラストラクチャ上の問題をスワップします。</span><span class="sxs-lookup"><span data-stu-id="49aa5-139">ASP.NET Core applications support unit testing, and their loose coupling and support for dependency injections makes it easy to swap infrastructure concerns with fake implementations for test purposes.</span></span> <span data-ttu-id="49aa5-140">ASP.NET Core では、メモリ内のホストのアプリに使用できる TestServer も同梱されています。</span><span class="sxs-lookup"><span data-stu-id="49aa5-140">ASP.NET Core also ships a TestServer that can be used to host apps in memory.</span></span> <span data-ttu-id="49aa5-141">機能テスト (ミドルウェア、ルーティング、モデルのバインド、フィルターなどを含む) 完全なアプリケーション スタックを使用すること、このメモリ内のサーバーに要求を作成でき、時間の割合ですべての応答を受け取るためにかかる実際のサーバー上でのアプリをホストネットワーク レイヤーを通じて要求を作成したりします。</span><span class="sxs-lookup"><span data-stu-id="49aa5-141">Functional tests can then make requests to this in-memory server, exercising the full application stack (including middleware, routing, model binding, filters, etc.) and receiving a response, all in a fraction of the time it would take to host the app on a real server and make requests through the network layer.</span></span> <span data-ttu-id="49aa5-142">これらのテストが記述するには特に容易、貴重な api、か最新の web アプリケーションでますます重要にします。</span><span class="sxs-lookup"><span data-stu-id="49aa5-142">These tests are especially easy to write, and valuable, for APIs, which are increasingly important in modern web applications.</span></span>

## <a name="traditional-and-spa-behaviors-supported"></a><span data-ttu-id="49aa5-143">従来と SPA 動作のサポート</span><span class="sxs-lookup"><span data-stu-id="49aa5-143">Traditional and SPA Behaviors Supported</span></span>

<span data-ttu-id="49aa5-144">従来の web アプリケーションでは、ほとんどのクライアント側の動作が関係しているが、代わりに依存して、サーバーのすべてのナビゲーション、クエリ、および更新プログラム、アプリが行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="49aa5-144">Traditional web applications have involved little client-side behavior, but instead have relied on the server for all navigation, queries, and updates the app might need to make.</span></span> <span data-ttu-id="49aa5-145">エンドユーザーのブラウザーでページ全体の再読み込みされている結果を使用して新しい web 要求に変換されるユーザーが行った各新しい操作。</span><span class="sxs-lookup"><span data-stu-id="49aa5-145">Each new operation made by the user would be translated into a new web request, with the result being a full page reload in the end user's browser.</span></span> <span data-ttu-id="49aa5-146">従来のモデル ビュー コント ローラー (MVC) フレームワークには、さらに、モデルで作業とビューを返す別のコント ローラーのアクションに対応する新しい要求のたびにこの方法は、通常に従います。</span><span class="sxs-lookup"><span data-stu-id="49aa5-146">Classic Model-View-Controller (MVC) frameworks typically follow this approach, with each new request corresponding to a different controller action, which in turn would work with a model and return a view.</span></span> <span data-ttu-id="49aa5-147">AJAX (Asynchronous JavaScript and XML) 機能により、特定のページにある個々 の操作を拡張することがありますが、多くのさまざまな MVC ビューと URL エンドポイントを使用するアプリの全体的なアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="49aa5-147">Some individual operations on a given page might be enhanced with AJAX (Asynchronous JavaScript and XML) functionality, but the overall architecture of the app used many different MVC views and URL endpoints.</span></span>

<span data-ttu-id="49aa5-148">これに対し、単一ページ アプリケーション (SPAs) は、(存在する場合) はほとんどの動的に生成されたサーバー側ページ読み込みが含まれません。</span><span class="sxs-lookup"><span data-stu-id="49aa5-148">Single Page Applications (SPAs), by contrast, involve very few dynamically generated server-side page loads (if any).</span></span> <span data-ttu-id="49aa5-149">多くの SPAs を起動し、アプリを実行するために必要な JavaScript ライブラリを読み込むための静的 HTML ファイル内で初期化されます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-149">Many SPAs are initialized within a static HTML file which loads the necessary JavaScript libraries to start and run the app.</span></span> <span data-ttu-id="49aa5-150">これらのアプリ、データ ニーズを満たす web Api の使用率が高いを行い程度豊富なユーザー エクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-150">These apps make heavy usage of web APIs for their data needs, and can provide much richer user experiences.</span></span>

<span data-ttu-id="49aa5-151">多くの web アプリケーションには、従来の web アプリケーションの動作 (通常はコンテンツ) との対話機能) SPAs の組み合わせが含まれます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-151">Many web applications involve a combination of traditional web application behavior (typically for content) and SPAs (for interactivity).</span></span> <span data-ttu-id="49aa5-152">ASP.NET Core は、MVC および web ツールの同じセットを使用して、フレームワーク ライブラリを基になる、同じアプリケーション内の Api の両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="49aa5-152">ASP.NET Core supports both MVC and web APIs in the same application, using the same set of tools and underlying framework libraries.</span></span>

## <a name="simple-development-and-deployment"></a><span data-ttu-id="49aa5-153">単純な開発と配置</span><span class="sxs-lookup"><span data-stu-id="49aa5-153">Simple Development and Deployment</span></span>

<span data-ttu-id="49aa5-154">ASP.NET Core アプリケーションを作成するには、単純なテキスト エディターとコマンド ライン インターフェイス、または Visual Studio と同様に、フル機能の開発環境を使用します。</span><span class="sxs-lookup"><span data-stu-id="49aa5-154">ASP.NET Core applications can be written using simple text editors and command line interfaces, or full-featured development environments like Visual Studio.</span></span> <span data-ttu-id="49aa5-155">モノリシックなアプリケーションは通常、単一のエンドポイントを展開します。</span><span class="sxs-lookup"><span data-stu-id="49aa5-155">Monolithic applications are typically deployed to a single endpoint.</span></span> <span data-ttu-id="49aa5-156">展開は、継続的インテグレーション (CI) と継続的な配信 (CD) パイプラインの一部として発生する可能性を簡単に自動化できます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-156">Deployments can easily be automated to occur as part of a continuous integration (CI) and continuous delivery (CD) pipeline.</span></span> <span data-ttu-id="49aa5-157">従来 CI/CD のツールに加えて、Windows Azure は git リポジトリ用のサポートが統合されてし、指定された git ブランチまたはタグに行われるように自動的に、更新プログラムを展開できます。</span><span class="sxs-lookup"><span data-stu-id="49aa5-157">In addition to traditional CI/CD tools, Windows Azure has integrated support for git repositories and can automatically deploy updates as they are made to a specified git branch or tag.</span></span>

## <a name="traditional-aspnet-and-web-forms"></a><span data-ttu-id="49aa5-158">従来の ASP.NET および Web フォーム</span><span class="sxs-lookup"><span data-stu-id="49aa5-158">Traditional ASP.NET and Web Forms</span></span>

<span data-ttu-id="49aa5-159">ASP.NET Core、従来の ASP.NET だけでなく 4.x は引き続き web アプリケーションを構築するための堅牢性と信頼性の高いプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="49aa5-159">In addition to ASP.NET Core, traditional ASP.NET 4.x continues to be a robust and reliable platform for building web applications.</span></span> <span data-ttu-id="49aa5-160">ASP.NET は、MVC、Web API の開発モデルだけでなく、豊富なページ ベースのアプリケーションの開発に適してと機能の豊富なサード パーティ コンポーネント エコシステム Web フォームをサポートします。</span><span class="sxs-lookup"><span data-stu-id="49aa5-160">ASP.NET supports MVC and Web API development models, as well as Web Forms, which is well-suited to rich page-based application development and features a rich third-party component ecosystem.</span></span> <span data-ttu-id="49aa5-161">Windows Azure は、ASP.NET 4.x アプリケーションの優れた従来からサポートを持ち、多くの開発者はこのプラットフォームに精通します。</span><span class="sxs-lookup"><span data-stu-id="49aa5-161">Windows Azure has great longstanding support for ASP.NET 4.x applications, and many developers are familiar with this platform.</span></span>

> ### <a name="references--modern-web-applications"></a><span data-ttu-id="49aa5-162">参照: 最新の Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="49aa5-162">References – Modern Web Applications</span></span>
> - <span data-ttu-id="49aa5-163">**ASP.NET Core の概要**</span><span class="sxs-lookup"><span data-stu-id="49aa5-163">**Introduction to ASP.NET Core**</span></span>  
> <span data-ttu-id="49aa5-164"><https://docs.microsoft.com/aspnet/core/></span><span class="sxs-lookup"><span data-stu-id="49aa5-164"><https://docs.microsoft.com/aspnet/core/></span></span>
> - <span data-ttu-id="49aa5-165">**6 キー メリットの ASP.NET Core を使用する異なると向上します。**</span><span class="sxs-lookup"><span data-stu-id="49aa5-165">**Six Key Benefits of ASP.NET Core which make it Different and Better**</span></span>  
> <span data-ttu-id="49aa5-166"><https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/></span><span class="sxs-lookup"><span data-stu-id="49aa5-166"><https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/></span></span>
> - <span data-ttu-id="49aa5-167">**ASP.NET Core でのテスト**</span><span class="sxs-lookup"><span data-stu-id="49aa5-167">**Testing in ASP.NET Core**</span></span>  
> <span data-ttu-id="49aa5-168"><https://docs.microsoft.com/aspnet/core/testing/></span><span class="sxs-lookup"><span data-stu-id="49aa5-168"><https://docs.microsoft.com/aspnet/core/testing/></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="49aa5-169">[前](index.md) [次へ] (choose-between-traditional-web-and-single-page-apps.md)</span><span class="sxs-lookup"><span data-stu-id="49aa5-169">[Previous] (index.md) [Next] (choose-between-traditional-web-and-single-page-apps.md)</span></span>