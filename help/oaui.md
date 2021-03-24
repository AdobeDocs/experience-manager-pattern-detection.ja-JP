---
title: OAUI
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 6%

---


# OAUI {#oaui}

OAuthユーザーインスタンス

## 背景 {#background}

`OAUI` 正しい移行が必要なOAuth関連の設定済みユーザーが少なくとも1人あるパターンを識別します。

`/home/user-path/user-node/oauth`の形式の`rep:AuthorizableId`ノードの直下に`oauth`という名前のサブノードがある場合、OAuthはユーザーに対して設定されます。

次に例を示します。`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`.

## 可能性のある影響およびリスク {#implications-and-risks}

* OAuthで構成された外部ユーザーは、次の手順で再設定されるまで、作成者インスタンスまたは発行インスタンスでログインできません。

## 可能な解決策 {#solutions}

* Adobe移行のオプションについては、ユーザーの担当者にお問い合わせください。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
