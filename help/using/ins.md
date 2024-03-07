---
title: INS
description: パターン検出コードのヘルプページ
source-git-commit: e469b546a75a77e538a54de3ffc1ca385c8cf21d
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 48%

---

# INS {#ins}

無効な名前空間

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_overview"
>title="無効な名前空間"
>abstract="INS は、AEMインスタンスの名前空間の問題を識別します"

`INS`  無効な名前空間は、AEMインスタンスで名前空間の問題を識別します。

次のようなサブタイプを使用して、各種情報を識別します。

* `uri`:AEMで無効な名前空間 URI を識別します。

## 可能性のある影響およびリスク {#implications-and-risks}

* コンテンツを（階層全体で）レプリケートしたり、コンテンツを（環境全体で）コピーしたりできない（経由で） `/crx/packMgr` またはコンテンツコピー )。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_guidance"
>title="実装ガイダンス"
>abstract="カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 以下に従って名前空間の定義を修正 [JCR 仕様](https://developer.adobe.com/experience-manager/reference-materials/spec/jcr/1.0/4.5_Namespaces.html). 前述の手順に従います [ここ](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/how-can-i-delete-a-namespace-created-in-crx/td-p/225163)
* 不明な点や対処すべき懸念がある場合は、アドビの [Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。