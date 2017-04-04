---
title: "Tworzenie planów wynagrodzeń o zmiennej wysokości"
description: "Wynagrodzenie o zmiennej wysokości to nieregularne wynagrodzenie pracownika, takie jak premie lub akcje. W tym temacie opisano elementy, które muszą być skonfigurowane przed można użyć wynagrodzenia o zmiennej wysokości i zarejestrowania danego pracownika w planie wynagrodzeń o zmiennej wysokości."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9397e84f03ee5b340fa2aa0a64e582fc0078526e
ms.openlocfilehash: be156afa73de731e54985485b617bcbae883db3a
ms.lasthandoff: 03/31/2017


---

# <a name="create-variable-compensation-plans"></a>Tworzenie planów wynagrodzeń o zmiennej wysokości

Wynagrodzenie o zmiennej wysokości to nieregularne wynagrodzenie pracownika, takie jak premie lub akcje. Ten artykuł zawiera opis składników, które muszą zostać skonfigurowane, zanim będzie można używać wynagrodzenia o zmiennej wysokości i rejestrować pracowników w planie wynagrodzeń o zmiennej wysokości.

Obliczanie kwot wynagrodzeń o zmiennej wysokości dla pracowników może być oparte na kilku czynnikach, takich jak wydajność pracownika, poziom wynagrodzeń i wydajność działu.

## <a name="variable-compensation-components"></a>Składniki wynagrodzenia o zmiennej wysokości
### <a name="create-compensation-types"></a>Utwórz typy wynagrodzeń

**Typy wynagrodzenia o zmiennej wysokości **są wymaganym składnikiem. Typy wynagrodzenia o zmiennej wysokości umożliwiają opis rodzajów wynagrodzenia o zmiennej wysokości, które otrzymuje organizacja. Pozwalają także określić, czy wynagrodzenie będzie w gotówce czy w formie niepięniężnej, np. formie akcji.

### <a name="describe-vesting-rules"></a>Opisz reguły wypłat

Opcjonalnie firma może skonfigurować **reguł wypłat**. Reguły wypłat opisują, jak nagrody o zmiennej wysokości powinna być rozdzielona na czas. Na przykład reguły wypłat może zawierać informację, że pracownik będzie otrzymywać jego lub jej kwota nagrody 25 procent rocznie przez następne cztery lata. Reguły wypłat mają wyłącznie charakter informacyjny.

## <a name="variable-compensation-plans"></a>Systemy wynagrodzeń o zmiennej wysokości
**Plan wynagrodzeń o zmiennej wysokości** zawiera reguły, metody obliczania i domyślne wartości do obliczania wynagrodzenia o zmiennej wysokości dla zarejestrowanych pracowników. Podczas tworzenia planu wynagrodzeń o zmiennej wysokości, należy ustawić typ wynagrodzenia o zmiennej wysokości. Typ wynagrodzenia o zmiennej wysokości Określa, czy system oblicza kwotę w walucie lub liczba jednostek, jako nagrody. Należy także ustawić metodę obliczania:

-   **Punkt w czasie** — obliczenia nagrody o zmiennej wysokości opiera się na stałe wynagrodzenie, które pracownik miał w określonym dniu. Czy data jest określona na zdarzenia procesowego podczas przetwarzania nowe kwoty rekompensaty.
-   **Złożona** — Kwota nagrody jest obliczana dla każdej stawki płacy unikatowy stałego wynagrodzenia, które miał pracownik między datą początkową cyklu a datą końcową zdarzenia procesu. Następnie dodaje się stawki razem do ustalenia ostatecznego nagrody. Na przykład podczas cyklu, pracownik przeniesiony w inne położenie, który miał stawka płacy różne. W takim przypadku nagroda o zmiennej wysokości jest korygowana na podstawie czasu obowiązywania każdej stawki płacy danego pracownika.

Kwota nagrody o zmiennej wysokości może być oparta na wartości procentowej zarobków bazowych pracownika lub na ustalonej liczbie jednostek.

