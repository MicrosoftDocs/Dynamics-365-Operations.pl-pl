---
title: "Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji"
description: "W tym temacie opisano sposób używania szablonów pracy i dyrektyw lokalizacji do określania, jak i gdzie praca jest wykonywana w magazynie."
author: perlynne
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4428613441424c81f4fd7dd92bbf842c62ce860
ms.openlocfilehash: 74e7c36fb912f35252d6e40d17477ac2962cbc23
ms.contentlocale: pl-pl
ms.lasthandoff: 09/22/2018

---

# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób używania szablonów pracy i dyrektyw lokalizacji do określania, jak i gdzie praca jest wykonywana w magazynie.

Instrukcje otrzymywane przez pracowników magazynu na urządzeniu przenośnym są określane w szablonach pracy konfigurowanych w programie Microsoft Dynamics 365 for Finance and Operations w celu zdefiniowania różnych procesów i zadań magazynowych. Szablony pracy określają, jak wykonywana jest praca dla każdego procesu magazynowego. Połączenie dyrektywy lokalizacji z szablonem pracy pomaga zagwarantować, że praca ma miejsce w określonych obszarach fizycznych magazynów.

## <a name="work-templates"></a>Szablony pracy
Strona **Szablony pracy** pozwala zdefiniować operacje pracy, które muszą być wykonane w magazynie. Zwykle operacje pracy w magazynie składają się z dwóch działań: pracownik magazynu odbiera dostępny towar w lokalizacji, a następnie odkłada odebrany towar w innej lokalizacji. 

Szablony pracy składają się z nagłówka i skojarzonych z nim wierszy. Każdy szablon pracy dotyczy określonego *typu zlecenia*. Wiele typów zleceń jest skojarzonych z dokumentami źródłowymi, takimi jak zamówienia zakupu lub sprzedaży. Jednak inne typy zleceń reprezentują odrębne czynności magazynowe, takie jak inwentaryzacja ciągła. *Identyfikator puli pracy* umożliwia organizowanie pracy w grupy. 

Ustawienia w definicji nagłówka pracy mogą służyć do określania, czy ma być tworzony nowy element pracy. Można na przykład ustawić maksymalną liczbę wierszy pobrania i maksymalny oczekiwany czas pobrania. Następnie, jeśli praca dla procesu odbioru zamówienia sprzedaży przekroczy którąś z tych wartości, ta praca jest dzielona na dwa fragmenty pracy. 

Wiersze pracy odpowiadają fizycznym zadaniom, które wymagane do przetworzenia pracy. Na przykład dla procesu magazynu wyjściowego może być wiersz pracy dla odbierania towarów w magazynie i inny wiersz do odkładania tych elementów w obszaru przygotowania wysyłki. Kolejny wiersz może dotyczyć odbioru towarów z obszaru przygotowania wysyłki, a jeszcze inny ładowania towarów na ciężarówkę w ramach procesu załadunkowego. Można ustawić *kod dyrektywy* w wierszach szablonu pracy. Kod dyrektywy jest połączony z dyrektywą lokalizacji i pomaga zagwarantować, że praca magazynu jest przetwarzana w odpowiednim miejscu w magazynie. 

Za pomocą specjalnego zapytania można kontrolować sposób używania określonego szablonu pracy. Można na przykład można ustawić ograniczenie, aby dany szablon był używany tylko dla pracy w danym magazynie. Można też mieć kilka szablonów do tworzenia pracy dla przetwarzania wychodzących zamówień sprzedaży w zależności od źródła sprzedaży. Za pomocą pola **Numer sekwencyjny** system określa porządek oceniania dostępnych szablonów pracy. Dlatego bardzo szczegółowe zapytania dotyczące konkretnego szablonu pracy powinny mieć niski numer kolejny. Takie zapytani jest wtedy oceniane przed innymi, które są ogólniejsze. 

Aby zatrzymać lub wstrzymać proces pracy, można użyć ustawienia **Zatrzymanie pracy** w wierszu pracy. W takim przypadku pracownik, który wykonuje pracę, nie będzie musiał wykonywać następnego kroku wiersza pracy. Aby przejść do następnego kroku, ten lub inny pracownik musi wybrać pracę ponownie. Można też oddzielić zadania w ramach danej pracy przy użyciu różnych *identyfikatorów klasy pracy* w wierszach szablonu pracy.

