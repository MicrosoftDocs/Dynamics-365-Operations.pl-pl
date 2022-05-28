---
title: Tworzenie harmonogramów rozliczania
description: W tym temacie wyjaśniono, jak tworzyć, usuwać i edytować harmonogramy rozliczeń.
author: JodiChristiansen
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ed31dd96b0115610cfb74aed69f1acc1055bfe56
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690453"
---
# <a name="create-billing-schedules"></a>Tworzenie harmonogramów rozliczania

[!include [banner](../includes/banner.md)]

Na stronie **Harmonogram fakturowania** można tworzyć, usuwać lub edytować harmonogramy fakturowania. Możesz również przejrzeć listę harmonogramów fakturowania. Podczas tworzenia harmonogramu fakturowania domyślne jego wartości są określane przez skojarzoną z nim grupę fakturowania. Dodatkowe informacje można skonfigurować na stronie **Parametry fakturowania umowy cyklicznej**.

## <a name="create-a-billing-schedule"></a>Utwórz harmonogram rozliczeń

Aby utworzyć harmonogram rozliczeń, wykonaj poniższe kroki.

1. Na stronie **Harmonogram fakturowania** wybierz opcję **Nowe**.
2. W oknie dialogowym **Tworzenie harmonogramu** fakturowania w polu **Grupa harmonogramów fakturowania** wybierz grupę harmonogramów fakturowania.
3. W polu **Konto odbiorcy** wybierz konto klienta.
4. W polu **Data rozpoczęcia** wybierz datę rozpoczęcia, a następnie w polu **Liczba okresów** wprowadź liczbę okresów. Pole **Data zakończenia** jest aktualizowane na podstawie liczby wpisanych okresów. Po zaktualizowaniu pola **Data zakończenia fakturowania** pole **Liczba okresów** zostanie zaktualizowane do **wartości 0** (zero).
5. Kliknij przycisk **OK**.
6. Na stronie **Harmonogram fakturowania**, na karcie **Ogólne**, w polu **Opis** wprowadź opis harmonogramu fakturowania.
7. W polu **Szablon punktu kontrolnego** wybierz szablon kamieni milowych do **fakturowania kamieni milowych**.

Pola, takie jak **Konto faktury** i **Kod waluty**, są aktualizowane przy użyciu informacji od odbiorcy.

Pola **Częstotliwość fakturowania** i **Interwał fakturowania** są ustawiane automatycznie na podstawie wybranej grupy harmonogramów fakturowania.

8. Aby utworzyć osobne faktury, ustaw opcję **Faktura oddzielnie** na wartość **Tak**.
9. Aby automatycznie odnawiać harmonogram rozliczeń po ostatnim okresie rozliczeniowym, ustaw opcję **Odnów automatycznie** na **Tak**, a następnie ustaw pole **Wiersze do dodania przy każdym odnowieniu**.

Pola **Parametry** są ustawiane automatycznie na podstawie wartości na stronie **Parametry fakturowania umowy cyklicznej**.

10. Aby proporcjonalnie oszacować wysokość harmonogramu rozliczeń, ustaw opcję **Proporcjonalnie częściowe okresy** na **Tak**.
11. Aby dopasować wiersze szczegółów harmonogramu fakturowania do końca miesiąca, **ustaw opcję Dopasuj do miesiąca** na **wartość Tak**.
12. W polach **Data rozpoczęcia umowy** i **Data zakończenia umowy** wpisz daty rozpoczęcia i zakończenia umowy. Daty te mają wyłącznie informacyjny termin.

W polu **Płatność** są podane informacje o płatności odbiorcy od odbiorcy. Gdy element zamówienia jest wstrzymany lub zamknięty, nie można zmienić informacji o płatności.

> [!NOTE]
> Podczas konsolidowania faktur według towarów wartości w **polach Warunki płatności**, **Metoda** oraz **Harmonogram fakturowania** muszą być zgodne. W przeciwnym razie nie można skonsolidować faktur.

