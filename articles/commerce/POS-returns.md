---
title: Tworzenie zwrotów w POS
description: W tym artykule opisano sposób inicjowania zwrotów dla transakcji cash-and-carry lub zamówień klientów w aplikacji Point of Sale (POS) Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.20
ms.openlocfilehash: a49e9abd0143d480cc1cafb05be5e995fb3cebdd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857005"
---
# <a name="create-returns-in-pos"></a>Tworzenie zwrotów w POS

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób inicjowania zwrotów dla transakcji cash-and-carry lub zamówień klientów w aplikacji Point of Sale (POS) Microsoft Dynamics 365 Commerce.

> [!NOTE]
> W wersji Commerce 10.0.20 i nowszych dostępna jest nowa funkcja, która nazywa się **Doświadczenie w przetwarzaniu zwrotów zunifikowanych w POS**. Funkcja ta zapewnia bardziej spójny i jednolity proces zwrotu w POS, niezależnie od typu transakcji (transakcja cash-and-carry lub zamówienie klienta) lub oryginalnego kanału, w którym zamówienie zostało utworzone. Zalecamy, aby wszystkie organizacje włączyły tę nową funkcję w celu poprawy ogólnej niezawodności przetwarzania zwrotów przez POS.
>
> Po włączeniu tej funkcji nie można jej wyłączyć.

## <a name="process-returns-by-using-the-return-transaction-operation"></a>Przetwarzanie zwrotów za pomocą operacji „transakcja zwrotna”

Zaleca się dodanie operacji zwrotu do układu ekranu [programu POS](pos-screen-layouts.md). W wersjach przed wydaniem Commerce w wersji 10.0.20 operacja transakcji zwrotu poprawnie obsługuje obsługę zwrotów tylko dla transakcji typu cash-and-carry. Po włączeniu funkcji **Ujednolicone przetwarzanie zwrotów dla POS** w wersji Commerce 10.0.20 lub nowszej, operacja transakcji zwrotów obsługuje również przetwarzanie zwrotów, które pochodzą z zamówień klienta, takich jak „odbiór” lub „wysyłka do domu”, które są już zafakturowane.

W operacji transakcji zwrotu użytkownik może wyszukać transakcję gotówkową lub zlecenie klienta do zwrotu, wprowadzając dowolne z czterech poniższych kryteriów wyszukiwania. Użytkownicy mogą wprowadzać te kryteria za pomocą klawiatury urządzenia, klawiatury ekranowej lub skanera kodów kreskowych.

- Identyfikator paragonu
- Numer zamówienia
- Identyfikator referencyjny kanału (znany również jako identyfikator potwierdzenia zamówienia)
- Identyfikator faktury

Jeśli zostanie znaleziona transakcja lub zamówienie spełniające kryteria wyszukiwania, zostanie wyświetlona strona **Produkty zwrotne**. W tym miejscu użytkownicy mogą określać zwracane towary. Mogą również wprowadzać ilości zwrotów i kody przyczyn.

Dla każdej linii zamówienia na liście produktów zwrotnych POS pokazuje informacje o pierwotnej ilości zakupu oraz ilości z wcześniej zrealizowanych zwrotów. Ilość zwrotu wprowadzana przez użytkownika dla wiersza zamówienia nie może być większa niż wartość pola **Dostępne do zwrotu**.

![Strona produktów zwrotnych.](media/returnslist.png)

Podczas przetwarzania zwrotu, jeśli użytkownik posiada produkt fizyczny, a produkt ten posiada kod kreskowy, użytkownik może zeskanować kod kreskowy, aby zarejestrować zwrot. Każdy skan kodu kreskowego zwiększa ilość zwracanych produktów o jedną sztukę. Jeśli jednak na etykiecie z kodem kreskowym znajduje się ilość, zostanie ona wprowadzona w polu **Zwrot teraz**.

Użytkownicy mogą także ręcznie wybrać towary, które mają zostać zwrócone na stronie **Produkty do zwrotu**, a następnie zaktualizować pole **Zwrot teraz**, korzystając z okienka szczegółów po prawej stronie.

Jeśli dla transakcji jest określona maksymalna dostępna ilość **Zwracana teraz**, użytkownik może wybrać operację **Wybierz wszystko** na pasku aplikacji w aplikacji w celu ustawienia maksymalnej zwracanej ilości we wszystkich wierszach.

