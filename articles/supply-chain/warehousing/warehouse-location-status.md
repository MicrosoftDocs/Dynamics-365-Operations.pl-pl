---
title: Stan lokalizacji w magazynie
description: Ten temat stanowi przegląd funkcji stanu lokalizacji w magazynie.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 31216c24f54f22ec928eb143d4a913aabcd50cf8
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435604"
---
# <a name="warehouse-location-status"></a>Stan lokalizacji w magazynie

[!include [banner](../includes/banner.md)]

Rozwiązanie Microsoft Dynamics 365 Supply Chain Management oferuje kilka pól lokalizacji, które zapewniają elastyczność podczas pracy z lokalizacjami i zarządzania nimi. Istnieje możliwość uwzględnienia stanu lokalizacji w kwerendzie dyrektywy lokalizacji w celu zapewnienia lepszej kontroli nad przepływem magazynowym.

Poniższe cztery pola na stronie **Lokalizacje** śledzą informacje o bieżącym stanie lokalizacji. Te pola umożliwiają kierownikom magazynu przegląd stanu lokalizacji magazynów. Umożliwiają także zaawansowane raportowanie i filtrowanie.

- **Kod towaru** – pozycja aktualnie w lokalizacji. Jeśli lokalizacja zawiera wiele towarów, pole to jest puste.
- **Data i godzina ostatniego działania** – sygnatura czasowa ostatniej transakcji magazynowej, która została wykonana w odniesieniu do tej lokalizacji.
- **Data wieku** – Data, kiedy zapasy w lokalizacji zostały wprowadzone do magazynu. Ta wartość jest obliczana na podstawie daty wiekowania numeru identyfikacyjnego. Jest ona dokładna w przypadku lokalizacji, w której numer identyfikacyjny jest śledzony, ale może być niedokładna w przypadku lokalizacji, dla których nie jest śledzony numer identyfikacyjny.
- **Stan lokalizacji** – stan lokalizacji. Możliwe są cztery wartości:

    - **Nieokreślony** – profil lokalizacji nie może śledzić stanu. W związku z tym bieżący stan jest nieznany.
    - **Puste** – obecnie w tej lokalizacji nie ma żadnych zapasów.
    - **Pobieranie** – transakcje wychodzące zostały wykonane w odniesieniu do lokalizacji, ponieważ była ona ostatnio pusta.
    - **Magazyn** – Tylko transakcje przychodzące zostały wykonane w odniesieniu do lokalizacji, ponieważ była ona ostatnio pusta.

## <a name="turn-on-the-warehouse-location-status-feature"></a>Włącz funkcję stanu dodatkowej strefy lokalizacji w magazynie

Aby móc używać funkcji *Status lokalizacji magazynu*, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Stan strefy lokalizacji w magazynie*

## <a name="set-up-warehouse-location-status"></a>Ustawianie stanu lokalizacji w magazynie

### <a name="prepare-the-sample-data-that-is-required-for-the-example-scenario"></a>Przygotuj przykładowe dane wymagane dla scenariusza przykładowego

Przed rozpoczęciem pracy nad scenariuszem należy aktywować przykładowe dane i skonfigurować funkcję zgodnie z opisem w tej sekcji. Aby wykonać przykładowy scenariusz, należy skorzystać z aplikacji magazynowej lub emulatora opartego na przeglądarce. Podane tutaj kroki korzystają z aplikacji magazynowej. Kroki dla emulatora opartego na przeglądarce są podobne.

#### <a name="use-the-usmf-legal-entity"></a>Użyj firmy USMF

Aby pracować z tymi przykładowymi scenariuszami przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

#### <a name="set-up-location-profiles"></a>Ustaw profile lokalizacji

Przykładowy scenariusz wymaga przygotowania dwóch profilów lokalizacji.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
1. Wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.
1. Wybierz profil **BULK-06**.
1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Włącz przedmiot w lokalizacji:** Ustaw wartość _Tak_ dla tej opcji.
    - **Włącz datę i godzinę aktywności lokalizacji:** Ustaw wartość tej opcji na _Tak_.
    - **Włącz stan lokalizacji:** Ustaw wartość _Tak_ dla tej opcji.

    Te opcje kontrolują, czy pola odwołania w danej lokalizacji są aktywne.

1. Powtórz kroki od 3 do 4 dla profilu **PICK-06**.

> [!NOTE]
> Jeśli parametry profilu lokalizacji (**Włącz obsługę towaru w lokalizacji**, **Włącz aktywności lokalizacji**, **Włącz obsługę stanu lokalizacji**) są ustawione na *Tak*, system natychmiast zaktualizuje odpowiednie lokalizacje, wykonując *Sprawdzane spójności stanu lokalizacji w magazynie*.

