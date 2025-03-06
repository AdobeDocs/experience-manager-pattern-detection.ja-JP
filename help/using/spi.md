---
title: SPI
description: パターン検出コードのヘルプページ。
source-git-commit: e050b9190f67fd6ccfac31490c4bf2a60d47731f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# SPI {#spi}

## 背景 {#background}

SIF は、AEM 6.5 LTS と互換性のない Search and Promote の使用を特定します。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

次の様々なサブタイプに対して考えられるソリューションを見つけます。

* `searchpromote.bundles.detected` – これらのバンドルはアップグレード時にアンインストールされます
* `earchpromote.packages.detected` – これらのパッケージはアップグレード中に削除されます
* `searchpromote.packages.dependency` - カスタムパッケージに含まれている可能性のある Search and Promote 依存関係を削除します
* `searchpromote.usage` - カスタムコードから Search and Promote API を削除します
* `searchpromote.users.detected` - カスタムコードで Search and Promote サービスユーザーを使用しない
* `searchpromote.configs.detected` - カスタムコードで Search and Promote 設定プロパティを使用しないでください。