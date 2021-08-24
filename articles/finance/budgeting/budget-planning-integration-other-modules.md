---
title: Integracja modułu Planowanie budżetu z innymi modułami
description: 'Plany budżetu mogą być generowane z kilku różnych zasobów: Podstawowe elementy przetwarzania okresowego są takie same dla wszystkich zasobów.'
author: ShylaThompson
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 64443
ms.assetid: f9a94db5-906c-404a-9ca5-91528d67c490
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a5841fe48ddf18e3966e25333c5e578912fa0c43c2a7cb27ad24fadd9ad8fb5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762371"
---
# <a name="budget-planning-integration-with-other-modules"></a>Integracja modułu Planowanie budżetu z innymi modułami

[!include [banner](../includes/banner.md)]

 Plany budżetu mogą być generowane z kilku różnych zasobów. Podstawowe elementy przetwarzania okresowego są takie same dla wszystkich zasobów. 



## <a name="periodic-processes-for-generating-budget-plans"></a>Przetwarzanie okresowe w celu generowania planów budżetu

Plany budżetu mogą być generowane z poniższych zasobów:

-   Transakcje modułu Księga główna
-   Środki trwałe
-   Stanowiska podlegające prognozie
-   Prognozy projektów
-   Prognozy dostaw
-   Prognozy popytu
-   Wpisy do rejestru budżetu
-   Inne plany budżetu

Podstawowe elementy przetwarzania okresowego są takie same dla wszystkich procesów. Na kartach można zdefiniować źródła danych, atrybuty docelowe (plan budżetu) oraz opcje uruchamiania procesu w tle jako zadania wsadowego. W dalszej części tego artykułu opisano elementy, które mogą nie być widoczne w każdym procesie.

### <a name="actions"></a>Akcje

Dla każdego procesu generowania dostępne są trzy operacje:

-   **Tworzenie nowego planu budżetu** tworzy nowy plan z atrybutami wybieranymi w sekcji **Cel**. Te atrybuty nie muszą być niepowtarzalne. W związku z tym dwa plany mogą mieć taką samą nazwę i inne wartości.
-   **Zamiana istniejącego scenariusza planu budżetu** powoduje usunięcie wszystkich danych w docelowym planie budżetu w wybranym scenariuszu planu budżetu i utworzenie nowych wierszy z wybranego źródła danych.
-   **Aktualizowanie istniejącego scenariusza planu budżetu i dołączanie nowych danych** aktualizacje istniejące wiersze w planie docelowym, które pasują do wierszy źródła, i dodaje nowe wiersze dla nowych danych. Dopasowanie opiera się na koncie księgowym, danych, klasie budżetu i różnych innych polach. Na przykład podczas generowania planów budżetu z pozycji prognozy, numer pozycji jest ważnym polem. Wszystkie wiersze zawierające numer pozycji odpowiadający źródłowemu numerowi pozycji są zastępowane nowymi wierszami z tekstu źródłowego.

### <a name="source"></a>Źródło

Dla wszystkich procesów karta **Źródło** umożliwia filtrowanie danych za pomocą przycisku **Filtr**. Domyślnie konkretne pola są dodawane do filtra dla każdego procesu. Na przykład dla procesu **Generowanie planu budżetu na podstawie księgi głównej** dostępne są kategorie **Konto księgowe** i **Konto główne** i są widoczne na stronie generowania. Wszelkie pola dodane do filtra są również dodawane do strony razem z wszelkimi dodanymi kryteriami.

### <a name="target"></a>Wartość docelowa

Opcja **Historyczny** na karcie **Cel** umożliwia używanie dat z danych źródłowych jako dat wejścia w życie w planie budżetu. Zwykle data wejścia w życie musi się mieścić w cyklu budżetu dla planu. Jeśli opcja **Historyczne** jest ustawiona na **Tak**, używana jest data źródła (nawet jeśli jest to tylko rok), umożliwiając użycie danych przeszłości jako podstawy do porównania. Nie można modyfikować danych historycznych w planie budżetu i plan jest ustawiony przepływ pracy ze stanem zatwierdzonym. Można jednak zresetować stan, jeśli inne scenariusze w planie wymagają zmiany.

