---
title: "在 .NET Framework 4.5 工作流程中使用 .NET Framework 3.0 或 .NET Framework 3.5 活動 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 在 .NET Framework 4.5 工作流程中使用 .NET Framework 3.0 或 .NET Framework 3.5 活動
<xref:System.Activities.Statements.Interop> 活動可讓您在 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 工作流程中執行 .NET Framework 3.0 [!INCLUDE[wf](../../../../includes/wf-md.md)] 活動。這個範例示範如何使用 <xref:System.Activities.Statements.Interop> 活動，將字串當做引數傳遞至自訂 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 活動。  
  
## 若要使用這個範例  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 開啟 SimpleInterop.sln 方案檔案。  
  
2.  若要建置此方案，請按下 CTRL\+SHIFT\+B。  
  
3.  若要執行此方案，請按下 CTRL\+F5。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。請先檢查下列 \(預設\) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至[用於 .NET Framework 4 的 Windows Communication Foundation \(WCF\) 與 Windows Workflow Foundation \(WF\) 範例](http://go.microsoft.com/fwlink/?LinkId=150780)，以下載所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 範例。此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## 請參閱