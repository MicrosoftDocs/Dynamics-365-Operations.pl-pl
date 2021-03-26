---
title: Konfiguracja rozpoznawania przychodów
description: W tym temacie opisano opcje konfiguracji dotyczące rozpoznawania przychodów oraz ich implikacje.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: ba9f58bc21bed25a5e86cb0c9133507a83371d83
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245671"
---
# <a name="revenue-recognition-setup"></a>Konfiguracja rozpoznawania przychodów
[!include [banner](../includes/banner.md)]

Dodano nowy moduł **Rozpoznawanie przychodów** obejmujący elementy menu dla wszystkich wymaganych ustawień. W tym temacie opisano opcje konfiguracji oraz ich implikacje.

> [!NOTE]
> Funkcji Rozpoznawanie przychodów nie można włączyć za pomocą modułu Zarządzanie funkcjami. Obecnie można ją włączyć tylko przy użyciu kluczy konfiguracji.

> Funkcje rozpoznawania przychodów, w tym funkcja pakietu, nie są obsługiwane w kanałach Commerce (handel elektroniczny, punkt sprzedaży, biuro obsługi). Towary skonfigurowane pod kątem rozpoznawania przychodu nie powinny być dodawane do zamówień ani transakcji tworzonych w kanałach Commerce.

Moduł **Rozpoznawanie przychodów** ma następujące opcje konfiguracji:

- Arkusze rozpoznawania przychodów
- Parametry rozpoznawania przychodów
- Harmonogramy przychodów 
- Ustawienia zapasów

    - Grupy pozycji i zwolnione produkty
    - Definiowanie harmonogramu przychodów
    - Definiowanie ceny przychodu

        - Profile księgowania
        - Pakiety

    - Składniki pakietu
    - Element pakietu

- Ustawienia projektu

## <a name="revenue-recognition-journals"></a>Arkusze rozpoznawania przychodów

Wprowadzono nowy typ arkusza dla rozpoznawania przychodów. Arkusz jest wymagany i jest używany w dwóch scenariuszach.

Pierwszy scenariusz występuje po spełnieniu wszystkich zobowiązań umownych, podczas gdy przychód odroczony jest rozpoznawany przez utworzenie arkusza rozpoznawania przychodów opartego na szczegółach harmonogramu przychodów. Arkusz zawiera wpis księgowania, który przenosi saldo z konta księgowego na odroczone przychody na konto księgowe odroczonego przychodu.

Drugi scenariusz występuje, gdy zostanie utworzony arkusz po zmianie alokacji. Zmiana alokacji ma miejsce, gdy wiersz zamówienia sprzedaży zostanie dodany do wcześniej zafakturowanego zamówienia sprzedaży lub gdy tworzone jest nowe zamówienie sprzedaży zawierające wiersz będący częścią oryginalnej umowy. Jeśli faktura została zaksięgowana przed dodaniem nowego wiersza zamówienia sprzedaży, należy utworzyć wpis księgowania korygującego dla zaksięgowanej faktury dla odbiorcy.

Arkusz jest ustawiany na stronie **Nazwa arkusza** (**Rozpoznawanie przychodów \> Ustawienia \> Nazwy arkusza**). Typ arkusza musi być określony jako **Rozpoznawanie przychodów**. Arkusz rozpoznawania przychodów umożliwia wybranie warstwy księgowania, na której ma być wykonywane księgowanie.

## <a name="parameters-for-revenue-recognition"></a>Parametry rozpoznawania przychodów

Ustawienia rozpoznawania przychodów są konfigurowane na karcie **Rozpoznawanie przychodów** na stronie **Parametry księgi głównej** (**Rozpoznawanie przychodów \> Ustawienia \> Parametry księgi głównej**). Dostępne są następujące ustawienia:

