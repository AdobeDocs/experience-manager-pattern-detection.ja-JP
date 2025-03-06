---
title: SCR
description: パターン検出コードのヘルプページ。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 7%

---

# SCR {#scr}

## 背景 {#background}

SIF は、AEM 6.5 LTS と互換性のないAEM Screensの使用状況を特定します。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

次の様々なサブタイプに対して考えられるソリューションを見つけます。

* `screens.bundles.detected` – これらのバンドルはアップグレード時にアンインストールされます。
* `screens.packages.detected` – これらのパッケージはアップグレード中に削除されます。
* `screens.packages.dependency` - カスタムパッケージからScreensへの依存を排除します。
* `screens.configs.detected` - カスタムコードでScreens設定プロパティを使用していないことを確認します。
* `screens.users.detected` - カスタムコードでScreens サービスユーザーを使用していないことを確認します。
* `screens.paths.detected` - Screensのパスを削除する前に、そのパスがAEMで使用されていないことを確認します。
* `screens.resource.type.detected` - Screens リソースタイプの使用状況を削除します。
* `screens.usage` - カスタムコードからScreens API を削除します。