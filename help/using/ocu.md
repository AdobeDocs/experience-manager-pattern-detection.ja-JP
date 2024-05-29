---
title: OCU
description: パターン検出コードのヘルプページ。
exl-id: cb28c727-415d-436c-ab74-cf7f1f34f7c7
source-git-commit: b77a168fc8c075e8e41149a38df4d83fd2504a14
workflow-type: ht
source-wordcount: '278'
ht-degree: 100%

---

# OCU {#ocu}

非推奨（廃止予定）：古いコードの使用（OU（古い使用）に置き換え）

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_overview"
>title="古いコードの使用"
>abstract="OCU は、Sling や AEM のコンポーネント、または API OSGi のエクスポートなどの一部の JCR ノードが、互換性のない方法で変更または削除される状況を識別します。顧客はアップグレード前に、この変更について認識していないことがあります。その結果、互換性のないバージョンにアップグレードされたり、まったく使用できなくなったりする可能性があります。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="主な変更点 - AEM as a Cloud Service"

`OCU` は、Sling や AEM のコンポーネントまたは API OSGi の書き出しなどの一部の JCR ノードが、互換性のない形で変更または削除される状況を表しています。顧客はアップグレード前に、この変更について認識していないことがあります。その結果、互換性のないバージョンにアップグレードされたり、まったく使用できなくなったりする可能性があります。

古いバージョンはデフォルトではインストールされていないので、お客様のアプリケーションが正常に動作しない場合があります。

## 考えられる影響とリスク {#implications-and-risks}

* 非推奨（廃止予定）のコンポーネントまたは API を使用するコンポーネントに依存する機能が破損して、アップグレード後に正しく解決されない場合があります。
* アップグレード後に、お客様のアプリケーションの機能や AEM 機能の一部が正しく動作しない場合やアクティブにならない場合があります。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_guidance"
>title="実装ガイダンス"
>abstract="ベストプラクティスとしては、カスタムコードを確認し、最新バージョンの AEM コンポーネントまたは API を使用するように修正することをお勧めします。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience Manager SDK API"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 短期的：互換性パッケージのインストールが役立つ場合があります。
* 長期的：最新バージョンの AEM コンポーネントまたは API を使用するようにカスタムコードを適応させます。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
