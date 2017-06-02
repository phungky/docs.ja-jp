---
title: "トランスポート セキュリティと証明書認証 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
caps.latest.revision: 20
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 20
---
# トランスポート セキュリティと証明書認証
このトピックでは、トランスポート セキュリティを使用する場合にサーバーとクライアントの認証に X.509 証明書を使用する方法について説明します。X.509 証明書の詳細については、「[X.509 公開キー証明書](http://msdn.microsoft.com/library/bb540819\(VS.85\).aspx)」を参照してください。証明書は、証明機関によって発行される必要があります。多くの場合、証明機関はサードパーティの証明書発行者です。Windows サーバー ドメインでは、そのドメインのクライアント コンピューターに対して証明書を発行する際に Active Directory 証明書サービスを使用できます。詳細については、「[Windows 2008 R2 証明書サービス](http://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409)」を参照してください。このシナリオでは、Secure Sockets Layer \(SSL\) を使用して構成されたインターネット インフォメーション サービス \(IIS\) でサービスをホストします。サービスは、クライアントがサーバーの ID を確認するための SSL \(X.509\) 証明書を使用して構成されます。クライアントも、サービスがクライアントの ID を確認するための X.509 証明書を使用して構成されます。サーバーの証明書はクライアントによって信頼されている必要があり、クライアントの証明書はサーバーによって信頼されている必要があります。サービスとクライアントが互いの ID を確認する方法の実際のしくみについては、このトピックでは説明しません。詳細については、Wikipedia の「[デジタル署名](http://go.microsoft.com/fwlink/?LinkId=253157)」を参照してください。  
  
 このシナリオでは、次の図に示すような要求\/応答のメッセージ パターンを実装します。  
  
 ![証明書を使用した、セキュリティで保護された転送](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968\-899f\-4538\-a9e8\-0eaa872a291c")  
  
 サービスでの証明書の使用方法[!INCLUDE[crabout](../../../../includes/crabout-md.md)]、「[証明書の使用](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)」および「[方法 : SSL 証明書を使用してポートを構成する](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)」を参照してください。このシナリオのさまざまな特性を次の表に示します。  
  
|特性|説明|  
|--------|--------|  
|セキュリティ モード|トランスポート|  
|相互運用性|既存の Web サービス クライアントおよびサービスとの相互運用性|  
|認証 \(サーバー\)<br /><br /> 認証 \(クライアント\)|○ \(SSL 証明書を使用\)<br /><br /> ○ \(X.509 証明書を使用\)|  
|データの整合性|○|  
|データの機密性|○|  
|トランスポート|HTTPS|  
|バインディング|<xref:System.ServiceModel.WSHttpBinding>|  
  
## サービスの構成  
 このシナリオのサービスは IIS でホストされるので、web.config ファイルを使用して構成します。次の web.config は、トランスポート セキュリティと X.509 クライアント資格情報を使用するように <xref:System.ServiceModel.WSHttpBinding> を構成する方法を示しています。  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>              
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>            
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
  
```  
  
## クライアントの構成  
 クライアントはコードまたは app.config ファイルで構成できます。次の例は、クライアントをコードで構成する方法を示しています。  
  
```vb  
// Create the binding.  
WSHttpBinding myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name   
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.   
EndpointAddress ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator   
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
CalculatorClient cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
  
```  
  
 また、次の例のように App.config ファイルでクライアントを構成することもできます。  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "   
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="Binding1"   
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
  
```  
  
## 参照  
 [セキュリティの概要](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Windows Server AppFabric のセキュリティ モデル](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)