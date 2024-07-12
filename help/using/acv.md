---
title: ACV
description: パターン検出コードのヘルプページ。
exl-id: 1dd1af45-aa56-48da-8582-c4330cded489
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---

# ACV {#acv}

Assets コンテンツバリデーター

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="Assets コンテンツバリデーター"
>abstract="ACV は、アセットコンテンツ内の欠落している必須ノードを識別します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/overview" text="主な変更点 - Experience Manager as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="Experience Manager as a Cloud Service - リリースノート"

`ACV`（Assets のコンテンツバリデーター）は、アセットコンテンツ内の欠落している必須ノードと違反を識別します。これにより、Experience Manager as a Cloud Service の特定の Assets 機能でエラーが発生する可能性があります。

次のようなサブタイプを使用して、各種情報を識別します。

* `missing.jcrcontent`：リポジトリ内の必須ノードが欠落しているフォルダーを識別します。リポジトリ内の欠落しているコンテンツを識別することで、機能やユースケースの破損を防ぐことができます。
* `missing.original.rendition`：リポジトリで、必須のオリジナルレンディションが欠落しているアセットを識別します。PDF のページをプレビューする場合、AEMaaCS でサブアセットを生成する必要はありません。したがって、PDF アセットの場合、オリジナルのレンディションが見つからないサブアセットのレポートは抑制されます。
* `metadata.descendants.violation`：リポジトリ内のアセットの metadata ノードの下に 100 を超える子孫を持つアセットを識別します。
* `conflict.node`：/content/dam/ パスの下のリポジトリで競合ノードの存在を識別します。
* `psb.file.large`：サイズが 2 GB を超える大きな PSB ファイル（`dc:format : application/vnd.3gpp.pic-bw-small`）を識別します。
* `invalid.asset.name`：名前に無効な文字 [`* / : [ \ ] | # % { } ? &`] が含まれるアセットを識別します。

## 考えられる影響とリスク {#implications-and-risks}

* Experience Manager as a Cloud Service の継承されたプロパティに依存している、特定の Assets 機能でエラーが発生する可能性があります。
* AEM Assets は、オリジナルのレンディションの存在に依存しています。元のレンディションがない場合、Cloud Service で処理するアセットはループします。サブアセットの生成は、AEMaaCS ではサポートされていません。
* メタデータノードの下に多数の子孫があると、違反しているアセットを含むフォルダーのダウンロードが遅くなる場合があります。
* 競合ノードが存在すると、AEM as a Cloud Service で取り込みエラーが発生する可能性があります。
* Experience Manager では、高い解像度の PSB ファイルを処理できない場合があります。大きなファイルの処理に ImageMagick を使用する場合は、Experience Manager サーバーの適切なベンチマークが行われていなければ、パフォーマンスに影響する可能性があります。
* アセット名に無効な文字が含まれていると、AEM as a Cloud Service への移行中にエラーが発生する可能性があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="実装ガイダンス"
>abstract="継承されたプロパティに依存するワークフローが壊れるのを避けるために、コンテンツ構造をレビューすることをお勧めします。カスタマーケアにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* フォルダーに欠落している子ノードがないか分析します。フォルダー数が管理可能な場合はノードを手動で作成し、それ以外の場合はスクリプトを使用します。
* オリジナルレンディションが欠落しているアセットの場合は、移行前にアセットを再アップロードするか削除します。
* サブアセットのオリジナルのレンディションが見つからない場合、アクションは必要ありません。
* 競合ノードが存在する場合は、AEM as a Cloud Service に移行する前に解決または削除する必要があります。
* 大きな PSD ファイルまたは PSB ファイルを大量に処理する予定がある場合は、アドビカスタマーサポートにお問い合わせください。Experience Manager では、30000 x 23000 ピクセルを超える高い解像度の PSB ファイルを処理できない場合があります。[ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/assets/extending/best-practices-for-imagemagick)を参照してください。
* 詳しい説明や懸念事項の対応については、[Experience Manager カスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
