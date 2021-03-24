---
title: 海
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---


# UMI {#umi}

アップグレードの設定ミスの問題

## 背景 {#background}

`UMI` アップグレードの失敗や機能の低下など、アップグレード時に問題を引き起こす特定のOSGi設定への変更を識別します。

次の設定で変更がチェックされます。
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`

## 可能性のある影響およびリスク {#implications-and-risks}

* 構成を変更または削除すると、次の問題が発生する可能性があります。
   * アップグレードが停止する可能性がある（例：`org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`が見つからないが`org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`に存在する）。
   * アップグレード(`org.apache.sling.engine.impl.auth.SlingAuthenticator`)後に認証の問題が発生する可能性があります。
   * 一部の機能が期待どおりに動作しない場合があります。 例えば`org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`を変更すると、一部のJSPファイルがコンパイルされず、最終的に機能が失われる可能性があります。

## 可能な解決策 {#solutions}

* 上記の4つの設定は変更または削除しないでください。
* 設定を変更した場合は、期待どおりの値に復元する必要があります。 これらの値は`UMI`メッセージに示されます。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
