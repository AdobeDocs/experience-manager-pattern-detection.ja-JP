---
title: ルイ
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 6%

---


# LUI {#lui}

レガシーユーザーインターフェイス

## 背景 {#background}

`LUI` AEMの新しいバージョンおよびAEMでCloud Serviceとして推奨されない、またはサポートされない非推奨のユーザーインターフェイス要素の使用を示します。

サブタイプは、アップグレードが必要または必要な様々なタイプのユーザーインターフェイス要素を識別するために使用されます。

* `legacy.dialog.classic`:ExtJSに基づくクラシックUIダイアログは、Coralに変更する必要があります。
   * これは、ダイアログ名が「dialog」または「design_dialog」の場合、および
`jcr:primaryType`プロパティ値または`xtype`プロパティ値は「cq:Dialog」です。
* `legacy.dialog.coral2`:Coral 2の対話は、Coral 3を使用するように更新する必要があります。
   * これは、ダイアログとその子コンテンツノード名が「cq:dialog/content」の場合に検出されます。
&quot;cq:design_dialog/content&quot;、&quot;cq:dialog.coral2/content&quot;、&quot;cq:design_dialog.coral2/content&quot;
`sling:resourceType`プロパティ値に
&quot;granite/ui/components/coral/foundation&quot;
* `legacy.custom.component`:から継承するコンポーネント `foundation/components`は、コアコンポーネントを使用するように更新する必要があります。
   * これは、`jcr:primaryType`プロパティの値が「cq:Component」で、
      `sling:resourceSuperType` プロパティの値に「foundation/components」またはいずれかの
      `sling:resourceSuperType` スーパータイプコンポーネントのチェーンのプロパティ値には、「foundation/components」が含まれます。
* `legacy.static.template`:静的テンプレートは、編集可能なテンプレートにアップグレードする必要があります。
   * これは、`jcr:primaryType`プロパティの値が「cq:Template」の場合に検出されます。

## 可能性のある影響およびリスク {#implications-and-risks}

* クラシックUIは、AEMではCloud Serviceとして使用できなくなりました。 オーサリングの標準のインターフェイスは、タッチ対応UIです。
* 既存のカスタムコンポーネントに依存すると、時間の経過と共にメンテナンスコストが増加する可能性があります。

## 可能な解決策 {#solutions}

* [AEM Modernization Tools suite](https://opensource.adobe.com/aem-modernize-tools/)を利用して、AEM Sitesの実装を最新化する手間を省きます。 これらのツールには、次の変換が含まれます。
   * Classic (ExtJS) Dialogs to Coral Dialogs
   * 基盤コンポーネントからコアコンポーネントへ
   * 編集可能なテンプレートとレスポンシブグリッドへの静的テンプレートと列コントロール
   * 編集可能なテンプレートポリシーに対するデザインおよびデザインダイアログ
* プロジェクトのカスタムコンポーネントライブラリとトランジションを、可能な限り、標準化された[コアコンポーネント](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=ja)のセットにレビューし、開発時間を短縮し、アプリケーションのメンテナンスコストを削減します。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
