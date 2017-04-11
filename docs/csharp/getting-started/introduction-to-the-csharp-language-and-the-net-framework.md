---
title: "C# 言語と .NET Framework の概要 | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, about C# language
- Visual C#, about
ms.assetid: 0a2dff4e-cd84-42ff-8141-e89889b24081
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bfd3c08f69461d65140ef948672774a7435c326d
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-the-c-language-and-the-net-framework"></a>C# 言語と .NET Framework の概要
C# は、タイプ セーフで洗練されたオブジェクト指向言語です。C# を使用すると、[!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] で稼働する、安全で信頼性の高いさまざまなアプリケーションを構築できます。 C# を使用すると、Windows クライアント アプリケーション、XML Web サービス、分散コンポーネント、クライアント/サーバー アプリケーション、データベース アプリケーションなど、さまざまなアプリケーションを作成できます。 Visual C# には、高度なコード エディター、便利なユーザー インターフェイス デザイナー、統合デバッガーなど、C# 言語と [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] に基づいたアプリケーション開発をより簡単にする多数のツールが用意されています。  
  
> [!NOTE]
>  [!INCLUDE[csprcs](../../csharp/includes/csprcs_md.md)] のドキュメントは、基本的なプログラミング概念を理解している方を対象に書かれています。 初心者である場合、Web で入手できる [!INCLUDE[csprcsxpr](../../csharp/getting-started/includes/csprcsxpr_md.md)] が参考になります。 C# に関する書籍や Web リソースを利用して、実践的なプログラミング スキルを身に付けることもできます。  
  
## <a name="c-language"></a>C# 言語  
 C# の構文は表現力が豊かですが、単純ですぐに覚えることができます。 C、C++、または Java に慣れていれば、C# の中かっこ ({}) 構文をすぐに理解できます。 これらの言語のいずれかを理解していると、一般に、C# での開発を短期間で始めることができます。 C# 構文では、C++ の複雑な部分が数多く簡略化され、null 許容値型、列挙体、デリゲート、ラムダ式、ダイレクト メモリ アクセスなど、Java にはない強力な機能が実装されました。 C# はジェネリック メソッドおよびジェネリック型をサポートしているため、タイプ セーフおよびパフォーマンスが向上し、反復子もサポートしているため、クライアント コードで簡単に使用できるカスタムの反復動作をコレクション クラスの実装側が定義できます。 [!INCLUDE[vbteclinqext](../../csharp/getting-started/includes/vbteclinqext_md.md)] 式により、厳密に型指定されたクエリは高度な言語構成要素になります。  
  
 C# は、オブジェクト指向言語として、カプセル化、継承、およびポリモーフィズムの概念をサポートしています。 アプリケーションのエントリ ポイントである `Main` メソッドなど、変数とメソッドのすべてがクラス定義内でカプセル化されています。 親クラスから直接継承できるクラスは 1 つのみですが、クラスで実装できるインターフェイスの数は任意です。 親クラスの仮想メソッドをオーバーライドする場合、誤って再定義しないように、`override` キーワードを指定する必要があります。 C# の構造体はコンパクトなクラスのようなものです。インターフェイスを実装できるスタック割り当て型ですが、継承はサポートされていません。  
  
 C# には、基本的なオブジェクト指向の原則とは別に、次のように革新的な言語構成要素が用意されているため、ソフトウェア コンポーネントの開発が容易になります。  
  
-   メソッドのシグネチャをカプセル化する "*デリゲート*"。タイプ セーフなイベント通知を実行できます。  
  
-   プロパティ。プライベート メンバー変数へのアクセサーとして機能します。  
  
-   属性。実行時に型に関する宣言のメタデータを提供します。  
  
-   インライン XML ドキュメントのコメント。  
  
-   [!INCLUDE[vbteclinqext](../../csharp/getting-started/includes/vbteclinqext_md.md)]。さまざまなデータ ソースを対象とする組み込みのクエリ機能を提供します。  
  
 COM オブジェクトやネイティブの Win32 DLL など、他の Windows ソフトウェアと対話するには、C# で "相互運用" というプロセスを使用します。 C# プログラムで相互運用機能を使用すると、ネイティブの C++ アプリケーションで実行できる機能をほぼすべて実行できます。 さらに、ダイレクト メモリ アクセスが必須の場合でも、ポインターと "unsafe" コードの概念がサポートされます。  
  
 C# のビルド処理は、C や C++ よりも単純で Java よりも柔軟です。 ヘッダー ファイルは分かれていません。また、メソッドや型を特定の順序で宣言する必要はありません。 C# のソース ファイルでは、クラス、構造体、インターフェイス、およびイベントをいくつでも定義できます。  
  
 その他に、C# の参照ドキュメントを紹介します。  
  
-   C# 言語の概略については、「[C# 言語仕様](../../csharp/language-reference/language-specification.md)」の第 1 章を参照してください。  
  
-   C# 言語の具体的な側面の詳細については、「[C# リファレンス](../../csharp/language-reference/index.md)」を参照してください。  
  
