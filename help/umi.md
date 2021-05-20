---
title: UMI
description: パターン検出コードのヘルプページ
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 100%

---

# 羽実 {#umi}

アップグレード設定ミスの問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="アップグレード設定ミスの問題"
>abstract="UMI は、アップグレードに伴い、アップグレードの失敗や機能低下も含め、問題を生じる原因となる特定の OSGi 設定への変更を識別します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja" text="主要な変更点 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja" text="AEM as a Cloud Service - リリースノート"

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

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、現在の設定を確認し、前述の設定に対して行った変更を元に戻して、今後アップグレードに関する問題が発生しないようにすることをお勧めします。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 上記の 4 つの設定は、変更または削除しないでください。
* 設定を変更した場合は、所定の値に戻す必要があります。これらの値は、`UMI` メッセージで指示されます。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
