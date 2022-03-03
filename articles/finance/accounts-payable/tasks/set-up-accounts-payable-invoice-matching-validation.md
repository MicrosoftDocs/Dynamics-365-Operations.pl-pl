---
title: Konfigurowanie sprawdzania poprawności uzgadniania faktur rozrachunków z dostawcami
description: Ten temat zawiera informacje o tym, jak skonfigurować weryfikację uzgadniania rozrachunków z dostawcami.
author: abruer
ms.date: 02/14/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 602666df4cf015791398939a3067a2cae85a12eb
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182562"
---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Konfigurowanie sprawdzania poprawności uzgadniania faktur rozrachunków z dostawcami

[!include [banner](../../includes/banner.md)]

Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur. Jeśli firma śledzi wydatki, na przykład koszty frachtu, przy użyciu opłat, upewnij się, że wybrany został klucz konfiguracji Opłaty.  Uzgadnianie faktur rozrachunków z dostawcami jest procesem uzgadniania obejmującym informacje z faktury dostawcy, zamówienia zakupu i przyjęć produktów. Różnice między tymi dokumentami są nazywane rozbieżnościami (w uzgadnianiu/wykrytymi podczas uzgadniania). Rozbieżności w uzgadnianiu są porównywane z ustawionymi wartościami tolerancji. Jeśli rozbieżność przekracza wartość procentową lub kwotową, są wyświetlane ikony uzgadniania odchyleń na stronach **Faktura od dostawcy** i **Szczegóły uzgadniania faktur**.

## <a name="determine-which-invoice-matching-validation-to-use"></a>Określ, która weryfikacja zgodności z fakturą ma być użyta
Dostępne są cztery różne typy weryfikacji zgodności. 

- **Dopasowywanie poziomu wiersza** — najczęściej spotykanym typem uzgodnienia jest dopasowywanie wierszy. Uzgadnianie faktur może być dwukierunkowe lub trzyelementowe zasady uzgadniania wierszy. Domyślne dopasowywanie poziomu wiersza można określić dla firmy na stronie parametrów **Parametr rozrachunków z dostawcami**. Uzgadnianie dwuelementowe — porównuje cenę jednostkową faktury z informacjami o cenie jednostkowej na zamówieniu zakupu. Trzykierunkowe dopasowywanie dodatkowo porównuje ilość fakturowaną do dopasowanej ilości w dokumencie przyjęcia produktów.
- **Uzgodnienie sum faktur** — uzgadnianie sum na fakturze z sumami na zamówieniu zakupu. Ten typ uzgadniania faktury zawiera najmniej szczegółów, pozwala więc wybrać opcje kontroli maksymalnie skracające czas weryfikacji informacji o uzgadniania faktur. Porównywane są sześć sum, w tym suma częściowa, rabat końcowy, opłaty, podatki, zaokrąglenie i kwota faktury. System będzie sprawdzać, czy którakolwiek z tych wartości na fakturze odchyla od kwot oczekiwanych o więcej niż akceptowalne odchylenie.
- **Uzgadnianie opłat** — uzgadnianie informacji o opłatach (kwotach) na fakturze z informacjami o opłatach (kwotami) zamówieniu zakupu.
- **Sumy cenowe dla uzgodnienia wierszy** — ten typ dopasowywania jest przydatny w przypadku firm, które zazwyczaj pobierają wiele faktur dla pojedynczego wiersza zamówienia zakupu. Jeśli zazwyczaj jest pobierana tylko jedna faktura dla wiersza zamówienia zakupu, ten typ zgodności nie jest konieczny. To uzgodnienie wymaga włączenia dwóch lub trzech kierunków współfinansowania i służy jako nieprzekraczającej weryfikacji kwoty netto na podstawie wartości procentowych tolerancji i kwot.  Ten typ dopasowania porównuje informacje o cenie netto każdego wiersza na fakturze oraz wszystkich oczekujących i wcześniej zaksięgowanych wierszy faktury z kwotą netto w odpowiednim wierszu zamówienia zakupu. Kwota netto jest określana według następującego wzoru: (cena jednostkowa * ilość wiersza) + opłaty wiersza - rabaty wiersza. Podczas uzgadniania cen całkowitych według wartości procentowej system porównuje wartości w walucie transakcji. Podczas uzgadniania cen całkowitych według kwoty system porównuje wartości w walucie rozliczeniowej.

