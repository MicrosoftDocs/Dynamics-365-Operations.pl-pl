---
title: Prognozy dotyczące stanowisk
description: Wydatki, które dotyczą pracowników, często stanowią znaczną część kosztów organizacji. Prognozowanie stanowisk umożliwia planowanie tych wydatków i uwzględnianie ich w planowaniu budżetu.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.custom: 64413
ms.assetid: 35e791d2-1905-4808-a579-7f181ddddd91
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3452b38fb9fcfc8f4f38e74a8f9c36789110e3a4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985518"
---
# <a name="position-forecasting"></a>Prognozy dotyczące stanowisk

[!include [banner](../includes/banner.md)]

Wydatki, które dotyczą pracowników, często stanowią znaczną część kosztów organizacji. Prognozowanie stanowisk umożliwia planowanie tych wydatków i uwzględnianie ich w planowaniu budżetu.

## <a name="position-forecasting-in-budget-planning"></a>Prognozowanie stanowisk w planowaniu budżetu

[![Składniki prognozowania stanowisk](./media/graphic-top.png)](./media/graphic-top.png) 

Prognozowanie stanowisk wykorzystuje trzy główne elementy w celu podania dokładnych kwot wydatków na dane stanowisko. Kwoty te mogą następnie zostać uwzględnione w planie budżetu na potrzeby obliczania budżetu. 

Głównym składnikiem jest **stanowisko podlegające prognozie**; reprezentuje wszystkie dane kosztów, związanych z jednym stanowiskiem. Można utworzyć wiele wersji stanowiska podlegającego prognozie poprzez przypisanie różnych scenariuszy planu budżetu do każdej z tych wersji. Wiele wersji umożliwia iteratywne podejście do budżetowania umożliwia porównywanie scenariuszy. Każde stanowisko podlegające prognozie ma odpowiednią pozycję w module Zasoby ludzkie.

**Składnik kosztu budżetowego** to element ustawienia reprezentujący określony koszt związany ze stanowiskiem, np. podstawowe wynagrodzenie, część składki na ubezpieczenie zdrowotne pokrywana przez pracodawcę, odpisy na telefon komórkowy itd. Składnik kosztu budżetowego obejmuje konto główne używane zawierające koszty i opcje do obliczenia. Każdy składnik kosztu budżetowego może być przypisany do wielu stanowisk podlegających prognozie. 

**Grupa wynagrodzeń** to opcjonalny element konfiguracji używany do przypisywania zestawu składników kosztu budżetowego i obliczeń wynagrodzeń do stanowisk o podobnych charakterystykach płacy. Grupa wynagrodzenia może zawierać siatkę wynagrodzeń stawek płacowych. Gdy grupa jest przypisany do stanowiska podlegającego prognozie, na poziomie i etapie w siatce można przypisać zarobki dla stanowiska podlegającego prognozie. Zestaw składników kosztu jest dodawany automatycznie.

### <a name="position-forecasting-processes"></a>Procesy prognozowania stanowisk

[![Ilustrowanie procesów prognozowania stanowisk](./media/graphic1b.png)](./media/graphic1b.png) 

W typowym procesie prognozowania stanowisk najpierw należy utworzyć zestaw elementów (składniki kosztu budżetowego i grupę wynagrodzeń). Stanowiska podlegające prognozie będą generowane na podstawie istniejących stanowisk. Następnie można wprowadzić korekty. Na przykład można dodać lub zakończyć stanowisko, zmienić stawki płac i koszty świadczeń oraz dodawać podwyżki. Można utworzyć wiele wersji stanowiska podlegającego prognozie, aby porównywać różne scenariusze budżetowania. Następnie można uwzględnić stanowiska podlegające prognozie w planach budżetu i wprowadzać koszty z pozycji prognozy jako wiersze planu budżetu.

Można tworzyć dodatkowe wersje stanowiska podlegającego prognozie w miarę korygowania planów budżetowych. Wersje te stanowią podstawę dla zmian.

## <a name="position-forecasting-setup"></a>Konfiguracja prognozowania stanowisk
[![Ustawienia podkreślania ilustracji](./media/graphic2-1024x327.png)](./media/graphic2.png)

### <a name="budget-cost-elements"></a>Składniki kosztu budżetowego

Składniki kosztu budżetowego służą do definiowania szczegółów kosztów stanowiska podlegającego prognozie. Informacje te obejmują typ kosztu, jak koszt jest obliczany i, czy koszt jest alokowany do wielu dat, gdy stanowisko podlegające prognozie jest uwzględnione w planie budżetu. 

