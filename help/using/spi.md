---
title: SPI
description: パターン検出コードのヘルプページ。
exl-id: 39f2d04e-c6e4-4da6-b000-0115bc2b87bf
source-git-commit: 29d702c9662fd185ef806123fc4f4a03a70d64aa
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
