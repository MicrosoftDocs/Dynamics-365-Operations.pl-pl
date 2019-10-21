---
title: Zarządzanie odpisami handlowymi
description: W tym temacie opisano zarządzanie rabatami handlowymi w programie Dynamics 365 Supply Chain Management.
author: t-benebo
manager: AnnBe
ms.date: 08/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: t-benebo
ms.search.validFrom: 2018-01-31
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 623c25490964ccdf6abc37acaffee7ac0844cf39
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251162"
---
# <a name="trade-allowance-management"></a>Zarządzanie odpisami handlowymi

[!include [banner](../includes/banner.md)]

Narzędzie Zarządzanie odpisami handlowymi pozwala firmom zarządzać programami promocji sprzedaży oferującymi nagrody pieniężne w postaci „wynagrodzenia za wyniki” odbiorcom, którzy osiągną wyznaczone cele ilościowe i behawioralne. Możliwości tej funkcji są przeznaczone dla firm, które realizują kompleksowe procesy promowania w celu osiągania zysku, obejmujące m.in. etapy budżetowania i przydzielania funduszy promocji, skonfigurowania umowy rabatowej, generowania i przetwarzania roszczeń, przetwarzania płatności oraz analizy efektywności promocji.


Ten artykuł zawiera ogólne omówienie funkcji Zarządzanie odpisami handlowymi oraz przybliża typowe zadania wykonywane w ramach zarządzania programem promocji sprzedaży. Oczekuje się, że z tej funkcjonalności będzie korzystać kilka rodzajów użytkowników, którzy mają różne obowiązki w zakresie operacji i podejmowania decyzji:

- Przydzielanie uznaniowych funduszy do wybranych kont oraz konfigurowanie umów rabatu handlowego (inaczej „dotyczących odpisów handlowych”) dla promocji rozliczanych poprzez fakturowanie zwrotne lub jednorazową ryczałtową wypłatę całej sumy (za uzgodnione usługi)
- Realizowanie wynegocjowanych umów na promocje w trakcie prowadzonej sprzedaży i generowanie roszczeń o rozliczenie z tytułu fakturowania zwrotnego
- Obliczanie, zatwierdzanie i przetwarzanie wygenerowanych roszczeń, a następnie przekazywanie ich do modułu Rozrachunki z odbiorcami jako potrącenia w celu rozliczenia płatności
- Uzgadnianie częściowych wpłat odbiorcy z należnymi potrąceniami
- Śledzenie wykorzystania funduszu promocyjnego oraz ocena rentowności i efektywności programu

## <a name="audience-and-purpose"></a>Odbiorcy i cel

Informacje w tym dokumencie są przeznaczone dla osób podejmujących decyzje biznesowe w przedsiębiorstwach na stanowiskach takich jak menedżer ds. zaopatrzenia, dyrektor finansowy (CFO) i menedżer księgowości, których obowiązki są następujące:

- Budżety ogólne i przydzielanie środków
- Planowanie i analizowanie promocji sprzedaży
- Zarządzanie personelem, które przetwarza roszczenia o rozliczenie z tytułu fakturowania zwrotnego, dokonuje płatności za przeprowadzone wydarzenia merchandisingowe oraz rozlicza wpłaty częściowe i potrącenia

Osoby pełniące te role szukają sposobów na osiągnięcie następujących celów:

- Lepsze wykorzystanie funduszy na działania promocyjne i marketingowe.
- Elastyczne dostosowanie do różnych typów programów promocyjnych i rabatowych.
- Zmniejszenie obciążeń administracyjnych i liczby błędów związanych z monitorowaniem realizacji promocji i przetwarzaniem roszczeń.
- Poprawa prognoz przepływów pieniężnych dzięki naliczeniu przyszłych zobowiązań.
- Określenie podstawy ilościowej dla trwających i przyszłych negocjacji z odbiorcami na temat promocji.

## <a name="promotional-fund-and-trade-allowance-agreement"></a>Fundusz promocyjny i umowa rabatu handlowego

Umowa rabatu handlowego to program motywacyjny, w którym oferuje się nagrody pieniężne w formie wynagrodzenia za wyniki odbiorcom, którzy osiągną wyznaczone cele ilościowe i/lub behawioralne. Fundusze promocyjne są wydatkami budżetowymi. W ten sposób można rejestrować informacje o kampaniach promocyjnych.

