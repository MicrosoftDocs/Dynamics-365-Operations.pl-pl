---
title: "Tworzenie planów wynagrodzeń o zmiennej wysokości"
description: "Wynagrodzenie o zmiennej wysokości to nieregularne wynagrodzenie pracownika, takie jak premie lub akcje. Ten temat zawiera opis składników, które muszą zostać skonfigurowane, zanim będzie można używać wynagrodzenia o zmiennej wysokości i rejestrować pracowników w systemie wynagrodzeń o zmiennej wysokości."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 26ed9de01bffbcd468ac0cf1b9eb3f101707eb04
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="create-variable-compensation-plans"></a>Tworzenie planów wynagrodzeń o zmiennej wysokości

[!include[banner](includes/banner.md)]


Wynagrodzenie o zmiennej wysokości to nieregularne wynagrodzenie pracownika, takie jak premie lub akcje. Ten artykuł zawiera opis składników, które muszą zostać skonfigurowane, zanim będzie można używać wynagrodzenia o zmiennej wysokości i rejestrować pracowników w planie wynagrodzeń o zmiennej wysokości.

Obliczanie kwot wynagrodzeń o zmiennej wysokości dla pracowników może być oparte na kilku czynnikach, takich jak wydajność pracownika, poziom wynagrodzeń i wydajność działu.

## <a name="variable-compensation-components"></a>Składniki wynagrodzenia o zmiennej wysokości
### <a name="create-compensation-types"></a>Utwórz typy wynagrodzeń

**Typy wynagrodzenia o zmiennej wysokości**są wymaganym składnikiem. Typy wynagrodzenia o zmiennej wysokości umożliwiają opis rodzajów wynagrodzenia o zmiennej wysokości, które otrzymuje organizacja. Pozwalają także określić, czy wynagrodzenie będzie w gotówce czy w formie niepięniężnej, np. formie akcji.

### <a name="describe-vesting-rules"></a>Opisz reguły wypłat

Opcjonalnie firma może skonfigurować **reguł wypłat**. Reguły wypłat opisują sposób alokacji nagród o zmiennej wysokości w czasie. Na przykład reguła wypłat może zawierać informację, że pracownik będzie otrzymywać 25 procent nagrody co roku przez następne 4 lata. Reguły wypłat mają wyłącznie charakter informacyjny.

## <a name="variable-compensation-plans"></a>Systemy wynagrodzeń o zmiennej wysokości
**Plan wynagrodzeń o zmiennej wysokości** zawiera reguły, metody obliczania i domyślne wartości do obliczania wynagrodzenia o zmiennej wysokości dla zarejestrowanych pracowników. Po utworzeniu systemu wynagrodzeń o zmiennej wysokości należy ustawić typ wynagrodzenia o zmiennej wysokości. Typ wynagrodzenia o zmiennej wysokości określa, czy system oblicza kwotę w walucie, czy liczbę jednostek jako nagrody. Należy także ustawić metodę obliczania:

-   **Punkt w czasie** — Obliczenia nagrody o zmiennej wysokości opiera się na stałym wynagrodzeniu, które miał pracownik w danym dniu. Data ta jest określona w zdarzeniu procesu podczas przetwarzania nowych kwot wynagrodzenia.
-   **Złożona** — Kwota nagrody jest obliczana dla każdej stawki płacy unikatowy stałego wynagrodzenia, które miał pracownik między datą początkową cyklu a datą końcową zdarzenia procesu. Stawki są następnie dodawane w celu ustalenia końcowej nagrody. Na przykład podczas cyklu pracownik został przeniesiony do na inne stanowisko z inną płacą. W takim przypadku nagroda o zmiennej wysokości jest korygowana na podstawie czasu obowiązywania każdej stawki płacy danego pracownika.

Kwota nagrody o zmiennej wysokości może być oparta na wartości procentowej zarobków bazowych pracownika lub na ustalonej liczbie jednostek.