- **Nazwa arkusza rozpoznawania przychodów** — umożliwia wybór arkusza utworzonego dla rozpoznawania przychodów. Arkusz jest wymagany, gdy przychód jest rozpoznawany na podstawie harmonogramu przychodów lub gdy następuje ponowna alokacja dla zamówienia sprzedaży, które zostało już zafakturowane.
- **Włącz metodę alokacji rabatu** — tę opcję należy ustawiać na **Tak**, aby określić cenę przychodu za pośrednictwem alokacji rzeczywistej wartości rynkowej określonej w cenie przychodu dla każdego zwolnionego produktu. Ta alokacja obejmuje przydzielanie rabatów wiersza dla poszczególnych pozycji. Jeśli ta opcja jest ustawiona na **Nie**, system używa ceny mediany określonej w cenie przychodu każdego zwolnionego produktu. Jeśli ta opcja jest ustawiona na wartość **Nie**, ale dla zwolnionych produktów nie skonfigurowano ceny mediany, alokacja ceny przychodu nie zachodzi.
- **Uwzględnij rabaty nagłówka** — tę opcję należy ustawiać na wartość **Tak**, aby określić cenę przychodu, przydzielając rabaty nagłówka dla poszczególnych produktów. Jeśli dla tej opcji jest ustawiona wartość **Nie**, rabat nagłówka nie jest uwzględniany w alokacji ceny przychodu.
- **Wyłącz warunki umowy** — ta opcja jest ustawiana na wartość **Tak**, jeśli produkty mające typ przychodu **Obsługa po wygaśnięciu umowy** można zwolnić, nawet jeśli nie są dla nich zdefiniowane daty rozpoczęcia i zakończenia obowiązywania umowy. Zazwyczaj daty rozpoczęcia i zakończenia umowy są wymagane dla pozycji typu przychodu **Obsługa po wygaśnięciu umowy**. Jeśli nie zostaną zdefiniowane daty rozpoczęcia i zakończenia obowiązywania umowy, szczegóły dotyczące harmonogramu przychodów w księgowaniu są obliczane przy użyciu liczby wystąpień i daty faktury.
- **Księgowanie korekt faktury do rozrachunków z odbiorcami podczas ponownego alokowania** — w przypadku ponownego alokowania faktur, które zostały już zaksięgowane, wpis księgowy dla zaksięgowanej faktury musi zostać poprawiony. Ta opcja służy do określenia sposobu wykonania korekty.

    - Ustawienie tej opcji na wartość **Nie** ograniczy księgowanie transakcji korygującej do księgi głównej. Jeśli ta opcja jest ustawiona na **Nie**, w rozrachunkach z odbiorcami nie są tworzone dodatkowe dokumenty dla wewnętrznej korekty księgowej. Podczas opłacania faktury proces rozliczenia używa starego wpisu księgowania do księgowania rabatów gotówkowych lub wszelkich zrealizowanych zysków lub strat.
    - Ustawienie tej opcji na wartość **Tak** powoduje automatyczne tworzenie dokumentu wycofania i nowej faktury dla korygowanej transakcji w module Rozrachunki z odbiorcami. Ponieważ korekta jest wewnętrzną korektą księgowania, nowe dokumenty nie są wysyłane ani przekazywane odbiorcy. Dokument wycofania jest rozliczany z oryginalną fakturą, a nowa skorygowana faktura jest opłacana przez odbiorcę. Należy zwrócić uwagę, że wszystkie trzy dokumenty są wyświetlane w raportach, np. wyciągach odbiorców.

[![Informacje o ustawieniach](./media/revenue-recognition-setup-info.png)](./media/revenue-recognition-setup-info.png)

## <a name="revenue-schedules"></a>Harmonogramy przychodów

Harmonogram przychodów musi zostać utworzony dla każdego wystąpienia przychodu, dla którego można odroczyć przychód. Jeśli na przykład organizacja oferuje pomoc techniczną w okresach 6-miesięcznych, 12-miesięcznych, 18-miesięcznych i 24-miesięcznych, należy utworzyć harmonogram przychodów dla każdego okresu. Konfiguracja harmonogramu przychodów określa sposób alokacji ceny przychodu w ramach wybranej liczby okresów. Określa także domyślne daty wprowadzane dla harmonogramu przychodów tworzonego podczas księgowania faktury.

Jeśli przychód jest rozpoznawany według punktów kontrolnych, zaleca się utworzenie harmonogramu rozpoznawania przychodów dla liczby punktów kontrolnych, niezależnie od dat uznania. Po utworzeniu harmonogramów można je edytować tak, aby odzwierciedlały oczekiwane daty punktów kontrolnych. Te rekordy można wstrzymać do momentu powiadomienia, że punkt kontrolny został osiągnięty i można rozpoznać przychód.

