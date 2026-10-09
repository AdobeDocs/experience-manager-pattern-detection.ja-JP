---
title: IOI
description: パターン検出コードのヘルプページ。
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: baa8f6dbf24b735348ed6b27f1e885b5078859ce
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 100%
---
# IOI {#ioi}

内部 Oak 取り込み

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="内部 Oak 取り込み"
>abstract="IOI コードは、OSGi を介して内部 Oak パッケージを読み込む顧客による使用を識別します。 Oak パッケージは、バージョンなしで書き出されます。 それらを使用するのは、Oak バンドルまたは低レベルの AEM サービスのみです。"

`IOI` は、OSGi を介して読み込まれた内部 Oak パッケージが使用されているかどうかを識別します。 Oak パッケージは、バージョンなしで書き出されます。 Oak バンドルまたは低レベルの AEM サービスは、それらのみを使用します。
これらの領域の一部は `com.adobe.granite.repository` によって使用され、起動時に AEM のリポジトリを設定します。 もう 1 つの例は、Oak メンテナンスタスクをラップして提供する `com.adobe.granite.maintenance.oak` Adobe バンドルです。

## 考えられる影響とリスク {#implications-and-risks}

* 今後の AEM バージョンでは、内部書き出しが削除されて、Oak に直接依存する依存関係が壊れたり、非アクティブなバンドルが発生したりする可能性があります。
* 内部書き出しの API は変更される場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="実装ガイダンス"
>abstract="カスタムコードを確認して、そのような API の使用状況を特定し、AEM as a Cloud Service に対応するようにカスタムコードをリファクタリングする必要があります。 ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 低レベルのアクセスではなく、Sling Resource API（または JCR API）を使用します。
* 公開 API や SPI の一部ではない内部パッケージへの依存は避けてください。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
