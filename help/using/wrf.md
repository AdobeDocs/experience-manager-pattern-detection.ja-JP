---
title: WRF
description: パターン検出コードのヘルプページ。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 8%

---

# WRF {#wrf}

## 背景 {#background}

WRF は、AEM 6.5 LTS と互換性のない We-Retail の使用状況を特定します。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

次の様々なサブタイプに対して考えられるソリューションを見つけます。

* `weretail.bundles.detected` – これらのバンドルはアップグレード時にアンインストールされます
* `weretail.packages.detected` – これらのパッケージはアップグレード中に削除されます
* `weretail.configs.detected` - カスタムコードで We.Retail 設定プロパティを使用しない
* `weretail.packages.dependency` - We.Retail のカスタムパッケージの依存関係の削除
* `weretail.paths.detected` – これらの We.Retail パスは、ソーシャルを使用していないことを確認した後に削除できます
* `weretail.resource.type.detected` - We.Retail リソースタイプの使用状況の削除
* `weretail.usage` - カスタムコードから We.Retail API を削除します。