W przypadku każdego wiersza, w którego ustawieniach jest dostępna ilość **Zwracana teraz**, użytkownik musi wybrać kod przyczyny zwrotu przy użyciu panelu szczegółów. W przypadku zwrotów transakcji gotówkowych i transakcji przenoszenia, kody przyczyn zwrotu są konfigurowane jako kody informacji w profilu funkcji sklepu. W przypadku zwrotów zamówień odbiorcy kody przyczyn zwrotu są konfigurowane na stronie **Kody przyczyn zwrotu** w centrali Dynamics 365 Commerce.

Po skonfigurowaniu ilości zwrotu i kodu przyczyny dla każdej pozycji, która musi zostać zwrócona, użytkownik musi wybrać operację **Zwrot** na pasku aplikacji w celu kontynuowania przetwarzania. Pojawia się strona transakcji POS, na której do koszyka zostały dodane wybrane na poprzedniej stronie artykuły zwrotne. Ilości towarów **zwróconych teraz** są w transakcji wyświetlane jako wiersze ilości ujemnej i jest obliczany łączny zwrot kosztów.

Użytkownicy mogą dodawać wiersze do transakcji zwrotu, jeśli tworzą zamówienie wymiany. Użytkownicy mogą również dodać więcej pozycji zwrotu ad-hoc do transakcji zwrotu, korzystając z operacji **Produkt zwrotu** dla wybranej, dodanej linii sprzedaży o dodatniej ilości.

> [!NOTE]
> Operacja **zwrotu produktu** w programie POS nie sprawdza żadnej weryfikacji względem oryginalnej transakcji i pozwala na zwrot dowolnego produktu. Dlatego w przypadku tej operacji zaleca się, aby tylko autoryzowani użytkownicy mogli wykonywać tę operację lub aby zastępowanie menedżera było wymagane.

Jeśli zwrot jest należny przy realizacji zamówienia, organizacje mogą skonfigurować [zasady płatności zwrotu](refund_policy_returns.md), które ograniczają metody płatności, których można używać w celu zwrotu pieniędzy klientom. Jeśli oryginalna transakcja została zapłacona kartą kredytową, w zależności od mechanizmu przetwarzania płatności i konfiguracji systemu, użytkownicy mogą mieć możliwość [wysłania zwrotu na oryginalną kartę](dev-itpro/linked-refunds.md). W takim przypadku zwrot można przetworzyć bez wymogu ponownego wsunięcia karty kredytowej odbiorcy. Oryginalny token płatności jest używany do wystawienia zwrotu.

## <a name="other-return-options-in-pos"></a>Inne opcje zwrotu w programie POS

Po włączeniu funkcji **przetwarzania zunifikowanych zwrotów w programie POS** użytkownicy mogą również używać operacji **Pokaż dziennik** w programie POS do inicjowania zwrotu dla transakcji typu „gotówka” lub „zamówienie odbiorcy”. Następnie mogą wybrać transakcję w dzienniku i wybrać operację **Zwrot** na pasku aplikacji w aplikacji w programie POS. Ta operacja jest dostępna tylko wtedy, gdy istnieją wiersze zamówienia zwrotu. Inicjuje to samo doświadczenie użytkownika co operacja **transakcji zwrotu**.

Użytkownicy mogą również używać operacji **Wycofaj zamówienie** w programie POS do wyszukiwania i wycofywania zamówień odbiorcy. (Tej operacji nie można używać w przypadku transakcji kasowych i transakcji gotówkowych). W takim przypadku po wybraniu zamówienia odbiorcy można użyć operacji zwrotu na pasku aplikacji POS w celu zainicjowania **zwrotu** dla zamówienia odbiorcy. Ta operacja jest dostępna tylko wtedy, gdy istnieją wiersze zamówienia zwrotu. Inicjuje to samo doświadczenie użytkownika co operacja **zwrotu transakcji** lub **pokazania dziennika**.

## <a name="return-orders-are-posted-to-commerce-headquarters-as-sales-orders"></a>Zamówienia zwrotu są księgowane w centrali Commerce jako zamówienia sprzedaży 

Gdy jest włączona funkcja **przetwarzania zunifikowanych zwrotów w programie POS**, wszystkie zwroty tworzone w programie POS są zapisywane w centrali Commerce jako zamówienia sprzedaży z wierszami ujemnymi. W wersjach przed wydaniem Commerce w wersji 10.0.20 użytkownicy mogą wybrać, czy zamówienia zwrotu mają być księgowane jako zamówienia sprzedaży z ujemnymi liniami, czy też mają to być zamówienia zwrotu tworzone w procesie autoryzacji zwrotu towarów (RMA). 

