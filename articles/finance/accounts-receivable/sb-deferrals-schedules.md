---
title: Harmonogramy odroczeń w rozliczeniach międzyokresowych przychodów i kosztów
description: W tym artykule opisano harmonogramy odroczeń w rozliczeniach międzyokresowych przychodów i kosztów.
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
ms.openlocfilehash: 093005f9b66d7ce741689b55612f006fa5123910
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903371"
---
# <a name="deferral-schedules"></a>Harmonogramy odroczeń

Harmonogramy odroczeń są tworzone po zaksięgowaniu transakcji.

Strona **Wszystkie harmonogramy odroczeń** lub **Aktywne harmonogramy odroczeń** umożliwia przeglądanie szczegółów harmonogramu odroczeń. Wyświetlane informacje zależą od typu harmonogramu odroczeń (liniowego lub liniowego) oraz typu transakcji. Zawiera wiersze harmonogramu odroczeń i sumy dla harmonogramu odroczeń. Za pomocą tej strony można zmodyfikować harmonogram odroczeń.

## <a name="recognize-revenue"></a>Rozpoznawanie przychodu

> [!NOTE]
> - Aby rozpoznać przychód dla jednego harmonogramu odroczeń, rozpocznij od kroku 1.
> - Aby ująć przychód dla wielu harmonogramów, należy rozpocząć od kroku 2.

1. Na stronie **Wszystkie harmonogramy odroczeń** w **siatce Wiersze harmonogramu** zaznacz wiersze, które chcesz rozpoznać, a następnie wybierz **pozycję Rozpoznaj**.
2. Na stronie **Przetwarzanie rozpoznawania** ustaw w polu Akcja **rozpoznawania** wartość **Utwórz arkusz rozpoznawania**.
3. W polu **Data ostateczna** wybierz datę ostateczną. Przetwarzanie obejmie tylko wiersze, w których data końcowa jest wcześniejsza lub taka sama jak wybrana data końcowa.
4. Wybierz **opcję Filtruj** i dodaj filtry danych, aby lista zawierała tylko zakres rekordów, które chcesz.
5. Wybierz **opcję Wyświetl podgląd**, aby wyświetlić wiersze.
6. Z listy wierszy wybierz wiersze, które nie chcesz przetwarzać, a następnie wybierz polecenie **Usuń**.
7. Umożliwia wybranie, czy należy podsumować wpis w arkuszu rozpoznawania.
8. W sekcji **Data transakcji** można zastąpić datę transakcji określoną datą do przetwarzania transakcji. Datę transakcji można określić dla zamkniętych okresów.
9. Aby wykonać przetwarzanie w ramach zadania wsadowego, wybierz pozycję **Partia**. W oknie dialogowym **Przetwarzanie wsadowe** ustaw parametry zadania wsadowego, a następnie wybierz przycisk **OK**, aby powrócić do strony **Przetwarzanie rozpoznawania**. Przychód zostanie przetworzony później podczas przetwarzania partii.
10. Wybierz **Proces**. Jeśli transakcja nie została dotworzona do partii, wszystkie wiersze są natychmiast przetwarzane. W przeciwnym razie wiersze zostaną przetworzone podczas przetwarzania partii.

## <a name="modify-a-schedule"></a>Modyfikuj harmonogram

Aby zmodyfikować harmonogram odroczeń, wykonaj poniższe kroki.

1. Na stronie **Wszystkie harmonogramy odroczeń** wybierz harmonogram odroczeń, a następnie wybierz **Księgowanie \> Modyfikuj harmonogram**.
2. Na stronie **Modyfikuj harmonogram** edytuj opcje, które chcesz zmienić. W zależności od harmonogramu odroczeń nie można edytować wszystkich opcji.
3. Wybierz **Podgląd**, aby sprawdzić zmiany w harmonogramie odroczeń.
4. Kliknij przycisk **OK**.