### <a name="promotional-fund"></a>Fundusz promocyjny

Środki finansowe przydzielane do umów rabatów handlowych są rejestrowane na stronie **Fundusze**. Aby otworzyć stronę **Fundusze**, wybierz kolejno opcje **Sprzedaż i marketing** \> **Odpisy handlowe** \> **Fundusze** \> **Fundusze**.

![Strona Fundusze](./media/trade-allowance-management-funds-page.png "Strona Fundusze")

Na stronie **Fundusze** można wyświetlić szczegóły dotyczące funduszy promocyjnych.

Skrócona karta **Ogólne** pokazuje okres, na który są przeznaczone fundusze, i jego zabudżetowaną kwotę. Aby fundusz został przydzielony do umowy na promocję, pole **Stan** musi mieć wartość **Zatwierdzone**.

Skrócona karta **Odbiorcy** pokazuje hierarchię odbiorców. Aby wybrać odbiorców, do których ma być kierowany fundusz, przeciągnij ich do obszaru **Odbiorcy funduszu**. Na tej skróconej karcie widać także sposób rozdziału łącznej kwoty funduszu.

Skrócona karta **Towary** zawiera towary objęte promocją.

### <a name="trade-allowance-agreement"></a>Umowa rabatu handlowego

Po utworzeniu definicji funduszy następnym krokiem w procesie planowania promocji jest zarejestrowanie umów na promocje (nazywanych umowami rabatów handlowych), przydzielenie funduszy oraz zdefiniowanie celów wydajnościowych dla każdego wydarzenia merchandisingowego.

Umowy rabatów handlowych rejestruje się na stronie **Umowy dotyczące odpisu handlowego**. Aby otworzyć stronę **Umowy dotyczące odpisu handlowego**, wybierz kolejno opcje **Sprzedaż i marketing** \> **Odpisy handlowe** \> **Umowy dotyczące odpisu handlowego**.

![Strona Umowy dotyczące odpisu handlowego](./media/trade-allowance-management-agreements-page.png "Strona Umowy dotyczące odpisu handlowego")

#### <a name="header"></a>Nagłówek

Wybierz opcję **Nagłówek**, aby przełączyć na widok nagłówka.

Na skróconej karcie **Ogólne** pola **Zamówienie do** i **Zamówienie od** określają okres ważności umowy. Stan zatwierdzenia umowy **Zatwierdzono wewnętrznie** wskazuje, że umowa jeszcze nie weszła w życie i nie może być stosowana w trakcie przetwarzania zamówienia sprzedaży.

Sekcja **Analizy** na skróconej karcie **Ogólne** zawiera ważne pola określające ilości i koszty używane do oceny promocji:

- Pole **Jednostki podstawowe** określa ilość produktów, jaką należy sprzedać wybranemu odbiorcy, aby można było zastosować promocję.
- Wartość **Obliczona ilość do wysyłki** jest obliczana na podstawie wartości **Procent przyrostu**, która jest planowanym docelowym zwiększeniem sprzedaży w tej promocji.
- Pole **Koszt odpisu handlowego** jest obliczane na podstawie ilości w różnych wydarzeniach w umowie rabatu handlowego.

Na skróconej karcie **Odbiorcy** na liście z lewej strony można wybrać i wyświetlić grupy odbiorców, które są skonfigurowane jako wstępnie zdefiniowane hierarchie. Następnie można wybrać całą hierarchię lub określone konta jako cele dla umowy rabatu.

Na skróconej karcie **Towary**, podobnie jak na skróconej karcie **Towary** na stronie **Fundusze**, produkty są dodawane do umowy w celu skojarzenia ich sprzedaży z uzgodnionym rabatem handlowym.

Na skróconej karcie **Fundusze** można wyświetlić fundusze promocyjne skojarzone z tą umową. Można także wyświetlić alokację kosztów do wydarzeń organizowanych w ramach umowy. Alokacja kosztu do wydarzenia w wysokości 100 procent oznacza, że ta promocja będzie finansowana wyłącznie z jednego funduszu. Alternatywnie umowa na promocję może być finansowana z kilku funduszy i korzystać z równej lub zróżnicowanej alokacji procentowej.