W ramach funkcji **Ujednolicone przetwarzanie zwrotów w POS** zrezygnowano z opcji korzystania z procesu RMA do tworzenia zwrotów w POS. Po włączeniu tej funkcji wszystkie zwroty będą tworzone jako zlecenia sprzedaży, które mają ujemne linie.

## <a name="offline-return-processing-improvements"></a>Usprawnienia w przetwarzaniu zwrotów w trybie offline

W większości przypadków, gdy zwrot jest przetwarzany w POS, system próbuje nawiązać połączenie w czasie rzeczywistym (RTS) z centralą Commerce w celu sprawdzenia aktualnych ilości dostępnych do zwrotu. Taka weryfikacja pomaga zapobiegać nieuczciwym scenariuszom, w których klient próbuje zwrócić ten sam produkt w wielu miejscach.

Aby poradzić sobie z sytuacjami, w których połączenie RTS nie może zostać wykonane z powodu problemów z siecią lub łącznością, wprowadzono proces okresowej synchronizacji danych dotyczących ilości zwrotów z centrali Commerce do bazy danych kanału w sklepie. Takie śledzenie zwrotów po stronie kanału pomaga zapewnić, że **Dostępne do zwrotu** ilości, które są wyświetlane w POS, są w miarę dokładne, nawet gdy POS jest offline. Gwarantuje również, że punkty sprzedaży mogą w dalszym ciągu sprawdzać poprawność informacji po stronie kanału, co pomaga zapobiegać fałszywym zwrotom.

Aby w odpowiedni sposób wykorzystać proces zwrotu offline, organizacje powinny zaplanować w centrali Commerce zadanie wsadowe **Aktualizacja ilości zwracanych** tak, aby było ono często uruchamiane. Zalecamy, aby to zadanie było uruchamiane z tą samą częstotliwością, co zadanie P, które ściąga nowe transakcje z kanałów Commerce do centrali Commerce.

Zadanie **Uaktualnienie ilości zwrotów** oblicza ilość, która jest dostępna do zwrotu dla wszystkich zamówień sprzedaży, które znajdują się w centrali Commerce. Dane wyliczone przez zadanie muszą być następnie przesłane do baz danych kanałów, aby kanały sklepowe mogły zostać zaktualizowane. W tym celu wykorzystuje się zadanie dystrybucyjne **Ilości do zwrotu** (1200). Ponieważ dane o ilości podlegającej zwrotowi są synchronizowane z centrali Commerce, jeśli zwrot jest przetwarzany w POS, ale nie można wykonać połączenia RTS, POS może wykorzystać informacje o zwrotach po stronie kanału do zatwierdzenia ilości **Dostępnych do zwrotu** dla danego wiersza sprzedaży.

Jeśli nie można wykonać połączenia RTS, a POS używa danych po stronie kanału do zatwierdzania zwrotów, komunikat ostrzegawczy informuje użytkowników, że tworzą zwrot „w trybie offline”. Dlatego są świadomi, że **Ilość dostępna do zwrotu** wyświetlana w POS może być nieaktualna i niedokładna, w zależności od tego, kiedy zadanie **Aktualizacja ilości do zwrotu** zostało ostatnio przetworzone i zsynchronizowane z kanałem.

Na przykład, klient ostatnio dokonał zwrotu dla linii zamówienia w innym kanale, ale dane te nie zostały jeszcze zsynchronizowane z bazami danych kanału poprzez zadanie **Aktualizacja ilości do zwrotu**. Następnie klient udaje się do innego sklepu i ponownie próbuje zwrócić ten sam towar. W tym przypadku, jeśli sklep nie może wykonać połączenia RTS do centrali Commerce, aby uzyskać dane o zwrotach w czasie rzeczywistym, POS pozwoli na ponowny zwrot towaru. Użytkownik jest jednak ostrzegany, że informacje, które są wykorzystywane do zatwierdzenia zwrotu, mogą być nieaktualne. Komunikat, który otrzymuje użytkownik, jest tylko komunikatem ostrzegawczym. Nie przeszkadza to użytkownikowi w dalszym przetwarzaniu zwrotu.

Jeśli informacje po stronie kanału z jakiegoś powodu nie są aktualne, a zwrot offline jest przetwarzany na ilość przekraczającą rzeczywistą **Dostępną do zwrotu** ilość, może zostać wygenerowany błąd podczas księgowania zestawienia w celu utworzenia transakcji w centrali Commerce.