## <a name="set-up-parameters-to-enable-invoice-matching-validation"></a>Konfigurowanie parametrów, aby włączyć sprawdzanie zgodności faktur
1. Wybierz kolejno opcje **Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami.**
2. Kliknij kartę **Weryfikacja faktury**
3. Zaznacz lub wyczyść pole wyboru **Włącz weryfikację uzgadniania faktur** .
    * Wybierz, czy do zaksięgowania uzgadnianej faktury zawierającej rozbieżności wymagane jest jej wcześniejsze zatwierdzenie. Jeśli zaznaczysz opcję **Zezwól z ostrzeżeniem**, wizualne wskazanie pojawi się, gdy rozbieżność dla uzgadniania faktur przekroczy tolerancję. Jednak będzie można zaksięgować fakturę. Aby korzystać z przepływów pracy razem ze sprawdzaniem poprawności uzgadniania faktur, upewnij się, że pole **Księguj fakturę z rozbieżnościami** ma ustawioną wartość **Zezwól z ostrzeżeniem**, aby uniknąć konieczności wielokrotnego zatwierdzania.  
    * W polu **Automatycznie aktualizuj stan uzgodnienia nagłówka faktury** określ, czy uzgodnienie będzie wykonywane automatycznie podczas wprowadzania danych faktur przez system. Zalecanym ustawieniem jest wartość **Tak**, chyba że występują problemy z wydajnością podczas wprowadzania danych. Wyłączenie funkcji aktualizacji automatycznych może poprawić wydajność systemu, ponieważ podczas wprowadzania danych będzie pomijane sprawdzanie poprawności uzgadniania faktur,. Jeśli zostanie zaznaczona opcja **Nie**, pracownik zajmujący się wprowadzaniem danych musi ręcznie zaktualizować stan uzgadniania faktury, aby widzieć wyniki weryfikacji uzgadniania faktury.  
4. Ustaw **Uzgadnianie sum faktur**
5. Zaznacz lub wyczyść pole wyboru **Dopasuj sumy faktur**, aby uzgadniać rzeczywiste sumy faktur z oczekiwanymi sumami.
    * Określ, czy ikona jest wyświetlana, gdy rozbieżność dla uzgadniania faktur przekracza limity tolerancji. Można ustawić wyświetlanie ikony, gdy dodatnia rozbieżność przekracza limity tolerancji lub gdy dodatnia lub ujemna rozbieżność przekracza limity tolerancji.  
    * Przykładowo, tolerancja wynosi 5 procent, a łączna kwota faktury dla zamówienia zakupu to 100. W takim wypadku ikona uzgadniania cen zostanie wyświetlona, jeśli łączna kwota faktury na fakturze przekroczy 105,00. Wybranie opcji  **Jeśli większe lub mniejsze niż dopuszczalna rozbieżność** sprawi, że odpowiednia ikona zostanie również wyświetlona w przypadku kwoty faktury mniejszej niż 95,00.  
