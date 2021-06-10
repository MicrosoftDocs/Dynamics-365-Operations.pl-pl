---
title: Płaca oparta na rejestracjach
description: W tym temacie wyjaśniono, jak płaca jest obliczana na podstawie rejestracji pracowników.
author: johanhoffmann
ms.date: 03/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgCalcApproveWeekView, JmgProdStatusListPagePayrollCostDetails, JmgPayCountTable, JmgPayStatConfig, JmgOvertimeSlize, JmgPayAgreementOverride, JmgPayCountSum, JmgPayAdjustSetup, JmgPayAdjustCostType, JmgPayEmployee, JmgMESBreak, JmgPayAddTable, JmgPayAddTransSelectTransId, JmgPayrollCostDetailsPart, jmgProdStatusListPagePayrollCosts, JmgPayrollCostPart, JmgPayEvents, JmgTermRegPayStatSetup, JmgPayStatGroup, JmgPayAddTrans, JmgPayStatTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-03-20
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 39786323e1ea11a960332e6e0a01f6ef8de1838d
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/26/2021
ms.locfileid: "6103006"
---
# <a name="pay-based-on-registrations"></a>Płaca oparta na rejestracjach

[!include [banner](../includes/banner.md)]

W tym temacie szczegółowo wyjaśniono, jak płaca jest obliczana na podstawie rejestracji pracowników. Zawiera przykłady pokazujące, jak różne kombinacje opcji konfiguracyjnych dostępnych dla obliczenia wpływają na wynik. Poniżej przedstawiono kilka obszarów, które zostaną omówione:

- Elastyczny czas pracy
- Nadgodziny
- Przerwy
- Kody przełączania
- Elementy płatności
- Umowy płacowe
- Parametry obliczeń w module Czas i frekwencja
- Nieobecność

## <a name="the-use-of-flex-time"></a>Używanie elastycznego czasu pracy

Okresy elastycznego czasu pracy są definiowane w profilach czasu używanych w module Czas i frekwencja. Istnieją dwa typy profili elastycznego czasu pracy: **Elastyczny czas pracy +** i **Elastyczny czas pracy -**. Gdy pracownik rejestruje czas w okresie dodania elastycznego czasu pracy (Elastyczny czas pracy +), saldo elastycznego czasu pracy pracownika jest zwiększane o liczbę przepracowanych godzin. Pracownik nie otrzymuje żadnego wynagrodzenia za godziny przepracowane w okresie Elastyczny czas pracy +. Jednakże pracownik może wziąć wolne w okresach odjęcia elastycznego czasu pracy (Elastyczny czas pracy -) i odebrać wynagrodzenie w postaci godzin ze swojego salda elastycznego czasu pracy. Z tego względu czas wolny od pracy w okresach elastycznego czasu pracy jest przez system traktowany jako nieobecność.

## <a name="scenarios-based-on-flex-periods"></a>Scenariusze oparte na okresach elastycznego czasu pracy

Dwa scenariusze przedstawione poniżej bazują na profilu elastycznego czasu pracy reprezentującym dzień roboczy. W obu scenariuszach płaca jest obliczana zgodnie z okresem elastycznego czasu pracy, w którym pracownik wszedł i wyszedł.

### <a name="flex-profile-for-one-workday"></a>Profil elastycznego czasu pracy dla jednego dnia roboczego

| Typ profilu  | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Dzień     |
|---------------|----------|----------|---------|
| Nadgodziny     | 24.00 | 6.00 | Poniedziałek  |
| Elastyczny czas pracy (+)         | 6.00 | 7.00 | Poniedziałek  |
| Wejście      | 7.00 | 7.00 | Poniedziałek  |
| Czas standardowy | 7.00 | 14.30 | Poniedziałek  |
| Elastyczny czas pracy -         | 14.30 | 15.30 | Poniedziałek  |
| Wyrejestruj się     | 15.30 | 15.30 | Poniedziałek  |
| Nadgodziny     | 15.30 | 6.00 | Wtorek |

### <a name="scenario-1-a-worker-registers-clock-in-during-a-flex-period-and-clock-out-during-a-flex--period"></a>Scenariusz 1: Pracownik rejestruje wejście w okresie dodania elastycznego czasu pracy oraz wyjście w okresie odjęcia elastycznego czasu pracy

Rejestracje pracownika w ciągu dnia wyglądają następująco.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      |
|---------------------------|----------|----------|
| Wejście                  | 6.30 | 6.30 |
| Zadanie produkcyjne            | 6.30 | 14.45 |
| Wyrejestruj się                 | 14.45 | 14.45 |

Rejestracje pracownika w dniu są obliczane i przenoszone do aparatu kalkulacji płac na stronie **Zatwierdź** (**Czas i frekwencja** &gt; **Przejrzyj i zatwierdź** &gt; **Zatwierdź**). Po obliczeniu rejestracji wynik obliczeń można obejrzeć na karcie **Czasy**. 

Aby zrozumieć ten scenariusz, zobacz następujące pola.

| Elastyczny czas pracy + | Elastyczny czas pracy - | Czas | Czas płatny |
|--------|--------|------|----------|
| 0.50   | 0.75   | 8.25 | 8.50     |

#### <a name="calculation-of-flex"></a>Obliczanie dodania elastycznego czasu pracy

Zgodnie z profilem elastycznego czasu pracy czas w godzinach od 6.00 i 7.00 jest okresem dodania elastycznego czasu pracy (Elastyczny czas pracy +). W związku z tym jeśli pracownik wejdzie o 6:30, zyskuje 0,5 godziny. Ta ilość czasu zostanie dodana do konta elastycznego czasu pracy pracownika.

#### <a name="calculation-of-flex-"></a>Obliczanie odjęcia elastycznego czasu pracy

Zgodnie z profilem elastycznego czasu pracy okres odjęcia elastycznego czasu pracy rozpoczyna się o 14.30 i kończy o 15.30. W związku z tym jeśli pracownik wyjdzie o godzinie 14.45, 45 minut (0,75 godziny) pozostałe w okresie odjęcia elastycznego czasu pracy zostaną zarejestrowane jako czas płatny i ta sama ilość czasu zostanie odjęta od konta elastycznego czasu pracy pracownika. 45 minut zostanie uwzględnionych w czasie płatnym, ponieważ pracownik otrzyma zapłatę za pozostałe 45 minut w okresie Elastyczny czas pracy -. Jeśli pracownik jest nieobecny w okresie odjęcia elastycznego czasu pracy, 45 minut zostanie odjętych od jego konta elastycznego czasu pracy.

