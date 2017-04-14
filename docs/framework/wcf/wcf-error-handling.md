---
title: "WCF 錯誤處理 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# WCF 錯誤處理
WCF 應用程式遇到的錯誤屬於下列其中一個群組：  
  
1.  通訊錯誤  
  
2.  Proxy\/通道錯誤  
  
3.  應用程式錯誤  
  
 當網路無法使用、用戶端使用不正確的位址，或者服務主機並未接聽傳入訊息時，就會發生通訊錯誤。這種類型的錯誤會當做 <xref:System.ServiceModel.CommunicationException> 或 <xref:System.ServiceModel.CommunicationException> 衍生的類別傳回給用戶端。  
  
 Proxy\/通道錯誤是指發生在通道或 Proxy 本身內部的錯誤。這種類型的錯誤包括：嘗試使用已經關閉的 Proxy 或通道、用戶端與服務之間存在合約不符，或者服務拒絕了用戶端的認證。還有許多不同類型的錯誤屬於此分類，但是數目太多無法在此列出。這種類型的錯誤會依現狀傳回給用戶端 \(不在例外狀況物件上執行任何轉換\)。  
  
 應用程式錯誤會在服務作業執行期間發生。這種類型的錯誤會當做 <xref:System.ServiceModel.FaultException> 或 <xref:System.ServiceModel.FaultException%601> 傳送至用戶端。  
  
 WCF 中的錯誤處理包括下列其中一種或多種執行方式：  
  
-   直接處理擲回的例外狀況。系統只會針對通訊和 Proxy\/通道錯誤進行這種處理方式。  
  
-   使用錯誤合約  
  
-   實作 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 介面  
  
-   處理 <xref:System.ServiceModel.ServiceHost> 事件  
  
## 錯誤合約  
 錯誤合約可讓您以獨立於平台的方式定義服務作業期間可能會發生的錯誤。根據預設，從服務作業內部擲回的所有例外狀況都會當做 <xref:System.ServiceModel.FaultException> 物件傳回給用戶端。<xref:System.ServiceModel.FaultException> 物件所包含的資訊非常少。您可以定義錯誤合約並將錯誤當做 <xref:System.ServiceModel.FaultException%601> 傳回，藉以控制傳送至用戶端的資訊。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][指定與處理合約和服務中的錯誤](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## IErrorHandler  
 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 介面可讓您進一步控制 WCF 應用程式如何回應錯誤。這不僅能讓您完全控制傳送至用戶端的錯誤訊息，還能讓您執行自訂錯誤處理，例如記錄。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Dispatcher.IErrorHandler> 和 [延伸對錯誤處理和報告的控制](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)  
  
## ServiceHost 事件  
 <xref:System.ServiceModel.ServiceHost> 類別會裝載服務並定義許多處理錯誤可能需要的事件。例如：  
  
1.  <xref:System.ServiceModel.ServiceHost.Faulted>  
  
2.  <xref:System.ServiceModel.ServiceHost.UnknownMessageReceived>  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] <xref:System.ServiceModel.ServiceHost>