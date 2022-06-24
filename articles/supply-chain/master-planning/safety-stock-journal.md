---
title: Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania dla pozycji
description: W tym artykule opisano sposób używania arkusza zapasu bezpieczeństwa do aktualizowania ilości zapasu bezpieczeństwa dla towarów przez obliczanie propozycji minimalnego zapotrzebowania na podstawie transakcji historycznych.
author: t-benebo
ms.date: 10/28/2021
ms.topic: article
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, ReqItemTableSetup, ReqItemTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-28
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 385144738b83fcf6873eae5204b4784d6ecd5b80
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851777"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage-for-items"></a>Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania dla pozycji

[!include [banner](../../includes/banner.md)]

Zapasy bezpieczeństwa wskazują dodatkową ilość towaru, który jest przechowywany w magazynie, aby zmniejszyć ryzyko wyczerpania towaru. Zapasy bezpieczeństwa są używane jako bufor na wypadek przyjścia zamówień sprzedaży, ale dostawca nie może dotrzymać żądanej przez klienta daty wysyłki.

W tym artykule opisano, jak używać dziennika zapasów bezpieczeństwa do obliczania propozycji minimalnego pokrycia na podstawie transakcji historycznych, a następnie aktualizować pokrycie pozycji propozycjami.

## <a name="overview-of-minimum-coverage-usage"></a>Przegląd minimalnego wykorzystania zapotrzebowania

Zapas bezpieczeństwa jest ustawiany na stronie **Zapotrzebowania na towar** dla każdego towaru. Różne typy uzupełnienia są reprezentowane przez różne kody zapotrzebowania. (Aby uzyskać więcej informacji, zobacz temat [Realizacja zapasu bezpieczeństwa dla pozycji](safety-stock-replenishment.md).) Jednak dla wszystkich kodów zapotrzebowania jest ustawiana wartość ustawiona w polu **Minimum** na stronie **Pokrycie towaru** dla każdego towaru. Istnieją dwa główne podejścia do korzystania z pola **Minimum**:

- **Minimalna ilość do celów min/maks** — to podejście wykorzystuje minimalną ilość wraz z logiką min/maks. Ma zastosowanie, gdy w polu **Kod zapotrzebowania** jest ustawiona wartość *Minimum/Maksimum* dla odpowiedniej pozycji lub grupy zapotrzebowania. Ilość **minimalna** reprezentuje średnie dzienne zużycie pomnożone przez czas realizacji towaru.
- **Minimalna ilość na potrzeby planu zapasów** — w tym podejściu jest używana ilość minimalna w celu reprezentowania planu zapasów w połączeniu z prognozami popytu. Ma zastosowanie, gdy w polu **Kod zapotrzebowania** jest ustawione na *Okres* lub *Wymaganie* dla odpowiedniej pozycji lub grupy pokrycia. Ilość **minimalna** reprezentuje plan zapasów odzwierciedlający żądany poziom obsługi klienta, co pomaga redukować zapasy, częściowe wysyłki i czas realizacji dostawy. Ilość minimalna odzwierciedla procent dokładności prognozy dla danego towaru. Nie reprezentuje żądanej pozycji magazynowej.

Wartość **Minimalną** można ustawić na trzy sposoby:

- Ręcznie na stronie **Zapotrzebowanie na towar**
- Według struktury zarządzania danymi (*Zakres pozycji* encje danych)
- Na podstawie obliczeń zapasu bezpieczeństwa, które są wykonywane przez arkusze zapasu bezpieczeństwa

## <a name="calculate-minimum-coverage-based-on-historical-usage"></a>Oblicz minimalne pokrycie na podstawie użycia historycznego

Arkusze zapasu bezpieczeństwa służą do obliczania proponowanej ilości minimalnej na podstawie historycznego użycia towaru w celach min./maks. do celów planu zapasów. Użycie historyczne reprezentuje wszystkie transakcje wydania w podanym okresie. Te transakcje wydania obejmują transakcje zamówień sprzedaży i korekty zapasów. Obliczenia identyfikują również wpływ proponowanej ilości minimalnej na wartość zapasów oraz zmianę wartości zapasów w porównaniu z bieżącymi ilościami minimalnymi.