Harmonogramy przychodów są tworzone na stronie **Harmonogramy przychodów** (**Rozpoznawanie przychodów \> Ustawienia \> Harmonogramy przychodów**).

[![Harmonogramy przychodów](./media/revenue-recognition-revenue-schedules.png)](./media/revenue-recognition-revenue-schedules.png)

Wprowadź wartości opisowe w polach **Harmonogram przychodów** i **Opis**. Poniższe dodatkowe ustawienia są używane do tworzenia harmonogramu przychodów podczas księgowania faktury.

- **Wystąpienia** — umożliwia wprowadzenie liczby miesięcy lub wystąpień odroczenia przychodu.
- **Wstrzymaj automatycznie** — to pole wyboru należy zaznaczyć, jeśli wszystkie wiersze harmonogramu przychodów powinny być automatycznie wstrzymane po zaksięgowaniu faktury. Wstrzymanie musi zostać usunięte ręcznie z każdego wiersza harmonogramu, zanim będzie możliwe rozpoznanie przychodu wiersza.
- **Automatyczne warunki umowy** — to pole wyboru należy zaznaczyć, jeśli daty rozpoczęcia i zakończenia umowy mają być ustawiane automatycznie. Te daty są ustawiane automatycznie tylko dla zwolnionych produktów typu przychodu **Obsługa po wygaśnięciu umowy**. Data rozpoczęcia umowy jest automatycznie ustawiana na żądaną datę wysyłki w wierszu zamówienia sprzedaży, a data zakończenia umowy jest automatycznie ustawiana na datę początkową powiększoną o liczbę miesięcy lub wystąpień zdefiniowaną w ustawieniach harmonogramu przychodów. Na przykład produkt w wierszu zamówienia sprzedaży dotyczy gwarancji na jeden rok. Domyślny harmonogram przychodów to **12M** (12 miesięcy) i dla tego harmonogramu przychodów jest zaznaczone pole wyboru **Automatyczne warunki umowy**. Jeśli wiersz zamówienia sprzedaży ma żądaną datę wysyłki w dniu 16 grudnia 2019 r., to domyślną datą rozpoczęcia umowy jest 16 grudnia 2019 r., a domyślną datą końcową umowy jest 15 grudnia 2020 r.
- **Podstawa uznania** — podstawa uznania określa sposób alokacji ceny przychodu w poszczególnych wystąpieniach.

    - **Miesięcznie według dat** — kwota jest alokowana na podstawie rzeczywistych dni w każdym miesiącu.
    - **Miesięcznie** — kwota jest alokowana równomiernie między liczbą miesięcy zdefiniowaną w wystąpieniach.
    - **Wystąpienia** — kwota jest alokowana równomiernie między wystąpieniami, ale może zawierać dodatkowy okres, jeśli jako konwencję uznania została wybrana **Rzeczywista data rozpoczęcia**.

- **Konwencja uznania** — konwencja uznania określa domyślne daty określone w harmonogramie przychodów dla faktury.

    - **Rzeczywista data rozpoczęcia** — harmonogram jest tworzony przy użyciu daty początkowej umowy (w przypadku pozycji z obsługą po wygaśnięciu umowy \[PCS\]) lub daty faktury (dla podstawowych i nieistotnych pozycji).
    - **1. dzień miesiąca** — data pierwszego wiersza harmonogramu to data rozpoczęcia umowy (lub data faktury). Jednak wszystkie kolejne wiersze harmonogramu są tworzone dla pierwszego dnia miesiąca.
    - **Podział półmiesięczny** — data pierwszego wiersza harmonogramu zależy od daty faktury. Jeśli faktura zostanie zaksięgowana między pierwszym a piętnastym dniem miesiąca, harmonogram przychodów jest tworzony przy użyciu pierwszego dnia miesiąca. Jeśli faktura zostanie zaksięgowana po szesnastym dniu miesiąca, harmonogram przychodów jest tworzony przy użyciu pierwszego dnia następnego miesiąca.
    - **1. dzień następnego miesiąca** — data w harmonogramie to pierwszy dzień następnego miesiąca.

