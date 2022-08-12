---
title: Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service
description: W tym artykule opisano sposób pobierania konfiguracji raportowania elektronicznego (ER) z globalnego repozytorium usługi Configuration service.
author: NickSelin
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 53007504f1094b69ec6578d382c451a2bf1f9059
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108927"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a>Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób pobierania [konfiguracji raportowania elektronicznego (ER)](general-electronic-reporting.md#Configuration) z globalnego repozytorium usługi Configuration service. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Microsoft Dynamics 365 Finance - Regulatory Services, Configuration service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="open-configurations-repository"></a>Otwieranie repozytorium konfiguracji

1. Zaloguj się do aplikacji Dynamics 365 Finance przy użyciu jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

2. Wybierz kolejno opcje **Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne**.
3. W obszarze **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.
3. Na kafelku **Microsoft** wybierz **Repozytoria**.

    ![Obszar roboczy raportowania elektronicznego.](./media/er-download-configurations-global-repo-er-workspace.png)

4. Na stronie **Repozytoria konfiguracji** w siatce zaznacz istniejące repozytorium typu **Globalne**. Jeśli to repozytorium nie jest wyświetlane w siatce, wykonaj następujące kroki:

    1. Wybierz **Dodaj**, aby dodać nowe repozytorium.
    2. Wybierz pozycję **Globalne** jako typ repozytorium, a następnie wybierz opcję **Utwórz repozytorium**.
    3. W przypadku wyświetlenia monitu postępuj zgodnie z instrukcjami autoryzacji.
    4. Wprowadź nazwę i opis repozytorium, a następnie kliknij przycisk **OK**, aby potwierdzić nowy wpis repozytorium.
    5. W siatce wybierz nowe repozytorium typu **Globalne**.

5. Wybierz **Otwórz**, aby wyświetlić listę konfiguracji modułu ER dla wybranego repozytorium.

    ![Strona repozytorium konfiguracji.](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a>Importowanie pojedyńczej konfiguracji

1. Na stronie **Repozytoria konfiguracji** w drzewie konfiguracje wybierz żądaną konfigurację encji.
2. Na skróconej karcie **Wersje** wybierz wymaganą wersję wybranej konfiguracji ER.
3. Wybierz **Importuj**, aby pobrać wybraną wersję z Globalnego repozytorium do bieżącego wystąpienia Finance.

    > [!NOTE]
    > Przycisk **Importuj** jest niedostępny dla wersji konfiguracji ER, które już się znajdują w bieżącym wystąpieniu Finance.

    ![Strona repozytorium konfiguracji, skrócona karta Konfiguracje.](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a>Importowanie filtrowanej konfiguracji

1. Na stronie **Repozytoria konfiguracji** w drzewie konfiguracje rozwiń skróconą kartę **Filtruj**.
2. W siatce **Znaczniki** dodaj potrzebne znaczniki.
3. W polu **Zastosowanie kraju/regionu** wybierz odpowiednie kody krajów/regionów, a następnie wybierz opcję **Zastosuj filtr**.

    > [!NOTE]
    > Na skróconej karcie **Konfiguracje** są wyświetlane wszystkie konfiguracje spełniające określone warunki wyboru.

4. Na skróconej karcie **Konfiguracje** wybierz opcję **Importuj**, aby pobrać przefiltrowane konfiguracje z repozytorium globalnego do bieżącego wystąpienia.
5. Na skróconej karcie **Konfiguracji** wybierz opcję **Resetuj filtr**, aby wyczyścić określone warunki wyboru.

    ![Strona repozytorium konfiguracji, skrócona karta Wersje, przycisk Importuj.](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> W zależności od ustawień ER podczas importowania konfiguracji jest sprawdzana ich poprawność. Możesz otrzymywać powiadomienia o wszelkich wykrytych problemach z niespójnością. Zanim będzie można użyć zaimportowanej wersji konfiguracji, należy rozwiązać problemy. Aby uzyskać więcej informacji, zobacz listę pokrewnych zasobów do tego artykułu.

> [!NOTE]
> Konfiguracje ER można skonfigurować jako zależne od innych konfiguracji. Dlatego też, wraz z wybraną konfiguracją, inne konfiguracje mogą być importowane automatycznie. Więcej informacji o zależnościach konfiguracji zawiera sekcja [Definiowanie zależności konfiguracji raportowania elektronicznego od innych składników](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