## <a name="location-directives"></a>Dyrektywy lokalizacji
Dyrektywy lokalizacji to zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego. Na przykład w ramach transakcji zamówienia sprzedaży, dyrektywa lokalizacji określa, gdzie towary zostaną pobrane i gdzie zostaną umieszczone pobrane zapasy. Dyrektywy lokalizacji składają się z nagłówka i skojarzonych z nim wierszy. Tworzy się je na stronie **Dyrektywy lokalizacji**. 

W nagłówku każda dyrektywa lokalizacji musi być skojarzona z *typem zlecenia* określającym rodzaj transakcji magazynowej, dla którego dyrektywa będzie używana, np. zamówienia sprzedaży, uzupełnienia zapasów czy pobranie surowca. *Typ pracy* określa, czy dyrektywa lokalizacji będzie używana do pobierania lub odkładania pracy czy jakiegoś innego procesu magazynu, np. liczenie czy zmiany stanu zapasów. Należy także określić *oddział* i *magazyn*. *Kod dyrektywy* określony w nagłówku może służyć do łączenia dyrektywy lokalizacji w jeden lub kilka szablonów pracy. 

W przypadku szablonów pracy można skonfigurować kwerendę do określania, kiedy dana dyrektywa lokalizacji jest używana. Na przykład można określić, że jeśli źródłem zamówienia sprzedaży jest e-commerce, zapasy muszą zostać odebrane dedykowanego obszaru w magazynie. Za pomocą pola **Numer sekwencyjny** system określa porządek oceniania dostępnych dyrektyw lokalizacji. 

Wiersze dyrektywy lokalizacji określają dodatkowe ograniczenia dotyczące stosowania reguł znajdowania lokalizacji. Można określić ilość minimalną i maksymalną, do której ma się stosować dyrektywa, i można określić, że dyrektywa powinna być skojarzona z konkretną jednostką magazynową. Na przykład, jeśli jednostką miary jest paleta, tylko towary na paletach można umieścić w określonej lokalizacji. Można też określić, czy ilość może być dzielona pomiędzy wiele lokalizacji. Podobnie jak w przypadku nagłówka dyrektywy każdy wiersz dyrektywy lokalizacji ma numer kolejny, który określa porządek, w jakim wiersze są oceniane. 

Dyrektywa lokalizacji ma jeden dodatkowy poziom szczegółowości: *działania dyrektywy lokalizacji*. Można określić wiele działań dyrektywy lokalizacji dla każdego wiersza. I znowu numer kolejny jest używany do określania porządku oceniania działań. Na tym poziomie można skonfigurować zapytanie do określenia sposobu znajdowania najlepszej lokalizacji w magazynie. Można też znaleźć optymalną lokalizację przy użyciu predefiniowanego ustawienia **Strategia**.

## <a name="location-directives-configuration-details"></a>Szczegóły konfiguracji dyrektyw lokalizacji 

 ### <a name="sequence-number"></a>Numer sekwencyjny
 
Ta liczba wskazuje kolejność przetwarzania dyrektywy lokalizacji dla wybranego typu zamówienia. Można ją zmienić za pomocą strzałek **Przenieś w górę** i **Przenieś w dół** w menu.
 
 ### <a name="work-type"></a>Typ pracy
 
To jest typ pracy do wykonania. Dostępny typ pracy zależy od typu transakcji magazynowej wybranej w polu **Typ zlecenia**.
-   **Odłożenie** — typ pracy **Odłożenie** oznacza, że dyrektywa lokalizacji znajdzie najbardziej idealną lokalizację do umieszczenia zapasu lub znalezienia zapasu wchodzącego do systemu z obszaru przyjęcia, produkcji lub korekt magazynowych. Może również służyć do zdefiniowania odłożenia do lokalizacji pośredniej lub do lokalizacji końcowej wysyłki przy bramie dokowej.
-   **Pobranie** — typ pracy **Pobranie** oznacza, że magazyn znajdzie najbardziej idealną lokalizację, z której mają być fizycznie rezerwowane zapasy (w celu wykonania pracy). Pobranie można zrealizować (wiersz pracy pobrania może być zamknięty), nawet jeśli praca nie jest wykonywana. Użytkownik może wykonać fizyczne pobranie, które jest krokiem pobrania. Użytkownik może następnie anulować z urządzenia przenośnego i wykonać pracę później. Jednak po ukończeniu końcowego odłożenia nagłówek pracy jest zamykany. 
-   **Inwentaryzacja, Korekty, Niestandardowe, Zmiana stanu zapasów, Tworzenie numeru identyfikacyjnego, Drukowanie, Zmiana stanu, Pakowanie do zagnieżdżonych numerów identyfikacyjnych** — te typy pracy nie są wykorzystywane w żadnej konfiguracji dyrektyw lokalizacji. Jest to element stałotekstowy, więc z typem zlecenia pracy nie jest połączone żadne filtrowanie. 