Określone pola definiują zachowanie składnika kosztu budżetowego. Każdy składnik kosztu budżetowego jest przypisany do typu kosztu budżetowego: **Zarobek**, **Świadczenie**, **Podatek** lub **Inny**. Typy kosztów budżetu są używane głównie do obliczania sum. Wartość **Zastąpienie stanowiska podlegającego prognozie** określa, czy kwoty dla elementu można zmodyfikować dla tego stanowiska podlegającego prognozie. Pole **Metoda alokacji** jest używane podczas dodawania stanowiska podlegającego prognozie do planu budżetu. Kwotę kosztu można podzielić na osobne wiersze planu budżetu z różnymi datami: miesięcznie, kwartalnie, tygodniowo lub co dwa tygodnie. Wybierając datę rozpoczęcia przypisujesz koszt jako osobną kwotę w dniu rozpoczęcia, ustawionym dla stanowiska podlegającego prognozie. 

Obliczenie kwoty kosztów składnika kosztu budżetowego używa dat obowiązywania, dzięki czemu jest możliwe używanie tego samego składnika kosztu w różnych okresach. W każdym okresie przypisane jest jedno konto główne wraz z wartością procentową kwoty rocznej wskazującą kwotę kosztu. Składnik kosztu budżetowego może używać wartości procentowej lub innych składników kosztu albo kwoty rocznej, ale nie obu tych elementów. Można również określić roczny limit. 

Jeśli składnik kosztu jest oparty na wartości procentowej, należy określić składniki kosztu budżetowego, które służą jako podstawa do obliczenia.

**Przykład** 

Organizacja Jodi pozwala na odpis za szkolenie w wysokości 5% wynagrodzenia podstawowego pracownika. Jodi chce utworzyć składnik kosztu budżetowego używany dla tego kosztu. Tworzy nowy składnik kosztu budżetowego i przypisuje typ kosztu budżetowego **Świadczenie**.

Jodi nie chce, żeby przełożeni zmienili kwotę świadczenia. Dlatego wybiera opcję **Nie zezwalaj na zmiany kosztów** w polu **Zastąpienie stanowiska podlegającego prognozie**. Organizacja chce, żeby ten koszt był równomiernie przypisany do każdego miesiąca. Dlatego Jodi wybiera opcję **Kwartalnie** w polu **Metoda alokacji**. 

Następnie Jodi dodaje wiersz obliczenia, ustawia daty i konto główne oraz wprowadza **5,00** jako wartość procentową. Jej organizacja może przeznaczyć rocznie 5000 USD na to świadczenie. Z tego względu Jodi wprowadza tę kwotę jako roczny limit. 

Na koniec Jodi dodaje składniki kosztu o typie dochodowym używane jako podstawa obliczania podstawowego wynagrodzenia. Jej składnik kosztu budżetowego jest teraz gotowy do użycia.

### <a name="compensation-groups"></a>Grupy wynagrodzeń

Grupa wynagrodzeń może służyć do grupowania stanowisk podlegających prognozie o podobnych atrybutach wynagrodzeń. Przy ich użyciu można również zdefiniować zarobki na stanowisku podlegającym prognozie i roczne podwyżki oraz przypisać zestaw wspólnych składników kosztu budżetowego. 

Podstawową funkcją grup wynagrodzeń jest przypisanie zestawu składników kosztu budżetowego do stanowiska podlegającego prognozie. Z tego względu grup wynagrodzeń można używać do dodawania wspólnych kosztów, takich jak programy świadczeń i podatki. Kierownik tworzący stanowisko podlegające prognozie nie musi znać wszystkich składników kosztu, które muszą być dodane. Zamiast tego składniki kosztu można dodawać po wybraniu grupy wynagrodzenia. Składniki są dodawane do ustawień grupy wynagrodzeń na karcie **składniki kosztu budżetowego**. 

Grupy wynagrodzeń mogą także określać stawki zarobków na stanowisku podlegającym prognozie. Grupę ustawia się pod kątem obliczania prognozowanych zarobków na danym stanowisku według stawki godzinowej lub corocznego wynagrodzenia. Na karcie **Tabele stawek wynagrodzenia** siatka wynagrodzeń dla stawek płatności określa zarobki, które są dodawane do pozycji prognozy na podstawie przypisanego poziomu i kroku. Te siatki mogą być oparte na istniejących siatkach wynagrodzeń w module Zasoby ludzkie. Można również tworzyć nowe siatki wynagrodzeń dla planowania budżetu. 

