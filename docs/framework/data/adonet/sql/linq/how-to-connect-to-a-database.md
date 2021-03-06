---
title: "HOW TO：連接資料庫 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# HOW TO：連接資料庫
<xref:System.Data.Linq.DataContext> 是主要管道，您可以透過該管道連接至資料庫、擷取資料庫中的物件，以及將變更送回給資料庫。  而 <xref:System.Data.Linq.DataContext> 的使用方式與 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] <xref:System.Data.SqlClient.SqlConnection> 的使用方式相同。  事實上，<xref:System.Data.Linq.DataContext> 是使用您所提供的連接或連接字串 \(Connection String\) 來初始化。  如需詳細資訊，請參閱[DataContext 方法 \(O\/R 設計工具\)](../Topic/DataContext%20Methods%20\(O-R%20Designer\).md)。  
  
 <xref:System.Data.Linq.DataContext> 的用途是將物件的要求轉譯為針對資料庫進行的 SQL 查詢，然後再從結果中組合物件。  <xref:System.Data.Linq.DataContext> 會實作與標準查詢運算子 \(如 `Where` 和 `Select`\) 相同的運算子模式，來啟用 [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)]。  
  
> [!IMPORTANT]
>  維護安全的連接是最重要的事。  如需詳細資訊，請參閱[LINQ to SQL 的安全性](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md)。  
  
## 範例  
 在下列範例中，<xref:System.Data.Linq.DataContext> 是用來連接至 Northwind 範例資料庫，以及擷取城市為倫敦 \(London\) 之客戶的資料列。  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 使用實體類別來識別每個資料庫資料表，這樣每個資料庫資料表會以透過 <xref:System.Data.Linq.DataContext.GetTable%2A> 方法取得的 `Table` 集合表示。  
  
## 範例  
 最佳做法是宣告強型別 \(Strongly Typed\) <xref:System.Data.Linq.DataContext>，而不是依賴基本 <xref:System.Data.Linq.DataContext> 類別和 <xref:System.Data.Linq.DataContext.GetTable%2A> 方法。  強型別 <xref:System.Data.Linq.DataContext> 會將所有 `Table` 集合宣告為內容的成員 \(如下列範例所示\)。  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 接著，您可以用下列更簡單的方式表示針對倫敦 \(London\) 客戶的查詢：  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## 請參閱  
 [與資料庫通訊](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)