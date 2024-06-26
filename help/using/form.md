---
title: FORM
description: パターン検出コードのヘルプページ。
exl-id: ac28760b-b0ab-4082-b7ce-730cddc4ad83
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 100%

---

# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_overview"
>title="Forms"
>abstract="Forms コードは、AEM（Adobe Experience Manager）Forms から AEM Forms as a Cloud Service への移行に伴って生じる可能性のある問題を特定します。Cloud Service に移行する前に、考えられる影響および関連するリスクを確認し、これらの問題に対処します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-manager-pattern-detection/table-of-contents/forms#implications-and-risks" text="考えられる影響とリスク"

`FORMS` は、[!DNL Adobe Experience Manager Forms] から [!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service] への移行に関連する潜在的な問題を識別します。[!DNL Cloud Service] への移行を開始する前に、これらの問題に対処します。

次のサブタイプを利用して、様々なタイプの問題を特定することができます。

* `modified.feature`：これらの機能、アセット、または API は、Cloud Service に対応して更新、または変更されています。Cloud Service に移行する前に、移行ユーティリティを実行して、これらの機能やアセットが Cloud Service との互換性を維持できるようにします。
* `unavailable.feature`：使用環境に、Cloud Service では利用できない、あるいは Cloud Service から削除された機能やアセットが含まれています。このような機能やアセットは、Cloud Service 環境には移行しないでください。
* `unsupported.feature`：使用環境で、Cloud Service ではまだサポートされていない機能が使用されています。このような機能やアセットは、Cloud Service 環境には移行しないでください。これらの機能の提供状況については、毎月のリリースノートを参照してください。
* `unsupported.api`：使用環境に、Cloud Service ではまだサポートされていない API が一部含まれています。Cloud Service に移行する前に、コード中のこれらの API を無効にするか、別の API に置き換えるか、削除してください。これらの機能の提供状況については、毎月のリリースノートを参照してください。

