---
title: ACV
description: パターン検出コードのヘルプページ
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a5
source-git-commit: d61fbb28fdf91fd9b356654d5cd2d50b156398c4
workflow-type: ht
source-wordcount: '219'
ht-degree: 100%

---

# ACV {#acv}

Assets コンテンツバリデーター

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="Assets コンテンツバリデーター"
>abstract="ACV は、アセットコンテンツ内の欠落している必須ノードを識別します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html?lang=ja" text="主な変更点 - Experience Manager as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja" text="Experience Manager as a Cloud Service - リリースノート"

`ACV` Assets のコンテンツバリデーターが、アセットコンテンツ内の欠落している必須ノードを識別します。これにより、Experience Manager as a Cloud Service で特定の Assets 機能でエラーが発生する可能性があります。

次のようなサブタイプを使用して、各種情報を識別します。

* `assets.sanity.missing.jcrcontent`：リポジトリー内の必須ノードが欠落しているフォルダーを識別します。リポジトリー内の欠落しているコンテンツを識別することで、機能やユースケースの破損を防ぐことができます。

## 可能性のある影響およびリスク {#implications-and-risks}

これにより、Experience Manager as a Cloud Service の継承されたプロパティに依存している特定の Assets 機能でエラーが発生する可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="実装ガイダンス"
>abstract="Adobe では、継承されたプロパティに依存するワークフローが壊れないように、コンテンツ構造を確認することをお勧めします。カスタマーケアにお問い合わせください。&quot;
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* フォルダーに欠落している子ノードがないか分析します。フォルダー数が管理可能な場合はノードを手動で作成し、それ以外の場合はスクリプトを使用します。
* 不明な点や懸念を解決するため、アドビの [Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
