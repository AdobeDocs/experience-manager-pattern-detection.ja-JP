---
title: IOI
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: ht
source-wordcount: '152'
ht-degree: 100%

---


# IOI {#ioi}

内部 Oak 読み込み

## 背景 {#background}

`IOI` は、OSGi を介して読み込む内部 Oak パッケージの使用を識別します。Oak パッケージは通常、特別なバージョンを使用することなく書き出され、別の Oak バンドルや低レベルの AEM で使用されることを想定しています。

その一部は、起動時に AEM のリポジトリを設定する `com.adobe.granite.repository` によって使用されます。もう １ つの例は、Oak メンテナンスタスクをラップして提供する `com.adobe.granite.maintenance.oak` Adobe バンドルです。

## 可能性のある影響およびリスク {#implications-and-risks}

* 今後の AEM バージョンでは、内部書き出しが削除されて、Oak に直接依存する依存関係が壊れたり、非アクティブなバンドルが発生したりする可能性があります。
* 内部書き出しの API は変更されることがあります。

## 可能な解決策 {#solutions}

* 低レベルのアクセスではなく、Sling Resource API（または JCR API）を使用します。
* 公開 API や SPI の一部ではない内部パッケージへの依存は避けてください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。