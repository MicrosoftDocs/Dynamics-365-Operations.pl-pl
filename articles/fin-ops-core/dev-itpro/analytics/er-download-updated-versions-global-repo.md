---
title: Importowanie zaktualizowanych wersji konfiguracji programu ER
description: W tym temacie opisano sposób importowania zaktualizowanych wersji konfiguracji raportowania elektronicznego (ER) z globalnego repozytorium usługi Configuration service.
author: NickSelin
ms.date: 06/09/2020
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
ms.openlocfilehash: 724048991fc8864ef72a5155af66b9c709f4b875
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893963"
---
# <a name="import-updated-versions-of-er-configurations"></a>Importowanie zaktualizowanych wersji konfiguracji programu ER

[!include [banner](../includes/banner.md)]

[Repozytoria](general-electronic-reporting.md#Repository) raportowania elektronicznego (ER) są używane do udostępniania [konfiguracji ER](general-electronic-reporting.md#Configuration). Można [importować](download-electronic-reporting-configuration-lcs.md) konfiguracjeER z różnych repozytoriów do danego wystąpienia rozwiązania Microsoft Dynamics 365 Finance. Podczas importowania konfiguracji ER [dostawcy konfiguracji](general-electronic-reporting.md#Provider) mogą publikować nowe [wersje](general-electronic-reporting.md#component-versioning) repozytoriów, tak aby można je było udostępniać.

W tym temacie opisano sposób importowania zaktualizowanych wersji konfiguracji ER z globalnego repozytorium usługi Configuration service. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="review-the-available-updated-versions"></a>Przejrzyj dostępne zaktualizowane wersje

1. Zaloguj się do programu Finance przy użyciu jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Import aktualizacji wersji konfiguracji**.

    ![Strona lokalizacji konfiguracji](./media/er-download-updated-versions-global-repo1.png)

4. W oknie dialogowym **Importowanie aktualizacji wersji konfiguracji ER** w polu **Tryb uruchamiania** wybierz opcję **Wyświetl tylko dostępne aktualizacje**. Następnie wybierz opcję **OK**. 

    ![Pole tryb uruchamiania ustawione w taki sposób, aby pokazywać tylko dostępne aktualizacje](./media/er-download-updated-versions-global-repo2.png)

5. Przejrzyj odebrane komunikaty. Komunikaty te zawierają następujące informacje na temat konfiguracji ER w bieżącym wystąpieniu Finance oraz w jaki sposób odnoszą się one do zawartości repozytorium globalnego:

    - Łączna liczba konfiguracji ER
    - Konfiguracje ER, które nie znajdują się w repozytorium globalnym
    - Konfiguracje ER, dla których najnowsza wersja jest już dostępna w bieżącym wystąpieniu Finance (aby wyświetlić pełną listę tych konfiguracji ER, należy wybrać łącze **Szczegóły wiadomości**).

        ![„Najnowsze wersje następujących konfiguracji zostały już zaimportowane” – komunikat i jego szczegóły](./media/er-download-updated-versions-global-repo3.png)

    - Konfiguracje ER, dla których najnowsza wersja jest już dostępna w repozytorium globalnym i które mogą być zaimportowane do bieżącego wystąpienia Finance (aby wyświetlić pełną listę tych konfiguracji ER, należy wybrać łącze **Szczegóły wiadomości**).

        ![„Dostępne aktualizacje” – komunikat i jego szczegóły](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a>Importowanie dostępnych wersji aktualizacji

1. Zaloguj się do programu Finance przy użyciu jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Import aktualizacji wersji konfiguracji**.
4. W oknie dialogowym **Importowanie wersji konfiguracji raportowania elektronicznego** w polu **Tryb uruchamiania** wybierz opcję **Importuj najnowsze aktualizacje**, aby zaimportować najnowsze wersje konfiguracji ER z repozytorium globalnego do bieżącego wystąpienia Finance.
5. Aby zaplanować zadanie wsadowe importowania, na skróconej karcie **Uruchom w tle** ustaw wartość opcji **Przetwarzanie wsadowe** na **Tak**. Jeśli chcesz okresowo powtarzać import, skonfiguruj wymagany cykl.

    ![Pole tryb uruchamiania ustawione na importowanie najnowszych aktualizacji](./media/er-download-updated-versions-global-repo5.png)

6. Kliknij przycisk **OK**.
7. Aby dowiedzieć się, jakie wersje konfiguracji zostały zaimportowane, wykonaj jedną z następujących czynności:

    - Jeśli import zostanie uruchomiony interaktywnie zamiast używania zadania wsadowego, należy przejrzeć otrzymane komunikaty.

        ![Komunikaty odebrane podczas interaktywnego przebiegu importu](./media/er-download-updated-versions-global-repo6.png)

    - W przypadku uruchomienia operacji importowania w trybie wsadowym należy wykonać następujące kroki:

        1. Wybierz kolejno opcje **Wspólne** \> **Zapytania** \> **Zadania wsadowe** \> **Moje zadania wsadowe**.
        2. Znajdź i zaznacz zadanie **Importowania wersji konfiguracji raportowania elektronicznego**, a następnie w okienku akcji na karcie **Zadanie wsadowe** wybierz opcję **Historia zadań wsadowych**, aby wyświetlić historię zadań.
        3. Na stronie **Historia zadań wsadowych** wybierz pozycję **Dziennik**. Następnie w odebranej wiadomości wybierz łącze **Szczegóły komunikatu**, aby wyświetlić dziennik zadań.

        ![Dziennik zadań](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> Nie zaleca się planowania cyklicznego zadania wsadowego w celu zaimportowania zaktualizowanych wersji konfiguracji ER bezpośrednio z repozytorium globalnego do środowiska produkcyjnego, ponieważ importowane wersje są natychmiast dostępne do użycia. Zamiast tego należy użyć tej metody w celu wdrożenia wersji konfiguracji systemu w środowisku piaskownicy. Następnie można je ocenić w środowisku piaskownicy przed wdrożeniem w środowisku produkcyjnym.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- [Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]