Każdy wiersz arkusza zapasu bezpieczeństwa reprezentuje towar i jego wymiary zapotrzebowania. Te wiersze arkusza są tworzone i pokazywane na stronie **Wiersze arkusza zapasu bezpieczeństwa** (**Planowanie główne \> Planowanie główne \> Uruchom \> Obliczanie zapasu bezpieczeństwa**). Proces biznesowy używania arkuszy zapasu bezpieczeństwa do obliczania proponowanych minimalnych ilości opisano w dalszej części tego artykułu.

Arkusz zapasu bezpieczeństwa jest używany do obliczania proponowanych minimalnych ilości wybranych towarów na podstawie historycznego użycia w wybranych okresach. Proponowane minimum można w razie potrzeby ręcznie zastąpić i przejrzeć potencjalny wpływ proponowanych minimum na wartość zapasów. Po zaksięgowaniu arkusza skojarzone minimalne ilości w za zapotrzebowaniach na towar są automatycznie aktualizowane.

### <a name="create-a-new-safety-stock-journal-name"></a>Tworzenie nowego arkusza zapasu bezpieczeństwa

Aby można było wygenerować ten typ arkusza, należy utworzyć co najmniej jedną nazwę arkusza zapasu bezpieczeństwa. Zazwyczaj kilka nazw arkuszy pomaga oddzielić obliczenia zapasu bezpieczeństwa.

1. Przejdź do **Planowanie główne \> Konfiguracja \> Nazwy arkuszy zapasu bezpieczeństwa**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Dla nowego wiersza należy określić następujące pola:

    - **Nazwa** — Wprowadź krótką nazwę czasopisma.
    - **Opis** — wprowadź opis arkusza.
    - **Prywatny dla grupy użytkowników** — aby ograniczyć odbiorców do bieżącej nazwy arkusza, wybierz grupę użytkowników.
    - **Usuń wiersze po zaksięgowaniu** — zaznaczenie tego pola wyboru spowoduje czyszczenie wierszy arkusza domyślnie po ich zaksięgowaniu. Wyczyść, aby zachować wszystkie zaksięgowane wiersze.

    Pole **Typ arkusza** jest tylko do odczytu i jest wstępnie ustawione dla *zapasu bezpieczeństwa*.

1. Zamknij stronę.

### <a name="create-a-safety-stock-journal-and-lines"></a>Utwórz dziennik zapasów bezpieczeństwa i wiersze

Spowoduje to utworzenie arkusza i automatyczne dodanie do niego wierszy. Każdy wiersz identyfikuje towar, jego wymiary zapotrzebowania oraz kilka obliczonych ilości z historii użycia. Obliczane ilości obejmują średnie wartości przychodów z czasu realizacji towaru, średnie miesięczne problemy z każdym miesiącem oraz miesięczne odchylenie standardowe.

#### <a name="automatically-generate-journal-lines"></a>Automatyczne generowanie wierszy arkusza

Wiersze arkusza mogą być generowane automatycznie tylko wtedy, gdy dla aktualnie wyświetlanego arkusza nie istnieją żadne wiersze.

Aby automatycznie generować wiersze arkusza, należy wykonać następujące kroki.

1. Przejdź do **Planowanie główne \> Planowanie główne \> Uruchom \> Obliczanie zapasu bezpieczeństwa**.
1. W okienku akcji wybierz opcję **Nowy**. Tworzony jest nowy dziennik zapasów bezpieczeństwa.
1. Na skróconej karcie **Szczegóły nagłówka dziennika** ustaw następujące pola:

    - **Nazwa** — umożliwia wybór nazwy arkusza zapasu bezpieczeństwa, do który zostanie dodanie wiersza.
    - **Opis** — Wartością domyślną jest opis wybranej nazwy arkusza. Możesz jednak edytować wartość według potrzeb.
    - **Usuń wiersze po zaksięgowaniu** — zaznaczenie tego pola wyboru spowoduje czyszczenie wierszy arkusza po ich zaksięgowaniu. Wyczyść, aby zachować wszystkie zaksięgowane wiersze. Ustawienie jest dziedziczone po wybranej nazwie arkusza.

    Pole **Arkusz** jest tylko do odczytu i zawiera numer identyfikacyjny arkusza, do który jest tworzenia i dodawania wierszy.

