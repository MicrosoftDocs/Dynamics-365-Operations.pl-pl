---
title: Tworzenie planu urlopów i nieobecności
description: W programie Dynamics 365 Human Resources można tworzyć plany różnego rodzaju urlopów.
author: andreabichsel
manager: tfehr
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f90e49c6191134a99b306fdc9de6b46c07844dea
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463413"
---
# <a name="create-a-leave-and-absence-plan"></a>Tworzenie planu urlopów i nieobecności

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Zdefiniuj plany urlopów i nieobecności w programie Dynamics 365 Human Resources dla każdego typu oferowanego urlopu. Plany urlopów i nieobecności mogą być naliczane z różnymi częstotliwościami, na przykład corocznie, miesięczne czy co pół miesiąca. Plan można również zdefiniować jako przydział, gdzie jedno naliczanie odbywa się w określonym dniu. Można na przykład utworzyć plan przyznający corocznie urlopy na żądanie.

Warstwowe plany urlopów umożliwiają pracownikom otrzymywanie świadczeń na podstawie ilości czasu przepracowanego w organizacji. Plany warstwowe umożliwiają automatyczne rejestrowanie na dodatkowe godziny świadczeń.

Istnieje możliwość określenia maksymalnych kwot przeniesienia lub salda minimalnego, aby zapewnić, że pracownicy wykorzystują tylko godziny świadczeń, które zgromadzili.

Na przykład w planie warstwowym można przyznać 80 godzin płatnego urlopu (PTO) nowym pracownikom. Następnie można przyznać 120 godzin po 60 miesiącach pracy.

Można również tworzyć urlopy zależne od stanowiska, na przykład urlopy tylko dla członków wyższej kadry kierowniczej.

## <a name="create-a-leave-plan"></a>Tworzenie planu urlopów

1. Na stronie **Urlopy i nieobecności** wybierz opcję **Utwórz nowy plan**.

2. W obszarze **Szczegóły** wypełnij pola **Nazwa**, **Data rozpoczęcia**, **Opis** i **Typ urlopu** dla swojego planu.

Jeśli funkcja **Konfigurowanie wielu typów urlopu dla jednego planu urlopów i nieobecności** jest włączona, typy urlopów są konfigurowane w **Harmonogram naliczania**, a nie w obszarze **Szczegóły**. Dla każdego rekordu w tabeli harmonogramu naliczania można zdefiniować typ urlopu. Ponadto, gdy ta funkcja jest włączona, należy skorzystać z nowych jednostek danych dla integracji lub innych scenariuszy, w których trzeba skorzystać z jednostek. 

Nowe jednostki:

- Transakcja banku urlopów i nieobecności wer. 2
- Rejestracja do urlopów i nieobecności wer. 2
- Warstwa planu urlopów i nieobecności wer. 2
- Plan urlopów i nieobecności wer. 2
- Wniosek urlopowy o czas wolny wersja 2

 > [!IMPORTANT]
   > Po włączeniu tej funkcji nie można jej wyłączyć.

