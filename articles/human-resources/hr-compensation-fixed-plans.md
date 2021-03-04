---
title: Tworzenie planów stałych wynagrodzeń
description: Pojęcie „stałe wynagrodzenie” odnosi się do standardowego wynagrodzenia brutto lub pensji pracownika. Ten artykuł zawiera opis składników, które muszą zostać skonfigurowane, zanim będzie można utworzyć plan stałych wynagrodzeń i zarejestrować pracowników.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompRefPointSetup, HRMCompEligibility, HRMCompEvent, HRMFixedCompPlanTable, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 15991
ms.assetid: ef8cf992-176c-4c98-9dff-6510e1eb9f1c
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 06f4a335adfc1e6f438589613efec02f92bfd756
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420084"
---
# <a name="create-a-fixed-compensation-plans"></a>Tworzenie planów stałych wynagrodzeń

Pojęcie „stałe wynagrodzenie” odnosi się do standardowego wynagrodzenia brutto lub pensji pracownika. Ten artykuł zawiera opis składników, które muszą zostać skonfigurowane, zanim będzie można utworzyć plan stałych wynagrodzeń i zarejestrować pracowników.

Można obliczyć kwoty stałych wynagrodzeń dla pracowników na podstawie czynników, takich jak wydajność, region i zwiększenia budżetu. Dynamics 365 Human Resources obsługuje wynagrodzenia etapowe, stopniowe i pasmowe.

## <a name="fixed-compensation-components"></a>Składniki wynagrodzenia o stałej wysokości
### <a name="compensation-levels"></a>Poziomy wynagrodzeń

Można użyć **poziomów wynagrodzeń** do ustawiania wynagrodzenia dla różnych zadań w celu zagwarantowania, że pracownicy, którzy posiadają te zadania, są uczciwie opłacani. Na stronie **Poziomy wynagrodzeń** można skonfigurować poziomy wynagrodzeń, które są wymagane w przypadku każdego systemu etapowego, stopniowego i pasmowego. Za pomocą przycisków **W górę** i **W dół** można ustawić poziomy we właściwej kolejności według ich typu. Poziomy wynagrodzeń dla zadania pozwalają zapewnić, że wszyscy pracownicy zatrudnieni na stanowiskach obsługujących dane zadanie są wynagradzani na tym samym poziomie.

### <a name="reference-points"></a>Punkty odniesienia

**Punkty odniesienia** to kolumny w siatce, określające zakresy wynagrodzeń dla poszczególnych poziomów. Poziom wynagrodzenia jest wierszem w siatce. Typowymi punktami odniesienia dla systemu stopniowego są minimum, środek i maksimum. Punkty odniesienia tworzy się na stronie **Konfiguracje punktów odniesienia**.

### <a name="compensation-grids"></a>Siatki wynagrodzeń

Po skonfigurowaniu poziomów i punktów odniesienia, można je łączyć, aby utworzyć **siatkę wynagrodzeń**. Na stronie **Siatka wynagrodzeń** określ informacje dotyczące siatki. Na przykład określ, do czego ma być używana projektowana siatka, z jakiego typu planem będzie używana i jakie punkty odniesienia lub kolumny są wymagane w siatce. Po zakończeniu wprowadzania tych informacji kliknij przycisk **Struktura wynagrodzeń**, aby dodać poziomy i kwoty do siatki. 

**Porada:** Użyj funkcji **Zmiany grupowe** w strukturze wynagrodzeń, aby ustawić kwoty wstępne, a następnie ustal przyrost procentowy lub kwotowy dla wszystkich poziomów lub punktów odniesienia.

### <a name="pay-frequencies"></a>Częstotliwości wypłat

**Częstotliwości wypłat** są używane do definiowania sposobu określania wynagrodzenia dla pracownika (na przykład 10 USD za godzinę, a 50 000 USD rocznie) i konwersji między stawkami godzinowymi, tygodniowymi, miesięcznymi (12 miesięcy) i rocznymi. Na przykład firmy, która obsługuje 38-godzinny tydzień pracy dla pracowników zatrudnionych według stawek godzinowych ustawia częstotliwość wypłat ze stawką godzinową 1, tygodniową 38, miesięczną 164,6666666667 i roczną 1 976. Konwersje te są używane do obliczania różnych stawek płacowych, które pojawiają się w rekordzie stałego wynagrodzenia pracownika.

