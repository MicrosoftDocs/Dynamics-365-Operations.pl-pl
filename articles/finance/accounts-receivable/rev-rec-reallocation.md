---
title: Zmiana alokacji rozpoznawania przychodów
description: Ten artykuł zawiera informacje dotyczące zmiany alokacji, która umożliwia organizacjom ponowne obliczanie cen przychodów w przypadku zmiany warunków umownych dotyczących sprzedaży. Temat zawiera łącza do innych tematów opisujących sposób rozpoznawania przychodu w wielu scenariuszach.
author: bking
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6c7e2149058ebbff85cbc2ac86dac3231fbcc41d
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348162"
---
# <a name="revenue-recognition-reallocation"></a>Zmiana alokacji rozpoznawania przychodów

[!include [banner](../includes/banner.md)]

Zmiana alokacji umożliwia organizacjom ponowne obliczanie cen przychodów w przypadku zmiany warunków umownych dotyczących sprzedaży. W kontekście rozpoznawania przychodów dokumenty zamówienia sprzedaży uznaje się za umowę.

Twoja organizacja musi zdecydować, czy zmiana alokacji jest w jej przypadku wymagana. Dodanie nowego wiersza do zamówienia sprzedaży lub dodanie nowego zamówienia sprzedaży dla odbiorcy może nie stanowić zmiany umowy. Zmiana alokacji może być wymagana w przypadku następujących scenariuszy:

- Odbiorca dodał towary do zamówienia sprzedaży lub usunął je z zamówienia sprzedaży po tym, jak zamówienie zostało w całości lub częściowo zafakturowane.
- Dla tej samej wynegocjowanej umowy wprowadzono wiele potwierdzonych lub zafakturowanych zamówień sprzedaży.
- Odbiorca zwrócił lub otrzymał kredyt na towar po tym, jak oryginalne zamówienie sprzedaży zostało całkowicie lub częściowo zafakturowane.

Z procesem zmiany alokacji wiąże się kilka istotnych ograniczeń:

- Proces można przeprowadzić tylko jeden raz. W związku z tym ważne jest, aby uruchomić go dopiero po sfinalizowaniu wszystkich zmian.

    - To ograniczenie będzie usunięte w wydaniu 10.0.17 i nowszym.

- Procesu nie można uruchomić dla zamówień sprzedaży dla projektu.

    - To ograniczenie będzie usunięte w wydaniu 10.0.17 i nowszym.

- Jeśli proces ma objąć wiele zamówień sprzedaży, wszystkie one muszą dotyczyć tego samego konta odbiorcy.
- Wszystkie zamówienia sprzedaży, dla których jest realizowana zmiana alokacji, muszą być w tej samej walucie transakcji.
- Raz uruchomionego procesu nie można odwrócić ani cofnąć.

    - To ograniczenie będzie usunięte w wydaniu 10.0.17 i nowszym.

- Zmianę alokacji można przeprowadzić tylko dla zamówień sprzedaży albo zamówień sprzedaży projektu. Nie można jej przeprowadzić dla kombinacji zamówień sprzedaży i zamówień sprzedaży projektu.

    - To ograniczenie będzie usunięte w wydaniu 10.0.17 i nowszym.

## <a name="set-up-reallocation"></a>Konfigurowanie zmiany alokacji

Istnieje jeden parametr, który wpływa na proces zmiany alokacji.

Jako że zmianę alokacji można przeprowadzić dla zamówienia sprzedaży, które jest częściowo lub w całości zafakturowane, wszelkie wcześniejsze wpisy księgowania dla faktury muszą zostać skorygowane przy użyciu nowych cen przychodu uwzględniających zmianę alokacji. Korektę wprowadza się poprzez wycofanie wpisu księgowania oryginalnej faktury i zaksięgowanie nowego wpisu księgowania na podstawie cen przychodu uwzględniających zmianę alokacji.