#### <a name="lines"></a>Wiersze

Następnie wybierz opcję **Wiersze**, aby przełączyć na widok wierszy.

Karta **Wydarzenia merchandisingowe** pokazuje typy wydarzeń objętych umową. Istnieją trzy typy: fakturowanie zwrotne, ryczałt i rabat od faktury.

Po wybraniu wydarzenia merchandisingowego i kliknięciu karty **Kwoty** zostaną wyświetlone szczegóły wydarzenia.

![Wierze umowy rabatu handlowego](./media/trade-allowance-management-agreements-lines.png "Wierze umowy rabatu handlowego")

W obszarze **Wiersze odpisu handlowego** można określić zakres ilości lub kwoty, jaki odbiorca musi osiągnąć, aby zgodnie z definicjami otrzymać nagrody.

W przypadku wydarzenia merchandisingowego o typie **Fakturowanie zwrotne** górna sekcja karty **Kwoty** określa reguły, na mocy których faktura zwrotna zostanie zastosowana, wygenerowana i zapłacona. Na przykład reguły mogą określać następujące warunki roszczenia o rozliczenie faktury zwrotnej:

- Bazuje na dacie utworzenia zamówienia sprzedaży (ustawienie **Typ daty przy obliczeniach** ma wartość **Utworzone**).
- Jest obliczane na podstawie kwoty wiersza zamówienia sprzedaży przed rabatami, a nie na podstawie kwoty netto, która uwzględnia rabaty (ustawienie **Na podstawie** ma wartość **Brutto**).
- Jest oparte na ilości sprzedanych produktów, a nie na kwocie (ustawienie **Typ podziału wiersza rabatu** ma wartość **Ilość**).
- Jest obliczane za okres miesiąca (ustawienie **Kumuluj sprzedaż na** ma wartość **Miesiąc**). 
- Jest rozliczane jako potrącenie, a nie za pomocą modułu rozrachunków z dostawcami (ustawienie **Typ płatności** ma wartość **Potrącenia od odbiorcy**).

W przypadku wydarzenia merchandisingowego o typie **Ryczałt** na karcie **Kwoty** jest podawana kwota, która zostanie zapłacona odbiorcy w formie potrącenia, gdy osiągnie on określony wynik zakupowy. Stan zatwierdzenia **Otwarte** wskazuje, że kwota ryczałtu nie została jeszcze uiszczona.

Aby umowa była stosowana do zamówień sprzedaży spełniających jej warunki, stan umowy musi być ustawiony na **Potwierdzone**. 

## <a name="perform-sales-under-the-planned-merchandising-event-and-generate-bill-back-claims"></a>Realizowanie sprzedaży w ramach zaplanowanego wydarzenia merchandisingowego i generowanie roszczeń o rozliczenie z tytułu fakturowania zwrotnego

Po utworzeniu zamówienia sprzedaży zawierającego wiersze, które spełniają wymagania umowy, można wyświetlić powiązane informacje na stronie **Zamówienie sprzedaży**, wybierając kolejno opcje **Wiersz zamówienia sprzedaży** \> **Widok** \> **Szczegóły ceny**.

Na stronie **Szczegóły ceny** na skróconej karcie **Rabaty** pracownik ds. sprzedaży może obejrzeć fakturowanie zwrotne z odnośnej umowy rabatu handlowego (jest wyświetlany identyfikator programu rabatowego) oraz całkowitą kwotę zastosowaną do wiersza. Ta kwota jest także widoczna w polu **Kwota rabatu** w sekcji **Szacowanie marży** strony **Szczegóły ceny**.

Po zaksięgowaniu faktury sprzedaży dla każdego wiersza faktury jest generowane odpowiednie roszczenie o rozliczenie z tytułu fakturowania zwrotnego.

> [!NOTE]
> Aby wyświetlić stronę **Szczegóły ceny**, na stronie **Parametry modułu rozrachunków z odbiorcami** na karcie **Ceny** zaznacz pole wyboru **Włączanie szczegółów ceny**. Z

## <a name="process-claims-and-pass-them-as-deductions-to-ar"></a>Przetwarzanie roszczeń i przekazywania ich jako potrąceń do modułu rozrachunków z odbiorcami

