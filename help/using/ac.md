---
title: AC
description: パターン検出コードのヘルプページ。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 7%

---

# AC {#ac}

## 背景 {#background}

AC は、AEM 6.5 LTS と互換性のないAssets バンドルの使用を識別します

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

次の様々なサブタイプに対して考えられるソリューションを見つけます。

* `asset.bundles.detected` – このバンドルはアップグレード時にアンインストールされます。
* `asset.usage` - アセット評価およびアセットカタログコンポーネントの依存関係をカスタムコードから削除します。 必要に応じて、新しい API `List<Scene7ConfigSetting>` `com.day.cq.dam.scene7.api.model.Scene7ViewerConfig#getSettingsList()` を使用するようにコードを変更します。
* `asset.overlays.detected` - Assetsの評価およびカタログコンポーネント上に作成されたオーバーレイは削除する必要があります。
* `asset.resource.type.detected` - カスタムコード内のAssets評価コンポーネントの resourcetype の使用を削除します。
* `asset.paths.detected` – これらのパスの下に存在するお客様のコンテンツを移動し、これらのパスがAEMで使用されていないことを確認した後、これらのパスを削除します。