1. Na skróconej karcie **Wiersze arkusza** zaznacz na pasku narzędzi **Utwórz wiersze**.
1. W **oknie dialogowym Tworzenie wierszy arkusza dla proponowanego minimalnego poziomu zapasów** należy ustawić następujące pola:

    - **Od dnia** — umożliwia wybór daty rozpoczęcia okresu, dla który mają być uwzględniane w obliczeniach.
    - **Do dnia** — Wybierz datę zakończenia okresu, dla którego emisje powinny być uwzględnione w tych obliczeniach. Między datą rozpoczęcia a datą zakończenia muszą być co najmniej dwa miesiące.
    - **Oblicz odchylenie standardowe** – Ustaw dla tej opcji wartość *Tak*, aby obliczyć odchylenie standardowe. Tę opcję należy ustawić na wartość *Tak*, aby używać opcji **Użyj poziomu usług** podczas obliczania propozycji (w sposób opisany dalej w tym artykule).

1. Na skróconej karcie **Rekordy do uwzględnienia** możesz skonfigurować filtry i ograniczenia, aby określić, które elementy są uwzględniane. (Można na przykład filtrować według **Wartość grupy zapotrzebowania**.) Wybranie opcji **Filtr** umożliwia otwarcie standardowego okna dialogowego edytora kwerend, w którym można definiować kryteria wyboru, kryteria sortowania i sprzężenia. Pola działają w ten sam sposób, w jaki to robią w przypadku innych typów zapytań w aplikacji Microsoft Dynamics 365 Supply Chain Management.
1. Na skróconej karcie **Uruchom w tle** wybierz, czy chcesz uruchomić zadanie w trybie wsadowym, i/lub skonfiguruj cykliczny harmonogram. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.
1. Kliknij przycisk **OK**. Dla wymiarów zawierających transakcje magazynowe tworzone są wiersze.

#### <a name="manually-add-or-remove-journal-lines"></a>Ręcznie dodaj lub usuń wiersze arkusza

Wiersze arkusza można w dowolnym momencie (po wygenerowaniu lub zamiast automatycznego generowania wierszy) dodawać lub usuwać ręcznie. Na pasku narzędzi skróconej karty **Wiersze arkusza** użyj następujących przycisków:

- **Nowy** – Dodaj nowy wiersz. Następnie wprowadź wartość w każdej kolumnie, aby zdefiniować produkt do obliczenia i zastosować nowe minimum. Ponieważ proponowane minimalne obliczenia nie są dostępne w wierszach dodanych ręcznie, nie są dla nich wyświetlane żadne nowe **obliczone wartości ilości minimalnej**. W związku z tym należy ręcznie wprowadzić **nowe wartości ilości minimalnej**. Można jednak nadal wyświetlać potencjalny wpływ **nowej wartości ilości minimalnej** na wartość zapasów oraz potencjalne zmiany w zapasach w porównaniu z aktualnie określonym minimum.
- **Usuń** – Służy do usuwania wybranego wiersza.
- **Usuwanie wierszy arkusza** — umożliwia usunięcie wszystkich wierszy z arkusza.

### <a name="calculate-a-proposal"></a>Obliczanie propozycji

Na tym etapie jest obliczana proponowana wartość minimalna dla każdego wiersza arkusza oraz potencjalny wpływ tego wiersza na wartość zapasów. (Proponowane minimum jest wyświetlane jako **Obliczona wartość minimalnej ilości**) W wymaganym przypadku obliczenia można wykonać wielokrotnie. Obliczenie aktualizuje wartość **Obliczona minimalna ilość** wyświetlana dla wszystkich wierszy arkusza.

Wyświetlane obliczenia nie wpływają na rzeczywiste wartości minimalnej ilości dla każdego produktu, dopóki nie wybierzesz opcji **Księguj** w okienku akcji. W tym czasie do każdego produktu będą stosowane **nowe wartości ilości minimalnej**.

