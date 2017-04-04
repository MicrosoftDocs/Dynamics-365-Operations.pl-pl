---
title: "Czas i frekwencja w sieci sprzedaży"
description: "W tym temacie opisano scenariusze, które są obsługiwane w przypadku zarządzania modułu Czas i frekwencja w usłudze Microsoft Dynamics 365 dla operacji - sieci sprzedaży."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: eac0b85a17df33c860333c5c19d4fb58f160930f
ms.lasthandoff: 03/31/2017


---

# <a name="retail-time-and-attendance"></a>Czas i frekwencja w sieci sprzedaży

W tym temacie opisano scenariusze, które są obsługiwane w przypadku zarządzania modułu Czas i frekwencja w usłudze Microsoft Dynamics 365 dla operacji - sieci sprzedaży. 

<a name="manage-worker-setup-and-scheduling"></a>Zarządzanie ustawień pracownika i planowania
----------------------------------

### <a name="initial-configuration"></a>Pierwotna konfiguracja 

-   Włącz kreatora konfiguracji.
-   Zarejestruj pracowników jako pracowników odpowiedzialnych za rejestrację czasu.

### <a name="plan-worker-schedules"></a>Planowanie harmonogramów pracowników

-   Zastosuj profil za pomocą planowania pracy. Aby uzyskać więcej informacji, zobacz <https://technet.microsoft.com/en-us/library/aa551234.aspx>.

Aby uzyskać więcej informacji o etapach konfiguracji, zobacz <https://technet.microsoft.com/en-us/library/aa496971.aspx>.

### <a name="retail-specific-configuration"></a>Konfiguracja właściwa dla sieci sprzedaży

-   Włącz profil funkcji dla Zegara, dla pracowników, którzy mają być odpowiedzialni za rejestrację czasu. Kliknij **profile funkcji POS**&gt;**funkcje**&gt;**rejestracje czasu POS**&gt;**Włącz rejestracje czasu**.
-   Skonfiguruj grupy uprawnień w punkcie sprzedaży, aby włączyć uprawnienie Wyświetlanie wpisów zegara. To uprawnienie pozwala wyświetlać rejestracje zegara innych pracowników w danym sklepie (i w każdym innym sklepie, z którym użytkownik jest skojarzony, za pomocą książki adresowej). Można włączyć uprawnienie dla roli Menedżer, ale nie dla roli Kasjer. Kliknij **grup uprawnień punktu sprzedaży**&gt;**wyświetlanie wpisów zegara**.

## <a name="register-time"></a>Czas rejestracji
### <a name="cashier-and-non-cashier-time-registrations"></a>Rejestracje czasu dla roli Kasjer i ról innych niż Kasjer

-   W punkcie sprzedaży:
    -   Operacje rejestrowania:
        -   Zaloguj się przy użyciu operację bez użycia szuflady lub jak Nowa zmiana.
        -   Wybierz operację Zegar.
        -   Wybierz żądaną operację:
            -   Wejście
            -   Przerwa w pracy
            -   Przerwa na lunch
            -   Wyjście

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Bieżący stan</th>
    <th>Dostępne operacje</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Wejście</td>
    <td><ul>
    <li>Przerwa w pracy</li>
    <li>Przerwa na lunch</li>
    <li>Wyjście</li>
    </ul></td>
    </tr>
    <tr class="even">
    <td>Przerwa w pracy</td>
    <td>Wejście</td>
    </tr>
    <tr class="odd">
    <td>Przerwa na lunch</td>
    <td>Wejście</td>
    </tr>
    <tr class="even">
    <td>Wyjście</td>
    <td>Wejście</td>
    </tr>
    </tbody>
    </table>

    [![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)
-   Wyświetl komunikat potwierdzający i sprawdź, czy godzina aktualnego działania jest prawidłowa.
-   Dziennik:
    -   Kliknij **Dziennik**, aby wyświetlić działanie zegara.
    -   Za pomocą filtrów czasu możesz wybrać różne okna czasowe.
    -   Jeśli pracujesz w wielu lokalizacjach sklepów, widoczne są rejestracje czasu we wszystkich sklepach, w których rejestrujesz czas. Za pomocą filtra sklepu możesz wyświetlać rejestracje czas z wybranego sklepu.

<!-- -->

-   Różne strefy czasowe:
    -   W przypadku wyświetlenia czasu z innej lokalizacji (dla dziennika kasjera lub za pomocą opcji **Wyświetlanie wpisów zegara** dla menedżera) i gdy ta lokalizacja jest w innej strefie czasowej, widoczne rejestracje czasu są konwertowane na czas lokalny. Na przykład jesteś menedżera dla dwóch magazynów, jeden w Arizona, a drugi w Nevadzie. Kasjer rejestruje wyrejestrowania o godzinie 9:00 W Arizona. W tym momencie w Nevadzie jest godzina 8:00. Jeśli więc jesteś w Nevadzie i przeglądasz dane rejestracji czasu, wskazywana jest godzina 8:00.

## <a name="view-worker-time-registrations"></a>Wyświetlanie pracowników rejestracji czasu
### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Wyświetlanie rejestracji czasu pracownika i filtrowanie według sklepu lub typu aktywności

W punkcie sprzedaży:

-   Wybierz **Wyświetlanie wpisów zegara**.
-   Widać działania rejestracji czasu dla wszystkich pracowników przypisanych do tych samych sklepów, do których jesteś przypisany Ty.
-   Za pomocą filtrów typu działania i sklepu możesz filtrować rejestracje czasu.

## <a name="process-and-manage-time-registrations"></a>Przetwarzanie i zarządzanie rejestracji czasu
365 Dynamics dla operacji - detalicznych użytkownika następuje przepływ pracy, aby obliczać, zatwierdzać i przenosić rejestracje czasu do listy płac.

### <a name="primary-operations"></a>Podstawowe operacje

-   Oblicz
-   Zatwierdź
-   Prześlij do listy płac

### <a name="other-common-operations"></a>Inne częste operacje

-   Grupowe wyrejestrowania
-   Rejestrowanie nieobecności

Aby uzyskać więcej informacji na temat przetwarzania rejestracji czasu i nieobecności, zobacz <https://technet.microsoft.com/en-us/library/aa573180.aspx>.


