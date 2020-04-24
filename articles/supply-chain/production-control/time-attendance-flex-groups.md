---
title: Grupy elastycznego czasu pracy
description: W tym temacie opisano sposób wykorzystywania grup elastycznego czasu pracy w module Czas i frekwencja.
author: johanhoffmann
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgFlexGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 753874e4cf1d0403e9c422f44d159b11ef1d7247
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210233"
---
# <a name="flex-groups"></a>Grupy elastycznego czasu pracy

[!include[banner](../includes/banner.md)]

Funkcja elastycznych godzin pracy pozwala firmom minimalizować płacenie za nadgodziny poprzez oferowanie pracownikom dodatkowego czasu wolnego w okresach mniejszego obciążenia pracą. Ta funkcja ma zastosowanie na przykład w segmentach, gdzie występują sezonowe wahania ilości pracy.

Za pomocą grup elastycznego czasu pracy można skonfigurować następujące reguły i zasady dotyczące elastycznych godzin pracy pracownika:

- Zasady regulowania elastycznego czasu pracy
- Reguła obliczania salda elastycznego czasu pracy pracownika

## <a name="set-up-flexible-working-hours-in-flex-groups"></a>Konfigurowanie elastycznych godzin pracy w grupach elastycznego czasu pracy

- Wybierz kolejno opcje **Czas i frekwencja** \> **Ustawienia** \> **Grupy** \> **Grupy elastycznego czasu pracy**, aby zdefiniować grupy elastycznego czasu pracy dla elastycznych godzin pracy.

## <a name="associate-workers-with-flex-groups"></a>Kojarzenie pracowników z grupami elastycznego czasu pracy

- Wybierz kolejno opcje **Czas i frekwencja** \> **Ustawienia** \> **Pracownicy odpowiedzialni za rejestrację czasu**.

## <a name="rules-for-flex-regulations"></a>Zasady regulowania elastycznego czasu pracy

Zasad regulowania elastycznego czasu pracy można używać do określania limitów elastycznego czasu pracy, czyli minimalnej i maksymalnej liczby godzin dozwolonych na koncie elastycznego czasu pracy pracownika. Limity elastycznego czasu pracy konfiguruje się w grupie elastycznego czasu pracy. Po przekroczeniu limitów elastycznego czasu pracy można skorygować saldo elastycznego czasu pracy i płacę pracownika.

W przypadku przekroczenia dozwolonego minimalnego salda elastycznego czasu pracy pracownika (to znaczy jeśli liczba godzin na koncie elastycznego czasu pracy jest niższa niż ustalone minimum), można użyć tych metod do skorygowania salda elastycznego czasu pracy pracownika poprzez wyregulowanie elastycznego czasu pracy:

- Konto elastycznego czasu pracy pracownika można skorygować na ustalone dozwolone minimum, ale bez pomniejszania płacy pracownika za liczbę godzin, na jaką saldo konta elastycznego czasu pracy jest mniejsze niż dozwolone minimum.
- Płacę pracownika można pomniejszyć za liczbę godzin, na jaką saldo konta elastycznego czasu pracy jest mniejsze niż dozwolone minimum. To zmniejszenie odbywa się przez generowanie elementów płacowych dla określonego typu płacy mających dodatnią lub ujemną jednostkę płacy.

W przypadku przekroczenia dozwolonego maksymalnego salda elastycznego czasu pracy pracownika można użyć tych metod do skorygowania salda elastycznego czasu pracy pracownika poprzez wyregulowanie elastycznego czasu pracy:

- Konto elastycznego czasu pracy pracownika można skorygować z powrotem na ustalone dozwolone maksimum, ale bez powiększania płacy pracownika za liczbę godzin przepracowaną ponad dozwolone maksimum.
- Godziny, jakie pracownik przepracował ponad dozwolone maksimum, można przekształcić na zapłatę. Ta konwersja odbywa się przez generowanie elementów płacowych dla określonego typu płacy.

Saldo elastycznego czasu pracy można korygować w następujących momentach:

