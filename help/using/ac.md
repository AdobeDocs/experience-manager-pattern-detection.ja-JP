---
title: AC
description: パターン検出コードのヘルプページ。
exl-id: 4c6ac075-5ba6-4511-97c6-a9b496d4677a
source-git-commit: 29d702c9662fd185ef806123fc4f4a03a70d64aa
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 7%

---

# AC {#ac}

## 背景 {#background}

ACは、AEM 6.5 LTSと互換性のないAssets バンドルの使用状況を特定します

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

以下の様々なサブタイプに対して考えられる解決策を見つけます。

* `asset.bundles.detected` – このバンドルはアップグレード中にアンインストールされます。
* `asset.usage` - アセットの評価とアセット カタログ コンポーネントの依存関係をカスタム コードから削除します。 該当する場合は、新しいAPI `List<Scene7ConfigSetting>` `com.day.cq.dam.scene7.api.model.Scene7ViewerConfig#getSettingsList()`を使用するようにコードを変更します。
* `asset.overlays.detected` - Assetsの評価とカタログのコンポーネントで作成されたオーバーレイを削除する必要があります。
* `asset.resource.type.detected` - カスタムコードでのAssets評価コンポーネントのリソースの種類の使用をすべて削除します。
* `asset.paths.detected` – これらのパスの下にある顧客コンテンツを移動し、これらのパスがAEMで使用されていないことを確認した後、これらのパスを削除します。
