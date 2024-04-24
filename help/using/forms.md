---
title: FORM
description: パターン検出コードのヘルプページ
exl-id: ac28760b-b0ab-4082-b7ce-730cddc4ad83
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 72%

---

# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_overview"
>title="FORMS"
>abstract="FORMS コードは、Adobe Experience Manager Forms から Adobe Experience Manager Forms as a Cloud Service への移行に伴って生じる可能性のある問題を特定します。Cloud Serviceへの移行を開始する前に、考えられる影響とリスクを確認し、これらの問題に対処します。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-pattern-detection/table-of-contents/forms#implications-and-risks" text="可能性のある影響およびリスク"

`FORMS`  は、からの移行に伴う潜在的な問題を特定します。 [!DNL Adobe Experience Manager Forms] 対象： [!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service]. [!DNL Cloud Service] への移行を開始する前に、これらの問題に対処します。

次のサブタイプを利用して、様々なタイプの問題を特定することができます。

* `modified.feature`：これらの機能、アセット、または API は、Cloud Service に対応して更新、または変更されています。Cloud Service に移行する前に、移行ユーティリティを実行して、これらの機能やアセットが Cloud Service との互換性を維持できるようにします。
* `unavailable.feature`：使用環境に、Cloud Service では利用できない、あるいは Cloud Service から削除された機能やアセットが含まれています。このような機能やアセットは、Cloud Service 環境には移行しないでください。
* `unsupported.feature`：使用環境で、Cloud Service ではまだサポートされていない機能が使用されています。このような機能やアセットは、Cloud Service 環境には移行しないでください。これらの機能の提供状況については、毎月のリリースノートを参照してください。
* `unsupported.api`：使用環境に、Cloud Service ではまだサポートされていない API が一部含まれています。Cloud Service に移行する前に、コード中のこれらの API を無効にするか、別の API に置き換えるか、削除してください。これらの機能の提供状況については、毎月のリリースノートを参照してください。