-   Wybierz opcję **procent podstawy**, aby wprowadzić domyślną wartość procentową i określić, czy podstawa powinna być stałą stawką płacy pracownika czy punktem kontrolnym poziomu wynagrodzenia pracownika. Poziom wynagrodzenia jest ustawiony na pracownika pracy. Jeden z punktów odniesienia w strukturze wynagrodzeń można ustawić jako punkt kontrolny na stałych wynagrodzeń. System będzie używać poziomu rekompensaty od pracownika pracy i odsyłacz go z punktu kontrolnego, która jest wyświetlana na plan stałego wynagrodzenia pracownika, aby znaleźć ilość punktów kontroli dla poziomu wynagrodzenia pracownika. Ilość punktów kontroli następnie posłuży zamiast pracownika stała stawka płacy jako podstawę udzielania zamówień.
-   Wybierz opcję** Liczba jednostek**, aby wprowadzić domyślne liczby jednostek, wartość każdej jednostki i walutę jednostki, jeśli plan wynagrodzeń dotyczy nagrody w formie niepieniężnej (np. 200 jednostek akcji wartych 40 USD), lub po prostu liczbę jednostek, jeśli plan wynagrodzeń dotyczy nagród pieniężnych. Nagrody pieniężne pracownik otrzyma określoną liczbę jednostek waluty, który jest używany do jego lub jej stałych wynagrodzeń (na przykład 500 jednostek 1 USD). Relacja jeden do jednego formantu może służyć do wskazują, czy istnieje bezpośrednie mapowanie jeden do jednego między liczbą jednostek i wartość jednostki. Podczas tworzenia planu wynagrodzeń o zmiennej wysokości dla planu kasowej przy użyciu liczby jednostek, ta opcja jest automatycznie blokowany, aby **tak**, a wartość Jednostka jest **1.0000**.

**Reguły zatrudnienia** ustawienie pozwala określić, czy wszystkich pracowników powinny otrzymywać samego wzrostu, bez względu na datę ich zatrudnienia (**reguły zatrudnienia** = **Brak**), lub czy pracowników powinien otrzymać procent nagrody, który opiera się na długości ich zatrudnienia podczas cyklu (**reguły zatrudnienia** = **%**). 

**Dźwignia finansowa** pozwala dopasować wielokrotnie dla pracownika, na podstawie wydajności pracownika działu. Wskaźniki wydajności można ustawić dla każdego działu **departamentów** strony, pod **formularzy związanych**&gt;**odszkodowania**&gt;**wydajności**. Nagrody, jaki pracownicy w tym departamencie otrzymują zależy od wartości **procent do osiągnięcia celu** pole, które wskazuje wydajność tego departamentu:

-   Jeśli wydajność działu wynosi 100 procent, nagroda dla pracowników z tego działu jest uzależniona od wartości procentowej ustawionej w polu **Wypłata za 100%**.
-   Jeśli wydajność działu przekracza 100%, system dodaje wartość ustawioną w polu **Na każdy 1% powyżej celu** do wartości procentowej ustawionej w polu **Wypłata za 100%**, aż do osiągnięcia wartości ustawionej w polu **Najwyższa dopuszczalna wypłata**.
-   Jeśli wydajność działu jest niższa od 100%, system odejmuje wartość ustawioną w polu **Na każdy 1% poniżej celu** od wartości procentowej ustawionej w polu **Wypłata za 100%**, aż do osiągnięcia wartości ustawionej w polu **Najniższa dopuszczalna wypłata**.

Można ustawić** poziomy tolerancji** na wartości procentowe progu, tak aby komunikat o błędzie był wyświetlany, gdy użycie dźwigni finansowej spowoduje wzrost wartości procentowej powyżej progu. 

Domyślnie system szuka działu, który jest ustawiony na stanowisko pracownika. Jednakże nagrodę dla niektórych pracowników może zależeć od wydajności z kilku działów. W takim przypadku różnym działom i procent nagrody, jaki jest przydzielone na wykonanie każdego działu zestaw przy rejestracji wynagrodzenia o zmiennej wysokości dla pracownika. Aby uzyskać więcej informacji zobacz sekcję "rejestracji wynagrodzenia o zmiennej wysokości", który następuje. 

Dźwignia finansowa jest używana tylko wtedy, gdy wybrano **Wynagrodzenie za wyniki** po uruchomieniu procesu wynagrodzenia. 

**Przesłonięcia formatowania szczeblach** kartę pozwala zastąpić domyślny procent nagrody lub liczba jednostek, w oparciu o poziom wynagrodzenia pracownika. Jeśli **Włącz zastępuje dla poziomów** jest ustawiona na **tak** dla pracowników, którzy są zarejestrowani w planie wynagrodzeń o zmiennej wysokości, system przyjmuje poziom ze stanowiska dla pracownika, a następnie szuka go w poziomie zastępuje tabeli, aby określić procent lub liczba jednostek dla tego poziomu. Jeśli poziom nie zostanie znaleziony w poziomie zastępuje tabeli, domyślny procent lub liczba jednostek, z **ogólne** karta jest używana. Procentowy udział i liczba jednostek również może być zastąpiona przy rejestracji pracownika w planie wynagrodzeń o zmiennej wysokości.

