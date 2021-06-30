---
title: ACV
description: パターン検出コードのヘルプページ
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a5
source-git-commit: 57e33b97aba253bad62cf95dcca9ef6885d263e6
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# ACV {#acv}

Assetsコンテンツバリデーター

## 背景 {#background}

>[!INFO]
>id=&quot;aemcloud_bpa_acv_overview&quot;
>title=&quot;Assetsコンテンツバリデーター&quot;
>abstract=&quot;ACVは、アセットコンテンツ内の欠落している必須ノードを識別します。&quot;
>additional-url=&quot;https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html&quot; text=&quot;主な変更点 —Cloud ServiceとしてのExperience Manager&quot;
>additional-url=&quot;https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html&quot; text=&quot;Cloud ServiceとしてのExperience Manager — リリースノート&quot;

`ACV`  アセットのコンテンツバリデーターが、アセットコンテンツ内の必須ノードが見つからないことを識別します。これにより、特定のAssets機能がCloud ServiceとしてExperience Managerされない可能性があります。

サブタイプは、次のような様々なタイプの情報を識別するために使用されます。

* `assets.sanity.missing.jcrcontent`:リポジトリ内の必須ノードが見つからないフォルダーを特定します。リポジトリ内の欠落しているコンテンツを特定すると、機能や使用例の破損を防ぐことができます。

## 可能性のある影響およびリスク {#implications-and-risks}

これにより、Cloud Serviceとしての継承されたプロパティに依存する特定のAssets機能が失敗する可能性があります。

## 可能な解決策 {#solutions}

>[!INFO]
>id=&quot;aemcloud_bpa_acv_guidance&quot;
>title=&quot;実装ガイダンス&quot;
>abstract=&quot;Adobeでは、継承されたプロパティに依存するワークフローが壊れないように、コンテンツ構造を確認することをお勧めします。 カスタマーケアにお問い合わせください。」
>additional-url=&quot;https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html&quot; text=&quot;Experience Cloudのサポート&quot;

* フォルダーに子ノードがない場合は、そのフォルダーを分析します。 フォルダー数が管理可能な場合はノードを手動で作成し、それ以外の場合はスクリプトを使用します。
* アドビの[Experience Managerカスタマーケアチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)に連絡して、明確な情報を入手したり、懸念事項に対処したりできます。
