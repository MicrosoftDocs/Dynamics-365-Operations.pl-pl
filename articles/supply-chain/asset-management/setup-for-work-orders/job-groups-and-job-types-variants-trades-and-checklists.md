---
title: Rodzaje prac konserwacyjnych, kategorie, warianty, wymiany i listy kontrolne
description: Ten artykuł opisuje typy zadań konserwacji i kategorie typów zadań konserwacji i typy zadań konserwacji, warianty typu zadań konserwacji, handel zadaniami konserwacyjnymi oraz listy kontrolne konserwacji w Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetJobTypeDefaultForecast, EntAssetJobTrade, EntAssetJobTypeDefaultCopy, EntAssetChecklistVariableValueLookup, EntAssetChecklistTemplateCreate, EntAssetJobVariant, EntAssetJobTypeDefaultReference, EntAssetJobTypeDefaultChecklist, EntAssetJobTypeDefault, EntAssetJobType, EntAssetJobTypeDefaultChecklistCopy, EntAssetChecklistTemplate, EntAssetJobTypeDefaultDescription, EntAssetJobTypeLookup, EntAssetJobTypeDefaultToolCopy, EntAssetJobTypePreviewPart, EntAssetJobTypeDefaultTool, EntAssetJobTypeDefaultForecastCopy, EntAssetChecklistTemplateLookup, EntAssetJobGroup, EntAssetChecklistVariable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6b4d0bf82dc0dfe12991b4a48fd68a029a2ff2f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887610"
---
# <a name="maintenance-job-types-categories-variants-trades-and-checklists"></a>Rodzaje prac konserwacyjnych, kategorie, warianty, wymiany i listy kontrolne

[!include [banner](../../includes/banner.md)]

Typ składnika majatku jest dołączany do każdego składnika majatku. Typy składników majatku definiują typy zadań konserwacji (i tym samym zadania konserwacji), które mogą być wykonywane na składnikach majatku. Tworząc zlecenie pracy należy wybrać typ zadań konserwacji. Można wybrać tylko typy zadań konserwacji, które są związane z konfiguracją typu składnika majatku, który jest używany dla składnika majatku.

Aby zapoznać się z graficznym omówieniem składników majątku i typów zadań konserwacji oraz ich połączenia ze zleceniami pracy, zobacz [Lokalizacje czynności konserwacyjnych i składniki majątku](../overview/functional-locations-and-objects.md).

Warianty typów zadań konserwacji mogą być ustawione w typach zadań konserwacji. Warianty typu zadania konserwacji definiują warianty typu zadania, takie jak rozmiary (małe, średnie lub duże), okresy (cotygodniowe, co dwa tygodnie, miesiąc lub trzy miesiące) oraz konfiguracje (niska norma, elastyczna lub wysoka wydajność).

Handel zadaniami konserwacyjnymi zawiera informacje o profesjonalnej wymianie, np. handel mechaniczny, elektryczny i hydrauliczny. Wymagania dotyczące kwalifikacji można skonfigurować w handlu zadaniami konserwacyjnymi. Wszystkie relacje handlowe zadań konserwacyjnych mogą być używane w odniesieniu do wszystkich typów zadań konserwacji. Wybór zadania konserwacji typu wariant i/lub obsługa prac konserwacyjnych w zleceniu pracy jest opcjonalna.

Dla każdego typu zlecenia konserwacji można utworzyć odmiany ustawień typu zlecenia konserwacji. Jeśli na przykład istnieje typ zadania obsługi o nazwie **Usługa**, można utworzyć następujące odmiany dla tego typu zadania konserwacji: **ciężarówki 30 000 km**, **samochody 30 000 km** oraz **samochody ciężarowe 30 000 km**.

Kategorie typów zadań konserwacji służą do zbierania grupy typów zadań konserwacyjnych na potrzeby przeglądu. Przykłady kategorii typów zadań obsługi mogą obejmować **kalibrację**, **inspekcję**, **przegląd** i **instrumentacja**.

Szablony list kontrolnych obsługi i listy kontrolne obsługi są używane do ustawiania list kontrolnych obsługi. Listy kontrolne konserwacji służą do ustawiania typów zadań konserwacji i używane w zleceniu pracy.

