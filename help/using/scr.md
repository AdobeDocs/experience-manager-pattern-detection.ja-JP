---
title: SCR
description: パターン検出コードのヘルプページ。
exl-id: 13b14cc2-f70b-45ff-a62d-dee647311d84
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: baa8f6dbf24b735348ed6b27f1e885b5078859ce
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
