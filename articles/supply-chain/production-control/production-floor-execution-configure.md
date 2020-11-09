---
title: Konfigurowanie interfejsu wykonania hal produkcyjnych
description: W tym temacie opisano sposób tworzenia jednej lub większej liczby konfiguracji dla interfejsu wykonywania pomieszczenia produkcyjnego. Po otwarciu interfejsu wykonania produkcji system automatycznie ładuje wybraną konfigurację i filtr zadania, które są właściwe dla przeglądarki i urządzenia. W konfiguracji ustawiane są zasady, które muszą być dostępne dla określonego użycia.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: cf58a7d851577854d08bad70cff69794c3841a2d
ms.sourcegitcommit: 9dd2d38e76d4d93171315ec319e6ce7d51d4e6c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2020
ms.locfileid: "4012501"
---
# <a name="configure-the-production-floor-execution-interface"></a>Konfigurowanie interfejsu wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Pracownicy hali produkcyjnej używają interfejsu wykonywania hali produkcyjnej do rejestrowania swojej codziennej pracy, na przykład kiedy rozpoczynają pracę, zgłaszają opinie o zadaniach, rejestrują czynności pośrednie i zgłaszają nieobecności. Te rejestracje stanowią podstawę śledzenia postępu i kosztu zleceń produkcyjnych oraz obliczania podstawy wypłat dla pracowników.

Po otwarciu interfejsu wykonania produkcji system automatycznie ładuje wybraną konfigurację i filtr zadania, które są właściwe dla przeglądarki i urządzenia. W konfiguracji ustawiane są zasady, które muszą być dostępne dla określonego użycia. Oto kilka przykładów użycia:

- W przypadku urządzenia w korytarzu w firmie pracownicy zarejestrują się w momencie wejścia do biura i logują się przed wyjściem z pracy.
- Na urządzeniu w hali operatorzy maszyn rejestrują, kiedy rozpoczynają i kończą pracę. Rejestrują również przerwy i czynności pośrednie.

W tym temacie opisano różne opcje konfigurowania urządzeń karty zadań.

## <a name="turn-on-new-features-in-feature-management"></a>Włącz nowe funkcje w zarządzaniu funkcjami

Niektóre z ustawień opisanych w tym temacie muszą być włączone w systemie, zanim są dostępne dla użytkownika. Strona [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) umożliwia włączenie w razie potrzeby wszelkich lub wszystkich wymienionych poniżej funkcji.

### <a name="generate-license-plate"></a>Generuj numer identyfikacyjny

