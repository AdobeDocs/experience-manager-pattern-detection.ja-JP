---
title: LUI
description: パターン検出コードのヘルプページ
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 1c2d064c239ad6f5599678d8057fe2a6b7fd8d01
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 98%

---

# LUI {#lui}

レガシーユーザーインターフェイス

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="レガシーユーザーインターフェイス"
>abstract="LUI は、非推奨（廃止予定）のユーザーインターフェイス要素を識別します。これらの要素は、AEM の後続バージョンや AEM as a Cloud Service ではサポートされなくなるため推奨されません。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja" text="主要な変更点 - AEM as a Cloud Service"

`LUI` は、非推奨（廃止予定）のユーザーインターフェイス要素を識別します。これらの要素は、AEM の後続バージョンや AEM as a Cloud Service ではサポートされなくなるため推奨されません。

サブタイプを使用して、アップグレードの必要な各種のユーザーインターフェイス要素を識別します。

* `legacy.dialog.classic`：ExtJS に基づくクラシック UI のダイアログは Coral に変更する必要があります。
   * この状況は、ダイアログ名が「dialog」または「design_dialog」の場合、および `jcr:primaryType` プロパティ値または `xtype` プロパティ値が「cq:Dialog」の場合に検出されます。
* `legacy.dialog.coral2`：Coral 2 のダイアログは Coral 3 を使用するように更新する必要があります。
   * この状況は、ダイアログと子コンテンツノードの名前が「cq:dialog/content」、「cq:design_dialog/content」、「cq:dialog.coral2/content」、
または「cq:design_dialog.coral2/content」の場合、および `sling:resourceType` プロパティ値に「granite/ui/components/coral/foundation」が含まれる場合に検出されます。
* `legacy.custom.component`：`foundation/components` から継承されるコンポーネントは、コアコンポーネントを使用するように更新する必要があります。
   * この状況は、`jcr:primaryType` プロパティ値が「cq:Component」で、
      `sling:resourceSuperType` プロパティ値に「foundation/components」が含まれる場合、
      またはスーパータイプコンポーネントチェーンのいずれかの `sling:resourceSuperType` プロパティ値に「foundation/components」が含まれている場合に検出されます。
* `legacy.static.template`：静的テンプレートは、編集可能なテンプレートにアップグレードする必要があります。
   * この状況は、`jcr:primaryType` プロパティ値が「cq:Template」の場合に検出されます。
* `content.fragment.template`：コンテンツフラグメントテンプレートでは、フラグメントテンプレートを置き換えるために、フラグメントモデルを作成する必要があります。
   * コンテンツフラグメントテンプレートは、次の場所にあります。
      * 標準搭載のコンテンツフラグメントテンプレートは、`/libs/settings/dam/cfm/templates` に格納されています。
      * それらは、`/apps/settings/dam/cfm/templates` または `/conf/.../settings/dam/cfm/templates`（... = global または &quot;tenant&quot;）でオーバーレイできます。

## 可能性のある影響およびリスク {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="実装ガイダンス"
>abstract="AEM as a Cloud Service ではクラシック UI が使用できなくなりました。オーサリングの標準インターフェイスはタッチ操作対応 UI です。ベストプラクティスとしては、サポートされていないインターフェイスをすべて移動し、AEM as a Cloud Service と互換性のある新しい機能に合わせて、リンクされたカスタマイズをリファクタリングすることをお勧めします。既存の AEM Modernization Tools スイートを利用すると、AEM Sites 実装の最新化に伴う労力を削減できます。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM Modernization Tools"

* AEM as a Cloud Service ではクラシック UI が使用できなくなりました。オーサリングの標準インターフェイスは、タッチ対応 UI です。
* 従来のカスタムコンポーネントへの依存を続けると、時間の経過とともにメンテナンスコストが増大する可能性があります。
* コンテンツフラグメントテンプレートは、AEM 6.3 ではコンテンツフラグメントモデルに置き換えられました。従来のテンプレートに基づくコンテンツフラグメントを AEM as a Cloud Service に移行すると、これらのフラグメントは引き続き機能しますが、従来のテンプレートに基づいて新しいフラグメントを作成することはできません。また、AEM GraphQL を使用してこれらのフラグメントを配信することもできません。この場合は、スキーマとしてコンテンツフラグメントモデルが必要になります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="ツールとリソース"
>abstract="AEM Modernization Tools スイートを使用すると、クラシック（ExtJS）ダイアログを Coral ダイアログに変換できます。サポートされていない機能や従来の機能から堅牢な最新の AEM ソリューションに移行する際の支援を目的としたツールです。これらのツールは、設定に応じた、拡張可能な設定が可能です。 また、カスタムコンポーネントの代わりに標準化されたコアコンポーネントのセットを使用して、開発時間を短縮しアプリケーションのメンテナンスコストを削減することも検討します。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/component/about.html" text="コンポーネントコンバーター"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="コアコンポーネント"

* [AEM Modernization Tools スイート](https://opensource.adobe.com/aem-modernize-tools/)を利用すると、AEM Sites の最新化に伴う労力を軽減することができます。これらのツールは、次の変換に対応します。
   * クラシック（ExtJS）ダイアログから Coral ダイアログへ
   * 基盤コンポーネントからコアコンポーネントへ
   * 静的テンプレートおよび列コントロールから編集可能テンプレートおよびレスポンシブグリッドへ
   * デザインおよびデザインダイアログから編集可能テンプレートポリシーへ
* プロジェクトのカスタムコンポーネントライブラリを見直し、可能であれば、標準化された[コアコンポーネント](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=ja)への移行を検討することにより、アプリケーションの開発時間を短縮し、メンテナンスコストを削減することができます。
* 従来のテンプレートと同等の機能を持つコンテンツフラグメントモデルを作成し、それらのモデルを使用してコンテンツフラグメントの作成を進めることをお勧めします。詳しくは、[コンテンツフラグメントモデル](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=ja)を参照してください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