Daty wprowadzenia i data ważności tabelami stawek wynagrodzenia pozwalają na zmianę stawek płac w dowolnym dniu. Ta funkcja jest przydatna, np. gdy jednostka wynegocjowała całościową podwyżkę płac w środku cyklu budżetowego. W takim przypadku zmienia się datę ważności istniejącej tabeli na dzień przed datą zmiany stawki i dodaje nową tabelę stawek, która zaczyna się od nowej daty. Podczas tworzenia nowej tabeli w przypadku wybrania opcji **Utwórz nową siatkę wynagrodzeń na podstawie istniejącej siatki** można wybrać istniejącą tabelę stawek z modułu Zasoby ludzkie. W tworzonej tabeli stawek opcja **Zmiana grupowa** pozwala stosować wzrost lub obniżenie według wartości procentowej lub stałej kwoty do wszystkich stawek na siatce. 

Pola **Harmonogram podwyżki** i **Data podwyższenia** w grupie wynagrodzeń są używane, gdy trzeba utworzyć wzrost wynagrodzeń, ponieważ stanowiska przechodzą z jednego etapu do następnego. Typowym scenariuszem jest wzrost płac. Harmonogram podwyżek określa, czy do podwyżek etapowych używana jest data rocznicy stanowiska czy po prostu jeden ze zwykłych dni. Harmonogram podwyżek stosuje się do wszystkich pozycji prognozy w grupie wynagrodzeń. 

Składnik kosztu typu dochodowego, który jest zaznaczony w grupie wynagrodzeń, jest używany podczas tworzenia dochodów dla stanowisk podlegających prognozie w grupie, włącznie z ich wynagrodzeniem bazowym oraz wszelkimi przyrostami etapowymi. Pole **System stałych wynagrodzeń** łączy grupę wynagrodzeń z planem stałych wynagrodzeń w module Zasoby ludzkie. To łącze może przypisywać informacje dotyczące stałego wynagrodzenia pracownika do stanowiska podlegającego prognozie, dzięki czemu planowanie budżetu może być dokładniejsze. Należy pamiętać, że struktura siatki wynagrodzenia (poziomy i etapy) dla grupy wynagrodzeń powinny być dopasowane do struktury planu stałych wynagrodzeń. W przeciwnym razie system nie może poprawnie połączyć grupy wynagrodzeń i planu stałych wynagrodzeń.

## <a name="creating-forecast-positions"></a>Tworzenie stanowisk podlegających prognozie
[![Podkreślanie ilustracji „Tworzenie stanowisk podlegających prognozie”](./media/graphic3-1024x327.png)](./media/graphic3.png)

### <a name="creating-forecast-positions-for-existing-positions"></a>Tworzenie stanowisk podlegających prognozie dla istniejących stanowisk

W celu uzyskania jak najdokładniejszego planu budżetu można utworzyć stanowiska prognozy za pomocą szczegółów z istniejących stanowisk, bez względu na to, czy stanowisko w danej chwili jest zajęte czy wolne. 

Funkcja **Dodaj istniejące stanowiska** pokazuje wszystkie pozycje dla organizacji. Wybierając datę **Na dzień**, można zmienić listę stanowisk w taki sposób, aby zawierała stanowiska, które istniały na dzień w przeszłości lub, co zdarza się częściej, w przyszłości (np. na początku następnego cyklu budżetowego). Wybierz proces planowania budżetu i scenariusz planu budżetu, wybierz stanowiska na liście, a następnie kliknij **OK**, aby utworzyć stanowisk podlegające prognozie dla wybranych stanowisk. Pamiętaj, że możesz utworzyć tylko jedno stanowiska podlegające prognozie dla każdego istniejącego stanowiska w procesie planowania budżetu i scenariuszu. Można jednak utworzyć dodatkowe wersje, przypisują różne scenariusze planu budżetu. 

Jeśli składniki kosztu budżetowego zostały przypisane do stanowiska w module Zasoby ludzkie, te składniki kosztu budżetowego są także przypisane do pozycji prognozy i używane w kwotach domyślnych. Pole **Przypisany pracownik** dla stanowiska podlegającego prognozie jest ustawione na nazwę pracownika, który jest przypisany do stanowiska, jeśli pracownik jest przypisany. To pole jest prostym polem tekstowym. Nie jest tworzony bezpośrednie łącze. 