### <a name="straight-line-deferral-schedules"></a>Harmonogramy odroczeń liniowych

Jeśli harmonogram odroczeń nie zawiera rozpoznanych lub zaksięgowanych zewnętrznie wierszy, można zmodyfikować cały harmonogram odroczeń, w tym datę rozpoczęcia.

Jeśli harmonogram odroczeń ma rozpoznawane lub zaksięgowane zewnętrznie wiersze, a harmonogram odroczeń zostanie zmodyfikować, wynikowe zachowanie harmonogramu odroczeń zależy od daty ponownego przeliczenia oraz daty zakończenia odroczenia rozpoznanych wierszy. Domyślnie datę zakończenia odroczenia określa pierwszy nieusztywniany okres.

Aby użyć daty rozpoznania, wybierz jedną z następujących wartości w polu **Początek harmonogramu**: 
- **Wyrównaj** — kwota po przeliczeniu wszystkich rozpoznanych wierszy.
- **Wycofanie** — wszystkie wiersze po dacie ponownego przeliczania są wycofywne przy użyciu określonej nazwy arkusza i daty księgowania. Kwota po dacie ponownego przeliczania jest następnie przeliczana.

Jeśli jest używany szablon, pominięte okresy są ignorowane i szablon jest używany tylko do obliczania daty końcowej.

### <a name="event-based-deferral-schedules"></a>Harmonogramy odroczeń oparte na zdarzeniach

W przypadku harmonogramu odroczeń opartego na zdarzeniach można modyfikować wszystkie nierozpoznane wiersze.

Jeśli harmonogram odroczeń ma jakieś wiersze uznane lub zaksięgowane zewnętrznie, nie można modyfikować szablonu i typu alokacji dla harmonogramu odroczeń. Podczas modyfikowania istniejącego harmonogramu odroczeń nie można zmienić wartości pola **Utwórz osobne zdarzenia na jednostkę**.

Jeśli wiersz jest rozpoznawany lub zaksięgowany zewnętrznie, zaznaczone jest pole wyboru **Rozpoznane**.

## <a name="modify-a-deferral-or-recognition-account"></a>Modyfikowanie konta odroczenia lub konta rozpoznawania

Aby zmodyfikować konto odroczenia lub konto rozpoznawania dla harmonogramu odroczeń, należy wykonać następujące kroki.

1. Na stronie **Wszystkie harmonogramy odroczeń** wybierz harmonogram odroczeń, a następnie wybierz **Księgowanie \> Modyfikuj konto**.
2. Na stronie **Modyfikuj konto** wybierz konto, które chcesz zmienić (odroczenie, krótkoterminowe lub uznaniowe).
3. W polu **Nowe konto** wybierz nowe konto.
4. Umożliwia wybór, czy zmiany w zapisach w arkuszu korekty konta będą tworzyć.
5. Jeśli w poprzednim kroku ustawisz opcję **Tak**, wybierz nazwę arkusza w polu **Nazwa arkusza** i określ datę transakcji **w polu Data transakcji**.
6. Kliknij przycisk **OK**.

## <a name="put-a-deferral-schedule-on-hold"></a>Wstrzymywanie harmonogramu odroczeń

Aby wstrzymać harmonogram odroczeń, wykonaj poniższe kroki.

1. Na stronie **Wszystkie harmonogramy odroczeń** wybierz harmonogram odroczeń, a następnie wybierz **Wstrzymaj \> Nałóż wstrzymanie**.
2. Na stronie **Nałóż wstrzymanie** określ, czy saldo ma zostać transferowe z konta odroczenia czy z konta przechowywania.
3. Jeśli wybrano opcję przeniesienia salda, wybierz nazwę dziennika w polu **Nazwa dziennika**, wybierz konto wstrzymania w polu **Konto wstrzymania** określ datę transakcji **w polu Data transakcji**.
4. Kliknij przycisk **OK**.

