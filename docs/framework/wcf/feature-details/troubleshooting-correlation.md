---
title: "相関関係のトラブルシューティング | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98003875-233d-4512-a688-4b2a1b0b5371
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# 相関関係のトラブルシューティング
相関関係は、ワークフロー サービス メッセージを互いに関連付けたり、正しいワークフロー インスタンスに関連付けたりするために使用されますが、正しく構成されていないと、メッセージが受信されず、アプリケーションが正しく機能しなくなります。ここでは、相関関係のトラブルシューティングのいくつかの方法の概要と、相関関係を使用するときに発生する一般的な問題について説明します。  
  
## UnknownMessageReceived イベントの処理  
 <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> イベントは、サービスで不明なメッセージ \(既存のインスタンスに関連付けることができないメッセージなど\) が受信されたときに発生します。自己ホスト型サービスでは、このイベントをホスト アプリケーションで処理できます。  
  
```csharp  
host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)  
{  
    Console.WriteLine("Unknown Message Received:");  
    Console.WriteLine(e.Message);  
};  
```  
  
 Web ホスト サービスでこのイベントを処理するには、まず、<xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> の派生クラスを作成し、<xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A> をオーバーライドします。  
  
```csharp  
class CustomFactory : WorkflowServiceHostFactory  
{  
    protected override WorkflowServiceHost CreateWorkflowServiceHost(Activity activity, Uri[] baseAddresses)  
    {  
        // Create the WorkflowServiceHost.  
        WorkflowServiceHost host = new WorkflowServiceHost(activity, baseAddresses);  
  
        // Handle the UnknownMessageReceived event.  
        host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)  
        {  
            Console.WriteLine("Unknown Message Received:");  
            Console.WriteLine(e.Message);  
        };  
  
        return host;  
    }  
}  
```  
  
 次に、そのカスタムの <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> をサービスの `svc` ファイルで指定します。  
  
```  
<% @ServiceHost Language="C#" Service="OrderServiceWorkflow" Factory="CustomFactory" %>  
```  
  
 このハンドラーが呼び出されると、<xref:System.ServiceModel.UnknownMessageReceivedEventArgs> の <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> プロパティを使用して次のようなメッセージを取得できます。  
  
```Output  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <To s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://localhost:8080/OrderService</To>  
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>  
  </s:Header>  
  <s:Body>  
    <AddItem xmlns="http://tempuri.org/">  
      <Item>Books</Item>  
    </AddItem>  
  </s:Body>  
</s:Envelope>  
  
```  
  
 <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> ハンドラーにディスパッチされたメッセージを調べることで、メッセージがワークフロー サービスのインスタンスに関連付けられなかった理由の手がかりを得られる可能性があります。  
  
## 追跡によるワークフローの進行状況の監視  
 追跡を使用すると、ワークフローの進行状況を監視できます。既定では、ワークフローのライフサイクル イベント、アクティビティのライフサイクル イベント、エラー伝達、およびブックマーク再開に対して追跡レコードが出力されます。そのほかに、カスタム アクティビティでカスタム追跡レコードを出力することもできます。相関関係のトラブルシューティングでは、アクティビティ追跡レコード、ブックマーク再開レコード、およびエラー伝達レコードが最も役立ちます。アクティビティ追跡レコードを使用すると、ワークフローの現在の進行状況を確認したり、現在メッセージを待機しているメッセージング アクティビティを特定したりすることができます。ブックマーク再開レコードを使用すると、ワークフローでメッセージが受信されたかどうかを確認できます。エラー伝達レコードは、ワークフローで発生したエラーの記録を提供します。追跡を有効にするには、<xref:System.ServiceModel.Activities.WorkflowServiceHost> の <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> で目的の <xref:System.Activities.Tracking.TrackingParticipant> を指定します。次の例では、既定の追跡プロファイルを使用して `ConsoleTrackingParticipant` \(「[カスタム追跡](../../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md)」を参照\) を構成しています。  
  