## <a name="variable-compensation-enrollment"></a>Rejestracja wynagrodzenia o zmiennej wysokości
### <a name="determine-who-is-eligible-for-the-plan"></a>Określanie, kto może skorzystać z planu

Pierwszym krokiem podczas rejestrowania pracowników w planie wynagrodzeń o zmiennej wysokości jest określenie, kto jest uprawniony do wynagrodzenia zdefiniowanego w systemie. Do czasu określenia uprawnień nie będzie można przypisać planu do żadnego pracownika. Aby skonfigurować uprawnienia, otwórz stronę **Reguły uprawnień**. W tym miejscu można utworzyć nową regułę uprawnień dla planu wynagrodzeń i zdefiniować kryteria, które pracownik musi spełnić, aby kwalifikować się do systemu wynagrodzeń. Można ograniczyć uprawnienia na podstawie działu, związku zawodowego, regionu wynagrodzenia (lokalizacja), zadania, funkcji zadania, typu zadania lub poziomu wynagrodzenia. Pracowników można rejestrować w planie wynagrodzeń, tylko jeśli spełniają **wszystkie** warunki ustawione w regule uprawnienia. 

**Uwaga:** Reguły uprawnienia są używane do określania uprawnień zarówno dla systemów stałych jak i zmiennych wynagrodzeń. Reguła uprawnienia uwzględnia wartość następujących pól w rekordach Zadanie, Stanowisko i Pracownik, aby określić, czy pracownik jest uprawniony do planu wynagrodzeń.

-   Na stronie **Zadanie**:
    -   Pole **Zadanie**
    -   Pola **Funkcja** i **Typ stanowiska** na karcie **Klasyfikacja stanowiska**
    -   Pole **Poziom** na karcie **Wynagrodzenie**
-   Na stronie **Stanowiska**: pola **Dział** i **Region wynagrodzenia**
-   Na **pracowników** strony: informacje o związkach skojarzonego z pracownika zgodnie z **informacji osobistych**&gt;**związków zawodowych** na *** kartę pracownika ***

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Włączanie rejestracji w systemie wynagrodzeń o zmiennej wysokości

Na stronie **systemów wynagrodzeń o zmiennej wysokości** należy ustawić opcję **Włącz rejestrację** jako **Tak**, aby umożliwić rejestrację uprawnionych pracowników w systemie.

### <a name="enroll-the-employee"></a>Rejestracja pracownika

Teraz można zarejestrować pracowników w systemie wynagrodzeń o zmiennej wysokości. Aby zarejestrować pracowników, przejdź na stronę **Pracownicy**, a następnie wybierz pracownika. W okienku akcji kliknij **wynagrodzenie**&gt;**rejestracji planu o zmiennej**. 

**Uwaga:** **Rejestracja** musi być ustawiona jako **Tak** w systemie wynagrodzeń o zmiennej wysokości. **Plan** pole zawiera tylko plany, które pracownik jest uprawniony, dla, w oparciu o zasady kwalifikowania wydatków, które są ustawione dla tych planów. Jeśli reguły uprawnienia nie jest ustawiony dla planu, brak pracowników będzie kwalifikujących się do tego planu. 

Upewnij się, że **Data wejścia w życie** pole jest ustawione prawidłowo. Jeśli plan wynagrodzeń o zmiennej wysokości używa **kompozytowe** metody obliczania daty rejestracji mogą być uznane za podczas obliczania nagrody dla pracownika. 

Można użyć **zastępuje** kartę, aby zastąpić określone wartości dla pracownika. Na przykład jeśli **reguły zatrudnienia** jest ustawiona na **procent** na plan, a data zatrudnienia różnych powinna być używana podczas obliczania procentu zatrudnienia pracownika, można ustawić datę zatrudnienia w **reguły zatrudnienia** pole. Można także zastąpić albo **procent nagrody** wartość lub **liczbę jednostek** wartość dla określonego pracownika, w zależności od ustawień planu. Te wartości będą nadal być rozkładane przez reguły zatrudnienia, czynników wpływających na wydajność i innych ustawień w planie. 

**Zastąpienia na poziomie organizacji** są używane do oprzeć na wydajność jeden lub więcej wydziałów wielokrotnie dla pracownika. Wartość procentową, która jest przydzielona w wydziałach powinien mieć wartość 100 procent. Uznano również wydajności poszczególnych pracowników. Te ustawienia są używane tylko wtedy, gdy **wynagrodzenie za wyniki** jest zaznaczone, po uruchomieniu procesu wynagrodzenia.

<a name="see-also"></a>Informacje dodatkowe
--------

[Plany wynagrodzeń](compensation-plans.md)


