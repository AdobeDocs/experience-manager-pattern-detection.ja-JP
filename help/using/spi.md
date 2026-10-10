---
title: SPI
description: パターン検出コードのヘルプページ。
exl-id: 39f2d04e-c6e4-4da6-b000-0115bc2b87bf
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: baa8f6dbf24b735348ed6b27f1e885b5078859ce
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%
---
# SPI {#spi}

## 背景 {#background}

SIFは、AEM 6.5 LTSと互換性のないSearch and Promoteの使用を特定します。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

以下の様々なサブタイプに対して考えられる解決策を見つけます。

* `searchpromote.bundles.detected` – これらのバンドルは、アップグレード中にアンインストールされます
* `earchpromote.packages.detected` – これらのパッケージはアップグレード中に削除されます
* `searchpromote.packages.dependency` - カスタムパッケージに含まれる可能性のある検索と昇格の依存関係を削除します
* `searchpromote.usage` - カスタムコードから検索およびプロモーション APIを削除します
* `searchpromote.users.detected` - カスタムコードでSearch and Promote サービスユーザーを使用しない
* `searchpromote.configs.detected` - カスタムコードで検索および昇格の設定プロパティを使用しないでください。
