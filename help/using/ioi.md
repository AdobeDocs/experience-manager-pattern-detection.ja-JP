---
title: IOI
description: パターン検出コードのヘルプページ
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 64%

---

# IOI {#ioi}

内部 Oak 読み込み

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="内部 Oak 読み込み"
>abstract="IOI コードは、OSGi を介して読み込む内部 Oak パッケージの使用を識別します。Oak パッケージは、特定のバージョンを使用することなく書き出され、別の Oak バンドルや低レベルのAEM サービスでのみ使用されることを想定しています。"

`IOI`  OSGi を介して読み込む内部 Oak パッケージの使用状況を特定します。 Oak パッケージは、特定のバージョンを使用することなく書き出され、別の Oak バンドルや低レベルのAEM サービスでのみ使用されることを想定しています。

その一部は、起動時に AEM のリポジトリーを設定する `com.adobe.granite.repository` によって使用されます。もう １ つの例は、Oak メンテナンスタスクをラップして提供する `com.adobe.granite.maintenance.oak` Adobe バンドルです。

## 可能性のある影響およびリスク {#implications-and-risks}

* 今後の AEM バージョンでは、内部書き出しが削除されて、Oak に直接依存する依存関係が壊れたり、非アクティブなバンドルが発生したりする可能性があります。
* 内部書き出しの API は変更されることがあります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="実装ガイダンス"
>abstract="カスタムコードを確認して、そのような API の使用状況を特定し、AEM as a Cloud Service に対応するようにカスタムコードをリファクタリングする必要があります。ヘルプまたは詳しい説明については、Adobeサポートにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 低レベルのアクセスではなく、Sling Resource API（または JCR API）を使用します。
* 公開 API や SPI の一部ではない内部パッケージへの依存は避けてください。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
