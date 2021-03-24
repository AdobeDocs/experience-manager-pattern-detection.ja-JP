---
title: DOPI
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 6%

---


# DOPI {#dopi}

非推奨の順序付けられたプロパティインデックス

## 背景 {#background}

`DOPI` は、6.1以降で廃止され、6.2で削除された、Ordered Property Index Definitions(`primaryType=oak:QueryIndexDefinition` AND `type="ordered"`)の使用を示します。

## 可能性のある影響およびリスク {#implications-and-risks}

* 一部のクエリは応答しない場合があります。
* 顧客の機能が正しく動作しない可能性があります。
* 廃止されたインデックスに対するトラバーサルの警告やエラー、著しいパフォーマンスのペナルティはありません。

## 可能な解決策 {#solutions}

* インデックス定義を変更して、サポートされているインデックス定義にします。 ([Oakクエリとインデックス](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html)を参照)。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)プロジェクトを見直し、[DOPI違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)がどのように修正され、AEMとCloud Serviceとして互換性を持つかを理解します。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