Pole **Agreguj sumę według** u góry strony określa również używaną datę. To pole sumuje kwoty i opcjonalnie ustawia datę obowiązywania na pierwszy dzień roku lub okresu obrachunkowego. 

Wiele pól na karcie <strong>Celu</strong> staje się dostępne do edycji lub tylko do odczytu, w zależności od wybranej akcji. W przypadku zmiany z tworzenia nowego planu budżetu na aktualizację istniejącego planu pole **Nazwa planu budżetu** staje się niedostępne, a dostępne stają się pola związane z wybieraniem istniejącego planu. Zarówno na karcie **Cel**, jak i **Źródło** pole **Księga** jest zawsze niedostępne, ponieważ wartość zależy od wybranego procesu planowania budżetu. 

Pole **Klasa budżetu** pozwala wybrać wiersze planu budżetu jako transakcje wydatkowe lub transakcje przychodu. Zazwyczaj transakcje przychodu stanowią kredyt na koncie księgowym i dlatego są zapisywane jako liczby ujemne. Te transakcje pojawiają się również zwykle jako kwoty ujemne w planie budżetu. Jednak po dodaniu klasy budżetu jako pola w układzie planu można włączyć wyświetlanie przychodu jako wartości dodatnich.

### <a name="generation-rules"></a>Reguły generowania

Trzy pola oferują dodatkowe funkcje : **Współczynnik**, **Minimum** i **Reguła** **zaokrąglania**. 

Wartość w polu **Współczynnik** jest mnożona przez wartość źródłową, by ustalić kwotę w planie budżetu. Następnie można wprowadzać poprawki podczas tworzenia wierszy planu budżetu. Można na przykład wpisać **1,03** dla wzrostu o 3%. Współczynnik musi być liczbą dodatnią. 

Pole **Minimum** pozwala określić kwotę progową dla tworzenia wiersza planu budżetu. Jeśli kwota źródłowa jest mniejsza od tej liczby, wiersz planu budżetu nie jest tworzony. Wartość **0,00** dopuszcza wszystkie kwoty, ale nie ogranicza wierszy do kwot dodatnich. (Żadna wartość nie ogranicza wierszy do kwot dodatnich. Kwoty ujemne są zawsze uwzględniane i zazwyczaj odpowiadają zapisom kredytowym).

Pole **Reguła zaokrąglania** pozwala ustawić dokładność tworzonych wierszy planu budżetu. Użytkownik może zaokrąglać kwoty do najbliższej wartości 1,00, 10,00, 100,00 itd. w wybranej walucie.

## <a name="notes-for-specific-processes"></a>Uwagi do konkretnych procesów
### <a name="generate-budget-plan-from-general-ledger"></a>Generowanie planu budżetu na podstawie księgi głównej

Podczas tworzenia planu budżetu z danych księgi głównej, należy ustawić w polu **Agreguj sumę według** wartość **Rok obrachunkowy**, jeśli opcja **Historyczne** jest ustawiona na **Nie**. Okresy i daty w źródle mogą być niezgodne z okresami w datach docelowych. Ponieważ w ramach procesu nie ma żadnego niezawodnego mechanizmu mapowania tych wartości, należy ograniczyć proces do pierwszego roku. 

W lokalizacji docelowej pole **Klasa budżetu** ma wartość **Wydatki** lub **Przychód**. Takie ustawienie jest używane w celu wybrania atrybutu **Typ budżetu** dla wierszy, które są tworzone, gdy konto główne w wierszu nie ma typu **Przychód** lub **Wydatki**.

### <a name="generate-budget-plan-from-fixed-assets"></a>Generowanie planu budżetu na podstawie środków trwałych