6. W polu **Procent tolerancji sum faktury** wprowadź akceptowalne odchylenie procentowe. Ta wartość jest wartością domyślną dla firmy. Wartość ta może zostać zastąpiona przez określonych dostawców przy użyciu strony **Tolerancje sum faktury**. Aby uzyskać informacje dotyczące sposobu zastąpienia wartości procentowej tolerancji sum faktury dla określonego dostawcy, zapoznaj się z sekcją „Konfigurowanie tolerancji uzgodnienia sum faktur dla dostawców” w dalszej części tego tematu.
7. Ustaw **Uzgadnianie cen i ilości**.
8. W polu **Zasady uzgadniania wierszy** wybierz wartość, która będzie używana jako domyślna zasada dla firmy, z którą pracujesz. Opcja **Niewymagane** oznacza, że nie będzie wymagana żadna weryfikacja zgodności cen poszczególnych wierszy faktury z cenami w zamówieniu zakupu ani ilości na fakturze z ilościami w dokumencie dostawy. Opcja **Uzgadnianie dwuelementowe** oznacza, że jest wymagana weryfikacja wierszy faktury, ale obejmuje tylko dokumenty zamówień zakupu i faktur od dostawcy. Dokument przyjęcia produktów nie jest brany pod uwagę przy sprawdzaniu poprawności uzgadniania. **Uzgadnianie trzyelementowe** oznacza, że cena jednostkowa netto na fakturze zostanie porównana ceną jednostkową netto w zamówienia zakupu, a ilość na dokumencie przyjęcia produktów zostanie porównana z ilością na fakturze.
9. Aby zezwolić na stosowanie różnych poziomów uzgadniania do towaru, dostawcy, kombinacji dostawców i towarów lub wierszy zamówienia zakupu, należy wybrać wartość w polu **Zezwalaj na zastępowanie zasad uzgadniania**. Zasadę uzgadniania wierszy obowiązującą w firmie można zastąpić dla określonego dostawcy, towaru lub kombinacji dostawcy i towaru na stronie **Zasady uzgadniania**.
    * Jeśli używasz zasady dwuelementowego lub trzyelementowego uzgadniania wierszy, na stronie **Rozbieżności cenowych towarów** można skonfigurować wartości procentowe rozbieżności cen dla firmy, towarów i dostawców. Domyślna tolerancja ceny firmy zostanie ustawiona na wartość zero procent dla dwu i trzyelementowego uzgadniania. Gdy faktury dostawców są porównywane z informacjami w zamówieniach zakupu, odpowiednia dozwolona wartość procentowa rozbieżności cen jest wyszukiwana.   
10. Aby uzgadniać całkowite ceny dla towarów w wierszach na fakturach, należy wybrać wartość w polu **Dopasuj ceny całkowite**. Ten typ uzgadniania przydaje się, gdy dostawca wysyła wielu faktur dla tego samego wiersza zamówienia zakupu. Istnieje możliwość porównania informacji o cenie netto każdego wiersza na fakturze oraz wszystkich oczekujących i wcześniej zaksięgowanych wierszy faktury z kwotą netto w odpowiednim wierszu zamówienia zakupu.  Dostępne opcje to **Brak**,**Procent**,**Kwota** lub **Wartość procentowa i kwota**.
11. W polu **Procent tolerancji całkowitej ceny zakupu** wprowadź wartość procentową odchylenia, która zostanie zaakceptowane. To pole jest dostępne wtedy, gdy w polu **Dopasuj ceny całkowite** wybrano opcję **Procent** lub **Procent i kwota**.
12. W polu **Tolerancja sumy ceny zakupu** wprowadź kwotę w walucie rozliczeniowej. To pole jest dostępne wtedy, gdy w polu **Dopasuj ceny całkowite** wybrano opcję **Kwota** lub **Procent i kwota**.
13. W polu **Wyświetl ikonę dopasowania ceny całkowitej** określ, czy ikona jest wyświetlana, gdy rozbieżność dla uzgadniania faktur przekracza limity tolerancji. Ikona może być wyświetlana, gdy dodatnia rozbieżność przekracza limity tolerancji lub gdy dodatnia lub ujemna rozbieżność przekracza limity tolerancji.
Przykładowo, tolerancja wynosi 5 procent, a cena całkowita dla wiersza zamówienia zakupu to 10,00. W takim wypadku ikona uzgadniania cen zostanie wyświetlona, jeśli cena całkowita dla wiersza na fakturze przekracza 10,50. Wybranie opcji  **Jeśli większe lub mniejsze niż dopuszczalna rozbieżność** sprawi, że odpowiednia ikona zostanie również wyświetlona w przypadku kwoty wiersza faktury mniejszej niż 9,50.
13. Ustaw **Uzgadnianie opłat**.
14. Aby uzgadniać rzeczywiste opłaty z opłatami oczekiwanymi zgodnie z informacjami zawartymi w zamówieniu zakupu, zaznacz pole wyboru **Dopasuj opłaty**.

## <a name="set-up-unit-price-tolerance-percentages"></a>Konfigurowanie dozwolonych wartości procentowych tolerancji ceny jednostkowej
Przejdź do **Ustawienia rozrachunków z dostawcami > Ustawianie > Ustawienia uzgadniania faktur > Rozbieżności cenowe** w celu zdefiniowania dozwolonych wartości procentowych tolerancji cen. Jeśli używasz zasady dwuelementowego lub trzyelementowego uzgadniania wierszy, na stronie rozbieżności cenowych towarów można skonfigurować wartości procentowe rozbieżności cen dla firmy, towarów i dostawców. Gdy faktury dostawców są porównywane z informacjami w zamówieniach zakupu, odpowiednia dozwolona wartość procentowa rozbieżności cen jest wyszukiwana. Poniżej podano domyślną kolejność wyszukiwania:
* Tabela/tabela
* Tabela/Grupa
* Tabela/Wszystkie
* Grupa/Tabela
* Grupa/Grupa
* Grupy/Wszystkie
* Wszystkie/Tabela
* Wszystkie/Grupa
* Wszystkie/Wszystkie

