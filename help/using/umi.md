---
title: UMI
description: パターン検出コードのヘルプページ。
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 100%

---

# UMI {#umi}

アップグレード設定ミスの問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="アップグレード設定ミスの問題"
>abstract="UMI は、アップグレードに伴い、アップグレードの失敗や機能低下も含め、問題を生じる原因となる特定の OSGi 設定への変更を識別します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="主な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - リリースノート"

`UMI` は、アップグレードに伴い、アップグレードの失敗や機能低下も含め、問題を生じる原因となる特定の OSGi 設定への変更を識別します。

次の設定について変更がないかをチェックします。

* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`
* `com.day.cq.commons.impl.ExternalizerImpl`
* `org.apache.sling.commons.log.LogManager.factory.config`：カスタムロガーの `org.apache.sling.commons.log.file` プロパティが `logs/error.log` ファイル以外を指しているかどうかを識別します。

## 考えられる影響とリスク {#implications-and-risks}

* 設定の変更や削除を行うと、次の問題が発生する場合があります。
   * アップグレードの停止（例：`org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids` には存在する `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` が存在していない場合）。
   * アップグレード後の認証の問題（`org.apache.sling.engine.impl.auth.SlingAuthenticator`）。
   * 特定の機能で所定の動作が実行されない場合があります。例えば、`org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` を変更すると、一部の JSP ファイルがコンパイルから除外され、結果的に機能が欠落することがあります。
   * Externalizer 設定の値 `com.day.cq.commons.impl.ExternalizerImpl` は、AEM as a Cloud Service の Cloud Manager 環境変数によって設定されます。
   * AEM as a Cloud Services は、カスタムログファイルをサポートしていません。カスタム名のログに書き込まれたログは、AEM as a Cloud Service からアクセスできません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、現在の設定を確認し、前述の設定に対して行った変更を元に戻して、今後アップグレードに関する問題が発生しないようにすることをお勧めします。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 上記の 4 つの設定は、変更または削除しないでください。
   * 次の違反があった場合：\
     「Required properties for the OSGi configuration `xyz-configuration` are missing: &#39;[property-1,property-2...]&#39;.」\
     これらの OSGi 設定は OOTB であり、OSGi 設定マネージャーから変更または保存されたことがない可能性があるので、これらの削除が正しいかどうかを確認してください。
* 設定を変更した場合は、所定の値に戻す必要があります。これらの値は、`UMI` メッセージで指示されます。
* `com.day.cq.commons.impl.ExternalizerImpl` について詳しくは、AEM as a Cloud Service の Cloud Manager 環境変数を使用して Externalizer 設定を行う場合の[ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/implementing/developer-tools/externalizer)を参照してください。
* `org.apache.sling.commons.log.LogManager.factory.config` について詳しくは、カスタマイズしたロガーを `logs/error.log` ファイルに送信するように OSGI 設定を変更します。`logs/error.log` ファイルへの再指定について詳しくは、[ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/logs)を参照してください。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