3. Zdefiniuj naliczenia na karcie **Naliczenia**. Naliczenia określają, kiedy i jak często pracownikowi jest przyznawany czas wolny. W tym kroku zdefiniujesz zasady określające, kiedy naliczenia mają być przyznawane, oraz zasady dotyczące proporcjonalnego naliczania długości urlopów.

   1. Wybierz wartość z pola rozwijanego **Częstotliwość naliczania**:

      - Codziennie
      - Cykl tygodniowy
      - Co dwa tygodnie
      - Co pół miesiąca
      - Miesięcznie
      - Kwartalna
      - Co pół roku
      - Co rok
      - Brak

   2. Wybierz opcję z pola rozwijanego **Podstawa okresu naliczania**, aby określić datę początkową używaną do obliczania okresów naliczania:

      | Podstawa okresu naliczania | Opis |
      | --- | --- |
      | **Data początkowa planu** | Data rozpoczęcia okresu naliczania to dzień, w którym plan staje się dostępny. |
      | **Data specyficzna dla pracownika** | Data rozpoczęcia okresu naliczania zależy od zdarzenia dotyczącego pracownika etatowego:</br><ul><li>Niestandardowe (należy określić podstawę daty naliczania osobno dla każdej rejestracji)</li><li>Rocznica</li><li>Pierwotna data zatrudnienia</li><li>Data stażu pracy</li><li>Skorygowana data rozpoczęcia pracownika</li><li>Data rozpoczęcia pracownika</li></ul> |

   3. Wybierz opcję z pola rozwijanego **Data przyznania naliczenia**:

      - **Data zakończenia okresu naliczania** — pracownikowi jest przyznawany czas wolny ostatniego dnia okresu przyznawania. Aby naliczyć poprawną kwotę, proces naliczania musi obejmować cały okres. Jeśli na przykład okres naliczania trwa od 1 stycznia 2020 r. do 31 stycznia 2020 r., należy wykonać proces naliczenia na dzień 1 lutego 2020 r., aby uwzględnić styczeń.

      - **Data rozpoczęcia okresu naliczania** — pracownikowi jest przyznawany czas wolny pierwszego dnia okresu przyznawania.

   4. Wybierz opcję z pola rozwijanego **Zasady dotyczące naliczania przy rejestracji**. Ta wartość określa sposób obliczania naliczenia, gdy pracownik rejestruje się w połowie okresu naliczania.

      - **Proporcjonalna** — zakres dat między datą początkową i datą rejestracji jest używana do określania różnicy w dniach. Ta różnica jest stosowana podczas przetwarzania naliczeń.

      - **Pełne naliczenia** — pełna kwota naliczeń w oparciu o warstwę jest przyznawana podczas wstępnego przetwarzania naliczania.

      - **Bez naliczenia** — żadne naliczenie nie jest przyznawane aż do rozpoczęcia następnego okresu naliczania.

   5. Wybierz opcję z pola rozwijanego **Zasady dotyczące naliczania przy wyrejestrowaniu**. Ta wartość określa sposób obliczania naliczenia, gdy pracownik wyrejestruje się w połowie okresu naliczania.

      - **Proporcjonalna** — zakres dat między datą początkową i datą rejestracji jest używana do określania różnicy w dniach. Ta różnica jest stosowana podczas przetwarzania naliczeń.

      - **Pełne naliczenia** — pełna kwota naliczeń w oparciu o warstwę jest przyznawana podczas wstępnego przetwarzania naliczania.

      - **Bez naliczenia** — żadne naliczenie nie jest przyznawane aż do rozpoczęcia następnego okresu naliczania.

4. Określ harmonogramie naliczania na karcie **Harmonogram**. Harmonogram naliczania określa:

   - Sposób naliczania czasu wolnego dla pracownika etatowego
   - Ilości naliczone dla pracownika etatowego
   - Ilości przenoszone na następny okres

   Można tworzyć warstwy, aby przyznawać czas wolny na podstawie różnych poziomów.

   Jeśli Twoja firma rozlicza pracowników godzinowo, można przyznawać czas wolny na podstawie liczby przepracowanych godzin, a nie stażu pracy w organizacji. Informacje o liczbie przepracowanych godzin są zazwyczaj przechowywane w systemie rejestracji czasu pracy. Można zaimportować przepracowane godziny zwykłe i nadgodziny z systemu rejestracji czasu pracy, a następnie wykorzystywać je jako podstawę do przyznawania pracownikom urlopów.
   
    1. Wybierz opcję z pola rozwijanego **Typ naliczania**:

      - **Miesiące zatrudnienia** — podstawą harmonogramu naliczania jest liczba miesięcy zatrudnienia w firmie.

      - **Przepracowane godziny** — podstawą harmonogramu naliczania są przepracowane godziny. Aby uzyskać więcej informacji o naliczeniach w oparciu o przepracowane godziny, zobacz [Naliczanie czasu wolnego na podstawie liczby przepracowanych godzin](hr-leave-and-absence-plans.md?accrue-time-off-based-on-hours-worked).

      Aby uzyskać więcej informacji o saldach naliczenia, zobacz [Naliczanie czasu wolnego na podstawie liczby przepracowanych godzin](hr-leave-and-absence-plans.md?enrollments-and-balances).

    2. Wprowadź wartości w tabeli harmonogramu naliczania:

      - **Miesiące zatrudnienia** — minimalna liczba miesięcy, które pracownicy muszą przepracować, aby mieć prawo do naliczeń. Jeśli wartość minimalna nie jest wymagana, wpisz 0.

      - **Przepracowane godziny** — minimalna liczba godzin, które pracownicy muszą przepracować w okresie naliczania, aby mieć prawo do naliczeń. Jeśli wartość minimalna nie jest wymagana, wpisz 0.

      - **Kwota naliczenia** — liczba godzin lub dni, które zostaną naliczone pracownikom w okresie. Okres zależy od częstotliwości naliczania.

      - **Minimalne saldo** — można użyć wartości ujemnej minimalnego salda, jeśli pracownicy mogą zażądać więcej urlopu niż mają dostępnego.

      - **Maksymalne przeniesienie na następny okres** — proces naliczania dostosowuje salda urlopów przekraczające maksymalne saldo przeniesienia na następny okres w rocznicą daty rozpoczęcia.

      - **Przyznana ilość** — początkowa liczba godzin lub dni, które pracownicy otrzymują, gdy po raz pierwszy zarejestrują się w planie urlopów. Kwota nie jest naliczana dla każdego okresu naliczania.
      
