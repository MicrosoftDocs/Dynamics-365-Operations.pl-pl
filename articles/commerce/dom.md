---
title: Zarządzanie zamówieniami rozdzielonymi (DOM)
description: W tym artykule opisano funkcję zarządzania zamówieniami rozdzielonymi (DOM) w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
ms.date: 02/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 26817321753c8e39d61957b4ea2004f20daf1b2f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878520"
---
# <a name="distributed-order-management-dom"></a>Zarządzanie zamówieniami rozdzielonymi (DOM)

[!include [banner](includes/banner.md)]

W tym artykule opisano funkcję zarządzania zamówieniami rozdzielonymi (DOM) w rozwiązaniu Microsoft Dynamics 365 Commerce.

Zarządzanie DOM to rozwiązanie optymalizacji realizacji zamówień zakupu obsługi wielokanałowej, które pomaga maksymalizować realizację zamówień w sieci łańcucha dostaw. Zarządzanie DOM pomaga zapewnić, by produkty były dostarczane do klientów w odpowiednich ilościach, z prawidłowych źródeł i o właściwej godzinie. Model DOM pomaga także maksymalizować zyski, minimalizować koszty i spełniać wymagania dotyczące poziomu usług.

Zarządzanie DOM używa programowania mieszanych liczb całkowitych (MIP) i modeli analizy predykcyjnej przed wykonaniem optymalizacji zarówno na poziomie partii, jak i na poziomie poszczególnych zamówień. Te możliwości umożliwiają sprzedawcom detalicznym używanie zdefiniowanych reguł w celu równoważenia wielu powodujących konflikt potrzeb w zakresie realizacji zamówień. W nowoczesnej sieci dostaw, w której realizacja produktów może pochodzić z wielu kanałów, organizacje muszą szybko dostosowywać się do zmian w zamówieniach, problemów z dostępnością dostawców oraz wahań popytu. Zarządzanie DOM pomaga maksymalizować realizację zamówień i znajdować poprawne źródła dostawy produktów na podstawie ograniczeń biznesowych i zamierzeń, takich jak minimalizowanie kosztów przez realizację zamówień z najbliższych źródeł. Zarządzanie DOM wykorzystuje odległość między źródłami realizacji produktów a miejscami docelowymi wysyłki, współczynnikami kosztów zdefiniowanymi jako zamierzenia optymalizacji oraz regułami zdefiniowanymi jako ograniczenia, takimi jak zapasy w węzłach realizacji w celu optymalizowania realizacji zamówień. Zarządzanie DOM umożliwia definiowanie wielu profilów, które pomagają firmom uruchamiać różne strategie optymalizacji w zależności od typu segmentu branży lub konsumenta. 

Poniższa ilustracja przedstawia cykl życia zamówienia sprzedaży w zarządzaniu DOM.

![Cykl życia zamówienia sprzedaży w kontekście systemu DOM.](./media/flow.png "Cykl życia zamówienia sprzedaży w kontekście systemu DOM")

## <a name="set-up-dom"></a>Ustaw format DOM

