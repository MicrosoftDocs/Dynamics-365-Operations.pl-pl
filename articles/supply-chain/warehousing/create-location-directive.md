---
title: Tworzenie dyrektyw lokalizacji
description: W tym temacie opisano sposób tworzenia dyrektyw lokalizacji. Dyrektywy lokalizacji to zdefiniowane przez użytkownika zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego.
author: Mirzaab
manager: tfehr
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-28
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 4f634b7f526fd198b394af6d3870c43ee560813e
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016777"
---
# <a name="create-location-directives"></a>Tworzenie dyrektyw lokalizacji

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia dyrektyw lokalizacji. Dyrektywy lokalizacji to zdefiniowane przez użytkownika zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego. Na przykład w ramach transakcji zamówienia sprzedaży, dyrektywa lokalizacji określa, gdzie towary zostaną pobrane i gdzie zostaną umieszczone pobrane zapasy.

> [!NOTE]
> Ten temat dotyczy funkcji w module **Zarządzanie magazynem**. Nie ma zastosowania do funkcji w module [Zarządzanie zapasami](../inventory/inventory-home-page.md).

Funkcja dyrektyw lokalizacji umożliwia wykonywanie następujących zadań:

- Odkładanie towarów przychodzących.
- Pobieranie i ustawianie etapów towarów dla transakcji wyjściowych.
- Pobranie i odkładanie surowców do produkcji.
- Uzupełnienie lokalizacji.

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było utworzyć dyrektywę lokalizacji, należy wykonać poniższe kroki w celu upewnienia się, że są spełnione wymagania wstępne.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Magazyny**.
1. Tworzenie magazynu.
1. Na skróconej karcie **Magazyn** ustaw opcję **Użyj procesów zarządzania magazynami** na *Tak*.
1. Utwórz lokalizacje, typy lokalizacji, profile lokalizacji i formaty lokalizacji. Aby uzyskać więcej informacji, przejrzyj [Konfigurowanie lokalizacji w magazynie z obsługą WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Tworzenie oddziałów, stref i grupy stref. Aby uzyskać więcej informacji, przejrzyj [Konfiguracja magazynu](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) i [Konfigurowanie lokalizacji w magazynie z obsługą WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="setup"></a>Konfiguracja

### <a name="create-location-directives"></a>Tworzenie dyrektyw lokalizacji

Aby utworzyć dyrektywę lokalizacji, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W okienku listy w polu **Typ zlecenia pracy** określ typ transakcji magazynowej, dla której tworzona jest dyrektywa lokalizacji.
1. W okienku akcji wybierz opcję **Nowa** , aby utworzyć nową dyrektywę lokalizacji.
1. W przypadku nowej dyrektywy lokalizacji należy określić pola opisane w poniższej tabeli.

    | Pole | opis |
    |---|---|
    | Identyfikator sekwencyjny | Umożliwia wprowadzenie liczby całkowitej wskazującej pozycję sekwencji dyrektywy lokalizacji. Stanowiska sekwencyjne określają, kiedy każda dyrektywa lokalizacji jest przetwarzana dla wybranego typu zlecenia pracy. |
    | Imię i nazwisko | Umożliwia wprowadzenie dyrektywy lokalizacji. | 
    | Typ pracy | Wybierz rodzaj pracy, którą chcesz wykonać. Lista wartości zależy od typu transakcji magazynowej, która jest wartością wybraną w polu **Typ zlecenia pracy**. Mogą być dostępne następujące wartości:<ul><li>**Odłożenie** — dyrektywa lokalizacji będzie próbować odnaleźć najlepszą lokalizację, aby umieścić lub zlokalizować zapasy, które są dostępne w systemie w wyniku korekt przyjęcia, produkcji lub zapasów. Dyrektywa lokalizacji jest również używana do definiowania lokalizacji lokalizacji docelowej na przełożonym lub w końcowej fazie dostawy w procesie wychodzącym.</li><li>**Pobranie** — dyrektywa lokalizacji podejmie próbę znalezienia najlepszych lokalizacji, z których można zarezerwować zapasy z magazynu (Tworzenie pracy). Pobranie można zrealizować (wiersz pracy pobrania może być zamknięty), nawet jeśli praca nie jest wykonywana. Użytkownik może dokończyć pobieranie fizyczne. W systemie ta akcja jest krokiem pobrania. Użytkownik może następnie anulować z urządzenia przenośnego i wykonać pracę (na przykład odłożenia) później. Jednak nagłówek pracy jest najpierw zamykany po zakończeniu końcowego wstawiania.</li><li>**Inwentaryzacja** , **Korekty** , **Niestandardowe** , **Zmiana stanu zapasów** , **Tworzenie numeru identyfikacyjnego** , **Drukowanie** , **Zmiana stanu** , **Pakowanie do zagnieżdżonych numerów identyfikacyjnych** — Tych wartości nie można używać w żadnej konfiguracji dyrektywy lokalizacji.</li></ul> |
    | Oddział | Wybierz oddział, w którym powinna być ukończona praca. |
    | Magazyn | Wybierz lokalizację magazynową, w której powinna być ukończona praca. |
    | Kod dyrektywy | Wybierz kod dyrektywy, aby kierować wyborem dyrektyw lokalizacji, które są powiązane z szablonem pracy, wstaw wiersze, w których ten kod jest przypisany. Na stronie **kodowej dyrektywy** można utworzyć nowe kody, za pomocą których można połączyć szablon pracy z dyrektywą lokalizacji. Możesz również użyć tej strony do ustanowienia połączenia między dowolnym wierszem szablonu pracy a dyrektywą dotyczącą lokalizacji (taką jak drzwi do hali lub lokalizacja sceny). Aby uzyskać informacje na temat konfigurowania kodu dyrektywy za pomocą szablonu pracy, zobacz [Kontrolowanie pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji](control-warehouse-location-directives.md).<p>Jeśli kod dyrektywy jest ustawiony, kiedy praca musi zostać wygenerowana, system przeszuka dyrektywy lokalizacji według kodu dyrektywy, a nie według sekwencji. W ten sposób można bardziej precyzyjnie określić szablon lokalizacji, który jest używany do określonego kroku w szablonie roboczym, na przykład etapu przygotowania materiałów.</p> |
    | Kod dyspozycji | Wybierz kod dyspozycji do przekierowania odłożenie przyjętych towarów w lokalizacji. (Aby uzyskać więcej informacji, należy zapoznać się z tematem [Ustawianie kodów dyspozycji](tasks/set-up-dispositions-codes.md).) To pole jest dostępne tylko wtedy, gdy w polu **Typ zlecenia produkcyjnego** jest ustawiona wartość *Zamówienia zakupu* , *Zamówienia zwrotu* lub *Ukończono odkładanie wyrobów*. |
    | Wiele jednostek JSZ | Ustaw tę opcję na *Tak* , aby używać wielu jednostek magazynowych (SKU) w lokalizacji. Na przykład ta opcja musi mieć wartość *Tak* dla drzwi w kieszeni.<p>Jeśli opcja **Wiele jednostek JSZ** jest ustawiona na *Tak* , lokalizacja wstawienia zostanie określona w pracy (zgodnie z oczekiwaniami). Jednak lokalizacja odkładania będzie w stanie obsłużyć odkładanie wielu elementów tylko wtedy, gdy praca zawiera różne kody SKU, które muszą zostać pobrane i odłożone, a nie, jeśli praca zawiera tylko jedną jednostkę SKU, którą należy umieścić.</p><p>Jeśli opcja **Wiele jednostek JSZ** jest ustawiona na *Nie* , lokalizacja odkładania zostanie określona tylko wtedy, gdy opcja sprzedaży ma tylko jeden typ jednostki SKU.</p><p>Aby użyć obu podejść, musisz określić dwie linie, które mają taką samą strukturę i konfigurację, ale ustaw opcję **Wiele jednostek JSZ** na *Tak* dla jednej z linii i *Nie* dla drugiej. Innymi słowy, dwie identyczne dyrektywy lokalizacji są wymagane dla operacji odkładania, nawet jeśli nie musisz rozróżniać między jedną i wieloma jednostkami SKU w identyfikatorze pracy. Musisz także ustawić dyrektywę lokalizacji do pobrania, jeśli masz zamówienie, które obejmuje więcej niż jeden przedmiot.</p><p>**Uwaga:** Jeśli ustawisz opcję **Wiele jednostek JSZ** na *Tak* dla dyrektywy lokalizacji typu pracy *Odłożenie* , system zawsze wybierze pierwszy wiersz dyrektywy lokalizacji, niezależnie od inne ograniczenia utworzone na liniach.</p> |

1. Opcjonalnie: W okienku akcji wybierz **Edytuj zapytanie** w celu wybierania lokalizacji lub określ ograniczenia dotyczące wybierania określonej dyrektywy lokalizacji.
1. Na skróconej karcie **Wiersze** , utwórz jeden lub więcej wierszy do określania jednostek i do znalezienia lub rezerwowania ilości w magazynie.
1. W każdym nowym wierszu ustaw pola zgodnie z opisem w poniższej tabeli.

    | Pole | opis |
    |---|---|
    | Identyfikator sekwencyjny | Umożliwia wprowadzenie liczby całkowitej wskazującej pozycję sekwencji dyrektywy lokalizacji. Stanowiska sekwencyjne określają, kiedy każda dyrektywa lokalizacji jest przetwarzana dla wybranego typu pracy. |
    | Ilość od | Określ zakres ilości dla sytuacji, gdy trzeba wybrać kolejność wewnątrz siatki. Wybierz jednostkę miary dla ilości w polu **Jednostka**. |
    | Do ilości | Określ końcowy zakres ilości, w którym ma zostać wybrana sekwencja środkowej siatki. Wybierz jednostkę miary dla ilości w polu **Jednostka**. |
    | Jednostka | Umożliwia wybranie jednostki miary dla towarów.<p>Można określić ilość minimalną i maksymalną ilość, której ma dotyczyć dyrektywa. Można również określić, że dana dyrektywa powinna być używana w odniesieniu do określonej jednostki magazynowej. Pole **Jednostka** w wierszu jest używane tylko do oceny ilości.</p><p>Aby określić, czy wiersz dotyczący dyrektywy lokalizacji ma być stosowany, system ocenia ilości, korzystając z wartości **Jednostki** określonej w wierszu. Za każdym razem, gdy uzyskuje się dostęp do wiersza dyrektywy lokalizacji, system próbuje przekształcić jednostkę zapotrzebowania na jednostkę określoną w wierszu. Jeśli konwersja jednostek nie istnieje, system przejdzie do następnego wiersza.</p> |
    | Zlokalizuj ilość | To pole jest ważne tylko w przypadku próby odłożenia lub zlokalizowania ilości w magazynie. Innymi słowy, jest on prawidłowy tylko w przypadku pracy *Odłożenie*. Wybierz metodę, która jest używana do sprawdzania, czy ilość znajduje się w zakresie zdefiniowanym w polach **Od ilości** i **Do ilości**. W przypadku dyrektywy lokalizacji dla transakcji przychodzących, wybierz jedną z następujących opcji:<ul><li>**Liczba tablic rejestracyjnych** — Aby ocenić, czy ilość mieści się w docelowym zakresie ilości, użyj ilości na otrzymanej tablicy rejestracyjnej.</li><li>**Ilość w jednostkach** — Aby ocenić, czy ilość mieści się w docelowym zakresie ilości, użyj ilości, która jest jednostkowa podczas transakcji. Na przykład w magazynie, jeśli możesz otrzymać ilość 1000 i podzielić ją na 10 numerów identyfikacyjnych, z których każda ma ilość 100, możesz użyć ilości 1000 pozycji zamiast liczby 100 numerów identyfikacyjnych.</li><li>**Pozostała ilość** — Aby ocenić, czy ilość mieści się w docelowym zakresie ilości, użyj ilości, która pozostała do odebrania w wierszu zamówienia zakupu, który jest aktualnie rejestrowany.</li><li>**Oczekiwana ilość** — Aby ocenić, czy ilość mieści się w docelowym zakresie ilości, użyj całkowitej ilości z wiersza zamówienia zakupu, niezależnie od ilości, która została już odebrana.</li></ul> |

1. Opcjonalnie: Na skróconej karcie **Wiersze** możesz ustawić następujące dodatkowe pola.

    | Pole | opis |
    |---|---|
    | Ogranicz według jednostki | To pole wyboru należy zaznaczyć, aby ograniczyć jednostki miary, które są uznawane za prawidłowe kryteria wyboru dla wierszy dyrektywy lokalizacji. Po określeniu jednostek miary tylko towary, w których jednostka pasuje do co najmniej jednej jednostki zdefiniowanej dla grupy sekwencji jednostek, będą uznawane za prawidłową dla wybranego wiersza.<p>Na przykład jednostka jest ograniczona do palet, a towar jest skojarzony z grupą sekwencji jednostek zawierającą jednostkę *palet*. W takim przypadku towary będą uznawane za prawidłową opcję dla dyrektywy lokalizacji.</p><p>Jednak pole wyboru **Ogranicz według jednostek** nie kontroluje jednostek lub jednostek stosowanych w wierszach pracy. Ograniczenie jednostkowe dotyczy tylko jednostek, które są udostępniane za pośrednictwem grupy sekwencji jednostek.</p><p>Na przykład element jest powiązany z grupą sekwencji jednostek, która obejmuje zarówno *palety* , jak i *szt*. Zdefiniowano jednostkę miary, w której 1 paleta = 100 sztuk, a dyrektywa lokalizacji wykorzystuje funkcję **Ogranicz według jednostki** tylko dla palet. Ponadto zdefiniowano szablon pracy, który ogranicza tworzenie nagłówków pracy do 50 szt. W takim przypadku zostaną utworzone linie robocze po 50 sztuk.</p><p>Aby określić jednostka miary ograniczeń, należy wykonać następujące kroki</p><ol><li>Na skróconej karcie **Wiersze** wybierz opcję **Ogranicz według jednostki**. Przycisk ten staje się dostępny dopiero po zaznaczeniu pola wyboru **Ogranicz według jednostki** w wierszu, a następnie wybraniu opcji **Zapisz**.</li><li>W polu **Jednostka** wybierz jednostkę miary w celu ustawienia ograniczenia dla procesu pobrania i odłożenia.</li></ol> |
    | Zaokrąglij do jednostki | Wybierz tę opcję, aby wskazać, czy pobranie surowca powinno być zaokrąglane w górę do wielokrotności jednostki załadunkowej określonej w polu **Ogranicz według jednostki**. To pole działa tylko dla pobrań surowca i dyrektyw lokalizacji o typie *Pobranie*. |
    | Zlokalizuj ilość opakowań | Wybierz to pole wyboru, jeśli ilość jednostek załadunkowych została określona na stronie **Zamówienie sprzedaży**. Po zaznaczeniu tego pola wyboru tylko lokalizacje z daną ilością jednostek załadunkowych będą zaznaczone. |
    | Zezwalaj na podział | Zaznaczenie tego pola wyboru powoduje dzielenie ilości na wiele lokalizacji. |
    | Szablon natychmiastowego uzupełniania zapasów | Utwórz połączenie z szablonem uzupełniania zapasów, aby uzupełnienie było uruchamiane natychmiast, jeśli towary nie zostaną przydzielone. Jeśli to pole jest pozostawione puste, uzupełnianie zapasów nie rozpocznie się dopóki, dopóty wszystkie wiersze dyrektywy lokalizacji nie zostaną przetworzone.<p>To pole jest dostępne tylko w przypadku wybranych typów zleceń produkcyjnych, na przykład *Zamówień sprzedaży* i *Pobrania surowca*.</p> |

1. Na skróconej karcie **Akcje dyrektywy lokalizacji** , kliknij przycisk **Nowy** w celu wybrania lokalizacji lub zakresu lokalizacji.
1. W polu **Numer sekwencyjny** jest wyświetlana sekwencja, w której dyrektywa lokalizacji będzie przetwarzana dla wybranego typu pracy. Można zmienić taką sekwencję. Należy jednak zachować ostrożność w przypadku numerów sekwencyjnych dla akcji dyrektywy lokalizacji, ponieważ akcje dyrektywy lokalizacji będą zawsze uruchamiane w tej kolejności.
1. W polu **Nazwa** wprowadź nazwę działania dyrektywy lokalizacji. Bądź konkretny, aby było jasne, na czym polega akcja.
1. Opcjonalnie: Kliknij **Edytuj zapytanie** , w celu zmodyfikowania lokalizacji magazynowych i innych kryteriów.
1. Opcjonalnie: Można wybrać następujące dodatkowe pola dla dyrektywy lokalizacji.

    | Pole | opis |
    |---|---|
    | Użycie stałej lokalizacji | Wybierz lokalizacje, które powinna uwzględniać dyrektywa dotycząca lokalizacji:<ul><li>**Lokalizacje stałe i niestałe** – dyrektywa lokalizacji będzie brać pod uwagę wszystkie lokalizacje.</li><li>**Tylko stałe lokalizacje dla produktu** – dyrektywa lokalizacji będzie brać pod uwagę tylko stałe lokalizacje dla produktów.</li><li>**Tylko stałe lokalizacje dla wariantu produktu** – dyrektywa lokalizacji będzie brać pod uwagę tylko stałe lokalizacje dla wariantów produktów.</li></ul> |
    | Pozwól na ujemny poziom zapasów | Zaznacz to pole wyboru, aby zezwolić na ujemny poziom zapasów w określonej lokalizacji magazynowej. |
    | Partia włączona | Zaznaczenie tego pola wyboru umożliwia wykorzystanie strategii wsadowej dla towarów, które obsługują operacje wsadowe. Jeśli to pole wyboru jest zaznaczone, a w polu **Strategia** jest ustawiona wartość *Brak* , system przejdzie do następnego wiersza akcji. |
    | Strategia | Wybierz strategię, której powinna używać dyrektywa lokalizacji:<ul><li>**Brak** — nie będzie używana żadna strategia.</li><li>**Dopasuj ilość opakowań** – ta strategia służy do sprawdzania, czy lokalizacja pobrania ma określoną ilość w paczce. Ta strategia jest prawidłowa tylko w przypadku, gdy w polu **Typ pracy** ustawiono wartość *Pobieranie*.</li><li>**Konsolidacja** – Ta strategia konsoliduje elementy w określonej lokalizacji, gdy podobne produkty są już dostępne. Ta strategia jest prawidłowa tylko w przypadku, gdy w polu **Typ pracy** ustawiono wartość *Odłożenie*. W typowej konfiguracji modułu odłożenie system podejmuje próbę konsolidacji w pierwszym wierszu akcji, a następnie w drugim wierszu akcji próbuje umieścić bez konsolidacji. Konsolidacja towarów usprawnia późniejsze pobieranie.</li><li>**Rezerwacja partii FEFO** – ta strategia jest używana, gdy zapasy są znajdowane przy użyciu daty ważności partii i przydzielane na potrzeby rezerwacji partii. Strategia rezerwacji partii pierwszego wygaśnięcia, pierwsze wyszło (FEFO) jest również używana, gdy zapasy są lokalizowane przy użyciu daty ważności partii oprócz daty ważności. Tej strategii można używać tylko dla towarów obsługujących operacje wsadowe. Ta strategia jest prawidłowa tylko w przypadku, gdy w polu **Typ pracy** ustawiono wartość *Pobieranie*. Po wybraniu tej strategii użytkownik zastępuje dowolne sortowanie kwerendy dla numerów partii, które są stosowane.</li><li>**Zaokrąglij w górę do pełnego nr id.** – Ta strategia zaokrągla ilość zapasów, tak aby była zgodna z ilością na tablicach rejestracyjnych przypisaną do towarów, które muszą zostać pobrane. Ta strategia może być używana tylko do określania typu uzupełnienia w dyrektywach lokalizacji i tylko wtedy, gdy pole **Typ pracy** jest ustawione jako *Pobranie*.</li><li>**Pusta lokalizacja bez przychodzącej pracy** – ta strategia jest używana do znajdowania pustych lokalizacji. Lokalizacja jest uważana za pustą, jeśli nie ma w niej fizycznych zapasów i nie ma żadnych oczekiwanych prac przychodzących. Ta strategia jest prawidłowa tylko w przypadku, gdy w polu **Typ pracy** ustawiono wartość *Odłożenie*.</li></ul> |

## <a name="example-of-the-use-of-location-directives"></a>Przykład zastosowania dyrektyw lokalizacji

W tym przykładzie zostanie omówiony proces zamówienia zakupu, w którym dyrektywa lokalizacji musi znaleźć wolne zdolności produkcyjne w magazynie dla pozycji magazynowych, które zostały właśnie zarejestrowane w doku rozładunkowym. Najpierw trzeba znaleźć wolne zdolności produkcyjne w magazynie poprzez konsolidację z istniejącymi zapasami dostępnymi. Jeśli konsolidacja jest niemożliwa, trzeba znaleźć pustą lokalizację.

W tym scenariuszu należy zdefiniować dwa działania dyrektywy lokalizacji. Pierwsze działanie w sekwencji musi wykorzystywać strategię **Konsolidacja** , a drugie powinno używać strategii **Pusta lokalizacja bez przychodzącej pracy**. O ile nie zdefiniowano trzeciego działania dla scenariusza przepełnienia, możliwe są dwa wyniki, jeśli w magazynie nie ma więcej zdolności produkcyjnych: praca może być tworzona nawet bez definiowania lokalizacji lub proces tworzenia pracy może się nie powieść. Wynik jest określany według ustawień na stronie **Błędy dyrektyw lokalizacji** , gdzie można wybrać opcję **Zatrzymaj pracę przy błędzie dyrektywy lokalizacji** dla każdego typu zlecenia.

## <a name="next-step"></a>Następne kroki

Po utworzeniu dyrektywy lokalizacji, każdy kod dyrektywy można skojarzyć z kodem szablonu pracy dla utworzenia pracy. Aby uzyskać więcej informacji, zobacz [Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="technical-information-for-system-admins"></a>Informacje techniczne dla administratorów systemu

Jeśli nie masz dostępu do stron, które są używane do ukończenia tego zadania, skontaktuj się z administratorem systemu i podaj informacje, które przedstawiono w poniższej tabeli.

| Kategoria | Wymaganie wstępne |
|---|---|
| Configuration Keys | Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**. Rozwiń klucz licencji **handlowej** , a następnie wybierz klucz konfiguracji **Zarządzanie magazynem i transportem**. |
