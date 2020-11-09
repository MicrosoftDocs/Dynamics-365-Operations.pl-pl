---
title: Jak pracownicy korzystają z interfejsu wykonania hal produkcyjnych
description: W tym temacie opisano sposób korzystania z interfejsu wykonywania pomieszczeń produkcyjnych z punktu widzenia pracownika.
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
ms.openlocfilehash: 40c6794fdf25da44a75aba4a502a89966c0ec4d0
ms.sourcegitcommit: 9dd2d38e76d4d93171315ec319e6ce7d51d4e6c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2020
ms.locfileid: "4012500"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Jak pracownicy korzystają z interfejsu wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Interfejs wykonywania pomieszczeń produkcyjnych jest zoptymalizowany pod kątem interakcji dotykowej. Jego projekt stanowi kontrast wizualny odpowiadający wymaganiom dotyczącym ułatwień dostępu w środowisku produkcyjnym. Oferuje wszystkie te same możliwości funkcjonalne, co urządzenie karty zadań. Pozwala to także na uruchamianie wielu zadań równolegle z listy zadań. (Ta możliwość jest również nazywana *przydzieleniem zadań* ) Ponadto na podstawie listy zadań pracownicy mogą otwierać Przewodnik utworzony w przewodniku Microsoft Dynamics 365 Guide. W ten sposób mogą uzyskać instrukcje wizualne w HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Zaloguj się do interfejsu wykonywania hali produkcyjnej jako pracownik

Zanim pracownicy będą mogli rozpocząć korzystanie z urządzenia, kierownik lub personel techniczny musi je przygotować i otworzyć odpowiednią stronę w systemie Dynamics 365 Supply Chain Management. Aby uzyskać więcej informacji o konfigurowaniu urządzenia, zapoznaj się z tematem [Konfigurowanie urządzenia do uruchamiania interfejsu wykonywania pomieszczeń produkcyjnego](production-floor-execution-setup.md).

Po przygotowaniu urządzenia zostanie na nim wyświetlona strona logowania. Na tej stronie są wyświetlane informacje o stanie zadań dla lokalnej komórki roboczej. Te informacje są aktualizowane okresowo. Na stronie pracownicy są używali identyfikatorów karty identyfikacyjnej do podpisania. Chociaż pracownicy nie muszą mieć konta użytkownika służącego do Supply Chain Management, muszą mieć *zarejestrowane konto pracownika* , które mogą być używane podczas logowania.

![Strona logowania do interfejsu wykonania hali produkcyjnej](media/pfei-sign-in-page.png "Strona logowania do interfejsu wykonania hali produkcyjnej")

Pozostałe sekcje w tym temacie opisują sposób interakcji pracowników z interfejsem.

## <a name="all-jobs-tab"></a>Karta wszystkie zadania

Na karcie **Wszystkie zadania** znajduje się lista zadań pokazująca wszystkie zadania produkcyjne o stanie *Nierozpoczęte* , *Zatrzymane* lub *Rozpoczęte*.

![Karta wszystkie zadania](media/pfei-all-jobs-tab.png "Karta wszystkie zadania")

Lista zadań ma następujące kolumny: (Liczby odpowiadają liczbom na poprzedniej ilustracji).

1. **Kolumna wyboru** — skrajna kolumna z lewej strony używa znaczników wyboru w celu wskazania zadań wybranych przez pracownika. Pracownicy mogą wybierać wiele zadań na liście jednocześnie. Aby wybrać wszystkie zadania z listy, zaznacz znacznik wyboru w nagłówku kolumny. W przypadku wybrania jednego zadania szczegóły dotyczące tego zadania są wyświetlane w dolnej części strony.
1. **Kolumna stanu zadania** — w tej kolumnie są używane symbole wskazujące stan każdego zadania. Zadania bez symbolu w tej kolumnie mają stan *Nierozpoczęty*. Zielony trójkąt wskazuje zadania o stanie *Rozpoczęte*. Dwie żółte linie pionowe wskazują zadania o stanie *Zatrzymane*.
1. **Kolumna wysokiego priorytetu** — w tej kolumnie są używane znaki wykrzyknika w celu wskazania zadań o wysokim priorytecie.
1. **Zamówienia** — w tej kolumnie jest wyświetlany numer zlecenia produkcyjnego dla zadania.
1. **Opis** — w tej kolumnie jest wyświetlany opis operacji, której częścią jest zadanie.
1. **Zażądano** — w tej kolumnie jest wyświetlana ilość, która została zaplanowana do wyprodukowania dla zadania.
1. **Rozpoczęte** — w tej kolumnie jest wyświetlana ilość, która została już rozpoczęta dla zadania.
1. **Zakończono** — w tej kolumnie jest wyświetlana ilość, która została już zakończona dla zadania.
1. **Wyrzucono** — w tej kolumnie jest wyświetlana ilość, która została już wyrzucona dla zadania.
1. **Pozostało** — w tej kolumnie jest wyświetlana ilość pozostała do wypełnienia dla zadania.

