---
title: Transakcje odroczone w Rozliczaniu abonamentu
description: W tym temacie opisano różne transakcje, które mogą być używane w transakcjach odroczeń jako część przychodów i odroczeń wydatków w ramach fakturowania subskrypcji.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: f66c538afc732caf3faed3cfea6c695ff7f16273
ms.sourcegitcommit: d0e99545d722c924db57ae2bd06f72154a1f1f97
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2022
ms.locfileid: "8558101"
---
# <a name="deferral-default-transactions"></a>Domyślne transakcje odroczeń

W tym temacie opisano transakcje umożliwiające przychody i odroczenia wydatków. Harmonogramy odroczeń są zawsze oparte na dokumencie źródłowym lub harmonogramie fakturowania i na nich zależą. Harmonogramy odroczeń są tworzone na podstawie wartości domyślnych i nie można ich wprowadzać ani tworzyć oddzielnie.

## <a name="sales-order-transaction-deferral"></a>Odroczenie transakcji zamówienia sprzedaży

Strona **Odroczenia** lub **Tworzenie faktury korygowej** umożliwia wprowadzanie lub edytowanie parametrów odroczeń dla wiersza zamówienia sprzedaży.

> [!NOTE]
> Gdy zamówienie sprzedaży jest tworzone na podstawie harmonogramu fakturowania, wszystkie wartości na stronie **Odroczenia** lub **Tworzenie faktury korygującej** są tylko do odczytu i nie można edytować parametrów odroczeń. Aby edytować wartości, użyj strony **Modyfikuj harmonogram**.

### <a name="edit-deferral-options"></a>Edytuj opcje odroczenia

Aby edytować opcje odroczenia dla wiersza, wykonaj następujące czynności.

1. Utwórz transakcję zlecenia sprzedaży.
2. Wybierz wiersz, a następnie **odroczenia**.
3. Na stronie **Odroczenie transakcji** opcja **Odroczone** musi mieć wartość **Tak**. Edytuj inne pola według własnych potrzeb.
4. Aby wyświetlić podgląd harmonogramu odroczeń, wybierz **Podgląd**.
5. Jeśli zostały wprowadzone zmiany w odroczenie transakcji, wybierz przycisk **OK** i wróć do strony transakcji.
6. Zat typuj i zak księguj transakcję.

Po zaksięgowaniu transakcji otwórz stronę **Wszystkie harmonogramy odroczeń**, aby wyświetlić harmonogram odroczeń.

### <a name="create-a-credit-note"></a>Tworzenie faktury korygującej

Aby utworzyć fakturę korygującą, należy wykonać poniższe kroki.

1. Utwórz transakcję zlecenia sprzedaży.
2. W sekcji **Wiersze zamówienia sprzedaży** wybierz towar, dla którego chcesz utworzyć notę korygzną.
3. Wybierz **Linia zamówienia sprzedaży** \> **Nowa**, a następnie wybierz **Nota kredytowa**.
4. Wybierz **odroczenia**.
5. Na stronie **Odroczenie transakcji zamówienia** sprzedaży ustaw dla pozycji opcję **Dostosuj istniejący harmonogram** na **Tak**.
6. W polu **Skorygowany harmonogram** wybierz harmonogram odroczeń, do którego ma zostać zastosować faktury korygacyjne.
7. W razie wymóg zaktualizuj pola **Oblicz ponownie datę** i **Datę końcową**.
8. Kliknij przycisk **OK**.
9. Zakończ księgowanie transakcji zamówienia sprzedaży.

### <a name="purchase-orders-and-purchase-invoices"></a>Zamówienia zakupu i faktury zakupu

Jeśli chcesz używać funkcji odroczenia w zamówieniu zakupu, wygeneruj najpierw fakturę. Następnie użyj strony **Oczekujące faktury od dostawcy**, aby edytować lub dodać towary odroczone. Nie można edytować ani dodawać odroczeń bezpośrednio w zamówieniu zakupu.

1. Użyj strony **Oczekujące faktury sprzedawcy**, aby wprowadzić fakturę sprzedawcy.

    Podczas wprowadzania wiersza odroczenie jest automatycznie ustawiane dla wybranej pozycji lub kategorii zaopatrzenia. To odroczenie jest oparte na konfiguracji odroczeń na stronie **Ustawień domyślnych odroczeń**. Odroczenia można edytować lub dodawać na poziomie dystrybucji.