13. Na karcie **Adres** możesz przejrzeć i zaktualizować pola **Adres dostawy** i **Adres dostawy**.
14. Na karcie **Informacje o kontakcie** można skojarzyć konto użytkownika końcowego z harmonogramem fakturowania.
15. W polach **Informacje o kontakcie** można wprowadzić kontakt, adres e-mail i adres internetowy.
16. Aby śledzić informacje o prowizji dla partnera, ustaw **pola Konto partnera** i **Stawka prowizji dla partnera**. Te pola służą wyłącznie do celów informacyjnych.
17. Na karcie **Suma** można przeglądać różne sumy obliczone dla harmonogramu fakturowania.
18. Na karcie **Wstrzymanie** można wyświetlić informacje inspekcji dotyczące czasu wstrzymania harmonogramu fakturowania w czasie jego usunięcia.
19. Na karcie **Zakończenie** zatrudnienia można wyświetlić historię zakończenia zatrudnienia, które zostały zastosowane lub usunięte z harmonogramu fakturowania.
20. Wybierz opcję **Zapisz**.
21. Na skróconej karcie **Harmonogram rozliczeń** wybierz pozycję **Dodaj wiersz**.
22. W polu **Numer pozycji** wybierz numer towaru. Jeśli dodawany element jest elementem nadrzędnym w podziale przychodów, wiersze są automatycznie aktualizowane o elementy podrzędne. W podziale przychodów można edytować tylko towar nadrzędny. Wszystkie elementy podrzędne zostaną odpowiednio zaktualizowane.
23. W polu **Typ pozycji** wybierz typ towaru.
24. Zaktualizuj daty rozpoczęcia i zakończenia.
25. Przed rozpoczęciem tworzenia faktur można zmienić częstotliwość fakturowania, aktualizując pole **Częstotliwość fakturowania**. Po utworzeniu pierwszej faktury dla harmonogramu rozliczeń nie można zmienić częstotliwości rozliczeń.
26. W polu **Jednostka** wybierz jednostkę miary dla pozycji.
27. W polu **Metoda cenowa** wybierz metodę kalkulacji cen dla pozycji.

Pole **Cena jednostkowa** jest automatycznie ustawiane z magazynu. Można ją jednak zaktualizować w przypadku zmiany metody cenowej na **Płaska**.

## <a name="remove-a-line-item"></a>Usuwanie wiersza towaru

Aby usunąć towar z harmonogramu fakturowania, wykonaj następujące kroki.

1. Na stronie **Harmonogram fakturowania**, w polu **Numer harmonogramu** wybierz numer harmonogramu fakturowania, który ma być edytowany.
2. Na skróconej **karcie Wiersze harmonogramu fakturowania** zaznacz wiersz do usunięcia, a następnie wybierz pozycję **Usuń**.
3. Wybierz opcję **Zapisz**.

W pozostałej części tego tematu opisano akcje i szczegóły dostępne dla wierszy na skróconej karcie **Wiersze harmonogramu fakturowania**.

## <a name="billing-schedule-line-actions"></a>Akcje wiersza harmonogramu fakturowania

Przyciski na skróconej karcie **Wiersze harmonogramu fakturowania** pozwalają na stosowanie akcji do poszczególnych wierszy.

