---
title: Parametry rozliczania umowy cyklicznej
description: Ten temat wyjaśnia, jak ustawić wartości domyślne dla harmonogramów rozliczeń tworzonych w Powtarzającym się rozliczaniu umów. Wyjaśnia również, jak tworzyć grupy grafików rozliczeniowych.
author: JodiChristiansen
ms.date: 11/04/2021
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
ms.openlocfilehash: 19fe77ade0523aa7fd6382266457fd739df46d75
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685839"
---
# <a name="recurring-contract-billing-parameters"></a>Parametry rozliczania umowy cyklicznej

Użyj strony **Parametry cyklicznego rozliczania kontraktów**, aby ustawić domyślne wartości dla harmonogramów rozliczeniowych tworzonych w ramach cyklicznego rozliczania kontraktów. Wszystkie harmonogramy billingowe, które utworzysz, będą początkowo używać tych wartości domyślnych. Możesz jednak zmienić wartości dla każdego harmonogramu rozliczeń zgodnie z własnymi potrzebami.

## <a name="general-tab"></a>Karta Ogólne

1. Na stronie **Parametry rozliczania umów cyklicznych**, w zakładce **Ogólne**, w polu **Grupa harmonogramów rozliczania** wybierz grupę harmonogramów rozliczania. Informacje o tym, jak skonfigurować grupy harmonogramów rozliczeń, znajdziesz w sekcji [Grupy harmonogramów rozliczeń](#set-up-billing-schedule-groups) w dalszej części tego tematu.
2. W polu **Typ zakończenia** wybierz, w jaki sposób będzie obliczana faktura końcowa, gdy harmonogram rozliczeniowy zostanie zakończony:

    - **Dostosuj harmonogram** – odetnij harmonogram rozliczeniowy w dniu zakończenia, zmień status harmonogramu na **Ostatnie rozliczenie** i dostosuj powiązany z nim harmonogram odroczeń, odwracając kwotę, która nie musi być już ujmowana. Jeśli data rozpoczęcia fakturowania jest późniejsza niż data zakończenia, pozostałe okresy fakturowania są usuwane.
    - **Pozostałe rozliczenie** – dodaj wszystkie kwoty pozostałe w harmonogramie rozliczeń do okresu zakończenia, zmień status harmonogramu na **Ostatnie rozliczenie** i zaktualizuj harmonogram odroczeń. Jeśli data rozpoczęcia fakturowania jest późniejsza niż data zakończenia, do okresu fakturowania jest dodawana łączna kwota wszystkich pozostałych okresów fakturowania, a pozostałe okresy fakturowania są usuwane.
    - **Brak korekty** — zakończ harmonogram rozliczeń w dniu zakończenia. Nie wprowadza się żadnych korekt do harmonogramu rozliczeń.

3. W polu **Typ unikatowego harmonogramu** wybierz **Żaden**, aby określić, że klienci są ograniczeni do jednego harmonogramu rozliczeniowego. Wybierz **Przez klienta** lub **Przez użytkownika końcowego**, aby określić, że klienci są ograniczeni do unikalnego harmonogramu.
4. Ustaw opcję **Wyrównaj do miesiąca** na **Tak**, aby wyrównać linie szczegółów harmonogramu rozliczeniowego do końca miesiąca, w którym tworzony lub aktualizowany jest harmonogram rozliczeniowy. Ustaw na **Nie**, aby używać dat przyrostowych.
5. Ustaw opcję **Rozliczaj okresy częściowe** na **Tak**, aby rozliczać kwoty na podstawie liczby dni w danym okresie. Ustaw **Nie**, aby w każdym okresie rozliczeniowym była taka sama kwota, niezależnie od liczby dni.
6. Jeśli ustawisz opcję **Proporcjonuj okresy częściowe** na **Tak**, ustaw pole **Metoda proporcjonowania** na **Dzienna**, aby rozdzielić kwoty na podstawie liczby dni w okresie. Ustaw na **Miesięcznie**, aby co miesiąc mieć taką samą kwotę.
7. Określ, czy nowo utworzone harmonogramy rozliczeniowe mają być domyślnie wstrzymane.

    > [!NOTE]
    > Aby usunąć wstrzymanie harmonogramu rozliczeniowego, użytkownik musi należeć do grupy użytkowników. Wybierz **Nadpisanie usunięcia wstrzymania grupy użytkowników**, aby skonfigurować grupę użytkowników, w której opcja **Zezwól na usunięcie wstrzymania** jest włączona.

8. W polu **Typ transakcji fakturowej** wybierz domyślny typ transakcji fakturowej dla nowych harmonogramów rozliczeń.
9. Ustaw opcję **Zrównaj odroczenia z rozliczeniami** na **Tak**, aby wyrównać odpowiedni harmonogram odroczeń tak, by używał tych samych dat, co harmonogram rozliczeń. Ustaw na **Nie**, aby mieć różne daty.
10. Jeśli korzystasz z funkcji podziału przychodu, ustaw opcję **Automatycznie twórz podział przychodu** na **Tak**, gdy pozycje są dodawane do harmonogramu rozliczeń. Pole wyboru **Podział przychodu** zostanie automatycznie zaznaczone w linii harmonogramu rozliczeń, jeśli dana pozycja jest ustawiona jako pozycja z podziałem przychodu. Ustaw tę opcję na **Nie**, jeśli chcesz ręcznie zaznaczyć pole wyboru **Podział dochodu**.
11. Ustaw pola do tworzenia zamówień sprzedaży:

    - Faktury mogą być konsolidowane według okresu, klienta lub pozycji. Można ustawić dowolną kombinację wartości **Tak** i **Nie**. Faktury mogą być również dzielone według grup pozycji.
    - Dla faktur dostępne są następujące opcje księgowania:

        - **Utwórz zamówienie sprzedaży** – utwórz tylko zamówienie sprzedaży.
        - **Pokaż fakturę księgowania** – fakturuje zamówienie sprzedaży i otwiera stronę, na której możesz ręcznie zaksięgować fakturę.
        - **Utwórz fakturę tekstową** – wybierz tę opcję, jeśli korzystasz z darmowych faktur tekstowych.
        - **Postaw fakturę automatycznie** – wystaw fakturę na zamówienie sprzedaży i automatycznie ją zaksięguj.

    - Ustaw opcję **Dodaj daty rozliczenia do opisu elementu** na **Tak**, aby dodać opis zawierający datę rozpoczęcia i zakończenia rozliczenia.
    - Ustaw opcję **Wyklucz zerowe zużycie** na **Tak**, aby wykluczyć linie harmonogramu billingowego, które nie mają zużycia. Ustaw wartość **Nie**, aby te wiersze były uwzględniane w zamówieniach sprzedaży.
    - Ustaw opcję **Nie drukuj pozycji podrzędnych** na **Tak**, jeśli nie chcesz drukować pozycji podrzędnych podziału przychodu na zleceniu sprzedaży. Na fakturze pojawi się tylko pozycja nadrzędna. Jeśli kwota netto (ukrytych) pozycji podrzędnych jest sumą niezerową, kwota netto linii nadrzędnej pokazuje podsumowanie linii podrzędnych. Ustaw tę opcję na **Nie**, aby na fakturze sprzedaży drukować wszystkie pozycje podrzędne poniżej pozycji nadrzędnej.

12. Ustaw pola dla wsparcia i odnowień:

    - Ustaw opcję **Automatyczne włączanie wsparcia i odnawiania** na **Tak**, aby automatycznie korzystać z funkcji wsparcia i odnawiania na zamówieniu sprzedaży.
    - W polu **Poziom wsparcia i odnawiania** wybierz domyślny poziom wsparcia i odnawiania.
    - W polu **Liczba wsparcia i odnowień** określ liczbę wsparcia i odnowień.
    - W polu **Domyślna data rozpoczęcia wsparcia i odnowienia** określ datę, która ma być używana jako domyślna data rozpoczęcia wsparcia i odnowienia:

        - **Data transakcji** – Jako daty początkowej należy użyć daty transakcji.
        - **Początek bieżącego miesiąca** — jako daty rozpoczęcia należy użyć pierwszego z bieżącego miesiąca.
        - **Początek następnego miesiąca** — jako daty rozpoczęcia należy użyć pierwszego następnego miesiąca. Jeśli data transakcji jest pierwsza, użyty zostanie pierwszy dzień bieżącego miesiąca.
        - **Reguła 15** – użyj pierwszego dnia bieżącego miesiąca jako daty początkowej, jeśli data transakcji mieści się w przedziale od pierwszego do piętnastego dnia miesiąca. Jeśli data transakcji jest szesnastego dnia lub późniejsza, jako datę początkową należy przyjąć pierwszy dzień następnego miesiąca.

    - Ustaw opcję **Włącz rabat do kalkulacji** na **Tak**, aby wliczyć kwotę rabatu do kwoty wsparcia lub odnowienia. Ustaw **Nie**, aby nie uwzględniać kwoty zniżki.
    - W polach **Częstotliwość wsparcia** i **Częstotliwość odnowienia** wybierz częstotliwość, która będzie stosowana, gdy pozycje dotyczące wsparcia i odnowienia zostaną dodane do harmonogramu rozliczeń: **codziennie**, **miesięcznie**, **kwartalnie**, **półrocznie** lub **rocznie**.
    - Ustaw opcję **Wyrównaj według grupy elementów** na **Tak**, aby wyrównać daty rozpoczęcia i zakończenia nowych elementów do istniejących elementów na podstawie grupy elementów.
    - Ustaw opcję **Dostosuj do następnego niefakturowanego okresu** na **Tak**, aby określić datę wyrównania pozycji odnowienia na podstawie daty następnego niefakturowanego okresu po rozpoczęciu odnowienia.
    - Ustaw opcję **Kopiuj numer seryjny** na **Tak**, aby skopiować numer seryjny artykułu z początkowego wiersza zamówienia sprzedaży do odpowiadającego wiersza harmonogramu rozliczeń.

13. Jeśli używasz eskalacji w harmonogramie rozliczeń, wybierz metodę, która jest używana do obliczania wskaźnika cen towarów i usług konsumpcyjnych.
14. Ustaw opcję **Śledź zmiany cen** na **Tak**, jeśli chcesz, aby zmiany cen były zapisywane w wierszach harmonogramu rozliczeń. Jeśli wiersze harmonogramu rozliczeń zostaną ręcznie zmienione ze standardowej na płaską i wprowadzona zostanie nowa cena, informacje o audycie są śledzone w wierszu harmonogramu rozliczeń. Ustaw tę opcję na **Nie**, jeśli nie chcesz śledzić tych zmian.
15. Określ, czy na stronie **Generuj fakturę** rekordy będą domyślnie filtrowane według daty początkowej czy końcowej.
16. Jeśli używasz funkcji **Dochody nierozliczone**, określ opcje, które są używane:

    - Ustaw opcję **Postaw dziennik ogólny automatycznie** na **Tak**, jeśli chcesz, by arkusz ogólny był tworzony i wysyłany w tym samym czasie. Ustaw **Nie**, jeśli chcesz utworzyć arkusz ogólny, a następnie ręcznie go opublikować.
    - W polu **Domyślna nazwa dziennika** wybierz domyślną nazwę dziennika, która będzie używana podczas tworzenia arkusza ogólnego.
    - W polu **Metoda rozliczania krótkoterminowego** wybierz metodę rozliczania krótkoterminowego, jeśli z niej korzystasz. Jeśli wybierzesz **Brak**, funkcja krótkoterminowa nie będzie używana w przypadku niefakturowanych przychodów. Wybierz **Okresy odnawialne**, aby zawsze stosować 12 miesięcy lub **Rok stały**, aby stosować pozostały rok fiskalny.

17. Określ opcje, które są używane, gdy harmonogram rozliczeniowy i jego linie są zamykane:

    - **Wystaw kredyt** – Utwórz notę kredytową po zakończeniu harmonogramu rozliczeń lub wiersza harmonogramu rozliczeń.
    - **Korekta kredytu** – Umożliwia utworzenie korekty kredytu dla harmonogramu fakturowania po zakończeniu wiersza. Korekta kredytu pojawi się w przyszłym okresie fakturowania dla harmonogramu fakturowania. Korekta kredytu będzie aktualizować kwotę faktury za kolejny okres rozliczeniowy, aż do momentu, gdy kredyt zostanie zastosowany w harmonogramie rozliczeń.
    - **Bez kredytu** – Nie twórz korekty kredytowej ani noty kredytowej, gdy harmonogram rozliczeń lub wiersz harmonogramu rozliczeń zostanie zakończony. Ta opcja jest dostępna tylko wtedy, gdy do zakończenia harmonogramu rozliczeniowego użyto opcji **Bez korekty**.

## <a name="sequence-number-tab"></a>Zakładka numeru sekwencji

Użyj zakładki **Numer sekwencji** na stronie **Parametry rozliczania umów cyklicznych**, aby ustawić domyślną wartość dla numerów harmonogramów rozliczeniowych. Wartości domyślne ustawia się na stronie **Sekwencje numerów** (**Administracja organizacyjna \> Sekwencje numerów \> Sekwencje numerów**).

## <a name="set-up-billing-schedule-groups"></a>Skonfiguruj grupy harmonogramów rozliczeń

Użyj strony **Grupa harmonogramów rozliczeń**, aby utworzyć grupę harmonogramów rozliczeń dla powtarzających się umów. Kiedy tworzony jest nowy harmonogram rozliczeniowy i stosowana jest do niego grupa harmonogramów rozliczeniowych, wartości zdefiniowane na stronie **Grupa harmonogramów rozliczeniowych** są wprowadzane jako wartości domyślne dla harmonogramu rozliczeniowego. Możesz zmienić każdą z wartości domyślnych dla konkretnego harmonogramu rozliczeń, który tworzysz. Możesz utworzyć wiele grup harmonogramów rozliczeniowych, a następnie przypisać jedną z nich jako domyślną grupę harmonogramów rozliczeniowych na stronie **Parametry rozliczania umów cyklicznych**.

Aby utworzyć grupę harmonogramów rozliczeń dla powtarzających się umów, wykonaj poniższe kroki.

1. Na stronie **Grupa harmonogramów rozliczeń** wybierz **Nowy**, aby utworzyć grupę harmonogramów rozliczeń.
2. W polu **Grupa harmonogramów rozliczeń** wpisz unikalny identyfikator.
3. W polu **Opis wprowadź** opis.
4. W polu **Częstotliwość rozliczeń** określ, jak często harmonogram rozliczeń będzie rozliczany z klientem: **jednorazowo**, **codziennie**, **miesięcznie**, **kwartalnie**, **półrocznie** lub **rocznie**.
5. W polu **Interwał rozliczeniowy** wprowadź odstępy czasowe między rozliczeniami. Na przykład ustaw pole **Częstotliwość rozliczeń** na **Miesięcznie**, a pole **Częstotliwość rozliczeń** na **2**, aby rozliczać się co drugi miesiąc.
6. W polu **Metoda ustalania cen** wybierz domyślną metodę ustalania cen dla pozycji w harmonogramie rozliczeniowym:

    - **Standard** – oblicza cenę jednostkową na podstawie wprowadzonej ilości całkowitej i używa standardowych cen ze strony **Wprowadzone produkty** w Zarządzaniu informacjami o produkcie.
    - **Prota** – zastosuj cenę zryczałtowaną, która została wprowadzona w linii harmonogramu rozliczeń.
    - **Poziom** – oblicz cenę jednostkową, używając stałej ilości przy różnych przedziałach cenowych. Każdy poziom musi zostać wypełniony przed przejściem do następnego przedziału cenowego.
    - **Proty poziom** – oblicz cenę jednostkową, używając stałej ilości i rozszerzonych kwot cenowych dla różnych przedziałów cenowych. Cena, która jest naliczana w okresie rozliczeniowym, wykorzystuje cenę rozszerzoną odpowiadającą poziomowi, na którym występuje ilość rozliczeniowa.

7. W polu **Typ towaru** wybierz typ pozycji dla grupy rozliczeniowej:

    - **Standard** — tę wartość należy wybrać, jeśli ilość jest statyczna.
    - **Użycie** — tę wartość należy wybrać dla towarów mierzonych lub o typie zużycia. Jeśli wybierzesz tę wartość, ustaw pole **Opcja odczytu** na **Odczyt**, aby wprowadzić wartość (odczyt) za okres rozliczeniowy na liczniku lub urządzeniu. Zużyta wartość zostanie obliczona na podstawie poprzedniego okresu rozliczeniowego i bieżącego odczytu, który wprowadzisz.
    - **Punkt kontrolny** – wybierz tę wartość, aby korzystać z funkcji rozliczania etapów. Jeśli wybierzesz tę wartość, w polu **Szablon etapu** wybierz szablon, jeśli go używasz.
    - **Zużycie** – wybierz tę wartość, aby wprowadzić wartość, która jest zużywana w danym okresie rozliczeniowym.

8. Ustaw opcję **Faktura osobno** na **Tak**, aby tworzyć kombinację faktur skonsolidowanych i osobnych dla tego samego klienta. Na przykład, klient ma pięć harmonogramów rozliczeniowych. Trzy z nich zostaną skonsolidowane na jednej fakturze, ale każda z dwóch pozostałych wymaga osobnej faktury. Ustaw tę opcję na **Nie**, aby utworzyć tylko jedną skonsolidowaną fakturę dla danego klienta.
9. Ustaw opcję **Odnów automatycznie** na **Tak**, aby automatycznie odnowić harmonogram rozliczeń cyklicznych na następny okres rozliczeniowy podczas tworzenia faktury. Ustaw na **Nie**, aby ręcznie odnowić harmonogram rozliczeń. W polu **Wiersze do dodania za odnowienie** określ, ile wierszy ma być dodanych dla każdego odnowienia.
10. Ustaw opcję **Eskalacja** na **Tak**, aby zastosować *eskalacje* (podwyżki cen) do harmonogramów billingowych powiązanych z tą grupą harmonogramów billingowych.
