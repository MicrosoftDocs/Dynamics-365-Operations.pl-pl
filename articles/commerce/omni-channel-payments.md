---
# required metadata
title: Omówienie płatności wielokanałowych
description: W tym temacie są omówione płatności wielokanałowe w programie Dynamics 365 Commerce.
author: BrianShook
ms.date: 09/17/2020
ms.topic: overview
ms.prod: null
ms.technology: null
audience: Application user
ms.reviewer: josaw
ms.custom:
  - '141393'
  - intro-internal
ms.assetid: null
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: '2019-01-01'
ms.dyn365.ops.version: AX 8.1.3
---

# <a name="omni-channel-payments-overview"></a>Omówienie płatności wielokanałowych

[!include [banner](../includes/banner.md)]

W tym temacie są omówione płatności wielokanałowe w programie Dynamics 365 Commerce. Zawiera pełną listę obsługiwanych scenariuszy, informacje o funkcjonalności, konfiguracji i rozwiązywaniu problemów oraz opisy typowych problemów.

## <a name="key-terms"></a>Kluczowe terminy

| Okres | Opis |
|---|---|
| Token  | Ciąg danych określany przez procesora płatności jako odwołanie. Tokeny mogą reprezentować numery kart płatniczych, autoryzacje płatności i wcześniejsze przechwycenia płatności. Tokeny są ważne, ponieważ ułatwiają odizolowanie poufnych danych od systemu punktu sprzedaży (POS). Czasami są one również nazywane *odwołaniami*. |
| Token karty | Token dostarczany przez procesora płatności do przechowywania w systemie POS. Token karty może być używany tylko przez akceptanta, który go otrzymał. Tokeny karty czasami są również nazywane *odwołaniami karty*. |
| Token autoryzacji (auth) | Unikatowy identyfikator, który stanowi część odpowiedzi wysyłanej w procesie płatności do systemu punktu sprzedaży po złożeniu żądania autoryzacji przez system punktu sprzedaży. Tokenu autoryzacji można użyć później, jeśli procesor jest wywoływany w celu wykonania akcji, takich jak wycofanie lub unieważnienie autoryzacji. Jest on jednak najczęściej używany do przechwytywania środków finansowych po zrealizowaniu zamówienia lub sfinalizowaniu transakcji. Tokeny autoryzacji czasami są również nazywane *odwołaniami autoryzacji*. |
| Przechwyć token | Odwołanie, które procesor płatności dostarcza do systemu punktu sprzedaży, gdy płatność zostanie sfinalizowana lub przechwycona. Tokenu przechwytywania można następnie użyć jako odwołania przechwytywania płatności w kolejnych operacjach, takich jak żądania zwrotu. | 
| Bez karty | Termin odnoszący się do transakcji płatności, w przypadku których nie jest prezentowana karta fizyczna. Takie transakcje mogą być na przykład realizowane w scenariuszach handlu elektronicznego lub biura obsługi. W przypadku tych transakcji informacje związane z płatnością są wprowadzane ręcznie w witrynie handlu elektronicznego, w przepływie obsługi lub w terminalu punktu sprzedaży albo płatności. |
| Z kartą | Termin odnoszący się do transakcji płatności, w przypadku których karta fizyczna jest prezentowana i wkładana do terminalu płatności podłączonego do systemu punktu sprzedaży Microsoft Dynamics 365. |

## <a name="overview"></a>Przegląd

Generalnie termin *płatności wielokanałowe* opisuje możliwość tworzenia zamówienia w jednym kanale i realizacji go w innym kanale. Kluczem do obsługi płatności wielokonałowych jest zachowanie szczegółów płatności wraz z pozostałymi szczegółami zamówienia, a następnie użycie tych szczegółów dotyczących płatności, gdy zamówienie jest przywoływane lub przetwarzane w innym kanale. Klasycznym przykładem jest scenariusz „Kup w trybie online, odbierz w sklepie”. W tym scenariuszu szczegóły dotyczące płatności są dodawane po utworzeniu zamówienia w trybie online. Następnie są one odczytywane w punkcie sprzedaży, aby obciążyć kartę płatności odbiorcy w momencie odbioru. 