| Guzik | Opis |
|--------|-------------|
| Dodaj wiersz | Dodaj wiersz do harmonogramu rozliczeń. |
| Dodaj z listy pozycji | Aby dodać wiele pozycji do harmonogramu fakturowania, należy zaznaczyć je na liście. |
| Usuń | <p>Usuń wybraną linię z harmonogramu rozliczeń.</p><p>W przypadku towarów, które są częścią podziału przychodu, można usunąć tylko towar nadrzędny. Wszystkie skojarzone elementy podrzędne zostaną wówczas automatycznie usunięte.</p> |
| Wyświetl szczegół rozliczenia | Wyświetl szczegóły płatności. |
| Zakończ zatrudnienie | <p>Zakończ zaznaczone wiersze. Ten przycisk jest dostępny tylko wtedy, gdy wybrane wiersze mają stan **Aktywne**.</p><p>W przypadku pozycji, które są częścią podziału przychodów, można zamknąć tylko pozycję nadrzędną.</p> |
| Usuń wypowiedzenie | <p>Usuń zakończenie z wybranych wierszy. Ten przycisk jest dostępny tylko wtedy, gdy wybrane wiersze mają stan **Usunięte**.</p><p>W przypadku pozycji, które są częścią podziału przychodów, możesz usunąć zakończenie tylko z pozycji nadrzędnej.</p> |
| Nałóż wstrzymanie | <p>Umożliwia wybór szczegółów dotyczących wstrzymywania wybranego wiersza.</p><p>W przypadku elementów, które są częścią podziału przychodów, możesz wstrzymać tylko element nadrzędny.</p> |
| Usuń wstrzymanie | <p>Usuń blokadę z wybranej linii.</p><p>W przypadku elementów, które są częścią podziału przychodów, blokadę można usunąć tylko z elementu nadrzędnego.</p> |
| Eskalacja i rabat | Ten przycisk nie jest dostępny w przypadku towarów, które są częścią podziału przychodów, z wyjątkiem towarów nadrzędnych, dla których podział przychodów wykorzystuje metodę alokacji **zerowej kwoty**. |
| Odroczenia | <p>Umożliwia wprowadzenie opcji odroczenia dla wybranego wiersza.</p><p>Ten przycisk nie jest dostępny dla pozycji nadrzędnych w podziale przychodów.</p> |
| Alokacja punktu kontrolnego | <p>Przejrzyj i zaktualizuj informacje dotyczące alokacji punktów kontrolnych dla wybranego wiersza.</p><p>Ten przycisk jest dostępny tylko wtedy, gdy elementem wiersza harmonogramu fakturowania jest element kamieni milowych.</p> |
| Obsługa i odnowienie | <p>Przejrzyj i zaktualizuj informacje o wsparciu i odnowieniu dla wybranej linii.</p><p>Ten przycisk jest dostępny tylko wtedy, gdy pozycja harmonogramu rozliczeń jest pozycją wsparcia lub odnowienia.</p> |
| Wyświetl wymiary | Pokaż lub ukryj kolumny wymiarów, które są widoczne w siatce **wierszy harmonogramu fakturowania**. |
| Oblicz cenę jednostkową | <p>Oblicz cenę jednostkową towaru, aby klient mógł zapłacić kwotę umowy w ratach (na przykład dziennie, miesięcznie, kwartalnie, półrocznie lub rocznie). Możesz wybrać cenę kontraktu i częstotliwość cen.</p><p>Możesz wyświetlić ścieżkę audytu zmian: cenę i częstotliwość starej umowy, cenę i częstotliwość nowej umowy, użytkownika, który wprowadził zmianę, oraz datę i godzinę zmiany.</p> |
| Data dopasowania | <p>Określ datę wyrównania dla odnowienia pozycji.</p><p>W przypadku wybrania grupy towarów w polu **Grupa pozycji** wszystkie towary będą używać daty wyrównania pierwszej pozycji z grupy towarów w harmonogramie fakturowania. Jeśli pole **Grupa pozycji** jest puste, można określić wyrównanie dla wszystkich towarów.</p><p>Ten przycisk jest dostępny tylko wtedy, gdy pole **Częstotliwość rozliczeń** jest ustawione na **Roczny**.</p> |
| Nierozliczony przychód | <p>Umożliwia ustawienie dla towaru funkcji niepodjętego przychodu. Następnie dla towaru można określić konto przychodu niepodbilonego i konto rabatu.</p><p>Przycisk ten jest dostępny tylko w przypadku towarów, dla których **w polu Typ towaru** jest ustawiona wartość **Standard**. Nie jest dostępna dla istniejących harmonogramów rozliczeń ani dla wierszy harmonogramu rozliczeń, w których faktura została już utworzona.</p> |
| Dodaj element podrzędny podziału przychodu | <p>Wybierz towar podrzędny, który chcesz dodać do zamówienia sprzedaży.</p><p>Ten przycisk jest dostępny tylko dla pozycji nadrzędnych w podziale przychodów.</p> |
| Opcje zaawansowanej kalkulacji cen | Edytowanie opcji cenowych dla towaru. |