#### <a name="calculation-of-time"></a>Obliczanie czasu

Czas jest obliczany jako okres między wejściem a wyjściem, czyli od 6.30 do 14.45, co daje 8,25 godziny.

#### <a name="calculation-of-pay-time"></a>Obliczanie czasu płatnego

Czas płatny to okres, za który pracownikowi przysługuje wynagrodzenie. W tym scenariuszu pracownik jest w pracy przez 8,25 godziny (**Czas**). Jednak wartość **Czas płatny** została obliczona na 8,50 godziny, ponieważ pracownikowi przyznano wynagrodzenie w okresie odjęcia elastycznego czasu pracy, gdy wyszedł z pracy. Czas pracy jest równy planowanej liczbie godzin pracy, ponieważ czas Elastyczny czas pracy + został dodany do konta elastycznego czasu pracy pracownika, a nie do czasu płatnego. Czas nieobecności w okresie odjęcia elastycznego czasu pracy jest kompensowany przez czas płatny i potrącany z konta elastycznego czasu pracy pracownika.

| Czas              | Typ rejestracji | Czas płatny (godziny)      |
|-------------------|-------------------|-----------------------|
| 6.30–7.00 | Elastyczny czas pracy (+)             | 0                     |
| 7.00–14.45 | Czas standardowy     | 7.75                  |
| 14.45–15.30 | Elastyczny czas pracy -             | 0,75 (okres nieobecności) |
|                   | Razem             | 8.50                  |

### <a name="scenario-2-a-worker-works-during-the-whole-flex--period-and-also-works-overtime"></a>Scenariusz 2: Pracownik pracuje w całym okresie odjęcia elastycznego czasu pracy oraz także w nadgodzinach

Rejestracje pracownika w ciągu dnia wyglądają następująco.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      |
|---------------------------|----------|----------|
| Wejście                  | 6.30 | 6.30 |
| Zadanie produkcyjne            | 6.30 | 17.00 |
| Wyrejestruj się                 | 17.00 | 17.00 |

Po obliczeniu rejestracji arkusza na stronie **Zatwierdź** można wyświetlić wynik obliczeń na karcie **Czasy**. Aby zrozumieć ten scenariusz, zobacz następujące pola.

| Elastyczny czas pracy + | Elastyczny czas pracy - | Czas  | Czas płatny | Płatne nadgodziny |
|--------|--------|-------|----------|--------------|
| 0.50   | 0,00   | 10,50 zł | 10,00    | 1.50         |

#### <a name="calculation-of-flex"></a>Obliczanie dodania elastycznego czasu pracy

Zgodnie z profilem elastycznego czasu pracy czas w godzinach od 6.00 i 7.00 jest okresem dodania elastycznego czasu pracy (Elastyczny czas pracy +). W związku z tym jeśli pracownik wchodzi o 6.30, otrzymuje dodatkowe 0,5 godziny elastycznego czasu pracy do swojego salda elastycznego czasu pracy.

#### <a name="calculation-of-flex-"></a>Obliczanie odjęcia elastycznego czasu pracy

Ponieważ pracownik pracuje w okresie odjęcia elastycznego czasu pracy, czas Elastyczny czas pracy - nie jest obliczany. Elastyczny czas pracy - oblicza się tylko wtedy, gdy pracownik jest nieobecny w okresie odjęcia elastycznego czasu pracy. W kontekście wypłaty jeśli pracownik pracuje w okresie odjęcia elastycznego czasu pracy, otrzymuje wynagrodzenie według stawki zdefiniowanej dla standardowego czasu pracy. Jeśli pracownik jest nieobecny w okresie odjęcia elastycznego czasu pracy, 45 minut zostanie odjętych od jego konta elastycznego czasu pracy.

#### <a name="calculation-of-time"></a>Obliczanie czasu

Czas jest obliczany jako okres między wejściem o godzinie 6.30 a wyjściem o 17.00, co daje 10,5 godziny.

#### <a name="calculation-of-pay-time"></a>Obliczanie czasu płatnego

W tym scenariuszu pracownik przepracowuje 10,50 godziny (**Czas**). Jednak wartość **Czas płatny** jest wyliczana na 10,00 godzin, ponieważ pracownikowi nie przysługuje wynagrodzenie w okresie dodania elastycznego czasu pracy.

#### <a name="calculation-of-pay-overtime"></a>Obliczanie płatnych nadgodzin

| Czas               | Typ rejestracji | Czas płatny (godziny) |
|--------------------|-------------------|------------------|
| 6.30–7.00  | Elastyczny czas pracy (+)             | 0                |
| 7.00–14.30  | Czas standardowy     | 7.50             |
| 14.30–15.30  | Elastyczny czas pracy -             | 1.00             |
| 15.30–17.00 | Nadgodziny          | 1.50             |
|                    | Razem             | 10,00            |

### <a name="generation-of-pay-items"></a>Generowanie elementów płacowych

Rejestracje pracownika w danym dniu można przenieść ze strony **Zatwierdź**. Podczas przenoszenia są generowane elementy płacowe i przeniesione rejestracje. Elementy płacowe reprezentują podział czasu płatnego na czas standardowy, nadgodziny, czas płatnej przerwy i tak dalej.

Aby otworzyć listę elementów płacowych, wybierz kolejno opcje **Czas i frekwencja** &gt; **Przejrzyj i zatwierdź** &gt; **Zatwierdź**. Następnie wybierz kolejno opcje **Informacje** &gt; **Przeniesione rejestracje**.

Elementy płacowe stanowią podstawę obliczania wynagrodzenia pracownika. Można wygenerować plik zawierający informacje z elementów płacowych, a następnie przenieść ten plik do systemu listy płac.

W ramach procesu przenoszenia czas i koszty z działań na produkcji i w projektach są przenoszone do arkuszy produkcji i projektów, aby uwzględnić poniesiony czas i koszty. Przeniesione rejestracje są podstawą dla czasu i kosztu własnego na godzinę dla zleceń produkcyjnych i projektów. Przeniesione rejestracje można otwierać za pomocą menu **Informacje** dostępnego na stronie **Zatwierdź**.

Na przykład w scenariuszu 2 są generowane następujące elementy płacowe.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs  | Łączny koszt |
|---------------|----------|-----------|-------|------------|
| Czas standardowy | 1201     | 10.0      | 10    | 100        |
| Nadgodziny      | 1301     | 1.50      | 5     | 7.50       |
|               |          |           | Razem | 107.50     |

