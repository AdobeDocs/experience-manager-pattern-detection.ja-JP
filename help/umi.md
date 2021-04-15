---
title: UMI
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: ht
source-wordcount: '145'
ht-degree: 100%

---


# UMI {#umi}

アップグレード設定ミスの問題

## 背景 {#background}

`UMI` は、アップグレードに伴い、アップグレードの失敗や機能低下も含め、問題を生じる原因となる特定の OSGi 設定への変更を識別します。

次の設定について変更がないかをチェックします。
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`

## 可能性のある影響およびリスク {#implications-and-risks}

* 設定の変更や削除を行うと、次の問題を生じることがあります。
   * アップグレードの停止（例：`org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids` には存在する `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` が存在していない場合）。
   * アップグレード後の認証の問題（`org.apache.sling.engine.impl.auth.SlingAuthenticator`）。
   * 特定の機能で所定の動作が実行されない場合があります。例えば、`org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` を変更すると、一部の JSP ファイルがコンパイルから除外され、結果的に機能が欠落することがあります。

## 可能な解決策 {#solutions}

* 上記の 4 つの設定は、変更または削除しないでください。
* 設定を変更した場合は、所定の値に戻す必要があります。これらの値は、`UMI` メッセージで指示されます。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