> [!NOTE]
> Gdy jest włączona funkcja **Ujednoliconych zwrotów w POS**, stają się dostępne nowe opcjonalne funkcje służące do weryfikacji serializowanych zwrotów produktów. Aby uzyskać więcej informacji, zobacz temat [Zwrot produktów z kontrolą numeru seryjnego w punkcie sprzedaży](POS-serial-returns.md).

## <a name="version-details"></a>Szczegóły wersji

Poniższa lista zawiera minimalne wymagania dotyczące wersji dla różnych składników.
- Commerce headquarters: wersja 10.0.20
- Commerce Scale Unit (CSU): wersja 9.30
- Punkt sprzedaży (POS): wersja 9.30

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Włącz poprawne obliczanie podatku dla zwrotów z ilością częściową

Ta funkcja zapewnia, że gdy zamówienie zostanie zwrócone przy użyciu wielu faktur, podatki będą ostatecznie równe kwocie podatku pierwotnie naliczonego.

1. Przejdź do obszaru roboczego **Zarządzanie funkcjami** i wyszukaj opcję **Włącz poprawne obliczanie podatku dla zwrotów z ilością częściową**.
1. Zaznacz opcję **Włącz poprawną kalkulację podatku dla zwrotów o ilości częściowej**, a następnie wybierz opcję **Włącz**.

## <a name="set-up-return-locations-for-retail-stores"></a>Ustawianie lokalizacji zwrotów dla sklepów

Commerce umożliwia skonfigurowanie miejsc zwrotu opartych na kodach informacyjnych sprzedaży detalicznej oraz kodach przyczyn sprzedaży i marketingu. Kiedy klienci zwracają zakupy, kasjerzy często podają powód zwrotu. Możesz określić, że zwrócone produkty powinny być przypisane do różnych lokalizacji zwrotów w magazynie, na podstawie kodów informacyjnych i kodów powodów, które kasjerzy wybierają w kasie.

Na przykład, klient zwraca wadliwy produkt, a kasjer przetwarza transakcję zwrotu. Gdy Retail POS pokazuje kod informacyjny dla zwrotów, kasjer wybiera podkod dla wadliwych zwrotów. Zwracany produkt jest wtedy automatycznie przypisywany do określonej lokalizacji zwrotu.

Lokalizacją zwrotu może być magazyn, miejsce w magazynie, a nawet konkretna paleta, w zależności od lokalizacji zapasów, które ma ustawione twoja organizacja. Każdą lokalizację zwrotu możesz przyporządkować do jednego lub kilku kodów informacyjnych sprzedaży detalicznej oraz kodów przyczyn sprzedaży i marketingu.

### <a name="prerequisites"></a>Wymagania wstępne

Zanim będziesz mógł ustawić miejsca powrotu, musisz skonfigurować następujące elementy:

- **Kody informacyjne dla detalu** – podpowiedzi w kasie, które są ustawione w module **Retail**. Aby uzyskać więcej informacji, zobacz [Ustawianie kodów informacyjnych](/dynamicsax-2012/appuser-itpro/setting-up-info-codes).
- **Kody powodów sprzedaży i marketingu** – podpowiedzi w kasie, które są ustawione w module **Sprzedaż i marketing**. Aby uzyskać więcej informacji, zobacz [Ustawianie kodów powodów](/dynamicsax-2012/appuser-itpro/set-up-return-reason-codes).
- **Lokalizacje magazynów** – miejsca przechowywania zapasów. Więcej informacji zawiera temat [Ustawianie lokalizacji zapasów](/dynamicsax-2012/appuser-itpro/about-locations).
    
### <a name="set-up-return-locations"></a>Ustawianie lokalizacji zwrotu

Aby skonfigurować lokalizacje zwrotów, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Magazyny**, a następnie wybierz magazyn.
1. Na Szybkiej karcie **Sprzedaż** w polu **Domyślna lokalizacja zwrotu** wybierz lokalizację magazynową, która ma być używana dla zwrotów, w przypadku których kody informacyjne lub kody przyczyny nie są zmapowane do lokalizacji zwrotu.
1. W polu **Domyślna paleta zwrotna** wybierz paletę, która będzie używana dla zwrotów, w których kody informacyjne lub kody przyczyny nie są przypisane do miejsc zwrotu.
1. Przejdź do **Retail i Commerce \> Zarządzanie zapasami \> Poziomy zapasów**.
1. Naciśnij przycisk **Nowy**, aby stworzyć politykę lokalizacji zwrotu.
1. Wprowadź unikatową nazwę i opis lokalizacji zwrotu.

    > [!NOTE]
    > Jeśli dla miejsc powrotu została ustawiona sekwencja numerów, nazwa zostanie wprowadzona automatycznie.