## <a name="fixed-compensation-plans"></a>Systemy stałych wynagrodzeń
Można zaprojektować plan stałych wynagrodzeń, aby łączył wszystkie skonfigurowane składniki. Aby utworzyć plan stałych wynagrodzeń, otwórz stronę **Plany stałych wynagrodzeń**. W tym miejscu można wpisać nazwę i opis planu, wybrać typ planu (etap, stopień czy pasmo), wybrać częstotliwość wypłat dla stawki pracownika (godzinowej, rocznej itd.) i ustawić niektóre opcje, które kontrolują sposób przetwarzania wynagrodzeń. 

Ustawienie **Tolerancja wyjścia poza zakres** pozwala określić, jak ściśle ma być przestrzegany zakres minimalnego i maksymalnego poziomu wynagrodzeń. **Twarda** tolerancja wymaga, aby wynagrodzenie mieściło się w określonym zakresie dla danego poziomu. **Miękka** tolerancja powoduje wyświetlenie ostrzeżenia, gdy kwota wynagrodzenia wykracza poza zakres, ale zezwala na kontynuowanie. Ustawienie **Brak** dla tolerancji umożliwia wpisanie dowolnej kwoty wynagrodzenia dla pracownika bez wyświetlania ostrzeżenia ani komunikatu o błędach. 

Ustawienie **Reguła zatrudnienia** pozwala określić, czy wszyscy pracownicy powinni otrzymać taką samą podwyżkę, niezależnie od daty ich zatrudnienia (**Reguła zatrudnienia** = **Brak**), czy też pracownicy powinni otrzymywać procent nagrody w oparciu o to, przez jaki czas byli zatrudnieni w cyklu (**Reguła zatrudnienia** = **Procent**). 

**Macierz zakresu wykorzystania** jest przydatna, jeśli chcesz zmniejszyć czas zatrudnienia pracowników, aby uzyskać środek ich zakresu, lub zwiększyć czas wymagany dla pracowników do osiągnięcia maksymalnego punktu odniesienia w zakresie. Na przykład, chcesz przyznać pracownikom, którzy są w dolnych 25 procentach ich zakresu, 110 procent nagrody docelowej, a pracownikom, którzy są w górnych 25 procentach zakresu — tylko 80 procent nagrody docelowej, aby za szybko nie przekroczyli punktu maksymalnego. 

Po zdefiniowaniu podstawy planu stałych wynagrodzeń, można skonfigurować strukturę wynagrodzeń dla planu. Kliknij przycisk **Konfiguruj wynagrodzenie**. Wyświetli się okno dialogowe z suwakiem, w którym są dostępne następujące trzy opcje:

-   Utwórz nową siatkę wynagrodzeń, zaznaczając konfigurację punktów odniesienia i nadając siatce nazwę.
-   Utwórz nową siatkę wynagrodzeń, wykonując kopię istniejącej siatki, którą można użyć jako punktu wyjścia.
-   Użyj istniejącej siatki wynagrodzeń, która została już zdefiniowana. Wszystkie plany wynagrodzeń, które używają tej samej siatki, otrzymują aktualizacje, jeśli siatka jest zmieniana.

Po wybraniu opcji otwiera się strona **Struktura wynagrodzeń** i można wprowadzić zmiany w nowej lub istniejącej siatce wynagrodzeń.

## <a name="fixed-compensation-enrollment"></a>Rejestracja stałego wynagrodzenia
### <a name="determine-who-is-eligible-for-the-plan"></a>Określanie, kto może skorzystać z planu