1. Przejdź do **Planowanie główne \> Planowanie główne \> Uruchom \> Obliczanie zapasu bezpieczeństwa**.
1. Otwórz arkusz, dla których będzie obliczana propozycja. Możesz również utworzyć nowy arkusz, tak jak opisano wcześniej w tym artykule.
1. Na skróconej karcie **Wiersze arkusza** zaznacz na pasku narzędzi **Obliczanie propozycji**. (Nie musisz wybierać żadnych linii.)
1. W oknie dialogowym **Oblicz propozycję minimalnego poziomu zapasów** należy ustawić następujące pola:

    - **Użyj średniego wydania w czasie realizacji** — wybierz tę opcję, aby wygenerować **obliczone wartości minimalnej ilości** na podstawie średniego wydania w określonym okresie. Następnie w polu **Współczynnik mnożenia** wprowadź wartość, o która ma zostać skorygowany wynik. Na przykład wprowadzenie wartości *1.0* umożliwia użycie dokładnej obliczonej średniej lub wartości *1.1* w celu dodania dodatkowego buforu o 10 procent.
    - **Użyj poziomu usług** — wybierz tę opcję, aby obliczyć proponowane minimum na podstawie żądanego poziomu usług. W polu **Poziom usług** wybierz preferowany poziom usług.
    - **Marża czasu realizacji** — umożliwia wprowadzenie wartości wydłużanej o normalny czas realizacji (na przykład w celu umożliwienia administrowania).
    - **Użyj obliczonej ilości minimalnej jako nowej ilości minimalnej** – ustaw tę opcję na *Tak*, aby automatycznie skopiować wartości z kolumny **Wyliczona ilość minimalna** do kolumny **Nowa ilość minimalna** dla wszystkich wierszy po zakończeniu obliczeń. Jeśli zostanie ustawiona opcja *Nie*, bieżąca **wartość ilości minimalnej** zostanie skopiowana do kolumny **Nowa ilość minimalna** dla wszystkich wierszy. W razie potrzeby konieczne będzie ręczna edycja **nowych wartości ilości minimalnej**.

1. Na skróconej karcie **Uruchom w tle** wybierz, czy chcesz uruchomić zadanie w trybie wsadowym, i/lub skonfiguruj cykliczny harmonogram. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.
1. Kliknij przycisk **OK**. Wyniki obliczeń są pokazywane w kolumnie **Obliczona ilość minimalna** na skróconej **karcie Wiersze arkusza**. Na razie wartości są tylko proponowanymi wartościami, które nie zostały jeszcze zastosowane do produktów.

### <a name="update-minimum-quantity"></a>Aktualizacja ilości minimalnej

Można wybrać dowolny wiersz w arkuszu zapasu bezpieczeństwa i ręcznie zastąpić wartość w polu **Nowa ilość minimalna**.

1. Przejdź do **Planowanie główne \> Planowanie główne \> Uruchom \> Obliczanie zapasu bezpieczeństwa**.
1. Otwórz dziennik do edycji. Możesz również utworzyć nowy arkusz, tak jak opisano wcześniej.
1. Na skróconej karcie **Wiersze arkusza** znajdź wiersz do skorygowania, a następnie zmodyfikować wartość w kolumnie **Nowa ilość minimalna**. Można na przykład ustawić wartość **Nowa ilość minimalna tak**, aby odpowiadała **obliczonej wartości ilości minimalnej**. Jeśli **obliczona minimalna ilość** wynosi *0* zero, można wprowadzić żądaną wartość przyszłą.

### <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Księgowanie nowej ilości minimalnej i sprawdzanie poprawności wyniku

Wykonaj poniższe czynności, aby opublikować nową minimalną ilość i sprawdzić wynik.

1. Przejdź do **Planowanie główne \> Planowanie główne \> Uruchom \> Obliczanie zapasu bezpieczeństwa**.
1. Otwórz arkusz, dla których będą księgować nowe minimalne ilości. Możesz również utworzyć nowy arkusz, tak jak opisano wcześniej.
1. W okienku akcji wybierz pozycję **Księguj**.
1. W **oknie dialogowym Księguj arkusz** ustaw w razie potrzeby ustaw pole na **Przenoszenie wszystkich błędów księgowania do nowego arkusza**. Następnie wybierz **OK**, aby zaksięgować księgę.
1. Jeśli zmieniono wartość **Nowa ilość minimalna** dla wiersza na skróconej karcie **Wiersze arkusza**, zmianę można potwierdzić, wykonać następujące kroki:

    1. W przypadku edytowanego wiersza wybierz łącze w **kolumnie Numer towaru**.
    1. W oknie dialogowym **Informacje o produkcie** zaznacz łącze w polu **Numer towaru**, aby otworzyć powiązany z nim rekord zwolnionego produktu.
    1. W okienku akcji na karcie **Plan** kliknij w grupie **Zapotrzebowanie** wybierz opcję **Zapotrzebowanie na pozycje**.
    1. Należy zauważyć, że **minimalna** wartość dla lokalizacji i magazynu, która została skorygowana za pomocą zaksięgowanego arkusza zapasu bezpieczeństwa, została zaktualizowana, aby dostosować go do edycji.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Realizacja zapasów bezpieczeństwa dla towarów](safety-stock-replenishment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