### <a name="directive-code"></a>Kod dyrektywy

Umożliwia wybranie kodu dyrektywy, który ma zostać skojarzony z szablonem pracy lub szablonem uzupełnienia zapasów. W formularzu **Kod dyrektywy** można utworzyć nowe kody, które będą używane do łączenia szablonu pracy, szablonu uzupełniania zapasów i dyrektywy lokalizacji. Kody mogą również służyć do tworzenia połączeń między wierszami szablonu pracy i dyrektywą lokalizacji (np. bramy dokowej lub lokalizacji przejściowej).

Zauważ, że jeśli ustawiono kod, podczas generowania pracy system nie będzie przeszukiwał dyrektyw lokalizacji po kolei, ale poszuka kodu dyrektywy. Oznacza to, że można być bardziej dokładnym w określaniu, który szablon lokalizacji jest wykorzystywany w określonym kroku w szablonie pracy, na przykład na etapie przygotowywania materiałów. 

### <a name="site"></a>Witryna

Pole Oddział jest wymagane, ponieważ dyrektywa lokalizacji potrzebuje oddziału oraz powiązanego z nim magazynu. 

### <a name="warehouse"></a>Magazyn

Pole Magazyn jest wymagane, ponieważ dyrektywa lokalizacji potrzebuje oddziału oraz powiązanego z nim magazynu.

### <a name="multiple-sku"></a>Wiele jednostek JSZ

Ta opcja pozwala używać wielu jednostek magazynowych (SKU) w lokalizacji, takiej jak brama dokowa. W przypadku wybrania opcji **Wiele jednostek JSZ** lokalizacja odłożenia będzie określona w pracy (co jest oczekiwane), ale będzie w stanie obsługiwać tylko odłożenia wielu towarów (jeżeli praca obejmuje różne SKU do pobrania i odłożenia, a nie odłożenie jednej SKU). Jeżeli nie wybierzesz opcji **Wiele jednostek JSZ**, lokalizacja odłożenia będzie określana tylko wtedy, gdy odłożenie obejmuje tylko jeden rodzaj SKU. Aby używać obu akcji, należy określić dwa wiersze: po jednym z włączoną i wyłączoną opcją wielu jednostek SKU. Te wiersze muszą mieć tę samą strukturę i konfigurację. Dla operacji odłożenia potrzeba dyrektyw lokalizacji, które są identyczne, nawet jeśli w pracy o danym identyfikatorze nie jest stosowane rozróżnianie między zdefiniowaniem jednej a wielu jednostek SKU. Trzeba również skonfigurować pobranie, jeśli zamówienie opiewa na więcej niż jeden towar.

### <a name="sequence-number"></a>Numer sekwencyjny

Wprowadź kolejność przetwarzania wierszy dyrektywy lokalizacji dla wybranego typu pracy. W razie potrzeby kolejność można zmienić za pomocą przycisków **Przenieś w górę** i **Przenieś w dół**.

### <a name="fromto-quantity"></a>Od/Do ilości

Ta opcja umożliwia określenie zakresu ilości dla sytuacji, gdy trzeba wybrać kolejność wewnątrz siatki. Zakres Od/Do można określić dla ilości w odnośnej jednostce.

### <a name="unit"></a>Jednostka

Można określić ilość minimalną i maksymalną, do której ma się stosować dyrektywa, i można określić, że dyrektywa powinna być skojarzona z konkretną jednostką magazynową. Pole Jednostka w wierszu jest używane tylko do oceny ilości.

Sprawdzanie, czy wiersz dyrektywy lokalizacji ma zastosowanie, będzie się opierać na ilości w odnośnej jednostce określonej w wierszu dyrektywy lokalizacji. Każdorazowo po dotarciu do wiersza dyrektywy lokalizacji system będzie próbował przekonwertować jednostkę popytu na jednostkę określoną w wierszu. Jeśli konwersja jednostki miary nie istnieje, system przejdzie do następnego wiersza. 