3. W wierszu zakupu zaznacz opcję **Finanse \> Dystrybuuj kwoty**.
4. Dla każdej kwoty dystrybucji wybierz opcję **Odroczenia**. Podczas zaksięgowania faktury jest tworzony harmonogram odroczeń dla każdej dystrybucji, dla których jest ustawiane odroczenie.

### <a name="tax"></a>Podatek

W niektórych przypadkach kwota podatku może być w całości lub częściowo nie podlega zwrotowi. Jeśli kwota podatku w wierszu odroczonego zawiera kwotę nie podlega zwrotu, kwota podatku niew odzyskania jest uwzględniana w kwocie harmonogramu odroczeń po zaksięgowaniu faktury.

### <a name="variance"></a>Odchylenie

Jeśli kwota w wierszu faktury od dostawcy różni się od kwoty w wierszu zamówienia zakupu, tworzone są dystrybucje odchylenia. Jeśli wiersz jest odroczony, konto księgowe dla tych dystrybucji jest ustawione na koncie odroczeń, a kwoty są uwzględniane w kwocie harmonogramu odroczeń podczas księgowania faktury. Te dystrybucje nosi nazwę **Odchylenie ceny** i **Odchylenie kosztu**.

### <a name="general-journals-and-invoice-journals"></a>Arkusze ogólne i arkusze faktur

Strona **Odroczenia** umożliwia wprowadzanie parametrów odroczeń dla wiersza załącznika arkusza. Można także wyświetlić podgląd harmonogramu odroczeń dla odroczeń liniowych. Podczas wprowadzania wiersza odroczenie jest ustawiane automatycznie na podstawie ustawień kont odroczeń na **stronie Ustawienia domyślne odroczeń**. Dla każdego wiersza można ręcznie zmienić opcje odroczenia. Po zaksięgowaniu bonu w dzienniku tworzony jest harmonogram odroczeń.

#### <a name="post-and-transfer"></a>Zaksięguj i przenieś

Aby zaksięgować załącznik arkusza, użyj polecenia **Księguj i przenieś**. Opcje odroczenia będą zgodne z wierszem, do których odnosi się załącznik. W przypadku załączników, które nie mają błędów, harmonogram odroczeń jest tworzony, jeśli jest odroczony. W przypadku załącznika, który ma błąd i są przenoszone, są wraz z nim przenoszone wszelkie opcje odroczenia.

#### <a name="tax"></a>Podatek

W niektórych przypadkach kwota podatku może być w całości lub częściowo nie podlega zwrotowi. Jeśli kwota podatku w wierszu odroczonego zawiera kwotę nie podlega zwrotu, kwota podatku niew odzyskania jest uwzględniana w kwocie harmonogramu odroczeń po zaksięgowaniu faktury.

## <a name="free-text-invoice-transaction-deferral"></a>Odroczenie transakcji na fakturze tekstowej

Strona **Odroczenia** służy do wprowadzania parametrów odroczenia dla dowolnego tekstowego podziału wiersza faktury. Po wprowadzeniu podziału środków odroczenie jest automatycznie ustawiane w oparciu o ustawienia odroczenia na **stronie Ustawienia domyślne odroczeń**.

## <a name="fields"></a>Pola

Strona **Odroczenie transakcji** zawiera następujące pola.