Element płacowy standardowego czasu pracy ma jednostkę płacy 10 godzin, która obejmuje czas standardowy, odejmowany elastyczny czas pracy i nadgodziny. Czas standardowy, odejmowany elastyczny czas pracy i nadgodziny są konsolidowane w jeden element płacowy, ponieważ wszystkie typy wynagrodzenia są obliczane jako standardowy czas pracy w oparciu o domyślne ustawienie parametru na stronie **Parametry obliczania** (**Czas i frekwencja** &gt; **Ustawienia** &gt; **Parametry obliczania**). Nadgodziny są obliczane jako zwiększenie czasu standardowego przy użyciu dodatkowej stawki 5.

Jeśli chcesz wyraźnie odróżnić standardowy czas pracy od nadgodzin, tak aby jednostki płacowe dla typów płac dotyczyły tylko rzeczywistego czasu przepracowanego w czasie standardowym i nadgodzinach, jednostki płacowe czasu standardowego muszą zostać wyliczone na 8,50, a jednostki płacowe nadgodzin muszą zostać wyliczone na 1,50.

Aby w systemie skonfigurować jednoznaczne rozróżnianie standardowego czasu pracy i nadgodzin, należy wykluczyć nadgodziny z czasu standardowego. Należy także zmienić konfigurację typu płacy dla nadgodzin, tak aby stawka płacy za nadgodziny obejmowała wszystkie wypłaty za godziny przepracowane w nadgodzinach.

### <a name="exclude-overtime-from-the-standard-time"></a>Wykluczanie nadgodzin ze standardowego czasu pracy

Na stronie **Parametry obliczania** wybierz wartość **Nadgodziny** jako typ specyfikacji profilu, a w opcji **Czas płatny** ustaw wartość **Nie**, jak pokazano poniżej.

| Specyfikacja reg. | Typ specyfikacji profilu | Obliczenie   | Ustawienie | Zapłacona         | Ustawienie |
|--------------------|----------------------------|---------------|-----|--------------|-----|
| Czas pracy       | Nadgodziny                   | Czas standardowy | Tak | Czas płatny     | Nr  |
|                    |                            | Czas płatny      | Tak | Płatne nadgodziny | Tak |

Po ustawieniu parametrów obliczania zostaną wygenerowane następujące elementy płacowe.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs  | Łączny koszt |
|---------------|----------|-----------|-------|------------|
| Czas standardowy | 1201     | 8.50      | 10    | 85.0       |
| Nadgodziny      | 1301     | 1.50      | 15    | 22.50      |
|               |          |           | Razem | 107.50     |

> [!NOTE]
> Parametry obliczeń mają zalecane ustawienie standardowe. Na ogół należy zachować ostrożność przy modyfikowaniu tych parametrów. Aby przywrócić zalecane ustawienia standardowe, na stronie **Parametry obliczania** wybierz opcję **Przywrócenie wartości**.

### <a name="allow-a-deviation-from-the-standard-pay-profiles"></a>Zezwalanie na odchylenia od profili płac standardowych

Na stronie **Profile** (**Czas i frekwencja** &gt; **Ustawienia** &gt; **Profile czasu** &gt; **Profile**) można skonfigurować typy profili zawierające kody przełączania i przerwy.

### <a name="switch-codes"></a>Kody przełączania

Za pomocą kodów przełączania można pozwalać pracownikom na odchyłki od ich typów profili, zmieniając na inny typ profilu. Na przykład można pozwolić pracownikowi na zmianę z czasu Elastyczny czas pracy + na nadgodziny. Pracownik może dodać kod przełączania podczas rejestracji lub można przypisać zadanie dodania kodu przełączania osobie zatwierdzającej rejestracje.

Zanim będzie można użyć kodu przełączania, należy go zdefiniować jako typ działania pośredniego. Następnie należy dodać kod przełączania do profilu czasu w okresie, w którym chcesz pozwolić na zmianę typu profilu. Na przykład wykonaj następujące kroki, aby utworzyć kod przełączania, który umożliwia zmianę okresu dodania elastycznego czasu pracy od 6.00 do 7.00 na nadgodziny.

1. Utwórz kod przełączania o nazwie **OTBCI (Konwersja elastycznego czasu pracy na nadgodziny przed wejściem)**. Wybierz kolejno opcje **Czas i frekwencja** &gt; **Zarządzaj działaniami pośrednimi** &gt; **Działania pośrednie**.
2. W kolumnie **Kod przełączania** dodaj pozycję OTBCI do wiersza Elastyczny czas pracy + w profilu czasu.
3. W kolumnie **Podrzędny** dodaj typ profilu **Nadgodziny**.

Przyjrzyjmy się następującemu profilowi elastycznego czasu pracy, który reprezentuje dzień pracy.

| Typ profilu  | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Dzień     |
|---------------|----------|----------|---------|
| Nadgodziny     | 24.00 | 6.00 | Poniedziałek  |
| Elastyczny czas pracy (+)         | 6.00 | 7.00 | Poniedziałek  |
| Wejście      | 7.00 | 7.00 | Poniedziałek  |
| Czas standardowy | 7.00 | 14.30 | Poniedziałek  |
| Elastyczny czas pracy -         | 14.30 | 15.30 | Poniedziałek  |
| Wyrejestruj się     | 15.30 | 15.30 | Poniedziałek  |
| Nadgodziny     | 15.30 | 6.00 | Wtorek |

Oto rejestracje pracownika w ciągu dnia.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      |
|---------------------------|----------|----------|
| Wejście                  | 6.30 | 6.30 |
| Zadanie produkcyjne            | 6.30 | 14.45 |
| Wyrejestruj się                 | 17.00 | 17.00 |

Po przeniesieniu są generowane następujące elementy płacowe.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs  | Łączny koszt |
|---------------|----------|-----------|-------|------------|
| Czas standardowy | 1201     | 8.50      | 10    | 85.0       |
| Nadgodziny      | 1305     | 1.50      | 15    | 22.50      |
|               |          |           | Razem | 107.50     |

Na stronie **Zatwierdź** cofnij przeniesienie, a następnie za pomocą menu **Kod przełączania** zastosuj kod przełączania **OTBCI**. Po przeniesieniu rejestracji po raz drugi są generowane następujące elementy płacowe.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs  | Łączny koszt |
|---------------|----------|-----------|-------|------------|
| Czas standardowy | 1201     | 8.50      | 10    | 80.0       |
| Nadgodziny      | 1305     | 2.00      | 15    | 30.0       |
|               |          |           | Razem | 107.50     |

