---
title: OID
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 5a83dd8d08da974a5d775032b8dbea2593be9d15
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 2%

---


# OID {#oid}

Oakインデックスの定義

## 背景 {#background}

`OID` Oakインデックスの定義に関連する問題を特定します。標準のOakインデックス定義に対して行われた変更を識別します。 また、AEMと互換性のないカスタムOakインデックス定義もCloud Serviceとして識別します。 各`OID`検索のメッセージは、インデックスを識別し、追加情報を提供します。

サブタイプは、異なる種類の情報を識別するために使用されます。

* `custom.index.violation`:カスタムOakインデックスは、Cloud ServiceーとしてAEMと互換性がありません。
* `standard.index.modification`:標準のOakインデックスに対する変更。

## 可能性のある影響およびリスク {#implications-and-risks}

* 標準Oakインデックス定義に対する変更は、AEMのアップグレード中に失われる場合があります。
* Oakの定義は不変で、お客様のプロジェクトコードでパッケージ化し、Cloud Managerを使用して展開する必要があります。
* すべてのOakインデックスの定義は、命名規則およびAEMのOakインデックスの他の規則に従ってCloud Serviceを定義する必要があります。 好ましくない行動を引き起こさないもの。

## 可能な解決策 {#solutions}

* メッセージで識別されるインデックス規則違反を解決します。
* 新しいまたはカスタムのOakインデックス定義を展開するには、Cloud Service[パッケージ化のガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)に従ってAEMに従います。
* AEM標準インデックスのカスタマイズと新しいカスタムOakインデックス定義は、AEMの[コンテンツインデックス作成のガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#preparing-the-new-index-definition)に従ってCloud Serviceを行う必要があります。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)プロジェクトを見直し、[OID違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)をCloud Serviceとして修正し、AEMと互換性を持たせる方法を理解します。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
* [Index Converter](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools)を活用して、既存のCustom Oak Index Definitionsを、Cloud Service互換のカスタムOak Index DefinitionsとしてAEMに移行します。
