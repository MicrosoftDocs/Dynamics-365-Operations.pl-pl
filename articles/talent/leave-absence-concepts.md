---
title: Koncepcje urlopów i nieobecności
description: W tym temacie opisano pojęcia dotyczące urlopów i nieobecności oraz sposób określania sald czasu wolnego.
author: andreabichsel
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: ''
ms.openlocfilehash: 03e2557e29194f17a9a586470ced5b352408b07c
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898649"
---
# <a name="leave-and-absence-concepts"></a>Koncepcje urlopów i nieobecności

Pojęcia i terminy, które zostały opisane w tym temacie, mogą pomóc określić, jak pracownikowi jest przyznawany czas wolny i jak obliczane są salda czasu wolnego pracownika. Aby uzyskać więcej informacji dotyczących zarządzania urlopami, zobacz [Zarządzanie urlopami i nieobecnościami](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).

## <a name="leave-plan-details"></a>Szczegóły planu urlopowego

### <a name="start-date"></a>Rozpoczęcie

Data rozpoczęcia jest datą rzeczywistego rozpoczęcia przetwarzania. Data rozpoczęcia służy również jako data rocznicy używana do obliczania kwot przenoszonych na następny okres.

## <a name="accruals"></a>Naliczenia

Naliczenia określają, kiedy i jak często pracownikowi jest przyznawany czas wolny. Zasady dotyczące przyznawania naliczeń oraz zasady dotyczące podziału proporcjonalnego są zdefiniowane w **Naliczenia** sekcji podczas konfigurowania planu urlopów i nieobecności.

### <a name="accrual-frequency"></a>Częstotliwość naliczania

Częstotliwość naliczania określa, jak często naliczany lub przyznawany jest urlop. Dostępne są następujące opcje:

- Codziennie
- Cykl tygodniowy
- Co dwa tygodnie
- Co pół miesiąca
- Miesięcznie
- Kwartalna
- Co pół roku
- Rocznie
- Brak

### <a name="accrual-period-basis"></a>Podstawa okresu naliczania

Podstawa okresu naliczania określa datę używaną do obliczania okresów naliczania. Dostępne są następujące opcje:

- **Data początkowa planu**
- **Data specyficzna dla pracownika** — kiedy ta opcja jest zaznaczona, wartość określa źródło daty początkowej, która jest używana do obliczania okresów naliczania. Dostępne są następujące opcje:

    - Niestandardowy
    - Rocznica
    - Pierwotna data zatrudnienia
    - Data stażu pracy
    - Skorygowana data rozpoczęcia pracownika
    - Data rozpoczęcia pracownika

### <a name="accrual-award-date"></a>Data przyznania naliczenia

Rzeczywista data przyznania naliczenia określa, kiedy pracownikowi jest przyznawany czas wolny. Dostępne są następujące opcje:

- **Data zakończenia okresu naliczania** — pracownikowi zostanie przyznany czas wolny ostatniego dnia okresu przyznawania.

    Aby naliczyć poprawną kwotę, proces naliczania musi obejmować cały okres. Na przykład okres naliczania jest od 1 stycznia 2018 do 31 stycznia 2018. W takim przypadku, aby styczeń został uwzględniony, naliczenie musi trwać do 1 lutego 2018.

- **Data rozpoczęcia okresu naliczania** — pracownikowi zostanie przyznany czas wolny pierwszego dnia okresu przyznawania.

### <a name="accrual-policy-on-enrollment"></a>Zasady dotyczące naliczania przy rejestracji

Zasada naliczania przy rejestracji definiują sposób obliczania naliczeń, gdy pracownik zostanie zarejestrowany w trakcie okresu naliczania. Dostępne są następujące opcje:

- **Proporcjonalna** — zakres dat między datą początkową i datą rejestracji jest używana do określania różnicy w dniach. Ta różnica jest stosowana podczas przetwarzania naliczeń.
- **Pełne naliczenia** — pełna kwota naliczeń w oparciu o warstwę jest przyznawana podczas wstępnego przetwarzania naliczania.
- **Bez naliczenia** — żadne naliczenie nie jest przyznawane aż do rozpoczęcia następnego okresu naliczania.

### <a name="accrual-policy-on-unenrollment"></a>Zasady dotyczące naliczania przy wyrejestrowaniu

Zasada naliczania przy wyrejestrowaniu definiują sposób obliczania naliczeń, gdy pracownik zostanie wyrejestrowany w trakcie okresu naliczania. Dostępne są następujące opcje:

- **Proporcjonalna** — zakres dat między datą początkową i datą rejestracji jest używana do określania różnicy w dniach. Ta różnica jest stosowana podczas przetwarzania naliczeń.
- **Pełne naliczenia** — pełna kwota naliczeń w oparciu o warstwę jest przyznawana podczas wstępnego przetwarzania naliczania.
- **Bez naliczenia** — żadne naliczenie nie jest przyznawane aż do rozpoczęcia następnego okresu naliczania.