Wybierz przycisk **Szczegóły harmonogramu przychodów**, aby wyświetlić okresy ogólne i wartości procentowe rozpoznawane w każdym okresie. Domyślnie **Wartość procentowa rozpoznawania** jest równo podzielona przez liczbę okresów. Jeśli podstawą rozpoznawania jest wartość **Miesięczna** lub **Liczba wystąpień**, można zmienić wartość procentową rozpoznawania. Podczas zmiany wartości procentowej rozpoznawania wyświetlany jest komunikat z ostrzeżeniem informującym, że suma nie jest równa 100 procent. Po wyświetleniu komunikatu można kontynuować edycję wierszy. Jednak suma wartości procentowych musi być równa 100 przed zamknięciem strony.

[![Szczegóły harmonogramu przychodów](./media/revenue-recognition-revenue-schedule-details.png)](./media/revenue-recognition-revenue-schedule-details.png)

## <a name="inventory-setup"></a>Ustawienia zapasów

Przychód dla zwolnionych produktów można rozpoznać w zamówieniach sprzedaży, ale nie w kategoriach sprzedaży w zamówieniach sprzedaży lub fakturach niezależnych, jeśli w dokumencie brak pozycji. Opcje wybrane podczas konfigurowania zwolnionych produktów decydują o rozpoznaniu przychodów za daną pozycję. Na przykład opcje te decydują o tym, czy cena przychodu jest alokowana oraz czy przychód jest odroczony za pomocą harmonogramu przychodów.

Konfigurację można rozpocząć na skróconej karcie **Rozpoznawanie przychodów** strony **Grupa pozycji** (**Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów i produktu \> Grupa pozycji**). Ta strona zawiera kilka pól ustawień. Pola te służą do ustawiania wartości domyślnych tylko dla nowych zwolnionych produktów, które są tworzone w systemie. W miarę tworzenia nowych produktów wartości ustawione w tym miejscu są domyślnie wprowadzane dla grupy pozycji. Wartości domyślne dla zwolnionych produktów można zastąpić na stronie **Zwolnione produkty** (**Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów i produktu \> Zwolnione produkty**). Wartości domyślne ustawione dla zwolnionych produktów są następnie przenoszone do zamówienia sprzedaży.

## <a name="item-groups-and-released-products"></a>Grupy pozycji i zwolnione produkty

### <a name="define-the-revenue-schedule"></a>Definiowanie harmonogramu przychodów

Przychód z wiersza zamówienia sprzedaży jest odroczony, jeśli harmonogram przychodów jest zdefiniowany dla zwolnionego produktu i używany domyślnie w wierszu zamówienia sprzedaży. Jeśli to ustawienie powinno być używane domyślnie dla danego produktu, można zdefiniować harmonogram przychodów na skróconej karcie **Rozpoznawanie przychodów** strony **Grupa pozycji** (**Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów i produktu \> Grupa pozycji**). Można również zdefiniować ustawienie zwolnionego produktu na skróconej karcie **Rozpoznawanie przychodów** strony **Zwolnione produkty** (**Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów \> Zwolnione produkty**).

W polu **Harmonogram przychodów** wybierz harmonogram przychodów odpowiadający okresowi, w którym przychód musi zostać odroczony. Harmonogram przychodów jest automatycznie wprowadzany w wierszu zamówienia sprzedaży, a szczegóły harmonogramu są tworzone podczas księgowania faktury zamówienia sprzedaży.

### <a name="define-the-revenue-price"></a>Definiowanie ceny przychodu

Grupy pozycji i zwolnione produkty można konfigurować za pomocą metody ceny mediany lub metody alokacji rabatu. Obie metody wymagają różnych ustawień na stronie **Zwolnione produkty**:

