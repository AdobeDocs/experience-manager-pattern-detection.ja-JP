---
title: OU
description: パターン検出コードのヘルプページ
source-git-commit: fdc3e8bdef27de971743a9ecb04d3912cf8e60ad
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---

# OU {#ou}

古い使用

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ou_overview"
>title="古い使用"
>abstract="OU は、Sling や AEM のコンポーネントまたは API OSGi のエクスポートなどの一部の JCR ノードが、互換性のない形で変更または削除される状況を表しています。アップグレードの前に、お客様がこの変更について認識していないことがあります。その結果、互換性のないバージョンにアップグレードされたり、まったく使用できなくなったりする可能性があります。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=ja" text="主要な変更点 - AEM as a Cloud Service"

`OU` は、Sling や AEM のコンポーネント、または API OSGi のエクスポートなどの一部の JCR ノードが、互換性のない方法で変更または削除される状況を識別します。アップグレードの前に、お客様がこの変更について認識していないことがあります。その結果、互換性のないバージョンにアップグレードされたり、まったく使用できなくなったりする可能性があります。

古いバージョンはデフォルトではインストールされていないので、お客様のアプリケーションが正常に動作しない場合があります。

## 可能性のある影響およびリスク {#implications-and-risks}

* 非推奨（廃止予定）のコンポーネントまたは API を使用するコンポーネントに依存する機能が破損して、アップグレード後に正しく解決されない場合があります。
* アップグレード後に、お客様のアプリケーションの機能や AEM 機能の一部が正しく動作しない場合やアクティブにならない場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ou_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、カスタムコードを確認し、最新バージョンの AEM コンポーネントまたは API を使用するように修正することをお勧めします。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience Manager SDK API"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 短期的：互換パッケージのインストールが役立つ場合があります。
* 長期的：最新バージョンの AEM コンポーネントまたは API に合わせてカスタムコードを適合させます。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