## <a name="accrual-schedule"></a>Harmonogram naliczania

Harmonogram naliczania określa sposób naliczania czasu wolnego przez pracownika oraz jakie kwoty zostaną temu pracownikowi naliczone i przeniesienie na następny okres. Można tworzyć warstwy, dzięki którym czas wolny jest przyznawany na podstawie różnych poziomów.

### <a name="months-of-service"></a>Miesiące zatrudnienia

Wartość **Miesiące usługi** definiują minimalną liczbę miesięcy, które pracownicy muszą przepracować, aby mieć prawo do naliczeń. Jeśli nie ustalono minimum niezbędnego dla pracowników, ustaw wartość na **0**.

### <a name="hours-worked"></a>Przepracowane godziny

Wartość **Przepracowane godziny** definiują minimalną liczbę godzin, które pracownicy muszą przepracować w okresie naliczania, aby mieć prawo do naliczeń. Jeśli nie ustalono minimum niezbędnego dla pracowników, ustaw wartość na **0**.

### <a name="accrual-amount"></a>Kwota naliczenia

Kwota naliczeń jest liczb ą godzin lub dni, które zostaną naliczone pracownikom według okresu. Okres zależy od częstotliwości naliczania.

### <a name="minimum-balance"></a>Minimalne saldo

Wartość ujemna może zostać użyta w przypadku minimalnego salda, jeśli pracownicy mogą zażądać więcej urlopu niż mają dostępnego.

### <a name="maximum-carry-forward"></a>Maksymalne przeniesienie na następny okres

Proces naliczania dostosuje salda urlopów przekraczające maksymalne saldo przeniesienia na następny okres w rocznicą daty rozpoczęcia.

### <a name="grant-amount"></a>Kwota dotacji

Kwota dotacji jest początkową liczbą godzin lub dni, które pracownicy otrzymują, gdy po raz pierwszy zarejestrują się w planie urlopów. Kwota nie jest naliczana dla każdego okresu naliczania.

## <a name="enrollments-and-balances"></a>Rejestracje i salda

### <a name="enrollment-date"></a>Data rejestracji

Data rejestracji określa, kiedy pracownik może rozpocząć naliczanie czasu wolnego. Na przykład, jeśli pracownik zostanie zarejestrowany w systemie urlopowym 15 czerwca 2018, nie może naliczać czasu przed 15 czerwca 2018.

### <a name="current-balance"></a>Bieżące saldo

Bieżące saldo jest czasem urlopu, który jest dostępny dla żądań czasu wolnego. Ta wartość obejmuje naliczenia, zatwierdzone wnioski oraz dostosowania względem bieżącej daty.

### <a name="current-balance-examples"></a>Przykłady salda bieżącego

#### <a name="annual-plan"></a>Plan roczny

**Konfiguracja planu**

| Data początkowa planu | Data rejestracji | Częstotliwość naliczania | Podstawa okresu naliczania | Data przyznania naliczenia    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Roczny            | Data początkowa planu      | Koniec okresu naliczania |

Naliczenia są przetwarzane 1 stycznia 2019 (1/1/2019), dlatego uwzględniany jest cały okres.

**Wyniki**

