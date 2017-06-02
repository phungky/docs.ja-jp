---
title: "Single-Table Queries (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b74bcf8-3f87-449f-bff7-6bcb0d69d212
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Single-Table Queries (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] のクエリは、<xref:System.Collections.Generic.IEnumerable%601> インターフェイスまたは <xref:System.Query.IQueryable%601> インターフェイスを実装するデータ ソースに対して動作します。  <xref:System.Data.DataTable> クラスには、いずれのインターフェイスも実装されていません。そのため、[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] クエリの `From` 句でソースとして <xref:System.Data.DataTable> を使用する場合は、<xref:System.Data.DataTableExtensions.AsEnumerable%2A> メソッドを呼び出す必要があります。  
  
 次の例では、SalesOrderHeader テーブルからオンラインでの注文をすべて取得し、注文 ID、注文日、および注文番号をコンソールに出力します。  
  
 [!code-csharp[dp linq to dataset examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]
 [!code-vb[dp linq to dataset examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]  
  
 ローカル変数 query はクエリ式で初期化されます。クエリ式は、少なくとも 1 つのクエリ演算子 \(標準クエリ演算子、[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] の場合は <xref:System.Data.DataSet> クラスに固有の演算子\) が適用されることによって、1 つまたは複数の情報ソースに対して機能します。  前の例のクエリ式には、2 つの標準クエリ演算子、`Where` と `Select` が使用されています。  
  
 この場合、`Where` 句では、`OnlineOrderFlag` \= `true` という条件に基づいてデータを抽出します。  `Select` 演算子は、その演算子に渡された引数をキャプチャする列挙可能なオブジェクトを割り当てて返します。  上の例では、`SalesOrderID`、`OrderDate`、`SalesOrderNumber` の 3 つのプロパティを使って匿名型を作成しています。  この 3 つのプロパティの値は、`SalesOrderHeader` テーブルの `SalesOrderID` 列、`OrderDate` 列、および `SalesOrderNumber` 列の値に設定されます。  
  
 次に、`Select` から返された列挙可能なオブジェクトを `foreach` ループで列挙し、クエリ結果を出力します。  クエリは <xref:System.Collections.Generic.IEnumerable%601> を実装する <xref:System.Linq.Enumerable> 型であるため、`foreach` ループでクエリ変数を反復処理するまでクエリは評価されません。  クエリの評価を遅らせることで、繰り返し評価することのできる値としてクエリを維持し、評価のたびに異なる結果を得ることができます。  
  
 <xref:System.Data.DataRowExtensions.Field%2A> は、<xref:System.Data.DataRow> の列値にアクセスするためのメソッドです。また、前出の例には使用されていませんが、<xref:System.Data.DataRowExtensions.SetField%2A> を使用すると、<xref:System.Data.DataRow> の列値を設定できます。  <xref:System.Data.DataRowExtensions.Field%2A> メソッドも <xref:System.Data.DataRowExtensions.SetField%2A> メソッドも Null 許容型を扱うことができるため、Null 値を明示的にチェックする必要はありません。  また、どちらのメソッドもジェネリック メソッドです。つまり、戻り値の型をキャストする必要はありません。  <xref:System.Data.DataRow> の既存の列アクセサー \(`o["OrderDate"]` など\) を使用することもできますが、その場合、返されたオブジェクトを適切な型にキャストする必要があります。  列に NULL 値が許容されている場合、<xref:System.Data.DataRow.IsNull%2A> メソッドを使って、値が NULL かどうかをチェックする必要があります。  詳細については、「[Generic Field and SetField Methods](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)」を参照してください。  
  
 <xref:System.Data.DataRowExtensions.Field%2A> メソッドおよび <xref:System.Data.DataRowExtensions.SetField%2A> メソッドのジェネリック パラメーター `T` に指定するデータ型は、基になる値の型と一致している必要があります。一致していない場合、<xref:System.InvalidCastException> がスローされます。  指定する列の名前も <xref:System.Data.DataSet> 内の列名と一致している必要があります。一致していない場合、<xref:System.ArgumentException> がスローされます。  どちらの場合も、例外は、実行時にデータが列挙されて、クエリが実行されたときにスローされます。  
  
## 参照  
 [Cross\-Table Queries](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)   
 [Querying Typed DataSets](../../../../docs/framework/data/adonet/querying-typed-datasets.md)   
 [Generic Field and SetField Methods](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)