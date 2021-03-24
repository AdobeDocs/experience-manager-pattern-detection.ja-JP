---
title: CTEM
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 8%

---


# CTEM {#ctem}

カスタムテンプレート

## 背景 {#background}

`CTEM` AEMにインストールされているカスタムテンプレートを識別します。この情報は、ベストプラクティス評価の目的で提供されます。

テンプレートは、「cq:Template」の主なタイプ値で識別されます。 サブタイプは、次のコードで使用され、テンプレートのカテゴリを識別します。

* `custom.editable.template`:テンプレートのパスは「/apps」と開始しません。
* `custom.static.template`:「/apps」を含むテンプレート開始のパスです。

## 可能性のある影響およびリスク {#implications-and-risks}

* ベストプラクティスは、すべての静的テンプレートを編集可能なテンプレートに移動することです。

## 可能な解決策 {#solutions}

* 静的テンプレートを編集可能なテンプレートに移行するには、[AEM Modernization Tools](https://opensource.adobe.com/aem-modernize-tools/)を利用します。
* 編集可能なテンプレートの詳細については、[テンプレート](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)を参照してください。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
