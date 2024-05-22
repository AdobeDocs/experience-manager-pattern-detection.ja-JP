---
title: IOI
description: パターン検出コードのヘルプページ。
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 60%

---

# IOI {#ioi}

内部 Oak 読み込み

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="内部 Oak 読み込み"
>abstract="IOI コードは、OSGi を介して読み込む内部 Oak パッケージの使用状況を特定します。 特定のバージョンなしで書き出されます。 Oak バンドルまたは低レベルのAEM サービスでのみ使用されます。"

`IOI` は、お客様による内部 Oak パッケージの使用状況を識別し、OSGi 経由で読み込みます。特定のバージョンなしで書き出されます。 Oak バンドルまたは低レベルのAEM サービスでのみ使用されます。
これらの領域の一部は、で使用されます `com.adobe.granite.repository`起動時にAEMのリポジトリを設定します。 もう １ つの例は、Oak メンテナンスタスクをラップして提供する `com.adobe.granite.maintenance.oak` Adobe バンドルです。

## 考えられる影響およびリスク {#implications-and-risks}

* 今後のAEM バージョンでは、内部の書き出しが削除され、Oak に直接依存している依存関係が壊れたり、バンドルが非アクティブになる可能性があります。
* 内部書き出しの API は変更されることがあります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="実装ガイダンス"
>abstract="カスタムコードを確認して、そのような API の使用状況を特定し、AEM as a Cloud Service に対応するようにカスタムコードをリファクタリングする必要があります。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 低レベルのアクセスではなく、Sling Resource API（または JCR API）を使用します。
* 公開 API や SPI の一部ではない内部パッケージへの依存は避けてください。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