Każda organizacja musi podjąć decyzję o tym, czy korekta ma powodować aktualizację wyłącznie księgi głównej, czy też zarówno księgi głównej, jak i rozrachunków z odbiorcami. Na podstawie podjętej decyzji należy określić właściwe ustawienie opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** na karcie **Rozpoznawanie przychodów** na stronie **Parametry księgi głównej** (**Rozpoznawanie przychodów \> Konfiguracja \> Parametry księgi głównej**). Właściwe ustawienie zależy od określonego scenariusza. Aby uzyskać więcej informacji na temat możliwych scenariuszy, użyj łączy z sekcji [Scenariusze zmiany alokacji](#scenarios-for-reallocation) w dalszej części tego artykułu.

[![Karta Rozpoznawanie przychodów na stronie Parametry księgi głównej.](./media/01_RevRecScenarios.png)](./media/01_RevRecScenarios.png)

Jeśli dla opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** jest ustawiona wartość **Tak**, proces zmiany alokacji pozwala uzyskać następujący wynik:

- W celu wycofania faktury wymagającej korekty w rozrachunkach z odbiorcami zostaje utworzony dokument kredytowy.

    - Dokument kredytowy jest oznaczony numerem oryginalnej faktury, po którym następuje oznaczenie liczbowe „-1”.
    - Dokument kredytowy jest automatycznie rozliczany względem oryginalnej faktury. Jeśli oryginalna faktura została już rozliczona z użyciem innego dokumentu kredytowego lub płatności, to rozliczenie zostaje automatycznie wycofywane.
    - Dokument kredytowy zostaje zaksięgowany w księdze głównej w celu wycofania wpisu księgowania zaksięgowanego w związku z oryginalną fakturą. Transakcje zapasów i kosztu własnego sprzedaży (KWS) nie są wycofywane.

- W obszarze rozrachunków z odbiorcami zostaje utworzona nowa faktura na podstawie cen uwzględniających zmianę alokacji.

    - Nowa faktura jest oznaczona numerem oryginalnej faktury, po którym następuje oznaczenie liczbowe „-2”.
    - Nowa faktura jest automatycznie rozliczana względem dowolnego dokumentu kredytowego lub płatności, które wcześniej rozliczono przy użyciu oryginalnej faktury.
    - Nowa faktura zostaje zaksięgowana w księdze głównej z uwzględnieniem nowych cen przychodów po zmianie alokacji. Nie jest ona ponownie księgowana na kontach zapasów ani KWS, ponieważ wpisy te są zachowane we wpisie księgowania oryginalnej faktury.

Jeśli dla opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** jest ustawiona wartość **Nie**, proces zmiany alokacji pozwala uzyskać następujący wynik:

- Wpis księgowania wycofania zostaje zaksięgowany tylko w księdze głównej. Zostaje wycofane całe księgowanie z oryginalnej faktury z wyjątkiem wpisów na koncie zapasów i KWS.
- Nowy wpis księgowania zostaje zaksięgowany tylko w księdze głównej na podstawie nowych cen przychodów uwzględniających zmianę alokacji. Nie jest ona ponownie księgowana na kontach zapasów ani KWS, ponieważ wpisy te są zachowane we wpisie księgowania oryginalnej faktury.
- Wpis nie ma wpływu na fakturę na stronie **Transakcje odbiorcy** ani nie powoduje jej zmiany, jako że nadal odzwierciedla oryginalny wpis księgowania. Nie ma żadnego odwołania do wpisów wycofania ani nowych wpisów księgowania.

Jak już wspomniano, można zaktualizować tylko księgę główną lub zarówno księgę główną, jak i rozrachunki z odbiorcami. Oba podejścia mają swoje wady i zalety. Zalecamy ocenę wymagań organizacji w celu ustalenia, które podejście należy zastosować. W przypadku aktualizacji zarówno księgi głównej, jak i rozrachunków z odbiorcami, poprawne wpisy księgowania będą widoczne na nowej fakturze oraz w dokumencie na stronie **Transakcje odbiorcy**. Ponadto zaktualizowane wpisy księgowania zostaną zaksięgowane w procesie rozliczania w celu zaksięgowania wszelkich zysków lub strat i rabatów gotówkowych. Z drugiej strony dokument kredytowy i nowa faktura będą widoczne na wyciągach odbiorcy i raportach wiekowania, podobnie jak ma to miejsce w przypadku innych dokumentów kredytowych i faktur dla odbiorców. Opis tych dokumentów będzie zawierał informację, że zostały one utworzone w procesie korekty księgowania.

## <a name="run-the-reallocation-process"></a>Uruchamianie procesu zmiany alokacji

Aby rozpocząć proces zmiany alokacji, wybierz opcję **Zmień alokację ceny za pomocą nowych wierszy zamówienia** w każdym zamówieniu sprzedaży, które musi zostać objęte zmianą alokacji. Możesz również wybrać kolejno **Rozpoznawanie przychodów \> Zadania okresowe \> Zmień alokację ceny za pomocą nowych wierszy zamówienia**, a następnie wprowadzić odpowiednie filtry, takie jak konto odbiorcy.

[![Strona Zmień alokację ceny za pomocą nowych wierszy zamówienia.](./media/02_RevRecScenarios.png)](./media/02_RevRecScenarios.png)

Górna siatka na stronie **Zmień alokację ceny za pomocą nowych wierszy zamówienia** nosi nazwę **Sprzedaż**. Zawiera ona listę zamówień sprzedaży dla odbiorcy. Wybierz zamówienia sprzedaży, które muszą zostać objęte zmianą alokacji. Jeśli zamówienie sprzedaży ma identyfikator zmiany alokacji, zostało już oznaczone do zmiany alokacji przez innego użytkownika. Jeśli alokacja co najmniej jednego zamówienia sprzedaży została poprzednio zmieniona i musi zostać uwzględniona w innej alokacji, należy najpierw cofnąć zmianę alokacji tych zamówień sprzedaży. Można ją następnie uwzględnić w nowej alokacji. Aby uzyskać bardziej szczegółowe informacje, zobacz sekcje [Cofnij zmianę alokacji](#undo-a-reallocation) i [Wielokrotnie zmień alokację](#reallocate-multiple-times) w dalszej części tego artykułu.

Dolna siatka widoczna na stronie nosi nazwę **Wiersze**. Po wybraniu co najmniej jednego zamówienia sprzedaży w siatce **Sprzedaż** w siatce **Wiersze** pojawiają się wiersze zamówienia sprzedaży. Wybierz wiersze zamówienia sprzedaży, które muszą zostać objęte zmianą alokacji. Jeśli wybrano tylko jedno zamówienie sprzedaży, wiersze w tym zamówieniu sprzedaży muszą zostać objęte zmianą alokacji. Taka sytuacja może mieć miejsce, gdy jeden z wierszy zamówienia sprzedaży został wcześniej zafakturowany, a następnie dodany został nowy wiersz albo istniejący wiersz został usunięty lub anulowany. Jeśli wiersz został usunięty, nie będzie widoczny w siatce. W związku z tym nie można go wybrać. Nadal będzie on jednak brany pod uwagę przy uruchamianiu procesu zmiany alokacji.

Po zakończeniu wybierania wymaganych wierszy zamówienia sprzedaży należy użyć przycisków w okienku akcji w sposób opisany w poniżej:

- **Aktualizuj zmianę alokacji** — umożliwia obliczanie nowych kwot cen przychodów dla wybranych wierszy zamówienia sprzedaży. Jeśli wiersz został usunięty lub anulowany, zmiana alokacji obejmie tylko istniejące wiersze, które wybrano. Na poniższej ilustracji pokazano przykład wierszy zamówienia sprzedaży przed aktualizacją zmiany alokacji.

    [![Wiersze zamówienia sprzedaży przed aktualizacją zmiany alokacji.](./media/03_RevRecScenarios.png)](./media/03_RevRecScenarios.png)

    Nowe kwoty cen przychodu są widoczne w kolumnie **Kwota po zmianie alokacji** w siatce **Wiersze**. Na tym etapie zmiana alokacji została przetworzona, ale nie została jeszcze obliczona. Na poniższej ilustracji pokazano przykład wierszy zamówienia sprzedaży po aktualizacji zmiany alokacji.

    [![Wiersze zamówienia sprzedaży po aktualizacji zmiany alokacji.](./media/04_RevRecScenarios.png)](./media/04_RevRecScenarios.png)

- **Przetwarzanie** — przetwarzanie lub księgowanie cen przychodu po zmianie alokacji. Po wybraniu tego przycisku nie można wycofać zmiany alokacji. Jeśli przed wybraniem opcji **Przetwarzanie** nie wybrano opcji **Aktualizuj zmianę alokacji**, zmiana alokacji zostanie uruchomiona automatycznie.

    - Jeśli żaden wiersz zamówienia sprzedaży nie został zafakturowany, kwoty ceny przychodu zostaną zaktualizowane na wszystkich zamówieniach sprzedaży, które wybrano do zmiany alokacji.
    - Jeśli zafakturowano co najmniej jeden wiersz zamówienia sprzedaży. zostaną zaksięgowane wpisy księgowania korygującego oraz skorygowane wszelkie szczegóły harmonogramu przychodów utworzone dla zafakturowanego wiersza zamówienia sprzedaży.

- **Oczekiwany załącznik** — umożliwia wyświetlenie podglądu wpisów księgowania utworzonych dla wszelkich zafakturowanych wierszy zamówienia sprzedaży. Jeśli nie zafakturowano żadnych wierszy, nie zostanie wyświetlona żadna zawartość. Jeśli przed wybraniem opcji **Oczekiwany załącznik** nie wybrano opcji **Aktualizuj zmianę alokacji**, zmiana alokacji zostanie uruchomiona automatycznie.
- **Zmiana alokacji przychodu** — pozwala otworzyć stronę, na której jest widoczna alokacja cen przychodów dla wszystkich wybranych wierszy. Nie można edytować żadnych informacji na tej stronie. Na stronie są widoczne kwoty dla wierzy użyte w celu przeprowadzenia procesu zmiany alokacji.

    [![Kwoty dla wierszy użyte do przeprowadzenia procesu zmiany alokacji.](./media/05_RevRecScenarios.png)](./media/05_RevRecScenarios.png)

- **Zresetuj dane dla wybranego odbiorcy** — pozwala wyczyścić dane w tabeli zmiany alokacji tylko dla wybranego odbiorcy w przypadku, gdy proces zmiany alokacji został rozpoczęty, ale nie został zakończony. Przykład: oznaczasz wiele wierszy zamówienia sprzedaży do zmiany alokacji i pozostawiasz otwartą stronę bez wybrania opcji **Przetwarzanie**. Limit czasu dla strony zostaje przekroczony. W takim przypadku wiersze zamówienia sprzedaży pozostaną oznaczone i inny użytkownik nie będzie mógł zakończyć procesu zmiany alokacji. Po otwarciu tej strony może nawet okazać się, że jest ona pusta. W takiej sytuacji można użyć przycisku **Zresetuj dane dla wybranego odbiorcy** w celu wyczyszczenia nieprzetworzonych zamówień sprzedaży, aby inny użytkownik mógł zakończyć proces zmiany alokacji.

## <a name="undo-a-reallocation"></a>Cofnij zmianę alokacji

Zmiana alokacji została cofnięta przez uruchomienie innej zmiany alokacji. Zmiana alokacji jest wykonywana ponownie. Użytkownik wybiera różne wiersze zamówienia sprzedaży, które zostaną dołączone do drugiego procesu zmiany alokacji.

Jeśli zmiana alokacji została wykonana dla co najmniej dwóch oddzielnych zamówień sprzedaży, można ją cofnąć, wybierając opcję **Zmień alokację ceny za pomocą nowych wierszy zamówienia** z dowolnego zamówienia sprzedaży uwzględnionego w zmianie alokacji. Nie można przejść do opcji **Rozpoznawanie przychodu \> Zadania okresowe \> Zmień alokację ceny za pomocą nowych wierszy zamówienia** w celu cofnięcia zmiany alokacji, ponieważ otwarta w ten sposób strona pokazuje tylko zamówienia sprzedaży, które nie mają identyfikatora zmiany alokacji. Identyfikator zmiany alokacji jest przypisywany po zmiany alokacji dokumentu.

Na stronie **Zmień alokację ceny za pomocą nowych wierszy zamówienia** usuń zaznaczenie z wszelkich zamówień sprzedaży, które powinny zostać wykluczone z umowy handlowej. Do przetworzenia zmiany alokacji służą odpowiednie przyciski w okienku akcji, takie jak **Aktualizuj zmianę alokacji** i **Proces**. Jeśli wszystkie zamówienia sprzedaży, z wyjątkiem aktywnego zamówienia sprzedaży, nie są zaznaczone, identyfikator zmiany alokacji zostanie usunięty podczas przetwarzania zmiany.

Jeśli zmiana alokacji została wykonana przez dodanie nowego wiersza do całkowicie lub częściowo zafakturowanego zamówienia sprzedaży, można ją cofnąć tylko przez usunięcie tego wiersza z zamówienia sprzedaży, a następnie ponowne uruchomienie zmiany alokacji. Wiersz zamówienia sprzedaży musi zostać usunięty, ponieważ zakłada się, że wszystkie wiersze zamówienia sprzedaży są częścią tej samej umowy. Nie można usunąć zaznaczenia wiersza zamówienia sprzedaży, jeśli użytkownik jest na stronie **Zmień alokację ceny za pomocą nowych wierszy zamówienia**.

## <a name="reallocate-multiple-times"></a>Wielokrotnie zmień alokację

Jeśli w umowie wprowadzono wiele zmian, można dokonać wielokrotnej zmiany alokacji dla tego samego zamówienia sprzedaży. Każda zmiana alokacji wyzwala przypisanie identyfikatora zmiany alokacji do zamówienia sprzedaży lub grupy zamówień sprzedaży w celu zgrupowania zmian. W przypadku wielu zmian alokacji każda dodatkowa zmiana alokacji używa tego samego identyfikatora zmiany alokacji, co pierwsza.

Na przykład zostało wprowadzone zamówienie sprzedaży 00045, które ma wiele wierszy. Po pełnym zafakturowaniu zamówienia sprzedaży jest do niego dodawany nowy wiersz zamówienia sprzedaży. Następnie zmiana alokacji jest uruchamiana przez otwarcie strony **Zmień alokację ceny za pomocą nowych wierszy zamówienia** z zamówienia sprzedaży 00045 lub przez przejście do opcji **Rozpoznawanie przychodu \> Zadania okresowe \> Zmień alokację ceny za pomocą nowych wierszy zamówienia**. Do zamówienia sprzedaży zostanie przypisany identyfikator zmiany alokacji **Reall000001**.

Dla tej samej umowy zostaje utworzone drugie zamówienie sprzedaży: 00052. Zmianę alokacji można uruchomić ponownie, otwierając stronę **Zmień alokację ceny za pomocą nowych wierszy zamówienia** z zamówienia sprzedaży 00045, ale nie z zamówienia sprzedaży 00052. Jeśli otworzysz stronę **Zmień alokację ceny za pomocą nowych wierszy zamówienia** z zamówienia sprzedaży 00052, zamówienie sprzedaży 00045 nie będzie wyświetlane, ponieważ przypisano do niego identyfikator zmiany alokacji. Na stronie widać tylko zamówienia sprzedaży, które nie mają identyfikatora zmiany alokacji.

Istnieją dwa sposoby na przeprowadzenie drugiej zmiany alokacji. Można cofnąć zmianę alokacji zamówienia sprzedaży 00045. W takim przypadku identyfikator zmiany alokacji jest usuwany, a następnie można przeprowadzić zmianę alokacji z zamówienia sprzedaży 00045 lub zamówienia sprzedaży 00052. Alternatywnie można otworzyć stronę **Zmień alokację ceny za pomocą nowych wierszy zamówienia** z zamówienia sprzedaży 00045 i dodać drugie zamówienie sprzedaży. Podczas przetwarzania zmiany alokacji identyfikator zmiany alokacji **Reall000001** zostanie przypisany zarówno do zamówienia sprzedaży 00045, jak i do zamówienia sprzedaży 00052.

## <a name="scenarios-for-reallocation"></a>Scenariusze zmiany alokacji

Poniższe tematy uwzględniają różne scenariusze dotyczące rozpoznawania przychodów:

- [Zmiana alokacji rozpoznawania przychodów — scenariusz 1](rev-rec-reallocation-scenario-1.md) — zostają wprowadzone dwa zamówienia sprzedaży, które są wyłącznie potwierdzane. Wyniki tego scenariusza będą podobne także w przypadku, gdy liczba potwierdzonych zamówień sprzedaży będzie większa niż dwa.
- [Zmiana alokacji rozpoznawania przychodów — scenariusz 2](rev-rec-reallocation-scenario-2.md) — zostają wprowadzone dwa zamówienia sprzedaży, po czym odbiorca dodaje pozycję do umowy po zafakturowaniu pierwszego zamówienia sprzedaży.
- [Zmiana alokacji rozpoznawania przychodów — scenariusz 3](rev-rec-reallocation-scenario-3.md) — do istniejącego, zafakturowanego zamówienia sprzedaży zostaje dodany nowy wiersz.
- [Zmiana alokacji rozpoznawania przychodów — scenariusz 4](rev-rec-reallocation-scenario-4.md) — z istniejącego, częściowo zafakturowanego zamówienia sprzedaży zostaje usunięty wiersz.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
