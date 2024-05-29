---
title: OAUI
description: パターン検出コードのヘルプページ。
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: b77a168fc8c075e8e41149a38df4d83fd2504a14
workflow-type: ht
source-wordcount: '228'
ht-degree: 100%

---

# OAUI {#oaui}

OAuth ユーザーインスタンス

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth ユーザーインスタンス"
>abstract="OAUI コードは、適切な移行を必要とする OAuth 関連の設定済みユーザーが 1 人以上存在するパターンを識別します。OAuth は、/home/user-path/user-node/oauth の形式で rep:AuthorizableId ノードの直下に OAuth という名前のサブノードがある場合に、ユーザーに設定されます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - リリースノート"

`OAUI` は、適切な移行を必要とする OAuth 関連の設定済みユーザーが 1 人以上存在するパターンを識別します。

OAuth は、`oauth` というサブノードが、`rep:AuthorizableId` ノードの直下に `/home/user-path/user-node/oauth` の形式で存在する場合に、ユーザーに対して設定されます。

例：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`

## 考えられる影響とリスク {#implications-and-risks}

* OAuth で設定された外部ユーザーは、下記の手順で再設定しない限り、オーサーインスタンスまたはパブリッシュインスタンスにはログインできません。

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="実装ガイダンス"
>abstract="OAuth で設定された外部ユーザーは、AEM as a Cloud Service と互換性があるように再設定しない限り、オーサーインスタンスまたはパブリッシュインスタンスにはログインできません。AEM as a Cloud Service では、作成者、管理者、開発者の各ユーザーにのみ IMS 認証サポートを提供し、パブリッシュ環境には SAML ベースの統合を提供します。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/security/ims-support" text="IMS のサポート - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/authoring/personalization/user-and-group-sync-for-publish-tier#integration-with-an-idp" text="SAML 統合 - パブリッシュ"

* ユーザーの移行に関するオプションについては、アドビ担当者にお問い合わせください。
* 詳しい説明や懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
