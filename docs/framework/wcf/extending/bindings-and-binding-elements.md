---
title: "バインディングとバインディング要素 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "バインディング要素 [WCF]"
ms.assetid: 765ff77b-7682-4ea3-90eb-e4d751e37379
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# バインディングとバインディング要素
バインディングは、*バインド要素*と呼ばれる特殊な構成要素のコレクションであり、クライアント エンドポイントまたはサービス エンドポイントが構築されるたびにサービス ランタイムによって評価されます。バインディング内のバインド要素の型と順序に基づいて、エンドポイントのチャネル スタック内のプロトコル チャネルとトランスポート チャネルが選択され、スタック順が決定されます。  
  
 また、バインディング \(特に、システム指定のバインディング\) は、通常、多数の構成プロパティを持ちますが、これらはカプセル化されたバインド要素の最も頻繁に変更されたプロパティを反映します。  
  
 バインディングには、トランスポート バインド要素が 1 つだけ含まれている必要があります。各トランスポート バインド要素は、1 つのメッセージ エンコード バインド要素をバインディングに追加することによってオーバーライドできる既定のメッセージ エンコード バインド要素です。トランスポート バインド要素とエンコーダー バインド要素に加えて、バインディングには任意の数のプロトコル バインド要素を含めることもできます。この要素により、サービスに必要な機能を実装し、エンドポイント間で SOAP メッセージを送信することができます。詳細については、「[サービスとクライアントを構成するためのバインディングの使用](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)」を参照してください。  
  
## バインディングとバインド要素の拡張  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] には、広範なシナリオをカバーするシステム指定のバインディングが用意されています \(詳細については、「[システム標準のバインディング](../../../../docs/framework/wcf/system-provided-bindings.md)」を参照してください\)。ただし、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] に用意されていないバインディングを作成し、使用することが必要になる場合もあります。次のシナリオでは、新しいバインディングを作成する必要があります。  
  
-   新しいバインド要素 \(新しいトランスポート バインド要素、エンコード バインド要素、またはプロトコル バインド要素\) を使用する場合。そのバインド要素を含む新しいバインディングを作成する必要があります。たとえば、UDP トランスポートのためのカスタム `UdpTransportBindingElement` を追加した場合は、そのカスタム バインド要素を使用する新しいバインディングを作成する必要があります。<xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName> 型を使用してこの動作を実行する方法については、「[カスタム バインディング](../../../../docs/framework/wcf/extending/custom-bindings.md)」を参照してください。  
  
-   パブリック プロパティでシステム指定のバインディングが公開されないように既存のバインド要素を構成する場合。たとえば、署名操作と暗号化操作の実行順序を変更するには、新しいバインディングを作成する必要があります。この動作を実行する方法については、「[方法 : システム指定のバインディングをカスタマイズする](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)」を参照してください。  
  
-   特定の構成オプションだけを公開する、企業の標準バインディングを確立する場合。たとえば、社内用にセキュリティを無効にできない <xref:System.ServiceModel.WSHttpBinding> のバリエーションを作成するには、<xref:System.ServiceModel.WSHttpBinding> のように動作し、セキュリティが常に有効になる新しいバインディングを作成します。詳細については、「[ユーザー定義バインディングの作成](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)」を参照してください。  
  
-   特定のカスタム バインド要素を状況に応じて構成または使用するようにメタデータをカスタマイズする場合。バインディングとバインド要素に対するメタデータのサポートの詳細については、「[構成とメタデータのサポート](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)」を参照してください。  
  
-  
  
## チャネル、バインディング、およびバインド要素  
 バインディングとバインド要素は、属性と動作を含むアプリケーション プログラミング モデルと、ファクトリとリスナー、メッセージ エンコーダー、およびトランスポートとプロトコルの実装を含むチャネル モデルを結び付けます。通常、バインド要素とバインディングは、アプリケーション層で使用されるチャネルを有効にするために実装されます。  
  
 チャネル層は、サービス層との間でメッセージを送受信し、そのメッセージをエンドポイント間で転送します。クライアントでは、チャネル層はネットワーク エンドポイントへのチャネルを作成するチャネル ファクトリのスタックです。サービスでは、チャネル層はネットワーク エンドポイントで受信されたチャネルを受け入れるチャネル リスナーのスタックです。  
  
 一般的なチャネルの種類としては、プロトコル チャネルとトランスポート チャネルの 2 つがあります。トランスポート チャネルの役割は、ネットワーク エンドポイント間でメッセージを実際に転送することです。トランスポート チャネルは、既定のメッセージ エンコーダーを持ち、メッセージ エンコーダー バインド要素を通じて供給される代替のメッセージ エンコーダーを使用できる必要があります。メッセージ エンコーダーには、<xref:System.ServiceModel.Channels.Message?displayProperty=fullName> をネットワーク上の表現に \(またはその逆方向に\) 変換する役割があります。プロトコル チャネルの役割は、SOAP レベルのプロトコル \(たとえば、WS\-Security や WS\-ReliableMessaging\) を実装することです。  
  
 トランスポート チャネルとプロトコル チャネルの主要要件は、必要なチャネル インターフェイスを実装することです。正常に機能するチャネル層を作成するには、ファクトリとリスナーを関連付ける必要があります。[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] でチャネルの実装を使用するには、チャネルごとに <xref:System.ServiceModel.Channels.BindingElement> から派生したバインド要素が関連付けられている必要があります。また、<xref:System.ServiceModel.Configuration.BindingElementExtensionElement> から派生する関連バインディング拡張要素を構成ファイルに含める必要もあります。  
  
 前述のように、メッセージ エンコーダー チャネル、プロトコル チャネル、およびトランスポート チャネルの実装に使用されるバインド要素をスタックすることによりチャネル スタックを形成できます。バインディングは、これらを順序付きセットに並べ替えるための機構です。バインディングとバインド要素は、アプリケーション プログラミング モデルをチャネル モデルに結び付けます。チャネルの実装をコードから直接使用することもできますが、エンコーダー、トランスポート、およびプロトコルがバインド要素として実装されていない限り、サービス層プログラミング モデルから使用できません。  
  
 チャネルとそのバインド要素の開発の詳細については、「[チャネル レイヤーの拡張](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)」を参照してください。