---
title: LOCP
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: ht
source-wordcount: '93'
ht-degree: 100%

---


# LOCP {#locp}

/libs カスタムパッケージの上書き

## 背景 {#background}

`LOCP` は、コンテンツを `/libs` に配信するカスタムパッケージを検出し識別します。これは、ACL の場合を除き、アンチパターンです。

## 可能性のある影響およびリスク {#implications-and-risks}

* カスタムコードは、CFP、SP または主要な AEM アップグレードで削除されたり置き換えられたりする場合があります。
* 新しいコンテンツが適切にインストールされない場合があります。

## 可能な解決策 {#solutions}

* カスタムパッケージでは、コンテンツは、`/libs` ではなく `/apps` にデプロイする必要があります。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