1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.
2. Na karcie **Klucze konfiguracji** rozwiń węzeł **Commerce**, a następnie wybierz pole wyboru **Zarządzanie zamówieniami rozdzielonymi**.
3. Przejdź do opcji **Retail i Commerce \> Zarządzanie zamówieniami rozdzielonymi \> Ustawienia \> Parametry DOM**.
4. Na karcie **Ogólne** ustaw następujące wartości:

    - **Włącz zarządzanie zamówieniami rozdzielonymi** — ustaw wartość **Tak** dla tej opcji.
    - **Potwierdź użycie Map Bing dla DOM** — ustaw wartość **Tak** dla tej opcji.

        > [!NOTE]
        > Dla tej opcji możesz ustawić wartość **Tak**, tylko jeśli ustawiono wartość **Tak** dla opcji **Włącz Mapy Bing** na karcie **Mapy Bing** strony **Wspólne parametry Commerce** (**Retail i Commerce \> Ustawienia centrali \> Parametry \> Wspólne parametry Commerce**) oraz jeśli wprowadzono prawidłowy klucz w polu **Klucz Map Bing**.
        >
        > [Centrum deweloperów usługi Mapy Bing](https://www.bingmapsportal.com/) umożliwia ograniczenie dla kluczy API Map Bing dostępu do zestawu określonych domen. Dzięki tej funkcji odbiorcy mogą zdefiniować ściśle określony zestaw wartości odwołań lub zakresy adresów IP, na podstawie których będzie sprawdzana poprawność klucza. Zapytania pochodzące z listy dozwolonych będą przetwarzane w zwykły sposób, podczas gdy żądania spoza listy będą zwracać odpowiedź o odmowie dostępu. Zwiększenie bezpieczeństwa domeny klucza interfejsu API jest opcjonalne, a klucze, dla których poziom ten nie zostanie dodatkowo zwiększony, będą nadal działać. Lista dozwolonych klucza działa niezależnie od pozostałych kluczy, dzięki czemu można ustanowić odrębne reguły dla każdego klucza. Zarządzanie zamówieniami rozdzielonymi nie obsługuje konfigurowania właściwości z odwołaniami domen.

    - **Okres przechowywania w dniach** — określ okres przechowywania w systemie planów realizacji generowanych przez sesje DOM. Uruchomienie zadania wsadowego **Ustawienia zadania usuwania danych realizacji DOM** spowoduje usunięcie wszystkich planów realizacji starszych niż liczba dni określona w tym miejscu.
    - **Okres odrzucania (w dniach)** — określ czas, jaki musi upłynąć, aby można było przypisać wiersz odrzuconego zamówienia do tej samej lokalizacji.

5. Na karcie **Zmienna** ustaw następujące wartości:

    - **Maksymalna liczba prób automatycznej realizacji** — określ liczbę prób przekazania wiersza zamówienia do lokalizacji przez aparat DOM. Jeśli w ciągu określonej liczby prób aparat DOM nie jest w stanie przekazać wiersza zamówienia do lokalizacji, wiersz zamówienia zostanie oznaczony jako wyjątek. W przyszłych sesjach ten wiersz będzie pomijany, dopóki stan nie zostanie ręcznie zresetowany.
    - **Promień regionu lokalnego sklepu** — wprowadź wartość. To pole pomaga w określeniu sposobu grupowania lokalizacji i traktowania ich jako równoważne pod względem odległości. Na przykład, jeśli wprowadzisz wartość **100**, wszystkie sklepy lub centra dystrybucji w promieniu 100 mil od adresu realizacji są uważane za równoważne pod względem odległości.
    - **Typ zmiennej** — wybierz wartości. W aplikacji Commerce zwalniane są dwa typy zmiennych: **Zmienna produkcji** i **Zmienna uproszczona**. W przypadku wszystkich maszyn z uruchomioną funkcją DOM (tj. wszystkich serwerów, które są częścią grupy DOMBatch) wybierz typ **Zmienna produkcji**. Zmienna produkcji wymaga specjalnego klucza licencji, który domyślnie jest licencjonowany i wdrażany w środowiskach produkcyjnych. W nowszej warstwie 2+ zmienna produkcji jest już włączona. W przypadku środowisk nieprodukcyjnych wdróż ten klucz licencji ręcznie. Aby ręcznie wdrożyć klucz licencji, wykonaj następujące czynności:

        1. W usłudze Microsoft Dynamics Lifecycle Services otwórz bibliotekę udostępnionych elementów zawartości, wybierz wartość **Model** jako typ elementu zawartości i pobierz plik **licencji DOM**.
        1. Uruchom Menedżera usług Microsoft Internet Information Services (IIS) kliknij prawym przyciskiem myszy pozycję **AOSService website**, a następnie wybierz opcję **Eksploruj**. Zostanie wyświetlone okno Eksploratora Windows z lokalizacją **\<AOS service root\>\\webroot**. Zanotuj ścieżkę \<AOS Service root\>, ponieważ będzie ona potrzebna w kolejnym kroku.
        1. Skopiuj plik konfiguracji do katalogu **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin**.
        1. Przejdź do klienta centrali, a następnie otwórz stronę **Parametry DOM**. Na karcie **Zmienna** w polu **Typ zmiennej** zaznacz opcję **Zmienna produkcji** i upewnij się, że nie są wyświetlane żadne komunikaty o błędach.

        > [!NOTE]
        > Zmienna uproszczona została udostępniona, aby sprzedawcy detaliczni mogli wypróbować funkcję DOM bez konieczności wdrażania specjalnej licencji. Organizacje nie powinny używać zmiennej uproszczonej w środowiskach produkcyjnych.
        >
        > Zmienna produkcji wpływa na poprawę wydajności (np. liczbę obsługiwanych w ramach sesji zamówień i wierszy zamówienia) i zbieżności wyników (partia zamówień może nie dawać najlepszych wyników w przypadku niektórych scenariuszy). Niektóre reguły, takie jak **Reguła zamówień częściowych** i **Reguła maksymalnej liczby lokalizacji**, wymagają zmiennej produkcji.

6. Przejdź z powrotem do opcji **Retail i Commerce \> Zarządzanie zamówieniami rozdzielonymi \> Ustawienia \> Parametry DOM**.
7. Na karcie **Sekwencje identyfikatorów** przypisz wymagane sekwencje numerów do różnych jednostek DOM.

    > [!NOTE]
    > Przed przypisaniem sekwencji numerów do jednostek zdefiniuj je na stronie **Sekwencje numerów** (**Administrowanie organizacją \> Sekwencje numerów \> Sekwencje numerów**).

8. Funkcja DOM obsługuje definicje różnych typów reguł DOM. Organizacje mogą konfigurować wiele reguł w zależności od potrzeb biznesowych. Reguły DOM możesz zdefiniować dla grupy lokalizacji lub poszczególnych lokalizacji, a także dla określonej kategorii produktów, produktu lub wariantu. Aby utworzyć grupowanie lokalizacji, które muszą być używane w regułach DOM, wykonaj następujące kroki:

    1. Przejdź do opcji **Retail i Commerce \> Konfiguracja kanału \> Grupy realizacji**.
    2. Wybierz opcję **Nowa** i nadaj nowej grupie nazwę i opis.
    3. Wybierz opcję **Zapisz**.
    4. Wybierz opcję **Dodaj wiersz**, aby dodać pojedynczą lokalizację do grupy. Możesz także wybrać opcję **Dodaj wiersze**, aby dodać wiele lokalizacji.

    > [!NOTE]
    > W rozwiązaniu Commerce w wersji 10.0.12 lub wyższej opcja **Możliwość określenia lokalizacji, w której włączono opcję „wysyłka” lub „pobranie” w grupie realizacji** musi być włączona w obszarze roboczym **Zarządzanie funkcjami**.
    >
    > Ta funkcja umożliwia dodanie nowych konfiguracji na stronie **Grupy realizacji**, dzięki czemu można określić, czy magazyn może być używany do wysyłki lub czy kombinacja magazynu/sklepu może być używana do wysyłki, pobierania lub do obu tych celów. 
    >
    > Po włączeniu tej funkcji zostaną zaktualizowane opcje dostępne dla wyboru lokalizacji podczas tworzenia zamówień odbioru lub wysyłki w punkcie sprzedaży.
    >
    > Włączenie funkcji powoduje także aktualizowanie stron w punkcie sprzedaży w przypadku zaznaczenia operacji „wyślij wszystko” lub „wybrane do wysyłki”.

9. Aby zdefiniować reguły, przejdź do opcji **Retail i Commerce \> Zarządzanie zamówieniami rozdzielonymi \> Ustawienia \> Zarządzaj regułami**. Obecnie obsługiwane są następujące reguły DOM:

    - **Reguła minimalnych zapasów** — ten typ reguły umożliwia organizacjom wyodrębnienie określonej ilości produktu, aby wykorzystać ją do celów innych niż realizacja zamówienia. Organizacje mogą na przykład nie chcieć, aby w systemie DOM na potrzeby realizacji zamówienia były dostępne wszystkie zapasy w sklepie. Zamiast tego mogą chcieć zarezerwować część zapasów dla klientów impulsowych. Jeśli używany jest ten typ reguły, możesz określić minimalny poziom zapasów dla kategorii produktów, określonego produktu lub wariantu produktu według lokalizacji lub grupy lokalizacji. Minimalny poziom zapasów można również zdefiniować za pomocą dodatkowych hierarchii kategorii. Jeśli produkt należy do wielu kategorii, kategoria uzupełniająca ma najwyższy priorytet dla wszystkich reguł, w których można używać kategorii.
    - **Reguła priorytetu lokalizacji realizacji** — ten typ reguły umożliwia organizacjom definiowanie hierarchii lokalizacji w celu ustalenia priorytetu, który jest uwzględniany przez aparat DOM podczas próby określenia lokalizacji realizacji dla poszczególnych produktów. Prawidłowy zakres priorytetów wynosi od 1 do 10, gdzie 1 oznacza najwyższy priorytet, a najniższy priorytet to 10. Lokalizacje, które mają wyższy priorytet, są brane pod uwagę przed lokalizacjami o niższym priorytecie. Jeśli dana reguła jest zdefiniowana jako ograniczenie bezwarunkowe, zamówienia są przekazywane tylko do lokalizacji, w przypadku których zostały zdefiniowane priorytety. Zarządzanie DOM preferuje wysyłanie zamówień całkowicie z jednej lokalizacji. Jeśli więc w lokalizacji o priorytecie 1 nie jest dostępne całe zamówienie i jego wiersze, zarządzanie DOM spróbuje zrealizować to zamówienie w lokalizacji o priorytecie 2.
    - **Reguła częściowych zamówień** — w wersji 10.0.5 rozwiązania Retail parametr **Zrealizować zamówienie tylko z jednej lokalizacji** został zmieniony na **Lokalizacje maksymalnej realizacji**. Stary parametr umożliwia użytkownikom skonfigurowanie, czy zamówienia mogą być realizowane tylko z jednej lokalizacji, czy z wielu możliwych lokalizacji. Nowy parametr umożliwia użytkownikom określenie, czy realizacja może pochodzić z określonego zestawu lokalizacji (do pięciu), czy z jak największej liczby lokalizacji. W przypadku wszystkich opcji z wyjątkiem realizacji z jednej lokalizacji zarządzanie DOM podzieli wiersz, ponieważ przetwarzanie zamówienia odbywa się według wiersza. Ta reguła działa tylko ze zmienną produkcji.
    - **Reguła lokalizacji realizacji offline** — ta reguła umożliwia organizacji określenie lokalizacji lub grupy lokalizacji jako działających w trybie offline lub niedostępnych dla funkcji DOM, dzięki czemu nie możesz przypisać do tych lokalizacji zamówień do realizacji.
    - **Reguła maksymalnej liczby odrzuceń** — ta reguła umożliwia organizacjom określenie progu liczby odrzuceń. Po osiągnięciu progu procesor DOM oznaczy zamówienie lub wiersz zamówienia jako wyjątek i wykluczy go z dalszego przetwarzania. Aby zapewnić wydajność, zarządzanie DOM nie sprawdza historii wszystkich odrzuceń. 

        Po przypisaniu wierszy zamówienia do lokalizacji może ona odrzucić przypisany wiersz zamówienia w związku z brakiem możliwości realizacji tego wiersza z określonych powodów. Odrzucone wiersze są oznaczane jako wyjątki i ponownie umieszczane w puli do przetwarzania podczas następnej sesji. Podczas następnej sesji funkcja DOM podejmie próbę przypisania odrzuconego wiersza do innej lokalizacji. Nowa lokalizacja może również odrzucić przypisany wiersz zamówienia. Ten cykl przypisania i odrzucenia może występować wiele razy. Jeśli liczba odrzuceń osiągnie określony próg, funkcja DOM oznaczy wiersz zamówienia jako stały wyjątek i nie będzie ponownie pobierać tego wiersza w celu jego przypisania. Funkcja DOM weźmie pod uwagę wiersz zamówienia w celu jego ponownego przypisania tylko w przypadku ręcznego zresetowania stanu wiersza zamówienia przez użytkownika.

    - **Reguła maksymalnej odległości** — ta reguła umożliwia organizacjom definiowanie maksymalnej odległości, w jakiej może znajdować się lokalizacja lub grupa lokalizacji w celu realizacji zamówienia. Jeśli dla lokalizacji określone są nakładające się na siebie reguły maksymalnej odległości, funkcja DOM zastosuje najniższą maksymalną odległość zdefiniowaną dla tej lokalizacji.
    - **Reguła maksymalnej liczby zamówień** — ta reguła umożliwia organizacjom definiowanie maksymalnej liczby zamówień do przetworzenia w lokalizacji lub grupie lokalizacji. W procesie optymalizacji system rozważy zamówienia, które nie zostały wysłane z tych lokalizacji. To sprawdzenie jest wykonywane w różnych profilach. Dlatego jeśli pokrywająca się maksymalna liczba zamówień zostanie zdefiniowana w profilach dla tej samej lokalizacji, system będzie uwzględniał maksymalną liczbę zamówień zdefiniowaną we wszystkich profilach. 

    Poniżej przedstawiono niektóre wspólne atrybuty, które mogą zostać zdefiniowane dla wszystkich wymienionych typów reguł:

    - **Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól można określić zakres dat obowiązywania każdej reguły.
    - **Wyłączone** — tylko te reguły, które mają wartość **Nie** w tym polu są brane pod uwagę w sesji DOM.
    - **Ograniczenie bezwarunkowe** — reguła może być zdefiniowana jako ograniczenie bezwarunkowe lub nie. Wszystkie sesje DOM odbywają się w dwóch iteracjach. W pierwszej iteracji każda reguła jest traktowana jako ograniczenie bezwarunkowe niezależnie od ustawienia tego pola. Oznacza to, że stosowane są wszystkie reguły. Jedynym wyjątkiem jest reguła **Priorytet lokalizacji**. W drugiej iteracji reguły, które nie zostały zdefiniowane jako ograniczenia bezwarunkowe, są usuwane, a zamówienie lub wiersze zamówienia, które nie zostały przypisane do lokalizacji, gdy wszystkie reguły były stosowane, są przypisywane do lokalizacji.

10. Profile realizacji są używane do grupowania kolekcji reguł, firm, źródeł zamówień sprzedaży i metod dostawy. Każda sesja DOM odnosi się do określonego profilu realizacji. W ten sposób organizacje mogą definiować i uruchamiać zestawy reguł dla zbioru firm w przypadku zamówień, które mają określone źródła zamówień sprzedaży i metody dostawy. W związku z tym, jeśli mają być uruchamiane różne zestawy reguł dla różnych źródeł zamówień sprzedaży lub metod dostawy, możesz odpowiednio zdefiniować profile realizacji. Aby skonfigurować profile realizacji, wykonaj następujące kroki:  

    1. Przejdź do opcji **Retail i Commerce \> Zarządzanie zamówieniami rozdzielonymi \> Ustawienia \> Profile realizacji**.
    2. Wybierz pozycję **Nowy**.
    3. Wprowadź wartości w polach **Profil** i **Opis**.
    4. Ustaw opcję **Wynik automatycznego zastosowania**. W przypadku ustawienia wartości **Tak** dla tej opcji wyniki sesji DOM dla profilu będą automatycznie stosowane do wierszy zamówienia sprzedaży. Po ustawieniu wartości **Nie** wyniki będą mogły być tylko przeglądane w planie realizacji. Nie będą one stosowane do wierszy zamówienia sprzedaży.
    5. W celu uruchomienia profilu DOM w przypadku zamówień ze wszystkimi źródłami zamówień sprzedaży, włącznie z zamówieniami z niezdefiniowanym źródłem zamówienia sprzedaży, ustaw wartość **Tak** opcji **Przetwarzaj zamówienia z pustym pochodzeniem sprzedaży**. Aby uruchomić profil tylko dla kilku źródeł zamówień sprzedaży, możesz zdefiniować je na stronie **Pochodzenia sprzedaży**, jak to wyjaśniono później.

        > [!NOTE]
        > W rozwiązaniu Commerce w wersji 10.0.12 lub wyższej funkcja **Możliwość przypisywania grupy realizacji do profilu realizacji** musi być włączona w obszarze roboczym **Zarządzanie funkcjami**. Ta funkcja umożliwia określenie listy magazynów, które powinny być uwzględniane przez zarządzanie DOM po uruchomieniu optymalizacji z profilem realizacji. Jeśli ta lista magazynów nie zostanie określona, zarządzanie DOM przeszuka wszystkie magazyny w osobach prawnych zdefiniowanych w profilu.
        >
        > Ta funkcja umożliwia dodanie nowej konfiguracji na stronie **Profil realizacji**, która może zostać skojarzona z jedną grupą realizacji. 
        >
        > W przypadku wybrania grupy realizacji, reguły modelu DOM dla tego profilu realizacji będą efektywnie uruchamiane w odniesieniu do magazynów „dostawy”, które znajdują się w grupie realizacji. 
        > 
        > Aby efektywnie wykorzystać tę funkcję, upewnij się, że istnieje jedna grupa realizacji zawierająca wszystkie magazyny wysyłki, a następnie skojarz tę grupę z profilem realizacji.

    6. Na skróconej karcie **Firmy** wybierz opcję **Dodaj**, a następnie wybierz firmę.
    7. Na skróconej karcie **Reguły** wybierz opcję **Dodaj**, a następnie wybierz regułę do połączenia z profilem.
    8. Powtórz dwa poprzednie kroki, aby skojarzyć wszystkie wymagane reguły z profilem.
    9. Wybierz opcję **Zapisz**.
    10. W okienku akcji na karcie **Ustawienia** wybierz opcję **Metody dostawy**.
    11. Na stronie **Metody dostawy** wybierz opcję **Nowa**.
    12. W polu **Firma** wybierz firmę. Lista firm zawiera tylko te firmy, które zostały wcześniej dodane.
    13. W polu **Metoda dostawy** wybierz metodę dostawy do skojarzenia z tym profilem. Metody dostawy nie możesz przypisać do wielu aktywnych profili.
    14. Powtórz dwa poprzednie kroki, aby skojarzyć wszystkie wymagane metody dostawy z profilem.
    15. Zamknij stronę **Metody dostawy**.
    16. W okienku akcji na karcie **Ustawienia** wybierz opcję **Pochodzenia zamówień sprzedaży**.
    17. Na stronie **Pochodzenia sprzedaży** wybierz opcję **Nowe**.
    18. W polu **Firma** wybierz firmę. Lista firm zawiera tylko te firmy, które zostały wcześniej dodane.
    19. W polu **Pochodzenie sprzedaży** wybierz pochodzenie sprzedaży do skojarzenia z tym profilem. Pochodzenia sprzedaży nie możesz przypisać do wielu aktywnych profili.
    20. Powtórz dwa poprzednie kroki, aby skojarzyć wszystkie wymagane pochodzenia sprzedaży z profilem.
    21. Zamknij stronę **Pochodzenia sprzedaży**.
    22. Ustaw wartość **Tak** opcji **Włącz profil**. W przypadku błędów w konfiguracji zostanie wyświetlony komunikat o błędzie.

## <a name="dom-processing"></a>Przetwarzanie DOM

Funkcja DOM zostanie uruchomiona tylko w ramach zadania wsadowego. Aby skonfigurować zadanie wsadowe dla sesji DOM, wykonaj poniższe kroki.

1. Przejdź do opcji **Retail i Commerce \> Zarządzanie zamówieniami rozdzielonymi \> Przetwarzanie wsadowe \> Ustawienia zadania procesora DOM**.
1. Na skróconej karcie **Parametry** w polu **Profil realizacji** wybierz profil, dla którego ma być uruchomiona funkcja DOM.
1. Na skróconej karcie **Uruchom w tle** w polu **Grupa zadań wsadowych** wybierz skonfigurowaną grupę zadań wsadowych.
1. W polu **Opis zadania** wprowadź nazwę zadania wsadowego.
1. Wybierz opcję **Cykl** i określ cykl zadania wsadowego.
1. Kliknij przycisk **OK**.

W czasie przetwarzania funkcja DOM uwzględni zamówienie i wiersze zamówienia w sposób opisany poniżej:

- Wiersze zamówienia spełniające kryteria określone dla źródeł zamówień sprzedaży, metod dostawy i firmy zgodnie z definicją podaną w profilu DOM, a także wiersze spełniające którekolwiek z tych kryteriów:

    - Zostały utworzone w kanałach handlu.
    - Nigdy nie były przekazywane przez funkcję DOM.
    - Były wcześniej przekazywane przez funkcję DOM, ale zostały oznaczone jako wyjątki i znajdują się poniżej progu liczby prób.
    - Metoda dostawy to nie odbiór ani dostawa elektroniczna.
    - Nie zostały oznaczone do dostawy.
    - Nie zostały ręcznie wykluczone.

- Zamówienia, które nie zostały wstrzymane.

Po zastosowaniu reguł, ograniczeń zapasów i optymalizacji funkcja DOM wybiera lokalizację położoną najbliżej adresu dostawy klienta. Zarządzanie DOM konwertuje adresy typu **Dostawa** na wartości szerokości i długości geograficznej. Następnie konwertuje adres dostawy na zamówieniu sprzedaży na wartości szerokości i długości geograficznej, po czym aktualizuje wartości szerokości i długości geograficznej adresu do przyszłego użytku. Zarządzanie DOM polega na Mapach Bing, aby określić dokładne wartości szerokości i długości geograficznej na podstawie informacji o adresie, miejscowości i kodzie pocztowym.

W zależności od ustawień zarządzanie DOM używa interfejsu API Map Bing do obliczania powietrznej i drogowej odległości. Następnie te informacje są używane do określania kosztu wysyłki. Model optymalizacji określa priorytety realizacji pełnego zamówienia z jednej lokalizacji. Nawet jeśli część zamówienia jest dostępna w tej samej miejscowości lub kodzie pocztowym, model został zoptymalizowany w celu zmniejszenia liczby wysyłek. 

Zarządzanie DOM wyszukuje dostępne zapasy, wyświetlając dostępne zapasy w encjach magazynowych V2. Podczas każdego uruchomienia partii zarządzanie DOM dzieli zamówienia na partie w zależności od wartości parametru **Procesor DOM** dla zadań zdefiniowanych w profilu. Wartość domyślna tego parametru to **2000**. Jeśli na przykład podczas uruchamiania jest optymalizowanych 10 000 wierszy zamówienia, a parametr **Procesor DOM** ma wartość domyślną **2000**, to zarządzanie DOM tworzy pięć przetwarzanych jednocześnie partii. Plany realizacji są następnie uzyskiwane z optymalizatora i stosowane w wierszu. Jeśli wiersz zamówienia musi zostać podzielony między dwie lokalizacje, zarządzanie DOM zapewnia odpowiednie rozłożenie cen i podatków na wiersze.

![Kryteria zamówień sprzedaży.](./media/ordercriteria.png "Kryteria zamówień sprzedaży")

## <a name="results-of-dom-runs"></a>Wyniki sesji DOM

Jeśli została ustawiona wartość profilu realizacji **Automatyczne zastosowanie**, wyniki sesji zostaną automatycznie zastosowane do wierszy zamówienia sprzedaży, a plan realizacji może zostać wyświetlony osobno. Jednak jeśli nie została ustawiona wartość profilu realizacji **Automatyczne zastosowanie**, wyniki sesji możesz wyświetlić tylko w widoku planu realizacji. 

Aby wyświetlić wszystkie wygenerowane plany realizacji, wykonaj opisane poniżej kroki.

1. Przejdź do opcji **Retail i Commerce \> Zarządzanie zamówieniami rozdzielonymi \> Zarządzanie zamówieniami rozdzielonymi**.
2. W obszarze roboczym **Zarządzanie zamówieniami rozdzielonymi** wybierz kafelek **Plany realizacji**.
3. Wybierz identyfikator odpowiedniego planu realizacji zamówienia w celu wyświetlenia tego planu.

    Sekcja szczegółów zamówienia planu realizacji zawiera wiersze oryginalnego zamówienia sprzedaży, które były częścią sesji. Oprócz standardowych pól wiersza zamówienia sprzedaży sekcja szczegółów zamówienia zawiera także następujące trzy pola związane z funkcją DOM:

    - **Typ realizacji** — to pole wskazuje, czy wiersz zamówienia sprzedaży został przekazany całkowicie lub częściowo do lokalizacji czy też nie został wcale do niej przekazany.
    - **Podziel** — to pole wskazuje, czy wiersz zamówienia sprzedaży został podzielony i przekazany do różnych lokalizacji.
    - **Liczba lokalizacji realizacji** — to pole wskazuje, ile wierszy realizacji zostało utworzonych dla jednego wiersza zamówienia sprzedaży (na podstawie liczby lokalizacji, do których został przekazany wiersz oryginalnego zamówienia sprzedaży).

    Sekcja szczegółów realizacji zamówienia zawiera przypisanie wierszy oryginalnego zamówienia sprzedaży do różnych lokalizacji wraz z ich ilościami.

## <a name="order-line-actions-and-statuses"></a>Akcje i stany wierszy zamówienia

Poniżej opisano ustawienia w wierszu zamówienia. Aby otworzyć wiersz zamówienia, przejdź do opcji **Retail i Commerce \> Odbiorcy \> Wszystkie zamówienia sprzedaży**.

- Jeśli zostanie ustawiona wartość **Tak** dla opcji **Wyklucz z przetwarzania DOM** na karcie **Ogólne** wiersza zamówienia sprzedaży, zamówienie lub wiersz zamówienia zostanie wykluczony z przetwarzania DOM.
- W polu **Stan DOM** na karcie **Ogólne** wiersza zamówienia sprzedaży możesz ustawić jedną z następujących wartości:

    - **Brak** — wiersz zamówienia nigdy nie został przekazany.
    - **Zakończono** — wiersz zamówienia został pomyślnie przekazany i przypisany do lokalizacji.
    - **Wyjątek** — wiersz zamówienia został pomyślnie przekazany, ale nie może zostać przypisany do lokalizacji. Wyjątki mają wiele podtypów, które możesz wyświetlić z poziomu obszaru roboczego DOM:

        - **Brak dostępnej ilości** — nie są dostępne zapasy, aby przypisać zamówienie w lokalizacjach.
        - **Maksymalna liczba odrzuceń** — dla wiersza zamówienia został osiągnięty próg maksymalnej liczby odrzuceń.
        - **Konflikt modyfikacji danych** — wiersz zamówienia sprzedaży został zmieniony od czasu przekazania zamówienia. Z tego względu nie możesz zastosować planu realizacji do zamówienia.
        - **Określony wyjątek wiersza zamówienia** — w wierszu zamówienia istnieje wiele wyjątków.

- Podczas wprowadzania zamówienia sprzedaży funkcja DOM może działać w trybie interaktywnym. Po określeniu produktów i ich ilości podczas wprowadzania danych wiersza zamówienia możesz wybrać opcję **Aktualizuj wiersz**, a następnie w obszarze **DOM** wybrać opcję **Sugeruj lokalizację realizacji**. Następnie zostanie wyświetlona oparta na regułach DOM lista lokalizacji, w ramach której możesz dokonać realizacji dla ilości wskazanej w wierszu zamówienia. Ta lista jest posortowana według odległości. Wybierz odpowiednią lokalizację i magazyn w wierszu zamówienia sprzedaży. W celu zapewnienia działania tej funkcji musi istnieć aktywny profil realizacji odpowiadający pochodzeniu sprzedaży i metodzie dostawy w wierszu sprzedaży.
- Aby wyświetlić dzienniki sesji DOM dla wiersza zamówienia sprzedaży, wybierz opcję **Wiersz zamówienia sprzedaży**, a następnie wybierz w obszarze **DOM** opcję **Wyświetl dzienniki DOM**. Dzienniki DOM umożliwiają wyświetlenie wszystkich zdarzeń i dzienników, które zostały wygenerowane przez sesję DOM. Dzienniki mogą ułatwiać zrozumienie, dlaczego określona lokalizacja została przypisana do wiersza zamówienia oraz jakie reguły i ograniczenia były brane pod uwagę w ramach przypisania. Na karcie **Zarządzaj** dzienniki DOM są również dostępne na poziomie nagłówka zamówienia sprzedaży.

## <a name="run-a-clean-up-job-for-dom-fulfillment-plans"></a>Uruchamianie zadania oczyszczania dla planów realizacji DOM

Podczas przetwarzania DOM tworzone są plany realizacji. Z biegiem czasu w systemie dostępnych będzie wiele zapisanych planów realizacji. Aby zarządzać liczbą planów realizacji przechowywanych w systemie, możesz skonfigurować zadanie wsadowe, które będzie usuwać starsze plany realizacji w oparciu o wartość **Okres przechowywania w dniach**.

1. Przejdź do opcji **Retail i Commerce \> Zarządzanie zamówieniami rozdzielonymi \> Przetwarzanie wsadowe \> Ustawienia zadania usuwania danych realizacji DOM**. 
1. W polu **Grupa zadań wsadowych** wybierz skonfigurowaną grupę zadań wsadowych.
1. Wybierz opcję **Cykl** i określ cykl zadania wsadowego.
1. Kliknij przycisk **OK**.

## <a name="more-information"></a>Więcej informacji

Poniżej przedstawiono niektóre kwestie, o których należy pamiętać podczas korzystania z funkcji DOM:

- Obecnie funkcja DOM sprawdza tylko zamówienia, które są tworzone w kanałach handlu. Zamówienia sprzedaży są identyfikowane jako zamówienia sprzedaży detalicznej, jeśli dla opcji **Commerce — sprzedaż** jest ustawiona wartość **Tak**.
- Firma Microsoft nie przetestowała funkcji DOM z wykorzystaniem zaawansowanych funkcji zarządzania magazynem. Klienci i partnerzy powinni zatem zachować ostrożność i ustalić, czy funkcja DOM jest zgodna z zaawansowanymi funkcjami zarządzania magazynem i istotnymi dla nich procesami. Zaawansowane magazynowanie umożliwia konfigurowanie wymiarów, takich jak stan zapasów, które nie zapewniają dokładnej interpretacji dostępnych zapasów. Zarządzanie DOM oferuje rozszerzalny sposób ustawiania dostępnych zapasów dla implementacji, w których jest stosowana funkcja zaawansowanego magazynowania. Można go używać do pracy z niestandardowymi wartościami stanu zapasów i innych wymiarów.

    Możliwości rozszerzania w zarządzaniu DOM są ograniczone, ponieważ optymalizacja występuje we wstępnie utworzonym modelu MIP, który uwzględnia optymalizację i jej ograniczenia. Dostępnych jest już kilka rozszerzalnych punktów do ustawiania zapasów i optymalizacji przetwarzania końcowego. Profile zarządzania DOM mogą różnić się według pochodzenia sprzedaży i trybu dostawy. Pochodzenie zamówienia sprzedaży można ustawić podczas pozyskiwania zamówienia i na podstawie tych wartości można używać różnych strategii optymalizacji. Zarządzanie DOM obsługuje także tworzenie niestandardowych zadań wsadowych, które mogą podejmować zadanie procesora DOM jako dane wejściowe i umożliwić przekazywanie profilu jako parametru. Dzięki temu jedna optymalizacja może być uruchamiana po drugiej w celu obsługi różnych scenariuszy biznesowych.

- Funkcja DOM jest dostępna tylko w chmurowej wersji aplikacji Commerce. Nie jest ona obsługiwana w przypadku wdrożeń lokalnych.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