## <a name="billing-schedule-line-details"></a>Szczegóły linii harmonogramu płatności

Po wybraniu wiersza w skróconej karcie **Wiersze harmonogramu fakturowania** można wyświetlić określone szczegóły dotyczące tego wiersza. Te szczegóły są podzielone na różne karty.

### <a name="general-tab"></a>Karta Ogólne

Poniższe informacje są dostępne na karcie **Ogólne**.

| Pole lub sekcja | Opis |
|------------------|-------------|
| Użycie | <p>Ta sekcja zawiera informacje o elementach użytkowych. Zawiera następujące pola:</p><ul><li>**Identyfikator użycia** — identyfikator miernika lub towaru użycia.</li><li>**Opcja odczytu** – Opcja odczytu użycia: **odczyt** lub **zużycie**.</li><li>**Szacowane zużycie** — umożliwia określenie szacunkowego zużycia towaru użycia w okresach, w których nie utworzono faktury. Na stronie **Szczegóły fakturowania** możesz przejrzeć wiersze szczegółów fakturowania dla szacowanego zużycia.</li></ul> |
| Odwołania zewnętrzne\* | Ta sekcja zawiera pola **Zewnętrzne** i **Numer wiersza**, w których można określić informacje o odwołaniach zewnętrznych. |
| Punkt kontrolny | <p>Ta sekcja zawiera informacje o elementach kamieni milowych. Zawiera ona pole **Szacowana data ukończenia**, w którym jest przedstawiana data ukończenia towaru.</li></ul> |
| Tekst | Komentarz do linii. Tekst jest tłumaczony na domyślny język odbiorcy lub firmy. |
| Grupa pozycji | Grupa towarów dla elementu zamówienia. |
| Data dopasowania | Data wyrównania harmonogramu fakturowania. |

\* Podczas konsolidowania faktur według towarów na stronie **Generowanie faktury** pola **Odwołania zewnętrzne** muszą być zgodne. Jeśli nawet jeden znak jest inny, towary nie zostaną skonsolidowane na fakturze. Nie sprawdzane jest żadne pole w sekcji **Odwołanie zewnętrzne**, a wartość w polu **Numer wiersza** musi być dodatnią liczbą całkowitą.

### <a name="address-tab"></a>Karta Adres

Poniższe informacje są dostępne na karcie **Adres**.

| Pole | Opis |
|-------|-------------|
| Adres dostawy | <p>Wybierz adres dostawy dla pozycji. Domyślny adres dostawy jest podstawowym adresem dostawy ze skróconej karty **Adres**.</p><p>Podczas zmiany adresu możesz wybrać następujące opcje adresu:</p><ul><li>**Adresy** — umożliwia wybór adresu bieżącego odbiorcy.</li><li>**W użyciu** — umożliwia wybór adresu, który jest obecnie używany dla bieżącego odbiorcy.</li><li>**Inny adres** — należy wybrać adres dowolnego rekordu odbiorcy.</li></ul><p>W przypadku towarów, w przypadku których jest dzielony przychód, można edytować tylko adres towaru nadrzędnego. Adres towarów podrzędnych pasuje do adresu nadrzędnego i nie można go edytować osobno.</p> |
| Adres rozliczeniowy | <p>Wybierz adres rozliczeniowy dla elementu zamówienia. Domyślny adres dostawy jest podstawowym adresem dostawy ze skróconej karty **Adres**. Adres można zmienić zgodnie z potrzebą, na podstawie celu dostępnych adresów:</p><ul><li>Jeśli żaden z adresów nie ma celu **Faktury**, domyślny adres weksla jest adresem podstawowym odbiorcy, niezależnie od celu.</li><li>Jeśli jeden lub więcej adresów ma cel **Faktury**, domyślny adres weksla jest adresem, który został ostatnio wprowadzony.</li><li>Jeśli jeden lub więcej adresów ma cel **Faktury**, a jeden z adresów na fakturze jest ustawiony jako adres podstawowy, domyślny adres na paragonie jest adresem, który ma cel **faktury** i jest ustawiony jako adres podstawowy.</li><li>W przypadku towarów, w przypadku których jest dzielony przychód, można edytować tylko adres towaru nadrzędnego. Adres towarów podrzędnych pasuje do adresu nadrzędnego i nie można go edytować osobno.</li></ul> |

