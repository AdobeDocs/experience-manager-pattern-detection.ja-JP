---
title: UMI
description: パターン検出コードのヘルプページ
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 41%

---

# UMI {#umi}

アップグレード設定ミスの問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="アップグレード設定ミスの問題"
>abstract="UMI は、アップグレードに伴い、アップグレードの失敗や機能低下も含め、問題の原因となる特定の OSGi 設定への変更を識別します。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="主要な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - リリースノート"

`UMI`  アップグレードに伴い、アップグレードの失敗や機能低下も含め、問題の原因となる特定の OSGi 設定への変更を特定します。

次の設定について変更がないかをチェックします。

* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`
* `com.day.cq.commons.impl.ExternalizerImpl`
* `org.apache.sling.commons.log.LogManager.factory.config`：カスタムロガーの `org.apache.sling.commons.log.file` プロパティが `logs/error.log` ファイル以外を指しているかどうかを識別します。

## 考えられる影響およびリスク {#implications-and-risks}

* 設定の変更や削除を行うと、次の問題を生じることがあります。
   * アップグレードの停止（例：`org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids` には存在する `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` が存在していない場合）。
   * アップグレード後の認証の問題（`org.apache.sling.engine.impl.auth.SlingAuthenticator`）。
   * 特定の機能で所定の動作が実行されない場合があります。例えば、 `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` 一部の JSP ファイルがコンパイルされなくなり、最終的に機能が失われる可能性があります。
   * Externalizer 設定の値 `com.day.cq.commons.impl.ExternalizerImpl` AEMas a Cloud Serviceの cloud manager 環境変数で設定されます。
   * AEM as a Cloud Services は、カスタムログファイルをサポートしていません。カスタム名のログに書き込まれたログは、AEM as a Cloud Serviceからアクセスできません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスは、現在の設定を確認し、前述の設定に対して行った変更を元に戻して、今後アップグレードに関する問題が発生しないようにすることです。 ヘルプまたは詳しい説明については、Adobeサポートにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 上記の 4 つの設定は、変更または削除しないでください。
   * 次の違反がある場合：\
     &quot;OSGi 設定に必要なプロパティ `xyz-configuration` が見つかりません：「」[property-1,property-2...]&#39;.&#39;&#39;\
     これらの OSGi 設定は OOTB であり、OSGi 設定マネージャーから変更または保存されたことがない可能性があるので、これらの削除が妥当かどうかを確認します。
* 設定を変更した場合は、所定の値に戻す必要があります。これらの値は、`UMI` メッセージで指示されます。
* の場合 `com.day.cq.commons.impl.ExternalizerImpl`を参照してください [詳細を見る](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developer-tools/externalizer) AEM as a Cloud Serviceの Cloud Manager 環境変数を使用して Externalizer 設定を行う場合。
* `org.apache.sling.commons.log.LogManager.factory.config` については、カスタマイズしたロガーを `logs/error.log` ファイルに送信するように OSGI 設定を変更します。参照： [詳細を見る](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/logs) を再指定する場合 `logs/error.log` ファイル。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