-   Wybierz opcję **procent podstawy**, aby wprowadzić domyślną wartość procentową i określić, czy podstawa powinna być stałą stawką płacy pracownika czy punktem kontrolnym poziomu wynagrodzenia pracownika. Poziom wynagrodzenia jest ustawiony dla zadania pracownika. Jeden z punktów odniesienia w strukturze wynagrodzeń można ustawić jako punkt kontrolny w systemie stałych wynagrodzeń. System będzie używać poziomu wynagrodzeń z zadania pracownika i odwoływać go do punktu kontrolnego wymienionego w systemie stałych wynagrodzeń tego pracownika w celu znalezienia kwoty punktu kontrolnego dla poziomu wynagrodzenia pracownika. Kwota w punkcie kontrolnym zostanie użyta zamiast stałej stawki płacy pracownika jako podstawa naliczenia nagrody.
-   Wybierz opcję**Liczba jednostek**, aby wprowadzić domyślne liczby jednostek, wartość każdej jednostki i walutę jednostki, jeśli plan wynagrodzeń dotyczy nagrody w formie niepieniężnej (np. 200 jednostek akcji wartych 40 USD), lub po prostu liczbę jednostek, jeśli plan wynagrodzeń dotyczy nagród pieniężnych. W przypadku nagród pieniężnych pracownik będzie otrzymywać określoną liczbę jednostek waluty używanej dla jego systemu stałych wynagrodzeń (na przykład 500 jednostek po 1 USD). Kontrola relacji jeden do jednego może być używana do wskazania, czy jest bezpośrednie mapowanie jeden do jednego między liczbą jednostek a wartością jednostki. W przypadku tworzenia systemu wynagrodzeń o zmiennej wysokości dla systemu opartego na gotówce przy użyciu liczby jednostek ta opcja jest automatycznie zablokowana jako **Tak**, a wartość jednostki wynosi **1,0000**.

Ustawienie **Reguła zatrudnienia** pozwala określić, czy wszyscy pracownicy powinni otrzymać taką samą podwyżkę, niezależnie od daty ich zatrudnienia (**Reguła zatrudnienia** = **Brak**), czy też pracownicy powinni otrzymywać procent nagrody w oparciu o to, przez jaki czas byli zatrudnieni w cyklu (**Reguła zatrudnienia** = **Procent**). 

**Dźwignia finansowa** umożliwia korygowanie nagrody dla pracownika na podstawie wydajności działu pracownika. Miary wydajności można ustawić dla poszczególnych działów na stronie **Działy** w menu **Powiązane formularze** &gt; **Wynagrodzenie** &gt; **Wydajność**. Nagroda, jaką pracownik otrzymuje w tym dziale, zależy od wartości w polu **Osiągnięty procent celu**, które wskazuje wydajność działu:

-   Jeśli wydajność działu wynosi 100 procent, nagroda dla pracowników z tego działu jest uzależniona od wartości procentowej ustawionej w polu **Wypłata za 100%**.
-   Jeśli wydajność działu przekracza 100%, system dodaje wartość ustawioną w polu **Na każdy 1% powyżej celu** do wartości procentowej ustawionej w polu **Wypłata za 100%**, aż do osiągnięcia wartości ustawionej w polu **Najwyższa dopuszczalna wypłata**.
-   Jeśli wydajność działu jest niższa od 100%, system odejmuje wartość ustawioną w polu **Na każdy 1% poniżej celu** od wartości procentowej ustawionej w polu **Wypłata za 100%**, aż do osiągnięcia wartości ustawionej w polu **Najniższa dopuszczalna wypłata**.

Można ustawić**poziomy tolerancji** na wartości procentowe progu, tak aby komunikat o błędzie był wyświetlany, gdy użycie dźwigni finansowej spowoduje wzrost wartości procentowej powyżej progu. 

Domyślnie system wyszukuje dział ustawiony na stanowisku pracownika, ale nagrody niektórych pracowników mogą zależeć od wydajności wielu działów. W takim przypadku różne działy i wartości procentowe nagrody przydzielane do wydajności każdego działu mogą być ustawione w rejestracji wynagrodzenia o zmiennej wysokości dla pracownika. Aby uzyskać więcej informacji, zobacz sekcję „Rejestracja wynagrodzenia o zmiennej wysokości" poniżej. 

Dźwignia finansowa jest używana tylko wtedy, gdy wybrano **Wynagrodzenie za wyniki** po uruchomieniu procesu wynagrodzenia. 

Na karcie **Zastąpienia poziomów** można zastępować domyślną wartość procentową nagrody lub liczbę jednostek na podstawie poziomu wynagrodzenia pracownika. Jeśli opcja **Włącz zastąpienia dla poziomów** jest ustawiona jako **Tak** dla pracowników zarejestrowanych w planie wynagrodzeń o zmiennej wysokości, system bierze pod uwagę poziom stanowiska pracownika, a następnie wyszukuje go w tabeli zastąpień poziomów, aby określić wartość procentową lub liczbę jednostek z karty **Ogólne**. Wartość procentową i liczbę jednostek też można zastąpić w rejestracji pracownika w systemie wynagrodzeń o zmiennej wartości.

## <a name="variable-compensation-enrollment"></a>Rejestracja wynagrodzenia o zmiennej wysokości
### <a name="determine-who-is-eligible-for-the-plan"></a>Określanie, kto może skorzystać z planu