> [!NOTE]
> Po zastosowaniu kodu przełączania ilość nadgodzin jest zwiększana o 0,5 godziny, z 1,50 na 2,00. 0,5 godziny to efekt konwersji zarejestrowanego dodania elastycznego czasu pracy — od 6.30 do 7.00 — na nadgodziny.

### <a name="breaks"></a>Przerwy

Przerwy w pracy wpływają na obliczenia płacy pracownika. Przerwy definiuje się jako działanie o typie pośrednim. Można je zdefiniować jako **Płatne**, tak aby przerwa była dodawana do płacy pracownika, lub **Niepłatne**, aby uniemożliwić dodawanie przerw do płacy pracownika. Przerwa może być również określona jako albo **Planowane** lub **Zarejestrowane**.

#### <a name="planned-breaks"></a>Planowane przerwy

Jeśli w firmie obowiązuje stały czas przerw, na przykład przerwa na obiad, taką przerwę można wstępnie zdefiniować w profilu czasu. W takim przypadku pracownik nie musi rejestrować przerwy na stronach kart zadań. Zamiast tego przerwy są automatycznie rozliczane podczas obliczania rejestracji pracownika na stronie **Zatwierdź**.

#### <a name="registered-breaks"></a>Zarejestrowane przerwy

Jeśli firma nie stosuje planowanych przerw, pracownicy mogą rejestrować przerwy w trakcie dnia pracy. Zarejestrowane przerwy można wykorzystywać na przykład w sytuacji, gdy pracownik używa profilu elastycznego czasu pracy, który nie ma zdefiniowanych czasów wejścia i wyjścia. Zarejestrowane przerwy są działaniem o typie pośrednim. Pracownik rejestruje przerwę na stronie **Karta zadania** w terminalu lub na stronie **Karta zadania** w urządzeniu. Na obu tych stronach użytkownik może wybrać typ przerwy z listy wstępnie zdefiniowanych działań przerw.

#### <a name="paid-and-unpaid-breaks"></a>Przerwy płatne i niepłatne

Działania przerw mogą być skonfigurowane jako **Płatne** lub **Niepłatne**. Płatna przerwa jest uwzględniana przy obliczaniu czasu płatnego, a system używa typu płatności zdefiniowanego w umowie płacowej dla rejestracji typu **Przerwa**.

### <a name="example-of-a-planned-break"></a>Przykład planowanej przerwy

Przyjrzyjmy się następującemu profilowi czasu, który zawiera niepłatną przerwę na obiad.

| Typ profilu  | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Dzień     |
|---------------|----------|----------|---------|
| Nadgodziny     | 24.00 | 6.00 | Poniedziałek  |
| Elastyczny czas pracy (+)         | 6.00 | 7.00 | Poniedziałek  |
| Wejście      | 7.00 | 7.00 | Poniedziałek  |
| Czas standardowy | 7.00 | 12.00 | Poniedziałek  |
| Przerwa         | 12.00 | 12.30 | Poniedziałek  |
| Czas standardowy | 12.30 | 14.30 | Poniedziałek  |
| Elastyczny czas pracy -         | 14.30 | 15.30 | Poniedziałek  |
| Wyrejestruj się     | 15.30 | 15.30 | Poniedziałek  |
| Nadgodziny     | 15.30 | 6.00 | Wtorek |

Oto rejestracje pracownika w ciągu dnia.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      |
|---------------------------|----------|----------|
| Wejście                  | 6.30 | 6.30 |
| Zadanie produkcyjne            | 6.30 | 14.45 |
| Wyrejestruj się                 | 17.00 | 17.00 |

Po obliczeniu rejestracji arkusza na stronie **Zatwierdź** można wyświetlić wynik obliczeń na karcie **Czasy**. Aby zrozumieć ten scenariusz, zobacz następujące pola.

| Elastyczny czas pracy + | Elastyczny czas pracy - | Czas  | Czas płatny | Niepłatny czas przerw | Płatne nadgodziny |
|--------|--------|-------|----------|---------------------|--------------|
| 0.50   | 0,00   | 10,50 zł | 9.50     | 0.5                 | 1.50         |

> [!NOTE] 
> System wyliczył 0,5 godziny niepłatnego czasu przerw i ten okres nie wlicza się do czasu płatnego.

### <a name="example-of-a-registered-break"></a>Przykład zarejestrowanej przerwy

Przyjrzyjmy się następującemu profilowi czasu, który nie zawiera planowanych przerw.

| Typ profilu  | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Dzień     |
|---------------|----------|----------|---------|
| Nadgodziny     | 24.00 | 6.00 | Poniedziałek  |
| Elastyczny czas pracy (+)         | 6.00 | 7.00 | Poniedziałek  |
| Wejście      | 7.00 | 7.00 | Poniedziałek  |
| Czas standardowy | 7.00 | 14.30 | Poniedziałek  |
| Elastyczny czas pracy -         | 14.30 | 15.30 | Poniedziałek  |
| Wyrejestruj się     | 15.30 | 15.30 | Poniedziałek  |
| Nadgodziny     | 15.30 | 6.00 | Wtorek |

Oto rejestracje pracownika w ciągu dnia.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      |
|---------------------------|----------|----------|
| Wejście                  | 6.30 | 6.30 |
| Zadanie produkcyjne            | 6.30 | 17.00 |
| Przerwa                     | 12.03 | 12.32 |
| Wyrejestruj się                 | 17.00 | 17.00 |

Podczas obliczania rejestracji jest obliczany czas działań.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Czas  |
|---------------------------|----------|----------|-------|
| Wejście                  | 6.30 | 6.30 |       |
| Zadanie produkcyjne            | 6.30 | 17.00 | 10,00 |
| Przerwa                     | 12.03 | 12.32 | 0.50  |
| Wyrejestruj się                 | 17.00 | 17.00 |       |

> [!NOTE]
> Czas przerwy biegnie równolegle z czasem działania (w tym przykładzie zadania produkcyjnego). To zachowanie jest zawsze stosowane do działań przerw. Podczas obliczania rejestracji czas przerwy jest odejmowany od czasu działania. W tym przypadku zadanie produkcyjne ma czas trwania 10,50 godziny, ale czas jest wyliczany jako 10, ponieważ od czasu działania jest odejmowane 0,5 czasu przerwy.

Po obliczeniu rejestracji arkusza na stronie **Zatwierdź** można wyświetlić wynik obliczeń na karcie **Czasy**. Aby zrozumieć ten scenariusz, zobacz następujące pola.

| Elastyczny czas pracy + | Elastyczny czas pracy - | Czas  | Czas płatny | Niepłatny czas przerw | Płatne nadgodziny |
|--------|--------|-------|----------|---------------------|--------------|
| 0.50   | 0,00   | 10,50 zł | 9.50     | 0.5                 | 1.50         |

