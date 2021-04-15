---
title: CTEM
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: ht
source-wordcount: '140'
ht-degree: 100%

---


# CTEM {#ctem}

カスタムテンプレート

## 背景 {#background}

`CTEM` は、AEM にインストールされているカスタムテンプレートを識別します。この情報は、ベストプラクティスの評価を目的として提供されます。

テンプレートは、「cq:Template」というプライマリタイプの値で識別できます。このコードに次のいずれかのサブタイプを指定して、テンプレートのカテゴリを識別します。

* `custom.editable.template`：テンプレートパスは「/apps」で始まりません。
* `custom.static.template`：テンプレートパスは「/apps」で始まります。

## 可能性のある影響およびリスク {#implications-and-risks}

* ベストプラクティスは、静的テンプレートをすべて、編集可能なテンプレートに変更することです。

## 可能な解決策 {#solutions}

* [AEM Modernization Tools](https://opensource.adobe.com/aem-modernize-tools/) を利用して、静的テンプレートを編集可能テンプレートに移行します。
* 編集可能テンプレートの詳細については、「[テンプレート](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=ja)」を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
