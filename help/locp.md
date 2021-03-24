---
title: LOCP
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 43%

---


# LOCP {#locp}

/libs カスタムパッケージの上書き

## 背景 {#background}

`LOCP` コンテンツを配信するカスタムパッケージの検出を識別します。これは、アンチパターン `/libs`です（ACLの場合を除く）。

## 可能性のある影響およびリスク {#implications-and-risks}

* カスタムコードは、CFP、SP または主要な AEM アップグレードで削除されたり置き換えられたりする場合があります。
* 新しいコンテンツが適切にインストールされない場合があります。

## 可能な解決策 {#solutions}

* カスタマーパッケージでは、`/libs`ではなく`/apps`にコンテンツを展開する必要があります。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
