---
title: OAUI
description: パターン検出コードのヘルプページ
translation-type: ht
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: ht
source-wordcount: '107'
ht-degree: 100%

---


# OAUI {#oaui}

OAuthユーザーインスタンス

## 背景 {#background}

`OAUI` は、適切な移行が要求される OAuth 関連の設定済みユーザーが 1 人以上存在するパターンを識別します。

OAuth は、`oauth` というサブノードが、`/home/user-path/user-node/oauth` という形式で `rep:AuthorizableId` ノードの直下に存在する場合に、ユーザーに対して設定されます。

例：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`

## 可能性のある影響およびリスク {#implications-and-risks}

* OAuth で設定された外部ユーザーは、下記の手順で再設定しない限り、author/publish インスタンスにはログインできません。

## 可能な解決策 {#solutions}

* ユーザーの移行に関するオプションについては、Adobe 担当者にお問合せください。
* 詳しい説明が必要な場合や、懸念事項の対応については、[AEM サポートチーム](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
