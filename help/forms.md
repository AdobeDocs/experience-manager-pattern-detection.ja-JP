---
title: Forms
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: a6ba6e93c89644160650882ecbf17028bec35068
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%

---


# [!DNL FORMS] {#forms}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

`FORMS` Cloud ServiceとしてAdobe Experience Manager FormsからAdobe Experience Manager Formsへの移行に関連する潜在的な問題を特定します。Cloud Serviceに移行する前に、これらの問題に対処してください。

次のサブタイプは、様々なタイプの問題を特定するのに役立ちます。

* `modified.feature`:これらの機能、アセット、またはAPIは、Cloud Serviceのために更新または変更されました。Cloud Serviceに移行する前に、移行ユーティリティを実行し、これらの機能とアセットをCloud Serviceと互換性のあるものにします。
* `unavailable.feature`:環境に、使用できない機能とアセットまたはCloud Serviceから削除された機能が含まれています。このような機能やアセットは、Cloud Service環境に移行しないでください。
* `unsupported.feature`:お使いの環境で、Cloud Serviceではまだサポートされていない機能が使用されています。このような機能やアセットは、Cloud Service環境に移行しないでください。 機能の可用性については、毎月のリリースノートを確認してください。
* `unsupported.api`:お使いの環境には、まだCloud ServiceでサポートされていないAPIがいくつかあります。Cloud Serviceに移行する前に、これらのAPIを無効にする、置き換える、またはコードから削除します。 機能の可用性については、毎月のリリースノートを確認してください。