一部の機能や API を Cloud Service と互換性のあるものにするために必要な置き換えやその他の処置については、[考えられる影響およびリスク](#implications-and-risks)や[考えられる解決策](#solutions)の節を参照してください。

## 考えられる影響とリスク {#implications-and-risks}

[!DNL Adobe Experience Manager Forms as a Cloud Service] への移行を開始する前に、次の問題に対処します。下記の影響とリスクに対応しておかないと、機能によっては Cloud Service 環境で期待通り動作しないものもあります。

* ルールエディター機能のうちのコードエディターの部分は使用できません。(CODE_EDITOR)

* メールのサポート（SMTP ポート）は、デフォルトで無効になっています。（EMAIL_SERVICE_CONFIGURATION）

* 「**[!UICONTROL PDF のメール]**」送信アクションは使用できません。(EMAIL_PDF_SUBMIT_ACTION)

* XFA ベースのアダプティブフォームは、まだサポートされていません。(XFA_BASED_FORM, XDP_BASED_FORM)

* 送信アクションは、すべての署名者が署名を完了するまで待機するのではなく、フォームが送信されると、ただちに呼び出されます。したがって、署名者に送信される Adobe Sign 契約書 PDF を送信アクションで使用したり処理したりすることはできません。(FORM_SIGN_INTEGRATION)

* 署名ステップは使用できません。(SIGNATURE_STEP)

* 検証ステップは使用できません。(VERIFY_STEP)

* **[!UICONTROL Forms Workflow に送信]**&#x200B;の送信アクションは使用できません。AEM 6.5 Forms およびそれ以前のバージョンでは、送信アクションを使用して、JEE ワークフローおよび LiveCycle ワークフローのレガシー AEM Forms にアダプティブフォームデータを送信していました。（LC_WORKFLOW_SUBMISSION）

* インタラクティブ通信の機能は使用できません。(FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* メタデータのアコーディオン機能は使用できません。(METADATA_ACCORDION_FORM_CONTAINER)

* CAPTCHA コンポーネントでは、デフォルトにより Google reCAPTCHA サービスを使用して CAPTCHA を検証できるようになりました。Adobe Experience Manager を使用して CAPTCHA を検証するオプションは廃止されました。（FORMS_CAPTCHA）

* [!DNL AEM Forms] アプリは [!DNL Cloud Services] には使用できません。(AEM_FORMS_APP)

* [ドキュメントサービス](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/forms/install-aem-forms/osgi-installation/install-configure-document-services#deployment-topology)のステップは、AEM ワークフローでは使用できません。(WORKFLOW_DOCSERVICES)

## 可能な解決策 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_guidance"
>title="実装ガイダンス"
>abstract="FORMS コードで公開された情報は、一部の機能および API を Cloud Service に対応させるために必要な置き換えなどの措置に関するガイダンスを提供できます。ヘルプおよび詳しい説明については、アドビサポートにお問い合わせください。"
>additional-url="https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud のサポート"

* 移行ユーティリティを使用して、現在の環境にあるルールスクリプトをすべて再利用可能な関数に変換します。再利用可能な関数をビジュアルルールエディターで使用することにより、ルールスクリプトで取得した結果を引き続き利用できるようになります。(CODE_EDITOR)

* ご使用の環境でメール（オープン SMTP ポート）機能を有効にする方法については、サポートチームにお問い合わせください。デフォルトでは、送信 HTTP と HTTPS 接続が有効になります。(EMAIL_SERVICE_CONFIGURATION, メールステップ)

* 「**[!UICONTROL PDF のメール]**」ではなく、「**[!UICONTROL メール]**」送信アクションを使用します。「**[!UICONTROL メール]**」送信アクションでは、添付ファイルを送信し、メールにレコードのドキュメント（DoR）を添付するオプションが提供されます。(EMAIL_PDF_SUBMIT_ACTION)

* 送信されたデータには、Adobe Sign 契約書 ID が含まれています。必要に応じて、Sign 契約書 ID を使用して Sign 契約書 PDF を取得できます。(FORM_SIGN_INTEGRATION)

* 既存のアダプティブフォームから署名ステップを削除します。[ブラウザー内署名エクスペリエンス](https://blog.developer.adobe.com/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)を使用するようにアダプティブフォームを設定します。アダプティブフォームの送信時に、ブラウザー内で契約書に署名するための Adobe Sign 契約書が表示されます。ブラウザー内署名エクスペリエンスにより、署名をより迅速に行えるようになり、署名者にとって時間の節約になります。(SIGNATURE_STEP)

* 既存のアダプティブフォームを [!DNL Cloud Service] 環境に移行する前に、このフォームから検証ステップを削除します。(VERIFY_STEP)

* 「[REST エンドポイントに送信](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#submit-to-rest-endpoint)」、「[メールを送信](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#send-email)」、「[フォームデータモデルを使用して送信](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#submit-using-form-data-model)」、「[AEM ワークフローを起動](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#invoke-an-aem-workflow)」の各送信アクションを使用するように、既存のアダプティブフォームを編集します。

* AEM ワークフローを作成し、既存のアダプティブフォームを編集して、「**[!UICONTROL Forms Workflow に送信]**」送信アクションを使用する代わりに、「[AEM ワークフロー](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#invoke-an-aem-workflow)」送信アクションを使用してデータを AEM ワークフローに送信できます。「[!UICONTROL Forms Workflow に送信]」を使用する代わりに、カスタム送信アクションを作成して、データ、添付ファイル、またはレコードのドキュメント（DoR）を LiveCycle プロセスに送信することができます。（LC_WORKFLOW_SUBMISSION）

* インタラクティブ通信機能の提供状況については、毎月のリリースノートを参照してください。この機能が利用できるようになるまでは、インタラクティブ通信、レター、関連辞書を Cloud Service 環境に移行しないでください。(FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* メタデータのアコーディオンの代わりとなる機能はありません。フォームを Cloud Service に移行する前に、メタデータのアコーディオンをフォームから削除しておいてください。(METADATA_ACCORDION_FORM_CONTAINER)

* Adobe Experience Manager で提供される CAPTCHA サービスの代わりに、Google reCAPTCHA を使用します。（FORMS_CAPTCHA）

* ドキュメントサービスワークフローステップを使用する AEM ワークフローモデルには移行しないでください。また、フォームを移行する前に、ドキュメントサービスワークフローステップを使用するワークフローモデルにユーザーデータを送信するアダプティブフォームを移行または更新したり、`Submit Action` を[サポート対象](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions)に変更したりしないでください。(WORKFLOW_DOCSERVICES)

* アダプティブフォームではレスポンシブデザインが可能です。これらのフォームは、ベースとなるデバイスに基づいて外観、デザイン、インタラクティブ機能を変更します。モバイルデバイスでアダプティブフォームを引き続き使用できます。[!DNL AEM Forms] アプリの提供状況については、毎月のリリースノートを参照してください。(AEM_FORMS_APP)

* XFA ベースのアダプティブフォームのサポートは、初期設定では利用できません。XFA ベースのアダプティブフォームを使用する場合は、アドビサポートに問い合わせて、使用例と具体的な要件の詳細をお伝えください。（XFA_BASED_FORM、XDP_BASED_FORM）

詳しい説明や懸念事項の対応については、[アドビサポート](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
