---
title: LUI
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: ht
source-wordcount: '347'
ht-degree: 100%

---


# LUI {#lui}

レガシーユーザーインターフェイス

## 背景 {#background}

`LUI` は、非推奨（廃止予定）のユーザーインターフェイス要素を識別します。これらの要素は、AEM の後続バージョンや AEM as a Cloud Service ではサポートされなくなるため推奨されません。

サブタイプを使用して、アップグレードの必要な各種のユーザーインターフェイス要素を識別します。

* `legacy.dialog.classic`：ExtJS に基づくクラシック UI ダイアログは、Coral UI に変更する必要があります。
   * この状況は、ダイアログ名が「dialog」または「design_dialog」の場合、および `jcr:primaryType` プロパティ値または `xtype` プロパティ値が「cq:Dialog」の場合に検出されます。
* `legacy.dialog.coral2`：Coral 2 のダイアログは、Coral 3 を使用するように更新する必要があります。
   * この状況は、ダイアログと子コンテンツノードの名前が「cq:dialog/content」、「cq:design_dialog/content」、「cq:dialog.coral2/content」、
または「cq:design_dialog.coral2/content」の場合、および `sling:resourceType` プロパティ値に「granite/ui/components/coral/foundation」が含まれる場合に検出されます。
* `legacy.custom.component`：`foundation/components` から継承されるコンポーネントは、コアコンポーネントを使用するように更新する必要があります。
   * この状況は、`jcr:primaryType` プロパティ値が「cq:Component」で、
      `sling:resourceSuperType` プロパティ値に「foundation/components」が含まれる場合、
      またはスーパータイプコンポーネントチェーンのいずれかの `sling:resourceSuperType` プロパティ値に「foundation/components」が含まれている場合に検出されます。
* `legacy.static.template`：静的テンプレートは、編集可能なテンプレートにアップグレードする必要があります。
   * この状況は、`jcr:primaryType` プロパティ値が「cq:Template」の場合に検出されます。

## 可能性のある影響およびリスク {#implications-and-risks}

* AEM as a Cloud Service ではクラシック UI が使用できなくなりました。オーサリングの標準インターフェイスは、タッチ対応 UI です。
* 従来のカスタムコンポーネントへの依存を続けると、時間の経過とともにメンテナンスコストが増大する可能性があります。

## 可能な解決策 {#solutions}

* [AEM Modernization Tools スイート](https://opensource.adobe.com/aem-modernize-tools/)を利用すると、AEM Sites の最新化に伴う労力を軽減することができます。これらのツールは、次の変換に対応します。
   * クラシック（ExtJS）ダイアログから Coral ダイアログへ
   * 基盤コンポーネントからコアコンポーネントへ
   * 静的テンプレートおよび列コントロールから編集可能テンプレートおよびレスポンシブグリッドへ
   * デザインおよびデザインダイアログから編集可能テンプレートポリシーへ
* プロジェクトのカスタムコンポーネントライブラリを見直し、可能であれば、標準化された[コアコンポーネント](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=ja)への移行を検討することにより、アプリケーションの開発時間を短縮し、メンテナンスコストを削減することができます。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
