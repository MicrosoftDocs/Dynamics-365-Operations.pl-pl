---
title: Zarządzanie czasem i frekwencją w module Retail
description: W tym temacie opisano scenariusze obsługiwane w zakresie zarządzania czasem i frekwencją w module Dynamics 365 Commerce.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: cca5e3232450e75f931a621b278c134129fc745c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023703"
---
# <a name="time-and-attendance-management-in-retail"></a>Zarządzanie czasem i frekwencją w module Retail

[!include [banner](includes/banner.md)]

W tym temacie opisano scenariusze obsługiwane w zakresie zarządzania czasem i frekwencją w module Dynamics 365 Commerce.

## <a name="manage-worker-setup-and-scheduling"></a>Zarządzanie ustawieniami i planowaniem pracowników

### <a name="initial-configuration"></a>Pierwotna konfiguracja 

- Włącz kreatora konfiguracji.
- Zarejestruj pracowników jako pracowników odpowiedzialnych za rejestrację czasu.

### <a name="plan-worker-schedules"></a>Planowanie harmonogramów pracowników

- Zastosuj profil za pomocą planowania pracy. Aby uzyskać więcej informacji, zobacz [Stosowanie profilu poprzez planowanie pracy](https://technet.microsoft.com/library/aa551234.aspx).

Uzyskać informacje dotyczące kroków konfiguracji, zobacz [Konfigurowanie modułu Czas i frekwencja](https://technet.microsoft.com/library/aa496971.aspx).

### <a name="commerce-specific-configuration"></a>Konfiguracja usług określonych dla Commerce

- Włącz profil funkcji dla Zegara, dla pracowników, którzy mają być odpowiedzialni za rejestrację czasu. Kliknij kolejno opcje **Profile funkcji punktu sprzedaży** &gt; **Funkcje** &gt; **Rejestracje czasu w punkcie sprzedaży** &gt; **Włącz rejestracje czasu**.
- Skonfiguruj grupy uprawnień w punkcie sprzedaży, aby włączyć uprawnienie Wyświetlanie wpisów zegara. To uprawnienie pozwala wyświetlać rejestracje zegara innych pracowników w danym sklepie (i w każdym innym sklepie, z którym użytkownik jest skojarzony, za pomocą książki adresowej). Można włączyć uprawnienie dla roli Menedżer, ale nie dla roli Kasjer. Kliknij kolejno opcje **Grupy uprawnień punktu sprzedaży** &gt; **Wyświetlanie wpisów zegara**.

## <a name="register-time"></a>Czas rejestracji

### <a name="cashier-and-non-cashier-time-registrations"></a>Rejestracje czasu dla roli Kasjer i ról innych niż Kasjer

- W punkcie sprzedaży:

    - Operacje rejestrowania:

        - Zaloguj się przy użyciu operację bez użycia szuflady lub jak Nowa zmiana.
        - Wybierz operację Zegar.
        - Wybierz żądaną operację:

            - Wejście
            - Przerwa w pracy
            - Przerwa na lunch
            - Wyjście

        <table>
        <thead>
        <tr>
        <th>Bieżący stan</th>
        <th>Dostępne operacje</th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td>Wejście</td>
        <td>
        <ul>
        <li>Przerwa w pracy</li>
        <li>Przerwa na lunch</li>
        <li>Wyjście</li>
        </ul>
        </td>
        </tr>
        <tr>
        <td>Przerwa w pracy</td>
        <td>Wejście</td>
        </tr>
        <tr>
        <td>Przerwa na lunch</td>
        <td>Wejście</td>
        </tr>
        <tr>
        <td>Wyjście</td>
        <td>Wejście</td>
        </tr>
        </tbody>
        </table>

        [![Stany zegara](./media/timeclockstates.png)](./media/timeclockstates.png)

- Wyświetl komunikat potwierdzający i sprawdź, czy godzina aktualnego działania jest prawidłowa.
- Dziennik:

    - Kliknij **Dziennik**, aby wyświetlić działanie zegara.
    - Za pomocą filtrów czasu możesz wybrać różne okna czasowe.
    - Jeśli pracujesz w wielu lokalizacjach sklepów, widoczne są rejestracje czasu we wszystkich sklepach, w których rejestrujesz czas. Za pomocą filtra sklepu możesz wyświetlać rejestracje czas z wybranego sklepu.

- Różne strefy czasowe:

    - W przypadku wyświetlenia czasu z innej lokalizacji (dla dziennika kasjera lub za pomocą opcji **Wyświetlanie wpisów zegara** dla menedżera) i gdy ta lokalizacja jest w innej strefie czasowej, widoczne rejestracje czasu są konwertowane na czas lokalny. Załóżmy, że zarządzasz dwoma sklepami — w Arizonie i Nevadzie. Kasjer rejestruje przyjście do pracy o godzinie 9:00 w Arizonie. W tym momencie w Nevadzie jest godzina 8:00. Jeśli więc jesteś w Nevadzie i przeglądasz dane rejestracji czasu, wskazywana jest godzina 8:00.

## <a name="view-worker-time-registrations"></a>Wyświetlanie rejestracji czasu pracownika

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Wyświetlanie rejestracji czasu pracownika i filtrowanie według sklepu lub typu aktywności

W punkcie sprzedaży:

- Wybierz **Wyświetlanie wpisów zegara**.
- Widać działania rejestracji czasu dla wszystkich pracowników przypisanych do tych samych sklepów, do których jesteś przypisany Ty.
- Za pomocą filtrów typu działania i sklepu możesz filtrować rejestracje czasu.

## <a name="process-and-manage-time-registrations"></a>Przetwarzanie rejestracji czasu i zarządzanie nimi

Użytkownik usługi Commerce wykonuje procedurę obliczania, zatwierdzania i przesłania rejestracji czasu do listy płac.

### <a name="primary-operations"></a>Podstawowe operacje

- Oblicz
- Zatwierdź
- Prześlij do listy płac

### <a name="other-common-operations"></a>Inne częste operacje

- Grupowe wyrejestrowania
- Rejestrowanie nieobecności

Aby uzyskać więcej informacji na temat procesu rejestracji czasu i obecności, zobacz [Przetwarzanie rejestracji czasu i frekwencji](https://technet.microsoft.com/library/aa573180.aspx).
