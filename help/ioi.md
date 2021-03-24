---
title: IOI
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 7%

---


# IOI {#ioi}

内部 Oak 読み込み

## 背景 {#background}

`IOI` 内部Oakパッケージを顧客が使用し、OSGiを介してインポートすることを識別します。通常は特別なバージョンなしでエクスポートされ、他のOakバンドルや低レベルのAEMサービスでのみ使用されます。

これらの一部は`com.adobe.granite.repository`が使用し、起動時にAEM用のリポジトリを設定します。 もう1つの例は、Oakのメンテナンスタスクをラップして提供する`com.adobe.granite.maintenance.oak`Adobeバンドルです。

## 可能性のある影響およびリスク {#implications-and-risks}

* 将来のAEMバージョンでは、内部エクスポートが削除され、依存関係の破損や非アクティブなバンドルがOakに直接依存する可能性があります。
* 内部エクスポートのAPIが変更される可能性があります。

## 可能な解決策 {#solutions}

* 低レベルアクセスではなく、SlingリソースAPI（またはJCR API）を使用します。
* パブリックAPIまたはSPIに含まれない内部パッケージに依存しないようにします。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。