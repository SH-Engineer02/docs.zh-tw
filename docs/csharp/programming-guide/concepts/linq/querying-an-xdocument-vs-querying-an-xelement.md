---
title: "查詢 XDocument 與查詢 XElement (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9a3da563618ad3dbc9797f252ab51588a43ce8e6
ms.contentlocale: zh-tw
ms.lasthandoff: 03/13/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a>查詢 XDocument 與查詢 XElement (C#)
透過 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> 載入文件時，您會注意到，撰寫查詢的方式與透過 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> 載入時略有不同。  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>XDocument.Load 和 XElement.Load 之比較  
 透過 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> 將 XML 文件載入到 <xref:System.Xml.Linq.XElement> 時，XML 樹狀結構根節點的 <xref:System.Xml.Linq.XElement> 會包含已載入文件的根項目。 不過，當您透過 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> 將相同的 XML 文件載入到 <xref:System.Xml.Linq.XDocument> 時，樹狀結構的根節點是 <xref:System.Xml.Linq.XDocument> 節點，而已載入文件的根項目是 <xref:System.Xml.Linq.XDocument> 的允許子系 <xref:System.Xml.Linq.XElement> 節點。 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 座標軸會相對於根節點進行運算。  
  
 這個第一個範例會使用 <xref:System.Xml.Linq.XElement.Load%2A> 載入 XML 樹狀結構。 接著，它會針對樹狀結構根目錄的子項目進行查詢。  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 這個範例預期會產生下列輸出：  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 下列範例與上述範例幾乎相同，不同處在於會將 XML 樹狀結構載入到 <xref:System.Xml.Linq.XDocument> 而非 <xref:System.Xml.Linq.XElement>。  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 這個範例會產生下列輸出：  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 請注意，相同的查詢會傳回一個 `Root` 節點，而非三個子節點。  
  
 其中一個處理方法是在存取座標軸方法之前使用 <xref:System.Xml.Linq.XDocument.Root%2A> 屬性，如下所示：  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 這個查詢現在會以查詢根節點為 <xref:System.Xml.Linq.XElement> 的樹狀結構的相同方式執行。 這個範例會產生下列輸出：  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>另請參閱  
 [基本查詢 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
