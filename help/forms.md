---
title: FORM
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: aa44c3ce87496f412191000f1980a7ebbde386cd
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 0%

---


# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

`FORMS` から [!DNL Adobe Experience Manager Forms] への移行に関連する潜在的な問題を、として特定 [!DNL Adobe Experience Manager Form]し [!DNL Cloud Service]ます。[!DNL Cloud Service]に移行する前に、これらの問題に対処してください。

次のサブタイプは、様々なタイプの問題を特定するのに役立ちます。

* `modified.feature`:これらの機能、アセット、またはAPIは、Cloud Serviceのために更新または変更されました。Cloud Serviceに移行する前に、移行ユーティリティを実行し、これらの機能とアセットをCloud Serviceと互換性のあるものにします。
* `unavailable.feature`:環境に、使用できない機能とアセットまたはCloud Serviceから削除された機能が含まれています。このような機能やアセットは、Cloud Service環境に移行しないでください。
* `unsupported.feature`:お使いの環境で、Cloud Serviceではまだサポートされていない機能が使用されています。このような機能やアセットは、Cloud Service環境に移行しないでください。 機能の可用性については、毎月のリリースノートを確認してください。
* `unsupported.api`:お使いの環境には、まだCloud ServiceでサポートされていないAPIがいくつかあります。Cloud Serviceに移行する前に、これらのAPIを無効にする、置き換える、またはコードから削除します。 機能の可用性については、毎月のリリースノートを確認してください。

