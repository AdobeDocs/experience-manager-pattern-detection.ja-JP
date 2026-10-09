---
title: SIF
description: パターン検出コードのヘルプページ。
exl-id: c0a5c565-16e7-407b-befc-5a2966089da1
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: baa8f6dbf24b735348ed6b27f1e885b5078859ce
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 7%
---
# SIF {#sif}

## 背景 {#background}

SIFは、AEM 6.5 LTSと互換性のないソーシャル使用を特定します。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能な解決策 {#solutions}

以下の様々なサブタイプに対して考えられる解決策を見つけます。

* `social.bundles.detected` – これらのバンドルは、アップグレード中にアンインストールされます
* `social.packages.detected` – これらのパッケージはアップグレード中に削除されます
* `social.packages.dependency` - ソーシャルのパッケージ依存関係をカスタムパッケージから削除してください
* `social.nodes.detected` - カスタム コードを更新して、ソーシャル ノードを作成しないようにします
* `social.configs.detected` - カスタム コードでソーシャル設定プロパティを使用しない
* `social.users.detected` - カスタムコードでソーシャルユーザーを使用しない
* `social.overlays.detected` - ソーシャルオーバーレイの使用を削除
* `social.paths.detected` – これらのパスがAEMで使用されていないことを確認した後、ソーシャルパスを削除します
* `social.resource.type.detected` - ソーシャルリソースタイプの使用状況を削除
* `social.usage` - カスタム コードからソーシャル APIを削除します。