- Podczas eksportowaniu pliku płatności opartego na danych listy płac za pomocą zadania **Przenieś do płac**. Dane listy płac są generowane podczas przenoszenia rejestracji pracownika ze strony **Zatwierdzanie**.
- W trakcie przetwarzania zadania **Koryguj salda elastycznego czasu pracy**.

> [!NOTE]
> Regulacje elastycznego czasu nie następują podczas codziennego zatwierdzania i przenoszenia rejestracji pracowników na stronie **Zatwierdzanie**.

## <a name="principle-for-calculating-a-workers-flex-balance"></a>Reguła obliczania salda elastycznego czasu pracy pracownika

Reguła obliczania liczby godzin, o jaką należy skorygować saldo elastycznego czasu pracy pracownika, jest ustawiana poprzez skonfigurowanie w grupie elastycznego czasu pracy. Wybierz kolejno opcje **Czas i frekwencja** \> **Ustawienia** \> **Grupy** \> **Grupy elastycznego czasu pracy**. 

Można używać następujących dwóch reguł:

- **Czas** — Elastyczne godziny pracy pracownika są obliczane tylko na podstawie zarejestrowanego czasu pracownika w danym dniu. Podczas obliczania dziennych rejestracji pracownika liczby godzin dodania i odjęcia elastycznego czasu pracy dla tego dnia są obliczane na podstawie stref dodawania i odejmowania elastycznego czasu pracy zdefiniowanych w profilu czasu pracownika.
- **Typy płac** — Elastyczne godziny pracy pracownika są obliczane na podstawie zarobków z tytułu typów płac dla dodania i odjęcia elastycznego czasu pracy zdefiniowanych w umowie płacowej pracownika. Umowa płacowa jest skojarzona z pracownikiem odpowiedzialnym za rejestrację czasu. Można używać typów płac do zarządzania kontami elastycznego czasu pracy, jeśli na przykład chcesz zwiększyć saldo konta elastycznego czasu pracy pracownika o określony współczynnik w jednej lub więcej stref elastycznego czasu pracy.

### <a name="scenario-1-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-minimum-is-exceeded"></a>Scenariusz 1: Korygowanie płacy pracownika i salda na koncie elastycznego czasu pracy z powodu przekroczenia dozwolonego minimalnego salda elastycznego czasu pracy

Pracownik, który może pracować w elastycznym wymiarze godzin, ma ujemne saldo konta elastycznego czasu pracy.

- **Konto elastycznego czasu pracy:** -4

Pracownik jest skojarzony z grupą elastycznego czasu pracy, który ma następującą konfigurację:

- **Minimalne saldo elastycznego czasu pracy:** -0,5
- **Typ płatności minimalnej:** 1302
- **Współczynnik typu płacy:** -1,00

Jak wskazuje różnica między kontem elastycznego czasu pracy pracownika a jego dozwolonym minimalnym saldem elastycznego czasu pracy, pracownik przekroczył dozwolone minimalne saldo elastycznego czasu pracy o 3,5 godziny.

Gdy administrator listy płac przesyła dane płacy pracownika za pomocą zadania **Przenieś do płac** lub **Korekta elastycznego czasu pracy**, są wykonywane następujące korekty:

- Konto elastycznego czasu pracy pracownika jest korygowane o 3,5 godziny. W związku z tym saldo elastycznego czasu pracy wynoszące -4,0 godziny zostaje skorygowane na dozwolone minimalne saldo elastycznego czasu pracy pracownika wynoszące -0,5 godziny.
- Jest tworzony element płacowy dla typu płacy 1302. Ten element płacowy ma jednostkę płacy -3,5 godziny, która zostanie odjęta od wynagrodzenia pracownika. W tym przypadku jednostka płacowa jest liczbą ujemną, ponieważ dodatnia korekta na 3,5 godziny jest mnożona przez ujemny współczynnik typu płacy -1,0 zdefiniowany w grupie elastycznego czasu pracy. Ten element płacowy będzie częścią pliku płatności wygenerowanego przez zadanie **Przenieś do płac**.

### <a name="scenario-2-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-maximum-is-exceeded"></a>Scenariusz 2: Korygowanie płacy pracownika i salda na koncie elastycznego czasu pracy z powodu przekroczenia dozwolonego maksymalnego salda elastycznego czasu pracy