Jeśli planowana przerwa byłaby płatna, a nie niepłatna, wynik obliczenia wyglądałby następująco.

| Elastyczny czas pracy + | Elastyczny czas pracy - | Czas  | Czas płatny | Czas płatnej przerwy | Płatne nadgodziny |
|--------|--------|-------|----------|-----------------|--------------|
| 0.50   | 0,00   | 10,50 zł | 10,00    | 0.5             | 1.50         |

### <a name="pay-items-and-paid-breaks"></a>Elementy płacowe i niepłatne przerwy

Po przeniesieniu rejestracji na stronie **Zatwierdź** są generowane elementy płacowe. Osobny element płacowy jest generowany dla płatnych przerw.

Stawka płacy dla płatnej przerwy zależy od typu płacy skonfigurowanego w umowach płacowych dla przerwy. Zamiast używać typu płacy, można skonfigurować koszt własny na godzinę przerwy dla określonego przedziału dat.

Przyjrzyjmy się następującemu profilowi czasu.

| Typ profilu  | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Dzień     |
|---------------|----------|----------|---------|
| Nadgodziny     | 24.00 | 6.00 | Poniedziałek  |
| Elastyczny czas pracy (+)         | 6.00 | 7.00 | Poniedziałek  |
| Wejście      | 7.00 | 7.00 | Poniedziałek  |
| Czas standardowy | 7.00 | 14.30 | Poniedziałek  |
| Elastyczny czas pracy -         | 14.30 | 15.30 | Poniedziałek  |
| Wyrejestruj się     | 15.30 | 15.30 | Poniedziałek  |
| Nadgodziny     | 15.30 | 6.00 | Wtorek |

Oto rejestracje pracownika w ciągu dnia.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Czas |
|---------------------------|----------|----------|------|
| Wejście                  | 7.00 | 7.00 |      |
| Zadanie produkcyjne            | 7.00 | 15.00 | 7.5  |
| Przerwa (płatna)              | 12.00 | 12.30 | 0.5  |
| Wyrejestruj się                 | 15.00 | 15.00 |      |

W tym przykładzie jako typ płacy dla czasu standardowego ustawiono **1201**, a w umowie płacowej ustawiono stawkę płacy **10**. Płatna przerwa ma typ płacy **1301** i stawkę płacy **8**. Po przeniesieniu rejestracji są generowane następujące elementy płacowe.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs |
|---------------|----------|-----------|------|
| Czas standardowy | 1201     | 7.50      | 10   |
| Elastyczny czas pracy -         | 1201     | 0.50      | 10   |
| Przerwa (płatna)  | 1301     | 0.50      | 8    |

## <a name="how-the-cost-of-paid-breaks-is-allocated-to-projects-and-production-orders"></a>Sposób przydzielania kosztu płatnych przerw do projektów i zleceń produkcyjnych

Koszt godzinowy działań projektu i zadań produkcyjnych można skonfigurować w taki sposób, aby był wyznaczany przez stawki płac obliczane w module Czas i frekwencja lub przez kategorie kosztów zdefiniowane dla działań.

Aby skonfigurować kategorię kosztu, wybierz kolejno opcje **Kontrola produkcji** &gt; **Ustawienia** &gt; **Wykonywanie produkcji** &gt; **Ustawienia domyślne zlecenia produkcyjnego**, a następnie w polu **Kategoria kosztu** ustaw wartość **Tak** lub **Nie**.

- **Nie** — koszt jest obliczany według stawek płac zdefiniowanych dla typów rejestracji w module Czas i frekwencja.
- **Tak** — koszt jest obliczany na podstawie kategorii kosztów działań na produkcji i w projektach.

### <a name="cost-calculation-based-on-pay-rates-that-are-calculated-in-time-and-attendance"></a>Obliczanie kosztów według stawek płac obliczanych w module Czas i frekwencja

W poniższym przykładzie pokazano sposób obliczania kosztu godzinowego, gdy koszt jest skonfigurowany tak, aby był obliczany na podstawie stawek płac.

Stawka kosztu godzinowego używana dla zleceń produkcyjnych i projektów jest obliczana w trakcie procesu przenoszenia. Aby wyświetlić stawkę godzinową dla każdego działania, otwórz stronę **Zatwierdź** w module Czas i frekwencja, a następnie wybierz kolejno opcje **Informacje** &gt; **Przeniesione rejestracje**. Stawka kosztu godzinowego dla rejestracji jest podana na karcie **Koszty własne**.

Przyjrzyjmy się następującym rejestracjom wykorzystującym ten sam profil czasu, jak w poprzednim przykładzie.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Czas |
|---------------------------|----------|----------|------|
| Wejście                  | 7.00 | 7.00 |      |
| Proces (zlecenie: 4711)     | 7.00 | 11.00 | 4    |
| Proces (zlecenie: 4712)     | 11.00 | 15.00 | 3.50 |
| Przerwa (płatna)              | 12.00 | 12.30 | 0.50 |
| Wyrejestruj się                 | 15.00 | 15.00 |      |

Po przeniesieniu rejestracji są generowane następujące przeniesione rejestracje.

| Typ rejestracji     | Czas | Koszt własny na godzinę |
|-----------------------|------|---------------------|
| Wejście              | 0,00 | 0,00                |
| Proces (zlecenie: 4711) | 4,00 | 10,00               |
| Proces (zlecenie: 4712) | 3.50 | 11.14               |
| Przerwa (płatna)          | 0.50 | 0,00                |
| Wyrejestruj się             | 0,00 | 0,00                |

Obliczanie kosztu własnego na godzinę dla płatnej przerwy zależy od ustawienia dla bezpośrednich kosztów płacowych. Wybierz kolejno opcje **Czas i frekwencja** &gt; **Ustawienia** &gt; **Parametry modułu Czas i frekwencja**. Na karcie **Koszt własny** w obszarze **Bezpośrednie koszty płacowe** w polu **Czas standardowy** można wybrać opcję **Tak**, **Nie** lub **Alokacja**.

- **Tak** — ta wartość jest używana w poprzednim przykładzie. Koszt jest alokowany do działania na produkcji lub w projekcie, które jest wykonywane równolegle z płatnym działaniem przerwy. W przykładzie to działanie jest zadaniem produkcyjnym dla zlecenia 4712. Jak widać, koszt własny na godzinę dla płatnej przerwy wynosi 0 (zero) i jest przydzielony do zadania wykonywanego równolegle z przerwą.

    Płatna przerwa ma czas trwania 0,5 godziny, a stawka płacy wynosi 8. W związku z tym łączny koszt płatnej przerwy wynosi 4. Łączny koszt jest następnie przydzielany do 3,5 godzinnego zadania procesu. W związku z tym płatna przerwa ma udział w koszcie wynoszący 1,14 na godzinę (4 / 3,5 = 1,14).