Proces **Generowanie planu budżetu na podstawie środków trwałych** nie oferuje opcji agregowania według dnia lub okresu. Nie można też ustawić planu jako historycznego. Ten proces okresowy służy do uwzględnienia przewidywanych transakcji na środkach trwałych w planowaniu budżetu.

### <a name="generate-budget-plan-from-forecast-positions"></a>Generowanie planu budżetu na podstawie pozycji prognozy

Proces **Generowanie planu budżetu na podstawie pozycji prognozy** przypisuje pozycję z prognozy źródłowej do wiersza planu budżetu. Można wyświetlić pozycję, dodając pozycję prognozy jako wiersz w układzie planu budżetu lub za pomocą zapytania **Wiersze planu budżetu**. Jeśli nie chcesz, aby stanowisko podlegającego prognozie było przypisane do wierszy planu budżetu, ustaw opcję **Uwzględnienie pozycji w wierszu planu budżetu** na **Nie**.

Wiersze w planie budżetu są agregowane według kont księgowych i pozycji. Można jednak wykluczyć numer pozycji, aby wiersze były agregowane tylko według konta księgowego. Na karcie **Cel** trzeba ustawić opcję **Uwzględnienie pozycji w wierszu planu budżetu** na **Nie**.

W polu **Scenariusz planu budżetu w przeliczeniu na pełne etaty** można wybrać scenariusz uwzględniający liczbę równoważników pełnego etatu (FTE) w planie budżetu. To pole jest ograniczone do scenariuszy typu ilościowego, które są uwzględniane w układzie docelowego planu budżetu. Wybranie scenariusza równoważnika pełnego etatu (FTE) wymaga również wybrania konta głównego FTE. To konto jest używane do tworzenia wierszy planu budżetu typu ilościowego. 

Proces planowania budżetu i scenariusz planu budżetu, wybrane w źródle, ustawiają scenariusz docelowy procesu i scenariusza planowania budżetu. Ponieważ te atrybuty są przypisane pozycji prognozy, muszą być dopasowane do planu budżetu. Dlatego te atrybuty nie mogą być zmodyfikowane w obiekcie docelowym.

### <a name="generate-budget-plan-from-project-forecasts"></a>Generuj plan budżetu na podstawie prognoz projektów

Proces **Generuj plan budżetu na podstawie prognoz projektów**, podobnie jak proces **Generowanie planu budżetu na podstawie pozycji prognozy** pozwala uwzględnić ilości projektu (godziny, wydatki i towary) w scenariuszu ilościowym. Oba procesy mają też podobne filtry dla kolumn w układzie planu budżetu. 

Na karcie **Źródło** trzy opcje w sekcji **Uwzględnij sprawozdanie** określają, które wiersze planu budżetu są tworzone. Te opcje są takie same, jak opcje dostępne podczas tworzenia wpisów do rejestru budżetu bezpośrednio na podstawie prognoz projektu. Ustaw **Zyski i straty** na **Tak**, aby utworzyć wiersze dla kosztów i przychodów. Ustaw opcję **PWT** na **Tak**, aby utworzyć wpisy pracy w toku. Ustaw opcję **Alokacja listy płac** na **Tak**, aby tworzyć wiersze dla kont przeciwstawnych dla transakcji godzinowych. 

Nie ma pola **Klasa budżetu**, ponieważ klasa budżetu (**Wydatki** lub **Przychód**) jest określana na podstawie źródła. 

Można używać budżetów projektu jako źródła przez wybraniu modelu prognozy zawierającego kwoty budżetu projektu. Należy pamiętać, że budżety projektu tworzą wpisy prognozy projektu po zatwierdzeniu.

Aby wybrać tylko koszty lub przychody dla wierszy planu budżetu, należy za pomocą filtru wybrać <strong>Aktualizacje budżetu: Typ kwoty = Koszt</strong>. Aby wybrać tylko jeden typ prognozy, należy za pomocą filtru wybrać <strong>Aktualizacje budżetu: Typ transakcji = *xxx</strong>*. 

