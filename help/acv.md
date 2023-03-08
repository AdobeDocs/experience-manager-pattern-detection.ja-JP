---
title: ACV
description: パターン検出コードのヘルプページ
exl-id: 1dd1af45-aa56-48da-8582-c4330cded489
source-git-commit: bbeb7193e198a32a9bc966e1821b1058dbbc8c02
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 81%

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
* `conflict.node`：/content/dam/ パスの下のリポジトリで競合ノードの存在を識別します。
* `psb.file.large`:大きな PSB ファイルの識別 (dc:format :application/vnd.3gpp.pic-bw-small) で、サイズが 2GB を超える場合。

## 考えられる影響およびリスク {#implications-and-risks}

* これにより、Experience Manager as a Cloud Service の継承されたプロパティに依存している特定の Assets 機能でエラーが発生する可能性があります。
* AEM Assets は、オリジナルレンディションの存在に依存しています。元のレンディションがない場合、Cloud Service で処理するアセットはループします。サブアセットの生成は、AEMaaCS ではサポートされていません。
* metadata ノードの下の子孫の数が多いと、これに違反するアセットで構成されるフォルダーの読み込みに時間がかかる場合があります。
* 競合ノードが存在すると、AEM as a Cloud Service で取り込みエラーが発生する可能性があります。
* Experience Managerは、非常に高解像度の PSB ファイルを処理できない場合があります。 大きなファイルの処理に ImageMagick を使用している場合、Image Server の適切なベンチマークがおこなわれていないと、Experience Managerのパフォーマンスに影響を与える可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="実装ガイダンス"
>abstract="Adobe では、継承されたプロパティに依存するワークフローが壊れないように、コンテンツ構造を確認することをお勧めします。カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* フォルダーに欠落している子ノードがないか分析します。フォルダー数が管理可能な場合はノードを手動で作成し、それ以外の場合はスクリプトを使用します。
* オリジナルレンディションが欠落しているアセットの場合は、移行前にアセットを再アップロードするか削除します。
* サブアセットの元のレンディションが見つからない場合、アクションは必要ありません。
* 競合ノードが存在する場合は、解決するか、AEM as a Cloud Service に移行する前に削除する必要があります。
* 大きなファイルや PSB ファイルを大量に処理する予定がある場合は、Adobeカスタマーサポートにお問い合わせください。 Experience Managerは、30000 x 23000ピクセルを超える高解像度の PSB ファイルを処理できない場合があります。 詳しくは、 [ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-64/assets/extending/best-practices-for-imagemagick.html).
* 不明な点や対処すべき懸念がある場合は、アドビの [Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