Najpierw należy skonfigurować wymagane kategorie typów prac konserwacyjnych, warianty rodzajów prac konserwacyjnych i zawody prac konserwacyjnych. Utwórz następnie typy zadania konserwacji. Na koniec na stronie **Ustawienia domyślne typu zadania konserwacji** można utworzyć wszystkie odmiany typów zadania konserwacji, które są wymagane dla danego sprzętu. Na tej stronie można również skonfigurować prognozy, listy kontrolne obsługi i narzędzia dla kombinacji typów zadań serwisowych.

> [!NOTE]
> Typ zadania konserwacji może być powiązany tylko z jedną kategorią typu zadania obsługi.

## <a name="create-a-maintenance-job-type-category"></a>Utwórz kategorię typu zadania konserwacji

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zadania** \> **Kategorie typów zadań konserwacji**.
2. Wybierz pozycję **Nowy**.
3. W polu **Kategorie typów zadań konserwacji** wprowadź identyfikator kategori typu zadania konserwacji.
4. W polu **Nazwa** wprowadź nazwę.

    Po utworzeniu relacji między kategoriami typów zadań konserwacji a zadaniami serwisowymi w polu **typy zadań** wyświetlana jest liczba typów zadań obsługi związanych z tą kategorią typu zadania konserwacji.