一部の機能やAPIをCloud Serviceと互換性を持たせるために必要な置き換えやその他の対応については、[考えられる示唆とリスク](#implications-and-risks)と[考えられる解決策](#solutions)の節を参照してください

## 可能性のある影響およびリスク {#implications-and-risks}

Cloud ServiceとしてAdobe Experience Manager Formsに移行する前に、次の問題に取り組んでください。 以下に示す意味とリスクに対処しない場合、一部の機能はCloud Service環境で期待どおりに機能しません。

* ルールエディター機能のコードエディター機能は使用できません。 (CODE_EDITOR)

* 電子メールのサポート（SMTPポート）は、デフォルトで無効になっています。 (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL PDFの電子メール]**&#x200B;送信アクションを使用できません。(EMAIL_PDF_SUBMIT_ACTION)

* XDPベースのアダプティブフォームは、まだサポートされていません。 (XDP_BASED_FORM)

* 送信アクションは、すべての署名者が署名を完了するのを待つ代わりに、フォームの送信時にすぐに呼び出されます。 したがって、アダプティブフォームの署名ドキュメント(署名者に送信されるAdobe Sign契約PDF)は、送信アクションで使用したり処理したりすることはできません。 (FORM_SIGN_INTEGRATION)

* 署名ステップは使用できません。 (SIGNATURE_STEP)

* [確認]ステップは使用できません。 (VERIFY_STEP)

* Formsポータル機能と&#x200B;**[!UICONTROL Formsポータル送信アクション]**&#x200B;は使用できません。 Formsポータルを使用して、フォームのリスト、ドラフトの保存、送信済みフォームの表示を行うことはできません。 アダプティブフォームに送信されたデータをFormsポータルに送信(**[!UICONTROL Formsポータル送信アクション]**&#x200B;を使用)することはできません。 [!UICONTROL 「] ドラフトとして保存」および「 [!UICONTROL 自動] 保存」アダプティブフォームの機能は、現在サポートされていません。(DRAFT_PORTAL_SUBMISSION、FORMS_PORTAL、DRAFT_AUTO_SAVE、DRAFT_SAVE)

* **[!UICONTROL Formsへの送信ワークフロー]**&#x200B;の送信アクションは使用できません。 AEM 6.5Formsおよび以前のバージョンでは、アダプティブフォームデータをJEE上のレガシーAEM Formsに送信する際に、送信アクションを使用してワークフローとLiveCycle Workflowを設定していました。 (LC_WORKFLOW_SUBMISSION)

* Interactive Communications機能は使用できません。  (FP_プロファイル_INTERACTIVE_COMMUNICATIONS)。

* **[!UICONTROL 「]** ドラフトとして保存」および「 **[!UICONTROL 自動]** 保存」アダプティブフォームの機能は、現在サポートされていません。(DRAFT_AUTO_SAVE、DRAFT_SAVE)

* メタデータアコーディオンは使用できません。 (METADATA_ACCORDION_FORM_コンテナ)

* CAPTCHAコンポーネントは、デフォルトで、Google reCAPTCHAサービスを使用してCAPTCHAを検証するようになりました。 Adobe Experience Managerを使用してCAPTCHAを検証するオプションは使用できません。 (FORMS_CAPTCHA)

## 可能な解決策 {#solutions}

* 移行ユーティリティを使用して、環境上のすべてのルールスクリプトを再利用可能な関数に変換します。 ルールスクリプトで取得した結果を引き続き取得するには、ビジュアルルールエディターで再利用可能な関数を使用します。 (CODE_EDITOR)

* お使いの環境に対して電子メール（SMTPポートを開く）機能を有効にするには、サポートチームにお問い合わせください。 デフォルトでは、送信HTTP接続とHTTPS接続のみが有効です。 (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL PDFの電子メール]**&#x200B;の代わりに、**[!UICONTROL 電子メール]**&#x200B;送信アクションを使用します。 **[!UICONTROL 電子メール]**&#x200B;送信アクションは、添付ファイルを送信し、レコード(DoR)のドキュメントを電子メールで添付するオプションを提供します。 (EMAIL_PDF_SUBMIT_ACTION)

* XDPベースのアダプティブフォームをCloud Service環境に移行しないでください。 機能の可用性については、毎月のリリースノートを確認してください。 (XDP_BASED_FORM)

* 送信されたデータには、署名契約IDが含まれます。 必要に応じて、署名者契約IDを使用して署名者契約PDFを取得できます。  (FORM_SIGN_INTEGRATION)

* アダプティブフォームの署名手順を、同じウィンドウでアダプティブフォームの投稿送信時に署名するオプションに置き換えます。 これは、引き続き[ブラウザー内署名エクスペリエンス](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)を提供するのに役立ちます。 (SIGNATURE_STEP)

* このようなフォームをCloud Service環境に移動する前に、既存のアダプティブフォームから確認手順を削除してください。 (VERIFY_STEP)

* **[!UICONTROL Formsポータル送信アクション]**&#x200B;に代わる手段はありません。 この送信アクションは、Cloud ServiceのFormsポータル機能がリリースされた後に使用できます。 機能の可用性については、毎月のリリースノートを確認してください。 (FORMSポータル送信、FORMSポータル)

* **[!UICONTROL 送信アクション]**&#x200B;に対する別の送信アクションはありません。 データ、添付ファイル、またはレコードのドキュメント(DoR)をLiveCycleプロセスに送信するカスタム送信アクションを作成できます。 (LC_WORKFLOW_SUBMISSION)

* インタラクティブコミュニケーション、レター、および関連する辞書をCloud Service環境に移行しないでください。 (FP_プロファイル_INTERACTIVE_COMMUNICATIONS)

* アダプティブフォームをCloud Serviceに移行する前に、アダプティブフォームで「**[!UICONTROL ドラフトとして保存]**」および「**[!UICONTROL 自動保存を有効にする]**」オプションを無効にします。 これらのオプションは、Cloud ServiceのFormsポータル機能がリリースされた後に有効にできます。 機能の可用性については、毎月のリリースノートを確認してください。 (DRAFT_AUTO_SAVE、DRAFT_SAVE)

* メタデータアコーディオンは置き換えられません。 フォームをCloud Serviceに移行する前に、フォームから削除してください。(METADATA_ACCORDION_FORM_コンテナ)

* Adobe Experience Managerが提供するCAPTCHAサービスの代わりに、Google reCaptchaを使用します。 (FORMS_CAPTCHA)

詳細を知ったり、懸念事項に対処するには、[Adobeサポート](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)に連絡してください。
