---
title: FORM
description: パターン検出コードのヘルプページ
exl-id: ac28760b-b0ab-4082-b7ce-730cddc4ad83
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '1228'
ht-degree: 39%

---

# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_overview"
>title="FORMS"
>abstract="Formsコードは、Adobe Experience Manager FormsからAdobe Experience Manager Formsへの移行に関連する潜在的な問題をCloud Serviceとして特定します。 Cloud Serviceに移行する前に、潜在的な意味合いと関連するリスクを確認し、これらの問題に対処します。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-pattern-detection/table-of-contents/forms.html#implications-and-risks" text="可能性のある影響およびリスク"

`FORMS` から [!DNL Adobe Experience Manager Forms] への移行に関連する潜在的な問題を、として特定 [!DNL Adobe Experience Manager Form]し [!DNL Cloud Service]ます。[!DNL Cloud Service]に移行する前に、これらの問題に対処してください。

次のサブタイプを利用して、様々なタイプの問題を特定することができます。

* `modified.feature`：これらの機能、アセット、または API は、Cloud Service に対応して更新、または変更されています。Cloud Service に移行する前に、移行ユーティリティを実行して、これらの機能やアセットが Cloud Service との互換性を維持できるようにします。
* `unavailable.feature`：使用環境に、Cloud Service では利用できない、あるいは Cloud Service から削除された機能やアセットが含まれています。このような機能やアセットは、Cloud Service 環境には移行しないでください。
* `unsupported.feature`：使用環境で、Cloud Service ではまだサポートされていない機能が使用されています。このような機能やアセットは、Cloud Service 環境には移行しないでください。機能の利用に関する情報については、毎月のリリースノートを参照してください。
* `unsupported.api`：使用環境に、Cloud Service ではまだサポートされていない API が一部含まれています。Cloud Service に移行する前に、コード中のこれらの API を無効にするか、別の API に置き換えるか、削除してください。機能の利用に関する情報については、毎月のリリースノートを参照してください。