一部の機能やAPIをCloud Serviceと互換性を持たせるために必要な置き換えやその他の対応については、[考えられる示唆とリスク](#implications-and-risks)と[考えられる解決策](#solutions)の節を参照してください

## 可能性のある影響およびリスク {#implications-and-risks}

[!DNL Adobe Experience Manager Forms as a Cloud Service]に移行する前に、次の問題に対処してください。 以下に示す意味とリスクに対処しない場合、一部の機能はCloud Service環境で期待どおりに機能しません。

* ルールエディター機能のコードエディター機能は使用できません。 (CODE_EDITOR)

* 電子メールのサポート（SMTPポート）は、デフォルトで無効になっています。 (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL PDFの電子メール]**&#x200B;送信アクションを使用できません。(EMAIL_PDF_SUBMIT_ACTION)

* XFAベースのアダプティブFormsは、まだサポートされていません。 (XFA_BASED_FORM、XDP_BASED_FORM)

* 送信アクションは、すべての署名者が署名を完了するのを待つ代わりに、フォームの送信時にすぐに呼び出されます。 したがって、署名者に送信されるAdobe Sign契約PDFは、送信アクションで使用したり処理を行うことができません。 (FORM_SIGN_INTEGRATION)

* 署名ステップは使用できません。 (SIGNATURE_STEP)

* [確認]ステップは使用できません。 (VERIFY_STEP)

* Formsポータル機能と&#x200B;**[!UICONTROL Formsポータル送信アクション]**&#x200B;はまだ使用できません。 (DRAFT_PORTAL_SUBMISSION、FORMS_PORTAL、DRAFT_AUTO_SAVE、DRAFT_SAVE)

* **[!UICONTROL Forms Workflowへの送信]**&#x200B;送信アクションは使用できません。 [!DNL AEM 6.5 Forms]以前のバージョンでは、送信アクションは、アダプティブフォームデータを従来の[!DNL AEM Forms on JEE]ワークフローやLiveCycle Workflowに送信するために使用されていました。 (LC_WORKFLOW_SUBMISSION)

* Interactive Communications機能は使用できません。  (FP_プロファイル_INTERACTIVE_COMMUNICATIONS)。

* **[!UICONTROL 「]** ドラフトとして保存」および「 **[!UICONTROL 自動]** 保存」アダプティブフォームの機能は、現在サポートされていません。(DRAFT_AUTO_SAVE、DRAFT_SAVE)

* メタデータアコーディオンは使用できません。 (METADATA_ACCORDION_FORM_コンテナ)

* CAPTCHAコンポーネントは、デフォルトで、Google reCAPTCHAサービスを使用してCAPTCHAを検証するようになりました。 Adobe Experience Managerを使用してCAPTCHAを検証するオプションは廃止されました。 (FORMS_CAPTCHA)

* [!DNL AEM Forms] アプリはでは使用できません [!DNL Cloud Services]。(AEM_FORMS_APP)

* [ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-65/forms/install-aem-forms/osgi-installation/install-configure-document-services.html?lang=en#deployment-topology) サービスの手順は、AEMワークフローでは使用できません。(WORKFLOW_DOCSERVICES)

## 可能な解決策 {#solutions}

* 移行ユーティリティを使用して、環境上のすべてのルールスクリプトを再利用可能な関数に変換します。 ルールスクリプトで取得した結果を引き続き取得するには、ビジュアルルールエディターで再利用可能な関数を使用します。 (CODE_EDITOR)

* お使いの環境に対して電子メール（SMTPポートを開く）機能を有効にするには、サポートチームにお問い合わせください。 デフォルトでは、送信HTTP接続とHTTPS接続のみが有効です。 （EMAIL_SERVICE_CONFIGURATION、電子メール手順）

* **[!UICONTROL 電子メールPDF]**&#x200B;の代わりに、**[!UICONTROL 電子メール]**&#x200B;送信アクションを使用します。 **[!UICONTROL 電子メール]**&#x200B;送信アクションは、添付ファイルを送信し、レコード(DoR)のドキュメントを電子メールで添付するためのオプションを提供します。 (EMAIL_PDF_SUBMIT_ACTION)

* 送信されたデータには、Adobe Sign契約IDが含まれます。 必要に応じて、署名者契約IDを使用して署名者契約PDFを取得できます。  (FORM_SIGN_INTEGRATION)

* 既存のアダプティブフォームから署名手順を削除します。 [ブラウザー内署名エクスペリエンス](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)を使用するようにアダプティブフォームを設定します。 アダプティブフォームの送信時にブラウザ内で契約に署名するためのAdobe Sign契約書を表示します。 ブラウザー内署名エクスペリエンスにより、より高速な署名エクスペリエンスが提供され、署名者の時間を節約できます。 (SIGNATURE_STEP)

* このようなフォームを[!DNL Cloud Service]環境に移動する前に、既存のアダプティブFormsから確認手順を削除します。 (VERIFY_STEP)

* 既存のアダプティブフォームを変更して、「RESTエンドポイントへの送信](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-to-rest-endpoint)」、「[電子メール](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#send-email)を送信」、「[フォームデータモデルを使用した送信](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-using-form-data-model)」、「[AEMワークフロー](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)送信アクションを呼び出します。 [FormsポータルとFormsポータルの送信アクションはまだ使用できません。 機能の可用性については、毎月のリリースノートを確認してください。 (FORMSポータル送信、FORMSポータル)

* AEMワークフローを開発し、既存のアダプティブフォームを変更して、**[!UICONTROL 「Forms Workflowへ送信」]**「送信」アクションを使用する代わりに、[AEMワークフロー](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)送信アクションを使用してAEMワークフローにデータを送信できます。 カスタムの送信アクションを作成して、[!UICONTROL Forms Workflow]に送信を使用する代わりに、データ、添付ファイル、またはレコードのドキュメント(DoR)をLiveCycleプロセスに送信できます。 (LC_WORKFLOW_SUBMISSION)

* インタラクティブコミュニケーション機能の可用性については、毎月のリリースノートを確認してください。 この機能が使用できない限り、Cloud Service環境にInteractive Communications、Letters、および関連する辞書を移行しないでください。 (FP_プロファイル_INTERACTIVE_COMMUNICATIONS)

* Cloud Serviceに移行する前に、アダプティブFormsで「**[!UICONTROL ドラフトとして保存]**」および「**[!UICONTROL 自動保存]**&#x200B;を有効にする」オプションを無効にします。 これらのオプションは、Cloud ServiceのFormsポータル機能がリリースされた後に有効にできます。 機能の可用性については、毎月のリリースノートを確認してください。 (DRAFT_AUTO_SAVE、DRAFT_SAVE)

* メタデータアコーディオンは置き換えられません。 フォームをCloud Serviceに移行する前に、フォームから削除してください。(METADATA_ACCORDION_FORM_コンテナ)

* Adobe Experience Managerが提供するCAPTCHAサービスの代わりに、Google reCaptchaを使用します。 (FORMS_CAPTCHA)

* レスポンシブデザインのアダプティブFormsオファー。 これらのフォームは、基になるデバイスに基づいて外観、デザインおよびインタラクティブ性を変更します。 [!DNL AEM Forms]アプリの提供状況に関する毎月のリリースノートを見ながら、モバイルデバイスでアダプティブFormsを引き続き使用できます。 (AEM_FORMS_APP)

* ドキュメントサービスワークフロー手順を使用するAEMワークフローモデルは移行しないでください。 また、ドキュメントサービスのワークフロー手順を使用するワークフローモデルにユーザーデータを送信するアダプティブFormsを移行または更新しないでください。また、フォームを移行する前に、[サポートされているアクション](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html)に送信します。 (WORKFLOW_DOCSERVICES)

* XFAベースのアダプティブFormsのサポートは、初期設定では利用できません。 XFAベースのアダプティブFormsを使用する場合は、使用事例と具体的な要件の詳細をAdobeサポートにお問い合わせください。(XFA_BASED_FORM, XDP_BASED_FORM)

詳細を知ったり、懸念事項に対処するには、[Adobeサポート](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)に連絡してください。