-   [!INCLUDE[vbteclinq](../../csharp/includes/vbteclinq_md.md)] の詳細については、「[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)」を参照してください。  
  
-   Visual C# チームが提供する最新記事とその他のリソース見つけるには、[Visual C# デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=47811)を参照してください。  
  
## <a name="net-framework-platform-architecture"></a>.NET Framework のプラットフォーム アーキテクチャ  
 C# プログラムは、[!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] で実行されます。これは、共通言語ランタイム (CLR: Common Language Runtime) と呼ばれる仮想実行システムや統合的なクラス ライブラリを備えた Windows の統合コンポーネントです。 CLR は、共通言語基盤 (CLI: Common Language Infrastructure) をサポートする Microsoft のシステムです。CLI は、複数の言語やライブラリをシームレスに連携する実行環境と開発環境を構築するための、基本的な国際規格です。  
  
 C# で記述したソース コードは、CLI 仕様に準拠する中間言語 (IL) にコンパイルされます。 IL コードおよびリソース (ビットマップや文字列など) は、アセンブリと呼ばれる実行可能ファイルのあるディスクに保存されます。アセンブリの拡張子は、一般的に .exe か .dll です。 アセンブリに含まれるマニフェストには、アセンブリの種類、バージョン、カルチャ、およびセキュリティ要件に関する情報が規定されています。  
  
 C# プログラムを実行すると、アセンブリが CLR に読み込まれ、マニフェストの情報に基づいてさまざまな処理が実行されます。 このとき、セキュリティ要件に一致すると、CLR で Just-In-Time (JIT) コンパイルが実行され、IL コードはネイティブのマシン語命令に変換されます。 CLR には、自動的なガベージ コレクション、例外処理、およびリソース管理に関するサービスも用意されています。 CLR で実行されるコードは、"マネージ コード" と呼ばれることがあります。反対に、特定のシステムを対象にしたネイティブのマシン語にコンパイルされたコードは、"アンマネージ コード" と呼ばれることがあります。 C# ソース コード ファイル、.NET Framework クラス ライブラリ、アセンブリ、および CLR について、コンパイル時間と実行時間の関係を次の図に示します。  
  
 ![ C&#35; ソース コードからマシン実行へ](../../csharp/getting-started/media/netarchitecture.png "NETarchitecture")  
  
 言語の相互運用性は、[!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] の主要機能です。 C# コンパイラで生成された IL コードは、共通型の仕様 (CTS: Common Type Specification) に準拠しています。このため、C# の IL コードは、Visual Basic、Visual C++ の .NET バージョンを始めとする、20 を超える CTS 準拠言語で生成されたコードと相互運用性があります。 1 つのアセンブリには、異なる .NET 言語で記述されたモジュールを複数含めることができます。また、同じ言語で記述されている場合と同様に、型を参照することもできます。  
  
 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] には、実行時のサービス以外にも、4,000 クラスを超える多数のライブラリが用意されています。このライブラリは、ファイルの入出力、XML 解析のための文字列操作、Windows フォーム コントロールなど、役に立つさまざまな機能を備えた名前空間に構成されています。 C# アプリケーションでは、一般に、[!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] クラス ライブラリを広範囲に使用して、一般的な "配管工事" のような作業を処理しています。  
  
 .NET Framework の詳細については、[Microsoft .NET Framework の概要](http://msdn.microsoft.com/en-us/d05daf50-00fe-45c7-8383-06fe41697355)に関する記事を参照してください。  
  
## <a name="featured-book-chapters"></a>参考書籍の該当する章  
 『[Learning C# 3.0: Master the fundamentals of C# 3.0 (C# 3.0 の学習: C# 3.0 の基礎を習得)](http://go.microsoft.com/fwlink/?LinkId=195412)』の「[C# Language Fundamentals (C# 言語の基礎)](http://go.microsoft.com/fwlink/?LinkId=195416)」  
  
 『[Learning C# 3.0: Master the fundamentals of C# 3.0 (C# 3.0 の学習: C# 3.0 の基礎を習得)](http://go.microsoft.com/fwlink/?LinkId=195412)』の「[C# and .NET Programming (C# および .NET プログラミング)](http://go.microsoft.com/fwlink/?LinkId=195413)」  
  
 『[Beginning Visual C# 2010 (Visual C# 2010 の開始)](http://go.microsoft.com/fwlink/?LinkId=221214)』の「[Introducing C# (C# の紹介)](http://go.microsoft.com/fwlink/?LinkId=221226)」  
  
 『[Learning C# 3.0: Master the fundamentals of C# 3.0 (C# 3.0 の学習: C# 3.0 の基礎を習得)](http://go.microsoft.com/fwlink/?LinkId=195412)』の「[Visual Studio 2008 and C# Express 2008 (Visual Studio 2008 および C# Express 2008)](http://go.microsoft.com/fwlink/?LinkId=195414)」  
  
## <a name="see-also"></a>関連項目  
 [C#](../../csharp/csharp.md)   
 [Visual C# と Visual Basic の概要](https://docs.microsoft.com/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)