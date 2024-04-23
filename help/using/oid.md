---
title: OID
description: パターン検出コードのヘルプページ
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 50%

---

# OID {#oid}

Oak インデックス定義

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak Index Definition"
>abstract="OID は、Oak インデックスの定義に関連する問題を識別します。標準 Oak インデックス定義に加えられた変更を識別します。AEM as a Cloud Service と互換性のないカスタム Oak インデックス定義も識別されます。OID 検索の各メッセージは、インデックスを識別し、追加情報を提供します。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing#how-to-use" text="コンテンツインデックス作成ガイドライン"

OID は、Oak インデックスの定義に関連する問題を識別します。標準 Oak インデックス定義に加えられた変更を識別します。AEM as a Cloud Service と互換性のないカスタム Oak インデックス定義も識別されます。それぞれのメッセージ `OID` を検索すると、インデックスが識別され、追加情報が提供されます。

サブタイプを使用して、各種情報を識別します。

* `index.rule.violation`：カスタム Oak インデックスと AEM as a Cloud Service との非互換性
* `standard.index.modification`：標準 Oak インデックスに対する変更

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、すべてのカスタムインデックスを確認し、コンテンツインデックス作成ガイドラインに従って再構築することです。 インデックスコンバーターを使用して、既存のカスタム Oak インデックス定義をAEMのas a Cloud Serviceの互換性のあるカスタム Oak インデックス定義に移行します。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#oak-indexes" text="パッケージガイドライン"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools" text="インデックスコンバーター"

* 標準 Oak インデックス定義に対する変更は、AEM のアップグレード中に失われることがあります。
* Oak の定義は不変であるため、カスタムプロジェクトコードでパッケージ化します。またデプロイは Cloud Manager を使用してのみ行います。
* すべての Oak インデックス定義は、AEM as a Cloud Serviceの Oak インデックスの命名規則とその他の規則に従う必要があります。 そうしないと、望ましくない動作を引き起こす可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="ツールとリソース"
>abstract="wknd-legacy プロジェクトを確認し、プロジェクトの OID 違反を解決する方法を把握します。また、GitHub の OID 違反例を確認して、インデックスコンバーターツールを使用して従来のインデックスを変換し、AEMと互換性を持たせる方法もas a Cloud Serviceします。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="wknd-legacy プロジェクト"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID 違反の例 – GitHub"

* メッセージで特定されたインデックスルールの違反を解決します。
* 新しい Oak インデックス定義またはカスタム Oak インデックス定義をデプロイするには、AEMのas a Cloud Serviceに従います [包装ガイドライン](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure).
* カスタマイズしたAEM標準インデックスと新しいカスタム Oak インデックス定義は、に従う必要があります。 [コンテンツのインデックス作成ガイドライン](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing#preparing-the-new-index-definition) （AEMas a Cloud Service用）。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid) プロジェクトを検証し、AEM as a Cloud Service との互換性を維持するために [OID 違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)を修正および変更する方法を確認します。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
* の使用 [インデックスコンバーター](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools) 既存のカスタム Oak インデックス定義をAEMのas a Cloud Serviceの互換性のあるカスタム Oak インデックス定義に移行する場合。
