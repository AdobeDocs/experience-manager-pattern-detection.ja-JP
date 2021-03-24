---
title: INST
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---


# INST {#inst}

インストール済みアーティファクト

## 背景 {#background}

`INST` お客様がAEMにインストールしたカスタムおよびサードパーティのパッケージおよびバンドルを識別します。これらは、システムの状態をアップグレード作業の一般的な範囲に特定するのに役立ちます。

パッケージの複数のバージョンがインストールされている場合は、最新バージョンのみが報告されます。

検出されたパッケージとバンドルは、AEM向けにCloud Serviceとして最適化されていない場合があります。 サードパーティ製パッケージは、AEMとの互換性を確保するために、Cloud Serviceとして作成者またはAdobeとの間で検証を行う必要があります。

サブタイプは、異なる種類の情報を識別するために使用されます。

* `custom.bundle`:AEMにインストールされたバンドル。
* `custom.package`:AEMにインストールされたパッケージです。

## 可能性のある影響およびリスク {#implications-and-risks}

* CRX Package Managerを使用したサードパーティパッケージのインストールは、AEMではCloud Serviceとして実行できません。
* サードパーティパッケージに依存するアプリケーションは、AEMをCloud Serviceとして正しく機能するように展開しないと、期待どおりに動作しない場合があります。
* サードパーティベンダーパッケージは、AEM向けにクラウドサービスとして最適化されていない場合、意図しない動作を引き起こす可能性があります。

## 可能な解決策 {#solutions}

* サードパーティパッケージは、Cloud Manager [展開プロセス](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html#deployment-process)を使用して、プロジェクトの一部としてAEMに展開する必要があります。
* AEM用のプロジェクトにサードパーティパッケージ[をCloud Serviceとして埋め込む方法を確認します。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embedding-3rd-party-packages)
* サードパーティパッケージは、Cloud Service[開発](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)および[パッケージ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html)のガイドラインとしてAEMに準拠する必要があります。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst)プロジェクトを見直し、[INST違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)がどのように修正され、AEMとの互換性をCloud Serviceとして持つかを理解します。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