```csharp  
host.WorkflowExtensions.Add(new ConsoleTrackingParticipant());  
```  
  
 ConsoleTrackingParticipant などの追跡参加要素は、コンソール ウィンドウを持つ自己ホスト型ワークフロー サービスで使用できます。Web ホスト サービスでは、追跡情報を永続ストアに記録する追跡参加要素 \(組み込みの <xref:System.Activities.Tracking.EtwTrackingParticipant> など\) か、情報をファイルに記録するカスタムの追跡参加要素 \(「[テキスト ファイルを使用した追跡](../../../../docs/framework/windows-workflow-foundation/samples/tracking-using-a-text-file.md)」の `TextWriterTrackingParticpant` など\) を使用する必要があります。  
  
 Web ホスト ワークフロー サービスの追跡および追跡の構成[!INCLUDE[crabout](../../../../includes/crabout-md.md)]、「[ワークフロー追跡とトレース](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)」、「[ワークフローの追跡の構成](../../../../docs/framework/windows-workflow-foundation//configuring-tracking-for-a-workflow.md)」、および「[追跡 &#91;WF サンプル&#93;](../../../../docs/framework/windows-workflow-foundation/samples/tracking.md)」のサンプルを参照してください。  
  
## WCF トレースの使用  
 WCF トレースは、ワークフロー サービスのメッセージ フローのトレースを提供します。このトレース情報は、相関関係 \(特にコンテンツ ベースの相関関係\) のトラブルシューティングに役立ちます。トレースを有効にするには、`web.config` ファイル \(Web ホスト ワークフロー サービスの場合\) または `app.config` ファイル \(自己ホスト型ワークフロー サービスの場合\) の `system.diagnostics` セクションで目的のトレース リスナーを指定します。トレース ファイルにメッセージの内容を含めるには、`system.serviceModel` の `diagnostics` セクションの `messageLogging` 要素で `logEntireMessage` に対して `true` を指定します。次の例では、メッセージの内容を含むトレース情報を `service.svclog` という名前のファイルに書き込むように構成しています。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information" propagateActivity="true">  
        <listeners>  
          <add name="corr"/>  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="corr"/>  
        </listeners>  
      </source>  
    </sources>  
  
    <sharedListeners>  
      <add name="corr" type="System.Diagnostics.XmlWriterTraceListener" initializeData="c:\logs\service.svclog">  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
  
  <system.serviceModel>  
    <diagnostics>  
      <messageLogging logEntireMessage="true" logMalformedMessages="false"  
         logMessagesAtServiceLevel="false" logMessagesAtTransportLevel="true" maxSizeOfMessageToLog="2147483647">  
      </messageLogging>  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 `service.svclog` に含まれているトレース情報を表示するには、[サービス トレース ビューアー ツール \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) を使用します。この方法を使用すると、渡されたメッセージの内容そのものを調べてコンテンツ ベースの相関関係の <xref:System.ServiceModel.CorrelationQuery> に一致するかどうかを確認できるため、コンテンツ ベースの相関関係のトラブルシューティングで特に便利です。WCF トレース[!INCLUDE[crabout](../../../../includes/crabout-md.md)]、「[サービス トレース ビューアー ツール \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)」、「[トレースの構成](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)」、および「[トレースを使用したアプリケーションのトラブルシューティング](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)」を参照してください。  
  
## コンテキスト交換の相関関係の一般的な問題  
 相関関係の中には、特定の種類のバインドが使用されていないと正しく機能しないものがあります。たとえば、要求\/応答の相関関係には <xref:System.ServiceModel.BasicHttpBinding> などの双方向のバインドが、コンテキスト交換の相関関係には <xref:System.ServiceModel.BasicHttpContextBinding> などのコンテキスト ベースのバインドが必要です。双方向の操作はほとんどのバインドでサポートされているため、要求\/応答の相関関係ではあまり問題になりませんが、コンテキスト ベースのバインドはわずかしかなく \(<xref:System.ServiceModel.BasicHttpContextBinding>、<xref:System.ServiceModel.WSHttpContextBinding>、<xref:System.ServiceModel.NetTcpContextBinding> など\)、それらのいずれかが使用されていないと、ワークフロー サービスへの最初の呼び出しは成功しますが、その後の呼び出しが次の <xref:System.ServiceModel.FaultException> で失敗します。  
  
```Output  
サービスの受信メッセージにコンテキストが関連付けられておらず、  
現在の操作が "CanCreateInstance = true" でマークされていません。  
このサービスと通信するには、受信したバインドでコンテキスト プロトコルが  
サポートされているかどうか、有効なコンテキストが初期化されているかどうかを確認してください。  
```  
  
 コンテキスト相関関係に使用されるコンテキスト情報は、双方向の操作が使用されている場合は <xref:System.ServiceModel.Activities.SendReply> から \(コンテキスト相関関係を初期化する\) <xref:System.ServiceModel.Activities.Receive> アクティビティに返され、操作が一方向の場合は呼び出し元によって指定されます。コンテキストが呼び出し元によって送信されず、ワークフロー サービスからも返されない場合は、後続の操作が呼び出されたときに上述の <xref:System.ServiceModel.FaultException> が返されます。  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [コンテキスト交換](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md).  
  
## 要求\/応答の相関関係の一般的な問題  
 要求\/応答の相関関係は、<xref:System.ServiceModel.Activities.ReceiveReply> と <xref:System.ServiceModel.Activities.Send> のペアと使用すると、ワークフロー サービスに双方向の操作を実装でき、<xref:System.ServiceModel.Activities.SendReply> と <xref:System.ServiceModel.Activities.Receive> のペアと使用すると、別の Web サービスの双方向の操作を呼び出すことができます。WCF サービスの双方向の操作を呼び出す場合、このサービスには、従来の命令型のコード ベースの [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] サービスを使用することも、ワークフロー サービスを使用することもできます。要求\/応答の相関関係を使用するには、<xref:System.ServiceModel.BasicHttpBinding> などの双方向のバインドを使用する必要があります。操作が双方向である必要もあります。  
  
 ワークフロー サービスで、並行または重複する <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> のペアまたは <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply> のペアに双方向の操作があると、<xref:System.ServiceModel.Activities.WorkflowServiceHost> によって提供される暗黙の関連付けハンドル管理が \(特に高負荷のシナリオで\) 不十分となり、メッセージが正しくルーティングされなくなる可能性があります。この問題が発生しないようにするために、要求\/応答の相関関係を使用する際には常に <xref:System.ServiceModel.Activities.CorrelationHandle> を明示的に指定することをお勧めします。ワークフロー デザイナーの **\[ツールボックス\]** の \[メッセージング\] セクションにある **SendAndReceiveReply** テンプレートと **ReceiveAndSendReply** テンプレートを使用すると、<xref:System.ServiceModel.Activities.CorrelationHandle> が既定で明示的に構成されます。コードを使用してワークフローを作成する場合は、ペアの最初のアクティビティの <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> で <xref:System.ServiceModel.Activities.CorrelationHandle> を指定します。次の例では、<xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> で <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> を明示的に指定して <xref:System.ServiceModel.Activities.Receive> アクティビティを構成しています。  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = ... // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> のペアや <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply> のペアの間で永続化を使用することはできません。両方のアクティビティが完了するまで存続する非永続化ゾーンが作成されます。遅延アクティビティなどのアクティビティがこの非永続化ゾーンにあって、ワークフローのアイドル状態を引き起こした場合、ホストでワークフローがアイドル状態になったときにワークフローを永続化するようにホストが構成されていても、ワークフローは永続化されません。Persist アクティビティなどのアクティビティが非永続化ゾーンで明示的に永続化を試みた場合、致命的な例外がスローされ、ワークフローが中止されて、<xref:System.ServiceModel.FaultException> が呼び出し元に返されます。次の致命的な例外メッセージが表示されます。"System.InvalidOperationException: 持続性のないブロックに Persist アクティビティを含めることはできません。"この例外は呼び出し元に返されませんが、追跡が有効になっている場合は確認できます。呼び出し元に返される <xref:System.ServiceModel.FaultException> のメッセージは、"WorkflowInstance '5836145b\-7da2\-49d0\-a052\-a49162adeab6' が完了しているため、操作を実行できませんでした" です。  
  
 要求\/応答の相関関係[!INCLUDE[crabout](../../../../includes/crabout-md.md)]、「[要求\/応答](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)」を参照してください。  
  
## コンテンツ ベースの相関関係の一般的な問題  
 コンテンツ ベースの相関関係は、ワークフロー サービスが複数のメッセージを受信し、交換されるメッセージ内の一部のデータによって目的のインスタンスが識別される場合に使用されます。コンテンツ ベースの相関関係では、顧客番号や注文 ID などのメッセージ内のデータを使用して、適切なワークフロー インスタンスにメッセージをルーティングします。ここでは、コンテンツ ベースの相関関係を使用するときに発生するいくつかの一般的な問題について説明します。  
  
### 識別データが一意であることの確認  
 インスタンスの識別に使用されるデータは、相関関係キーにハッシュされます。相関関係による関連付けで使用するデータは必ず、一意にする必要があります。一意でない場合は、ハッシュされたキーで競合が発生し、誤った場所にメッセージがルーティングされる可能性があります。たとえば、顧客名だけに基づいた関連付けでは、同じ名前の顧客が複数存在する場合があるため、競合が発生する可能性があります。メッセージの関連付けに使用するデータの一部として、コロン \(:\) を使用することはできません。コロンは、メッセージ クエリのキーと値の区切り文字として既に使用されており、後でハッシュされる文字列に含まれるためです。永続化を使用している場合は、現在の識別データが、以前に永続化されたインスタンスによって使用されていないかどうかを確認する必要があります。この問題は、永続化を一時的に無効にすることによって特定できます。WCF トレースを使用すると、計算された相関関係キーを表示できるため、この種の問題のデバッグに役立ちます。  
  
### 競合状態  
 サービスがメッセージを受信してから実際に相関関係が初期化されるまでにはわずかな時間差があり、その間は後続のメッセージが無視されます。ワークフロー サービスで、クライアントから一方向の操作で渡されるデータを使用してコンテンツ ベースの相関関係が初期化される場合に、呼び出し元が後続のメッセージをすぐに送信すると、この時間差の間それらのメッセージが無視されます。この問題を回避するには、双方向の操作を使用して相関関係を初期化するか、<xref:System.ServiceModel.Activities.TransactedReceiveScope> を使用します。  
  
### 関連付けクエリについての問題  
 関連付けクエリは、メッセージの関連付けに使用するメッセージ内のデータを指定するために使用されます。このデータは、XPath クエリを使用して指定します。特に問題がないように見えるにもかかわらず、サービスへのメッセージがディスパッチされない場合は、トラブルシューティングの手法として、メッセージ データの値に一致するリテラル値を XPath クエリの代わりに指定することができます。リテラル値を指定するには `string` 関数を使用します。次の例では、`OrderId` に対して `11445` というリテラル値を使用するように <xref:System.ServiceModel.MessageQuerySet> が構成されています。XPath クエリはコメント アウトされています。  
  
```csharp  
MessageQuerySet = new MessageQuerySet  
{  
    {  
        "OrderId",   
        //new XPathMessageQuery("sm:body()/tempuri:StartOrderResponse/tempuri:OrderId")  
        new XPathMessageQuery("string('11445')")  
    }  
}  
```  
  
 関連付けデータが取得されないなど、XPath クエリが正しく構成されていない場合、次のメッセージと共にエラーが返されます。"関連付けクエリで空の結果セットが生成されました。エンドポイントの関連付けクエリが正しく構成されていることを確認してください。"前のセクションで説明したとおり、XPath クエリをリテラル値と置換すると、すばやくトラブルシューティングすることができます。この問題は、**\[関連付け初期化子の追加\]** ダイアログ ボックスまたは **\[CorrelatesOn の定義\]** ダイアログ ボックスで XPath クエリ ビルダーを使用し、ワークフロー サービスでメッセージ コントラクトが使用された場合に発生する可能性があります。次の例では、メッセージ コントラクト クラスを定義します。  
  
```csharp  
[MessageContract]  
public class AddItemMessage  
{  
    [MessageHeader]  
    public string CartId;  
  
    [MessageBodyMember]  
    public string Item;  
}  
  
```  
  
 このメッセージ コントラクトはワークフローの <xref:System.ServiceModel.Activities.Receive> アクティビティで使用されます。メッセージのヘッダーにある `CartId` は、メッセージを正しいインスタンスに関連付けるために使用されます。`CartId` を取得する XPath クエリがワークフロー デザイナーの関連付けダイアログを使用して作成される場合、次の正しくないクエリが生成されます。  
  
```  
sm:body()/xg0:AddItemMessage/xg0:CartId  
  
```  
  
 <xref:System.ServiceModel.Activities.Receive> アクティビティがデータのパラメーターを使用した場合、この XPath クエリは正しいですが、メッセージ コントラクトを使用しているため、誤りとなります。次の XPath クエリがヘッダーから `CartId` を取得するために正しい XPath クエリです。  
  
```  
sm:header()/tempuri:CartId  
  
```  
  
 これはメッセージの本文を調べて確認することができます。  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>  
    <h:CartId xmlns:h="http://tempuri.org/">80c95b41-c98d-4660-a6c1-99412206e54c</h:CartId>  
  </s:Header>  
  <s:Body>  
    <AddItemMessage xmlns="http://tempuri.org/">  
      <Item>Books</Item>  
    </AddItemMessage>  
  </s:Body>  
</s:Envelope>  
  
```  
  
 次の例では、データを受信するために前のメッセージ コントラクトを使用する `AddItem` 操作のために構成された <xref:System.ServiceModel.Activities.Receive> アクティビティを示します。XPath クエリは正しく構成されています。  
  
```xaml  
<Receive CorrelatesWith="[CCHandle] OperationName="AddItem" ServiceContractName="p:IService">  
  <Receive.CorrelatesOn>  
    <XPathMessageQuery x:Key="key1">  
      <XPathMessageQuery.Namespaces>  
        <ssx:XPathMessageContextMarkup>  
          <x:String x:Key="xg0">http://schemas.datacontract.org/2004/07/MessageContractWFService</x:String>  
        </ssx:XPathMessageContextMarkup>  
      </XPathMessageQuery.Namespaces>sm:header()/tempuri:CartId</XPathMessageQuery>  
  </Receive.CorrelatesOn>  
  <ReceiveMessageContent DeclaredMessageType="m:AddItemMessage">  
    <p1:OutArgument x:TypeArguments="m:AddItemMessage">[AddItemMessage]</p1:OutArgument>  
  </ReceiveMessageContent>  
</Receive>  
  
```  
  
 コンテンツ ベースの相関関係[!INCLUDE[crabout](../../../../includes/crabout-md.md)]、「[コンテンツ ベース](../../../../docs/framework/wcf/feature-details/content-based-correlation.md)」および「[相関電卓](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)」を参照してください。