Wszystkie scenariusze opisane w tym temacie można zaimplementować przy użyciu standardowego zestawu SDK Płatności dostarczanego z modułem Commerce. [Łącznik płatności usługi Dynamics 365 dla Adyen](/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3) stanowi gotową do użycia implementacją wszystkich opisanych w tym temacie scenariuszy. 

### <a name="prerequisites"></a>Wymagania wstępne

Każdy scenariusz opisany w tym temacie wymaga łącznika płatności, który obsługuje płatności wielokanałowe. Można również użyć gotowego łącznika Adyen, ponieważ obsługuje on scenariusze udostępniane za pośrednictwem zestawu SDK Płatności. Aby uzyskać więcej informacji na temat implementowania łączników płatności oraz ogólnie o zestawie SDK modułu Retail, odwiedź [stronę główną Podstawowe funkcje handlowe](/dynamics365/unified-operations/retail/dev-itpro/dev-retail-home-page#payment-connectors).

#### <a name="supported-versions"></a>Obsługiwane wersje

Funkcje płatności wielokanałowych opisane w tym temacie zostały wydane jako część programu Microsoft Dynamics 365 for Retail w wersji 8.1.3. 

#### <a name="card-present-and-card-not-present-connectors"></a>Łączniki „Z kartą” i „Bez karty”

Zestaw SDK Płatności jest oparty na dwóch zestawach interfejsów programowania aplikacji (API) dla płatności. Pierwszy zestaw interfejsów API nosi nazwę **iPaymentProcessor**. Jest on używany do implementowania łączników płatności „bez karty”, które mogą być używane w biurach obsługi i na platformie handlu elektronicznego Microsoft Dynamics. Aby uzyskać więcej informacji o interfejsie **iPaymentProcessor**, przeczytaj oficjalny dokument [Implementowanie łącznika płatności i urządzenia płatniczego](https://download.microsoft.com/download/e/2/7/e2735c65-1e66-4b8d-8a3c-e6ef3a319137/The%20Guide%20to%20Implementing%20Payment%20Connector%20and%20Payment%20Device_update.pdf), w którym są omówione płatności. 

Drugi zestaw interfejsów API nosi nazwę **iNamedRequestHandler**. Obsługuje on implementację integracji płatności typu „z kartą”, które korzystają z terminalu płatności. Aby uzyskać więcej informacji o interfejsie **iNamedRequestHandler**, zobacz temat [Tworzenie integracji płatności dla terminala płatniczego](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension). 

### <a name="setup-and-configuration"></a>Instalacja i konfiguracja

Wymagane są następujące składniki i kroki konfiguracji:

- **Integracja eCommerce:** integracja z modułem Commerce jest wymagana do obsługi scenariuszy, w których zamówienie pochodzi z witryny handlowej online. Aby uzyskać więcej informacji na temat zestawu SDK handlu elektronicznego modułu Retail, zobacz temat [Zestaw SDK platformy handlu elektronicznego](/dynamics365/unified-operations/retail/dev-itpro/ecommerce-platform-sdk). W środowisku demonstracyjnym referencyjna witryna handlowa obsługuje scenariusze płatności wielokanałowych. 
- **Konfiguracja płatności online:** konfiguracja kanału online musi zawierać łącznik płatności, który został zaktualizowany w celu obsługi płatności wielokanałowych. Alternatywnie można użyć gotowego łącznika płatności. Aby uzyskać informacje o konfigurowaniu łącznika płatności Adyen dla sklepów internetowych, zobacz temat [Łącznik płatności Adyen](/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3#e-commerce). Oprócz kroków konfiguracji handlu elektronicznego, które opisano w tym temacie, w ustawieniach łącznika Adyen wartość parametru **Zezwalaj na zapisywanie informacji o płatności w handlu elektronicznym** musi zostać zmieniona na **true**. 
- **Konfiguracja płatności wielokanałowych:** na zapleczu przejdź do opcji **Sprzedaż detaliczna i komercyjna \> Ustawienia Headquarters \> Parametry \> Wspólne parametry sieci sprzedaży komercyjnej**. Następnie na karcie **Płatności wielokanałowe** zmień ustawienie opcji **Użyj płatności wielokanałowych** na **Tak**. W Commerce w wersji 10.0.12 lub nowszej to ustawienie znajduje się w obszarze roboczym **Zarządzanie funkcjami**. Wybierz funkcję **Płatności wielokanałowe** i kliknij przycisk **Włącz teraz**. 
- **Usługi płatności:** biuro obsługi używa domyślnego łącznika płatności na stronie **Usługi płatności**, aby przetwarzać płatności. Aby obsługiwać scenariusze takie jak „Kup w biurze obsługi, odbierz w sklepie”, tym domyślnym łącznikiem płatności musi być łącznik płatności Adyen lub łącznik płatności spełniający wymagania dotyczące implementacji płatności wielokanałowych.
- **Usługa EFT:** płatności za pomocą terminalu płatności muszą być skonfigurowane na skróconej karcie **Usługi EFT** profilu sprzętu. Łącznik Adyen obsługuje gotowe do użytku scenariusze płatności wielokanałowych. Możliwe jest również użycie innych łączników płatności obsługujących interfejs **iNamedRequestHandler**, jeśli obsługują płatności wielokanałowe.
- **Dostępność łącznika płatności**: w momencie odczytywania zamówienia wiersze środka płatniczego odczytywane razem z zamówieniem zawierają nazwę łącznika płatności, który został użyty do utworzenia autoryzacji skojarzonych z tym zamówieniem. Po zrealizowaniu zamówienia zestaw SDK Płatności próbuje użyć tego samego łącznika, który został użyty do utworzenia oryginalnej autoryzacji. Dlatego łącznik płatności o tej samej właściwości akceptanta musi być dostępny do przechwycenia. 
- **Typy kart:** aby scenariusze wielokanałowe działały prawidłowo, każdy kanał musi mieć takie same ustawienia dotyczące typów metod płatności, które mogą być używane wielokanałowo. Ta konfiguracja obejmuje identyfikatory metod płatności i identyfikatory typów kart. Jeśli na przykład dla typu metody płatności **Karty** w ustawieniach sklepu internetowego jest przypisany identyfikator **2**, powinien on mieć ten sam identyfikator w ustawieniach sklepu detalicznego. Ten sam wymóg dotyczy identyfikatorów typu karty. Jeśli w sklepie internetowym karcie **VISA** przypisano numer karty **12**, ten sam identyfikator musi być skonfigurowany w sklepie detalicznym. 
- Retail Modern POS dla Windows lub Android z wbudowaną stacją sprzętową   -lub-
- Nowoczesny POS na iOS lub Cloud POS z podłączoną wspólną stacją sprzętową. 

### <a name="basic-principle-supporting-omni-channel-payments"></a>Podstawowa zasada obsługi płatności wielokanałowych

Łączniki płatności i procesory płatności używają tokenów lub odwołań, aby odwoływać się do interakcji związanych z płatnościami kartą. Na przykład w przypadku żądania autoryzacji płatności dostarczane jest odwołanie tej autoryzacji. To odwołanie autoryzacji może zostać użyte później, gdy środki są przechwytywane w czasie realizacji. Autoryzacja ta jest unikatowa dla akceptanta, łącznika płatności i procesora. 

Jeśli zamówienie, które zostało utworzone w trybie online, jest odbierane w sklepie, należy odczytać te same szczegóły płatności tego zamówienia i ich użyć. Jeśli oryginalne szczegóły są dostarczane jako część żądania przechwycenia płatności na podstawie oryginalnej autoryzacji, procesor płatności będzie mógł obsłużyć żądanie i przechwycić płatność. 

Aby odwołanie zamówienia online było poprawne, musi być dostępny łącznik płatności „bez karty”, który obsługuje ten sam procesor. W ten sposób system punktu sprzedaży może mieć jeden procesor dla płatności „z kartą”, ale może również mieć dostęp do innych łączników płatności, dzięki czemu może realizować zamówienia utworzone w innych kanałach za pomocą różnych procesorów płatności. 

## <a name="supported-scenarios"></a>Obsługiwane scenariusze

Obsługiwane są następujące scenariusze płatności wielokanałowych:

- Kup w trybie online, odbierz w sklepie
- Kup w biurze obsługi, odbierz w sklepie
- Kup w sklepie A, odbierz w sklepie B
- Kup w sklepie A, wyślij na adres odbiorcy

    > [!NOTE]
    > Płatności dokonywane w biurach rozmów telefonicznych, które są mapowane na „normalną” funkcję płatności, muszą zostać oznaczone jako **Przedpłata** = **Tak**, aby zostały odzwierciedlone w kwocie należnej podczas odwoływania zamówienia w punkcie sprzedaży. Płatności bez przedpłaty typu „Normalne” nie są rozpoznawane w momencie wycofania zamówienia w punkcie sprzedaży. 

Są także obsługiwane odmiany tych scenariuszy. Na przykład zamówienie online może zawierać zarówno wiersze, które zostaną wysłane do odbiorcy, jak i wiersze, które zostaną odebrane w sklepie. Wszystkie opcje realizacji zamówień są obsługiwane przez płatności wielokanałowe. 

W poniższych sekcjach opisano kroki poszczególnych scenariuszy i przedstawiono sposób uruchamiania tych scenariuszy przy użyciu danych demonstracyjnych. 

### <a name="buy-online-pick-up-in-store"></a>Kup w trybie online, odbierz w sklepie

Przed rozpoczęciem upewnij się, że są spełnione następujące wymagania wstępne:

- Istnieje referencyjna witryna handlowa, w której jest skonfigurowany łącznik Adyen.
- Wartością opcji **Płatności wielokanałowe** na stronie **Wspólne parametry sieci sprzedaży komercyjnej** jest **True**. W nowszych wersjach ten settng jest przenoszony do obszaru roboczego **Zarządzanie funkcjami**, gdzie można wybrać funkcję **Płatności wielokanałowej** i kliknąć przycisk **Włącz teraz**. 
- Łącznik płatności Adyen został skonfigurowany dla rejestru punktu sprzedaży Houston.
- Retail Modern POS dla Windows lub Android z wbudowaną stacją sprzętową   -lub-
- Nowoczesny POS na iOS lub Cloud POS z podłączoną wspólną stacją sprzętową. 

Wykonaj scenariusz, postępując w następujący sposób:

1. W referencyjnej witrynie handlowej utwórz zamówienie do odbioru w sklepie. Pamiętaj, aby wybrać sklep **Houston**. 
2. Przejdź przez etapy realizacji transakcji i zapłać, podając numer testowej karty kredytowej. Numery testowych kart kredytowych są podane na stronie [Numery testowych kart Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description).
3. W module Commerce użyj zadania wsadowego **Synchronizuj zamówienia** oraz harmonogramu dystrybucji **P-001**, aby utworzyć zamówienia na zapleczu.
4. W punkcie sprzedaży, na stronie powitalnej, wybierz operację **Zamówienia do odbioru**, aby wyświetlić zamówienia do odbioru w sklepie. 
5. Wybierz jeden lub więcej wierszy z zamówienia utworzonego w referencyjnej witrynie handlowej, a następnie wybierz opcję **Odbiór.**

    Zamówienie zostanie pobrane z zaplecza. 

6. Jeśli szczegóły wiersza zamówienia są odczytywane z zaplecza i zostanie wykryta płatność kartą, która może być użyta w płatności wielokanałowej, zostanie wyświetlona informacja o dostępności metody płatności.
7. Wybierz opcję **Użyj dostępnej metody płatności**, aby dokończyć transakcję, korzystając z szczegółów karty wprowadzonych w referencyjnej witrynie handlowej.

    Wiersze zamówienia są ładowane na stronie transakcji, a saldo należne wynosi 0 (zero). 

8. Wybierz kartę **Płatności**, aby wyświetlić wiersz metody płatności, który pochodzi z zamówienia online. 
9. Wybierz dowolną metodę płatności, aby ukończyć transakcję. 

### <a name="buy-in-call-center-pick-up-in-store"></a>Kup w biurze obsługi, odbierz w sklepie

1. W module Commerce, na stronie **Obsługa klienta** wpisz **Karen Berg** na pasku wyszukiwania, a następnie kliknij przycisk **Wyszukaj**. 
3. Wybierz opcję **Karen Berg** w wynikach wyszukiwania.
4. Po załadowaniu Karen na stronie **Obsługa klienta** wybierz opcję **Nowe zamówienie sprzedaży**.
5. Na stronie nowego zamówienia sprzedaży wybierz opcję **Nagłówek**, aby wyświetlić nagłówek zamówienia. 
6. Na stronie **Nagłówek** zamówienia wybierz oddział **Centralny** i magazyn **Houston**.
7. Na karcie **Dostawa** zmień wartość w polu **Metoda dostawy** na **60**, która oznacza odbiór przez odbiorcę.
8. Wybierz opcję **Wiersze**, a następnie dodaj jeden lub więcej wierszy do zamówienia. 
9. Wybierz opcję **Gotowe**, aby wprowadzić przepływ ukończenia zamówienia.
10. Przewiń w dół do sekcji płatności, naciśnij przycisk pozycję **Dodaj**, a następnie wybierz wiersz, dla którego ustawiono typ metody płatności **Karty**. 
11. Wybierz znak plus (**+**), aby dodać płatność kartą. 
12. Wprowadź numer testowej karty kredytowej odczytany na stronie [Numery testowych kart Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description), a następnie naciśnij przycisk **OK**.

    > [!NOTE]
    > Jeśli marka karty wprowadzonego numeru karty różni się od marki wybranej w momencie inicjowania płatności, płatność też zostanie zaakceptowana. Zostanie ona jednak zaksięgowana na kontach zmapowanych do marki karty wybranej w kroku 10.

12. Ponownie naciśnij przycisk **OK**, aby zamknąć okno dialogowe **Płatności za zamówienie**.
13. Na stronie **Podsumowanie zamówienia sprzedaży** naciśnij przycisk **Prześlij.**
14. W punkcie sprzedaży, na stronie powitalnej, wybierz operację **Zamówienia do odbioru**, aby wyświetlić zamówienia do odbioru w sklepie. 
15. Wybierz jeden lub więcej wierszy z zamówienia utworzonego w referencyjnej witrynie handlowej, a następnie wybierz opcję **Odbiór.**

    Zamówienie zostanie pobrane z zaplecza. 

16. Jeśli szczegóły wiersza zamówienia są odczytywane z zaplecza i zostanie wykryta płatność kartą, która może być użyta w płatności wielokanałowej, zostanie wyświetlona informacja o dostępności metody płatności.
17. Wybierz opcję **Użyj dostępnej metody płatności**, aby dokończyć transakcję, korzystając z szczegółów karty wprowadzonych w referencyjnej witrynie handlowej.

    Wiersze zamówienia są ładowane na stronie transakcji, a saldo należne wynosi 0 (zero).

18. Wybierz kartę **Płatności**, aby wyświetlić wiersz metody płatności, który pochodzi z zamówienia online. 
19. Wybierz dowolną metodę płatności, aby ukończyć transakcję. 

### <a name="buy-in-store-a-pick-up-in-store-b"></a>Kup w sklepie A, odbierz w sklepie B

1. Uruchom punkt sprzedaży sklepu Houston.
2. Na stronie **Transakcja** dodaj Karen Berg do transakcji, wprowadzając wartość **2001** za pomocą klawiatury numerycznej.
3. Dodaj jeden lub więcej wierszy do transakcji.
4. Naciśnij przycisk **Zamówienia**, aby wyświetlić opcje zamówienia.
5. Wybierz opcję **Pobierz wszystko**, a następnie, po wyświetleniu monitu, wybierz opcję **Zamówienieodbiorcy**.
6. Na pasku wyszukiwania wpisz **Seattle**, a następnie wybierz sklep **Seattle** jako miejsce odbioru. 
7. Kliknij przycisk **OK**, aby zaakceptować bieżącą datę jako datę odbioru.
9. Wybierz opcję **Płatność kartą**, aby zainicjować płatność.
10. Dokonaj płatności kartą na kwotę należną za depozyt. 
11. Dokonaj płatności depozytu na terminalu płatności. 
12. Po zapłaceniu depozytu wybierz opcję, aby użyć tej samej karty do realizacji i poczekaj, aż zamówienie zostanie zrealizowane. 
13. Uruchom punkt sprzedaży sklepu Seattle.
14. W punkcie sprzedaży, na stronie powitalnej, wybierz operację **Zamówienia do odbioru**, aby wyświetlić zamówienia do odbioru w sklepie. 
15. Wybierz jeden lub więcej wierszy z zamówienia utworzonego w referencyjnej witrynie handlowej, a następnie wybierz opcję **Odbiór.**

    Zamówienie zostanie pobrane z zaplecza. 

16. Jeśli szczegóły wiersza zamówienia są odczytywane z zaplecza i zostanie wykryta płatność kartą, która może być użyta w płatności wielokanałowej, zostanie wyświetlona informacja o dostępności metody płatności.
17. Wybierz opcję **Użyj dostępnej metody płatności**, aby dokończyć transakcję, korzystając z szczegółów karty wprowadzonych w referencyjnej witrynie handlowej.

    Wiersze zamówienia są ładowane na stronie transakcji, a saldo należne wynosi 0 (zero).

18. Wybierz kartę **Płatności**, aby wyświetlić wiersz metody płatności, który pochodzi z zamówienia online. 
19. Wybierz dowolną metodę płatności, aby ukończyć transakcję. 

### <a name="buy-in-store-a-ship-to-customer"></a>Kup w sklepie A, wyślij na adres odbiorcy

1. Uruchom punkt sprzedaży sklepu Houston.
2. Na stronie **Transakcja** dodaj Karen Berg do transakcji, wprowadzając wartość **2001** za pomocą klawiatury numerycznej.
3. Dodaj jeden lub więcej wierszy do transakcji.
4. Naciśnij przycisk **Zamówienia**, aby wyświetlić opcje zamówienia.
5. Wybierz opcję **Wyślij wszystko**, a następnie, po wyświetleniu monitu, wybierz opcję **Zamówienie odbiorcy**.
6. Na stronie Metoda wysyłki wybierz opcję **Standardowa noc**, a następnie kliknij przycisk **OK**, aby zaakceptować datę dzisiejszą jako datę wysyłki. 
7. Kliknij przycisk **OK**, aby zaakceptować bieżącą datę jako datę odbioru.
8. Wybierz opcję **Płatność kartą**, aby zainicjować płatność.
9. Dokonaj płatności kartą na kwotę należną za depozyt. 
10. Dokonaj płatności depozytu na terminalu płatności. 
11. Po zapłaceniu depozytu wybierz opcję, aby użyć tej samej karty do realizacji i poczekaj, aż zamówienie zostanie zrealizowane.

Po pobraniu, spakowaniu i zafakturowaniu zamówienia w zapleczu szczegóły płatności podane w punkcie sprzedaży zostaną użyte do przechwycenia środków za towary wysyłane do odbiorcy. 

## <a name="scenario-details"></a>Szczegóły scenariusza

Oprócz opisanych podstawowych scenariuszy, w zestawie SDK Płatności wprowadzono kilka ulepszeń, które umożliwiają obsługę płatności wielokanałowych. 

### <a name="pos"></a>Punkt sprzedaży

#### <a name="single-swipedip-for-customer-orders"></a>Pojedyncze przeciągnięcie dla zamówień odbiorcy

Zanim została zaimplementowana funkcja płatności wielokanałowych po utworzeniu w punkcie sprzedaży zamówień odbiorcy zawierających depozyt odbiorcy musieli przeciągać kartę dwa razy: jeden raz, aby wpłacić depozyt, i jeden raz, aby autoryzować kartę podczas późniejszej realizacji zamówienia. Gdy jest włączona funkcja autoryzacji wielokanałowej, odbiorcy muszą przeciągnąć kartę tylko jeden raz, aby wpłacić depozyt i autoryzować kwotę należną za towary, które zostaną zrealizowane później. W momencie realizacji są przechwytywane autoryzowane środki. Przed zaimplementowaniem funkcji autoryzacji wielokanałowej był tworzony tylko cykliczny token karty do późniejszej realizacji zamówienia. W związku z tym środki za niezrealizowane zamówienie nie były autoryzowane i ponieważ nie były zablokowane w tym określonym celu ich późniejsze przechwycenie było mniej prawdopodobne.

> [!NOTE]
> Pojedyncze przeciągnięcie nie jest obsługiwane w module Retail w wersji 8.1.3. Przepływ zamówień odbiorcy w wersji 8.1.3 jest taki sam, jak przed zaimplementowaniem funkcji autoryzacji wielokanałowej. 

### <a name="cards-that-cant-issue-recurring-card-tokens"></a>Karty, które nie mogą wystawiać cyklicznych tokenów karty

Niektórych kart nie można używać do płatności wielokanałowych, ponieważ nie obsługują wystawiania cyklicznych tokenów karty. Jeśli w momencie tworzenia zamówienia w punkcie sprzedaży depozyt jest wpłacany kartą nieobsługującą cyklicznych tokenów karty, autoryzacja karty odbywa się zgodnie z dawnym przepływem, W związku z tym odbiorca chcący dokonać płatności, która zostanie użyta później po realizacji zamówienia, musi przedstawić drugą kartę. Jeśli druga karta nie obsługuje cyklicznych tokenów karty, autoryzacja zostanie odrzucona i zostanie wyświetlony komunikat, aby kasjer poprosił o inną kartę. 

### <a name="using-a-different-card"></a>Użycie innej karty

Odbiorca przychodzący do sklepu po odbiór zamówienia ma możliwość użycia innej karty. Jeśli kasjer zobaczy komunikat **Użyj dostępnej metody płatności** w momencie odbierania zamówienia, kasjer/kasjerka może zapytać, czy odbiorca chce skorzystać z tej samej karty. Jeśli odbiorca stracił kartę, która została użyta do utworzenia zamówienia i chce zapłacić za zamówienie inną kartą, kasjer może wybrać opcję **Użyj innej metody płatności**. Jeśli później odbiorca przychodzi ponownie, aby odebrać inne artykuły z tego samego zamówienia i pierwotna autoryzacja karty jest nadal ważna, kasjer może ponownie zapytać, czy odbiorca chce użyć tej karty.

### <a name="invalid-authorizations"></a>Nieprawidłowe autoryzacje

Jeśli karta użyta do utworzenia zamówienia nie jest już ważna w momencie wybierania produktów do odbioru, żądanie przechwycenia płatności nie powiedzie się. Łącznik płatności punktu sprzedaży podejmie następnie próbę utworzenia nowej autoryzacji i przechwycenia przy użyciu tych samych danych karty. Jeśli nowa autoryzacja lub przechwycenie nie powiedzie się, kasjer zostanie poinformowany, że nie można przetworzyć płatności. Kasjer musi wówczas otrzymać nową płatność od odbiorcy. 

### <a name="multiple-available-payments"></a>Wiele dostępnych płatności

W przypadku odbierania zamówienia z więcej niż jedną metodą płatności i więcej niż jednym wierszem kasjerowi jest najpierw wyświetlany komunikat **Użyj dostępnej metody płatności**. Jeśli istnieje więcej niż jedna karta, po wybraniu przez kasjera opcji **Użyj dostępnej metody płatności**, istniejące wiersze metody płatności są przechwytywane do momentu spłacenia salda za towary, które są odbierane. Kasjer nie będzie mógł wybrać karty, która ma zostać użyta do płatności za odbierane towary. 

## <a name="related-topics"></a>Powiązane tematy

- [Płatności — często zadawane pytania](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)
- [Łącznik płatności usługi Dynamics 365 dla Adyen](/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3)
- [Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce](./cpe-bopis.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]