Tylko jeden model prognozy może służyć do generowania scenariusza planu budżetu. Jeśli uruchomisz procesu dla jednego modelu prognozy, wykonasz aktualizację i spróbujesz określić inny model, pierwszy model zostanie zastąpiony, jeśli obowiązują te same konta projektu i księgowe. Aby wygenerować scenariusz planu budżetu z więcej niż jednego modelu prognozy, należy wygenerować je do różnych scenariuszy planu budżetu i użyć opcji alokacji, aby dodać je w innym scenariuszu. 

Proces **Generuj plan budżetu na podstawie prognoz projektów** również przypisuje projekt źródłowy do wiersza plan budżetu.

### <a name="generate-budget-plan-from-supply-forecast"></a>Generuj plan budżetu na podstawie prognozy dostaw

Opcje filtra źródłowego w procesie **Generuj plan budżetu na podstawie prognozy dostaw** zostały stworzone na podstawie opcji funkcji **Przeniesienie budżetu zakupów do księgi** ze względu na podobieństwa między procesem i funkcją.

### <a name="generate-budget-plan-from-demand-forecast"></a>Generuj plan budżetu na podstawie prognozy popytu

Dla procesu **Generuj plan budżetu na podstawie prognoz popytu** można ustawić opcję **Zamówienie sprzedaży** na **Tak**, aby wygenerować wiersze przychodu w planie budżetu, ustawić opcję **Konsumpcja** na **Tak**, aby utworzyć wiersze wydatków lub ustawić obie opcje na **Tak**.

### <a name="generate-budget-plan-from-budget-register-entries"></a>Generowanie planu budżetu na podstawie wpisów do rejestru budżetu

Dla procesu **Generowanie planu budżetu z wpisów do rejestru budżetu** źródło musi określać jeden model podrzędny, jeden kod budżetu i jeden numer wpisu. Innymi słowy jednocześnie można tworzyć wiersze planu budżetu tylko dla jednego wpisu rejestru budżetu. Można użyć dodatkowych wpisów w tym samym planie budżetu, uruchamiając proces raz la każdego wpisu źródła.

### <a name="generate-budget-plan-from-budget-plan"></a>Generowanie planu budżetu na podstawie planu budżetu

Dla procesu **Generowanie planu budżetu na podstawie planu budżetu** dodatkowy zestaw opcji na karcie **Cel** pozwala przypisać nowe wymiary finansowe. Po wybraniu wymiaru finansowego ta wartość będzie używana dla wszystkich wierszy planu budżetu. W związku z tym można użyć jednego planu budżetu jako podstawy dla innego planu budżetu, ale można też przypisać np. inny dział lub MPK do nowego planu budżetu.

## <a name="looking-back-from-the-budget-plan"></a>Wyszukiwanie wstecz z planu budżetu
### <a name="budget-plans-by-dimension-set-inquiry"></a>Plany budżetu na podstawie zapytania o zestaw wymiarów

Zapytanie **Plany budżetu według zestawu wymiarów** obejmują kilka opcji, które pozwalają wysyłać zapytania umożliwiające identyfikację źródła danych planu budżetu. 

Wybierz wiersz i kliknij przycisk **Wiersze planu budżetu**, aby uruchomić zapytanie **Wiersze planu budżetu**. Wyniki są filtrowane dla wartości wymiaru wybranego wiersza. Następnie można zastosować dodatkowe parametry. 

Te zapytania można wysyłać za pomocą przycisków **Prognoza podaży** i **Prognoza popytu**. W obu przypadkach zapytanie wyszukuje wierszy prognozy, które mogły utworzyć wiersze budżetu. 

Wśród raportów dodatkowych, które są dostępne, jest raport **Pozycje prognozy według planów budżetu**. Ten raport jest szczególnie przydatny do ustalania, czy alokacja pozycji do planów budżetu jest prawidłowa.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]