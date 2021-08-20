---
title: Marginesy bezpieczeństwa
description: W tym temacie opisano, jak marginesy bezpieczeństwa mogą być używane z dodatkiem Optymalizacja planowania dla rozwiązania Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 09/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-9-14
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 52740246f745272f238ec3dcf8e53f7310e4b24271da4a5d6388a1b9c4706521
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774856"
---
# <a name="safety-margins"></a>Marginesy bezpieczeństwa

[!include [banner](../../includes/banner.md)]

W tym temacie opisano, jak marginesy bezpieczeństwa mogą być używane z dodatkiem Optymalizacja planowania dla rozwiązania Microsoft Dynamics 365 Supply Chain Management.

## <a name="safety-margins-overview"></a>Przegląd marginesów bezpieczeństwa

Marginesy bezpieczeństwa umożliwiają włączenie konfiguracji, która zapewnia pewien czas bufora poza normalnym czasem realizacji. Jeśli na przykład materiał musi zostać rozpakowany lub zbadany po odebraniu od dostawcy, nie można dodać dodatkowego czasu do czasu realizacji zakupu, ponieważ takie podejście da dodatkowy czas bufora tylko dostawcy. W tym przykładzie można użyć marginesu przychodu, aby upewnić się, że dostawca dostarczy wcześniej. Ta metoda zapewnia odpowiednią ilość czasu, dzięki czemu towary mogą być wewnętrznie przetworzone.

Istnieją trzy typy zamówień marginesów bezpieczeństwa:

- **Zapas czasu dla ponownego zamówienia** — czas do umieszczenia w zleceniu dostawy
- **Zapas czasu dla przyjęcia** — czas na potrzeby obsługi dostaw przychodzących
- **Zapas czasu dla wydania** — czas na obsługę wysyłek

Na poniższej ilustracji przedstawiono sposób stosowania tych marginesów bezpieczeństwa w czasie.

![Marginesy bezpieczeństwa.](media/safety-margins-1.png)

Wszystkie marginesy są definiowane w dniach. Domyślna wartość *0* (zero) oznacza, że nie jest używany żaden margines. W przypadku skonfigurowania wielu marginesów wszystkie one będą się sumować do łącznego czasu od daty *złożenia zamówienia* do *daty zapotrzebowania*. Na przykład konfiguracja nie ma czasu realizacji, a wszystkie trzy typy marginesu są ustawione na jeden dzień. W takim przypadku będą potrzebne trzy dni między datą zamówienia a datą zapotrzebowania, więc jeśli datą zamówienia jest 1 lipca, datą zapotrzebowania będzie 4 lipca.

### <a name="receipt-margin"></a>Zapas czasu dla przyjęcia

Zapas czasu dla przyjęcia jest prawdopodobnie najbardziej używanym z trzech dostępnych marginesów. Jest on stosowany względem *daty dostawy* — wstecz względem *daty zapotrzebowania*. Innymi słowy, produkty powinny zostać odebrane w ciągu określonej liczby dni w zapasie czasu dla przyjęcia, zanim staną się dostępne.

Poniższa ilustracja przedstawia ten proces.

![Zapas czasu dla przyjęcia.](media/safety-margins-2.png)

Zapas czasu dla przyjęcia jest zazwyczaj używany jako bufor w celu zapewnienia czasu na potrzeby rejestracji w magazynie lub innych procesów czasochłonnych, które nie są częścią ogólnego czasu realizacji w systemie. W przypadku zakupów jedną z korzyści jest to, że *Data dostawy* zamówienia zakupu jest odpowiednio przenoszona do przodu. W przypadku zwiększenia czasu realizacji zamiast używania marginesu bezpieczeństwa, dostawca musiałby dostarczyć towar w ostatnim możliwym przedziale czasowym.