Jeśli funkcja **Konfigurowanie wielu typów urlopu dla jednego planu urlopów i nieobecności** jest włączona, należy wybrać opcję w polu **Typ urlopu**. 

   > [!IMPORTANT]
   > Po włączeniu tej funkcji nie można jej wyłączyć.

Po włączeniu funkcji **Używanie przeliczenia na pełne etaty** moduł Human Resources będzie korzystał z przeliczenia na pełne etaty (FTE) zdefiniowanego dla stanowiska w celu proporcjonalnego naliczania urlopu pracownikowi. Na przykład jeśli przeliczenie na pełne etaty to 0,5, a naliczona ilość wynosi 10, pracownikowi zostanie naliczone 5. Tej funkcji można używać tylko po włączeniu wielu typów urlopów.  

5. Wybierz opcję **Zapisz**.

## <a name="accrue-time-off-based-on-hours-worked"></a>Naliczanie czasu wolnego na podstawie liczby przepracowanych godzin

Jeśli Twoja firma rozlicza pracowników godzinowo, można przyznawać czas wolny na podstawie liczby przepracowanych godzin, a nie stażu pracy w organizacji. Informacje o liczbie przepracowanych godzin są zazwyczaj przechowywane w systemie rejestracji czasu pracy. Można zaimportować przepracowane godziny zwykłe i nadgodziny z systemu rejestracji czasu pracy, a następnie wykorzystywać je jako podstawę do przyznawania pracownikom urlopów.

W przypadku wybrania opcji liczby przepracowanych godzin jako typu naliczania można używać dwóch typów godzin do naliczania: zwykłe i nadgodziny. Mechanizm przetwarzania naliczeń w planach opartych na liczbie przepracowanych godzin wykorzystuje częstotliwość naliczania oraz podstawę okresu naliczania do określenia liczby godzin, jaką trzeba naliczyć.

### <a name="annual-accrual-frequency"></a>Roczna częstotliwość naliczania

| Data przyznania naliczenia    | Warstwa liczby przepracowanych godzin    | Kwota naliczenia        | Daty przepracowanych godzin   | Faktycznie przepracowane godziny| Nagroda               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 01.01.2018–31.12.2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 01.01.2018–31.12.2018  | 2000                | 0                 |


### <a name="monthly-accrual-frequency"></a>Miesięczna częstotliwość naliczania

| Data przyznania naliczenia    | Warstwa liczby przepracowanych godzin    | Kwota naliczenia        | Daty przepracowanych godzin   | Faktycznie przepracowane godziny| Nagroda               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 01.08.2018–31.08.2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 01.08.2018–31.08.2018   | 184                 | 3                   |

### <a name="semi-monthly-accrual-frequency"></a>Dwutygodniowa częstotliwość naliczania

| Data przyznania naliczenia    | Warstwa liczby przepracowanych godzin    | Kwota naliczenia        | Daty przepracowanych godzin   | Faktycznie przepracowane godziny| Nagroda               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 16.08.2018–31.08.2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 16.08.2018–31.08.2018  | 75                  | 0                   |