Pracownik, który może pracować w elastycznym wymiarze godzin, ma dodatnie saldo konta elastycznego czasu pracy.

- **Konto elastycznego czasu pracy:** 6

Pracownik jest skojarzony z grupą elastycznego czasu pracy, który ma następującą konfigurację:

- **Maksymalne saldo elastycznego czasu pracy:** 2,0
- **Typ płatności minimalnej:** 1302
- **Współczynnik typu płacy:** -1,0

Jak wskazuje różnica między kontem elastycznego czasu pracy pracownika a jego dozwolonym maksymalnym saldem elastycznego czasu pracy, pracownik przekroczył dozwolone maksymalne saldo elastycznego czasu pracy o 4,0 godziny.

Gdy administrator listy płac przesyła dane płacy pracownika za pomocą zadania **Przenieś do płac** lub **Korekta elastycznego czasu pracy**, są wykonywane następujące korekty:

- Konto elastycznego czasu pracy pracownika jest korygowane o -4,0 godziny. W związku z tym saldo elastycznego czasu pracy wynoszące 6,0 godziny zostaje skorygowane na dozwolone maksymalne saldo elastycznego czasu pracy pracownika wynoszące 2,0 godziny.
- Jest tworzony element płacowy dla typu płacy 1302. Ten element płacowy ma jednostkę płacy 4,0 godziny, która zostanie dodana do wynagrodzenia pracownika. W tym przypadku jednostka płacowa jest liczbą dodatnią, ponieważ ujemna korekta na 4,0 godziny jest mnożona przez ujemny współczynnik typu płacy -1,0 zdefiniowany w grupie elastycznego czasu pracy. Ten element płacowy będzie częścią pliku płatności wygenerowanego przez zadanie **Przenieś do płac**.

### <a name="scenario-3-managing-a-workers-flex-balance-based-on-pay-types"></a>Scenariusz 3: Zarządzanie saldem elastycznego czasu pracy pracownika na podstawie typów płac

Jak już wcześniej wyjaśniono, kontami elastycznego czasu pracy można zarządzać na podstawie czasu zarejestrowanego w strefach dodawania i odejmowania elastycznego czasu pracy zdefiniowanych w profilu czasu pracownika lub na podstawie typów płac zdefiniowanych w umowach płacowych pracownika. Jeśli są używane typy płac, konto elastycznego czasu pracy pracownika jest korygowane o elementy płacowe wygenerowane podczas przenoszenia rejestracji pracownika ze strony **Zatwierdzanie**. Można używać typów płac do zarządzania kontami elastycznego czasu pracy, jeśli na przykład chcesz zwiększyć saldo konta elastycznego czasu pracy pracownika o określony współczynnik w jednej lub więcej stref elastycznego czasu pracy.

W tym scenariuszu jest wykorzystywany następujący profil elastycznego czasu pracy, który reprezentuje dzień pracy.

| Typ profilu  | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      |
|---------------|----------|----------|
| Elastyczny czas pracy (+)         | 12.00 | 08.00 |
| Wejście      | 08.00 | 08.00 |
| Elastyczny czas pracy -         | 08.00 | 09.00 |
| Czas standardowy | 09.00 | 11.30 |
| Płatna przerwa    | 11.30 | 12.00 |
| Elastyczny czas pracy -         | 12.00 | 16.00 |
| Wyrejestruj się     | 16.00 | 16.00 |
| Elastyczny czas pracy (+)         | 16.00 | 12.00 |

W tym przypadku chcesz mieć możliwość zarządzania saldem elastycznego czasu pracy pracownika na podstawie typów płac. W związku z tym w grupie elastycznego czasu pracy pracownika w opcji **Na podstawie typów płac** należy ustawić wartość **Tak**.

W celu uwzględnienia elastycznych godzin pracy należy również zdefiniować nowy typ płacy. W tym scenariuszu typ płacy otrzymuje nazwę **FlexCnt**.

| Typ płatności | opis  |
|----------|--------------|
| FlexCnt  | Licznik elastycznego czasu pracy |

