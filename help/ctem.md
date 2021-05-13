---
title: CTEM
description: パターン検出コードのヘルプページ
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
translation-type: ht
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: ht
source-wordcount: '284'
ht-degree: 100%

---

# CTEM {#ctem}

カスタムテンプレート

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_overview"
>title="カスタムテンプレート"
>abstract="CTEM は、AEM にインストールされているカスタムコンポーネントを識別します。この情報は、ベストプラクティスの評価を目的として提供されます。"

`CTEM` は、AEM にインストールされているカスタムテンプレートを識別します。この情報は、ベストプラクティスの評価を目的として提供されます。

テンプレートは、「cq:Template」というプライマリタイプの値で識別できます。このコードに次のいずれかのサブタイプを指定して、テンプレートのカテゴリを識別します。

* `custom.editable.template`：テンプレートパスは「/apps」で始まりません。
* `custom.static.template`：テンプレートパスは「/apps」で始まります。

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、静的テンプレートをすべて、編集可能なテンプレートに変更することをお勧めします。ユーザーは、既存の AEM Modernization Tools を利用して静的テンプレートを編集可能テンプレートに移行できます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=ja" text="編集可能なテンプレート"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM Modernization Tools"

* ベストプラクティスとしては、静的テンプレートをすべて、編集可能なテンプレートに変更することをお勧めします。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="ツールとリソース"
>abstract="AEM Modernization Tools スイートを使用すると、ページの構造を操作して、静的な定義から編集可能なテンプレートに変更できます。従来の限られた機能から堅牢な最新の AEM ソリューションに移行する際の支援を目的としたツールです。これらのツールは設定可能かつ拡張可能です。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/page-structure.html" text="ページ構造コンバーター"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* [AEM Modernization Tools](https://opensource.adobe.com/aem-modernize-tools/) を利用して、静的テンプレートを編集可能テンプレートに移行します。
* 編集可能テンプレートの詳細については、「[テンプレート](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=ja)」を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
