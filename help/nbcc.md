---
title: NBCC
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: ht
source-wordcount: '123'
ht-degree: 100%

---


# NBCC {#nbcc}

後方互換性のない変更

## 背景 {#background}

`NBCC` は、一部の JCR ノードやバンドルが、互換性のない方法で変更される状況を識別します。アップグレードの前に、お客様がこの変更について認識していないことがあります。

## 可能性のある影響およびリスク {#implications-and-risks}

* 後方互換性のない変更を使用したいずれかのコンポーネントに依存する機能は、破損したり、正しく解決されない可能性があります。
* アップグレード後に、お客様のアプリケーションの機能や AEM 機能の一部が正しく動作しなくなる場合があります。

## 可能な解決策 {#solutions}

* 後方互換性のある Sling コンポーネントだけをオーバーレイまたは参照の対象とします。
* AEM のアップグレード後、`/libs` またはバンドルに由来するリソースを適合させること検討してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