1. Na szybkiej karcie **Ogólne** ustaw opcję **Drukuj etykiety** na **Tak**, aby drukować etykiety dla wszystkich produktów, które są przypisane do miejsc zwrotu.
1. Ustaw opcję **Blokuj zapasy** na **Tak**, aby umieścić zwracane produkty w domyślnej lokalizacji zwrotu poza zapasami i zapobiec ich sprzedaży.
1. Aby przypisać określone kody i podkody informacji detalicznej do miejsc zwrotu, wykonaj poniższe kroki:

    1. Na skróconej karcie **Kody informacyjne Retail** wybierz pozycję **Dodaj**.
    1. W polu **Kod informacyjny** wybierz kod informacji dla zwrotów.
    1. W polu **Podkod** wybierz podkod przyczyny zwrotu. W polu **Opis** wprowadź opis wybranego podkodu.
    1. W polu **Sklep** wybierz sklep, w którym używany jest dany kod informacji.
    1. Użyj pól **Magazyn**, **Miejsce** i **Identyfikator palety**, aby określić miejsce zwrotu. Na przykład, aby wskazać określoną lokalizację w sklepie, wybierz sklep w polu **Sklep** i lokalizację w polu **Miejsce**.
    1. Zaznacz pole wyboru **Blokada zapasów**, aby wykluczyć zwracane produkty z zapasów i zapobiec ich sprzedaży.

1. Aby przypisać określone kody powodów sprzedaży i marketingu do miejsc powrotu, wykonaj poniższe kroki:

    1. Na skróconej karcie **Kody przyczyn sprzedaży i marketingu** wybierz opcję **Dodaj**.
    1. Następnie w polu **Kod przyczyny** wybierz nowy kod przyczyny zwrotu. W polu **Opis** wprowadź opis wybranego kodu przyczyny.
    1. W polu **Sklep**, wybierz sklep, w którym używany jest kod przyczyny.
    1. Użyj pól **Magazyn**, **Miejsce** i **Identyfikator palety**, aby określić miejsce zwrotu. Na przykład, aby wskazać określoną paletę w lokalizacji w magazynie, wybierz magazyn w polu **Magazyn**, lokalizację w polu **Miejsce** oraz paletę w polu **Identyfikator palety**.
    1. Zaznacz pole wyboru **Blokada zapasów**, aby wykluczyć zwracane produkty z zapasów i zapobiec ich sprzedaży.

    > [!NOTE]
    > Jeśli dla danego przedmiotu użyto zasad lokalizacji zwrotu, ale powód zwrotu, który wybierze kasjer, nie pasuje do żadnego kodu określonego na szybkiej karcie **Kody informacyjne sprzedaży detalicznej** lub **Kody przyczyn sprzedaży i marketingu**, przedmiot jest wysyłany do domyślnej lokalizacji zwrotu zdefiniowanej na stronie **Magazyn**. Dodatkowo ustawienie pola wyboru **Blokuj zapasy** w zakładce **Ogólne** na stronie **Miejsca zwrotu** decyduje o tym, czy zwracany przedmiot powinien zostać zablokowany w zapasach.

1. Wybierz kolejno opcje **Retail i Commerce \> Hierarchia produktów Commerce**.
1. Na skróconej karcie **Właściwości kategorii zapasów**, w polu **Miejsce zwrotu** wybierz miejsce zwrotu. Ponieważ dla tego samego sklepu można zdefiniować wiele zasad lokalizacji zwrotów, wartość, którą tutaj wybierzesz, określa zasady lokalizacji zwrotów, które zostaną zastosowane.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zwrot produktów oznaczonych numerami seryjnymi w POS](POS-serial-returns.md)

[Połączone zwroty poprzednio zatwierdzonych i potwierdzonych transakcji](dev-itpro/linked-refunds.md)

[Tworzenie i aktualizowanie zasad zwrotów i refundacji dla kanału](refund_policy_returns.md)

[Konfiguracje wizualne interfejsu użytkownika punktu sprzedaży](pos-screen-layouts.md)