## <a name="active-jobs-tab"></a>Karta aktywne zadania

![Karta aktywne zadania](media/pfei-active-jobs-tab.png "Karta aktywne zadania")

Lista zadań na karcie **Aktywne zadania** ma następujące kolumny:

- **Kolumna wyboru** — skrajna kolumna z lewej strony używa znaczników wyboru w celu wskazania zadań wybranych przez pracownika. Pracownicy mogą wybierać wiele zadań na liście jednocześnie. Aby wybrać wszystkie zadania z listy, zaznacz znacznik wyboru w nagłówku kolumny. W przypadku wybrania jednego zadania szczegóły dotyczące tego zadania są wyświetlane w dolnej części strony.
- **Zamówienia** — w tej kolumnie jest wyświetlany numer zlecenia produkcyjnego dla zadania.
- **Opis** — w tej kolumnie jest wyświetlany opis operacji, której częścią jest zadanie.
- **Zażądano** — w tej kolumnie jest wyświetlana ilość, która została zaplanowana do wyprodukowania dla zadania.
- **Rozpoczęte** — w tej kolumnie jest wyświetlana ilość, która została już rozpoczęta dla zadania.
- **Zakończono** — w tej kolumnie jest wyświetlana ilość, która została już zakończona dla zadania.
- **Wyrzucono** — w tej kolumnie jest wyświetlana ilość, która została już wyrzucona dla zadania.
- **Pozostało** — w tej kolumnie jest wyświetlana ilość pozostała do wypełnienia dla zadania.

## <a name="starting-and-completing-production-jobs"></a>Rozpoczynanie i kończenie zadań produkcyjnych

Pracownicy rozpoczynają zadanie produkcji, zaznaczając zadanie na karcie **Wszystkie zadania** , a następnie wybierając przycisk **Rozpocznij zadanie** , aby otworzyć okno dialogowe **Rozpoczęcie zadania**.

![Okno dialogowe Rozpocznij zadanie](media/pfei-start-job-dialog.png "Okno dialogowe Rozpocznij zadanie")

Pracownicy używają okna dialogowego **Rozpoczęcie zadania** w celu potwierdzenia ilości produkcji, a następnie uruchomienia zadania. Pracownicy mogą korygować ilość, wybierając pole **Ilość** , a następnie używając wyświetlonej klawiatury numerycznej. Następnie pracownikom wybierz przycisk **Rozpocznij** , aby rozpocząć pracę nad zadaniem. Okno dialogowe **Rozpoczęcie zadania** jest zamknięte, a zadanie jest dodawane do karty **Aktywne zadania**.

Pracownicy mogą uruchamiać zadanie o dowolnym stanie. Jeśli pracownik uruchamia zadanie o stanie *Nierozpoczęte* , w polu **Ilość** w oknie dialogowym **Rozpoczęcie zadania** jest początkowo wyświetlana pełna ilość. Gdy pracownik rozpoczyna zadanie, które ma status *Rozpoczęte* lub *Zatrzymane* , pole **Ilość** początkowo pokazuje pozostałą ilość.

## <a name="reporting-good-quantities"></a>Raportowanie dobrych ilości

