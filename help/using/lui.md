---
title: LUI
description: パターン検出コードのヘルプページ。
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 49%

---

# LUI {#lui}

レガシーユーザーインターフェイス

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="レガシーユーザーインターフェイス"
>abstract="LUI は、非推奨（廃止予定）のユーザーインターフェイス要素の使用を特定します。 これらの要素は、AEMの後続バージョンやAEM as a Cloud Serviceではサポートされなくなるため推奨されません。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="主な変更点 - AEM as a Cloud Service"

`LUI`  非推奨（廃止予定）のユーザーインターフェイス要素の使用を識別します。 これらの要素は、AEMの後続バージョンやAEMas a Cloud Service環境ではサポートされなくなるため、お勧めしません。

サブタイプを使用して、アップグレードが必要な、各種のユーザーインターフェイス要素を識別します。

* `legacy.dialog.classic`:ExtJS に基づくクラシック UI ダイアログボックスは Coral に変更する必要があります。
   * このサブタイプは、ダイアログボックス名がの場合に検出されます `dialog` または `design_dialog` また、 `jcr:primaryType` プロパティの値または `xtype` プロパティの値： `cq:Dialog`.
* `legacy.dialog.coral2`：`Coral 3` を使用するには、`Coral 2` ダイアログボックスを更新する必要があります。
   * このサブタイプは、ダイアログボックスとその子コンテンツノードの名前が
      * `cq:dialog/content`、
      * `cq:design_dialog/content`、
      * `cq:dialog.coral2/content`、
      * または `cq:design_dialog.coral2/content`
および `sling:resourceType` プロパティの値にが含まれていません `granite/ui/components/coral/foundation`.
* `legacy.custom.component`：`foundation/components` から継承されるコンポーネントは、コアコンポーネントを使用するようにアップデートする必要があります。
   * このサブタイプは、 `jcr:primaryType` プロパティの値： `cq:Component` および
     `sling:resourceSuperType` プロパティ値に「基盤/ コンポーネント」が含まれています。 または、
     `sling:resourceSuperType` スーパータイプコンポーネントのチェーンのプロパティ値には、「foundation / components」が含まれます。
* `legacy.static.template`：静的テンプレートは、編集可能なテンプレートにアップグレードする必要があります。
   * このサブタイプは、 `jcr:primaryType` プロパティの値： `cq:Template`.
* `content.fragment.template`：コンテンツフラグメントテンプレートでは、フラグメントテンプレートを置き換えるために、フラグメントモデルを作成する必要があります。
   * コンテンツフラグメントテンプレートは、次の場所にあります。
      * 標準搭載のコンテンツフラグメントテンプレートは、`/libs/settings/dam/cfm/templates` に格納されています。
      * それらは、`/apps/settings/dam/cfm/templates` または `/conf/.../settings/dam/cfm/templates`（... = global または &quot;tenant&quot;）でオーバーレイできます。
* `translation.dictionary`: `I18n` の下にある辞書 `/apps`.
   * `/apps` は実行時に不変で、translator.html はAEM as a cloud service では使用できなくなりました。

## 考えられる影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="実装ガイダンス"
>abstract="AEM as a Cloud Service ではクラシック UI が使用できなくなりました。オーサリングの標準インターフェイスはタッチ操作対応 UI です。ベストプラクティスは、サポートされていないインターフェイスをすべて移動し、AEMas a Cloud Serviceと互換性のある新しい機能に合わせて、リンクされたカスタマイズをリファクタリングすることです。 顧客は、既存の AEM Modernization Suite を使用すると、AEM Sites 実装の最新化に必要な労力を軽減できます。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM Modernization Tools"

* AEM as a Cloud Service ではクラシック UI が使用できなくなりました。オーサリングの標準インターフェイスは、タッチ対応 UI です。
* 従来のカスタムコンポーネントへの依存を続けると、時間の経過とともにメンテナンスコストが増大する可能性があります。
* AEM 6.3 では、コンテンツフラグメントテンプレートがコンテンツフラグメントモデルに置き換わりました。従来のテンプレートに基づくコンテンツフラグメントをAEMas a Cloud Serviceバージョンに移行しても、これらのフラグメントは機能として保持されますが、従来のテンプレートに基づくフラグメントは作成できません。 また、AEM GraphQLを使用してこれらのフラグメントを配信することもできません。この場合は、スキーマとしてコンテンツフラグメントモデルが必要になります。
* /apps は実行時に不変で、translator.html は AEM as a Cloud Service では使用できなくなりました。したがって、 `I18n` 辞書は、CI/CD パイプラインを介して Git から取得する必要があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="ツールとリソース"
>abstract="AEM Modernization Tools スイートを使用すると、クラシック（ExtJS）ダイアログを Coral ダイアログに変換できます。サポートされていない機能や従来の機能から堅牢な最新の AEM ソリューションに移行する際の支援を目的としたツールです。これらのツールは設定可能で、設定を認識し、拡張可能です。また、カスタムコンポーネントの代わりに標準化されたコアコンポーネントのセットを使用して、開発時間を短縮しアプリケーションのメンテナンスコストを削減することも検討します。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/component/about.html" text="コンポーネントコンバーター"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-core-components/using/introduction" text="コアコンポーネント"

* AEM Sitesの実装を最新化するために必要な労力を減らすには、を使用します。 [AEM Modernization Tools スイート](https://opensource.adobe.com/aem-modernize-tools/). これらのツールは、次の変換に対応します。
   * クラシック（ExtJS）ダイアログから Coral ダイアログへ
   * 基盤コンポーネントからコアコンポーネントへ
   * 静的テンプレートと列コントロールから、編集可能テンプレートとレスポンシブグリッドへ
   * 編集可能なテンプレートポリシーのデザインおよびデザインダイアログ
* プロジェクトのカスタムコンポーネントライブラリを見直し、可能であれば、標準化された[コアコンポーネント](https://experienceleague.adobe.com/ja/docs/experience-manager-core-components/using/introduction)への移行を検討することにより、アプリケーションの開発時間を短縮し、メンテナンスコストを削減することができます。
* 従来のテンプレートと同等の機能を持つコンテンツフラグメントモデルを作成し、今後それらのモデルを使用してコンテンツフラグメントを作成する予定です。 詳しくは、[コンテンツフラグメントモデル](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/assets/content-fragments/content-fragments-models)を参照してください。
* `I18n` 辞書は、CI/CD パイプラインを通じて Git から取得する必要があります。 [ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#apps-libs-immutable)
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
