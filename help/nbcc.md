---
title: NBCC
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 9%

---


# NBCC {#nbcc}

後方互換性のない変更

## 背景 {#background}

`NBCC` 一部のJCRノードまたはバンドルが互換性のない方法で変更された状況を識別します。アップグレード前に、お客様はこの変更を認識していない可能性があります。

## 可能性のある影響およびリスク {#implications-and-risks}

* 下位互換性のない変更を使用するコンポーネントに依存する機能は壊れる可能性があり、正しく解決されない場合があります。
* アップグレード後、お客様のアプリケーションの一部の機能や、AEMの一部の機能が正常に動作しない場合があります。

## 可能な解決策 {#solutions}

* 下位互換性のあるSlingコンポーネントのみをオーバーレイまたは参照します。
* AEMのアップグレード後に、`/libs`やバンドルからのリソースを適応させることを検討します。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
