---
title: OAUI
description: パターン検出コードのヘルプページ
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 100%

---

# OAUI {#oaui}

OAuth ユーザーインスタンス

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth ユーザーインスタンス"
>abstract="OAUI コードは、適切な移行を必要とする OAuth 関連の設定済みユーザーが 1 人以上存在するパターンを識別します。OAuth は、/home/user-path/user-node/oauth の形式で rep:AuthorizableId ノードの直下に oauth という名前のサブノードがある場合にユーザーに設定されます。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja" text="AEM as a Cloud Service - リリースノート"

`OAUI` は、適切な移行が要求される OAuth 関連の設定済みユーザーが 1 人以上存在するパターンを識別します。

OAuth は、`oauth` というサブノードが、`rep:AuthorizableId` ノードの直下に `/home/user-path/user-node/oauth` の形式で存在する場合に、ユーザーに対して設定されます。

例：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`

## 考えられる影響およびリスク {#implications-and-risks}

* OAuth で設定された外部ユーザーは、下記の手順で再設定しない限り、オーサーインスタンスまたはパブリッシュインスタンスにはログインできません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="実装ガイダンス"
>abstract="OAuth で設定された外部ユーザーは、AEM as a Cloud Service に対応するように再設定されるまでは、オーサーインスタンスまたはパブリッシュインスタンスにログインできません。AEM as a Cloud Service では、作成者、管理者、開発者の各ユーザーおよびパブリッシュ環境向けの SAML ベース統合に対してのみ IMS 認証をサポートしています。ヘルプおよび詳しい説明については、アドビサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/ims-support.html?lang=ja" text="IMS のサポート - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/personalization/user-and-group-sync-for-publish-tier.html?lang=ja#integration-with-an-idp" text="SAML 統合 - パブリッシュ"

* ユーザーの移行に関するオプションについては、Adobe 担当者にお問合せください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