## <a name="remove-a-hold-from-a-deferral-schedule"></a>Usuwanie wstrzymania z harmonogramu odroczeń

Aby usunąć harmonogram odroczenia z wstrzymania, wykonaj następujące czynności.

1. Na liście **Wszystkie harmonogramy odroczeń** wybierz harmonogram odroczeń, a następnie wybierz **Wstrzymaj \> Usuń wstrzymanie**.
2. W polu **Nazwa arkusza** wybierz nazwę arkusza, która ma być używana.
3. W polu **Data aktywacji transakcji** podaj datę transakcji.
4. Kliknij przycisk **OK**.

## <a name="cancel-unrecognized-amounts"></a>Anuluj nierozpoznane kwoty

> [!NOTE]
> Z tego procesu są wykluczone wszystkie wiersze, które zostały już rozpoznane lub zaksięgowane zewnętrznie.

Aby anulować nierozpoznane kwoty w harmonogramie odroczeń, należy wykonać poniższe kroki.

1. Na stronie **Wszystkie harmonogramy odroczeń** wybierz harmonogram odroczeń, a następnie wybierz **Anuluj \> Nierozpoznane kwoty**.
2. Na stronie **Anuluj nieuznaną kwotę** określ, czy chcesz tworzyć wpisy anulowania.
3. Jeśli wybrano opcję tworzenia wpisów anulujących, należy wybrać nazwę dziennika w polu **Nazwa arkusza**, wybrać konto anulujące w polu **Konto anulujące** oraz określ datę transakcji **w polu Data transakcji**.
4. Kliknij przycisk **OK**.

## <a name="cancel-a-completed-schedule"></a>Anuluj ukończony harmonogram

Strona **Wszystkie harmonogramy odroczeń** zawiera informacje o wycofaniu rozpoznanych lub zaksięgowanych zewnętrznie kwot oraz anulowaniu harmonogramu odroczeń, co uniemożliwia dalsze rozpoznawanie tych kwot.

Aby anulować cały harmonogram odroczeń, wykonaj poniższe kroki.

1. Na stronie **Wszystkie harmonogramy odroczeń** wybierz harmonogram odroczeń, a następnie wybierz **Anuluj \> Zakończ harmonogram**.
2. Na stronie **Anuluj cały harmonogram** określ, czy chcesz tworzyć wpisy anulowania.
3. Jeśli wybrano opcję tworzenia wpisów anulujących, należy wybrać nazwę dziennika w polu **Nazwa arkusza**, wybrać konto anulujące w polu **Konto anulujące** oraz określ datę transakcji **w polu Data transakcji**.
4. Kliknij przycisk **OK**.

## <a name="reverse-transactions"></a>Wycofaj transakcje

> [!NOTE]
> - Aby odwrócić ujęcie przychodów dla jednego harmonogramu odroczeń, należy rozpocząć od kroku 1.
> - Aby odwrócić proces ujmowania przychodów dla wielu harmonogramów, należy rozpocząć od kroku 2.

