---
title: URC
description: パターン検出コードのヘルプページ
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 3%

---


# URC {#urc}

サポートされていない実行モードの構成

## 背景 {#background}

`URC` は、AEMでCloud Serviceとしてサポートされていないrunmode名に基づく設定の使用を識別します。

## 可能性のある影響およびリスク {#implications-and-risks}

* Cloud ServiceとしてAEMの実行モードで使用できる名前のセットは限られています。
* サポートされていない実行モード名に基づく設定は、AEMにCloud Serviceとして展開した場合に何も起こりません。

## 可能な解決策 {#solutions}

* この設定の使用を確認し、必要かどうかを判断します。
* サポートされている[runmode names](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes)のいずれかを使用するように設定の名前を変更し、[runmode resolution guidelines](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution)に従います。
* [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)プロジェクトを見直し、[URC違反](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)をCloud Serviceとして修正し、AEMと互換性を持たせる方法を理解します。
* 詳しい説明を入手したり、懸念事項に対処するには、[AEMサポートチーム](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