| Pole | Opis |
|-------|-------------|
| Odłożone | <p>Określ, czy wiersz jest odroczeniem:</p><ul><li>**Tak** – Linia ta jest odroczona.</li><li>**Nie** – Linia ta nie jest odroczona.</li></ul><p>Gdy ta opcja ma wartość **Tak**, opcja **Dostosuj istniejący harmonogram** jest nie dostępna. W przypadku towarów i opłat, które są już ustawione jako odroczone, ta opcja ma wartość **Tak**. W przypadku pozycji i opłat, które nie są domyślnie ustawione jako odroczone, ustaw tę opcję na **Tak**.</p> |
| Dostosuj istniejący harmonogram | <p>Umożliwia określenie, czy wiersz stanowi korektę istniejącego harmonogramu odroczeń:</p><ul><li>**Tak** – Nowa linia sprzedaży jest dostosowaniem do istniejącego harmonogramu odroczeń. W takim przypadku można wybrać harmonogram odroczeń w polu **Skorygowany harmonogram**.</li><li>**Nie** – Nowa linia sprzedaży nie jest dostosowaniem do istniejącego harmonogramu odroczeń.</li></ul><p>Gdy ta opcja ma wartość **Tak**, opcja **Odłożone** jest nie dostępna.</p> |
| Skorygowany harmonogram | <p>Wybierz harmonogram odroczeń, do których jest korygowany wiersz. Wszystkie wartości na tej stronie zostaną wówczas zaktualizowane przy użyciu wartości z pochodzących z inicjatora harmonogramu odroczeń. Tych wartości nie można edytować.</p><p>To pole jest dostępne tylko wtedy, gdy opcja **Dostosuj istniejący harmonogram** jest ustawiona na **Tak**.</p> |
| Data ponownego obliczania | <p>Umożliwia określenie daty rozpoczęcia okresu, na który ma zostać ponownie przeliczenie pozostałej kwoty. Datą domyślną jest data następnego nierozpoznanego okresu.</p><p>To pole jest dostępne tylko wtedy, gdy opcja **Dostosuj istniejący harmonogram** jest ustawiona na **Tak**.</p> |
| Data końcowa | <p>W zależności od typu odroczenia data zakończenia może być aktualizowana:</p><ul><li>W przypadku odroczenia liniowego należy określić nową datę końcową harmonogramu. Wartością domyślną jest istniejąca data zakończenia harmonogramu odroczeń.</li><li>W przypadku odroczenia opartego na zdarzeniu należy określić datę końcową wiersza zdarzenia kredytowego. Ta data może być pusta.</li></ul><p>To pole jest dostępne tylko wtedy, gdy opcja **Dostosuj istniejący harmonogram** jest ustawiona na **Tak**.</p> |
| Numer harmonogramu rozliczania | <p>Numer harmonogramu rozliczeń.</p><p>To pole jest dostępne tylko w przypadku cyklicznych harmonogramów fakturowania umowy.</p> |
| Metoda korekty odroczenia | <p>Metoda odroczonej korekty. Ta wartość pasuje do wartości na stronie **Przetwarzania zakończenia zatrudnienia** masowego dla harmonogramu fakturowania umowy cyklicznej.</p><p>To pole jest dostępne tylko w przypadku cyklicznych harmonogramów fakturowania umowy.</p> |
| **Konta - Przychody** | |
| Konto odroczenia | <p>Konto odroczenia, czyli konto księgowania wyświetlane na stronie **Zamówienie sprzedaży**.</p><p>Jeśli wiersz nie został odroczony, to pole jest puste. W tym przypadku domyślnym kontem przychodów jest konto księgowania.</p> |
| Konto rozpoznania | <p>Umożliwia określenie konta używanego podczas rozpoznania odroczenia. Konto to musi się różnić od konta odroczeń.</p><p>Gdy opcja **Odroczone** ma początkowo wartość **Tak**, wartości wymiarów używane na koncie odroczeń są kopiowane do konta rozpoznawania. Jeśli wymiar na koncie odroczeń nie istnieje dla konta rozpoznawania, zostanie zignorowany.</p> |
| Konto początkowego rozpoznania | <p>Wybierz konto dla początkowego ujęcia dochodów. Wartość domyślna pochodzi ze strony **Ustawienia domyślne odroczenia**.</p><p>To pole jest dostępne tylko wtedy, gdy w polu **Metoda księgowania odroczeń** ustawiono wartość **Wynikowa** na stronie **Parametry odroczeń przychodów i wydatków**.</p> |
| Konto przeciwstawne rozpoznania | <p>Wybierz konto do kompensacji ujmowania dochodów. Wartość domyślna pochodzi ze strony **Ustawienia domyślne odroczenia**.</p><p>To pole jest dostępne tylko wtedy, gdy w polu **Metoda księgowania odroczeń** ustawiono wartość **Wynikowa** na stronie **Parametry odroczeń przychodów i wydatków**.</p> |
| **Konta - Rabat** | Ta sekcja jest wyświetlana tylko dla towarów odroczonych. Jest ono ukryte dla opłat odroczonych. |
| Konto odroczenia | <p>Należy podać numer konta odroczenia dyskonta. Wartość domyślna pochodzi ze strony **Ustawienia domyślne odroczenia**.</p><p>To pole jest dostępne tylko wtedy, gdy w polu **opcja Odroczenie rabatu** jest ustawiona wartość **Rozdziel harmonogram dla rabatu** na stronie **parametrów odroczeń przychodów i wydatków**, a do wiersza stosowany jest rabat.</p> |
| Konto rozpoznania | <p>Określ numer konta uznania rabatu. Wartość domyślna pochodzi ze strony **Ustawienia domyślne odroczenia**.</p><p>To pole jest dostępne tylko wtedy, gdy w polu **opcja Odroczenie rabatu** jest ustawiona wartość **Rozdziel harmonogram dla rabatu** na stronie **parametrów odroczeń przychodów i wydatków**, a do wiersza stosowany jest rabat.</p> |
| Konto początkowego rozpoznania | <p>Wybierz konto do początkowego ujęcia rabatu. Wartość domyślna pochodzi ze strony **Ustawienia domyślne odroczenia**.</p><p>To pole jest dostępne tylko wtedy, gdy w polu **Metoda księgowania odroczenia** jest ustawiona wartość **Wynikowe** na stronie **parametrów odroczeń przychodów i wydatków**, a do wiersza stosowany jest rabat.</p> |
| Konto przeciwstawne rozpoznania | <p>Wybierz konto do kompensacji ujmowania dochodów. Wartość domyślna pochodzi ze strony **Ustawienia domyślne odroczenia**.</p><p>To pole jest dostępne tylko wtedy, gdy w polu **Metoda księgowania odroczenia** jest ustawiona wartość **Wynikowe** na stronie **parametrów odroczeń przychodów i wydatków**, a do wiersza stosowany jest rabat.</p> |
| **Konta - Zużycie** | Ta sekcja jest wyświetlana tylko dla towarów odroczonych. Jest ono ukryte dla opłat odroczonych. |
| Konto odroczenia | <p>Należy podać numer konta odroczenia zużycia.</p><p>W przypadku produktów standardowych tworzone są dwa harmonogramy odroczeń:</p><ul><li>**Standardowa sprzedaż** – Plan przychodów z saldem kredytowym. W tym przypadku należy wybrać konto odroczeń zużycia.</li><li>**Zużycie** — plan wydatków (koszt własny sprzedaży \[COGS\]) z saldem debetowym. W tym przypadku należy wybrać konto rozpoznania zużycia.</li></ul><p>Po zaksięgowaniu faktury kwota zużycia jest księgowana na określonym koncie odroczeń zużycia. Te pola nie są dostępne dla usług.</p> |
| Konto rozpoznania | Podaj numer konta rozpoznania spożycia. |
| Konto początkowego rozpoznania | <p>Umożliwia określenie konta dla początkowej kwoty rozpoznawania zużycia. Wartość domyślna pochodzi ze strony **Ustawienia domyślne odroczenia**.</p><p>To pole jest dostępne tylko wtedy, gdy w polu **Metoda księgowania odroczeń** ustawiono wartość **Wynikowa** na stronie **Parametry odroczeń przychodów i wydatków**.</p> |
| Konto przeciwstawne rozpoznania | <p>Określenie konta dla kwoty kompensacji ujęcia zużycia. Wartość domyślna pochodzi ze strony **Ustawienia domyślne odroczenia**.</p><p>To pole jest dostępne tylko wtedy, gdy w polu **Metoda księgowania odroczeń** ustawiono wartość **Wynikowa** na stronie **Parametry odroczeń przychodów i wydatków**.</p> |
| **Zaplanuj** | |
| Typ harmonogramu | <p>Wybierz typ harmonogramu odroczeń: **liniowy** (domyślny) lub **Oparty na zdarzeniu**.</p><p>Opcje wyświetlane na stronie są oparte na wybranych typach harmonogramu odroczeń.</p><p>Jeśli na stronie **Ustawienia domyślne odroczeń** dla wiersza transakcji jest ustawiony szablon domyślny, typ harmonogramu odroczeń jest oparty na typie wybranego szablonu.</p> |
| **Harmonogram - linia prosta** | |
| Konsoliduj poprzednie okresy | <p>Określ, czy chcesz skonsolidować wiersze harmonogramu odroczeń dla wcześniejszych okresów:</p><ul><li>**Tak** — konsolidowanie wierszy harmonogramu odroczeń dla poprzednich okresów.</li><li>**Nie** — Nie należy konsolidować wierszy harmonogramu odroczeń dla wcześniejszych okresów.</li></ul><p>Wartość domyślna pochodzi ze strony **parametrów odroczeń przychodów i wydatków**.</p> |
| Równe dla okresu | <p>Określ, czy liczba dni w każdym okresie jest równa okresowi, czy też może być różna:</p><ul><li>**Tak** — każdy okres ma taką samą liczbę dni.</li><li>**Nie** — okresy nie mają takiej samej liczby dni.</li></ul><p>Jeśli dla tej opcji jest ustawiona wartość **Nie**, podczas obliczania kwoty w każdym okresie dla harmonogramu odroczeń jest obliczana liczba dni w okresie.</p><p>Wartość domyślna pochodzi ze strony **parametrów odroczeń przychodów i wydatków**.</p> |
| Harmonogram na podstawie szablonu | <p>Umożliwia określenie, czy harmonogram odroczeń jest tworzony na podstawie szablonu, czy daty końcowej:</p><ul><li>**Tak** — harmonogram odroczeń jest tworzony na podstawie szablonu.</li><li>**Nie** — Harmonogram odroczeń jest tworzony w oparciu o datę końcową.</li></ul> |
| Szablon | Wybierz szablon odroczenia. |
| Zastąp datę rozpoczęcia | <p>Określ, czy chcesz zastąpić datę rozpoczęcia:</p><ul><li>**Tak** — umożliwia zastąpienie daty rozpoczęcia datą wprowadzeniu w **polu Data rozpoczęcia**.</li><li>**Nie** — data rozpoczęcia to **domyślna reguła daty rozpoczęcia odroczenia** stosowana do daty faktury określonej na **stronie Księgowanie faktury**. Regułę tę można ustawić na stronie **Parametry odraczania przychodów i kosztów**.</li></ul> |
| Data początkowa odroczenia | Określ datę rozpoczęcia odroczenia. Domyślną wartością jest data transakcji. |
| Data zakończenia odroczenia | <p>Data zakończenia odroczenia.</p><p>Ta data jest obliczana automatycznie na podstawie szablonu odroczeń. Jeśli nie wybrano żadnego szablonu, należy ręcznie wprowadzić datę.</p> |
| **Harmonogram - na podstawie zdarzeń** | |
| Szablon | <p>Wybierz szablon oparty na zdarzeniach. To pole jest opcjonalne.</p><p>Po wybraniu szablonu wartości z tego szablonu zastępują wszystkie dane i wiersze zdarzeń zdarzeń.</p> |
| Typ alokacji | <p>Umożliwia wybór typu alokacji dla wierszy zdarzeń:</p><ul><li>**Kwoty zmienne** — Dla każdego wiersza wprowadza się określoną kwotę przydziału.</li><li>**Równe kwoty** — kwota jest alokowana równomiernie dla każdego wiersza.</li><li>**Procent** — Kwota jest przydzielana na podstawie wartości procentowej wprowadzonej dla każdego wiersza.</li><li>**Procent ukończenia** — Dla każdego wiersza podawana jest łączna wartość zakończenia.</li><p>**Ilość zmienna** — Dla każdego wiersza wprowadza się określoną liczbę przydziałów.</li></ul><p>**Uwaga:** Aby wybrać **procent ukończenia**, daty muszą być w kolejności rosnącej.</p> |
| **Utwórz osobne zdarzenia na jednostkę** | |
| Opis | <p>Umożliwia określenie, czy mają być oddzielane zdarzenia na jednostkę:</p><ul><li>**Tak** — należy oddzielić wiersze zdarzenia, tak aby był jeden wiersz na ilość.<p>Na przykład istnieją trzy wiersze zdarzeń, a faktura ma ilość czterech. W tym przypadku wynikowy harmonogram odroczeń ma 12 wierszy.</p></li><li>**Nie** — nie oddzielaj wierszy zdarzeń.</li></ul> |
| Konto wygaśnięcia | <p>Wybierz konto używane dla rozpoznanych wygasłych wierszy. Konto można wybrać po utworzeniu harmonogramu odroczeń.</p><p>Jeśli data ważności jest ustawiona dla zdarzenia, podczas procesu rozpoznawania kwota rozpoznania jest przesyłana na konto wygaśnięcia, a nie na konto rozpoznawania.</p> |
| **Harmonogram - Wiersze na podstawie zdarzeń** | |
| Opis | Opis wydarzenia. |
| Data zakończenia odroczenia | <p>Wybierz datę zakończenia wydarzenia.</p><p>**Uwaga:** W przypadku wybrania daty końcowej pole **Data ważności** jest wyczyszowane. Nie możesz użyć daty końcowej i daty ważności.</p> |
| Data ważności | <p>Wybierz datę wygaśnięcia zdarzenia.</p><p>**Uwaga:** W przypadku wybrania daty końcowej pole **Data ważności** jest wyczyszowane. Nie możesz użyć daty końcowej i daty ważności.</p> |
| Ilość | <p>Określ ilość przydziału. Wartość domyślna dla wszystkich wierszy wynosi **0** (zero). W przypadku aktualizacji ilości, łączna ilość ze wszystkich wierszy musi być równa ilości określonej w wierszu towaru na zamówieniu sprzedaży lub mniejsza.</p><p>Ta opcja jest dostępna tylko w przypadku, gdy w polu **Typ alokacji** jest wartość **Ilość zmienna**.</p><p>Jeśli ilość towaru w wierszu zamówienia sprzedaży zostanie zmieniona tak, aby była mniejsza niż ilość oryginalna i została utworzona faktura, tworzona jest mniejsza liczba wierszy zdarzeń. Łączna zaalokowana ilość nie przekracza ilości określonej w inicjatorze zamówienia sprzedaży lub harmonogramie fakturowania.</p> |
| Procent alokacji | <p>Określa alokację w procentach. Jeśli w polu **Typ alokacji** jest ustawiona wartość **Procent** lub **Procent ukończenia**, można ręcznie wprowadzić wartość procentową. W przeciwnym razie zostanie obliczony automatycznie.</p><p>Jeśli w polu **Typ alokacji** jest ustawiona wartość **Procent**, suma procentów musi być równa 100.</p> |
| Ilość | <p>Określ kwotę przydziału. Jeśli w polu **Typ alokacji** jest ustawiona wartość **Ilość zmienna** lub **Procent ukończenia**, można ręcznie wprowadzić wartość.</p><p>Jeśli w polu **Typ alokacji** jest ustawiona wartość **Procent ukończenia**, a w tym miejscu zostanie w tym polu wprowadzeniu wartość pola **Procent ukończenia**, zostanie automatycznie obliczona.</p><p>Z powodu zaokrąglania obliczona kwota może nie odpowiadać dokładnie kwocie wprowadzonej ręcznie. Jeśli musisz określić dokładną kwotę, w polu **Typ alokacji** ustaw wartości **Kwoty zmienne**.</p> |
| Procent wykonania | <p>Określ procent ukończenia. Wartość musi być z zakresu od 0 (zero) do 100.</p><p>Ta opcja jest dostępna tylko w przypadku, gdy w polu **Typ alokacji** jest wartość **Procent zaawansowania**.</p> |
| Kwota wykonania | <p>Obliczona suma dla wszystkich wierszy w harmonogramie odroczeń.</p><p>Jeśli w polu **Typ alokacji** jest ustawiona wartość **Procent ukończenia**, można ręcznie wprowadzić wartość. W takim przypadku wartość pola **Procent ukończenia** jest obliczana na podstawie wprowadzeniu kwoty.</p><p>Z powodu zaokrąglania obliczona kwota może nie odpowiadać dokładnie kwocie wprowadzonej ręcznie.</p><p>Ta opcja jest dostępna tylko w przypadku, gdy w polu **Typ alokacji** jest wartość **Procent zaawansowania**.</p> |
| Rozpoznaj po wpisie | <p>Umożliwia określenie, czy wiersz jest automatycznie rozpoznawany po zaksięgowaniu transakcji:</p><ul><li>**Wybrane** – Umożliwia określenie, czy wiersz jest automatycznie rozpoznawany po zaksięgowaniu transakcji.</li><li>**Wyczyszczone** – Umożliwia określenie, czy wiersz nie jest automatycznie rozpoznawany po zaksięgowaniu transakcji.</li></ul> |
| Konto rozpoznania | <p>Umożliwia określenie konta rozpoznawania zdarzenia, jeśli konto różni się od konta używanego dla całego harmonogramu odroczeń.</p><p>Tego pola można używać w połączeniu z opcją **Rozpoznawanie przy księgowaniu**.</p> |
