---
title: CTEM
description: パターン検出コードのヘルプページ
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 64%

---

# CTEM {#ctem}

カスタムテンプレート

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_overview"
>title="カスタムテンプレート"
>abstract="CTEMは、AEMにインストールされているカスタムコンポーネントを識別します。 この情報は、ベストプラクティス評価の目的で提供されます。"

`CTEM` は、AEM にインストールされているカスタムテンプレートを識別します。この情報は、ベストプラクティスの評価を目的として提供されます。

テンプレートは、「cq:Template」というプライマリタイプの値で識別できます。このコードに次のいずれかのサブタイプを指定して、テンプレートのカテゴリを識別します。

* `custom.editable.template`：テンプレートパスは「/apps」で始まりません。
* `custom.static.template`：テンプレートパスは「/apps」で始まります。

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="導入ガイダンス"
>abstract="ベストプラクティスは、静的テンプレートをすべて、編集可能なテンプレートに変更することです。お客様は、既存のAEM最新化ツールを活用して、静的テンプレートを編集可能なテンプレートに移行できます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html" text="編集可能なテンプレート"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM Modernization Tools"

* ベストプラクティスは、静的テンプレートをすべて、編集可能なテンプレートに変更することです。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="ツールとリソース"
>abstract="AEM Modernization Suiteを使用すると、ユーザーは静的な定義から編集可能なテンプレートまで、ページの構造を操作できます。 目的は、お客様がレガシー機能の限られた機能から堅牢かつ最新のAEM製品に移行する際の支援です。 これらのツールは、構成に対応し、拡張可能で構成に対応しています。 ヘルプと説明を求めるAdobeサポートにご連絡ください。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/page-structure.html" text="ページ構造コンバーター"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloudサポート"

* [AEM Modernization Tools](https://opensource.adobe.com/aem-modernize-tools/) を利用して、静的テンプレートを編集可能テンプレートに移行します。
* 編集可能テンプレートの詳細については、「[テンプレート](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=ja)」を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