- **Czy alokacja przychodu jest aktywna** — ustawienie tej opcji na wartość **Tak** powoduje uwzględnienie zwolnionego produktu w obliczeniu alokacji przychodu. Jeśli ta opcja jest ustawiona na **Nie**, zwolniony produkt używa metody ceny mediany, jeśli cena mediany została zdefiniowana. Jeśli cena mediany nie została zdefiniowana, do księgowania przychodu lub przychodu odroczonego używana jest cena jednostkowa w wierszu zamówienia sprzedaży.
- **Typ przychodu** — umożliwia wybór typu przychodu definiującego produkt zwolniony:

    - **Podstawowe** — pozycja jest podstawowym źródłem przychodu organizacji. Ta wartość jest ustawieniem domyślnym.
    - **Nieistotne** — pozycja nie jest podstawowym źródłem przychodu organizacji. Po użyciu ustawień ceny mediany cena jest „wykształtowana” do ceny mediany, a następnie przydzielona. Na przykład podstawowa pozycja ma stałą cenę, która musi zostać uznana za przychód. Jeśli istnieje rabat, rabat może zostać wykształtowany z przychodu podstawowej pozycji, ale **tylko** do stałej kwoty ceny. Reszta rabatu jest wypłacona z przychodów nieistotnych pozycji. Alternatywnie rabat może nie być wykształtowany z przychodu podstawowej pozycji.
    - **Obsługa po wygaśnięciu umowy** — pozycja obsługuje inne elementy, które są uwzględnione w sprzedaży dla odbiorcy. Cena przychodu jest rozdzielana między podstawowymi i nieistotnymi produktami uwzględnionymi w sprzedaży. W zależności od konfiguracji pozycje z obsługą po wygaśnięciu umowy mogą nie wymagać, by daty rozpoczęcia i zakończenia obowiązywania umowy były określone w wierszu zamówienia sprzedaży.

- **Wyklucz z wykształtowania** — tę opcję należy ustawić na wartość **Tak**, aby wskazać, że cena mediany pozycji nie może zostać skorygowana poniżej minimalnej zdefiniowanej wartości procentowej lub powyżej maksymalnej wartości procentowej. Cena przychodu zostanie obliczona na podstawie ceny przychodu innego zwolnionego produktu, który jest uwzględniony w zamówieniu sprzedaży. Jeśli ta opcja jest ustawiona na **Nie**, cena mediany pozycji może zostać skorygowana lub wykształtowana. Należy zauważyć, że w przypadku sprzedaży więcej niż jednej pozycji ustawionej jako cena mediany, co najmniej jeden zwolniony produkt musi zostać ustawiony w taki sposób, by opcja **Wyklucz z wykształtowania** miała wartość **Nie**. W ten sposób istnieje co najmniej jedna pozycja, do której można przydzielić wszelkie różnice w cenie przychodu.
- **Cena mediany** — tę opcję należy ustawić na wartość **Tak**, aby wskazać, że cena przychodu pozycji powinna zostać skorygowana tak, aby była równa cenie mediany, jeśli jest niższa niż określona minimalna tolerancja lub większa od maksymalnej tolerancji, oraz że kwota wykształtowana powinna być alokowana do wierszy, które zawierają produkty z opcją **Wyklucz z wykształtowania** ustawioną na **Nie**.

    - **Maksymalna tolerancja** — umożliwia wprowadzenie procentu powyżej dozwolonej ceny mediany.
    - **Minimalna tolerancja** — umożliwia wprowadzenie procentu poniżej dozwolonej ceny mediany.

Po zakończeniu konfigurowania ustawień zwolnionego produktu należy ręcznie zdefiniować cenę przychodu, wprowadzając rzeczywistą cenę wartości lub cenę mediany (jeśli jest używana metoda ceny mediany) na stronie **Ceny przychodu** (przejdź do **Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów \> Zwolnione produkty**, a następnie w okienku akcji na karcie **Sprzedaż** w grupie **Rozpoznawanie przychodów** wybierz **Ceny przychodu**).

[![Ceny przychodu](./media/revenue-recognition-revenue-prices.png)](./media/revenue-recognition-revenue-prices.png)

Cena przychodu, która jest ręcznie zdefiniowana na tej stronie, służy do ustalania alokacji ceny przychodu na poszczególnych zamówieniach sprzedaży na podstawie zdefiniowanych kryteriów. Każde kryterium jest dopasowywane do wiersza zamówienia sprzedaży w celu określenia ceny przychodu, która powinna zostać użyta w procesie alokacji.