Gdy pracownik ukończy lub częściowo wykonuje zadanie, może zgłosić dobre ilości wyprodukowane przez zaznaczenie zadania na karcie **Aktywne zadania** , a następnie wybrać **Postęp raportowania**. Następnie w oknie dialogowym **Postęp raportowania** pracownik wprowadza ilość dobrych za pomocą klawiatury numerycznej. Domyślnie ilość jest pusta. Po wprowadzeniu ilości pracownik może zaktualizować stan zadania jako *W toku* , *Zatrzymany* lub *Ukończony*.

![Okno dialogowe Postęp raportu](media/pfei-report-progress-dialog.png "Okno dialogowe Postęp raportu")

## <a name="reporting-scrap"></a>Raportowanie odpadków

Gdy pracownik ukończy lub częściowo wykonuje zadanie, może zgłosić odpadki przez zaznaczenie zadania na karcie **Aktywne zadania** , a następnie wybrać **Zgłoś odpadki**. Następnie w oknie dialogowym **Zgłoś odpadki** pracownik wprowadza ilość odpadków za pomocą klawiatury numerycznej. Pracownik również wybiera przyczynę ( *Brak* , *Maszyna* , *Operator* lub *Materiały* ).

![Okno dialogowe Zgłoś odpadki](media/pfei-report-scrap-dialog.png "Okno dialogowe Zgłoś odpadki")

## <a name="completing-a-job-and-starting-a-new-job"></a>Kończenie zadania i rozpoczynanie nowego zadania

Zazwyczaj pracownicy wypełniają zadanie, wybierając jedno lub więcej zadań bieżących na karcie **Aktywne zadania** , a następnie wybierając opcję **Raportuj postęp**. Następnie wprowadź ilość wyprodukowaną (ilość dobrych) i określ stan na *Zakończony*. Jeśli zaznaczono więcej niż jedno zadanie, do przechodzenia między nimi są używane przyciski **Poprzedni** i **Następny**. Aby rozpocząć nowe zadanie, pracownik wybiera go na karcie **Wszystkie zadania** , a następnie wybiera **Zadanie rozpoczęcia**.

Pracownik może również uruchomić nowe zadanie, gdy poprzednie zadanie jest otwarte. Ponownie, aby rozpocząć nowe zadanie, pracownik wybiera go na karcie **Wszystkie zadania** , a następnie wybiera **Zadanie rozpoczęcia**. Jednak w tym przypadku okno dialogowe **Rozpoczęcie zadania** informuje pracownika, że aktualnie pracuje nad zadaniem, i dlatego musi je zatrzymać lub zakończyć przed rozpoczęciem nowego zadania.

## <a name="working-on-multiple-jobs-in-parallel"></a>Praca nad wieloma zadaniami równolegle

Jeden pracownik może jednocześnie pracować z wieloma zadaniami (równolegle). W takim przypadku zbieranie zadań, nad którymi pracuje pracownik, jest nazywane *pakietem zadań*. Pracownik może dodawać nowe zadania do pakietu lub wykonywać jedno lub więcej zadań w pakiecie. Poniższe dwa scenariusze pokazują, w jaki sposób pracownik może pracować równolegle z zadaniami.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>Scenariusz 1: pracownik, który nie ma aktywnych zadań, chce rozpocząć dwa zadania i pracować równolegle

Pracownik wybiera dwa zadania na karcie **Wszystkie zadania** , a następnie wybiera **Zadanie rozpoczęcia**. W oknie dialogowym **Rozpoczęcie zadania** wyświetlane są zarówno wybrane zadania, jak i pracownik, który może zmienić ilość na początkową dla każdego zadania. Następnie pracownik potwierdzi to okno dialogowe i może uruchomić oba zadania.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>Scenariusz 2: pracownik, który ma dwa aktywne zadania będące w toku, chce rozpocząć trzecie zadanie i pracować nad nim równolegle z dwoma innymi

Pracownik wybiera trzecie zadanie na karcie **Wszystkie zadania** , a następnie wybiera **Pakiet**. W oknie dialogowym **Pakiet** pracownik może skorygować ilość do rozpoczęcia. Następnie pracownik zatwierdza okno dialogowe, wybierając opcję **Pakiet**.

## <a name="working-on-indirect-activities"></a>Praca przy działaniach pośrednich