Następnymi krokami w procesie obsługi fakturowania zwrotnego jest przejrzenie, obliczenie i zatwierdzenie roszczeń, a następnie przekształcenie ich na potrącenia.

Pulpit Fakturowanie zwrotne to miejsce, w którym właściciel umowy na promocję okresowo przegląda i przetwarza wygenerowane oświadczenia. Również tutaj administrator rozrachunków z odbiorcami konwertuje zatwierdzone roszczenia o rozliczenie na potrącenia lub regularne płatności, w zależności od metody płatności ustawionej dla roszczenia.

Na stronie **Pulpit fakturowania zwrotnego** można zapoznać się z wierszami roszczeń. Jeśli roszczenia mają stan **Do ponownego obliczenia**, należy je przeliczyć, jeśli mają być ujęte w jakichkolwiek skutkach skumulowanych.

### <a name="recalculate-claims"></a>Ponowne obliczanie roszczeń

Aby ponownie obliczyć roszczenia, w okienku akcji wybierz opcję **Kumuluj**. Następnie w oknie dialogowym **Kumuluj rabaty** wybierz odbiorcę.

W wyniku ponownego obliczenia program generuje nowe roszczenia na kwoty zapewniające dostosowanie pierwotnych roszczeń do kwoty kwalifikowanej za każdą jednostkę. Jedno roszczenie korygujące jest generowane dla każdej unikatowej kombinacji odbiorcy, towaru, waluty, jednostka miary, wymiarów magazynowych, wymiarów finansowych i grupy podatku. Te roszczenia korygujące zawierają to samo odwołanie do numeru zamówienia sprzedaży i faktury, jak roszczenia korygowane (to znaczy roszczenia utworzone pierwotnie na podstawie dokumentu sprzedaży). W odróżnieniu od pierwotnego roszczenia roszczenie korygujące nie ma wartości w polach, które opisują kwoty i ilości wiersza oryginalnego zamówienia sprzedaży.

Po zakończeniu ponownego obliczania stan roszczeń o rozliczenia zmienia się na **Obliczone**. Aby zatwierdzić roszczenia, w okienku akcji wybierz opcję **Zatwierdź**.

### <a name="process-claims-and-pass-them-to-ar"></a>Przetwarzanie roszczeń i przekazywania ich do modułu rozrachunków z odbiorcami

Roszczenia o rozliczenie są teraz gotowe do przetwarzania w module rozrachunków z odbiorcami. Aby wykonać ich przetwarzanie, w okienku akcji wybierz opcję **Przetwarzaj**. 

Podczas przetwarzania roszczeń stan został zmieniony na **Zaznacz** i wskazuje, że księgowanie arkusza (jest księgowany arkusz naliczania rabatów określony w parametrach rozrachunków z odbiorcami) spowodowało zaistnienie następujących zdarzeń: 

- Roszczenia zostały przeniesione do tymczasowego salda odbiorcy jako potrącenia.
- Konto naliczania rabatów zostało uznane kwotą reprezentującą przyszłe zobowiązanie odbiorcy.
- Konto wydatków rabatowych zostało obciążone kwotą reprezentującą koszt poniesiony w związku ze sprzedażą.

Aby sfinalizować proces, pracownik ds. rozrachunków z odbiorcami teraz musi rozliczyć potrącenia naliczeń, przenosząc je do salda odbiorcy za pomocą faktury korygującej (dodającej zobowiązanie). 

Aby rozpocząć zadanie, w okienku akcji na stronie **Odbiorca** wybierz kolejno opcje **Windykacja** \> **Rozlicz transakcje**. Następnie na stronie **Rozlicz transakcje** wybierz kolejno opcje **Funkcje** \> **Program fakturowania zwrotnego**. Ta strona rabatu pokazuje wszystkie roszczenia o rozliczenie z tytułu fakturowania zwrotnego, które wcześniej przetworzono.

Jeśli chcesz utworzyć fakturę korygującą, zaznacz pole wyboru **Zaznacz** we wszystkich wierszach, a następnie wybierz kolejno opcje **Funkcje** \> **Tworzenie faktury korygującej**.

Utworzenie faktury korygującej powoduje zaksięgowanie arkusza. (Jest księgowany arkusz zużycia dla rozrachunków z odbiorcami określony w parametrach rozrachunków z odbiorcami). W związku z tym rzeczywista kwota zobowiązania (uznania) została przeniesiona do salda odbiorcy. Pod względem finansowym ta sytuacja sugeruje, że wystąpiły następujące zdarzenia:

- Konto należności odbiorcy zostało uznane.
- Konto naliczania rabatów zostało obciążone.

Aby zatwierdzić wydarzenie merchandisingowe o typie **Ryczałt**, zaznacz je na stronie **Umowy dotyczące odpisu handlowego**, a następnie na karcie **Kwota** wybierz opcję **Zatwierdź**.

## <a name="settle-the-deduction-that-is-due-and-the-customer-short-pay-by-using-the-deduction-workbench"></a>Rozliczanie należnego potrącenia i częściowej wpłaty odbiorcy za pomocą pulpitu Potrącenie

Często w przewidywaniu fakturowania zwrotnego odbiorcy postanawiają zapłacić tylko część wybranych faktur. Aby zapobiec przyszłym problemom z uzgadnianiem płatności, pracownik ds. rozrachunków z odbiorcami odnotowuje te częściowe wpłaty jako potrącenia podczas rejestrowania faktycznych płatności od odbiorców. Następnie w pulpicie Potrącenie te potrącenia od odbiorców można łatwo rozliczyć względem kwot roszczeń należnych od firmy.

Aby zarejestrować częściową wpłatę odbiorcy w arkuszu płatności, wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Płatności** \> **Arkusz płatności** i utwórz nowy arkusz płatności. Następnie w okienku akcji wybierz opcję **Potrącenia**. Na stronie **Potrącenie** można utworzyć i śledzić kwotę, która została zapłacona częściowo.

Teraz menedżer ds. windykacji odpowiada za rozliczenie otwartej transakcji faktury korygującej względem transakcji częściowej płatności w pulpicie Potrącenie.

Aby zarządzać potrąceniami, wybierz kolejno opcje **Sprzedaż i marketing** \> **Odpisy handlowe** \> **Potrącenia** \> **Pulpit potrącenia**. Górna część strony zawiera wiersze reprezentujące częściowe wpłaty od odbiorcy. Dolna części strony zawiera otwarte transakcje uznania odbiorcy. 

Aby rozliczyć potrącenie względem otwartej transakcji, zaznacz wiersz potrącenia, a następnie na karcie Otwarte transakcje zaznacz wiersz. W okienku akcji kliknij kolejno opcje Obsługa > Uzgodnij.

Stan źródłowych roszczeń o rozliczenie zmieni się na **Zakończone**.

## <a name="analyze-the-effectiveness-of-the-promotion-and-fund-consumption"></a>Analizowanie skuteczności promocji i wykorzystania funduszy

Aby uzyskać podgląd najważniejszych statystyk i wykorzystania funduszy w programie, można użyć kilku raportów i widoków analitycznych dostępnych w module Zarządzanie odpisami handlowymi.

Na stronie **Działanie związane z odpisem handlowym** na karcie **Przegląd** są wyświetlane główne szczegóły umowy rabatu handlowego. Pozostałe karty zawierają więcej szczegółów o powiązanych dokumentach, płatnościach i innych zdarzeniach związanych z programem.

Karta **Podsumowanie** pokazuje łączną ilość produktów, jaką sprzedano w ramach promocji, zafakturowaną kwotę sprzedaży oraz kwoty zapłacone w ramach fakturowania zwrotnego i ryczałtem.

Karta **Uznania dla fakturowania zwrotnego** zawiera szczegółowe informacje o poszczególnych fakturowaniach zwrotnych, którymi uznano odbiorcę.

Aby uzyskać bardziej analityczny podgląd różnych mierników wydajności promocji, można użyć widoku Analiza. Aby przejść do widoku Analiza, kliknij kolejno opcje **Sprzedaż i marketing** \> **Odpisy handlowe** \> **Umowy dotyczące odpisu handlowego**. W okienku akcji kliknij pozycję **Analiza**.  

Aby uzyskać bardziej analityczny podgląd różnych mierników wydajności promocji, można użyć widoku Analiza. Aby przejść do widoku Analiza, kliknij kolejno opcje **Sprzedaż i marketing** \> **Odpisy handlowe** \> **Umowy dotyczące odpisu handlowego**. W okienku akcji kliknij pozycję **Analiza**. 