Należy zauważyć, że zapas czasu dla przyjęcia nie zmienia *daty zapotrzebowania* na dostawę. W związku z tym zapas czasu dla przyjęcia nie jest bezpośrednio widoczny, gdy są porównywane daty zapotrzebowania i dostarczenia (na przykład na **Wymagania netto**). Jeśli na przykład zapas czasu dla przyjęcia jest ustawiony na 4 dni, a wiersz zamówienia zakupu jest planowany do przyjęcia w piętnastym dniu miesiąca, podczas planowania głównego zostanie obliczona skorygowana data przyjęcia w dziewiętnastym dniu miesiąca.

Należy zauważyć, że zapas czasu dla przyjęcia nie jest zastosowany, jeśli jako dostawa są używane zapasy dostępne. Wszystkie dostępne zapasy są przyjmowane natychmiast, niezależnie od momentu ich odebrania.

### <a name="reorder-margin"></a>Zapas czasu dla ponownego zamówienia

> [!NOTE]
> **Wkrótce:** Ta funkcja nie jest jeszcze obsługiwana na potrzeby planowania optymalizacji. Dopóki nie będzie obsługiwana, wszystkie wartości wprowadzone dla **Zapasu czasu dla ponownego zamówienia** będą traktowane jako *0* (zero).

Poniższa ilustracja przedstawia Zapas czasu dla ponownego zamówienia.

![Zapas czasu dla ponownego zamówienia.](media/safety-margins-3.png)

Zapas czasu dla ponownego zamówienia jest dodawany przed upływem czasu realizacji towaru dla wszystkich zamówień planowanych podczas planowania głównego. W związku z tym zapewnia on dodatkowy czas na wprowadzenie zlecenia dostawy. Jest zazwyczaj używany jako bufor w celu zapewnienia odpowiedniej ilości czasu dla procesów zatwierdzania lub innych procesów wewnętrznych, które są wymagane podczas tworzenia zleceń dostawy. Zapas czasu dla ponownego zamówienia jest umieszczany między *datą zamówienia* i *datą rozpoczęcia*.

### <a name="issue-margin"></a>Zapas czasu dla rozchodu

> [!NOTE]
> **Wkrótce:** Ta funkcja nie jest jeszcze obsługiwana na potrzeby planowania optymalizacji. Dopóki nie będzie obsługiwana, wszystkie wartości wprowadzone dla **Zapas czasu dla rozchodu odjęty od daty zapotrzebowania** będą traktowane jako *0* (zero).

Poniższa ilustracja przedstawia Zapas czasu dla rozchodu.

![Zapas czasu dla rozchodu.](media/safety-margins-4.png)

Podczas planowania głównego zapas czasu dla rozchodu jest odejmowany od daty zapotrzebowania. Pomaga to zapewnić czas na reagowanie na przychodzące zamówienia i ich wysyłanie. Ten zapas czasu jest zazwyczaj używany jako bufor w celu zapewnienia odpowiedniej ilości czasu na potrzeby wysyłek i powiązanych z nimi procesów magazynowych.

Zwróć uwagę, że w przypadku zastosowania zapasu czasu dla rozchodu daty zapotrzebowania związane z podażą i popytem są niezgodne. Zamiast tego różnią się one wartością zapasu czasu dla rozchodu, ponieważ margines rozchodu jest dodawany pomiędzy *datą zapotrzebowania* dostawy a *datą zapotrzebowania* żądania.

## <a name="set-up-safety-margins"></a>Konfiguracja marginesów bezpieczeństwa

### <a name="turn-on-safety-margins-in-feature-management"></a>Włącz marginesy bezpieczeństwa w module Zarządzanie funkcjami

Aby móc używać tej funkcji razem z optymalizacją planowania, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** _Planowanie główne_
- **Nazwa funkcji:** _Marginesy bezpieczeństwa w optymalizacji planowania_

### <a name="define-safety-margins"></a>Określenie marginesów bezpieczeństwa

