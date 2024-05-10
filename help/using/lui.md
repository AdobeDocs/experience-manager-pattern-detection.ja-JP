---
title: LUI
description: パターン検出コードのヘルプページ。
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '703'
ht-degree: 100%

---

# LUI {#lui}

レガシーユーザーインターフェイス

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="レガシーユーザーインターフェイス"
>abstract="LUI は、AEM の後続バージョンや AEM as a Cloud Service では推奨またはサポートされていない、非推奨（廃止予定）のユーザーインターフェイス要素の使用を識別します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="主な変更点 - AEM as a Cloud Service"

`LUI` は、AEM の後続バージョンや AEM as a Cloud Service では推奨またはサポートされていない、非推奨（廃止予定）のユーザーインターフェイス要素の使用を識別します。

サブタイプを使用して、アップグレードが必要な、各種のユーザーインターフェイス要素を識別します。

* `legacy.dialog.classic`：ExtJS に基づくクラシック UI のダイアログは Coral に変更する必要があります。
   * この状況は、ダイアログ名が「dialog」または「design_dialog」の場合や、
`jcr:primaryType` プロパティ値または `xtype` プロパティ値が `cq:Dialog` の場合に検出されます。
* `legacy.dialog.coral2`：`Coral 3` を使用するには、`Coral 2` ダイアログボックスを更新する必要があります。
   * この状況は、ダイアログ ボックスとその子コンテンツノード名が `cq:dialog/content`、
     `cq:design_dialog/content`、`cq:dialog.coral2/content`&quot; または `cq:design_dialog.coral2/content` で、
`sling:resourceType` プロパティ値に
「granite/ui/components/coral/foundation」が含まれていない場合に検出されます。
* `legacy.custom.component`：`foundation/components` から継承されるコンポーネントは、コアコンポーネントを使用するようにアップデートする必要があります。
   * この状況は、`jcr:primaryType` プロパティ値が「`cq:Component`」で、
     `sling:resourceSuperType` プロパティ値に「foundation/components」が含まれている場合に検出されます。または、
     またはスーパータイプコンポーネントチェーンのいずれかの `sling:resourceSuperType` プロパティ値に「foundation/components」が含まれている場合に検出されます。

* `legacy.static.template`：静的テンプレートは、編集可能なテンプレートにアップグレードする必要があります。
   * この状況は、`jcr:primaryType` プロパティ値が「`cq:Template`」の場合に検出されます。
* `content.fragment.template`：コンテンツフラグメントテンプレートでは、フラグメントテンプレートを置き換えるために、フラグメントモデルを作成する必要があります。
   * コンテンツフラグメントテンプレートは、次の場所にあります。
      * 標準搭載のコンテンツフラグメントテンプレートは、`/libs/settings/dam/cfm/templates` に格納されています。
      * それらは、`/apps/settings/dam/cfm/templates` または `/conf/.../settings/dam/cfm/templates`（... = global または &quot;tenant&quot;）でオーバーレイできます。
* `translation.dictionary`：/apps の下にある `I18n` 辞書。
   * /apps は実行時に不変で、translator.html は AEM as a Cloud Service では使用できなくなりました。

## 考えられる影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="実装ガイダンス"
>abstract="AEM as a Cloud Service ではクラシック UI が使用できなくなりました。オーサリングの標準インターフェイスはタッチ操作対応 UI です。ベストプラクティスとしては、サポートされていないインターフェイスをすべて移動し、AEM as a Cloud Service と互換性のある新しい機能に合わせて、リンクされたカスタマイズをリファクタリングすることをお勧めします。顧客は、既存の AEM Modernization Suite を使用すると、AEM Sites 実装の最新化に必要な労力を軽減できます。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM Modernization Tools"

* AEM as a Cloud Service ではクラシック UI が使用できなくなりました。オーサリングの標準インターフェイスは、タッチ対応 UI です。
* 従来のカスタムコンポーネントへの依存を続けると、時間の経過とともにメンテナンスコストが増大する可能性があります。
* コンテンツフラグメントテンプレートは、AEM 6.3 ではコンテンツフラグメントモデルに置き換えられました。従来のテンプレートに基づくコンテンツフラグメントを AEM as a Cloud Service に移行すると、これらのフラグメントは引き続き機能しますが、従来のテンプレートに基づいてフラグメントを作成することはできません。また、コンテンツフラグメントモデルをスキーマとして必要とする AEM GraphQL を使用してこれらのフラグメントを配信することもできません。
* /apps は実行時に不変で、translator.html は AEM as a Cloud Service では使用できなくなりました。そのため、`I18n` 辞書は CI/CD パイプラインを通じて Git から取得する必要があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="ツールとリソース"
>abstract="AEM Modernization Tools スイートを使用すると、クラシック（ExtJS）ダイアログを Coral ダイアログに変換できます。サポートされていない機能や従来の機能から堅牢な最新の AEM ソリューションに移行する際の支援を目的としたツールです。これらのツールは設定可能で、設定を認識し、拡張可能です。また、カスタムコンポーネントの代わりに標準化されたコアコンポーネントのセットを使用して、開発時間を短縮しアプリケーションのメンテナンスコストを削減することも検討します。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/component/about.html" text="コンポーネントコンバーター"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-core-components/using/introduction" text="コアコンポーネント"

* AEM Sites の実装を最新化するために必要な労力を軽減するには、[AEM Modernization Tools スイート](https://opensource.adobe.com/aem-modernize-tools/)を使用します。これらのツールは、次の変換に対応します。
   * クラシック（ExtJS）ダイアログから Coral ダイアログへ
   * 基盤コンポーネントからコアコンポーネントへ
   * 静的テンプレートおよび列コントロールから編集可能テンプレートおよびレスポンシブグリッドへ
   * デザインおよびデザインダイアログから編集可能テンプレートポリシーへ
* プロジェクトのカスタムコンポーネントライブラリを見直し、可能であれば、標準化された[コアコンポーネント](https://experienceleague.adobe.com/ja/docs/experience-manager-core-components/using/introduction)への移行を検討することにより、アプリケーションの開発時間を短縮し、メンテナンスコストを削減することができます。
* 従来のテンプレートと同等の機能を持つコンテンツフラグメントモデルを作成し、将来のコンテンツフラグメントの作成にこれらのモデルを使用します。詳しくは、[コンテンツフラグメントモデル](https://experienceleague.adobe.com//docs/experience-manager-65/content/assets/content-fragments/content-fragments-models)を参照してください。
* `I18n` 辞書は、CI/CD パイプラインを通じて Git から取得する必要があります。[ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#apps-libs-immutable)
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