Po wybraniu składnika kosztu budżetowego kwota rocznego stałego wynagrodzenia jest przypisywana do stanowiska podlegającego prognozie, używając wybranego składnika kosztu pod warunkiem, że przypisany pracownik ma plan stałego wynagrodzenia. Jeśli pracownik nie ma stałego planu wynagrodzeń lub jeśli żaden pracownik nie jest przypisany, dla składnika kosztu budżetowego używana jest domyślna kwota. 

Jeśli opcja **Przypisz grupę wynagrodzeń** ma wartość **Tak** i jeśli pracownik, który jest przypisany do stanowiska na podstawie stałego planu wynagrodzenie z etapami połączonego z grupą wynagrodzeń (jak to opisano wcześniej), poziom i etap pracownika są przypisane do stanowiska podlegającego prognozie wraz z grupą wynagrodzeń. Składnik kosztu budżetowego dochodów z grupy wynagrodzeń jest dodawany do stanowiska podlegającego prognozie i stosowana jest stawka płacy na poziomie i etapie z grupy wynagrodzeń. 

Ustawienie opcji **Przypisz grupę wynagrodzeń** jest ważniejsze niż ustawienie **Przypisz składnik kosztu budżetowego** . Oba te ustawienia mogą być używane jednocześnie. 

[![Wykres „Przypisz grupę wynagrodzeń”](./media/graphic4.png)](./media/graphic4.png) 

Inną opcją jest przypisanie daty rocznicy. Wybrana data (skorygowana data początkowa, data rozpoczęcia dla pracownika data rozpoczęcia zatrudnienia lub data stażu pracy) dla przypisanego pracownika jest następnie ustawiana jako data rocznicy stanowiska podlegającego prognozie i jest używana w celach informacyjnych gdy generowana jest podwyżka płacy.

### <a name="creating-new-forecast-positions"></a>Tworzenie nowych stanowisk podlegających prognozie

Nowe stanowiska można tworzyć na dwa sposoby: kopiując istniejące stanowisko podlegające prognozie i tworząc całkowicie nowe stanowisko podlegające prognozie. 

Po wybraniu stanowiska podlegającego prognozie zaznacz **Kopiuj wybrane stanowisko podlegające prognozie**, aby utworzyć nowe stanowisk podlegające prognozie, ze stanem prognozy **Proponowane**. Tego stanowiska podlegające prognozie zawiera wszystkie takie same dane jak stanowisko podlegającego prognozie, które zostało skopiowane, oprócz przypisanego pracownika i ewentualnych uwag dla składników kosztu budżetowego. Pamiętaj, że odpowiednie nowe stanowisko jest także tworzone w module Zasoby ludzkie. To stanowisko ma opis **Utworzono według prognozy**. 

Można też utworzyć całkowicie nowe stanowisko podlegające prognozie. Wybierz istniejące stanowisko i wybierz proces planowania budżetu i scenariusz planu budżetu. Następnie możesz dodać dowolne inne szczegóły. Tu także nowe stanowisko jest jednocześnie tworzone w module Zasoby ludzkie.

## <a name="working-with-forecast-positions"></a>Praca ze stanowiskami podlegającymi prognozie
[![Podkreślanie ilustracji „modyfikowanie prognoz stanowisk”](./media/graphic5-1024x327.png)](./media/graphic5.png)

### <a name="multiple-versions-of-a-forecast-position"></a>Wiele wersji stanowiska podlegającego prognozie

Stanowiska podlegające prognozie można modyfikować w celu zastosowania znanych zmian w cyklu budżetu lub aby zmienić zaplanować proponowane zmiany. Typową metodą jest tworzenie podstawowego zestawu stanowisk podlegających prognozie, tworzenie kopii tych stanowisk, a następnie używanie ich do modelowania różnych zestawów zmian. Kopie są przypisywane do różnych scenariuszy planu budżetu, ale przynajmniej do czasu wprowadzenia zmian są poza tym identyczne ze źródłowymi stanowiskami podlegającymi prognozie. Oryginały i kopie dzielą to samo stanowisko w module Zasoby ludzkie. 

Tę funkcję oferuje opcja **Kopii do scenariusza**. Zwróć uwagę, że każde stanowisko w module Zasoby ludzkie może mieć tylko jedno stanowisko podlegające prognozie w poszczególnych scenariuszach planu budżetu.