- **Alokacja** — płatna przerwa jest rozdzielana równomiernie do zadań zarejestrowanych w danym dniu. Jeśli ta wartość zostanie użyta w poprzednim przykładzie, zostaną wygenerowane następujące przeniesione rejestracje.

    | Typ rejestracji     | Czas | Koszt własny na godzinę |
    |-----------------------|------|---------------------|
    | Wejście              | 0,00 | 0,00                |
    | Proces (zlecenie: 4711) | 4,00 | 10.53               |
    | Proces (zlecenie: 4712) | 3.50 | 10.53               |
    | Przerwa (płatna)          | 0.50 | 0,00                |
    | Wyrejestruj się             | 0,00 | 0,00                |

    Łączny czas procesu dla dwóch zadań produkcyjnych wynosi 7,5 godziny, a łączny koszt płatnej przerwy wynosi 4. W związku z tym koszt przerwy jest wyliczany na 0,53 (= 4 / 7,5).

- **Nie** — koszt płatnej przerwy nie zwiększa kosztu godzinowego działań procesu.

    | Typ rejestracji     | Czas | Koszt własny na godzinę |
    |-----------------------|------|---------------------|
    | Wejście              | 0,00 | 0,00                |
    | Proces (zlecenie: 4711) | 4,00 | 10,00               |
    | Proces (zlecenie: 4712) | 3.50 | 10,00               |
    | Przerwa (płatna)          | 0.50 | 0,00                |
    | Wyrejestruj się             | 0,00 | 0,00                |

## <a name="absence"></a>Nieobecność

Kod nieobecności służy do rejestrowania okresu nieobecności pracownika w pracy. Podobnie jak przerwy i kody przełączania, kod nieobecności jest działaniem typu pośredniego. Czas nieobecności może być zaplanowany albo zarejestrowany, a nieobecność może być usprawiedliwiona lub nieusprawiedliwiona. Przykładami usprawiedliwionych nieobecności są wizyta u lekarza, udział w seminarium lub obowiązek sędziego przysięgłego. Nieobecność nieusprawiedliwiona nie ma rzetelnego powodu i jej przykładem jest spóźnienie do pracy. Zazwyczaj nieobecność usprawiedliwiona nie powoduje potrącenia z płacy pracownika, podczas gdy nieobecność nieusprawiedliwiona powoduje potrącenie.

### <a name="planned-absence"></a>Planowana nieobecność

Planowane nieobecności pracowników można tworzyć na stronie **Utwórz planowaną nieobecność** (**Czas i frekwencja** &gt; **Utwórz planowaną nieobecność**). Na tej stronie planowana nieobecność jest rejestrowana jako zadanie nieobecności w określonym dniu i przedziale czasu.

Zadanie jest oparte na zapytaniu. Z tego względu planowaną nieobecność można utworzyć dla wielu pracowników, takich jak pracownicy należący do tej samej grupy obliczania. Jeśli planowana nieobecność dotyczy jednego pracownika, rejestrację można wprowadzić na stronie **Obecność** lub na stronie **Pracownicy odpowiedzialni za rejestrację czasu**.

- Aby wprowadzić rejestrację nieobecności na stronie **Obecność**, wybierz kolejno opcje **Czas i frekwencja** &gt; **Zapytania i raporty** &gt; **Obecność** &gt; **Obecność**, a następnie wybierz opcję **Rejestracja nieobecności**.
- Aby wprowadzić rejestrację nieobecności ze strony *<strong><em>Pracownicy odpowiedzialni za rejestrację czasu</em></strong>*, wybierz kolejno opcje <strong>Czas i frekwencja</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Pracownicy odpowiedzialni za rejestrację czasu</strong>, a następnie na karcie <strong>Czas</strong> w obszarze <strong>Przypisanie czasu</strong> wybierz opcję <strong>Rejestracje nieobecności</strong>.

Można użyć raportu **Zaplanowane nieobecności** w celu wyświetlania przeglądu planowanych nieobecności pracowników. Aby otworzyć ten raport, wybierz kolejno opcje **Czas i frekwencja** &gt; **Zapytania i raporty** &gt; **Raporty dotyczące nieobecności** &gt; **Zaplanowane nieobecności**.

### <a name="registered-absence"></a>Zarejestrowana nieobecność

Zasadniczo pracownicy są traktowani jako nieobecni, jeśli nie znajdują się w miejscu pracy przez jakikolwiek okres między zaplanowanymi dla nich godzinami wejścia i wyjścia. Jeśli pracownicy przyjdą później niż zaplanowano albo wyjdą wcześniej niż zaplanowano, są monitowani o wybranie kodu nieobecności w celu określania przyczyn nieobecności. Kod nieobecności można skonfigurować tak, aby pasował do rejestracji. Tylko pasujące kody będą dostępne do wyboru na liście.

## <a name="scenarios-based-on-various-combinations-of-work-hour-registrations"></a>Scenariusze oparte na różnych kombinacjach rejestracji godzin pracy

W poniższych scenariuszach pokazano elementy płacowe i wpisy do zatwierdzenia, które są generowane dla pracowników na podstawie ich rejestracji. Wszystkie scenariusze bazują na następującym profilu czasu.

| Typ profilu  | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Dzień     |
|---------------|----------|----------|---------|
| Nadgodziny     | 24.00 | 6.00 | Poniedziałek  |
| Elastyczny czas pracy (+)         | 6.00 | 7.00 | Poniedziałek  |
| Wejście      | 7.00 | 7.00 | Poniedziałek  |
| Czas standardowy | 7.00 | 14.30 | Poniedziałek  |
| Elastyczny czas pracy -         | 14.30 | 15.30 | Poniedziałek  |
| Wyrejestruj się     | 15.30 | 15.30 | Poniedziałek  |
| Nadgodziny     | 15.30 | 6.00 | Wtorek |

### <a name="scenario-1-the-worker-clocks-in-later-than-planned"></a>Scenariusz 1: Pracownik przychodzi później niż zaplanowano