1. Na stronie **Wszystkie harmonogramy odroczeń** w **siatce Wiersze harmonogramu** zaznacz wiersze, które chcesz cofnąć, a następnie wybierz **Cofnij**.
2. Na stronie **Przetwarzanie rozpoznawania** ustaw w polu Akcja **rozpoznawania** wartość **Cofnij arkusz rozpoznawania**.
3. W polu **Data ostateczna** wybierz datę ostateczną. Przetwarzanie obejmie tylko wiersze, w których data końcowa jest wcześniejsza lub taka sama jak wybrana data końcowa.
4. Wybierz **opcję Filtruj** i dodaj filtry danych, aby lista zawierała tylko zakres rekordów, które chcesz.
5. Wybierz **opcję Wyświetl podgląd**, aby wyświetlić wiersze.
6. Z listy wierszy wybierz wiersze, które nie chcesz przetwarzać, a następnie wybierz polecenie **Usuń**.
7. Pola **Nazwa** i **Opis** są automatycznie aktualizowane przy użyciu domyślnej nazwy i opisu arkusza. Można jednak zmienić jego wartości. Można również wybrać, czy wpis dziennika ujmowania ma być podsumowywany.
8. W sekcji **Data transakcji** można zastąpić datę transakcji określoną datą do przetwarzania transakcji. Datę transakcji można określić dla zamkniętych okresów.
9. Aby wykonać przetwarzanie w ramach zadania wsadowego, wybierz pozycję **Partia**. W oknie dialogowym **Przetwarzanie wsadowe** ustaw parametry zadania wsadowego, a następnie wybierz przycisk **OK**, aby powrócić do strony **Przetwarzanie rozpoznawania**. Przychód cofnięty zostanie przetworzony później podczas przetwarzania partii.
10. Kliknij przycisk **OK**. Jeśli transakcja nie została dotworzona do partii, wszystkie wiersze są natychmiast przetwarzane. W przeciwnym razie wiersze zostaną przetworzone podczas przetwarzania partii.

## <a name="apply-or-unapply-a-credit-note"></a>Stosowanie faktury koryguje lub niezastosuj jej

Aby zastosować fakturę korygującą, należy wykonać poniższe kroki.

> [!NOTE]
> W przypadku utworzenia faktury koryguje się ze strony **odroczenia transakcji zamówienia sprzedaży** i ustaw w ustawieniach opcji **Dostosuj istniejący harmonogram** wartość **Tak**, podczas zaksięgowania faktury koryguje ona automatycznie.

1. Na stronie **Wszystkie harmonogramy odroczeń** wybierz harmonogram odroczeń.
2. Z listy **korekt kredytu wybierz** wiersz, a następnie wybierz pozycję **Zastosuj**.
3. Na stronie **Zastosuj notę kredytową (odroczenia)** określ datę ponownego przeliczania w polu **Data ponownego przeliczania** oraz datę zakończenia w polu **Data zakończenia**.
4. Z listy **Nagłówek** wybierz **zamówienie sprzedaży** z notami koryg uwagami
5. Z listy **Wiersze** wybierz wiersz.
6. Kliknij przycisk **OK**.
7. Wybierz opcję **Tak**.

> [!NOTE]
> Aby zastosować fakturę korygową do kilku pojedynczych towarów z różnych faktur, należy powtórzyć te kroki.

Aby anulować notę kredytową, wykonaj następujące czynności.

1. Na stronie **Wszystkie harmonogramy odroczeń** wybierz harmonogram odroczeń.
2. Z listy **korekt kredytu wybierz** faktur, a następnie wybierz pozycję **Cofnij zastosowanie**.
3. Wybierz opcję **Tak**.

## <a name="fields"></a>Pola

Strona **Wszystkie harmonogramy odroczeń** zawiera następujące pola.