- **Kod pozycji** i **Relacja produktu** — cenę przychodu można zdefiniować dla pojedynczego produktu lub grupy produktów. W przypadku wybrania opcji **Tabela** w polu **Kod pozycji** wybierz produkt zwolniony w polu **Relacja produktu**. W przypadku wybrania opcji **Grupa** w polu **Kod pozycji** wybierz grupę pozycji w polu **Relacja produktu**.
- **Kod konta** i **Numer konta/grupy** — cenę przychodu można zdefiniować dla wszystkich odbiorców, pojedynczego odbiorcy lub grupy odbiorców. W przypadku wybrania opcji **Wszystkie** w polu **Kod konta** cena będzie używana dla wszystkich odbiorców. W przypadku wybrania opcji **Tabela** w polu **Kod konta** wybierz odbiorcę w polu **Numer konta/grupy**. W przypadku wybrania opcji **Grupa** w polu **Kod konta** wybierz grupę w polu **Numer konta/grupy**.
- **Waluta** — należy wprowadzić oddzielną cenę przychodu dla każdej waluty, w której wprowadzane jest zamówienie sprzedaży. Na przykład, jeśli obecnie sprzedaż dokonywana jest w dolarach amerykańskich, dolarach kanadyjskich i euro, należy zdefiniować cenę przychodu we wszystkich trzech walutach. Cena przychodu nie jest tłumaczona z jednej waluty, takiej jak waluta rozliczeniowa, na dowolną inną walutę transakcji, która jest używana.
- **Kwota lub procent listy** — służy do określania, czy cena przychodu jest ustawiona jako kwota, czy jako procent ceny katalogowej. W przypadku wybrania opcji **Procent listy** użytkownicy mogą wprowadzić cenę mediany jako procent ceny katalogowej zamiast kwoty. Wartość **Procent listy** jest używana tylko w przypadku zwolnionych produktów, które są skonfigurowane jako pozycje z obsługą po wygaśnięciu umowy.
- **Cena alokacji przychodu** — zależnie od wartości wybranej w polu **Kwota lub procent listy** wprowadź kwotę lub wartość procentową, która będzie stanowić cenę przychodu używaną do alokacji przychodu między elementami zamówienia sprzedaży.
- **Data początkowa** i **Data końcowa** — umożliwia wprowadzenie zakresu dat, dla którego jest aktywna cena przychodu. Te pola są opcjonalne.

Jeśli opcja **Włącz metodę alokacji rabatu** na stronie **Parametry księgi głównej** ma wartość **Tak**, a w polu **Typ przychodu** dla zwolnionego produktu ustawiono opcję **Obsługa po wygaśnięciu umowy**, należy również określić pozycje obsługiwane przez zwolniony produkt. Te ustawienia są konfigurowane na stronie **Podstawa konfiguracji** (przejdź do **Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów \> Zwolnione produkty**, a następnie w okienku akcji na karcie **Sprzedaż** w grupie **Rozpoznawanie przychodów** wybierz **Podstawa konfiguracji**).

Na stronie **Podstawa konfiguracji** dodaj zapis dla każdej grupy pozycji, którą obsługuje dana pozycja. W przypadku wystąpienia alokacji przychodu cena przychodu będzie dystrybuowana między ważnymi i nieistotnymi pozycjami z obsługą po wygaśnięciu umowy.

### <a name="posting-profiles"></a>Profile księgowania

Trzy dodatkowe typy księgowania umożliwiają odroczenie przychodu. Te typy księgowania konfiguruje się na karcie **Zamówienie sprzedaży** na stronie **Księgowanie** (**Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów i produktu \> Księgowanie**).

- **Przychód odroczony** — umożliwia wprowadzenie konta głównego dla ceny przychodu, która jest księgowana jako przychód odroczony (zamiast przychód). Cena przychodu jest odroczona, jeśli wiersz zamówienia sprzedaży ma harmonogram przychodów.
- **Odroczony koszt własny sprzedaży** — umożliwia wprowadzenie konta głównego dla kwoty kosztu własnego sprzedaży księgowanej do odroczonego kosztu własnego sprzedaży, jeśli przychód jest również odroczony.
- **Częściowe rozliczenie przychodu faktury** — umożliwia wprowadzenie konta głównego dla konta rozliczeniowego, które jest używane, gdy zamówienie sprzedaży jest częściowo zafakturowane lub gdy występuje zmiana alokacji. Saldo na tym koncie zwraca wartość 0 (zero), gdy zamówienia sprzedaży są w pełni zafakturowane.