| Kwota naliczenia | Minimalne saldo | Maksymalne przeniesienie na następny okres | Kwota żądania | Bieżące saldo (z dnia 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 200            | 0               | 120                   | 40             | 160                              |

Bieżące saldo (160) = naliczona kwota (200) — kwota żądania (40)

#### <a name="semimonthly-plan"></a>Plan półmiesięczny

**Konfiguracja planu**

| Data początkowa planu | Data rejestracji | Częstotliwość naliczania | Podstawa okresu naliczania | Data przyznania naliczenia    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Co pół miesiąca       | Data początkowa planu      | Koniec okresu naliczania |

Naliczenia są przetwarzane 1 maja 2018 (5/1/2018), dlatego uwzględniany jest cały okres.

**Wyniki**

| Kwota naliczenia | Minimalne saldo | Maksymalne przeniesienie na następny okres | Kwota żądania | Bieżące saldo (z dnia 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 22                               |

Bieżące saldo (22) = naliczona kwota (5 × 6) — kwota żądania (8)

#### <a name="monthly-plan"></a>Plan miesięczny

**Konfiguracja planu**

| Data początkowa planu | Data rejestracji | Częstotliwość naliczania | Podstawa okresu naliczania | Data przyznania naliczenia    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Co pół miesiąca       | Data początkowa planu      | Koniec okresu naliczania |

Naliczenia są przetwarzane 1 maja 2018 (5/1/2018), dlatego uwzględniany jest cały okres.

**Wyniki**

| Kwota naliczenia | Minimalne saldo | Maksymalne przeniesienie na następny okres | Kwota żądania | Bieżące saldo (z dnia 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Bieżące saldo (7) = naliczona kwota (5 × 3) — kwota żądania (8)

### <a name="forecasted-balance"></a>Prognozowane saldo

*Prognozowane saldo* jest kwotą urlopu dostępną w przyszłości. Korekty naliczeń i przeniesień na następny okres są prognozowane do tej daty.

Stosowany jest poniższy wzór:

Saldo prognozowane na poniedziałek = Saldo bieżące – Żądania + Naliczenia – Korekta o przeniesienia na następny okres

### <a name="forecasted-balance-examples"></a>Przykład prognozowanego salda

#### <a name="annual-plan"></a>Plan roczny

**Konfiguracja planu**

| Data początkowa planu | Data rejestracji | Częstotliwość naliczania | Podstawa okresu naliczania | Data przyznania naliczenia    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Roczny            | Data początkowa planu      | Koniec okresu naliczania |

Naliczenia są przetwarzane 15 lutego 2019 (2/15/2019), dlatego uwzględniany jest cały okres.

**Wyniki**

| Kwota naliczenia | Minimalne saldo | Maksymalne przeniesienie na następny okres | Bieżące saldo | Prognozowane saldo (z dnia 2/15/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 20             | 0               | 20                    | 40              | 40                                   |

Prognozowane saldo (40) = Kwota naliczeń (20) + Saldo bieżące (40) – Korekta o przeniesienia na następny okres (20)

#### <a name="semimonthly-plan"></a>Plan półmiesięczny

**Konfiguracja planu**

| Data początkowa planu | Data rejestracji | Częstotliwość naliczania | Podstawa okresu naliczania | Data przyznania naliczenia    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Co pół miesiąca       | Data początkowa planu      | Koniec okresu naliczania |

Naliczenia są przetwarzane 15 lutego 2019 (2/15/2019), dlatego uwzględniany jest cały okres.

**Wyniki**

| Kwota naliczenia | Minimalne saldo | Maksymalne przeniesienie na następny okres | Bieżące saldo | Prognozowane saldo (z dnia 2/15/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 5              | 0               | 20                    | 40              | 35                                   |

Prognozowane saldo (35) = Kwota naliczeń (5 × 3) + Saldo bieżące (40) – Korekta o przeniesienia na następny okres (20)

#### <a name="monthly-plan"></a>Plan miesięczny

**Konfiguracja planu**

| Data początkowa planu | Data rejestracji | Częstotliwość naliczania | Podstawa okresu naliczania | Data przyznania naliczenia    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Co pół miesiąca       | Data początkowa planu      | Koniec okresu naliczania |

Naliczenia są przetwarzane 15 lutego 2019 (2/15/2019), dlatego uwzględniany jest cały okres.

**Wyniki**

| Kwota naliczenia | Minimalne saldo | Maksymalne przeniesienie na następny okres | Bieżące saldo | Prognozowane saldo (z dnia 2/15/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 10             | 0               | 20                    | 40              | 30                                   |

Prognozowane saldo (30) = Kwota naliczeń (10 × 1) + Saldo bieżące (40) – Korekta o przeniesienia na następny okres (20)

### <a name="proration-balance-examples"></a>Przykłady salda proporcjonalnego

#### <a name="prorated-monthly-plan"></a>Miesięczny plan proporcjonalny

**Konfiguracja planu**

| Data początkowa planu | Częstotliwość naliczania | Podstawa okresu naliczania |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Miesięcznie           | Data początkowa planu      |

**Wyniki**

| Pracownik            | Miesiące zatrudnienia | Data rejestracji | Rozpoczęcie | Kwota naliczenia | Proces naliczania | Bilansowe |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1.00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1.00           | 9/1/2018        | 2.53    |

#### <a name="full-accrual-monthly-plan"></a>Plan miesięczny pełnego naliczania

**Konfiguracja planu**

| Data początkowa planu | Częstotliwość naliczania | Podstawa okresu naliczania |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Miesięcznie           | Data początkowa planu      |

**Wyniki**

| Pracownik            | Miesiące zatrudnienia | Data rejestracji | Rozpoczęcie | Kwota naliczenia | Proces naliczania | Bilansowe |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1.00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1.00           | 9/1/2018        | 3,00    |

#### <a name="no-accrual-monthly-plan"></a>Plan miesięczny bez naliczania

**Konfiguracja planu**

| Data początkowa planu | Częstotliwość naliczania | Podstawa okresu naliczania |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Miesięcznie           | Data początkowa planu      |

**Wyniki**

| Pracownik            | Miesiące zatrudnienia | Data rejestracji | Rozpoczęcie | Kwota naliczenia | Proces naliczania | Bilansowe |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1.00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1.00           | 9/1/2018        | 2.00    |