### <a name="scenario"></a>Scenariusz

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Wybierz pozycję **Nowy**.
1. W oknie dialogowym **Tworzenie zamówienia zakupu**, na skróconej karcie **Dostawcy**, w polu **Konto dostawcy** wybierz pozycję *104*.
1. Na skróconej karcie **Ogólne** w polu **Magazyn** wybierz wartość *61*.
1. Kliknij przycisk **OK**.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera pusty wiersz w siatce **Wiersze zamówienia kupna**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** _A0002_
    - **Ilość:** _5_

1. W okienku akcji na karcie **Zakup**, w grupie **Akcje** kliknij **Potwierdź**, aby potwierdzić zamówienie zakupu.
1. Na urządzeniu przenośnym przejdź do **Przychodzące \> Przyjęcia zakupu**.
1. Zaznacz pole **PONUM**, a następnie wprowadź numer zamówienia zakupu i potwierdź wybór.
1. Zaznacz pole **POZYCJA**, a następnie wprowadź *A0002* jako numer zamówienia zakupu i potwierdź wybór.
1. Na stronie **ILOŚĆ** wprowadź *5* jako ilość i potwierdź.

    Można wprowadzić ilość na dwa sposoby:

    - Wybierz przycisk znak plus (**+**) lub znak minus (**–**), aby dodać lub odjąć wartość liczbową.
    - Aby otworzyć konsolę numeryczną, należy wybrać puste pole między przyciskami znaku plus (**+**) i minus (**–**).

1. Potwierdź wybór numeru pozycji *A0002* i ilość *5*. W dolnej części strony pojawi się komunikat „Praca wykonana”.
1. Wybierz przycisk menu (niekiedy nazywany przyciskiem hamburger lub hamburgerem) w prawym górnym rogu, a następnie wybierz opcję **Anuluj**, aby zamknąć **Odbiór zakupu** i powrócić do menu **Przychodzące**.
1. Na stronie zamówienie zakupu wybierz **Szczegóły pracy** powyżej siatki **Wiersze zamówienia zakupu**.
1. Na karcie **Ogólne** zwróć uwagę na **Identyfikator pracy** i wartość **Docelowego numeru identyfikacyjnego**, które zostały utworzone.
1. W sekcji **Wiersze** zwróć uwagę na wartości **Lokalizacji** dla typów pracy *Pobranie* i *Umieszczenie*.
1. Na urządzeniu przenośnym przejdź do **Przychodzące \> Umieszczenie zakupu**.
1. Zaznacz pole **ID**, a następnie wprowadź numer identyfikacyjny pracy i potwierdź wybór.
1. Jeszcze raz potwierdź, aby ukończyć wpis *Pobrania*.
1. Kliknij przycisk menu w prawym górnym rogu strony, wybierz **Zrobione**, aby zakończyć zlecenie pracy *Pobierz*.
1. Zanotuj lokalizację umieszczenia, a następnie ją potwierdź. W dolnej części strony pojawi się komunikat „Praca wykonana”.
1. Wybierz przycisk menu w prawym górnym rogu, a następnie wybierz opcję **Anuluj**, aby zamknąć **Umieszczenie zakupu** i powrócić do menu **Przychodzące**.
1. Wybierz przycisk **Wstecz**, aby powrócić do menu głównego.
1. Korzystając z Dynamics 365 Supply Chain Management, wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.
1. Filtruj w **Lokalizacji** i wprowadź lokalizację umieszczenia ze zlecenia pracy zamówienia zakupu. Powinny zostać wyświetlone następujące wyniki:

    - W kolumnie **Stan lokalizacji** jest wyświetlana wartość *Magazynu*, ponieważ ostatnia transakcja w tej lokalizacji to umieszczenie.
    - W kolumnie **Kod towaru** wyświetlana jest wartość *A0002*, ponieważ dany towar został odebrany i wprowadzony do lokalizacji.
    - Kolumna **Data i godzina ostatniej aktywności** zawiera sygnaturę czasową daty i godziny zakończenia pracy w lokalizacji.