| Pola | Opis |
|--------|-------------|
| **Nagłówek** | |
| **Zaplanuj** | |
| Typ alokacji | Typ alokacji dla odroczeń opartych na zdarzeniach: **procent** lub **kwota**. |
| Data przeklasyfikowania | <p>Ostatnia data przetworzenia krótkoterminowej przeklasyfikowania harmonogramu odroczeń. Ta data jest aktualizowana za każdym razem, gdy **dla harmonogramu odroczeń** jest używana krótkoterminowe przeklasyfikowanie zdarzenia.</p>To pole jest dostępne tylko w przypadku, gdy stosowana jest metoda odroczenia krótkoterminowego w okresach lub w ustalonym roku. |
| **Konto** | |
| Konto odroczenia | Konto używane dla kwoty odroczenia. |
| Konto rozpoznania | Konto, które jest używane dla kwoty uznania. |
| Typ rozpoznania | Typ rozpoznawania. |
| Typ dystrybucji | Typ dystrybucji. |
| **Transakcja** | |
| Źródło tworzenia | Źródło, z którego została utworzona transakcja. |
| Typ transakcji | Typ transakcji. |
| Zamówienie sprzedaży | Numer zamówienia sprzedaży. |
| Faktura | Numer faktury. |
| Pozycja | Kod towaru. |
| **Harmonogram rozliczania** | |
| Numer harmonogramu rozliczania | Numer odpowiedniego harmonogramu rozliczeń. |
| Stan wiersza rozliczania | Status odpowiedniej pozycji harmonogramu rozliczeniowego. |
| Odwołania zewnętrzne | Informacje o odwołaniach zewnętrznych z harmonogramu fakturowania: **zewnętrzny** i **numer wiersza**. |
| Sumy | <p>Sumy dla harmonogramu odroczeń:</p><ul><li>**Długookresowe** — suma kwot odroczonych długoterminowych. Ta wartość jest dostępna tylko wtedy, gdy w polu **Metoda odroczeń krótkoterminowych** jest ustawiona wartość **Brak** na stronie **Parametry odroczeń przychodów i wydatków** lub kwota krótkoterminowego odroczenia jest większa od zera.</li><li>**Krótkoterminowe** — suma kwot odroczonych krótkoterminowych. Ta wartość jest dostępna tylko wtedy, gdy w polu **Metoda odroczeń krótkoterminowych** jest ustawiona wartość **Brak** na stronie **Parametry odroczeń przychodów i wydatków** lub kwota krótkoterminowego odroczenia jest większa od zera.</li><li>**Nierozpoznane** – Suma kwot nieuznanych dla wszystkich wierszy.</li><li>**Przycięte** – Suma kwot zaksięgowanych zewnętrznie dla wszystkich linii.</li><li>**Rozpoznane** – Suma kwot uznanych dla wszystkich wierszy.</li><li>**Zewnętrznie zaksięgowane i rozpoznawane** — suma kwot zaksięgowanych i rozpoznanych zewnętrznie dla wszystkich wierszy.</li><li>**Razem** – Suma kwot dla wszystkich wierszy.</li></ul> |
| **Wiersze harmonogramu** | |
| Wiersz | Numer kolejny wiersza pracy. |
| Data początkowa odroczenia | Data rozpoczęcia harmonogramu odroczeń. |
| Data zakończenia odroczenia | Data zakończenia harmonogramu odroczeń. |
| Ilość | Kwota odroczenia. |
| Zewnętrznie | Wartość określająca, czy wiersz został wysłany na zewnątrz. |
| Rozpoznane | Wartość określająca, czy wiersz został rozpoznany. |
| Arkusz z numerem partii | Numer partii, w których kwota została rozpoznana. |
| Opis zdarzenia | Opis wydarzenia. To pole jest dostępne tylko w przypadku harmonogramów odroczeń opartych na zdarzeniach. |
| **Korekty kredytu** | |
| Faktura | <p>Numer faktury.</p><p>Wartość ta wskazuje fakturę korekty noty kredytowej, która została już zastosowana do harmonogramu odroczeń.</p> |
| Zastosowana kwota | Kwota korekty kredytu, która została już zastosowana do harmonogramu odroczeń. |
| Data zastosowania | Data zastosowania korekty kredytu. |
| **Korekta** | Wartości korekty są wyświetlane tylko wtedy, gdy została przetworzona nota kredytowa dla harmonogramu odroczeń. Jeśli nie przetworzono faktury korygują, te wartości są ukryte. |
| Kwota korekty | Łączna kwota korekty obliczona jako kwota *oryginalna* — kwota *harmonogramu*. |
| Oryginalna data zakończenia | Data pierwotnego zakończenia harmonogramu odroczeń. |
| Oryginalna kwota harmonogramu | Suma pierwotnego harmonogramu odroczeń. |