### <a name="modifying-forecast-positions"></a>Modyfikowanie podlegających prognozie

Zmiany wprowadzone do stanowisk podlegających prognozie są ograniczone do tych stanowisk. Zmiany nie wpływają na rekordy stanowisk w module Zasoby ludzkie. Większość zmian jest też ograniczona do stanowiska podlegającego prognozie, które jest akurat edytowane. Innymi słowy zmiany są właściwe dla przypisanych procesu planowania budżetu i scenariusza planu budżetu. Wyjątkami są zmiany pól wspólnych dla stanowisk we wszystkich procesach i scenariuszach. Te pola obejmują pola dostępne na karcie **Ogólne** i karcie **Wymiary finansowe**. Gdy te pola zostaną zmienione, do pozycji we wszystkich scenariuszach planowania budżetu stosowane są nowe wartości. Dzięki temu za pomocą tych pól można szybko zaktualizować wszystkie wersje.

#### <a name="budget-cost-elements"></a>Składniki kosztu budżetowego

Składniki kosztu budżetowego oferują najważniejsze informacje dla planów budżetu: kwota budżetu i konto główne. Kwota budżetu jest kwotą, która jest wysyłana do planu budżetu, gdy stanowisko podlegające prognozie jest ujęte w planie. Kwota budżetu jest obliczana i nie można zmienić jej bezpośrednio. Ta kwota jest kwotą roczną lub obliczeniem wartości procentowej składników bazowych kwoty rocznej (wg definicji w ustawieniach składnika kosztu budżetowego). Kwota jest następnie brana pod uwagę w liczbie dni w przedziale dat składnika (data początkowa i końcowa), a także przez wartość **przeliczenia na pełne etaty** (FTE) dla tego stanowiska podlegającego prognozie. 

Na przykład wiersz składnika kosztu budżetowego od 1 stycznia 2017 r. do 30 czerwca 2017 r., zawierający roczną kwotę 100 000 i wartość FTE **0,50** jest obliczany następująco: 100 000 × (181 dni ÷ 365 dni) × 0,50 = 24 794,52. 

W przypadku zmiany wartości FTE dla stanowiska podlegającego prognozie, wiersze składnika kosztów budżetowych muszą być obliczane ponownie. Podobnie wiesze te muszą być obliczane ponownie po zmianie dat aktywacji lub przejścia na emeryturę. Zmiany tych dat mogą powodować aktualizację dat początkowej i końcowej składnika kosztu budżetowego, które muszą mieścić się w przedziale czasowym dla stanowiska podlegającego prognozie. Jeśli wymagane jest ponowne obliczenie, przycisk **Oblicz ponownie** staje się dostępny i wyświetlany jest komunikat „Wymaga obliczenia”. Ponowne obliczenie jest również wymagane po dodaniu lub usunięciu składnika kosztu budżetowego.

**Przykład** 

Organizacja rozważa dwie możliwości redukcji kosztów na stanowisku księgowego. Jedna możliwość to likwidacja stanowiska przed końcem roku. Druga to zmiana stanowiska na pół etatu dla całego roku. Brad utworzył stanowisko podlegające prognozie dla istniejącego stanowiska księgowego w scenariuszu bazowym. Kopiuje to bazowe stanowisko podlegające prognozie do scenariusza A, ustawia datę przejścia na emeryturę na 31 maja oblicza ponownie. Następnie Brad kopiuje stanowisko podlegające prognozie do scenariusza B, zmienia wartość FTE na **0,50** i oblicza ponownie. Brad ma teraz trzy wersje, z których każda ma zawiera sumy kosztów dostosowane do jego opcji.

#### <a name="assigning-a-compensation-group"></a>Przypisywanie grupy wynagrodzeń

Podczas pierwszego przypisywania grupy wynagrodzeń do pozycji prognozy dodawane są domyślne elementy kosztu budżetowego z grupy wynagrodzeń. Jeśli elementy kosztów są już przypisane do stanowiska podlegającego prognozie, te elementy kosztów pozostają bez zmian. Jeśli grupa wynagrodzenia został już przypisana i zmieniona, istniejące składniki kosztu budżetowego są usuwane i zastępowane przez zestawem z grupy wynagrodzeń. 

