---
title: "&lt;ws2007FederationHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;ws2007FederationHttpBinding&gt;
衍生自 [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 且支援聯合安全性的安全、可互通的繫結。  
  
## 語法  
  
```  
  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"   
        hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        privacyNoticeAt="Uri"  
        privacyNoticeVersion="Integer"  
        proxyAddress="Uri"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                issuedTokenType="string"  
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"           
            maxStringContentLength="Integer" />  
    </binding>  
</ws2007FederationHttpBinding>  
```  
  
## 屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### 屬性  
  
|屬性|描述|  
|--------|--------|  
|`bypassProxyOnLocal`|一個指出本機位址是否略過 Proxy 伺服器的值。  預設為 `false`。|  
|`closeTimeout`|<xref:System.TimeSpan> 值，指定提供用來讓關閉作業完成的時間間隔。  這個值應該大於或等於 <xref:System.TimeSpan.Zero>。  預設為 00:01:00。|  
|`hostnameComparisonMode`|指定用於剖析 URI 的 HTTP 主機名稱比較模式。  這個屬性的型別為 <xref:System.ServiceModel.HostnameComparisonMode>，表示比對 URI 時此主機名稱是否會用來取用服務。  預設值為 <xref:System.ServiceModel.HostnameComparisonMode.StrongWildcard>，表示比對時忽略主機名稱。|  
|`maxBufferPoolSize`|此繫結的緩衝集區大小上限。  預設為 524,288 個位元組 \(512 \* 1024\)。  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 有許多組件會使用緩衝區。  每次使用這些組件時建立並終結緩衝區是高度耗費資源的作業，回收緩衝區的記憶體也是如此。  有了緩衝集區，您就可以從集區取出緩衝區來使用，用完後再還給集區，  因此可以避免建立及終結緩衝區的負荷。|  
|`maxReceivedMessageSize`|在使用此繫結設定之通道上可以接收的訊息大小上限 \(以位元組為單位，包括標頭\)。  超出此限制之訊息的寄件者將會收到 SOAP 錯誤。  收件者會捨棄訊息，然後在追蹤記錄檔中建立此事件的項目。  預設值為 65536。|  
|`messageEncoding`|定義用來對訊息進行編碼的編碼器。  有效值包括以下的值：<br /><br /> -   Text：使用文字訊息編碼器。<br />-   Mtom：使用 Message Transmission Organization Mechanism 1.0 \(MTOM\) 編碼器。<br /><br /> 預設為 Text。<br /><br /> 此屬性的型別為 <xref:System.ServiceModel.WSMessageEncoding>。|  
|`name`|繫結的組態名稱。  這個值應該是唯一的，因為它會當做繫結的識別使用。  從 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 開始，繫結和行為都不需要有名稱。  如需預設組態和無名稱繫結與行為的詳細資訊，請參閱[簡化的組態](../../../../../docs/framework/wcf/simplified-configuration.md)和[WCF 服務的簡化組態](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。|  
|`openTimeout`|<xref:System.TimeSpan> 值，指定提供用來讓開啟作業完成的時間間隔。  這個值應該大於或等於 <xref:System.TimeSpan.Zero>。  預設為 00:01:00。|  
|`privactyNoticeAt`|隱私權注意事項所在的 URI。|  
|`privactyNoticeVersion`|目前隱私權注意事項的版本。|  
|`proxyAddress`|指定 HTTP Proxy 位址的 URI。  如果 `useDefaultWebProxy` 為 `true`，則這項設定必須為 `null`。  預設為 `null`。|  
|`receiveTimeout`|<xref:System.TimeSpan> 值，指定接收作業完成其作業之時間間隔。  這個值應該大於或等於 <xref:System.TimeSpan.Zero>。  預設為 00:10:00。|  
|`sendTimeout`|<xref:System.TimeSpan> 值，指定提供用來讓傳送作業完成的時間間隔。  這個值應該大於或等於 <xref:System.TimeSpan.Zero>。  預設為 00:01:00。|  
|`textEncoding`|設定要在繫結上發出訊息時使用的字元集編碼方式。  有效值包括以下的值：<br /><br /> -   BigEndianUnicode：Unicode BigEndian 編碼方式。<br />-   Unicode：16 位元編碼方式。<br />-   UTF8：8 位元編碼方式。<br /><br /> 預設為 UTF8。  此屬性的型別為 <xref:System.Text.Encoding>。|  
|`transactionFlow`|指定繫結是否支援流動 WS\-Transactions 的值。  預設為 `false`。|  
|`useDefaultWebProxy`|一個值，指定是否使用系統自動設定的 HTTP Proxy。  如果這個屬性為 `true`，則 Proxy 位址必須為 `null` \(也就是不設定\)。  預設為 `true`。|  
  
### 子項目  
  
|項目|描述|  
|--------|--------|  
|[\<安全性\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|定義訊息的安全性設定。  此項目的型別為 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>。|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|定義 SOAP 訊息複雜度的條件約束，而這些條件約束可由以此繫結所設定的端點處理。  此項目的型別為 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。|  
|[reliableSession](http://msdn.microsoft.com/zh-tw/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|指定是否在通道端點之間建立可靠的工作階段。|  
  
### 父項目  
  
|項目|描述|  
|--------|--------|  
|[\<繫結\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|這個項目會保存標準和自訂繫結的集合。|  
  
## 備註  
 聯合是在多個企業或信任網域上共用識別以便進行驗證和授權的能力。  它使用 WS\-Trust 通訊協定從一信任網域對應身分識別表示至其他信任網域。  聯合 HTTP 繫結支援 SOAP 安全性以及混合模式安全性，但不支援獨立使用傳輸安全性。  使用這個繫結設定的服務必須使用 HTTP 傳輸。  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).  
  
## 範例  
  
```  
<configuration>  
<system.ServiceModel>  
<bindings>  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://www.contoso.com"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## 請參閱  
 <xref:System.ServiceModel.WS2007FederationHttpBinding>   
 <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>   
 [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)   
 [繫結](../../../../../docs/framework/wcf/bindings.md)   
 [設定系統提供的繫結](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/zh-tw/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<繫結\>](../../../../../docs/framework/misc/binding.md)