Aby ta funkcja była dostępna, włącz następujące funkcje w module [zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (w tej kolejności):

1. Numer identyfikacyjny do zgłoszenia wyrobów gotowych został dodany do urządzenia karty zadań
1. Włącz automatyczną generację numeru identyfikacyjnego podczas zgłaszania wyrobów gotowych w urządzeniu karty zadań

### <a name="print-label"></a>Drukuj etykietę

Aby ta funkcja była dostępna, włącz następujące funkcje w module [zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (w tej kolejności):

1. Numer identyfikacyjny do zgłoszenia wyrobów gotowych został dodany do urządzenia karty zadań
1. Drukowanie etykiety z menu Urządzenie karty zadań

### <a name="allow-locking-the-touch-screen"></a>Zezwalaj na blokowanie ekranu dotykowego

Aby ta funkcja była dostępna, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- (Wersja zapoznawcza) Funkcja umożliwiająca blokowanie urządzenie karty zadań i terminalu karty zadań w celu ich wyczyszczenia

## <a name="work-with-production-floor-execution-configurations"></a>Praca z konfiguracjami wykonania hali produkcyjnej

Aby utworzyć i zarządzać konfiguracjami urządzeń, przejdź do **Kontrola produkcji \> Konfiguracja \> Uruchomienie produkcji \> Konfigurowanie interfejsu wykonania hal produkcyjnych**. Na stronie **Konfigurowanie interfejsu wykonania hal produkcyjnych** wyświetlana jest lista istniejących konfiguracji. Na tej stronie można wykonać następujące akcje:

- Wybierz dowolną konfigurację hali produkcyjnej znajdującą się w lewej kolumnie, aby ją wyświetlić i edytować.
- Wybierz opcję **Nowy** w okienku akcji, aby dodać nową konfigurację urządzenia do listy. Następnie w polu **Konfiguracja** wprowadź nazwę, aby zidentyfikować nową konfigurację. Wprowadzona tutaj nazwa musi być unikatowa wśród wszystkich konfiguracji urządzeń i nie będzie można jej później edytować.

Następnie skonfiguruj różne ustawienia dla wybranej konfiguracji urządzenia. Dostępne są następujące pola:

- **Zgłoś ilość przy wyjściu** – wartość *Tak* powoduje, że pracownicy będą monitowani o raportowanie informacji zwrotnych dotyczących zadań w toku podczas wyrejestrowywania. Jeśli ustawiono wartość *Nie* , pracownik nie będzie monitowany.
- **Zablokuj pracownika** — Jeśli ta opcja ma wartość *Nie* , pracownicy są wylogowani natychmiast po dokonaniu rejestracji (np. nowego zadania). Urządzenie wróci do strony rejestracji. Jeśli ta opcja jest ustawiona na wartość *Tak* , pracownicy pozostaną zalogowani na urządzeniu z kartą pracy. Pracownik może jednak wylogować się ręcznie, aby inny pracownik mógł się zalogować, gdy urządzenie karty będzie nadal działać na tym samym koncie użytkownika systemu. Aby uzyskać więcej informacji o tych typach kont, zobacz, zobacz temat [Przypisani użytkownicy](config-job-card-device.md#assigned-users).
- **Użyj faktycznego czasu rejestracji** – Ustaw to na *Tak* , aby ustawić czas każdej nowej rejestracji na dokładny czas, w którym pracownik przesłał rejestrację. Jeśli ta opcja jest ustawiona na *Nie* , w zamian zostanie użyta godzina logowania. Zazwyczaj ustawienie to jest ustawione na *Tak* , jeśli włączono opcję **Zablokuj pracownika** i/lub opcję **Jeden pracownik** ustawioną na *Tak* , gdzie pracownik często pozostaje zalogowany przez dłuższy okres czasu.
- **Jeden pracownik** – Ustawienie tej opcji na wartość *Tak* , jeśli tylko jeden pracownik korzysta z każdego urządzenia karty zadań, w którym ta konfiguracja jest aktywna. Po ustawieniu tej opcji na *Tak* , opcja **Blokowanie pracownika** jest automatycznie ustawiana na wartość *Tak*. Ponadto to ustawienie usuwa zapotrzebowanie (i zdolność) pracownika, który ma być zalogowany przy użyciu identyfikatora karty identyfikacyjnej (lub podobnego identyfikatora). Zamiast tego pracownik loguje się do Microsoft Dynamics 365 Supply Chain Management, używając konta użytkownika systemowego powiązanego z *pracownik zarejestrowany w czasie* (z tabeli *pracownicy* ) i jednocześnie loguje się do urządzenia karty pracy jako ten pracownik.
- **Zezwalaj na blokowanie ekranu dotykowego** – tę opcję należy wybrać *Tak* , aby umożliwić pracownikom zablokowanie ekranu dotykowego urządzenia karty zadań w celu ich usunięcia. Jeśli ta opcja jest ustawiona na *Tak* , do strony rejestracji urządzenia zostanie dodany przycisk **Blokowanie ekranu ze względu na dezynfekcję**. Po wybraniu tego przycisku przez pracownika ekran dotykowy jest tymczasowo blokowany, aby zapobiec niezamierzonemu wprowadzaniu. Wyświetlany jest również czasomierz odliczania. Pracownik może następnie bezpiecznie oczyścić urządzenie i ekran. Po zakończeniu odliczania ekran dotykowy automatycznie odblokowuje ekran.
- **Czas trwania blokady ekranu** – gdy opcja **Zezwalaj na blokowanie ekranu dotykowego** jest ustawiona na *Tak* , ta opcja służy do określenia liczby sekund, kiedy ekran dotykowy powinien być zablokowany do oczyszczania. Czas trwania musi być liczbą od 5 do 120 sekund.
- **Generowanie numeru identyfikacyjnego** – ustawienie tej opcji na wartość *Tak* powoduje generowanie nowego numeru identyfikacyjnego za każdym razem, gdy pracownik używa urządzenia karty zadań do zgłaszania wyrobów gotowych. Numer identyfikacyjny jest generowany na podstawie sekwencji numerów ustawionej na stronie **Parametry zarządzania magazynem**. Po ustawieniu wartości opcji *Nie* pracownicy muszą określić istniejący numer identyfikacyjny podczas zgłaszania wyrobów gotowych.
- **Drukuj etykietę** – ustawienie tej opcji na wartość *Tak* powoduje Drukowanie etykiety numeru identyfikacyjnego, gdy pracownik korzysta z urządzenia karty zadań w celu zgłoszenia jako gotowej. Konfiguracja etykiety jest ustawiana w obszarze marszruta dokumentów, zgodnie z opisem w [Układ rozsyłania dokumentów dla etykiet numerów identyfikacyjnych](../warehousing/document-routing-layout-for-license-plates.md).

## <a name="clean-up-job-configurations"></a>Oczyszczanie konfiguracji zadań

Kiedy kierownik hali konfiguruje interfejs wykonawczy hali produkcyjnej, wybiera konfigurację i filtr zadań. Opcje te są przechowywane w tabeli odwołań w Supply Chain Management, a przeglądarka używa identyfikatora przechowywanego w lokalnym pliku cookie w celu znalezienia właściwego wiersza w tej tabeli. Tabela rejestruje również datę i godzinę ostatniego logowania pracownika na każdym urządzeniu.

Zadanie wsadowe okresowo oczyszcza wpisy w tabeli odwołań dla urządzeń, które nie zarejestrowały żadnych działań w ciągu ostatnich 60 dni. Wpisy można również czyścić ręcznie w dowolnym momencie, wykonując następujące kroki:

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Wykonywanie produkcji \> Konfigurowanie interfejsu wykonania hal produkcyjnych**.
1. W okienku akcji wybierz opcję **Oczyść konfiguracje klientów**.
1. W oknie dialogowym **Oczyść konfigurację klientów** w polu **Liczba dni** ustaw liczbę dni nieaktywności (przed dniem dzisiejszym), które mają być brane pod uwagę. Wszystkie konfiguracje i rekordy logowania dla urządzeń, które nie były aktywne w tym czasie, zostaną usunięte.
1. Wybierz przycisk **OK** , aby oczyścić odpowiednie konfiguracje na podstawie **Liczby dni**.