Po wybraniu poziomu wynagrodzeń i etapu dodawany jest składnik kosztu budżetowego dochodów (wg definicji w grupie wynagrodzeń). Kwota roczna jest obliczana przy użyciu kursu na wybranym poziomie i etapie, i roczna liczba godzin w grupie wynagrodzeń (lub dla wynagrodzeń obliczanych rocznie, pełna kwota na danym poziomie i etapie) Ponownie ta kwota jest brana pod uwagę przez zakres dat w wierszu składnika kosztu i wartość FTE pozycji prognozy.

#### <a name="generating-increases"></a>Generowanie podwyżek

Roczne podwyżki (jedna w roku kalendarzowym) mogą być tworzone automatycznie dla stanowisk podlegających prognozie, które mają przypisane grupy wynagrodzenia według etapu. Kliknij **Generuj podwyżki**, aby dodać składnika kosztu budżetowego dochodów na następnym najwyższym etapie. Data rozpoczęcia nowego składnika kosztu budżetowego dochodów jest datą planowanej podwyżki pokazywaną dla stanowiska podlegającego prognozie. Ta data jest ustawiana na podstawie grupy wynagrodzeń następująco: Jeśli harmonogram podwyżek grupy wynagrodzeń jest ustawiony na **Data kalendarzowa**, data podwyżki jest określana w grupie wynagrodzeń. Jeśli harmonogram podwyżek jest ustawiony na **Rocznica**, używane jest pole rocznicy dla stanowiska podlegającego prognozie, a cykl budżetowy wypełnia rok. W przypadku wielu lat kalendarzowych w cyklu budżetu, dodawanych jest wiele podwyżek. 

Data zakończenia bieżącego składnika kosztu budżetowego dochodów jest aktualizowana na dzień przed datą podwyżki. Procesu ponownego obliczania jest stosowany automatycznie podczas generowania podwyżek. Nie trzeba obliczać ponownie ręcznie. 

Jeśli została kliknięta pozycja **Generuj podwyżki** proces jest uruchamiany ponownie, ale nie dodaje kolejnych rekordów. Tworzona jest tylko jedna podwyżka na rok kalendarzowy.

#### <a name="changes-from-other-pages"></a>Zmiany z innych stron

Aktualizacje stanowisk podlegających prognozie mogą też pochodzić z innych obszarów, takich jak strony składnika kosztu budżetowego czy konfiguracji grupy wynagrodzeń. Można także modyfikować stanowiska podlegające prognozie przy użyciu procesu masowej aktualizacji. 

Dostępne są dwie opcje na stronie konfiguracji **Składnik kosztu budżetowego**: **Dodaj do stanowisk** i **Aktualizuj stanowiska**. Opcja **Dodaj do stanowisk** dodaje składniki kosztu budżetowego do zaznaczonych stanowisk podlegających prognozie. Jeśli element jest już przypisany do stanowiska podlegającego prognozie, to stanowisko jest pomijane. Opcja **Aktualizuj stanowisk** ma zastosowanie do bieżących wartości (konto główne, procent, kwota roczna itp.) do wybranych stanowisk podlegających prognozie. 

Każdy proces ma podobną stronę, na której można wybrać stanowiska podlegające prognozie. Na stronie **Dodaj do stanowisk** są pokazane wszystkie stanowiska podlegające prognozie, które są dostępne do wybrania, natomiast na stronie **Aktualizuj stanowiska** widać tylko te stanowiska podlegające prognozie, które mają już przypisany składnik kosztu budżetu. (Dzięki temu na stronie **Aktualizuj stanowiska** można wyszukiwać stanowiska podlegające prognozie, które mają już dołączony składnik kosztu). Przenosisz stanowiska podlegające prognozie z górnej siatki do dolnej siatki, by ująć je w aktualizacji. 

Należy pamiętać, że funkcja **Zmień daty** na karcie **obliczania kosztów** natychmiastowo zmienia daty początkową i końcową składnika kosztu budżetowego dla stanowisk objętych prognozą. Żadne opcje nie są dostępne. 

Na stronie **Grupy wynagrodzeń** funkcja **Aktualizuj stawki stanowisk** dotyczy stosuje stawki z bieżącej tabeli wynagrodzeń do stanowisk objętych prognozą, które są przypisane do grupy. Stawki są aktualizowane i dodatkowe wiersze składnika kosztu są dodawane dla wszystkich wierszy tabeli stawek (na podstawie dat). Jednak składniki kosztu budżetowego i daty podwyżek nie są aktualizowane. Można wybrać procesy i scenariusze planowania budżetu do aktualizacji. Można więc zaktualizować scenariusz, ale zostawić inne scenariusze bez zmian do porównania. 