Działania pośrednie to działania, które nie są bezpośrednio związane ze zleceniem produkcyjnym. Działania pośrednie można definiować elastycznie, jak to opisano w temacie [Ustawianie działań pośrednich dla modułu czas i frekwencja](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Na przykład Shannon, pracownica hali w firmie Contoso, chce uczestniczyć w spotkaniu firmy, a spotkania są traktowane jako działania pośrednie. Ma zastosowanie jedno z następujących dwóch scenariuszy:

- **Shannon pracuje z co najmniej jednym aktywnym zadaniem.** Shannon wybiera **Działanie** , identyfikuje działanie (spotkanie) i potwierdza jego wybór. Komunikat informujący, że posiada zadania, które są w toku. Na podstawie wiadomości Shannon może wybrać opcję ukończenia lub zatrzymania zadań, nad którymi pracuje, zanim zostaną one przechodzące na spotkanie.
- **Shannon nie ma żadnych aktywnych zadań.** Shannon wybiera **Działanie** , identyfikuje działanie (spotkanie) i potwierdza jego wybór. Jest obecnie zarejestrowana jako przebywająca na spotkaniu.

W obu przypadkach, po potwierdzeniu przez Shannon wyboru, przechodzi do strony logowania lub strony, która będzie czekać, aż potwierdzi, że wróciła ze swojej pośredniej działalności. Wyświetlana strona zależy od konfiguracji interfejsu wykonywania pomieszczeń produkcyjnych. (Aby uzyskać więcej informacji, zobacz [Konfigurowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-configure.md).)

## <a name="working-on-breaks"></a>Praca z przerwami

Pracownicy mogą rejestrować przerwy. Przerwy można definiować elastycznie, zgodnie z opisem w [Płaca oparta na rejestracjach](pay-based-on-registrations.md).

Pracownik rejestruje przerwę, wybierając opcję **Przerwa** , a następnie wybierając kartę, która reprezentuje typ przerwy (np. obiad). Gdy pracownik potwierdzi wybór, na urządzeniu zostanie wyświetlona strona logowania lub strona, która będzie czekać, aż pracownik potwierdzi, że wrócił z przerwy. Wyświetlana strona zależy od konfiguracji interfejsu wykonywania pomieszczeń produkcyjnych. (Aby uzyskać więcej informacji, zobacz [Konfigurowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-configure.md).)

## <a name="opening-instructions"></a>Otwieranie instrukcji

Pracownicy mogą otwierać dokument dołączony do stanowiska, wybierając odpowiednie **Instrukcje**. Przycisk **Instrukcje** jest dostępny tylko wtedy, gdy dokument jest skojarzony z zadaniem w danych głównych. Na przykład dokument dołączony do produktu na stronie **Zwolnione produkty** w module Supply Chain Management będzie dostępny dla pracowników, którzy będą otwierali się w interfejsie realizacji produkcji.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Otwieranie przewodników rzeczywistości mieszanej dla HoloLens

[Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) ułatwiają pracownikom udzielanie informacji poprzez dostarczanie wskazówek, które korzystają z rzeczywistości mieszanej. Możesz zdefiniować znormalizowane procesy, w których instrukcje krok po kroku kierują pracowników do potrzebnych im narzędzi i części oraz pokazują, jak używać tych narzędzi w rzeczywistych sytuacjach zawodowych. Poniżej znajduje się omówienie procesu.

1. Za każdym razem, gdy pracownik otwiera listę zadań w interfejsie wykonywania prac produkcyjnych, interfejs wyszukuje wszystkie odpowiednie przewodniki dotyczące wyświetlanych zadań.
1. Pracownik wybiera **Przewodniki** , aby wyświetlić listę poradników.
1. Pracownik wybiera odpowiedni przewodnik z listy.
1. Interfejs realizacji oddziału produkcyjnego pokazuje kod QR dla wybranego przewodnika.
1. Pracownik wprowadza do systemu HoloLens i rzutuje kod QR, aby rozpocząć Przewodnik.
1. Pracownik pracuje z przewodnikiem w celu uzyskania informacji o zadaniu.

Aby uzyskać więcej informacji na temat sposobu tworzenia, przypisywania i używania przewodników dla HoloLens, zapoznaj się z tematem [Zapewnianie przewodników Guides rzeczywistości mieszanej dla pracowników w produkcji](instruction-guides-in-production-overview.md).