### <a name="product-tab"></a>Zakładka produktów

Poniższe informacje są dostępne na karcie **Produkt**.

| Pole lub sekcja | Opis |
|------------------|-------------|
| Wymiary magazynowania | <p>Ta sekcja zawiera informacje o magazynie dla pozycji. Zawiera pole **Numer seryjny**, w którym jest przedstawiany numer seryjny towaru.</p><p>Numer seryjny jest kopiowany z początkowego zamówienia sprzedaży w trakcie procesu pomocy technicznej i odnowienia. W przypadku towarów, w przypadku których jest dzielone przychody, numer seryjny towaru nadrzędnego jest kopiowany do wszystkich towarów podrzędnych. Numer seryjny jest kopiowany, gdy opcja **Kopiuj numer seryjny** ma wartość **Tak** na stronie **Parametry fakturowania umowy cyklicznej**.</li></ul> |
| Wymiary produktu | Szczegóły produktu dla towaru i wartości są automatycznie aktualizowane na podstawie wartości **numeru wariantu** wybranej dla wiersza harmonogramu fakturowania. |

### <a name="account-tab"></a>Zakładka Konto

Poniższe informacje są dostępne na karcie **Konto**.

| Pole | Opis |
|-------|-------------|
| Konto główne | Konto główne utworzone w wierszu sprzedaży. Wartość domyślna pochodzi z zamówienia sprzedaży. To pole może być puste. |
| Wymiary finansowe pozycji | <p>Domyślne wartości wymiaru finansowego oparte na rekordzie odbiorcy i towaru.</p><p>W przypadku towarów, w przypadku których jest stosować podział przychodów, towary podrzędne używają wartości wymiarów finansowych odbiorcy i rekordów towarów, jak opisano wcześniej. Jeśli musisz zaktualizować wartości wymiarów finansowych elementów podrzędnych, możesz zaimportować jednostkę danych.</p> |

### <a name="renewals-tab"></a>Karta Odnowienia

Poniższe informacje są dostępne na karcie **Odnowienia**.

| Pole | Opis |
|-------|-------------|
| Automatycznie odnawiaj | <p>Wartość wskazująca, czy wiersz harmonogramu fakturowania jest automatycznie odnowiony dla następnego okresu fakturowania:</p><ul><li>**Tak** — wiersz harmonogramu rozliczeń jest automatycznie odnawiany na następny okres rozliczeniowy po utworzeniu faktury.</li><li>**Nie** — wiersz harmonogramu fakturowania nie jest automatycznie odnowiony. Należy ręcznie odnowić harmonogram fakturowania.</li></ul> |
| Wiersze do dodania na odroczenie | Liczba wierszy, które należy dodać do odnowienia harmonogramu fakturowania. |

Dodatkowo na karcie **Odnowy** dostępne są następujące przyciski.