Wybierając stanowiska podlegające prognozie, a następnie klikając przycisk **Aktualizacja grupowa**, można dodać lub zmienić jednocześnie kilka stanowisk podlegających prognozie. Dostępnych jest wiele opcji: Jedna opcja na karcie **Wymiary finansowe** różni się nieznacznie od innych i jest związana ze składnikami kosztu budżetowego. Aby dodawać składniki kosztu budżetowego, w opcji **Ustawienia domyślne budżetu** trzeba wybrać **Tak**. Jeśli żadne elementy kosztu nie zostaną wybrane, ale **Ustawienia domyślne budżetu** mają wartość **Tak**, wszystkie zaznaczone elementy kosztu budżetu są usuwane. 

Proces ponownego obliczania jest automatycznie używany dla dowolnego stanowiska podlegającego prognozie, które zostało zmienione.

## <a name="bringing-forecast-positions-into-budget-plans"></a>Wprowadzanie pozycji prognozy do planów budżetu

[![Podkreślanie ilustracji „Dodaj do planu budżetu”](./media/graphic6-1024x327.png)](./media/graphic6.png)

Celem tworzenia i modyfikowania pozycji prognozy jest dodawanie ich do planów budżetu, tak aby te plany budżetu obejmowały najdokładniejsze kwoty budżetu. Istnieją dwie metody dodawania pozycji prognozy do planów budżetu. Można użyć procesu generowania lub procesu wybierania w planie budżetu.

### <a name="generating-a-budget-plan-from-forecast-positions"></a>Generowanie planu budżetu na podstawie pozycji prognozy

Funkcja **Generowanie planu budżetu na podstawie pozycji prognozy** tworzy lub aktualizuje plany budżetowe, aby miały kwoty budżetowe i wyniki FTE ze stanowisk podlegających prognozie. Kwoty budżetowe ze stanowisk podlegających prognozie stają się kwotami wiersza planu budżetowego i są zbierane przez wartości wymiaru finansowego i datę wejścia w życie. Proces generowania przypisuje pozycję z prognozy źródłowej do wiersza planu budżetu. Aby wyświetlić stanowisko, można dodać stanowisko prognozy jako wiersz w układzie planu budżetu lub za pomocą zapytania **Wiersze planu budżetu**. Aby pominąć ten przydział, należy ustawić opcję **Uwzględnienie pozycji w wierszu planu budżetu** na **Nie**. 

Można wybrać scenariusz planu budżetowego FTW uwzględniający liczbę FTE w planie budżetu. Można wybrać tylko scenariusze typu ilościowego, które uwzględnione w układzie docelowego planu budżetu. Po wybraniu scenariusza FTE musisz też określić konto główne FTE. To konto jest używane do tworzenia wierszy planu budżetu typu ilościowego. 

Proces planowania budżetu i scenariusz planu budżetu, wybrane w źródle, ustawiają scenariusz docelowy procesu i scenariusza planowania budżetu. Ponieważ te atrybuty są przypisane pozycji prognozy, muszą być dopasowane do planu budżetu. Dlatego atrybuty nie mogą być edytowane w obiekcie docelowym. 

Jeśli zaś idzie o inne procesy generowania, dostępne są trzy opcje:

-   **Tworzenie nowego planu budżetu** — tworzy nowy plan z atrybutami wybieranymi w sekcji **Cel**.
-   **Zamiana istniejącego scenariusza planu budżetu** — powoduje usunięcie wszystkich danych w docelowym planie budżetu w wybranym scenariuszu planu budżetu i utworzenie nowych wierszy z wybranych danych stanowiska podlegającego prognozie.
-   **Aktualizowanie istniejącego scenariusza planu budżetu i dołączanie nowych danych** — aktualizacje istniejące wiersze w planie docelowym, które pasują do wierszy źródła, i oprócz tego dodaje nowe wiersze dla nowych danych. Dopasowanie opiera się na koncie księgowym, dacie, klasie budżecie i innych wartościach, takich jak stanowisko podlegające prognozie. Wszystkie wiersze zawierające numer pozycji odpowiadający źródłowemu numerowi pozycji są zastępowane nowymi wierszami z tekstu źródłowego.

### <a name="selecting-forecast-positions"></a>Wybieranie stanowisk podlegających prognozie

