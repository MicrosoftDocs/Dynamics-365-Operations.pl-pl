---
title: Praca z dyrektywami lokalizacji
description: W tym temacie opisano sposób pracy z dyrektywami lokalizacji. Dyrektywy lokalizacji to zdefiniowane przez użytkownika zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego.
author: Mirzaab
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-11-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 91482bb24356a14a8d44e887620548cdf6f4c5d3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838401"
---
# <a name="work-with-location-directives"></a>Praca z dyrektywami lokalizacji

[!include [banner](../includes/banner.md)]

Dyrektywy lokalizacji to zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego. Na przykład w ramach transakcji zamówienia sprzedaży, dyrektywa lokalizacji określa, gdzie towary zostaną pobrane i gdzie zostaną umieszczone pobrane zapasy. Dyrektywy lokalizacji składają się z nagłówka i skojarzonych wierszy. Są one tworzone dla wybranych *typów zleceń produkcyjnych*.

> [!NOTE]
> Ten temat dotyczy funkcji w module **Zarządzanie magazynem**. Nie ma zastosowania do funkcji w module [Zarządzanie zapasami](../inventory/inventory-home-page.md).

Funkcja dyrektyw lokalizacji umożliwia wykonywanie następujących zadań:

- Odkładanie towarów przychodzących.
- Pobieranie i ustawianie etapów towarów dla transakcji wyjściowych.
- Pobranie i odkładanie surowców do produkcji.
- Uzupełnienie lokalizacji.

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było utworzyć dyrektywę lokalizacji, należy wykonać poniższe kroki w celu upewnienia się, że są spełnione wymagania wstępne.

