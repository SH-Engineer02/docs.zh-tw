---
title: "dotnet-add reference 命令 - .NET Core CLI | Microsoft Docs"
description: "dotnet-add reference 命令提供方便的選項，以新增專案對專案參考。"
keywords: "dotnet-add, CLI, CLI 命令, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e2a3efd-443c-4f23-a1b1-a662a5387879
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 1b342f0aea19c01d7bdae94552019f4c171fd1a2
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-add-reference"></a>dotnet-add reference

## <a name="name"></a>名稱

`dotnet-add reference` - 新增專案對專案 (P2P) 參考。

## <a name="synopsis"></a>概要

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>說明

`dotnet add reference` 命令提供方便的選項，將專案參考新增至專案。 執行命令之後，系統就會將 [`<ProjectReference>`](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-items) 元素新增至專案檔。

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>引數

`PROJECT`

指定專案檔。 如果未指定，命令會在目前的目錄中搜尋一個方案檔。

`PROJECT_REFERENCES`

要新增的專案對專案 (P2P) 參考。 指定一個或多個專案。 Unix/Linux 系統支援 [Glob 模式 (英文)](https://en.wikipedia.org/wiki/Glob_(programming))。

## <a name="options"></a>選項

`-h|--help`

印出命令的簡短說明。

`-f|--framework <FRAMEWORK>`

只有在以特定[架構](../../standard/frameworks.md)為目標時，才能新增專案參考。

## <a name="examples"></a>範例

新增專案參考：

`dotnet add app/app.csproj reference lib/lib.csproj`

新增多個專案參考：

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

在 Linux/Unix 上使用 Glob 模式新增多個專案參考：

`dotnet add app/app.csproj reference **/*.csproj`

