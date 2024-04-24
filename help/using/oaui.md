---
title: OAUI
description: パターン検出コードのヘルプページ
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 44%

---

# OAUI {#oaui}

OAuth ユーザーインスタンス

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth ユーザーインスタンス"
>abstract="OAUI コードは、適切な移行を必要とする OAuth 関連の設定済みユーザーが 1 人以上存在するパターンを識別します。OAuth は、/home/user-path/user-node/oauth の形式で rep:AuthorizableId ノードの直下に oauth という名前のサブノードがある場合にユーザーに設定されます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - リリースノート"

`OAUI`  は、正しい移行を必要とする OAuth 関連の設定済みユーザーが 1 人以上存在するパターンを識別します。

OAuth は、`oauth` というサブノードが、`rep:AuthorizableId` ノードの直下に `/home/user-path/user-node/oauth` の形式で存在する場合に、ユーザーに対して設定されます。

例：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`

## 可能性のある影響およびリスク {#implications-and-risks}

* OAuth で設定された外部ユーザーは、以下の手順で再設定しない限り、オーサーインスタンスまたはパブリッシュインスタンスにログインできません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="実装ガイダンス"
>abstract="OAuth で設定された外部ユーザーは、AEMas a Cloud Service環境に対応するように再設定されるまでは、オーサーインスタンスまたはパブリッシュインスタンスにログインできません。 AEMas a Cloud Serviceでは、作成者、管理者、開発者の各ユーザーに対してのみ IMS 認証をサポートしており、公開環境向けには SAML ベースの統合を提供しています。 ヘルプまたは詳しい説明については、Adobeサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/security/ims-support" text="IMS のサポート - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/personalization/user-and-group-sync-for-publish-tier#integration-with-an-idp" text="SAML 統合 - パブリッシュ"

* ユーザー移行のオプションについて話し合う必要がある場合は、Adobe担当者にお問い合わせください。
* に連絡してください [AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 説明するため、または懸念に対処するため。
