---
title: OAUI
description: パターン検出コードのヘルプページ
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 48%

---

# OAUI {#oaui}

OAuthユーザーインスタンス

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuthユーザーインスタンス"
>abstract="OAUIコードは、正しい移行が必要なOAuth関連の設定済みユーザーが少なくとも1人存在するパターンを識別します。 OAuthは、/home/user-path/user-node/oauthの形式でrep:AuthorizableIdノードの直下にoauthという名前のサブノードがある場合にユーザー用に構成されます"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=ja" text="AEMをCloud Serviceとして — リリースノート"

`OAUI` は、適切な移行が要求される OAuth 関連の設定済みユーザーが 1 人以上存在するパターンを識別します。

OAuth は、`oauth` というサブノードが、`/home/user-path/user-node/oauth` という形式で `rep:AuthorizableId` ノードの直下に存在する場合に、ユーザーに対して設定されます。

例：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`

## 可能性のある影響およびリスク {#implications-and-risks}

* OAuth で設定された外部ユーザーは、下記の手順で再設定しない限り、author/publish インスタンスにはログインできません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="導入ガイダンス"
>abstract="OAuthで設定された外部ユーザーは、AEMとの互換性を持つように再設定されるまで、作成者インスタンスまたは発行インスタンスでログインできません。 AEM as aCloud ServiceオファーIMS認証は、作成者、管理者、開発者のユーザーおよび発行環境用のSAMLベースの統合に対してのみサポートされます。 ヘルプと説明を求めるAdobeサポートにご連絡ください。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/ims-support.html?lang=ja" text="IMSのサポート — AEMをCloud Serviceとして"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/personalization/user-and-group-sync-for-publish-tier.html?lang=en#integration-with-an-idp" text="SAML統合 — 発行"

* ユーザーの移行に関するオプションについては、Adobe 担当者にお問合せください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
