---
title: SQL Server の共通言語ランタイム統合
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 7451ed06e8a7c9797c66fd81734eb8b6b3b81f12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355738"
---
# <a name="sql-server-common-language-runtime-integration"></a>SQL Server の共通言語ランタイム統合
SQL Server 2005 で、Microsoft Windows 用の .NET Framework の共通言語ランタイム (CLR) コンポーネントの統合が導入されました。 つまり、Microsoft Visual Basic .NET や Microsoft Visual C# を含む任意の .NET Framework 言語を使用して、ストアド プロシージャ、トリガー、ユーザー定義型、ユーザー定義関数、ユーザー定義集計、およびストリーミング テーブル値関数を作成できるようになりました。 マネージ コードが Microsoft SQL Server 環境とデータをやり取りできるように、<xref:Microsoft.SqlServer.Server> 名前空間には新しいアプリケーション プログラミング インターフェイス (API) のセットが含まれています。  
  
 このセクションでは、SQL Server の共通言語ランタイム (CLR) 統合および SQL Server のインプロセス固有の ADO.NET の拡張に固有の機能や動作ついて説明します。  
  
 このセクションは、SQL Server の CLR 統合を利用したプログラミングを始めるのに十分な情報を提供することを目的としており、包括的な情報の提供は目的としていません。 詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。  
  
 **SQL Server オンライン ブック**  
  
1.  [共通言語ランタイム (CLR) 統合のプログラミングの概念](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a>このセクションの内容  
 [SQL Server の CLR 統合の概要](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 SQL Server の CLR 統合の概要について説明します。 追加情報へのリンクもあります。  
  
 [CLR ユーザー定義関数](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 テーブル値関数、スカラー関数、ユーザー定義集計関数など、さまざまな種類の CLR 関数の実装方法と使用方法について説明します。  
  
 [CLR ユーザー定義型](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 CLR のユーザー定義型を実装して使用する方法について説明します。 追加情報へのリンクもあります。  
  
 [CLR ストアド プロシージャ](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 CLR のストアド プロシージャを実装して使用する方法について説明します。 追加情報へのリンクもあります。  
  
 [CLR トリガー](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 CLR のトリガーを実装して使用する方法について説明します。 追加情報へのリンクもあります。  
  
 [コンテキスト接続](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 コンテキスト接続について説明します。  
  
 [SQL Server のインプロセス固有の ADO.NET の動作](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 SQL Server のインプロセス固有の ADO.NET の拡張およびコンテキスト接続について説明します。 追加情報へのリンクもあります。  
  
## <a name="see-also"></a>関連項目  
 [SQL Server と ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [マネージ コードでの SQL Server 2005 のオブジェクトの作成](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [ADO.NET のマネージ プロバイダーと DataSet デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=217917)