| Guzik | Opis |
|--------|-------------|
| Inspekcja wpisu w arkuszu nierozliczonego przychodu | Umożliwia wyświetlanie wszystkich zmian dla pozycji, dla których jest dostępna funkcja nieskomplikowanych przychodów. |
| Dodaj termin odnowienia | Dodaj termin odnowienia dla pozycji. Data rozpoczęcia nowego termy przedłużenia jest następną datą późniejszą niż data zakończenia poprzedniego okresu. Można **zaktualizować pola Data zakończenia przedłużenia**, **Data rozpoczęcia odroczenia**, **Data zakończenia odroczenia**, **Ilość pozycji** i **Cena jednostkowa**. |
| Modyfikuj termin odnowienia | <p>Modyfikowanie terminu odnowienia. W początkowym terminie można zmienić daty rozpoczęcia i zakończenia odroczeń przed utworzeniem początkowego wpisu w arkuszu. W przypadku kolejnych warunków nie można zmienić daty rozpoczęcia. Jest to zawsze następna data po zakończeniu poprzedniego okresu.</p><p>Jeśli po modyfikowaniu terminu istnieje termin odnowienia, nie można zmienić jego dat. W takim przypadku można zaktualizować tylko pola **Ilość** i **Cena jednostkowa** dla odnowienia towaru.</p><p>Istnieją na przykład trzy terminy. <ul><li>Nie można zmienić pierwszego terminu, ponieważ został on już uruchomiony.</li><li>W przypadku drugiego terminu można zmieniać tylko ilość i cenę jednostkową.</li><li>W przypadku trzeciego terminu można zmieniać wszystkie wartości z wyjątkiem daty rozpoczęcia. Dodatkowo opcja Harmonogram **na podstawie szablonu** umożliwia tworzenie harmonogramu odroczeń opartego na szablonie dla niepodjętego przychodu. Jeśli dla tej opcji jest ustawiona **wartość Tak**, wybierz szablon odroczeń w polu **Szablon** i zmień wymagane daty rozpoczęcia i zakończenia odroczeń. Kolejne warunki odnowienia używają tego samego szablonu odroczenia. Szablon odroczenia można jednak zmienić.</p></li></ul> |

### <a name="termination-tab"></a>Karta zakończenie

Poniższe informacje są dostępne na karcie **zakończenie**.

| Pole | Opis |
|-------|-------------|
| Data zakończenia | Data zakończenia wiersza harmonogramu fakturowania. Wartość domyślna pochodzi z pola **Data zakończenia** w nagłówku. Można jednak zmienić jego wartość. |
| Typ wypowiedzenia | Typ zakończenia. Wartość domyślna pochodzi z pola **Typ zakończenia** w nagłówku. |

### <a name="hold-tab"></a>Karta Wstrzymaj

Jeśli używane są przychody i odroczenia wydatków, na **karcie Wstrzymanie** jest używana data odroczenia.

### <a name="escalation-and-discount-tab"></a>Karta Eskalacja i rabat

Poniższe informacje są dostępne w zakładce **Eskalacja i rabat**.

| Pole | Opis |
|-------|-------------|
| Eskalacja | <p>Wybierz, czy eskalacja jest dozwolona dla wiersza harmonogramu fakturowania. Wszystkie wiersze eskalacji z nagłówka są stosowane podczas tworzenia wiersza harmonogramu fakturowania.</p><ul><li>**Tak** — eskalacje mogą być stosowane do wiersza. Po wybraniu tej opcji można skonfigurować eskalacje dla wierszy harmonogramu fakturowania na stronie **Eskalacja i rabat**.</li><li>**Nie** — eskalacje nie mogą być stosowane do wiersza.</li></ul><p>Ustawienie domyślne jest oparte na wybranej **grupie harmonogramu fakturowania**.</p> |

### <a name="price-changes-tab"></a>Zakładka zmian cen

W przypadku wierszy, które zostały zmienione **z Cena** standardowa na **Cena ryczałt**, siatka na karcie **Zmiany ceny** zawiera następujące kolumny:

- Zmień datę
- Zmieniono przez użytkownika
- Cena standardowa
- Cena ryczałtowa
- Aktualizacja ceny