### <a name="locate-quantity"></a>Zlokalizuj ilość

Ta opcja służy tylko do odkładania/znajdowania ilości w magazynie. Dotyczy wyłącznie typu pracy Odłożenie. Prawidłowe wartości:

-   **Ilość pod numerem identyfikacyjnym** — podczas oceniania, czy ilość mieści się w zakresie ilości „Od” i „Do”, jest używana ilość z przyjmowanej dostawy o numerze identyfikacyjnym.
-   **Ilość w jednostkach** — podczas oceniania, czy ilość mieści się w zakresie ilości „Od” i „Do”, jest używana ilość wyrażana w jednostkach w określonej transakcji.
-   **Pozostała ilość** — podczas oceniania, czy ilość mieści się w zakresie ilości „Od” i „Do”, jest używana ilość pozostała do otrzymania na podstawie aktualnie ewidencjonowanego wiersza zamówienia zakupu.
-   **Oczekiwana ilość** — podczas oceniania, czy ilość mieści się w zakresie ilości „Od” i „Do”, jest używana ilość łączna ilość z wiersza zamówienia zakupu, niezależnie od ilości już otrzymanej.

### <a name="restrict-by-unit"></a>Ogranicz według jednostki

Ta opcja pozwala ustawić wiersz dyrektywy lokalizacji jako specyficzny dla jednostki miary lub wielu jednostek miary. Jeśli podczas rezerwowania ilości chcesz zarezerwować palety tylko z określonego zbioru lokalizacji, to kolejność wewnątrz siatki spowoduje ograniczenie konkretnie używanej kolejności do wartości „PL”, tak aby wszelkie ilości mniejsze niż paleta nie były uwzględniane. Wybierz opcję **Ogranicz według jednostki**, aby skonfigurować jednostki. Można również ograniczyć wiersz do więcej niż jednej jednostki. Ta funkcja działa tylko w przypadku dyrektyw lokalizacji typu Pobranie. 

### <a name="round-up-to-unit"></a>Zaokrąglij do jednostki

To pole to jest powiązane z polem **Ogranicz według jednostki**. Jeśli wiersz dyrektywy lokalizacji **Ogranicz według jednostki** ma wartość „Skrzynka”, to zaznaczenie opcji **Zaokrąglij do jednostki** wskazuje, że praca pobrania surowca wygenerowana na podstawie dyrektywy powinna być zaokrąglana do wielokrotności jednej jednostki załadunkowej (określonej w polu **Ogranicz według jednostki**). Zauważ, że ten mechanizm działa tylko dla pobrań surowca i tylko dla dyrektyw lokalizacji o typie Pobranie.

### <a name="locate-packing-qty"></a>Zlokalizuj ilość w paczce

Jeśli określono ilość w paczce w zamówieniu sprzedaży, zamówieniu przeniesienia lub zleceniu produkcyjnym, nakłada to na system ograniczenie umożliwiające wybieranie tylko lokalizacji mających opcję ilości w paczce. Ta funkcja działa tylko w przypadku dyrektyw lokalizacji typu Pobranie.

### <a name="allow-split"></a>Zezwalaj na podział

To określa, czy dyrektywa lokalizacji może dzielić ilość przyjmowaną lub rezerwowaną między wiele lokalizacji w magazynie albo czy w celu utworzenia pracy cała ilość musi zostać znaleziona w jednej lokalizacji lub rezerwowana z jednej lokalizacji. 

### <a name="sequence-number"></a>Numer sekwencyjny

Ta liczba określa kolejność przetwarzania dyrektywy lokalizacji dla wybranego typu pracy. Można zmienić taką sekwencję, jeśli trzeba. Jednak podczas używania numeracji należy zachować ostrożność, ponieważ przetwarzanie zawsze odbywa się w ustawionej kolejności. 

### <a name="name"></a>Nazwisko

Umożliwia nazwanie działania w dyrektywie lokalizacji. Pamiętaj, aby utworzyć precyzyjną nazwę.

### <a name="fixed-location-usage"></a>Użycie stałej lokalizacji 

