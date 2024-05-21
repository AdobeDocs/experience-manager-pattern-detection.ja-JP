---
title: INS
description: パターン検出コードのヘルプページ。
exl-id: d89e1589-3195-4b2d-98f4-136bedaecb0b
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 87%

---

# INS {#ins}

無効な名前空間

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_overview"
>title="無効な名前空間"
>abstract="INS が AEM インスタンスの名前空間の問題を特定"

`INS`（無効な名前空間）は、AEM インスタンスの名前空間の問題を識別します。

次のようなサブタイプを使用して、各種情報を識別します。

* `uri`：AEM で無効な名前空間 URI を特定します。

## 考えられる影響およびリスク {#implications-and-risks}

* コンテンツを（階層全体）レプリケートしたり、コンテンツを（`env` 全体 - `/crx/packMgr` またはコンテンツコピーを介して）コピーしたりできません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_guidance"
>title="実装ガイダンス"
>abstract="カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* に従って名前空間定義を修正します。 [JCR 仕様](https://developer.adobe.com/experience-manager/reference-materials/spec/jcr/1.0/4.5_Namespaces.html). 前述の手順に従います [こちら](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/how-can-i-delete-a-namespace-created-in-crx/td-p/225163)
* 詳しい説明や懸念事項の対応については、[Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