Następnie wykonaj poniższe kroki, aby skonfigurować typ płacy i dodać wiersze nowego typu do profilu płacy.

1. Wybierz kolejno opcje **Czas i frekwencja** \> **Ustawienia** \> **Grupy** \> **Grupy elastycznego czasu pracy** i kliknij przycisk **Nowy**.
2. W polach **Elastyczny czas pracy +** i **Elastyczny czas pracy -** określić nowy typ płacy **FlexCnt**.
3. Wybierz kolejno opcje **Czas i frekwencja** \> **Ustawienia** \> **Umowy płacowe**, a następnie wybierz opcję **Wiersze umowy**.
4. Dla dnia **Poniedziałek** w typie profilu **Elastyczny czas pracy +** dodaj następujące trzy wiersze.

    | Typ płatności | opis  | Od godziny | Do godziny  | Minimum | Maksimum | Współczynnik |
    |----------|--------------|-----------|----------|---------|---------|--------|
    | FlexCnt  | Licznik elastycznego czasu pracy | 12.00  | 18.00 | 00.00   | 00.00   | 1.00   |
    | FlexCnt  | Licznik elastycznego czasu pracy | 18.00  | 12.00 | 00.00   | 02.00   | 1.50   |
    | FlexCnt  | Licznik elastycznego czasu pracy | 18.00  | 12.00 | 02.00   | 06.00   | 2.00   |

    > [!NOTE]
    > Każdy wiersz jest używany dla innego przedziału czasu i ma inny współczynnik. Elastyczne godziny pracy, które pracownik przepracowuje w przedziale czasu, są mnożone przez współczynnik dla tego wiersza. Na przykład godziny przepracowane w przedziale od 18:00 do 20:00 są mnożone przez 1,50. Współczynnik jest określany w polu **Współczynnik** na karcie **Ogólne** na stronie **Wiersze umowy płacowej**.

Pracownik wprowadza następujące rejestracje dla dnia.

| Typ rejestracji arkusza | Rozpocznij    | Zamknięcie zlecenia produkcyjnego      |
|---------------------------|----------|----------|
| Wejście                  | 7.00 | 7.00 |
| Zadanie produkcyjne            | 7.00 | 21.00 |
| Wyrejestruj się                 | 21.00 | 21.00 |

Ilość, za jaką należy zapłacić, jest obliczana na stronie **Zatwierdzanie** w oparciu o rejestrację pracownika. Po obliczeniu rejestracji wynik można obejrzeć na karcie **Czasy**. W tym scenariuszu interesują Cię następujące pola:

| Elastyczny czas pracy + | Elastyczny czas pracy - | Czas  | Czas płatny |
|--------|--------|-------|----------|
| 6,00   | 0,00   | 13.50 | 08.00    |

Ilość dodanego elastycznego czasu pracy wynosi sześć godzin, a obliczenie jest oparte na strefach elastycznego czasu pracy w profilu czasu. Ta ilość składa się z jednej godziny dodanego elastycznego czasu pracy od 07.00:00 do 08.00 oraz 5 godzin dodanego elastycznego czasu od 16.00 do 21.00.

Podczas przenoszenia rejestracji można zauważyć, że ilość dodanego elastycznego czasu pracy została zmieniona z 6,0 na 8,0 godzin.

| Elastyczny czas pracy + | Elastyczny czas pracy - | Czas  | Czas płatny |
|--------|--------|-------|----------|
| 8.00   | 0,00   | 13.50 | 08.00    |

Ta zmiana następuje po przeniesieniu, ponieważ elastyczne godziny pracy zostały obliczone na podstawie typów płac, a nie czasu. W poniższej tabeli przedstawiono sposób obliczenia ośmiu godzin:

| od     | do       | Czas | Współczynnik    | Konto elastycznego czasu pracy |
|----------|----------|------|-----------|--------------|
| 7.00 | 08.00 | 1    | 1         | 1            |
| 16.00 | 18.00 | 2    | 1         | 2            |
| 18.00 | 20.00 | 2    | 1.5       | 3            |
| 20.00 | 21.00 | 1    | 2         | 2            |
|          |          |      | **Suma** | **8**        |