-   **Lokalizacje stałe i niestałe** — dyrektywa lokalizacji będzie brać pod uwagę wszystkie lokalizacje.
-   **Tylko stałe lokalizacje dla produktu** — dyrektywa lokalizacji będzie brać pod uwagę tylko stałe lokalizacje dla produktów.
-   **Tylko stałe lokalizacje dla wariantu produktu** — dyrektywa lokalizacji będzie brać pod uwagę tylko stałe lokalizacje dla wariantów produktów.

### <a name="allow-negative-inventory"></a>Pozwól na ujemny poziom zapasów

Wybierz tę opcję, aby w dyrektywach lokalizacji zezwolić na ujemny poziom zapasów w określonej lokalizacji magazynowej. 

### <a name="batch-enabled"></a>Partia włączona 

Zaznaczenie tej opcji umożliwia wykorzystanie strategii wsadowych dla towarów, które obsługują operacje wsadowe. Jeżeli nastąpi dojście do wiersza, który w opcji **Obsługa partii** ma ustawiony towar partii Brak, proces przejdzie do następnego wiersza działania. 

### <a name="strategy"></a>Strategia

-   **Konsolidacja** — ta strategia jest używana do konsolidacji towarów w określonej lokalizacji, gdy podobne towary są już dostępne. Ta funkcja działa tylko w przypadku dyrektyw lokalizacji typu Odłożenie. Popularna konfiguracja odłożenia polega na konsolidowaniu w pierwszym wierszu działania, a następnie w drugim wierszu próbowaniu wykonania odłożenia bez konsolidacji. Konsolidowanie towarów usprawnia późniejsze pobieranie.
-   **Dopasuj ilość opakowań** — ta strategia służy do sprawdzania, czy lokalizacja pobrania ma określoną ilość w paczce. Ta funkcja działa tylko w przypadku dyrektyw lokalizacji typu Pobranie. 
-   **Rezerwacja partii FEFO** — ta strategia jest używana, gdy zapasy są znajdowane przy użyciu daty ważności partii i przydzielane na potrzeby rezerwacji partii. Tej strategii można używać tylko dla towarów obsługujących operacje wsadowe. Ta funkcja działa tylko w przypadku dyrektywy lokalizacji dla pracy typu Pobranie. 
-   **Zaokrąglij w górę do pełnego nr id.** — ta strategia ta umożliwia zaokrąglanie ilości zapasów w górę w celu dopasowania ilości pod numerem identyfikacyjnym przypisanej do towarów, które mają zostać pobrane. Tę strategię można stosować tylko do typu uzupełniania zapasów w dyrektywie lokalizacji typu Pobranie. 
-   **Pusta lokalizacja bez przychodzącej pracy** — ta strategia jest używana do znajdowania pustych lokalizacji. Lokalizacja jest uważana za pustą, jeśli nie ma w niej fizycznych zapasów i nie ma żadnych oczekiwanych prac przychodzących. Ta strategia jest używana tylko do dyrektywy lokalizacji typu Odłożenie. 

### <a name="example-of-the-use-of-location-directives"></a>Przykład zastosowania dyrektyw lokalizacji

W tym przykładzie zostanie omówiony proces zamówienia zakupu, w którym dyrektywa lokalizacji musi znaleźć wolne zdolności produkcyjne w magazynie dla pozycji magazynowych, które zostały właśnie zarejestrowane w doku rozładunkowym. Najpierw trzeba znaleźć wolne zdolności produkcyjne w magazynie poprzez konsolidację z istniejącymi zapasami dostępnymi. Jeśli konsolidacja jest niemożliwa, trzeba znaleźć pustą lokalizację. 

W tym scenariuszu należy zdefiniować dwa działania dyrektywy lokalizacji. Pierwsze działanie w sekwencji musi wykorzystywać strategię **Konsolidacja**, a drugie powinno używać strategii **Pusta lokalizacja bez przychodzącej pracy**. O ile nie zdefiniowano trzeciego działania dla scenariusza przepełnienia, możliwe są dwa wyniki, jeśli w magazynie nie ma więcej zdolności produkcyjnych: praca może być tworzona nawet bez definiowania lokalizacji lub proces tworzenia pracy może się nie powieść. Wynik jest określany według ustawień na stronie **Błędy dyrektyw lokalizacji**, gdzie można wybrać opcję **Zatrzymaj pracę przy błędzie dyrektywy lokalizacji** dla każdego typu zlecenia.