![Strona Kategorie typu zadania konserwacji.](media/01-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type-variant"></a>Utwórz wariant typu zadania konserwacji

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zadania** \> **Warianty typów zadań konserwacji**.
2. Wybierz pozycję **Nowy**.
3. W polu **Warianty typów zadań konserwacji** wprowadź identyfikator wariant typu zadania konserwacji.
4. W polu **Opis wprowadź** opis.
5. W skróconej karcie **Typy zadań konserwacji** wybierz opcję **Dodaj**, aby dodać typ zadania konserwacji.
6. W polu typ zadania konserwacji **typ zadania konserwacji** wybierz typ zadania konserwacji.
7. Powtórz kroki od 5 do 6, aby dodać więcej typów zadań obsługi do wariantu typu zadania serwisowego.

    W polu **szczegóły** naskróconej karcie pole **typy zadań** zawiera liczbę typów zadań obsługi, które zostały dodane do danego typu zadania serwisowego.

![Strona Warianty typu zadania konserwacji.](media/02-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-trade"></a>Tworzenie zawodu zadania konserwacji

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zadania** \> **Zawody zadań konserwacji**.
2. Wybierz pozycję **Nowy**.
3. W polu **Zawód** wprowadź identyfikator zawodu pracy konserwacji.
4. W polu **Opis wprowadź** opis.
5. Na skróconej karcie **Umiejętności** wybierz opcję **Dodaj**, aby dodać nowe kwalifikacje, które powinny być związane z zawodem zadań konserwacji.
6. W polu **Umiejętności** wybierz umiejętność.
7. W polu **Poziom** wybierz Poziom umiejętności.
8. Powtórz kroki od 5 do 7, aby dodać więcej umiejętności do zawodu w ramach zadania serwisowego.

    W polu **szczegóły** na skróconej karcie pole **Umiejętności** zawiera liczbę umiejętności, które zostały dodane do danego zawodu zadania serwisowego.

9. Na skróconej karcie **certyfikaty** wybierz pozycję **Dodaj**, aby dodać certyfikat do zawodu zadania konserwacji.
10. W polu **Typ certyfikatu** zaznacz opcję Certyfikat.
11. Powtórz kroki od 9 do 10, aby dodać więcej certyfikatów do zawodu w ramach zadania serwisowego.

    W polu **szczegóły** na skróconej karcie pole **Certyfikaty** zawiera liczbę certyfikatów, które zostały dodane do danego zawodu zadania serwisowego.

![Strona Tworzenie zawodu zadania konserwacji.](media/03-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-variable"></a>Utwórz zmienną listę kontrolną konserwacji

Podczas tworzenia wierszy listy kontrolnej w ramach zadania obsługi typu domyślnego należy wybrać typ listy prac dla konserwacji. **Zmienna** jest typem listy kontrolnej konserwowanego składnika majątku. Służy do definiowania możliwego wyniku w zakresie w wierszu listy kontrolnej obsługi, który jest powiązany z wierszem zlecenia pracy. Zmienna umożliwia utworzenie zbioru wstępnie zdefiniowanych wyników bez konieczności dokładnego pomiaru.

**Przykład 1:** można zmierzyć poziom oleju, definiując trzy wartości: **poziom zbyt wysoki**, **poziom zbyt niski** i **poziom w zakresie**. Dla każdej wartości określa się, czy wartość wyniku jest równa **Sukces**, **Niepowodzenie** lub **Brak**.

**Przykład 2:** przeprowadzasz wzrokową kontrolę nad urządzeniem, aby ocenić zużycie.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Listy kontrolne konserwacji** \> **Zmienne listy kontrolnej konserwowanego składnika majątku**.
2. Wybierz pozycję **Nowy**.
3. W polu **Zmienna** wprowadź identyfikator zmienną listy kontrolnej pracy konserwacji.
4. W polu **Nazwa** wprowadź nazwę.
5. Na skróconej karcie **Ogólne** wybierz opcję **Dodaj**, aby dodać wiersz do zmiennej.

    W polu **Numer wiersza** automatycznie jest wprowadzany następujący numer. Po dodaniu wszystkich wierszy można zmienić numery wierszy w zależności od potrzeb. Wybranie opcji wiersz i naciśnięcie klawisza **strzałka w dół** powoduje, że kolejny numer w sekwencji jest wprowadzany automatycznie w następnym wierszu.

6. W polu **Wartość** wpisz opis wartości.
7. W polu **wynik** wybierz wynik dla wiersza.

![Strona Zmienne listy kontrolnej konserwowanego składnika majątku.](media/04-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-template"></a>Utwórz szablon listy kontrolnej konserwacji

Szablony listy prac konserwacyjnych mogą być używane jako wspólny zbiór zadań, które pracownik musi wykonać w celu prawidłowego zrealizowania zlecenia. Istnieją odwołania do tych szablonów z wierszy listy kontrolnej obsługi w obszarze domyślny typ zadania konserwacji. Do szablonów można odwoływać się za pośrednictwem wielu domyślnych wierszy typu zadania obsługi. Dzięki temu można łatwo ponownie użyć zbioru typowych zadań listy prac konserwacyjnych. Przykładowe szablony listy kontrolnej obsługi obejmują ogólne instrukcje dotyczące bezpieczeństwa oraz listę elementów i warunków, które muszą być sprawdzone w odniesieniu do konkretnej pompy lub podobnych modeli pasa przenośnika.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Listy kontrolne konserwacji** \> **Szablony listy kontrolnej konserwowanego składnika majątku**.
2. Wybierz pozycję **Nowy**.

    Identyfikator szablonu jest automatycznie wprowadzany w polu **Szablon listy kontrolnej konserwowanego składnika majątku**.

3. W polu **Nazwa** wprowadź nazwę nowego szablonu.
4. W skróconej karcie **Szablony listy kontrolnej konserwowanego składnika majątku** wybierz pozycję **Dodaj**, aby dodać wiersz szablonu.

    W polu **Numer wiersza** automatycznie jest wprowadzany następujący numer. Po dodaniu wszystkich wierszy można zmienić numery wierszy w zależności od potrzeb. Wybranie opcji wiersz i naciśnięcie klawisza **strzałka w dół** powoduje, że kolejny numer w sekwencji jest wprowadzany automatycznie w następnym wierszu.

5. W polu **Typ** wybierz typ wiersza listy kontrolnej konserwacji. Dla każdej listy kontrolną konserwowanego składnika majątku powiązane pola są wyświetlane w skróconej karcie **Szczegóły wiersza**. Dostępne są następujące wartości:

    - **Tekst** — wiersz zawiera tekst opisujący, co należy zrobić. Tego typu listy kontrolnej konserwacji należy użyć, jeśli pracownik chce coś sprawdzić lub sprawdzić, ale nie oczekuje się określonego (mierzalnego) wyniku. Po wybraniu tego typu należy wprowadzić nazwę lub nagłówek w polu **nazwa**. W polu **instrukcje** wprowadź opis czynności, które należy wykonać. Jeśli krok jest wymagany dla listy kontrolnej obsługi, należy skonfigurować opcję **obowiązkowe** na wartość **Tak**.
    - **Nagłówek** - Ten wers służy do grupowania wierszy listy czynności, które są widoczne poniżej nagłówka. ten typ jest przydatny w przypadku kilku wierszy listy kontrolnej obsługi, które można podzielić na określone obszary. Nagłówki zawierają przegląd dotyczący pracownika, który ukończy listę kontrolną obsługi, która zawiera wiele wierszy listy kontrolnej obsługi. Po wybraniu tego typu należy wprowadzić opisową nazwę w polu **nazwa**.
    - **Szablon** — wiersz służy do tworzenia odwołania do istniejącego szablonu. Po wybraniu tego typu należy wprowadzić nazwę dla szablonu w polu **nazwa**. W polu **Szablon** wybierz dany szablon.
    - **Zmienna** — wiersz służy do definiowania możliwego wyniku w zakresie. Aby uzyskać informacje o ustawianiu zmiennych listy czynności konserwacyjnych, zapoznaj się z sekcją [Utwórz zmienną listę kontrolną konserwacji](#create-a-maintenance-checklist-variable). Po wybraniu tego typu należy wprowadzić opisową nazwę dla zmiennej w polu **nazwa**. Wybierz typ zmiennej w polu **Zmienna**. W polu **instrukcje** wprowadź opis czynności, które należy wykonać. Jeśli krok jest wymagany dla listy kontrolnej obsługi, należy skonfigurować opcję **obowiązkowe** na wartość **Tak**.
    - **Miara** – Jest używana do rejestrowania konkretnej miary. Można ustawić miarę, która powinna być związana z wstępnie zdefiniowanym licznikiem. Po wybraniu tego typu należy wprowadzić nazwę dla szablonu w polu **nazwa**. Jeśli ten krok jest wymagany dla listy kontrolnej obsługi, należy skonfigurować opcję **obowiązkowe** na wartość **Tak**. Aby użyć wiersza miary jako rejestracji liczników, należy wybrać licznik w polu **licznik.** Pole powiązane **Jednostka** jest aktualizowane automatycznie. Jeśli wybrano licznik, należy wybrać metodę aktualizacji w polu **wartość**. W polach **Wartość min.** i **Wartość max.** wprowadź dozwolony zakres wartości. W polu **instrukcje** wprowadź opis czynności, które należy wykonać.

        > [!NOTE]
        > Dowolna linia typu **Miara**, która nie ma konfiguracji licznika, jest traktowana jako niezależna Rejestracja miary, ponieważ w module Zarządzanie środkami trwałymi nie jest wykonywane automatyczne uzupełnianie. Podobnie, jeśli wybrany typ licznika nie występuje w składniku aktywów związanym ze zleceniem produkcyjnym, zadanie z listy kontrolnej konserwacji jest traktowane jako niezależna miara. Wartość licznika można zmienić wiele razy. Nie jest on księgowany dopóki [stan cyklu życia zlecenia pracy](work-order-lifecycle-states.md) nie zostanie zmieniony, tak, aby opcja **Przetwarzaj listę kontrolną konserwowanego składnika majątku** jest ustawiona na **tak**.

    W polu **szczegóły** skróconej karcie pole **czeki** zawiera łączną liczbę wierszy list kontrolnych w szablonie. Ta liczba uwzględnia zagnieżdżone wiersze w istniejącym szablonie, do którego odwołano się w szablonie.

![Strona Szablony listy kontrolnej konserwowanego składnika majątku.](media/05-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type"></a>Tworzenie typu zadania konserwacji

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zadania** \> **Typy zadań konserwacji**.
2. Wybierz pozycję **Nowy**.
3. W polu **Typ żądania konserwacji** wprowadź identyfikator typu zadania konserwacji.
4. W polu **Nazwa** wprowadź nazwę.

    Na skróconej karcie **Szczegóły** zawierają przegląd liczby wariantów typów zadań obsługi, umiejętności, certyfikatów, zadań i typów środków, które zostały utworzone dla danego typu zadania obsługi. W polu **wiersze ustawień** wyświetlana jest liczba domyślnych wierszy typu zadania obsługi skonfigurowanych dla tego typu zadania serwisowego. W **Składniki majątku** wyświetlana jest liczba aktywnych składników majątku, dla których dany typ zadania serwisowego jest aktualnie używany.

5. W skróconej karcie **Ogólne** w polu **Kategorie typów zadań konserwacji** wprowadź kategorię typu zadania konserwacji.
6. Ustawienie opcji **Działania w ramach przerwy konserwacyjnej** jest wartość **tak** tak, jeśli typ zadania obsługi wymaga zatrzymania czynności konserwacyjnych w urządzeniu, zanim będzie można wykonać zadanie.
7. W polu **Opis** na skróconej karcie wprowadź opis typu zadania konserwacji.
8. W skróconej karcie **Warianty typów zadań konserwacji** wprowadź wariant typu zadania konserwacji.
9. W przypadku skróconych kart **wymaganych umiejętności** i **wymaganych certyfikatów** można dodawać do typu zadania obsługi umiejętności i wymagania dotyczące certyfikatów.
10. Jeśli określony typ zadania konserwacji musi zostać wykonany, należy go dodać do **kolejnych zadań** na skróconej karcie. Można również skonfigurować typ zadania obsługi (wariant i handel) związany z typem zadania serwisowego. Jeśli zadanie, które powiodło się, ma rozpocząć określoną liczbę dni przed rozpoczęciem lub po rozpoczęciu pracy z tym typem zadania konserwacji, należy wprowadzić liczbę dni w **polu opóźnienie według** dni Liczby dodatnie reprezentują dni po rozpoczęciu pokrewnego zadania, a liczby ujemne oznaczają dni przed planowanym rozpoczęciem zadania pokrewnego. Jeśli na przykład zostanie wprowadzona **wartość 5**, następne zadanie rozpocznie się po upływie pięciu dni od rozpoczęcia zadania związanego z typem zadania serwisowego. Jeśli na przykład zostanie wprowadzona **wartość -3**, następne zadanie rozpocznie się po trzy dni przed zaplanowanym rozpoczęciem zadania związanego z typem zadania serwisowego.

    > [!NOTE]
    > Jeśli zostanie dodany więcej niż jeden wiersz typu zadania obsługi, sekwencja wierszy wskazuje kolejność, w jakiej powinny być wykonywane. Sekwencja rozpoczyna się od początku listy.

11. Na skróconej karcie **Typy składników majątku** można dodać typy środków trwałych do typu zadania konserwacji.

![Strona Typy zadań konserwacji.](media/06-setup-for-work-orders.png)

## <a name="create-maintenance-job-type-default-lines-and-related-forecasts-maintenance-checklists-tools-description-and-attachments"></a>Utwórz zadanie obsługi typu wiersze domyślne i powiązane prognozy, listy kontrolne obsługi, narzędzia, opis i załączniki

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zadania** \> **Ustawienia domyślne typu zadania konserwacji**.

    – lub –

    Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zadania** \> **Typy zadań konserwacji**, wybierz typ zadania konserwacji i następnie **Ustawienia domyślne typu zadania konserwacji**.

2. Wybierz pozycję **Nowy**.
3. W obszarze **lokalizacjaczynności konserwacyjnych**, **typ składnika majątku**, **producent**, **model** i **składnik majątku**, wybierz odpowiednie wartości w zależności od wybranego typu zadania konserwacji wartość domyślna powinna wyglądać inaczej.
4. W polu **Typ zadania konserwacji** wybierz typ zadania obsługi, jeśli nie zostało ono automatycznie wybrane.
5. W polach **Wariant typu zadania konserwacji** i **Zawód** zadania serwisowego wybierz wariant i zawód związany z typem zadania konserwacji w miarę potrzeb.
6. Wybierz **Prognoza**.
7. W ramach **Domyślna prognoza konserwacji typu zadania konserwacji** można tworzyć prognozy dotyczące godzin, towarów i wydatków Na odpowiednich kartach zaznacz opcję **Dodaj**, a następnie wybierz opcje, aby utworzyć wymagane prognozy dla typu zadania konserwacji.
8. Na karcie **Prognoza dla pozycji** można wybrać wymiary magazynowe, które powinny być wyświetlane w wierszu pozycji. Wybierz **Zapasy** \> **Wymiary**, wybierz wymiary do pokazania, ustaw opcję **Zapisz ustawienia** jako **Tak**, a następnie **OK**.
9. W karcie **Prognoza dla pozycji** wybierz **Używająca pozycja** jeśli chcesz uzyskać informacje o tym, gdzie w module Zarządzaniu składnikami majątku jest używany element w wybranym wierszu, w odniesieniu do składników majątku, zadań konserwacji, części zamiennych i zleceń pracy. 

    Sumy **Sumy prognozy konwersacji** na skróconej karcie zawiera przegląd sum prognoz. Przegląd obejmuje łączną liczbę godzin i wierszy prognozy, które zostały utworzone.

    > [!NOTE]
    > Aby skopiować ustawienia prognozy z innego typu zadania obsługi, wybierz opcję **Kopiuj prognozę**, a następnie wybierz typ zadania obsługi, z którego zostaną skopiowane ustawienia.

11. Wybierz **Zapisz**, żeby zapisać zmiany.
12. Zamknij zadanie **Domyślna prognoza konserwacji typu zadania konserwacji**, aby powrócić do strony **Ustawienia domyślne typu zadania konserwacji** .
13. Wybierz **Lista kontrolna konserwowanego składnika majątku**.
14. Na stronie **Lista kontrolna ustawień domyślnych typów zadań konserwacji** można dodawać wiersze listy kontrolnej w celu wybrania domyślnego typu zadania obsługi. W skróconej karcie **Wiersze kontrolne konserwowanego składnika majątku** wybierz pozycję **Nowe**, aby dodać wiersz listy.

    Numer wiersza jest automatycznie wstawiany w polu **Numer wiersza** w celu wskazania kolejności środków trwałych w wierszu kontrolnym czynności konserwacyjnych. Numery wierszy można edytować w razie konieczności. Po utworzeniu pierwszego wiersza listy kontrolnej eksploatacji wybierz wiersz, a następnie naciśnij klawisz **strzałki w dół**, aby dodać wiersz poniżej. Można również wybrać wiersz listy prac, a następnie wybrać opcję **nowy.** W tym przypadku nowy wiersz zostanie dodany powyżej wybranego wiersza listy kontrolnej obsługi.

15. W polu **typ** wybierz typ wiersza, a następnie Dodaj informacje związane z typem listy kontrolnej obsługi. Aby uzyskać opis dostępnych typów i pól pokrewnych, zajrzyj do sekcji [Utwórz szablon listy kontrolnej konserwacji](#create-a-maintenance-checklist-template).

    > [!NOTE]
    > Aby skopiować ustawienia listy kontrolnej konserwowanego składnika majątku z innego typu zadania konserwacji, wybierz opcję **Kopiuj listę kontrolną konserwowanego składnika majątku**, a następnie wybierz typ zadania obsługi, z którego zostaną skopiowane ustawienia.
    >
    > Możesz utworzyć nowy szablon albo wybrać jedeną z istniejących list kontrolnych konserwowanego składnika majątku. Następnie można ponownie użyć szablonu na wiele list kontrolnych dotyczących obsługi. Nowy szablon będzie dokładną kopią listy kontrolnej aktywnej obsługi technicznej. Wybierz **Stwórz szablon** i nadaj szablonowi nazwę. Aby zamienić istniejącą listę kontrolną obsługi na pojedynczy wiersz odwołujący się do nowego szablonu należy określić opcję **Zamień** na wartość **tak**. Zawartość szablonu można wyświetlić na stronie **Szczegóły szablonów kontrolnej konserwowanego składnika majątku**.

16. Wybierz **Zapisz**, żeby zapisać zmiany.
17. Wróć do strony **Ustawienia domyślne typu zadania konserwacji**.
18. Wybierz **Narzędzia**.
19. Na **Domyślne narzędzia typu zadania konserwacji** można dodawać narzędzia (zasoby), które powinny być używane dla danego typu zadania obsługi. Wybierz **Nowy** i wybierz narzędzie w polu **Zasób**.

    > [!NOTE]
    > Aby skopiować ustawienia narzędzia z innego typu zadania obsługi, wybierz opcję **Kopiuj narzędzia**, a następnie wybierz typ zadania obsługi, z którego zostaną skopiowane ustawienia.

20. Wybierz **Zapisz**, żeby zapisać zmiany.
21. Wróć do strony **Ustawienia domyślne typu zadania konserwacji**.
22. Wybierz **Opis pracy**.
23. Na stronie **Opis pracy** wybierz opcję **Edytuj**, a następnie Dodaj opis, który jest powiązany z wybranym ustawieniem domyślnym typu zadania obsługi.
24. Wybierz **Zapisz**, aby zapisać opis.

    Jeśli w tym miejscu zostanie dodany opis pracy, zastąpi on wszelkie opisy skonfigurowane dla typu zadania obsługi na stronie **Typy zadań konserwacji**. Jeśli w tym polu nie zostanie dodany opis pracy, zostanie użyty dowolny Opis ustawiony dla danego typu zadania obsługi. Opisy są automatycznie przenoszone do zleceń roboczych, w których jest używany typ zadania konserwacji lub domyślny typ zadania serwisowego.

25. Wróć do strony **Ustawienia domyślne typu zadania konserwacji**.
26. Aby skonfigurować załączniki w wybranym wierszu typu zadania obsługi, wybierz opcję **Dołącz dokumenty**. Załączniki skonfigurowane dla zadania obsługi typu domyślny wiersz są automatycznie uwzględniane w wierszach zlecenia produkcyjnego, w którym jest używany ten wiersz domyślny typu zadania serwisowego.
27. Wybierz **Nowy** i następnie wybierz typ dokumentu.
28. Załaduj dokument lub plik.
29. Skonfiguruj pola na karcie **Załączniki**. W ustawieniach załącznika do systemu używana jest funkcja standardowego ustawienia dokumentu.
30. Wybierz **Zapisz**, aby zapisać załącznik.

    > [!NOTE]
    > Załączniki w ramach zadania obsługi typ wiersz domyślny jest drukowany razem z raportem zlecenia produkcyjnego tylko wtedy, gdy typy załączników są zaznaczone na karcie typy **Tyoy dokumentów** na stronie **Parametry zarządzania składnikami majątku** (**Zarządzanie składnikami majątku** \> **ustawienia** \> **Parametry zarządzania składnikami majątku**). Przykładami załączników są wskazówki wyjaśniające sposób wykonania określonego zadania lub wstępnie zdefiniowanej listy kontrolnej obsługi (jeśli nie jest używana funkcja listy kontrolnej obsługi dla wierszy domyślnych typu zadania obsługi).

    Na stronie **ustawienia domyślne typu zadania konserwacij** w każdym wierszu wyświetlana jest liczba prognozowanych godzin, a także liczba wierszy utworzonych dla towarów, wydatków, list kontrolnych konserwacji i narzędzi. W **Składniki majątku** wyświetlana jest liczba aktywnych składników majątku, dla których dany typ domyślny zadania serwisowego jest aktualnie używany.

31. Aby skopiować domyślny typ zadania serwisowego do innego typu zadania obsługi, należy wybrać domyślny wiersz zadania obsługi, aby skopiować inne ustawienia do systemu, wybierz opcję **Kopiuj ustawienia**, a następnie wybierz typ zadania konserwacji domyślne do skopiowania.
32. Aby wyświetlić listę środków trwałych, planów serwisowych lub zaokrąglenia konserwacyjnego, które aktualnie używają wiersza domyślnego typu zadania obsługi, zaznacz wiersz, a następnie wybierz opcję **używaneprzez**.

![Strona Ustawienia domyślne typu zadania konserwacji.](media/07-setup-for-work-orders.png)

Jeśli system wybierze domyślną wartość typu zadania obsługi, która powinna być używana w wierszu zlecenia, wybór jest oparty na składniku aktywów i ustawieniach powiązanego typu środka trwałego. Zarządzanie środkami trwałymi przechodzi między wszystkimi domyślnymi rekordami, które są powiązane z typem zadania konserwacji związanym z typem środka, aby można było sprawdzić, czy takie dopasowanie jest możliwe. W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową. Innymi słowy, aby znaleźć najbardziej konkretną kombinację, najpierw należy sprawdzić, czy jest możliwe dopasowanie dla pola **Zawód**. Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Wariant typu zadania konserwacji**. Jeśli nie zostanie znaleziony żaden odpowiednik, system sprawdza zgodność dla pola typu **zadanie konserwacji** itd. (**Zawód**, później **Wariant typu zadania konserwacji**, później **Typ zadania konserwacji**, później **Składnik majatku**, później **Model**, późńiej **Producent** i **Typ składnika majątku**). Jeśli nie zostanie znaleziony żaden odpowiednik, używany jest typ zadania konserwacji domyślny, w którym jest wybrany tylko grupa projektu.

Identyfikator działania projektu jest automatycznie powiązany z każdym tworzonym wierszem domyślnym typu zadania obsługi. Działanie projektu jest tworzone w projekcie prognozy wybranym w polu projekt **Projekt prognozy konserwacji** na karcie **składniki majątku** na stronie **Parametry zarządzania składnikami majątku**. Celem działania projektu jest zarządzanie prognozami według godzin, towarów i wydatków w odniesieniu do zleceń produkcyjnych. Prognozy typu zadania konserwacji są automatycznie przenoszone do wiersza zlecenia produkcyjnego i są kopiowane z projektu prognozy do projektu zlecenia produkcyjnego tworzonego dla wiersza zlecenia Celem działania projektu jest zarządzanie prognozami według zleceń pracy.

Istnieje możliwość skonfigurowania zadania wsadowego w celu zaktualizowania typu zadania konserwacji w regularnych odstępach czasu lub zadania, które można uruchomić ręcznie. Aby utworzyć zadanie wsadowe lub uruchomić aktualizację ręczną, należy wybrać **Zarządzanie składnikami majątku** \> **Okresowe** \> **Konserwacja zapobiegawcza** \> **Aktualizuj odwołania domyślnego typu zadania konserwacji**.

## <a name="overview-of-maintenance-job-types-that-are-related-to-assets"></a>Przegląd typów zadań obsługi związanych z składnikami majątku

Po utworzeniu wymaganych kombinacji domyślnych dla zadania konserwacji można skorzystać z strony **wszystkie składniki majątku**, aby uzyskać przegląd informacji o bieżącym typie zadania konserwacji, które jest związane z określonym środkiem trwałym. Przegląd zawiera wszystkie kombinacje domyślne typu zadania obsługi, które mogą być używane w przypadku typu środka trwałego wybranego dla środka trwałego Te kombinacje obejmują kombinacje, które mają różne warianty typu zadania obsługi oraz zawód zadań konserwacyjnych.

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku** lub **Aktywne składniki majątku**.
2. Z listy wybierz składnik aktywów, aby wyświetlić przegląd kombinacji typów zadań konserwacyjnych dla.
3. W okienku akcji, na karcie **ogólne**, w grupie **informacje pokrewne** wybierz **typy zadań konserwacji**.

    W lewym okienku na **Typy zadań konserwacji składnika majątku** jest wyświetlana lista wszystkich kombinacji typów zadań serwisowych, które są powiązane z wybranym środkiem trwałym.

4. Wybierz kombinację typu zadania konserwacji, aby wyświetlić powiązaną konfigurację list kontrolnych konserwacji, prognoz i narzędzi. W **Szczegóły** dotyczącej **typu zadania konserwacji** skróconej karcie wyświetlana jest liczba powiązanych list kontrolnych konserwacji, godzin prognozowanych, towarów itp., które są powiązane z wybraną kombinacją typów zadań konserwacyjnych.
5. Aby wyświetlić szczegóły wybranego typu zadania obsługi, należy wybrać **typy zadań konserwacji**.

![Strona Typy zadań konserwacji składnika majątku.](media/08-setup-for-work-orders.png)

## <a name="automatic-update-of-maintenance-job-type-forecasts"></a>Automatyczna aktualizacja prognoz typu zadania obsługi

W module Zarządzanie składnikami majątku można automatycznie aktualizować zmiany prognoz zleceń, dotyczące kosztów godzinowych, kosztówtowarów i wydatków, które zostały zaktualizowane w innych modułach. W ten sposób można zagwarantować, że w prognozach typu zadanie konserwacji zawsze będą używane najnowsze koszty własne.

1. Wybierz **Zarządzanie składnikami majątku** \> **Okresowe** \> **Prognoza** \> **Aktualizuj prognozę typu zadania konserwacji**.
2. W oknie **Aktualizuj prognozę typów zadań konserwacji**, dla **Rekordy do uwzględnienia** na skróconej karcie, można dodawać wybrane opcje dla konkretnych typów zadań obsługi, które są wymagane. Wybierz **Filtruj**, a następnie **wybierz**, aby wybrać opcje.
3. Na skróconej karcie **uruchom w tle** w razie potrzeby możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe.
4. Wybierz przycisk **OK**, aby rozpocząć aktualizację prognozy.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]