一部の機能や API を Cloud Service と互換性のあるものにするために必要な置き換えやその他の処置については、[考えられる影響およびリスク](#implications-and-risks)や[考えられる解決策](#solutions)の節を参照してください。

## 考えられる影響およびリスク {#implications-and-risks}

[!DNL Adobe Experience Manager Forms as a Cloud Service] への移行を開始する前に、次の問題に対処します。下記の影響とリスクに対応しておかないと、機能によっては Cloud Service 環境で期待通り動作しないものもあります。

* ルールエディター機能のうちのコードエディターの部分は使用できません。(CODE_EDITOR)

* メールのサポート（SMTP ポート）は、デフォルトで無効になっています。 (EMAIL_SERVICE_CONFIGURATION)

* この **[!UICONTROL メールPDF]** 送信アクションは使用できません。 (EMAIL_PDF_SUBMIT_ACTION)

* XFA ベースのアダプティブフォームは、まだサポートされていません。(XFA_BASED_FORM, XDP_BASED_FORM)

* 送信アクションは、すべての署名者が署名を完了するまで待機するのではなく、フォームが送信されると、ただちに呼び出されます。したがって、署名者に送信される Adobe Sign 契約書 PDF を送信アクションで使用したり処理したりすることはできません。(FORM_SIGN_INTEGRATION)

* 署名ステップは使用できません。(SIGNATURE_STEP)

* 検証ステップは使用できません。(VERIFY_STEP)

* **[!UICONTROL Forms Workflow に送信]**&#x200B;の送信アクションは使用できません。AEM 6.5 Forms およびそれ以前のバージョンでは、送信アクションを使用して、JEE ワークフローおよび LiveCycle ワークフローのレガシー AEM Forms にアダプティブフォームデータを送信していました。(LC_WORKFLOW_SUBMISSION)

* インタラクティブ通信機能は使用できません。 (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* メタデータのアコーディオン機能は使用できません。(METADATA_ACCORDION_FORM_CONTAINER)

* CAPTCHA コンポーネントでは、デフォルトにより Google reCAPTCHA サービスを使用して CAPTCHA を検証できるようになりました。Adobe Experience Manager を使用して CAPTCHA を検証するオプションは廃止されました。(FORMS_CAPTCHA)

* [!DNL AEM Forms] アプリは [!DNL Cloud Services] には使用できません。(AEM_FORMS_APP)

* [ドキュメントサービス](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/install-aem-forms/osgi-installation/install-configure-document-services#deployment-topology) AEM Workflows では手順を使用できません。 (WORKFLOW_DOCSERVICES)

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_guidance"
>title="実装ガイダンス"
>abstract="FORMS コードで公開された情報は、一部の機能および API を Cloud Service に対応させるために必要な置き換えなどの措置に関するガイダンスを提供できます。ヘルプまたは詳しい説明については、Adobeサポートにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 移行ユーティリティを使用して、現在の環境にあるルールスクリプトをすべて再利用可能な関数に変換します。再利用可能な関数をビジュアルルールエディターで使用することにより、引き続き、ルールスクリプトで取得した結果を利用できるようになります。(CODE_EDITOR)

* ご使用の環境でメール機能を有効（SMTP ポートを開く）にできるように、サポートチームにお問い合わせください。 デフォルトでは、送信 HTTP 接続と送信 HTTPS 接続のみが有効になっています。 (EMAIL_SERVICE_CONFIGURATION, メールステップ)

* 「**[!UICONTROL PDF のメール]**」ではなく、「**[!UICONTROL メール]**」送信アクションを使用します。「**[!UICONTROL メール]**」送信アクションでは、添付ファイルを送信し、メールにレコードのドキュメント（DoR）を添付するオプションが提供されます。(EMAIL_PDF_SUBMIT_ACTION)

* 送信されたデータには、Adobe Sign 契約書 ID が含まれています。必要に応じて、署名契約 ID を使用して署名契約PDFを取得できます。 (FORM_SIGN_INTEGRATION)

* 既存のアダプティブフォームから署名ステップを削除します。[ブラウザー内署名エクスペリエンス](https://blog.developer.adobe.com/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)を使用するようにアダプティブフォームを設定します。アダプティブフォームの送信時に、ブラウザー内で契約書に署名するための Adobe Sign 契約書が表示されます。ブラウザー内署名エクスペリエンスにより、署名をより迅速に行えるようになり、署名者にとって時間の節約になります。(SIGNATURE_STEP)

* このようなフォームをに移動する前に、既存のアダプティブFormsから検証ステップを削除します [!DNL Cloud Service] 環境。 (VERIFY_STEP)

* 既存のアダプティブフォームを編集して、次を使用できるようにします [REST エンドポイントへの送信](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#submit-to-rest-endpoint), [メールを送信](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#send-email), [フォームデータモデルを使用して送信](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#submit-using-form-data-model)、および [AEM ワークフローを起動](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#invoke-an-aem-workflow) 送信アクション。

* AEM ワークフローを作成し、既存のアダプティブフォームを編集して使用することができます [AEM ワークフロー](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#invoke-an-aem-workflow) を使用する代わりに、AEM Workflow にデータを送信する「送信アクション」 **[!UICONTROL Forms Workflowに送信]** 送信アクション。 「[!UICONTROL Forms Workflow に送信]」を使用する代わりに、カスタム送信アクションを作成して、データ、添付ファイル、またはレコードのドキュメント（DoR）を LiveCycle プロセスに送信することができます。(LC_WORKFLOW_SUBMISSION)

* インタラクティブ通信機能の提供状況については、毎月のリリースノートを参照してください。この機能が利用できるようになるまでは、インタラクティブ通信、レター、関連辞書を Cloud Service 環境に移行しないでください。(FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* メタデータのアコーディオンの代わりとなる機能はありません。フォームを Cloud Service に移行する前に、メタデータのアコーディオンをフォームから削除しておいてください。(METADATA_ACCORDION_FORM_CONTAINER)

* Adobe Experience Managerが提供する CAPTCHA サービスの代わりに、Google reCAPTCHA を使用します。 (FORMS_CAPTCHA)

* ドキュメントサービスワークフローステップを使用するAEM ワークフローモデルは移行しないでください。 また、ドキュメントサービスワークフローステップを使用するワークフローモデルにユーザーデータを送信するアダプティブ Formsを移行または更新しないでください。または、 **`Submit Action`** から [サポートされるもの](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions) フォームを移行する前に以下のことを行います。 (WORKFLOW_DOCSERVICES)

* アダプティブフォームではレスポンシブデザインが可能です。これらのフォームは、ベースとなるデバイスに基づいて外観、デザイン、インタラクティブ機能を変更します。モバイルデバイスでアダプティブフォームを引き続き使用できます。[!DNL AEM Forms] アプリの提供状況については、毎月のリリースノートを参照してください。(AEM_FORMS_APP)

* XFA ベースのアダプティブフォームのサポートは、初期設定では利用できません。XFA ベースのアダプティブフォームを使用する場合は、アドビサポートに問い合わせて、使用例と具体的な要件の詳細をお伝えください。（XFA_BASED_FORM、XDP_BASED_FORM）

連絡先 [Adobeサポート](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) 詳しい説明や懸念に対処する必要がある場合。
