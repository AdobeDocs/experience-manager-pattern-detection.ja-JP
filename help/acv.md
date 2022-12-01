---
title: ACV
description: パターン検出コードのヘルプページ
exl-id: 1dd1af45-aa56-48da-8582-c4330cded489
source-git-commit: e7096efc1d9da7f5aad5a5b353ba622c879cc4a5
workflow-type: ht
source-wordcount: '348'
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

`ACV` Assets のコンテンツバリデーターが、アセットコンテンツ内の欠落している必須ノードと違反を識別します。これにより、Experience Manager as a Cloud Service で特定の Assets 機能でエラーが発生する可能性があります。

次のようなサブタイプを使用して、各種情報を識別します。

* `missing.jcrcontent`：リポジトリ内の必須ノードが欠落しているフォルダーを識別します。リポジトリ内の欠落しているコンテンツを識別することで、機能やユースケースの破損を防ぐことができます。
* `missing.original.rendition`：リポジトリで、必須のオリジナルレンディションが欠落しているアセットを識別します。PDF のページをプレビューする場合、AEMaaCS でサブアセットを生成する必要はありません。したがって、PDF アセットの場合、元のレンディションが見つからないサブアセットのレポートはまったく表示されません。
* `metadata.descendants.violation`：リポジトリ内のアセットの metadata ノードの下に 100 を超える子孫を持つアセットを識別します。

## 考えられる影響およびリスク {#implications-and-risks}

* これにより、Experience Manager as a Cloud Service の継承されたプロパティに依存している特定の Assets 機能でエラーが発生する可能性があります。
* AEM Assets は、オリジナルレンディションの存在に依存しています。元のレンディションがない場合、Cloud Service で処理するアセットはループします。サブアセットの生成は、AEMaaCS ではサポートされていません。
* metadata ノードの下の子孫の数が多いと、これに違反するアセットで構成されるフォルダーの読み込みに時間がかかる場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="実装ガイダンス"
>abstract="Adobe では、継承されたプロパティに依存するワークフローが壊れないように、コンテンツ構造を確認することをお勧めします。カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* フォルダーに欠落している子ノードがないか分析します。フォルダー数が管理可能な場合はノードを手動で作成し、それ以外の場合はスクリプトを使用します。
* オリジナルレンディションが欠落しているアセットの場合は、移行前にアセットを再アップロードするか削除します。
* サブアセットの元のレンディションが見つからない場合、アクションは必要ありません。
* 不明な点や対処すべき懸念がある場合は、アドビの [Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
