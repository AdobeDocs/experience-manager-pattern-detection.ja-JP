---
title: WRF
description: パターン検出コードのヘルプページ。
exl-id: 36578498-d5b2-46d1-a274-a1646ceaa764
source-git-commit: 29d702c9662fd185ef806123fc4f4a03a70d64aa
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# WRF {#wrf}

## 背景 {#background}

WRFは、AEM 6.5 LTSと互換性のないwe-retailの使用を特定します。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

以下の様々なサブタイプに対して考えられる解決策を見つけます。

* `weretail.bundles.detected` – これらのバンドルは、アップグレード中にアンインストールされます
* `weretail.packages.detected` – これらのパッケージはアップグレード中に削除されます
* `weretail.configs.detected` - カスタムコードでWe.Retail設定プロパティを使用しないでください
* `weretail.packages.dependency` - We.Retailの任意のカスタム パッケージの依存関係を削除します
* `weretail.paths.detected` – これらのWe.Retail パスは、ソーシャルを使用していないことを確認した後に削除できます
* `weretail.resource.type.detected` - We.Retail リソースタイプの使用状況を削除
* `weretail.usage` - カスタムコードからWe.Retail APIを削除します。
