---
title: "3551 - BufferOutOfOrderMessageNoBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3551 - BufferOutOfOrderMessageNoBookmark
## 屬性  
  
|||  
|-|-|  
|ID|3551|  
|關鍵字|WFServices|  
|層級|資訊|  
|通道|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## 描述  
 表示書籤繼續執行失敗。  當服務執行個體準備好處理這個特定作業時，就會再次嘗試緩衝接收作業。  
  
## 訊息  
 目前無法在服務執行個體 '%1' 上執行作業 '%2'。  將在服務執行個體準備就緒可以處理這個特定作業時，再次嘗試。  
  
## 詳細資料  
  
|資料項目名稱|資料項目型別|描述|  
|------------|------------|--------|  
|OperationName|xs:string|作業的名稱。|  
|ServiceInstanceId|xs:string|服務執行個體的 ID。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 傳回的字串。|