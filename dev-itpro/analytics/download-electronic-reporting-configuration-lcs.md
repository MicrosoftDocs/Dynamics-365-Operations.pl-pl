---
title: "Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services"
description: "Ten temat wyjaśnia sposób pobierania konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS)."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 9dca5dec846670da25926826f59d7bce0fa0dcea
ms.lasthandoff: 03/31/2017


---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services

Ten temat wyjaśnia sposób pobierania konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS).

Ten samouczek prowadzi przez proces pobierania najnowszej wersji konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS).

1.  Zaloguj się do programu Dynamics 365 for Operations przy użyciu jednej z następujących ról:
    -   Deweloper raportowania elektronicznego
    -   Konsultant funkcjonalny raportowania elektronicznego
    -   Administrator systemu

2.  Wybierz kolejno opcje **Administrowanie organizacją** &gt; **Raportowanie elektroniczne**.
3.  W obszarze **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.
4.  Na kafelku **Microsoft** kliknij opcję **Repozytoria**. [![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)
5.  Na stronie **Repozytoria konfiguracji** w siatce zaznacz istniejące repozytorium typu **LCS**. Jeśli to repozytorium nie jest wyświetlane w siatce, wykonaj następujące kroki:
    1.  Kliknij przycisk **Dodaj**, aby dodać nowe repozytorium.
    2.  Jako typ repozytorium wybierz **LCS**.
    3.  Kliknij opcję **Utwórz repozytorium**.
    4.  Wprowadź nazwę i opis repozytorium.
    5.  Kliknij przycisk **OK**, aby potwierdzić wprowadzenie nowego repozytorium.
    6.  W siatce wybierz nowe repozytorium typu **LCS**.

6.  Kliknij opcję **Otwórz**, aby wyświetlić listę konfiguracji modułu ER dla wybranego repozytorium. [![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)
7.  W drzewie konfiguracji w lewym okienku zaznacz wymaganą konfigurację ER.
8.  Na skróconej karcie **Wersje** wybierz wymaganą wersję wybranej konfiguracji ER.
9.  Kliknij opcję **Importuj**, aby pobrać wybraną wersję z usługi LCS do bieżącego wystąpienia programu Dynamics 365 for Operations. **Uwaga:** Przycisk **Importuj** jest niedostępny dla wersji konfiguracji ER, które już się znajdują w bieżącym wystąpieniu programu Dynamics 365 for Operations. [![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

**Uwaga:** W zależności od ustawień ER podczas importowania konfiguracji jest sprawdzana ich poprawność. Możesz otrzymywać powiadomienia o wszelkich wykrytych problemach z niespójnością. Przed rozpoczęciem używania zaimportowanej wersji konfiguracji należy rozwiązać te problemy. Aby uzyskać więcej informacji, zobacz listę pokrewnych artykułów do tego tematu.

<a name="see-also"></a>Informacje dodatkowe
--------

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)


