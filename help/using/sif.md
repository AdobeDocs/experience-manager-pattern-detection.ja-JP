---
title: SIF
description: パターン検出コードのヘルプページ。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 7%

---

# SIF {#sif}

## 背景 {#background}

SIF は、AEM 6.5 LTS と互換性のないソーシャル使用状況を特定します。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

次の様々なサブタイプに対して考えられるソリューションを見つけます。

* `social.bundles.detected` – これらのバンドルはアップグレード時にアンインストールされます
* `social.packages.detected` – これらのパッケージはアップグレード中に削除されます
* `social.packages.dependency` - ソーシャルのパッケージ依存関係をカスタム パッケージから削除してください
* `social.nodes.detected` - ソーシャルノードを作成しないようにカスタムコードを更新します
* `social.configs.detected` - カスタムコードでソーシャル設定プロパティを使用しない
* `social.users.detected` - カスタムコードでソーシャルユーザーを使用しない
* `social.overlays.detected` - ソーシャルオーバーレイの使用を削除
* `social.paths.detected` - ソーシャルパスがAEMで使用されていないことを確認した後、これらのパスを削除します
* `social.resource.type.detected` - ソーシャルリソースタイプの使用状況を削除
* `social.usage` - カスタムコードからソーシャル API を削除します。