### <a name="weekly-accrual-frequency"></a>Tygodniowa częstotliwość naliczania

| Data przyznania naliczenia    | Warstwa liczby przepracowanych godzin    | Kwota naliczenia        | Daty przepracowanych godzin   | Faktycznie przepracowane godziny| Nagroda               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 27.08.2018–31.08.2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 27.08.2018–31.08.2018  | 35                  | 0                   |

### <a name="employee-assigned-leave-plans"></a>Przypisane plany urlopów przypisane do pracownika

W przypisanych pracownikowi planach urlopów z naliczaniem według liczby przepracowanych godzin są wyświetlane podstawa warstwy i typ godzin. Dla aktywnych planów jest również wyświetlana rzeczywista liczba przepracowanych godzin w okresach naliczania według stanu na bieżący dzień.

### <a name="loading-data"></a>Ładowanie danych

Faktycznie przepracowane godziny można zaimportować za pomocą jednostki **Godziny przepracowane do podstawy urlopu i nieobecności** dostępnej w module Zarządzanie danymi. Jeśli są używane kalendarze czasu pracy, aparat importu sprawdza, czy liczba zwykłych przepracowanych godzin nie przekracza liczby godzin określonej w dziennym harmonogramie w kalendarzu. Ponadto aparat importu sprawdzi, czy liczba godzin przepracowanych w danym dniu nie przekracza 24. 

Następujące informacje są potrzebne w celu zaimportowania liczby faktycznie przepracowanych godzin do wykorzystania w procesie naliczania urlopu:

- Numer pracownika 
- Data dnia pracy
- Typ
- Godziny

Z jedną datą może być skojarzony tylko jeden element każdego typu.

| Numer pracownika       | Data dnia pracy           | Typ                  | Godziny                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Zwykłe               | 8                    |       
| 000337                | 8/7/2018             | Zwykłe               | 8                    |
| 000337                | 8/7/2018             | Nadgodziny              | 3                    |
| 000337                | 8/8/2018             | Zwykłe               | 8                    |
| 000337                | 8/7/2018             | Zwykłe               | 8                    |
| 000337                | 8/9/2018             | Zwykłe               | 8                    |

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

Naliczenia są przetwarzane 1 stycznia 2019 (1/1/2019), aby uwzględnić cały okres.

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

Naliczenia są przetwarzane 1 maja 2018 (5/1/2018), aby uwzględnić cały okres.

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

Naliczenia są przetwarzane 1 maja 2018 (5/1/2018), aby uwzględnić cały okres.

**Wyniki**

| Kwota naliczenia | Minimalne saldo | Maksymalne przeniesienie na następny okres | Kwota żądania | Bieżące saldo (z dnia 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Bieżące saldo (7) = naliczona kwota (5 × 3) — kwota żądania (8)

### <a name="forecasted-balance"></a>Prognozowane saldo

*Prognozowane saldo* jest kwotą urlopu dostępną w przyszłości. Korekty naliczeń i przeniesień na następny okres są prognozowane do tej daty.

W module Human Resources jest stosowana następująca formuła:

Saldo prognozowane na poniedziałek = Saldo bieżące – Żądania + Naliczenia – Korekta o przeniesienia na następny okres

### <a name="forecasted-balance-examples"></a>Przykład prognozowanego salda

#### <a name="annual-plan"></a>Plan roczny

**Konfiguracja planu**

| Data początkowa planu | Data rejestracji | Częstotliwość naliczania | Podstawa okresu naliczania | Data przyznania naliczenia    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Roczny            | Data początkowa planu      | Koniec okresu naliczania |

Naliczenia są przetwarzane 15 lutego 2019 (2/15/2019), aby uwzględnić cały okres.

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

Naliczenia są przetwarzane 15 lutego 2019 (2/15/2019), aby uwzględnić cały okres.

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

Naliczenia są przetwarzane 15 lutego 2019 (2/15/2019), aby uwzględnić cały okres.

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
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1.00           | 9/1/2018        | 3.00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1.00           | 9/1/2018        | 2.00    |

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md)
- [Naliczanie do planów urlopów i nieobecności](hr-leave-and-absence-accrue.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]