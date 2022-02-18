---
title: Obszar roboczy zarządzania personelem
description: W tym temacie opisano elementy pojęć obszaru roboczego Zarządzanie pracownikami.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7a83dea308e3e2eec1edebd5d619f9455e1a2268
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066582"
---
# <a name="personnel-management-workspace"></a>Obszar roboczy zarządzania personelem


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Obszar roboczy **Zarządzanie pracownikami** zawiera ilość zawartości. Zawiera ruchy personalne, śledzi zmiany pracowników, otwarte stanowiska, zmiany adresów, wygasające rekordy i analizy oraz udostępnia linki do konkretnych informacji. Ten temat zawiera szczegółowe informacje o każdej części obszaru roboczego.

## <a name="activity-tab"></a>Karta Działanie

Karta **Działanie** zawiera sekcje, w których grupuje się pracowników na podstawie ich etapu w procesie zatrudnienia:

- **Kandydaci do zatrudnienia**
- **Wkrótce zaczyna**
- **Ostatnio zatrudnieni**
- **Zamykanie**
- **Odeszli**

Gdy pracownik znajduje się w jednym z tych etapów, określone akcje są dostępne jako przyciski na karcie lub w menu, które pojawia się po wybraniu wielokropka (**...**) w prawym górnym rogu. W poniższych podsekcjach opisano sekcje karty **Działanie** i listę dostępnych akcji.

### <a name="candidates-to-hire"></a>Kandydaci do zatrudnienia

Sekcja **Kandydaci do zatrudnienia** w obszarze roboczym jest wypełniona z wielu źródeł:

- Jednostka Open Data Protocol (OData)
- Integracja z serwisem LinkedIn
- Dane wprowadzane ręcznie w produkcie

Gdy w sekcji **Kandydaci do zatrudnienia** pojawiają się kandydaci, można wykonać następujące akcje, wybierając wielokropek na karcie kandydata:

- **Odrzuć kandydata**
- **Nie zatrudniać**
- **Zatrudnić**

> [!NOTE]
> Jeśli lista kandydatów jest wypełniana z Microsoft Dataverse, ci sami kandydaci będą wyświetlani we wszystkich podmiotach prawnych, ponieważ podmiot prawny nie został powiązany z kandydatem.

### <a name="starting-soon"></a>Wkrótce zaczyna

W sekcji **Rozpoczęcie wkrótce** zostanie wymieniona lista pracowników, dla których data rozpoczęcia będzie datą w przyszłości. Lista jest posortowana według daty rozpoczęcia. Data rozpoczęcia, która jest najbliższa dzisiejszej dacie, jest wyświetlana jako pierwsza.

Jeśli kierownik nie widnieje na karcie, stanowisko nie zostało przypisane pracownikowi.

> [!NOTE] 
> Zaleca się przypisanie stanowiska do pracownika przed zastosowaniem listy kontrolnej. Czasami zadania dołączania są przypisywane do nowo zatrudnionego menedżera pracownika. Jeśli jednak nie zostanie przydzielone żadne stanowisko, nie można ustalić kierownika nowego pracownika. W takim przypadku zadania związane z wprowadzaniem, które są przeznaczone dla menedżera, zostaną zamiast tego przypisane właścicielowi listy kontrolnej.

Gdy pracownicy pojawią się w sekcji **Rozpoczęcie wkrótce**, są dla nich dostępne następujące akcje:

- Przypisz stanowisko
- Weryfikuj zatrudnienie
- Przypisz stałe wynagrodzenie
- Przypisz wynagrodzenie o zmiennej wysokości
- Wyświetl w hierarchii
- Zastosuj listę kontrolną\*\*

\*\* Ta akcja jest akcją domyślną. Pojawia się on jako przycisk na karcie.

### <a name="recent-hires"></a>Ostatnio zatrudnieni

W sekcji **Ostatnio zatrudnieni** jest wymieniona lista pracowników, dla których data rozpoczęcia należy do przeszłości. Lista jest posortowana według daty rozpoczęcia. Data rozpoczęcia, która jest najbliższa dzisiejszej dacie, jest wyświetlana jako pierwsza.

Domyślnie lista zawiera pracowników zatrudnionych w ciągu ostatnich siedmiu dni. Aby zmienić to ustawienie, na karcie **Parametry Human Resources** na karcie **Ogólne** zdefiniuj ramy czasowe dla parametru **Ostatnio zatrudnieni**. Dane w sekcji **Ostatnio zatrudnieni** mogą być wyświetlane dla określonej liczby dni, miesięcy lub lat. Na przykład, aby wyświetlić listę pracowników, którzy byli zatrudnieni w ciągu ostatnich 14 dni, ustaw w polu **Okres** wartość **14**, a w polu **Jednostka** wartość **Dni**.