Pierwszym krokiem podczas rejestrowania pracowników w planie wynagrodzeń o zmiennej wysokości jest określenie, kto jest uprawniony do wynagrodzenia zdefiniowanego w systemie. Do czasu określenia uprawnień nie będzie można przypisać planu do żadnego pracownika. Aby skonfigurować uprawnienia, otwórz stronę **Reguły uprawnień**. W tym miejscu można utworzyć nową regułę uprawnień dla planu wynagrodzeń i zdefiniować kryteria, które pracownik musi spełnić, aby kwalifikować się do systemu wynagrodzeń. Można ograniczyć uprawnienia na podstawie działu, związku zawodowego, regionu wynagrodzenia (lokalizacja), zadania, funkcji zadania, typu zadania lub poziomu wynagrodzenia. Pracowników można rejestrować w planie wynagrodzeń, tylko jeśli spełniają **wszystkie** warunki ustawione w regule uprawnienia. 

**Uwaga:** Reguły uprawnienia są używane do określania uprawnień zarówno dla systemów stałych jak i zmiennych wynagrodzeń. Reguła uprawnienia uwzględnia wartość następujących pól w rekordach Zadanie, Stanowisko i Pracownik, aby określić, czy pracownik jest uprawniony do planu wynagrodzeń.

-   Na stronie **Zadanie**:
    -   Pole **Zadanie**
    -   Pola **Funkcja** i **Typ stanowiska** na karcie **Klasyfikacja stanowiska**
    -   Pole **Poziom** na karcie **Wynagrodzenie**
-   Na stronie **Stanowiska**: pola **Dział** i **Region wynagrodzenia**
-   Na stronie **Pracownicy**: Informacje o związkach zawodowych powiązane z pracownikiem w menu **Informacje osobiste** &gt; **Związki zawodowe** na karcie ****Pracownik****

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Włączanie rejestracji w systemie wynagrodzeń o zmiennej wysokości

Na stronie **systemów wynagrodzeń o zmiennej wysokości** należy ustawić opcję **Włącz rejestrację** jako **Tak**, aby umożliwić rejestrację uprawnionych pracowników w systemie.

### <a name="enroll-the-employee"></a>Rejestracja pracownika

Teraz można zarejestrować pracowników w systemie wynagrodzeń o zmiennej wysokości. Aby zarejestrować pracowników, przejdź na stronę **Pracownicy**, a następnie wybierz pracownika. Następnie w okienku akcji kliknij kolejno opcje **Wynagrodzenie** &gt; **Rejestracja w planie o zmiennej wysokości**. 

**Uwaga:** **Rejestracja** musi być ustawiona jako **Tak** w systemie wynagrodzeń o zmiennej wysokości. Pole **Plan** zawiera tylko systemy, do których pracownik jest uprawniony na podstawie reguł uprawnień skonfigurowanych dla tych systemów. Jeśli reguła uprawnienia nie jest ustawiona w systemie, pracownik nie będzie uprawniony do tego systemu. 

Upewnij się, że pole **Data wejścia w życie** jest poprawnie ustawione. Jeśli system wynagrodzeń o zmiennej wysokości używa metody obliczania **Złożone**, data wejścia w życie rejestracji może być brana pod uwagę podczas obliczania nagrody dla pracownika. 

Można użyć karty **Zastąpienia**, aby zastąpić określone wartości dla pracownika. Na przykład jeśli opcja **Reguła zatrudnienia** ma wartość **Procent** w systemie i do obliczania wartości procentowych zatrudnienia pracownika mają być używane różne daty zatrudnienia, można ustawić datę zatrudnienia w polu **Dane reguły zatrudnienia**. Można także zastąpić wartość **Procent nagrody** lub wartość **Liczba jednostek** dla określonego pracownika w zależności od ustawień systemu. Te wartości będą nadal być brane pod uwagę przez regułę zatrudnienia, współczynniki wydajności i inne ustawienia w systemie. 

Opcja **Zastąpienia na poziomie organizacji** jest używana do określania nagrody dla pracownika na podstawie wydajności jednego lub kilku działów. Procent, który jest alokowany między działami, powinien mieć wartość 100 procent. Indywidualna wydajność pracownika jest również uwzględniana. Te ustawienia są używane tylko wtedy, gdy wybrano opcję **Wynagrodzenie za wyniki** podczas uruchamiania procesu wynagrodzeń.

<a name="see-also"></a>Informacje dodatkowe
--------

[Plany wynagrodzeń](compensation-plans.md)