1. Upewnij się, że wymagany klucz licencji jest włączony. Przejdź do **Administrowanie systemem \> Konfiguracja licencji \> Konfiguracja licencji**, rozwiń **Handel** klucz licencji, a następnie wybierz **Zarządzanie magazynem i transportem**. Należy zauważyć, że do tego kroku jest wymagana opcja dostępu administratora.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Magazyny**.
1. Tworzenie magazynu.
1. Na skróconej karcie **Magazyn** ustaw opcję **Użyj procesów zarządzania magazynami** na *Tak*.
1. Utwórz lokalizacje, typy lokalizacji, profile lokalizacji i formaty lokalizacji. Aby uzyskać więcej informacji, przejrzyj [Konfigurowanie lokalizacji w magazynie z obsługą WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Tworzenie oddziałów, stref i grupy stref. Aby uzyskać więcej informacji, przejrzyj [Konfiguracja magazynu](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) i [Konfigurowanie lokalizacji w magazynie z obsługą WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="work-order-types-for-location-directives"></a>Typy zleceń roboczych dyrektyw dotyczących lokalizacji

Wiele pól, które można ustawiać w dyrektywach lokalizacji, jest wspólne dla wszystkich typów zleceń produkcyjnych. Jednak inne pola są charakterystyczne dla poszczególnych typów zleceń produkcyjnych.

![Typy zleceń roboczych dyrektyw dotyczących lokalizacji](media/Location_Directives_Work_Order_Types.png "Typy zleceń roboczych dyrektyw dotyczących lokalizacji")

> [!NOTE]
> Dwa typy zleceń roboczych, *anulowane zadania* i *Inwentaryzacja* są używane tylko w systemie. Nie można utworzyć dyrektyw lokalizacji dla tych typów zleceń roboczych.

W tabelach przedstawionych w poniższych podsekcjach wymieniono pola wspólne i odpowiednie dla typu zamówienia pracownika, które są dostępne po skonfigurowaniu dyrektywy lokalizacji.

### <a name="fields-that-are-common-to-all-work-order-types"></a>Pola wspólne dla wszystkich typów zleceń

W poniższej tabeli wymieniono pola wspólne dla wszystkich typów zleceń produkcyjnych.

| Skrócona karta | Pole |
|---|---|
| Dyrektywy lokalizacji | Typ pracy |
| Dyrektywy lokalizacji | Oddział |
| Dyrektywy lokalizacji | Magazyn |
| Dyrektywy lokalizacji | Kod dyrektywy |
| Dyrektywy lokalizacji | Wiele jednostek JSZ |
| Wiersze | Numer sekwencyjny |
| Wiersze | Ilość od |
| Wiersze | Do ilości |
| Wiersze | Jednostka |
| Wiersze | Zlokalizuj ilość |
| Wiersze | Ogranicz według jednostki |
| Wiersze | Zaokrąglij do jednostki |
| Wiersze | Zlokalizuj ilość opakowań |
| Wiersze | Zezwalaj na podział |
| Działania dyrektywy lokalizacji | Numer sekwencyjny |
| Działania dyrektywy lokalizacji | Imię i nazwisko |
| Działania dyrektywy lokalizacji | Użycie stałej lokalizacji |
| Działania dyrektywy lokalizacji | Pozwól na ujemny poziom zapasów |
| Działania dyrektywy lokalizacji | Partia włączona |
| Działania dyrektywy lokalizacji | Strategia |

### <a name="fields-that-are-specific-to-work-order-types"></a><a name="fields-specific-types"></a>Pola charakterystyczne dla typów zleceń

W poniższej tabeli wymieniono pola charakterystyczne dla poszczególnych typów zleceń produkcyjnych.

| Skrócona karta | Pole | Typ zlecenia |
|---|---|---|
| Dyrektywy lokalizacji | Lokalizuj według | Zamówienia zakupu |
| Dyrektywy lokalizacji | Stosowany kod dyspozycji | Zamówienia zakupu |
| Dyrektywy lokalizacji | Kod dyspozycji | Zamówienia zakupu |
| Dyrektywy lokalizacji | Stosowany kod dyspozycji | Ukończono odkładanie wyrobów |
| Dyrektywy lokalizacji | Kod dyspozycji | Ukończono odkładanie wyrobów |
| Dyrektywy lokalizacji | Stosowany kod dyspozycji | Zamówienia zwrotu |
| Dyrektywy lokalizacji | Kod dyspozycji | Zamówienia zwrotu |
| Dyrektywy lokalizacji | Stosowany kod dyspozycji | Kanban odłożone |
| Dyrektywy lokalizacji | Stosowany kod dyspozycji | Pobieranie Kanban |
| Wiersze | Szablon natychmiastowego uzupełniania zapasów | Zamówienia sprzedaży |
| Wiersze | Szablon natychmiastowego uzupełniania zapasów | Pobranie surowca |
| Wiersze | Szablon natychmiastowego uzupełniania zapasów | Wydanie przeniesienia |
| Wiersze | Szablon natychmiastowego uzupełniania zapasów | Pobieranie Kanban |

## <a name="open-the-location-directives-page"></a>Otwórz stronę dyrektyw lokalizacji

Aby wyświetlić **Dyrektywy lokalizacji**, przejdź do **Zarządzanie magazynem \> Konfiguracja \> Dyrektywy lokalizacji**.

W tym miejscu można wyświetlać, tworzyć i edytować dyrektywy lokalizacji za pomocą poleceń dostępnych w okienku akcji. Pozostałe sekcje tego tematu zawierają informacje dotyczące używania wszystkich pól dostępnych na stronie.

## <a name="action-pane"></a>Okienko akcji

Okienko akcji na **stronie dyrektywy lokalizacji** zawiera przyciski, które umożliwiają tworzenie, edytowanie i usuwanie dyrektyw (**Edycja**, **nowe** i **usuwanie**). Zawiera także następujące przyciski, które umożliwiają dostosowanie kolejności przetwarzania dyrektywy lokalizacji oraz skonfigurowanie kwerendy definiującej kryteria stosowania dyrektywy lokalizacji:

- **Przenieś w górę**— umożliwia przeniesienie wybranej dyrektywy lokalizacji w górę w kolejności. Można na przykład przenieść ją z sekwencji o numer 4 do numeru sekwencyjnego 3.
- **Przenieś w dół**— umożliwia przeniesienie wybranej dyrektywy lokalizacji w dół w kolejności. Można na przykład przenieść ją z sekwencji o numer 4 do numeru sekwencyjnego 5.
- **Edytuj zapytanie** — umożliwia otwarcie okna dialogowego, w którym można zdefiniować warunki, pod jakimi wybrana dyrektywa lokalizacji powinna zostać przetworzona. Może to być na przykład sposób zastosowania tylko do określonego magazynu.

## <a name="location-directives-header"></a>Nagłówek dyrektyw lokalizacji

Nagłówek dyrektywy lokalizacji zawiera następujące pola dla numeru sekwencyjnego i nazwy opisowej lokalizacji:

- **Numer sekwencyjny** — to pole wskazuje sekwencję, z jaką system próbuje zastosować każdą dyrektywę lokalizacji dla wybranego typu zlecenia produkcyjnego. Małe numery są stosowane jako pierwsze. Sekwencję można zmieniać za pomocą przycisków **Przenieś w górę** i **Przenieś w dół** w okienku akcji.
- **Nazwa** – wprowadź opisową nazwę dyrektywy lokalizacji. Ta nazwa ułatwia identyfikowanie ogólnego celu dyrektywy. Na przykład wprowadź *pobieranie zamówienia sprzedaży w magazynie 24*.

## <a name="location-directives-fasttab"></a>Karta skrócona dyrektyw lokalizacji

Pola w **dyrektywach lokalizacji** na skróconej karcie są charakterystyczne dla typu zlecenia produkcyjnego wybranego w polu **Typ zlecenia produkcyjnego** w okienku listy.

- **Typ pracy** – Wybierz rodzaj pracy, którą musi zostać wykonana. Lista wartości zależy od typu transakcji magazynowej, która jest wartością wybraną w polu **Typ zlecenia pracy**. Należy wybrać jedną z następujących opcji:

    - **Odłożenie** — dyrektywa lokalizacji będzie próbować odnaleźć najlepszą lokalizację, aby umieścić lub zlokalizować zapasy, które są dostępne w systemie w wyniku korekt przyjęcia, produkcji lub zapasów. Może również służyć do zdefiniowania odłożenia do lokalizacji pośredniej lub do lokalizacji końcowej wysyłki przy bramie dokowej.
    - **Pobranie** — dyrektywa lokalizacji podejmie próbę znalezienia najlepszych lokalizacji, z których można zarezerwować zapasy z magazynu (Tworzenie pracy). Pobranie można zrealizować (wiersz pracy pobrania może być zamknięty), nawet jeśli praca nie jest wykonywana. Użytkownik może dokończyć pobieranie fizyczne. W systemie ta akcja jest krokiem pobrania. Użytkownik może następnie anulować z urządzenia przenośnego i wykonać pracę później. Jednak nagłówek pracy jest najpierw zamykany po zakończeniu końcowego wstawiania.

    > [!IMPORTANT]
    > Inne wartości w polu **Typ pracy** nie odpowiadają dyrektywom dotyczącym lokalizacji. Są one wyświetlane tylko w przypadku, gdy pole nie jest filtrowane zgodnie z wybranym typem zlecenia produkcyjnego.

- Pole **Oddział** jest wymagane, ponieważ dyrektywa lokalizacji musi być w stanie ustalić oddział oraz powiązany z nim magazyn.
- Pole **Magazyn** jest wymagane, ponieważ dyrektywa lokalizacji musi być w stanie ustalić oddział oraz powiązany z nim magazyn.
- **Kod dyrektywy** – Umożliwia wybranie kodu dyrektywy, który ma zostać skojarzony z szablonem pracy lub szablonem uzupełnienia zapasów. Na stronie **kod dyrektywy** można utworzyć nowe kody, za pomocą których można połączyć szablony pracy lub uzupełnienia z dyrektywą lokalizacji. Możesz również użyć kodów dyrektywy do ustanowienia połączenia między dowolnym wierszem szablonu pracy a dyrektywą dotyczącą lokalizacji (taką jak drzwi do hali lub lokalizacja sceny).

    > [!TIP]
    > Jeśli kod dyrektywy jest ustawiony, kiedy praca musi zostać wygenerowana, system nie przeszuka dyrektywy lokalizacji według kodu sekwencji. W zamian zostanie wyszukany kod dyrektywy. W ten sposób można bardziej precyzyjnie określić szablon lokalizacji, który jest używany do określonego kroku w szablonie roboczym, na przykład etapu przygotowania materiałów.

- **Wiele SKU** – Ustaw tę opcję na *Tak*, aby używać wielu jednostek magazynowych (SKU) w lokalizacji. Na przykład dla lokalizacji drzwi ładowania musi być włączone wiele jednostek SKU. Jeśli zostanie włączona wiele jednostek SKU, lokalizacja umieszczania zostanie określona w pracy w oczekiwany sposób. Jednak lokalizacja umieszczania będzie mogła obsługiwać tylko wiele pozycji (Jeśli praca obejmuje różne jednostki SKU, które muszą zostać pobrane i umieszczone). Nie będzie mógł obsłużyć operacji załadowania z jedną jednostką SKU. Jeśli ta opcja zostanie ustawiona na *nie*, lokalizacja umieszczania będzie określona tylko wtedy, gdy dla danego odłożenia jest używany tylko jeden rodzaj jednostki SKU.

    > [!IMPORTANT]
    > Aby można było wykonywać zarówno ładowanie z wieloma pozycjami, jak i pojedyncze jednostki SKU, należy określić dwa wiersze o tej samej strukturze i konfiguracji, ale dla opcji **wielu jednostek SKU** należy ustawić wartość *tak* dla jednego wiersza, a *nie* dla drugiego. Dlatego dla operacji odłożenia potrzeba dwóch dyrektyw lokalizacji, które są identyczne, nawet jeśli w pracy o danym identyfikatorze nie trzeba stosować rozróżniania między zdefiniowaniem jednej a wielu jednostek SKU. Często, jeśli nie zostaną skonfigurowane obie te dyrektywy lokalizacji, nieoczekiwane lokalizacje procesów biznesowych będą pochodzić z dyrektywy dotyczącej lokalizacji zastosowania. Należy użyć podobnej konfiguracji dla dyrektyw lokalizacji, które mają **Typ pracy** określony jako *pobranie*, jeśli zachodzi potrzeba przetwarzania zamówień zawierających wiele jednostek SKU.

    W przypadku wierszy pracy obsługujących więcej niż jeden kod towaru należy używać opcji **wielu jednostek SKU**. (Kod pozycji będzie pusty w szczegółach pracy i będzie wyświetlany jako **Wiele** na stronach przetwarzania w aplikacji Warehouse Management.)

    W typowym scenariuszu przykładowym szablon pracy jest skonfigurowany w taki sposób, aby miał więcej niż jedną parę pobranie/odłożenie. W takim przypadku można wyszukać określoną lokalizację przemieszczania, która ma być używana dla wierszy **Typu pracy** jako *Odłożenie*.

    > [!NOTE]
    > Jeśli **opcja wielu jednostek SKU** jest ustawiona na *Tak*, nie można wybrać **Edycji zapytania** w okienku akcji, ponieważ kwerenda nie może ocenić na poziomie elementu, jeśli istnieje wiele elementów. Aby upewnić się, że wybrana dyrektywa lokalizacji jest zaznaczona, należy skorzystać z pola **Kod dyrektywy** w celu wybrania dyrektywy lokalizacji powiązanej z wierszami umieszczania, w których kod dyrektywy jest przypisany w szablonie pracy.

    Jeśli użytkownik nie zawsze pracuje z operacjami pojedynczego towaru lub mieszanego, bardzo ważne jest, aby zdefiniować dwie dyrektywy lokalizacji dla typu pracy *Odłożenie*, jeden, w którym opcja **Wiele SKU** ma wartość *Tak* i jeden, na którym jest ustawiona wartość *nie*.

- **Stosowany kod dyspozycji** – Określ, czy kod dyspozycji dyrektywy lokalizacji musi pasować do kodu dyspozycji stosowanego podczas przyjęcia towaru, lub czy dyrektywę lokalizacji można wybrać na podstawie dowolnego kodu dyspozycji. Po wybraniu *dokładnego dopasowania* i pozostawieniu pola **kodu dyspozycji** pustego, do celów niniejszej dyrektywy lokalizacji uwzględniane będą tylko puste kody dyspozycji.

    > [!NOTE]
    > To pole jest dostępne tylko dla wybranych typów zlecenia produkcyjnego, w których jest dozwolone uzupełnienie zapasów. Aby uzyskać pełną listę, należy zapoznać się z [polami w sekcji Typy zleceń roboczych](#fields-specific-types) wcześniej w tym temacie.

- **Znajdź według** — umożliwia określenie, czy ilość putaway powinna być całkowitą ilością na numer identyfikacyjny, czy powinna być towarem towaru. To pole służy do zapewnienia, że cała zawartość numeru identyfikacyjnego jest umieszczana w jednej lokalizacji, a system nie sugeruje podzielenia zawartości na kilka lokalizacji dla systemu **ASN** (odbierającego numer identyfikacyjny), **odbierania mieszanych numerów identyfikacyjnych** oraz **procesów odbierania w klastrze**. (Proces odbierania w **Klastrze** wymaga włączenia funkcji *Odłóż klaster*.) Zachowanie kwerendy dotyczącej dyrektywy lokalizacji, wierszy oraz akcji dotyczących dyrektywy lokalizacji zależy od wybranej wartości. **Wiersze** skróconej karcie są używane tylko wtedy, gdy pole **Znajdź według** jest ustawione na wartość *pozycja*.

    > [!NOTE]
    > To pole jest dostępne tylko dla wybranych typów zlecenia produkcyjnego, w których jest dozwolone uzupełnienie zapasów. Aby uzyskać pełną listę, należy zapoznać się z [polami dla typów zleceń roboczych](#fields-specific-types).

- **Kod dyspozycji** — to pole jest używane w dyrektywach lokalizacji, które mają typ *zlecenia zakupu*, *towary gotowe odłożone* lub *zamówienia zwrotu* oraz typ pracy *odłożenie*. Za jego pomocą można kierować przepływem do używania konkretnej dyrektywy lokalizacji, w zależności od kodu dyspozycji wybranego przez pracownika w aplikacji Warehouse Management. Można na przykład skierować towary do lokalizacji inspekcji przed ich zwróceniem do magazynu. Kod dyspozycji można połączyć ze stanem zapasów. W ten sposób można go użyć do zmiany stanu zapasów jako części procesu przyjmowania. Na przykład użytkownik ma kod dyspozycji, *QA*, który ustawia stan zapasów na *QA*. Następnie można umieścić oddzielną dyrektywę lokalizacji w celu przeniesienia jej zapasów do lokalizacji kwarantanny.

    > [!NOTE]
    > To pole jest dostępne tylko dla wybranych typów zlecenia produkcyjnego, w których jest dozwolone uzupełnienie zapasów. Aby uzyskać pełną listę, należy zapoznać się z [polami dla typów zleceń roboczych](#fields-specific-types).

## <a name="lines-fasttab"></a>Skrócona karta wierszy

Aby określić warunki stosowania powiązanych akcji określonych w **dyrektywie lokalizacji**, należy skorzystać ze skróconej karty **Wiersze**. Dla każdego wiersza można określić ilość minimalną i maksymalną ilość, której ma dotyczyć akcja. Można również określić, że dana akcja powinna być używana w odniesieniu do określonej jednostki magazynowej.

- **Numer sekwencyjny** – Podaj sekwencję, w której każdy wiersz dyrektywy lokalizacji będzie przetwarzany dla wybranego typu pracy. Sekwencję można zmieniać za pomocą przycisków **Przenieś w górę** i **Przenieś w dół** na pasku narzędzi.
- **Od ilości** — określa początek zakresu ilości, do którego odnosi się wiersz. Wybierz jednostkę miary dla ilości w polu **Jednostka**.
- **Do ilości** — określa koniec zakresu ilości, do którego odnosi się wiersz. Wybierz jednostkę miary dla ilości w polu **Jednostka**.
- **Jednostka** – Umożliwia wybranie jednostki miary dla towarów. Można określić ilość minimalną i maksymalną, do której ma się stosować dyrektywa, i można określić, że dyrektywa powinna być skojarzona z konkretną jednostką magazynową. Pole **Jednostka** jest używane *tylko* do oceny ilości. Aby określić, czy wiersz dotyczący dyrektywy lokalizacji ma być stosowany, system ocenia ilości, korzystając z wartości jednostki określonej w wierszu. Za każdym razem, gdy uzyskuje się dostęp do wiersza dyrektywy lokalizacji, system próbuje przekształcić jednostkę zapotrzebowania na jednostkę określoną w wierszu. Jeśli konwersja jednostek nie istnieje, system przejdzie do następnego wiersza.
- **Odszukaj ilość** — to pole jest używane tylko podczas prób umieszczenia lub zlokalizowania towarów w magazynie. Dlatego też ta strategia jest prawidłowa tylko w przypadku, gdy w polu **Typ pracy** ustawiono wartość *Odłożenie*. Umożliwia wybór jednej z następujących wartości, aby określić ilość używaną do oceny, czy ilość mieści się w zakresie **od ilości** do zakresu **do ilości**:

    - **Ilość w numerze identyfikacyjnym** — służy do używania ilości w odbieranych numerach licencji.
    - **Ilość w jednostkach** — używana jest ilość używana podczas transakcji. Na przykład w magazynie otrzymujemy ilość 1 000 i podzielić ją na 10 numerów identyfikacyjnych, z których każdy ma ilość 100. W takim przypadku można użyć ilości 1 000 pozycji zamiast numeru identyfikacyjnego 100.
    - **Pozostała ilość** — używana jest ilość, która musi być wciąż odebrana w przetwarzanym wierszu zamówienia zakupu.
    - **Ilość oczekiwana** — umożliwia użycie łącznej ilości wiersza zamówienia zakupu bez względu na to, co już przyjęto.

- **Ogranicz na jednostkę** — to pole wyboru umożliwia utworzenie wiersza dyrektywy lokalizacji właściwej dla jednostka miary lub wielu jednostek miary. Należy zaznaczyć, aby ograniczyć jednostki miary, które są uznawane za prawidłowe kryteria wyboru dla wierszy dyrektywy lokalizacji. Ta funkcja działa tylko w odniesieniu do dyrektyw lokalizacji, w których pole **Typ pracy** jest ustawione jako *pobranie*.

    Na przykład podczas rezerwowania ilości paleta powinna być rezerwowana tylko z określonego zbioru lokalizacji. W takim przypadku wiersze będą ograniczać tę sekwencję do palet w taki sposób, aby żadna ilość mniejsza niż paleta nie była zaznaczona dla dyrektywy lokalizacji.

    Jednak pole wyboru **Ogranicz według jednostek** nie kontroluje jednostek lub jednostek stosowanych w wierszach pracy. Ograniczenie jednostkowe dotyczy tylko jednostek, które są udostępniane za pośrednictwem grupy sekwencji jednostek. Na przykład element jest powiązany z grupą sekwencji jednostek, która obejmuje zarówno *palety*, jak i *szt*. Zdefiniowano jednostkę miary, w której 1 paleta = 100 sztuk, a dyrektywa lokalizacji wykorzystuje funkcję **Ogranicz według jednostki** tylko dla palet. Ponadto zdefiniowano szablon pracy, który ogranicza tworzenie nagłówków pracy do 50 szt. W takim przypadku zostaną utworzone linie robocze po 50 sztuk. Aby określić jednostka miary ograniczeń, należy wykonać następujące kroki:

    1. Na skróconej karcie **Wiersze** zaznacz na pasku narzędzi **Ogranicz na jednostkę**. (Przycisk ten staje się dostępny dopiero po zaznaczeniu pola wyboru **Ogranicz według jednostki** w wierszu, a następnie wybraniu opcji **Zapisz**.)
    1. Na **stronie Ogranicz wg jednostek** w polu **Jednostka** wybierz jednostka miary, który chcesz ograniczyć do procesu pobierania i odkładania.

- **Zaokrąglanie w górę do jednostki** — to pole działa razem z polem wyboru **Ogranicz według jednostek**. Jeśli wybrano wiersz dyrektywy lokalizacji **Ogranicz według jednostki** oraz **Zaokrąglij do jednostki**, to praca pobrania surowca wygenerowana na podstawie dyrektywy powinna być zaokrąglana do wielokrotności jednej jednostki załadunkowej (określonej w polu **Ogranicz według jednostki**).

    > [!NOTE]
    > Ustawienie **Zaokrąglanie w górę do jednostki** działa tylko dla typu zlecenia produkcyjnego *pobrania surowca* i tylko w przypadku dyrektyw lokalizacji, w których pole **Typ prac** jest ustawione jako *pobranie*.

- **Lokalizacja opakowania** — w przypadku określenia ilości opakowania w zamówieniu sprzedaży, zamówieniu przeniesienia lub zleceniu produkcyjnym to pole wyboru umożliwia ograniczenie systemu w taki sposób, aby było możliwe wybranie tylko lokalizacji, w których ilość jest równa co najmniej w odniesieniu do ilości w paczce.

    > [!NOTE]
    > Ta funkcja działa tylko w przypadku dyrektyw lokalizacji typu *Pobranie*.

- **Zezwól na podział** – określa, czy dyrektywa lokalizacji może dzielić ilość przyjmowaną lub rezerwowaną między wiele lokalizacji w magazynie albo czy w celu utworzenia pracy cała ilość musi zostać znaleziona w jednej lokalizacji lub rezerwowana z jednej lokalizacji.
- **Szablon natychmiastowego uzupełniania zapasów** – Utwórz połączenie z szablonem uzupełniania zapasów, aby uzupełnienie było uruchamiane natychmiast, jeśli towary nie zostaną przydzielone. Jeśli to pole jest pozostawione puste, uzupełnianie zapasów nie rozpocznie się dopóki, dopóty wszystkie wiersze dyrektywy lokalizacji nie zostaną przetworzone.

    > [!NOTE]
    > To pole jest dostępne tylko dla wybranych typów zlecenia produkcyjnego, w których jest dozwolone uzupełnienie zapasów. Aby uzyskać pełną listę, należy zapoznać się z [polami dla typów zleceń roboczych](#fields-specific-types).

## <a name="location-directive-actions-fasttab"></a>Karta skrócona akcji dyrektyw lokalizacji

Można określić wiele działań dyrektywy lokalizacji dla każdego wiersza. I znowu numer kolejny jest używany do określania porządku oceniania działań. Na tym poziomie można skonfigurować zapytanie do określenia sposobu znajdowania najlepszej lokalizacji w magazynie. Można też znaleźć optymalną lokalizację przy użyciu predefiniowanego ustawienia **Strategia**.

- **Numer sekwencyjny** – W tym polu jest wyświetlana sekwencja, w której akcje będą przetwarzane dla wybranego typu pracy. Sekwencję można zmieniać za pomocą przycisków **Przenieś w górę** i **Przenieś w dół** na pasku narzędzi.
- **Nazwa** – Wprowadź nazwę działania dyrektywy lokalizacji. Musi być konkretna, aby akcja, która zostanie wykonana, była wyczyszczona w nazwie.
- **Stałe użycie lokalizacji** — umożliwia określenie lokalizacji, których powinna uwzględnić dyrektywa lokalizacji. Należy wybrać jedną z następujących opcji:

    - **Lokalizacje stałe i niestałe** – dyrektywa lokalizacji będzie brać pod uwagę wszystkie lokalizacje.
    - **Tylko stałe lokalizacje dla produktu** – dyrektywa lokalizacji będzie brać pod uwagę tylko stałe lokalizacje dla produktów.
    - **Tylko stałe lokalizacje dla wariantu produktu** – dyrektywa lokalizacji będzie brać pod uwagę tylko stałe lokalizacje dla wariantów produktów.

- **Zezwól na zapasy ujemne** – Wybierz tę opcję, aby w dyrektywach lokalizacji zezwolić na ujemny poziom zapasów w określonej lokalizacji magazynowej.
- **Włączono partię** – Zaznaczenie tego pola wyboru umożliwia wykorzystanie strategii wsadowej dla towarów, które obsługują operacje wsadowe. Należy zaznaczyć to pole wyboru w przypadku procesów używających dyrektyw lokalizacji w celu znalezienia lokalizacji, z których mają być pobierane numery partii — z których są śledzone towary. W ten sposób jest uwzględniana lokalizacja przechowywania śledzonych towarów o numerze partii. Jeśli to pole wyboru jest zaznaczone, a w polu **Strategia** jest ustawiona wartość *Brak*, system przejdzie do następnego wiersza akcji.
- **Strategia** – Aby szybciej i łatwiej określić zadania związane z wierszem dyrektywy lokalizacji, użyj jednej z wstępnie zdefiniowanych strategii.

    - **Brak** — nie będzie używana żadna strategia.
    - **Dopasuj ilość opakowań** – ta strategia służy do sprawdzania, czy lokalizacja pobrania ma określoną ilość w paczce. Ta strategia jest prawidłowa tylko w przypadku, gdy w polu **Typ pracy** ustawiono wartość *Pobieranie*.
    - **Konsolidacja** – Ta strategia konsoliduje elementy w określonej lokalizacji, gdy podobne produkty są już dostępne. Ta strategia jest prawidłowa tylko w przypadku, gdy w polu **Typ pracy** ustawiono wartość *Odłożenie*. W typowej konfiguracji modułu odłożenie zostanie podjęta próba konsolidacji w pierwszym wierszu akcji, a następnie w drugim wierszu akcji próba umieszczenia bez konsolidacji. Konsolidacja towarów usprawnia późniejsze pobieranie.
    - **Rezerwacja partii FEFO** — Ta strategia używa rezerwacji partii wg kolejki FEFO. Taka strategia jest używana, gdy zapasy znajduje się przy użyciu daty ważności partii i jest przydzielana do rezerwacji partii. Tej strategii można używać tylko dla towarów obsługujących operacje wsadowe. Ta strategia jest prawidłowa tylko w przypadku, gdy w polu **Typ pracy** ustawiono wartość *Pobieranie*.
    - **Zaokrąglanie w górę do pełnej partii LP i FEFO** — Ta strategia łączy elementy *rezerwacji partii FEFO* i *zaokrągla w górę do strategii z pełnym LP*. Jest ona ważna tylko dla pozycji z włączonymi partiami i dyrektyw lokalizacji, które mają typ prac *pobrania*. Wiersz musi mieć włączoną funkcję wsadową, aby można było użyć strategii *rezerwacji wsadowej FEFO*, zaś strategii *zaokrąglenia do pełnego LP* można użyć tylko do odnawiania. Jeśli ta strategia zostanie skonfigurowana razem z limitem składowania lokalizacji, może to spowodować, że wybrana lokalizacja pracy zostanie zastąpiona, a limity składowania zostaną pominięte.
    - **Zaokrąglij w górę do pełnego nr id.** – Ta strategia zaokrągla ilość zapasów, tak aby była zgodna z ilością na tablicach rejestracyjnych przypisaną do towarów, które muszą zostać pobrane. Tę strategię można stosować tylko do typu uzupełniania zapasów w dyrektywie lokalizacji typu *Pobranie*. Jeśli ta strategia zostanie skonfigurowana razem z limitem składowania lokalizacji, może to spowodować, że wybrana lokalizacja pracy zostanie zastąpiona, a limity składowania zostaną pominięte.
    - **Oparta na numerze ID** – Po zwolnieniu zamówienia do magazynu, w celu utworzenia pracy pobrania i odłożenia wykorzystywana jest strategia w dyrektywie lokalizacji. Można to zrobić dla wielu numerów identyfikacyjnych. Ta strategia oparta na numerach identyfikacyjnych będzie próbować zarezerwować i utworzyć pracę pobrania w odniesieniu do lokalizacji przechowujących żądane numery identyfikacyjne, które zostały skojarzone z wierszami zamówienia przeniesienia. Jeśli jednak nie można ukończyć tych akcji, ale nadal chcesz utworzyć pracę pobrania, powróć do innej strategii dotyczącej akcji dyrektyw dotyczących lokalizacji. W zależności od wymagań dotyczących procesu biznesowego można również wyszukać zapasy w innym obszarze magazynu.
    - **Pusta lokalizacja bez przychodzącej pracy** – ta strategia jest używana do znajdowania pustych lokalizacji. Lokalizacja jest uważana za pustą, jeśli nie ma w niej fizycznych zapasów i nie ma żadnych oczekiwanych prac przychodzących. Tę strategię można stosować tylko do lokalizacji, które mają typ pracy *Odłożenie*.
    - **Wiekowanie lokacji FIFO** Za pomocą strategii FIFO  można wysyłać zarówno towary śledzone wsadowo, jak i towary nieśledzone partiami, na podstawie daty wprowadzenia zapasów do magazynu. Ta możliwość może być szczególnie przydatna w przypadku nieśledzonych partii zapasów, gdy data wygaśnięcia nie jest dostępna do sortowania. Strategia FIFO znajduje lokalizację, która zawiera najstarszą datę wiekowania, oraz przydziela pobieranie na podstawie tej daty wiekowania.
    - **Wiekowanie lokacji LIFO** Za pomocą strategii LIFO można wysyłać zarówno towary śledzone wsadowo, jak i towary nieśledzone partiami, na podstawie daty wprowadzenia zapasów do magazynu. Ta możliwość może być szczególnie przydatna w przypadku nieśledzonych partii zapasów, gdy data wygaśnięcia nie jest dostępna do sortowania. Strategia LIFO znajduje lokalizację, która zawiera najnowszą datę wiekowania, oraz przydziela pobieranie na podstawie tej daty wiekowania.

## <a name="example-using-location-directives"></a>Przykład zastosowania dyrektyw lokalizacji

W tym przykładzie zostanie omówiony proces zamówienia zakupu, w którym dyrektywa lokalizacji musi znaleźć wolne zdolności produkcyjne w magazynie dla pozycji magazynowych, które zostały właśnie zarejestrowane w doku rozładunkowym. Najpierw trzeba znaleźć wolne zdolności produkcyjne w magazynie poprzez konsolidację z istniejącymi zapasami dostępnymi. Jeśli konsolidacja jest niemożliwa, trzeba znaleźć pustą lokalizację.

W tym scenariuszu należy zdefiniować dwa działania dyrektywy lokalizacji. Pierwsze działanie w sekwencji musi wykorzystywać strategię *Konsolidacja*, a drugie powinno używać strategii *Pusta lokalizacja bez przychodzącej pracy*. O ile nie zdefiniowano trzeciego działania dla scenariusza przepełnienia, możliwe są dwa wyniki, jeśli w magazynie nie ma więcej zdolności produkcyjnych: praca może być tworzona nawet bez definiowania lokalizacji lub proces tworzenia pracy może się nie powieść. Wynik jest określany według ustawień na stronie **Błędy dyrektyw lokalizacji**, gdzie można wybrać opcję **Zatrzymaj pracę przy błędzie dyrektywy lokalizacji** dla każdego typu zlecenia.

## <a name="next-step"></a>Następne kroki

Po utworzeniu dyrektywy lokalizacji, każdy kod dyrektywy można skojarzyć z kodem szablonu pracy dla utworzenia pracy. Aby uzyskać więcej informacji, zobacz [Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="additional-resources"></a>Dodatkowe zasoby

- Wideo: [Konfiguracja zarządzania magazynem — zaawansowana](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Temat pomocy: [Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji](control-warehouse-location-directives.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
