---
title: Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services
description: Ten artykuł wyjaśnia sposób pobierania konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS).
author: kfend
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.form: ERSolutionImport, ERWorkspace
ms.openlocfilehash: f48dd14bc3009550d78bd71db030c172d2ef6450
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277825"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak pobrać najnowszą wersję [konfiguracji modułu raportowania elektronicznego (ER)](general-electronic-reporting.md#Configuration) z [biblioteki udostępnionych elementów](../lifecycle-services/asset-library.md) w Microsoft Dynamics Lifecycle Services (usługi LCS).

> [!IMPORTANT]
> [Zrezygnowano](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release) z używania LCS jako repozytorium do przechowywania konfiguracji raportowania elektronicznego (ER). Więcej informacji: [Regulatory Configuration Service (RCS) — wycofanie pamięci w Lifecycle Services (LCS)](../../../finance/localizations/rcs-lcs-repo-dep-faq.md).

1. Zaloguj się do aplikacji przy użyciu jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

2. Wybierz kolejno opcje **Administrowanie organizacją** &gt; **Obszary robocze** &gt; **Raportowanie elektroniczne**.
3. W obszarze **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.
4. Na kafelku **Microsoft** wybierz **Repozytoria**.

    [![Kafelek Microsoft na stronie konfiguracje lokalizacji.](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. Na stronie **Repozytoria konfiguracji** w siatce zaznacz istniejące repozytorium typu **LCS**. Jeśli to repozytorium nie jest wyświetlane w siatce, wykonaj następujące kroki:

    1. Wybierz **Dodaj**, aby dodać repozytorium.
    2. Jako typ repozytorium wybierz **LCS**.
    3. Kliknij opcję **Utwórz repozytorium**.
    4. Jeśli zostanie wyświetlony monit o autoryzację, postępuj zgodnie z instrukcjami wyświetlanymi na ekranie.
    5. Wprowadź nazwę i opis repozytorium.
    6. Wybierz przycisk **OK**, aby potwierdzić wprowadzenie nowego repozytorium.
    7. W siatce wybierz nowe repozytorium typu **LCS**.

6. Wybierz **Otwórz**, aby wyświetlić listę konfiguracji modułu ER dla wybranego repozytorium.

    [![Strona repozytorium konfiguracji.](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

    > [!TIP]
    > Jeśli występują problemy z dostępem do repozytorium usługi LCS w celu pobrania konfiguracji z biblioteki udostępnionych elementów w usłudze LCS, można pobrać konfiguracje z [repozytorium globalnego](er-download-configurations-global-repo.md).

7. W drzewie konfiguracji w lewym okienku zaznacz wymaganą konfigurację ER.
8. Na skróconej karcie **Wersje** wybierz wymaganą wersję wybranej konfiguracji ER.
9. Wybierz opcję **Importuj**, aby pobrać wybraną wersję z usługi LCS do bieżącego wystąpienia.

    > [!NOTE]
    > Przycisk **Importuj** jest niedostępny dla wersji konfiguracji ER, które już się znajdują w bieżącym wystąpieniu.

    [![Strona Repozytorium konfiguracji.](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> W zależności od ustawień ER podczas importowania konfiguracji jest sprawdzana ich poprawność. Możesz otrzymywać powiadomienia o wszelkich wykrytych problemach z niespójnością. Przed rozpoczęciem używania zaimportowanej wersji konfiguracji należy rozwiązać te problemy. Aby uzyskać więcej informacji, zobacz listę pokrewnych tematów tego artykułu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)

[Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