Pierwszym krokiem podczas rejestrowania pracowników w planie stałego wynagrodzenia jest określenie, kto jest uprawniony do wynagrodzenia zdefiniowanego w planie. Do czasu określenia uprawnień nie będzie można przypisać planu do żadnego pracownika. Aby skonfigurować uprawnienia, otwórz stronę **Reguły uprawnienia**. W tym miejscu można utworzyć nową regułę uprawnień dla systemu wynagrodzeń i zdefiniować kryteria, które pracownik musi spełnić, aby kwalifikować się do systemu. Można ograniczyć uprawnienia na podstawie działu, związku zawodowego, regionu wynagrodzenia (lokalizacja), zadania, funkcji zadania, typu zadania lub poziomu wynagrodzenia. Pracowników można rejestrować w planie wynagrodzeń, tylko jeśli spełniają wszystkie warunki ustawione w regule uprawnienia. 

**Uwaga:** Reguły uprawnienia są używane do określania uprawnień zarówno dla planów stałych jak i zmiennych wynagrodzeń. 

Reguła uprawnienia uwzględnia wartość określonych pól w rekordach Zadanie, Stanowisko i Pracownik, aby określić, czy pracownik jest uprawniony do planu wynagrodzeń.

-   Na stronie **Zadanie** reguła uprawnienia bierze pod uwagę wartości następujących pól:
    -   Pole **Zadanie**
    -   Na karcie **Klasyfikacja zadania** pola **Funkcja** i **Typ zadania**
    -   Na karcie **Wynagrodzenie** pole **Poziom**
-   Na stronie **Stanowiska** reguła uprawnienia bierze pod uwagę wartości pól **Dział** i **Region wynagrodzenia**.

Reguły uprawnienia biorą również pod uwagę związki zawodowe skojarzone z pracownikiem (na stronie **Pracownicy** na karcie **Pracownik** kliknij kolejno opcje **Informacje osobiste** &gt; **Związki zawodowe**).

### <a name="define-fixed-compensation-actions"></a>Definiowanie akcji związanych ze stałym wynagrodzeniem

**Akcje związane ze stałym wynagrodzeniem** są używane podczas konfigurowania lub stosowania zmian stałego wynagrodzenia pracownika. Akcje związane ze stałym wynagrodzeniem pozwalają nadać opisową nazwę typom akcji, które mogą być wykonywane przez menedżera ds. wynagrodzeń i świadczeń. Różne typy akcji opierają się na określonej logice, więc mogą być używane o określonych porach. 

Na przykład podczas ustawiania stałego wynagrodzenia dla pracownika mogą być używane tylko akcje typu **Zatrudnienie/ponowne zatrudnienie**. W takim przypadku można utworzyć trzy różne akcje typu **Zatrudnienie/ponowne zatrudnienie** i nadać im nazwy **Zatrudnienie**, **Ponowne zatrudnienie** i **Przeniesieni**. Następnie można utworzyć bardziej opisowe wyjaśnienie, dlaczego stałe wynagrodzenie zostało przyznane pracownikowi lub zmienione.

### <a name="enroll-the-employee"></a>Rejestracja pracownika

Teraz można przypisać pracownika do planu stałych wynagrodzeń. Otwórz stronę **Pracownicy** i wybierz pracownika, których chcesz zarejestrować w planie wynagrodzeń. W okienku akcji kliknij kolejno opcje **Wynagrodzenie** &gt; **Plan stałych wynagrodzeń**. Teraz możesz utworzyć nową akcję stałego wynagrodzenia dla tego pracownika. 

**Uwaga:** pole planu wynagrodzeń zawiera tylko plany dla pracownika, który może skorzystać z planu zgodnie z regułami uprawnień określonymi dla każdego planu. Jeśli nie skonfigurowano żadnej reguły uprawnienia w planie, żaden pracownik nie będzie uprawniony do tego planu. 

System sprawdza, czy kwota wynagrodzenia określona dla planu wynagrodzeń typu stopniowego lub pasmowego mieści się zakresie wyznaczonym przez maksymalne i minimalne punkty odniesienia dla danego poziomu wynagrodzeń w zadaniu pracownika. Jeśli kwota wynagrodzenia jest spoza dozwolonym zakresem, pojawia się ostrzeżenie lub komunikat o błędzie w zależności od poziomu tolerancji ustawionego w planie stałych wynagrodzeń.



[!INCLUDE[footer-include](../includes/footer-banner.md)]