1. Na urządzeniu przenośnym przejdź do obszaru **Jakość \> Przeniesienie**.
1. Zaznacz pole **LOC/LP** i wprowadź lokalizację, którą zapisano w poprzednich krokach.
1. Potwierdź wyświetlane informacje. Zanotuj wygenerowany numer identyfikacyjny.
1. Na ekranie **Do informacji** wybierz pole **LOK/NUMID/** i wprowadź *06A07R2S1B* jako lokalizację, do której ma zostać przeniesiony towar.
1. Na ekranie **Do informacji** należy potwierdzić wartość **NUMID** (identyfikator docelowego numeru identyfikacyjnego), która jest generowana automatycznie. W dolnej części strony pojawi się komunikat „Praca wykonana”.
1. Wybierz przycisk menu w prawym górnym rogu, a następnie wybierz opcję **Anuluj**, aby zamknąć **Przeniesienie** i powrócić do menu **Zarządzanie jakością**.
1. Wybierz przycisk **Wstecz**, aby powrócić do menu głównego.
1. Korzystając z Dynamics 365 Supply Chain Management, wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.
1. Odśwież stronę **Lokalizacje** i ponownie wyświetl oryginalną lokalizację umieszczenia. Zauważ, że pole **Stan lokalizacji** jest ustawione na *Puste*, a kolumna **Kod towaru** też jest pusta.
1. Wyświetl rekord lokalizacji *06A07R2S1B* i sprawdź, czy wartość **Stan** zmieniła się na *Magazyn*, a pola **Kod towaru** i **Data ostatniego działania** zostały zaktualizowane.
1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowy**.
1. W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz *US-002*.
1. W polu **Magazyn** wybierz wartość *61*.
1. Kliknij przycisk **OK**.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera pusty wiersz w siatce w siatce **Wiersze zamówienia kupna**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** _A0002_
    - **Ilość:** _1_

1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja** wybierz **Rezerwacja partii** w celu zarezerwowania wiersza zamówienia. Następnie kliknij przycisk **Zamknij** – (**X**), znajdujący się w prawym górnym rogu, aby zamknąć stronę.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.
1. W sekcji **Wiersze zamówienia sprzedaży**, w menu **Magazyn**, wybierz **Szczegóły pracy**.
1. Umożliwia skopiowanie wartości **Identyfikatora pracy**, która została utworzona.
1. Na urządzeniu przenośnym przejdź do opcji **Wychodzące \> Pobieranie sprzedaży**.
1. Zaznacz pole **ID**, a następnie wprowadź wcześniej zapisany numer identyfikacyjny pracy i potwierdź wybór.
1. W przypadku **Zamówień sprzedaży: Pobranie**, pole **LOC** sugeruje lokalizację pobrania jako lokalizację umieszczenia utworzoną wcześniej. Zanotuj wartość lokalizacji.
1. Zaznacz pole **LOC**, a następnie wprowadź lokalizację i potwierdź wybór.
1. Zaznacz pole **NUMID**, wprowadź numer identyfikacyjny, który został zanotowany podczas działania dotyczącego przeniesienia, i potwierdź.
1. Zaznacz pole **Element**, a następnie wprowadź *A0002* jako numer zamówienia zakupu i potwierdź wybór.
1. Na stronie **ILOŚĆ** wprowadź *1* jako ilość i potwierdź.

    Można wprowadzić ilość na dwa sposoby:

    - Wybierz przycisk znak plus (**+**) lub znak minus (**–**), aby dodać lub odjąć wartość liczbową.
    - Aby otworzyć konsolę numeryczną, należy wybrać puste pole między przyciskami znaku plus (**+**) i minus (**–**).

1. Zaznacz pole **DOCELOWE LP**, wprowadź zdefiniowany przez użytkownika identyfikator numeru identyfikacyjnego i potwierdź.
1. Jeszcze raz potwierdź, aby ukończyć zlecenie pracy pobrania. W dolnej części strony pojawi się komunikat „Praca wykonana”.
1. Wybierz przycisk menu w prawym górnym rogu, a następnie wybierz opcję **Anuluj**, aby zakończyć akcję pobrania i powrócić do menu **Wychodzące**.
1. Korzystając z Dynamics 365 Supply Chain Management, wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.
1. Filtruj w **Lokalizacji** i wprowadź lokalizację pobrania ze zlecenia pracy zamówienia sprzedaży.
1. Należy zauważyć, że pole **Stan lokalizacji** dla lokalizacji, z której pobrano dane z zamówienia sprzedaży, jest obecnie ustawione na *Pobranie*, a pole **Data i godzina ostatniego działania** zostało zaktualizowane.

> [!NOTE]
> Pola lokalizacji są aktualizowane tylko przez transakcje magazynowe. Jeśli zapasy są przenoszone przy użyciu arkusza lub procesów innych niż procesy WHS, pola nie zostaną zaktualizowane.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]