Pracownik przychodzi o 8.30. Ponieważ jego planowana godzina przyjścia to 7.00, jest 1,50 godziny spóźniony do pracy. Ponieważ 1,50 godziny jest uznawane za czas nieobecności, pracownik otrzymuje monit o wybranie kodu nieobecności. Pracownik wychodzi o godzinie 15:30, czyli zgodnie z planem. Gdy rejestracje pracownika są obliczane i zatwierdzane, rejestracja nieobecności razem z kodem nieobecności wybranym przez pracownika przy wejściu pojawiają się dla okresu od 7.00 do 8.30.

W profilu czasu można w typie rejestracji **Wejście** skonfigurować tolerancję dla przypadków, gdy pracownicy spóźniają się do pracy. Na przykład jeśli ustawisz tolerancję 5, pracownik będzie monitowany o podanie kodu nieobecności tylko wtedy, gdy wejdzie później niż 7.05.

W tym przypadku, ponieważ pracownik nie ma rzetelnego powodu spóźnienia się do pracy, wybiera kod nieobecności zdefiniowany dla nieobecności nieusprawiedliwionej. Kod nieobecności jest traktowany jako pasujący do nieusprawiedliwionej nieobecności, jeśli ustawienie potrącania z nadgodzin jest włączone dla grupy nieobecności, do której należy kod nieobecności. Aby skonfigurować to ustawienie, wybierz kolejno opcje **Czas i frekwencja** &gt; **Ustawienia** &gt; **Grupy** &gt; **Grupy nieobecności**, a następnie zaznacz pole wyboru **Odejmij nadgodziny**.

Poniżej przedstawiono sposób wyświetlania rejestracji pracownika w danym dniu na stronie **Zatwierdź** po wykonaniu obliczeń.

| Typ rejestracji arkusza         | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Czas |
|-----------------------------------|----------|----------|------|
| Nieobecność (nieusprawiedliwione - spóźnienia dla pracy) | 7.00 | 8.30 | 1.5  |
| Wejście                          | 8.30 | 8.30 |      |
| Zadanie produkcyjne                    | 7.30 | 15.30 | 7.0  |
| Wyrejestruj się                         | 15.30 | 15.30 |      |

Oto wynikowy element płacowy po przeniesieniu rejestracji.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs |
|---------------|----------|-----------|------|
| Czas standardowy | 1201     | 7.00      | 10   |

### <a name="scenario-2-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-standard-time-period"></a>Scenariusz 2: Pracownik wychodzi przed zaplanowaną godziną wyjścia się okresie czasu standardowego

Pracownik wchodzi o 7.00, a wychodzi przedwcześnie o 13.00. Ponieważ godzina 13.00 jest przed planowaną godziną wyjścia 15.30 i należy do okresu czasu standardowego, pracownikowi jest wyświetlany monit o wybranie kodu nieobecności. Pracownik wybiera kod nieobecności mówiący o wizycie u lekarza, który jest zdefiniowany jako nieobecność usprawiedliwiona. Stawka płacy dla nieobecności usprawiedliwionej jest zdefiniowana w umowach płacowych dla typu rejestracji **Nieobecność** (**Czas i frekwencja** &gt; **Ustawienia** &gt; **Lista płac** &gt; **Umowy płacowe**).

Poniżej przedstawiono sposób wyświetlania rejestracji pracownika w danym dniu na stronie **Zatwierdź** po wykonaniu obliczeń.

| Typ rejestracji arkusza              | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Czas |
|----------------------------------------|----------|----------|------|
| Wejście                               | 7.00 | 7.00 |      |
| Zadanie produkcyjne                         | 7.00 | 13.00 | 4.0  |
| Wyrejestruj się                              | 13.00 | 13.00 |      |
| Nieobecność (usprawiedliwiona — wizyta u lekarza) | 13.00 | 15.30 | 3.5  |

Oto wynikowy element płacowy po przeniesieniu rejestracji.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs |
|---------------|----------|-----------|------|
| Czas standardowy | 1201     | 7.50      | 10   |

### <a name="scenario-3-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-flex--period"></a>Scenariusz 3: Pracownik wychodzi przed zaplanowaną godziną wyjścia się okresie odjęcia elastycznego czasu pracy

Pracownik wchodzi o 7.00 i wychodzi o 14.15, co mieści się w planowanym okresie odjęcia elastycznego czasu pracy. Czas między rzeczywistą godziną wyjścia a planowaną godziną wyjścia nie jest uznawany za nieobecność, a pracownikowi nie jest wyświetlany monit o wybranie kodu nieobecności. Ilość jest odejmowana od konta elastycznego czasu pracy pracownika, a pracownik otrzymuje zapłatę za pozostałą części okresu odjęcia elastycznego czasu pracy, czyli za czas od 14.15 do 15.30.

Poniżej przedstawiono sposób wyświetlania rejestracji pracownika w danym dniu na stronie **Zatwierdź** po wykonaniu obliczeń.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Czas |
|---------------------------|----------|----------|------|
| Wejście                  | 7.00 | 7.00 |      |
| Zadanie produkcyjne            | 7.00 | 14.15 | 7.25 |
| Wyrejestruj się                 | 14.15 | 14.15 |      |

Oto wynikowy element płacowy po przeniesieniu rejestracji.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs |
|---------------|----------|-----------|------|
| Czas standardowy | 1201     | 8.50      | 10   |

### <a name="scenario-4-the-worker-clocks-in-late-and-clocks-out-after-the-planned-clock-out-time-during-an-overtime-period"></a>Scenariusz 4: Pracownik wychodzi spóźniony, a wychodzi po zaplanowanej godzinie wyjścia w okresie nadgodzin

Pracownik wchodzi spóźniony o 9.30, a następnie, aby skompensować to spóźnienie, pracuje w nadgodzinach i wychodzi o 17.00. Ponieważ pracownik przyszedł później i zrekompensował to, pracując dłużej, firma nie chce przyznać pracownikowi płacy za nadgodziny w czasie, gdy pracował on między planowaną godziną wyjścia o 15.30 a faktyczną godziną wyjścia o 17.00, mimo iż ten okres jest zdefiniowany jako nadgodziny w profilu czasu.

Do obsługi tego scenariusza można skonfigurować kod nieobecności, który będzie zmniejszał liczbę nadgodzin o liczbę godzin nieusprawiedliwionej nieobecność pracownika w tym samym dniu. Aby odejmować nadgodziny od czasu nieusprawiedliwionej nieobecności, wybierz kolejno opcje **Czas i frekwencja** &gt; **Ustawienia** &gt; **Grupy** &gt; **Grupy nieobecności**, a następnie zaznacz pole wyboru **Odejmij nadgodziny**.

Poniżej przedstawiono sposób wyświetlania rejestracji pracownika w danym dniu na stronie **Zatwierdź** po wykonaniu obliczeń.