特定の機能や API を Cloud Service と互換性のあるものするために必要となる置き換えやその他の処置については、「[可能性のある影響およびリスク](#implications-and-risks)」および「[可能な解決策](#solutions)」のセクションを参照してください

## 可能性のある影響およびリスク {#implications-and-risks}

[!DNL Adobe Experience Manager Forms as a Cloud Service]に移行する前に、次の問題に対処してください。 下記の影響とリスクに対応しておかないと、機能によっては Cloud Service 環境で期待通り動作しないものもあります。

* ルールエディター機能のうちのコードエディターの部分は使用できません。(CODE_EDITOR)

* 電子メールのサポート（SMTPポート）は、デフォルトで無効になっています。(EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL PDFの電子メール]**&#x200B;送信アクションを使用できません。(EMAIL_PDF_SUBMIT_ACTION)

* XFAベースのアダプティブFormsは、まだサポートされていません。 (XFA_BASED_FORM、XDP_BASED_FORM)

* 送信アクションは、すべての署名者が署名を完了するのを待つ代わりに、フォームの送信時にすぐに呼び出されます。 したがって、署名者に送信されるAdobe Sign契約PDFは、送信アクションで使用したり処理を行うことができません。 (FORM_SIGN_INTEGRATION)

* 署名ステップは使用できません。(SIGNATURE_STEP)

* 検証ステップは使用できません。(VERIFY_STEP)

* Formsポータル機能と&#x200B;**[!UICONTROL Formsポータル送信アクション]**&#x200B;はまだ使用できません。 (FORMS_PORTAL_SUBMISSION, FORMS_PORTAL, DRAFT_AUTO_SAVE, DRAFT_SAVE)

* **[!UICONTROL Forms Workflowへの送信]**&#x200B;送信アクションは使用できません。 [!DNL AEM 6.5 Forms]以前のバージョンでは、送信アクションは、アダプティブフォームデータを従来の[!DNL AEM Forms on JEE]ワークフローやLiveCycle Workflowに送信するために使用されていました。 (LC_WORKFLOW_SUBMISSION)

* インタラクティブ通信の機能は使用できません。(FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* 現在のところ、アダプティブフォームの「**[!UICONTROL ドラフトとして保存]**」と「**[!UICONTROL 自動保存]**」の機能はサポートされていません。(DRAFT_AUTO_SAVE, DRAFT_SAVE)

* メタデータのアコーディオン機能は使用できません。(METADATA_ACCORDION_FORM_CONTAINER)

* CAPTCHA コンポーネントでは、デフォルトにより Google reCAPTCHA サービスを使用して CAPTCHA を検証できるようになりました。Adobe Experience Managerを使用してCAPTCHAを検証するオプションは廃止されました。 (FORMS_CAPTCHA)

* [!DNL AEM Forms] アプリはでは使用できません [!DNL Cloud Services]。(AEM_FORMS_APP)

* [ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-65/forms/install-aem-forms/osgi-installation/install-configure-document-services.html?lang=en#deployment-topology) サービスの手順は、AEMワークフローでは使用できません。(WORKFLOW_DOCSERVICES)

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_guidance"
>title="導入ガイダンス"
>abstract="FORMSコードで公開された情報は、一部の機能およびAPIをCloud Serviceと互換性を持たせるために必要な置き換えやその他の対応に関するガイダンスを提供できます。 ヘルプと説明を求めるAdobeサポートにご連絡ください。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloudサポート"

* 移行ユーティリティを使用して、現在の環境にあるルールスクリプトをすべて再利用可能な関数に変換します。再利用可能な関数をビジュアルルールエディターで使用することにより、引き続き、ルールスクリプトで取得した結果を利用できるようになります。(CODE_EDITOR)

* ご使用の環境で電子メール（オープン SMTP ポート）機能を有効にする方法については、サポートチームにお問い合わせください。デフォルトでは、送信 HTTP と HTTPS 接続が有効になります。（EMAIL_SERVICE_CONFIGURATION、電子メール手順）

* **[!UICONTROL 電子メールPDF]**&#x200B;の代わりに、**[!UICONTROL 電子メール]**&#x200B;送信アクションを使用します。 **[!UICONTROL 電子メール]**&#x200B;送信アクションは、添付ファイルを送信し、レコード(DoR)のドキュメントを電子メールで添付するためのオプションを提供します。 (EMAIL_PDF_SUBMIT_ACTION)

* 送信されたデータには、Adobe Sign契約IDが含まれます。 Sign Agreement ID により、必要に応じて Sign Agreement PDF を検索できます。(FORM_SIGN_INTEGRATION)

* 既存のアダプティブフォームから署名手順を削除します。 [ブラウザー内署名エクスペリエンス](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)を使用するようにアダプティブフォームを設定します。 アダプティブフォームの送信時にブラウザ内で契約に署名するためのAdobe Sign契約書を表示します。 ブラウザー内署名エクスペリエンスにより、より高速な署名エクスペリエンスが提供され、署名者の時間を節約できます。 (SIGNATURE_STEP)

* このようなフォームを[!DNL Cloud Service]環境に移動する前に、既存のアダプティブFormsから確認手順を削除します。 (VERIFY_STEP)

* 既存のアダプティブフォームを変更して、「RESTエンドポイントへの送信](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-to-rest-endpoint)」、「[電子メール](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#send-email)を送信」、「[フォームデータモデルを使用した送信](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-using-form-data-model)」、「[AEMワークフロー](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)送信アクションを呼び出します。 [FormsポータルとFormsポータルの送信アクションはまだ使用できません。 機能の利用に関する情報については、毎月のリリースノートを参照してください。 (FORMS_PORTAL_SUBMISSION, FORMS_PORTAL)

* AEMワークフローを開発し、既存のアダプティブフォームを変更して、**[!UICONTROL 「Forms Workflowへ送信」]**「送信」アクションを使用する代わりに、[AEMワークフロー](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)送信アクションを使用してAEMワークフローにデータを送信できます。 カスタムの送信アクションを作成して、[!UICONTROL Forms Workflow]に送信を使用する代わりに、データ、添付ファイル、またはレコードのドキュメント(DoR)をLiveCycleプロセスに送信できます。 (LC_WORKFLOW_SUBMISSION)

* Interactive Communications機能の可用性については、毎月のリリースノートを参照してください。 この機能が使用できない限り、Cloud Service環境にInteractive Communications、Letters、および関連する辞書を移行しないでください。 (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* Cloud Serviceに移行する前に、アダプティブFormsで「**[!UICONTROL ドラフトとして保存]**」および「**[!UICONTROL 自動保存]**&#x200B;を有効にする」オプションを無効にします。 これらのオプションは、フォームポータル機能が Cloud Service でリリースされた後、有効にできます。機能の利用に関する情報については、毎月のリリースノートを参照してください。 (DRAFT_AUTO_SAVE、DRAFT_SAVE)

* メタデータのアコーディオンの代わりとなる機能はありません。フォームを Cloud Service に移行する前に、メタデータのアコーディオンをフォームから削除しておいてください。(METADATA_ACCORDION_FORM_コンテナ)

* Adobe Experience Manager で提供される CAPTCHA サービスの代わりに Google reCAPTCHA を使用してください。(FORMS_CAPTCHA)

* レスポンシブデザインのアダプティブFormsオファー。 これらのフォームは、基になるデバイスに基づいて外観、デザインおよびインタラクティブ性を変更します。 アダプティブFormsをモバイルデバイスで引き続き使用できます。 [!DNL AEM Forms]アプリの提供状況については、毎月のリリースノートを参照してください。 (AEM_FORMS_APP)

* ドキュメントサービスワークフロー手順を使用するAEMワークフローモデルは移行しないでください。 また、ドキュメントサービスのワークフロー手順を使用するワークフローモデルにユーザーデータを送信するアダプティブFormsを移行または更新しないでください。また、フォームを移行する前に、[サポートされているアクション](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html)に送信します。 (WORKFLOW_DOCSERVICES)

* XFAベースのアダプティブFormsのサポートは、初期設定では利用できません。 XFAベースのアダプティブFormsを使用する場合は、使用事例と具体的な要件の詳細をAdobeサポートにお問い合わせください。(XFA_BASED_FORM, XDP_BASED_FORM)

詳しい説明が必要な場合や、懸念事項の対応については、[アドビサポート](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)までお問い合わせください。