> [!NOTE]
> Ustawienia na stronie **parametrów Human Resources** są specyficzne dla firmy. Dlatego przedział czasowy, dla którego przeglądasz ostatnie zatrudnienie, może się różnić w zależności od firmy. Na przykład w firmie USMF możesz chcieć wyświetlić wszystkich nowych pracowników z ostatnich siedmiu dni. Jednak w firmie USSI chcesz wyświetlić wszystkich nowych pracowników z ostatnich 14 dni. W takim przypadku należy otworzyć stronę **Parametry Human Resources** w każdej firmie i w razie potrzeby ustawić parametry.

Jeśli kierownik nie widnieje na karcie, stanowisko nie zostało przypisane pracownikowi.

Gdy pracownicy pojawią się w sekcji **Ostatnio zatrudnieni**, są dla nich dostępne następujące akcje:

- Przypisz stanowisko
- Weryfikuj zatrudnienie
- Stałe wynagrodzenie
- Przypisz wynagrodzenie o zmiennej wysokości
- Wyświetl w hierarchii
- Zastosuj listę kontrolną\*\*

\*\* Ta akcja jest akcją domyślną. Pojawia się on jako przycisk na karcie.

### <a name="exiting"></a>Zamykanie

W sekcji **Odchodzący** jest wymieniona lista pracowników, dla których data zakończenia należy do przyszłości. Lista jest posortowana według daty zakończenia. Data zakończenia, która jest najbliższa dzisiejszej dacie, jest wyświetlana jako pierwsza. 

Domyślnie na liście są wyświetloni pracownicy z datą zakończenia zatrudnienia w ciągu następnych siedmiu dni. Aby zmienić to ustawienie, na karcie **Parametry Human Resources** na karcie **Ogólne** zdefiniuj ramy czasowe dla parametru **Widoki odchodzących pracowników**. Dane w sekcji **Odchodzący** mogą być wyświetlane dla określonej liczby dni, miesięcy lub lat. Na przykład, aby wyświetlić listę pracowników, którzy odchodzą w ciągu następnych 14 dni, ustaw w polu **Okres** wartość **14**, a w polu **Jednostka** wartość **Dni**.

Gdy pracownicy pojawią się w sekcji **Odchodzący**, są dla nich dostępne następujące akcje:

- Zastosuj listę kontrolną\*\*
- Weryfikuj zatrudnienie
- Wyświetl w hierarchii

\*\* Ta akcja jest akcją domyślną. Pojawia się on jako przycisk na karcie.

### <a name="exited"></a>Odeszli

W sekcji **Odeszli** jest wymieniona lista pracowników, dla których data zakończenia należy do przeszłości. Lista jest posortowana według daty zakończenia. Data zakończenia, która jest najbliższa dzisiejszej dacie, jest wyświetlana jako pierwsza.

Domyślnie na liście są wyświetloni pracownicy z datą zakończenia zatrudnienia w ciągu ostatnich siedmiu dni. Aby zmienić to ustawienie, na karcie **Parametry Human Resources** na karcie **Ogólne** zdefiniuj ramy czasowe dla parametru **Widoki pracowników, którzy odeszli**. Dane w sekcji **Odeszli** mogą być wyświetlane dla określonej liczby dni, miesięcy lub lat. Na przykład, aby wyświetlić listę pracowników, którzy odeszli w ciągu ostatnich 14 dni, ustaw w polu **Okres** wartość **14**, a w polu **Jednostka** wartość **Dni**.

Gdy pracownicy pojawią się w sekcji **Odeszli**, są dla nich dostępne następujące akcje:

- Zastosuj listę kontrolną\*\*
- Weryfikuj zatrudnienie
- Wyświetl w hierarchii

\*\* Ta akcja jest akcją domyślną. Pojawia się on jako przycisk na karcie.

## <a name="employee-changes-tab"></a>Karta Zmiany pracowników

Karta **Zmiany pracownika** zawiera listę wszystkich akcji pracowników. Ta lista jest domyślnie niedostępna. Aby włączyć tę funkcję, na stronie **Wspólne parametry Human resources**, na karcie **Akcje dotyczące pracowników** ustaw opcję **Włącz akcje dotyczące pracownika** na wartość **Tak**.

## <a name="position-changes-tab"></a>Karta Zmiany stanowisk

Karta **Zmiany stanowiska** zawiera listę wszystkich akcji stanowisk pracowników. Ta lista jest domyślnie niedostępna. Aby włączyć tę funkcję, na stronie **Wspólne parametry Human resources**, na karcie **Akcje dotyczące pracowników** ustaw opcję **Włącz akcje dotyczące stanowiska** na wartość **Tak**.