Można również dodawać do planu budżetu kwoty budżetowe dla stanowisk objętych prognozowaniem. Użyj funkcji **Dodawanie pozycji** nad wierszami planu budżetu, aby wybrać stanowiska podlegające prognozie, które chcesz uwzględnić. 

Scenariusze planu budżetu, które można wybrać jako źródło są ograniczone do scenariuszy, które są w układzie planu. Jedna z opcji na karcie **Celu** pozwala określić, czy scenariusz i konto główne FTE mogą zawierać liczby FTE, ale nie są wymagane. 

Ten proces wyboru zachowuje się tak jak opcja **Aktualizowanie istniejącego scenariusza planu budżetu i dołączanie nowych danych** w procesie generowania. Wszystkie istniejące wiersze planu budżetu, w do których jest dodawane stanowisko podlegające prognozie, są usuwane i zastępowane nowymi wierszami opartymi na aktualnym stanie stanowiska podlegającego prognozie.

#### <a name="date-options"></a>Opcje daty

Zarówno dla procesu generowania, jak i dla procesu wyboru, data początkowa wierszu składnika kosztu budżetowego określa datę wejścia w życie odpowiedniego wiersza planu budżetu. Pole **Metoda alokacji** na stronie konfiguracji składnika kosztu budżetowego określa metodę alokacji:

-   **Data początkowa** — data rozpoczęcia składnika kosztu budżetowego jest używana jako data obowiązywania wiersza planu budżetu.
-   **Co miesiąc** — kwota budżetu jest równo podzielona przez liczbę miesięcy w zakresie dat w celu otrzymania typowej kwoty miesięcznej przypisywanej każdego pierwszego dnia miesiąca. Jeśli pierwszy okres jest niepełnym miesiącem, kwota dla tego miesiąca jest brana pod uwagę w liczbie dni aktywności kosztu w tym miesiącu, a wynik jest przypisywany do daty początkowej. Kwota dla ostatniego miesiąca różni się między łączną kwotą budżetu i sumą wszystkich innych miesięcy. Dlatego zaokrąglanie może mieć wypływ na kwotę w ostatnim miesiącu.
-   **Co kwartał** — ta metoda jest taka sama, jak **Co miesiąc**, ale obliczenia są wykonywane za okres trzech miesięcy.
-   **Co tydzień** — logika przypomina tę stosowaną w metodach **Co miesiąc** i **Co kwartał**. Kwota budżetu jest równo podzielona przez liczbę tygodni w zakresie dat w celu otrzymania typowej kwoty tygodniowej przypisywanej każdego pierwszego dnia tygodnia. Jeśli pierwszy okres jest niepełnym tygodniem, kwota dla tego tygodnia jest brana pod uwagę w liczbie dni aktywności kosztu w tym tygodniu, a wynik jest przypisywany do daty początkowej. Kwota dla ostatniego tygodnia różni się między łączną kwotą budżetu i sumą wszystkich innych tygodni. Dlatego zaokrąglanie może mieć wypływ na kwotę w ostatnim tygodniu.
-   **Co dwa tygodnie** — ta metoda jest taka sama, jak **Co tydzień**, ale obliczenia są wykonywane za okres dwóch tygodni.

#### <a name="changing-budget-plan-lines-that-have-forecast-positions"></a>Zmienianie wierszy planu budżetu, które mają stanowiska podlegające prognozie

Wiersze planu budżetu pokazują źródło kwot budżetu (liczba stanowiska podlegającego prognozie), ale nie są połączone. Dlatego zmiany stanowiska podlegającego prognozie nie są wyświetlane w wierszu planu budżetu, a zmiany wiersza planu budżetu są widoczne w stanowisku podlegającym prognozie. W przypadku zmiany stanowiska podlegającego prognozie i jeśli aktualizacje mają być ujęte w planie budżetu, trzeba ponownie umieścić stanowisko podlegające prognozie w planie. Należy jednak pamiętać, że ten proces usuwa wszystkie wiersze, którym przypisano to stanowiska podlegającego prognozie. Dlatego wszelkie zmiany wprowadzone w tych wierszach są usuwane. 

Aby wyświetlić, do których planach budżetowych dodano stanowisko podlegające prognozie, można wygenerować raport **Pozycje prognozy według planów budżetu**. Ewentualnie na stanowisku podlegającym prognozie można otworzyć skróconą kartę **Skojarzone plany budżetu**, aby wyświetlić plany.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]