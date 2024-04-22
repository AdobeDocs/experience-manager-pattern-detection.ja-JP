---
title: PCX
description: パターン検出コードのヘルプページ
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a0
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 58%

---

# PCX {#pcx}

ページの複雑さ

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_overview"
>title="ページの複雑さ"
>abstract="PCX は、構造中に多数のノードを含むページを識別します。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="主要な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - リリースノート"

PCX は、構造内に多数のノードを含むページを識別します。

サブタイプを使用して、各種情報を識別します。

* `page.complexity.medium`：ページに、レンダリングパフォーマンスに影響する可能性のある比較的多くのノードが含まれています。
* `page.complexity.high`：ページには、レンダリングのパフォーマンスに影響を与える可能性が高いノードが多数含まれています。

## 可能性のある影響およびリスク {#implications-and-risks}

* ページ内の多くのノードが、レンダリングパフォーマンスに影響を与える可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、コンテンツ構造を確認して、ページの複雑さを軽減することです。これにより、ページレンダリングのパフォーマンスが向上します。 ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 次のアクションを実行して、ページ内のノードの合計数を減らします。
   * 不要なコンテナがないことを確認します。
   * コンテナを減らしてもレイアウトが同じになるかどうかをテストします。
   * ページのコンテンツを簡素化します。
   * ノード構造の深さを減らします。
   * 簡素化のために、内部のエクスペリエンスフラグメントをリファクタリングします。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