## <a name="open-positions-tab"></a>Karta Otwórz stanowiska

Na karcie **Otwarte stanowiska** są wszystkie otwarte stanowiska. Aby stanowiska były widoczne na liście, muszą mieć datę aktywacji dzisiejszą lub wcześniejszą i nie mogą mieć bieżącego przypisania pracownika.

> [!NOTE]
> Na liście jest teraz rozważane przypisanie pracownika. Wszystkie stanowiska, dla których przypisano pracownika z datą przyszłą, będą nadal pojawiać się na liście. Jednak po osiągnięciu daty wejścia w życie przypisania pracownika stanowisko zostanie usunięte z listy.

## <a name="expiring-records-tab"></a>Karta Wygasające rekordy

Na karcie **Wygasające rekordy** znajduje się lista wszystkich pozycji, które wygasły lub wygaśnie dla pracowników w firmie, do których jest zalogowany użytkownik. Na liście są wyświetlane następujące elementy:

- **Certyfikaty**
- **Identyfikator**
- **Okresy próbne**
- **Kontrole**
- **Testy**

Aby określić, czy lista zawiera wygasłe rekordy, czy rekordy wygasające, na stronie **Parametry Human Resources** na karcie **Ogólne** zdefiniuj ramy czasowe dla rekordów **Wygasające rekordy** lub **Wygasłe rekordy**. Dane na karcie **Wygasające rekordy** mogą być wyświetlane dla określonej liczby dni. Na przykład aby wyświetlić listę rekordów, które wygasną w ciągu następnych 14 dni, ustaw w polu **Liczba dni** wartość **14**.

> [!NOTE] 
> Jeśli dla rekordów **wygasłych** lub **Wygasających rekordów** ustawisz wartość **0** na stronie **Parametry Human Resources**, na liście nie będą wyświetlane żadne z tych rekordów.

## <a name="employees-tile"></a>Kafelek pracowników eedytnych

Kafelek **Pracownicy** umożliwia zliczanie wszystkich pracowników zatrudnionych w firmie, do których użytkownik jest obecnie zalogowany. Po wybraniu **kafelka Pracownicy** na nowej stronie są widać szczegóły dotyczące pracowników.

## <a name="contractors-tile"></a>Kafelek zleceniobiorcy

Kafelek **Zleceniobiorcy** umożliwia zliczanie wszystkich zleceniobiorców zatrudnionych w firmie, do których użytkownik jest obecnie zalogowany. Po wybraniu **kafelka Zleceniobiorcy** na nowej stronie są widać szczegóły dotyczące zleceniobiorcy.

## <a name="open-positions-tile"></a>Kafelek Otwórz stanowiska

Kafelek **otwarte stanowiska** zapewnia zliczanie wszystkich otwartych stanowisk. Po wybraniu **kafelka Otwarte stanowiska** na nowej stronie są widać szczegóły dotyczące otwartych stanowisk. Aby zostały uwzględnione w liczeniu, stanowiska muszą mieć datę aktywacji dzisiejszą lub wcześniejszą i nie mogą mieć bieżącego przypisania pracownika.

> [!NOTE]
> Na kafelku jest teraz rozważane przypisanie pracownika. Każde stanowisko, które ma przydział pracownika z datą przyszłą, będzie nadal uwzględniane w liczeniu. Jednak po osiągnięciu daty wejścia w życie przydziału pracownika stanowisko zostanie wyłączone z liczenia.

## <a name="approvals-tile"></a>Kafelki zatwierdzeń

Kafelek **Zatwierdzenia** zawiera liczbę wszystkich elementów przepływu pracy, które oczekują na zatwierdzenie przez bieżącego użytkownika. Po wybraniu kafelka **Zatwierdzania** na nowej stronie są widać szczegóły elementów przepływu pracy, które wymagają zatwierdzenia.

## <a name="address-changes-tile"></a>Kafelek zmian adresu

Kafelek **zmian adresu** zawiera liczbę wszystkich zmian adresów, które wystąpiły podczas liczby dni określonej na stronie **Parametry Human Resources**. Po wybraniu kafelka **Zmiany adresu** na nowej stronie są wyświetlane szczegółowe informacje o wszelkich zmianach adresu. W prawym górnym rogu strony możesz wybrać **Dołącz przyszłe zmiany adresu**, aby wyświetlić zmiany w adresie z przyszłą datą.

Aby uzyskać więcej informacji dotyczących sposobu wyświetlania zmian adresów i zarządzania nimi, zobacz temat [Wyświetlanie zmian adresów i zarządzanie nimi](hr-personnel-view-address-changes.md).