### <a name="bundles"></a>Pakiety

Elementy pakietu są unikatowymi zwolnionymi produktami skonfigurowanymi w taki sposób, aby obejmowały składniki. Tej konfiguracji dokonuje się za pomocą funkcji listy składowej BOM. Po wprowadzeniu elementu pakietu w zamówieniu sprzedaży poszczególne składniki są używane do określenia cen przychodu i harmonogramów przychodów. Jednak dokumenty drukowane dla odbiorcy, takie jak zamówienie sprzedaży i faktura, odzwierciedlają element pakietu.

#### <a name="bundle-components"></a>Składniki pakietu

Składniki uwzględnione w pakiecie muszą zostać skonfigurowane na stronie **Zwolnione produkty** (**Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów i produktu \> Zwolnione produkty**). Te składniki to zwolnione produkty i muszą być skonfigurowane w ten sam sposób, jak produkty uwzględnione w BOM. Na przykład zwolniony produkt może być pozycją typu **Pozycja** lub **Usługa**, ale musi być przypisany do grupy modeli pozycji, w której opcja **Produkt magazynowany** jest ustawiona na wartość **Tak**. Aby uzyskać więcej informacji, zapoznaj się z dokumentacją konfiguracji pozycji BOM.

Składniki muszą być również skonfigurowane do rozpoznawania przychodu, tak jak w przypadku produktów, które mogą być sprzedawane pojedynczo w zamówieniu sprzedaży. Na przykład upewnij się, że dla każdego składnika zdefiniowano poprawną cenę przychodu i że podstawa ceny jest ustawiona dla pozycji z obsługą po wygaśnięciu umowy.

#### <a name="bundle-items"></a>Elementy pakietu

Podczas konfiguracji elementu pakietu należy ustawić dwa pola na stronie **Zwolnione produkty** (**Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów i produktu \> Zwolnione produkty**):

- Na skróconej karcie **Konstruuj** w polu **Typ produkcji** element musi być ustawiony jako pozycja BOM.
- Na skróconej karcie **Ogólne** w polu **Pakiet** należy oznaczyć pozycję jako element pakietu.

Składniki muszą być następnie przypisane do elementu nadrzędnego pakietu/BOM na stronie **Wersje BOM** (przejdź do **Rozpoznawanie przychodów \> Ustawienia \> Ustawienia zapasów i produktu \> Zwolnione produkty**, a następnie w okienku akcji na karcie **Konstruuj** w grupie **BOM** wybierz **Wersje BOM**). Aby uzyskać więcej informacji, zapoznaj się z dokumentacją konfiguracji elementów BOM.

[![Zwolnione produkty, harmonogramy BOM](./media/revenue-recognition-bom-scheduleds.jpg)](./media/revenue-recognition-bom-scheduleds.jpg)

Jeśli pakiet nadrzędny i składniki pakietu są ustawione jako alokowane, cena przychodu pakietu będzie dystrybuowana do składników na podstawie wartości procentowej marży przychodu.

## <a name="project-setup"></a>Ustawienia projektu

Rozpoznawanie przychodów może być również używane dla zamówień sprzedaży tworzonych za pośrednictwem projektów typu czas i materiały. W przypadku zamówień sprzedaży pochodzących z projektów wystarczy zdefiniować konta główne w profilach księgowania projektów, które są używane do księgowania faktur projektu. Konta główne są definiowane na stronie **Ustawienia księgowania w księdze** (**Rozpoznawanie przychodów \> Ustawienia \> Ustawienia projektu \> Ustawienia księgowania w księdze**).

- **Odroczony przychód faktury** (pod **Kontami przychodów**) — umożliwia wprowadzenie konta głównego dla ceny przychodu, która jest księgowana jako przychód odroczony (zamiast przychód). Cena przychodu jest odroczona, jeśli wiersz zamówienia sprzedaży ma harmonogram przychodów.
- **Odroczony koszt** (pod **Kontami kosztów**) — umożliwia wprowadzenie konta głównego dla kwoty kosztu własnego sprzedaży, księgowanej do odroczonego kosztu własnego sprzedaży, jeśli przychód jest również odroczony.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]