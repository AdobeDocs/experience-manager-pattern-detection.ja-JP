---
title: SCR
description: パターン検出コードのヘルプページ。
exl-id: 13b14cc2-f70b-45ff-a62d-dee647311d84
source-git-commit: 29d702c9662fd185ef806123fc4f4a03a70d64aa
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 7%

---

# SCR {#scr}

## 背景 {#background}

SIFは、AEM 6.5 LTSと互換性のないAEM Screensの使用状況を特定します。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

以下の様々なサブタイプに対して考えられる解決策を見つけます。

* `screens.bundles.detected` – これらのバンドルは、アップグレード中にアンインストールされます。
* `screens.packages.detected` – これらのパッケージは、アップグレード中に削除されます。
* `screens.packages.dependency` - Screensへの依存関係をカスタムパッケージから削除します。
* `screens.configs.detected` - カスタムコードでScreens設定プロパティを使用していないことを確認してください。
* `screens.users.detected` - カスタムコードでScreens サービスユーザーを使用していないことを確認してください。
* `screens.paths.detected` - Screens パスがAEMで使用されていないことを確認した後、パスを削除します。
* `screens.resource.type.detected` - Screens リソースタイプの使用状況を削除します。
* `screens.usage` - カスタムコードからScreens APIを削除します。