Domyślna rozbieżność cen w firmie ma wartość 0 procent i jest stosowana do wszystkich towarów i wszystkich kont (Wszystkie, Wszystkie). Nie można usunąć rekordu dla domyślnej rozbieżności cen w firmie.

Domyślnie w systemie są dozwolone ujemne wartości rozbieżności cen. Jednakże nie można wprowadzić liczby ujemnej jako wartości procentowej dla rozbieżności cen. Aby śledzić wartości procentowe tolerancji cen, należy wybrać opcję **Jeśli większe lub mniejsze niż dopuszczalna rozbieżność** w polu **Wyświetl ikonę uzgadniania opłat** na stronie  **Parametry modułu rozrachunków z dostawcami**. Następnie wprowadź wartości procentowe rozbieżności cen na stronie **Rozbieżności cenowe**.

## <a name="set-up-matching-policy-override"></a>Skonfiguruj na zastępowanie zasad uzgadniania

Przejdź do **Ustawień rozrachunków z dostawcami >Ustawienia > Ustawienia uzgadniania faktur > Zasady uzgadniania**, aby zdefiniować domyślny wpis dla pól **zasad uzgadniania** dla wierszy na stronie **zamówienia zakupu**. To jest opcjonalna konfiguracja. Użyj tej strony, aby skonfigurować dopasowanie dwukierunkowe lub trzykierunkowe dla towarów, dostawców lub kombinacji pozycji i dostawców. Te wpisy umożliwiają zdefiniowanie bardziej szczegółowych zasad niż zasady uzgadniania firmy zdefiniowane na stronie parametry **Rozrachunki z dostawcami**. Domyślne zasady dopasowywania wierszy firmy są stosowane do wszystkich towarów i dostawców, z wyjątkiem tych, dla których na tej stronie określono różne zasady dotyczące zgodności wierszy.

Na tej stronie wybierz **Poziom zasad dopasowywania**. Wybierz poziom w dopasowanej hierarchii zasad, aby ustawić zasady uzgadniania wierszy.

- **Pozycja i dostawca** — określa zasady dotyczące zgodności dla określonych towarów, które zostały zakupione od określonych dostawców.
- **Towar** — służy do określania zasad uzgodnienia dla określonych towarów nabywanych od dowolnego dostawcy, z wyjątkiem tych określonych na poziomie towaru i dostawcy.
- **Dostawca** — służy do określania zasad uzgodnienia dla określonych towarów nabywanych od danego dostawcy, z wyjątkiem tych określonych na poziomie towaru i dostawcy.
  
Następująca hierarchia jest używana do określenia stosowanej zasady dopasowywania:
  *  Pozycja i dostawca
  *  Element
  *  Dostawca
  *  Firma
  
## <a name="set-up-invoice-totals-matching-tolerance-for-vendors"></a>Skonfiguruj dozwolonych rozbieżności uzgadniania sum faktur dla dostawców

Przejdź do **Ustawienia rozrachunków z dostawcami >Ustawienia > Ustawienia uzgadniania faktur >Tolerancje sum faktur** są przeznaczone do określania tolerancji specyficznych dla dostawcy dla uzgadniania sum faktur. W obliczeniu dopasowywania jest używana wartość procentowa tolerancji sumy faktury z konta dostawcy określonego jako konto zamówienia na fakturze od dostawcy. Jeśli dla konta dostawcy nie określono procentu tolerancji dla sum faktury, używana jest wartość procentowa tolerancji sumy faktury określona dla firmy na stronie **Parametry rozrachunków z dostawcami**.

1. Aby określić tolerancje dla poszczególnych dostawców, które zastępują domyślną tolerancję, wybierz **Konto dostawcy**.
2. Wprowadź procent odchylenia, który akceptujesz dla tego dostawcy.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
