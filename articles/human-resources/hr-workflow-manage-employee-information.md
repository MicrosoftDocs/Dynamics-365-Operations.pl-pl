---
title: Używanie przepływów pracy do zarządzania informacjami pracowników etatowych
description: W tym artykule wyjaśniono, jak używać przepływów pracy do zarządzania informacjami o pracownikach.
author: twheeloc
ms.date: 11/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dbbbb0ee807cb65fa4f4f9a29cc4a2b6b045b08c
ms.sourcegitcommit: 2b654e60e2553a5835ab5790db4ccfa58828fae7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750742"
---
# <a name="use-workflows-to-manage-employee-information"></a>Używanie przepływów pracy do zarządzania informacjami pracowników etatowych

[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule wyjaśniono, jak za pomocą funkcji przepływów pracy dostępnych w module Zasoby ludzkie zarządzać informacjami o pracownikach. Można na przykład skojarzyć przepływ pracy ze stanowiskiem oraz skonfigurować przepływ pracy zatwierdzania, który jest uruchamiany, gdy pracownicy zmodyfikuje swój rekord.

Funkcjonalność przepływów pracy zawarta w module Zasoby ludzkie oferuje wiele przepływów pracy do zarządzania działaniami dotyczącymi zasobów ludzkich. Ponadto są dostępne liczne opcje umożliwiające modyfikowanie konkretnych przepływów pracy i ich kojarzenie z hierarchią raportowania. Dostępne są przepływy pracy pomagające zarządzać zmianami w kilku typach informacji o pracownikach. Przepływ pracy można skojarzyć ze stanowiskiem. Następnie jeśli pracownicy zmodyfikują swoje rekordy pracowników, będzie uruchamiany przepływ pracy, który wymaga zatwierdzenia, zanim nowe informacje zostaną zapisane. Przepływy pracy są wstępnie zdefiniowane dla następujących typów informacji, aby ułatwić efektywne zarządzanie zmianami i zachować rzetelność danych pracowników:

-   Numery identyfikacyjne
-   Kursy
-   Edukacja
-   Wizerunek
-   Wypożyczone elementy
-   Doświadczenie zawodowe
-   Doświadczenie w projekcie
-   Umiejętności
-   Stanowiska zaufania
-   Akcje w module Zasoby ludzkie
-   Rejestracja na kurs

Kiedy pracownicy są zatrudniani, przenoszeni lub zwalniani, przepływ pracy może zawierać proces weryfikacji. W ten sposób w ramach przepływu pracy można sprawdzić dokument lub zdefiniować warunki czynności. Po zakończeniu procesu weryfikacji następuje finalizacja dokumentu lub czynność, a przepływ pracy przechodzi do ostatniego etapu zatwierdzania.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Kojarzenie przepływu pracy z hierarchią stanowisk

Przepływ pracy można powiązać z dowolną skonfigurowaną hierarchią stanowisk. Do marszrut przepływu pracy są używane dwa typy hierarchii: **Menedżerskie** i **Konfigurowalne**.

- Hierarchia **menedżerska** reprezentuje strukturę raportowania firmy lub organizacji. Aby uzyskać więcej informacji o tym typie hierarchii, zobacz [stanowisko przełożonego](hr-personnel-positions.md#reports-to-position).
- **Konfigurowalna** hierarchia reprezentuje hierarchię macierzową lub niestandardową. Aby uzyskać więcej informacji o tym typie hierarchii, zobacz [Relacje](hr-personnel-positions.md#relationships).

### <a name="managerial-hierarchy-example"></a>Przykład hierarchii kierowniczej

Przepływ pracy można skonfigurować w taki sposób, aby po przesłaniu przez pracownika zamówienia zakupu na nowym komputerze był on przesyłany do menedżera pracownika i kierownika poziomu pomijania. Konfigurując etap przepływu pracy, ustaw pole **Typ przypisania** na **Hierarchia**. Karta **Typ hierarchii** staje się dostępna. W tym przykładzie wybierz hierarchię **Menadżerska**.

### <a name="configurable-hierarchy-example"></a>Przygkład konfigurowalnej hierarchii

Jeśli stanowisko jest powiązane z macierzową hierarchią raportowania, można skonfigurować przepływ pracy, który kieruje wydatki na konkretny projekt do kierownika projektu zamiast do kierownika pracownika. W takim przypadku w polu **Typ przypisania** należy ustawić wartość **Hierarchia**. Następnie na karcie **Typ hierarchii** wybierz hierarchię **Konfigurowalna**. Po skonfigurowaniu przepływu pracy wybierz opcję **Powiązanie** hierarchii na stronie **Ustawienia przepływu pracy**, aby wybrać hierarchię, która ma być używana dla marszruty przepływu pracy.

> [!IMPORTANT]
> Podczas przesyłania dokumentu, transakcji lub rekordu głównego do zatwierdzania w ramach przepływu pracy do określania, kto powinien być przekierowywowany do następnego, będzie używane główne stanowisko osoby przesyłacej.

### <a name="hierarchy-setting-in-workflow-parameters"></a>Ustawienie hierarchii w parametrach przepływu pracy

1. Na stronie **Parametry przepływu** pracy przejdź do marszruty **hierarchii**.
2. Domyślnie opcja **Użyj hierarchii stanowisk** jest ustawiona na wartość **Nie**. W tym przypadku przepływ pracy będzie używać podstawowego stanowiska pracownika podczas przechodzenia do hierarchii. Ustaw opcję **Tak**, aby przepływ pracy był elementem nadrzędnym stanowiska podczas przechodzenia do hierarchii.

### <a name="additional-example"></a>Dodatkowy przykład 

Dla pracownika Grace Sturman są dwa stanowiska: konsultant i szkoleniowca. Głównym stanowiskiem dla prolongaty jest szkoleniowca. Gdy nie szkolenie nowych pracowników, może pracować z konsultingiem. Dzięki swojej głównej pozycji Grace podlega Claire, dyrektorowi ds. zasobów ludzkich. Claire podlega Charliemu. Na stanowisku konsultanta Grace ma wiele relacji po kropce, w zależności od projektu.

Firma grace tworzy reguły marszruty przepływu pracy oparte na hierarchii **konfigurowalnej** (hierarchii macierzowej/projektowej). W tej hierarchii jest używane stanowisko konsultanta Grace. Jeśli opcja **Użyj hierarchii pozycji** jest ustawiona na **Nie**, kiedy dokument jest kierowany do Grace w celu jego zatwierdzenia, przepływ pracy będzie patrzył na jej główną pozycję (trener), aby określić, gdzie dokument powinien być kierowany w następnej kolejności. W tym przypadku będzie on kierowany najpierw do Claire, a następnie do Charliego. Jeśli opcja jest ustawiona na **Tak**, a przepływ wykorzystuje **Konfigurowalną** hierarchię, przepływ będzie patrzył na pozycję konsultanta Grace i relację przynależności, aby określić, gdzie dokument powinien być kierowany w następnej kolejności.

### <a name="configure-a-human-resources-workflow"></a>Konfigurowanie przepływu pracy dla modułu Zasoby ludzkie
Aby skonfigurować podstawowy przepływ pracy uruchamiany w momencie, gdy pracownicy proszą o zmiany ich osobistych numerów identyfikacyjnych, wykonaj następujące czynności:

1.  Na stronie **Przepływy pracy modułu Zasoby ludzkie** wybierz przycisk **Nowy**.
2.  Na liście dostępnych przepływów pracy wybierz opcję **Numery identyfikacyjne**.
3.  Wybierz **Uruchom**, aby uruchomić projektanta przepływów pracy, a następnie w odpowiedzi na monit wprowadź swoją nazwę użytkownika i hasło.
4.  Przeciągnij element **Zatwierdź numer identyfikacyjny** z listy elementów przepływu pracy na kanwę projektanta.
5.  Połącz element zatwierdzania z czynnościami **Rozpocznij** i **Zakończ**.
6.  Kliknij dwukrotnie (lub kliknij dwukrotnie) **Zatwierdź element**, wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy), a następnie wybierz polecenie **Właściwości**.
7.  Wykonaj następujące kroki, aby dodać instrukcje elementu pracy:

    1.  Wybierz opcję **Przypisanie**, a następnie w polu typu przypisania wybierz opcję **Hierarchia**.
    2.  W obszarze **Hierarchia** zaznacz opcję **Konfigurowalna hierarchia**.
    3.  Dodaj warunek zatrzymania i zamknij stronę.

8.  Wykonaj wszelkie dodatkowe instrukcje.
9.  Wybierz opcję **Zapisz i zamknij**. Gdy zostanie otwarte okno dialogowe, wybierz opcję **Uaktywnij**.
10. Wybierz kolejno opcje **Zasoby ludzkie** &gt; **Stanowiska** &gt; **Typy hierarchii stanowisk**.
11. Wybierz opcję **Macierz**.
12. Dodaj przepływ pracy **Numer identyfikacyjny pracownika** do listy.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wyświetlanie zmian adresu i zarządzanie nimi](hr-personnel-view-address-changes.md) 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