| Typ rejestracji arkusza         | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Czas |
|-----------------------------------|----------|----------|------|
| Nieobecność (nieusprawiedliwione - spóźnienia dla pracy) | 7.00 | 9.30 | 1.5  |
| Wejście                          | 9.30 | 9.30 |      |
| Zadanie produkcyjne                    | 9.30 | 17.00 | 7.5  |
| Wyrejestruj się                         | 17.30 | 17.30 |      |

Jeśli pole wyboru **Odejmij nadgodziny** zostanie zaznaczone dla wybranego kodu nieobecności, płatność za nadgodziny będzie odejmowana od liczby godzin nieusprawiedliwionej nieobecności pracownika. W takim przypadku po przeniesieniu rejestracji zostaną wygenerowane następujące elementy płacowe.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs |
|---------------|----------|-----------|------|
| Czas standardowy | 1201     | 9.00      | 10   |
| Nadgodziny      | 1301     | 0.5       | 15   |

1,5 godziny nieusprawiedliwionej nieobecności od 7.00 do 9.30 zmniejszyło 2,0 godziny nadgodzin przepracowanych od 15.30 do 17.30. Wynikiem rejestracji jest 1,5 godziny czasu standardowego i 0,5 nadgodzin.

Z drugiej strony jeśli pole wyboru **Odejmij nadgodziny** jest wyczyszczone dla wybranego kodu nieobecności, pracownik otrzymuje zapłatę za nadgodziny, mimo że się spóźnił i miał nieusprawiedliwioną nieobecność. W takim przypadku po przeniesieniu rejestracji zostaną wygenerowane następujące elementy płacowe.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs |
|---------------|----------|-----------|------|
| Czas standardowy | 1201     | 7.50      | 10   |
| Nadgodziny      | 1301     | 2.0       | 15   |

### <a name="scenario-5-the-worker-clocks-out-before-the-planned-clock-out-time-and-can-convert-the-absence-period-to-a-flex--period"></a>Scenariusz 5: Pracownik wyszedł przed planowaną godziną wyjścia i może przekształcić okres nieobecności na okres odjęcia elastycznego czasu pracy

W poniższym przykładzie pokazano, jak saldo konta elastycznego czasu pracy pracownika można zmniejszyć poprzez przekonwertowanie okresu nieobecności na okres odjęcia elastycznego czasu pracy.

Pracownik wchodzi o 7.00, a wychodzi o 13.00. Pracownik ma umowę, że może wrócić do domu na weekend, jeśli odliczy te godziny ze swojego konta elastycznego. Jeśli pracownik wyjdzie o 13.00, zobaczy monit o wybranie kodu nieobecności, ponieważ okres nieobecności w pozostałej części dnia pracy nie jest planowanym okresem odjęcia elastycznego czasu pracy. Aby przekształcić pozostałą część dnia pracy na okres odjęcia elastycznego czasu pracy, pracownik może wybrać kod nieobecności skonfigurowany do zmniejszania salda konta elastycznego czasu pracy.

Aby zmniejszać saldo elastycznego czasu pracy dla pracowników, którzy rejestrują nieobecność w trakcie dnia roboczego, wybierz kolejno opcje **Czas i frekwencja** &gt; **Ustawienia** &gt; **Grupy** &gt; **Grupy nieobecności** i zaznacz pole wyboru **Redukcja elastycznego czasu pracy**.

Poniżej przedstawiono sposób wyświetlania rejestracji pracownika w danym dniu na stronie **Zatwierdź** przed wykonaniem obliczeń.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      | Czas |
|---------------------------|----------|----------|------|
| Wejście                  | 7.00 | 7.00 |      |
| Zadanie produkcyjne            | 7.00 | 13.00 | 6.0  |
| Wyrejestruj się                 | 13.00 | 13.00 |      |

Jeśli pracownik wybierze kod nieobecności dla nieobecności nieusprawiedliwionej, oto jak będzie wyglądał wynikowy element płacowy po przeniesieniu rejestracji.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs |
|---------------|----------|-----------|------|
| Czas standardowy | 1201     | 6,00      | 10   |

Jeśli pracownik wybierze kod nieobecności dla nieobecności usprawiedliwionej, a ten kod nieobecności jest skonfigurowany do zmniejszania jego salda konta elastycznego czasu pracy, oto jak będzie wyglądał wynikowy element płacowy po przesłaniu rejestracji.

| Typ płacy     | Typ płatności | Jednostki płac | Kurs |
|---------------|----------|-----------|------|
| Czas standardowy | 1201     | 8.50      | 10   |

W takim przypadku saldo elastycznego czasu pracy pracownika jest zmniejszanie o liczbę godzin między rzeczywistą godziną wyjścia a planowaną godziną wyjścia (czyli o 2,5 godziny między 13.00 a 15.30).

> [!NOTE]
> Nie zalecamy zaznaczania równocześnie pól wyboru **Odejmij elastyczny czas pracy** i **Odejmij nadgodziny** dla kodu nieobecności, ponieważ ta konfiguracja spowoduje odejmowanie nieusprawiedliwionych godzin od nadgodzin pracownika i jednocześnie zmniejszenie salda elastycznego czasu pracy pracownika.

### <a name="scenario-6-there-is-no-planned-absence-for-the-day-and-no-worker-attendance-for-the-day"></a>Scenariusz 6: Nie ma planowanej nieobecności ani obecności pracownika w danym dniu

Jeśli pracownik nie przyjdzie do pracy w dniu roboczym oraz nie ma planowanej nieobecności pracownika w tym dniu, do obliczania rejestracji pracownika jest używany domyślny kod nieobecności. Aby zdefiniować domyślne kody nieobecności, wybierz kolejno opcje **Czas i frekwencja** &gt; **Parametry modułu Czas i frekwencja**. Następnie można wybrać kod nieobecności w następujących polach:

- Automatyczne wstawianie elastycznego czasu pracy-
- Automatyczne wstawianie nieobecności

Podczas obliczania dziennych rejestracji dla pracownika, który ma włączoną funkcję elastycznych godzin pracy, kod nieobecności określony w polu **Automatyczne wstawianie elastycznego czasu pracy-** jest używany jako domyślny kod nieobecności. Jeśli pracownik nie ma włączonej funkcji elastycznych godzin pracy, jest używany kod nieobecności określony w polu **Automatyczne wstawianie nieobecności**. Jeśli w firmie części pracowników ma, a część nie ma włączonej funkcji elastycznych godzin pracy, należy skonfigurować oba parametry.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]