Ustawienia marginesów bezpieczeństwa są elastyczne. Można je ustawiać zarówno dla *grupy zapotrzebowania*, jak i *planu głównego*. Ważne jest, aby rozumieć, że marginesy są dodawane jeden na drugi. Na przykład, margines zapasu czasu dla przyjęcia wynoszący dwa dni w grupie zapotrzebowania i trzy dni w planie głównym stworzą efektywny margines przychodu wynoszący pięć dni.

Możliwość ustawienia marginesu czasu w planie głównym może być przydatna w przypadku symulowania dłuższego czasu realizacji lub niepewności dla konkretnego planu, ale bez wpływu na planowanie dzienne.

#### <a name="coverage-group-safety-margins"></a>Grupy zapotrzebowania z marginesami bezpieczeństwa

Aby zastosować margines bezpieczeństwa do grupy zapotrzebowania, należy wykonać następujące kroki.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Grupy zapotrzebowania**.
1. W okienku listy wybierz żądaną grupę zapotrzebowania.
1. Na skróconej karcie **Inne**, w sekcji **Marginesy bezpieczeństwa w dniach** należy skorzystać z następujących pól, aby określić wymagane marginesy bezpieczeństwa (w dniach):

    - Zapas czasu dla przyjęcia dodany do daty zapotrzebowania
    - Zapas czasu dla rozchodu odjęty od daty zapotrzebowania
    - Zapas czasu dla ponownego zamówienia dodany do czasu realizacji towaru

#### <a name="master-plan-safety-margins"></a>Plany główne z marginesem bezpieczeństwa

Aby zastosować margines bezpieczeństwa do planu głównego, należy wykonać następujące kroki.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. W okienku listy wybierz żądany plan główny.
1. Na skróconej karcie **Marginesy bezpieczeństwa w dniach** należy skorzystać z następujących pól, aby określić wymagane marginesy bezpieczeństwa (w dniach):

    - Zapas czasu dla przyjęcia dodany do daty zapotrzebowania
    - Zapas czasu dla rozchodu odjęty od daty zapotrzebowania
    - Zapas czasu dla ponownego zamówienia dodany do czasu realizacji towaru

### <a name="define-whether-calculations-are-based-on-calendar-days-or-work-days"></a>Umożliwia określenie, czy obliczenia są oparte na dniach kalendarzowych, czy dniach roboczych

Można tak skonfigurować wszystkie marginesy bezpieczeństwa, aby były obliczane na podstawie dni kalendarzowych lub dni roboczych.

1. Wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Parametry planowania głównego**.
1. Na karcie **Ogólne**, w sekcji **Marginesy bezpieczeństwa w dniach** ustaw wartość w polu **Dni robocze** na *Tak*, aby obliczyć marginesy na podstawie dni roboczych. Aby obliczyć marginesy na podstawie dni kalendarzowych, należy wybrać opcję wartość *Nie*.

Na przykład kalendarz jest otwarty od poniedziałku do piątku, a następnie zamknięty w sobotę i niedzielę. Jeśli istnieje zapas czasu dla przyjęcia w postaci jednego dnia, data zapotrzebowania w poniedziałek powoduje utworzenie daty dostawy w poprzedni piątek, ponieważ sobota i niedziela nie są dniami roboczymi.

Kalendarz używany do określenia dni roboczych zależy od konfiguracji i typu dostawy. Może on być kontrolowany przez kalendarze grupy zapotrzebowania, magazyn i dostawcę.

> [!NOTE]
> Jeśli *Magazyn* nie jest częścią wymiaru zapotrzebowania (innymi słowy, planowanie jest oparte tylko na bazie *oddziału*), kalendarz magazynu nie jest używany.

System może obsługiwać konfigurację, w której zdefiniowano co najmniej jeden kalendarz. W poniższych podsekcjach opisano możliwe kombinacje, których można używać do kontrolowania wyników.

#### <a name="calendar-that-is-used-for-the-duration"></a>Kalendarz używany w trakcie czasu trwania

Zdefiniowane kalendarze kontrolują całkowity czas realizacji w dniach kalendarzowych — od daty zamówienia dostaw do daty zapotrzebowania żądania. Stosowana jest następująca prioretyzacja kalendarza:

- **Czas realizacji zakupu** — uwzględniany jest tylko kalendarz grupy zapotrzebowania.
- **Zapas czasu dla przyjęcia** — jest używany kalendarz grupy zapotrzebowania (jeśli jest zdefiniowany). W przeciwnym razie jest używany kalendarz magazynu.
- **Zapas czasu dla wydania** — jest używany kalendarz grupy zapotrzebowania (jeśli jest zdefiniowany). W przeciwnym razie jest używany kalendarz magazynu.
- **Zapas czasu dla zamówienia** — uwzględniany jest tylko kalendarz grupy zapotrzebowania.

#### <a name="calendar-that-is-used-for-the-final-date"></a>Kalendarz używany na potrzeby daty końcowej

Poniższe reguły są stosowane w celu określenia, czy silnik planowania może użyć danej daty dla danego typu daty:

- **Data przyjęcia zakupu** — jest używany kalendarz dostawcy, jeśli jest zdefiniowany. W przeciwnym wypadku jest używany kalendarz grupy zapotrzebowania (jeśli jest zdefiniowany). Jeśli żaden z tych kalendarzy nie jest zdefiniowany, używany jest kalendarz magazynu.
- **Data przyjęcia zamówienia przeniesienia** — jest używany kalendarz grupy zapotrzebowania (jeśli jest zdefiniowany). W przeciwnym razie jest używany kalendarz magazynu.
- **Data przyjęcia w zamówienia produkcji** — jest używany kalendarz grupy zapotrzebowania (jeśli jest zdefiniowany). W przeciwnym razie jest używany kalendarz magazynu.
- **Dzień złożenia zapotrzebowania** — jest używany kalendarz grupy magazynowy (jeśli jest zdefiniowany). W przeciwnym wypadku jest używany kalendarz grupy zapotrzebowania.
- **Dzień złożenia zamówienia** — kombinacja (połączenie) kalendarza grupy zapotrzebowania i kalendarza dostawcy. Oba kalendarze muszą być otwarte, aby użyć danej daty. Jeśli żaden z tych kalendarzy jest zdefiniowany, używany jest ten właśnie kalendarz.

#### <a name="calendar-setup-overview-matrix"></a>Przegląd ustawień kalendarza — macierz

Na poniższej ilustracji przedstawiono macierz, która podsumowuje, które kalendarze są stosowane w przypadku obliczania marginesów bezpieczeństwa. (Wybierz obraz, aby otworzyć jego wersję wysokiej rozdzielczości) Poniższe skróty i kolory służą do wskazania, gdzie określony jest każdy typ kalendarza:

- **Grupa zapotrzebowania (CG):** Zielona
- **Magazyn (WH):** Żółty
- **Dostawca (V):** Niebieski

[![Przegląd ustawień kalendarza — macierz.](media/safety-margins-calendar-matrix.png)](media/safety-margins-calendar-matrix-high.png)

## <a name="calculating-delays"></a>Obliczanie opóźnienia

Wszystkie trzy typy marginesów bezpieczeństwa są uwzględniane, gdy system określa, czy zamówienie jest opóźnione.

Na przykład towar ma czas realizacji o jeden dzień dłuższy, ale zapas bezpieczeństwa wynoszący trzy dni. Zamówienie sprzedaży dla tego towaru jest ustawiane jako wymagane dzisiaj. W takim przypadku opóźnienie jest obliczane jako *czas realizacji* + *zapas czasu dla przyjęcia* = cztery dni. W związku z tym, jeśli dzisiaj jest 14 sierpnia, cztery dni opóźnienia oznaczają dostawy w dniu 18 sierpnia. Na poniższej ilustracji pokazano ten przykład.

![Przykład obliczania opóźnienia.](media/safety-margins-delays.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Rozpoczęcie optymalizacji planowania](get-started.md)

[Analiza dopasowań optymalizacji planowania](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]