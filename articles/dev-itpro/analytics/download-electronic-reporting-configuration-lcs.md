---
title: "Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services"
description: "Ten temat wyjaśnia sposób pobierania konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1a4e8c25fb65b35a52a0d1bc0f1a745c06ca53ab
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services

[!include [banner](../includes/banner.md)]

Ten temat wyjaśnia sposób pobierania konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS).

Ten samouczek prowadzi przez proces pobierania najnowszej wersji konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS).

1.  Zaloguj się do programu Finance and Operations przy użyciu jednej z następujących ról:
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
    4. W przypadku wyświetlenia monitu postępuj zgodnie z instrukcjami autoryzacji.
    5.  Wprowadź nazwę i opis repozytorium.
    6.  Kliknij przycisk **OK**, aby potwierdzić wprowadzenie nowego repozytorium.
    7.  W siatce wybierz nowe repozytorium typu **LCS**.

6.  Kliknij opcję **Otwórz**, aby wyświetlić listę konfiguracji modułu ER dla wybranego repozytorium. [![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)
7.  W drzewie konfiguracji w lewym okienku zaznacz wymaganą konfigurację ER.
8.  Na skróconej karcie **Wersje** wybierz wymaganą wersję wybranej konfiguracji ER.
9.  Kliknij opcję **Importuj**, aby pobrać wybraną wersję z usługi LCS do bieżącego wystąpienia programu Finance and Operations. **Uwaga:** Przycisk **Importuj** jest niedostępny dla wersji konfiguracji ER, które już się znajdują w bieżącym wystąpieniu programu Finance and Operations. [![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

**Uwaga:** W zależności od ustawień ER podczas importowania konfiguracji jest sprawdzana ich poprawność. Możesz otrzymywać powiadomienia o wszelkich wykrytych problemach z niespójnością. Przed rozpoczęciem używania zaimportowanej wersji konfiguracji należy rozwiązać te problemy. Aby uzyskać więcej informacji, zobacz listę pokrewnych artykułów do tego tematu.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie raportowania elektronicznego](general-electronic-reporting.md)




