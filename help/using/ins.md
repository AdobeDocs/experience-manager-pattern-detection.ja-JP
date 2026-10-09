---
title: INS
description: パターン検出コードのヘルプページ。
exl-id: d89e1589-3195-4b2d-98f4-136bedaecb0b
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: baa8f6dbf24b735348ed6b27f1e885b5078859ce
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 100%
---
# INS {#ins}

無効な名前空間

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_overview"
>title="無効な名前空間"
>abstract="INS が AEM インスタンスの名前空間の問題を特定"

`INS`（無効な名前空間）は、AEM インスタンスの名前空間の問題を識別します。

サブタイプは、次のような各種情報を識別するために使用されます。

* `uri`：AEM で無効な名前空間 URI を特定します。

## 考えられる影響およびリスク {#implications-and-risks}

* コンテンツを（階層全体）レプリケートしたり、コンテンツを（`env` 全体 - `/crx/packMgr` またはコンテンツコピーを介して）コピーしたりできません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_guidance"
>title="実装ガイダンス"
>abstract="カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* [JCR 仕様](https://developer.adobe.com/experience-manager/reference-materials/spec/jcr/1.0/4.5_Namespaces.html)に従って、名前空間の定義を修正します。 [こちら](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/how-can-i-delete-a-namespace-created-in-crx/td-p/225163)に記載されている手順に従ってください。
* 詳しい説明や懸念事項の対応については、[Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
