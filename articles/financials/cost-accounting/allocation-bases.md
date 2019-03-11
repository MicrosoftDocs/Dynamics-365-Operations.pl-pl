---
title: Podstawy alokacji
description: Ten temat zawiera informacje dotyczące podstaw alokacji. Podstawy alokacji są kluczowymi składnikami w rachunku kosztów i zwykle służą do alokowania kosztów ogólnych.
author: AndersGirke
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 92824cf0fb5ad361090d8dccfd64353d2c16317c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "311687"
---
# <a name="allocation-bases"></a>Podstawy alokacji 

[!include [banner](../includes/banner.md)]

Podstawa alokacji stanowi bazę, w oparciu o którą moduł Rachunek kosztów przydziela koszty ogólne. Podstawą alokacji może być ilość, np. używana liczba roboczogodzin, zużywana liczba kilowatogodzin (kWh) lub zajmowana powierzchnia (w stopach lub metrach kwadratowych). Podstawy alokacji przeważnie są używane do przypisywania kosztów ogólnych do wytwarzanych zapasów. Na przykład dział IT alokuje swoje wydatki według liczby komputerów używanej w poszczególnych działach.

Istnieją trzy typy podstaw alokacji w rachunku kosztów:

- Podstawy alokacji wstępnie zdefiniowanych elementów członkowskich wymiarów
- Podstawy alokacji hierarchii
- Podstawy alokacji formuły

## <a name="predefined-dimension-member-allocation-bases"></a>Podstawy alokacji wstępnie zdefiniowanych elementów członkowskich wymiarów

Wstępnie zdefiniowane podstawy alokacji elementów członkowskich wymiarów są tworzone automatycznie podczas tworzenia elementów członkowskich wymiarów o jednym z następujących typów:

- Elementy członkowskie wymiaru statystycznego
- Elementy członkowskie wymiaru składnika kosztu

> [!NOTE]
> Wstępnie zdefiniowane podstawy alokacji elementów członkowskich wymiarów oparte na elemencie członkowskim wymiaru składnika kosztów uwzględniają wartości tylko z dostawcy źródła danych, takiego jak księga główna lub budżet.

### <a name="example-1-use-a-cost-element-dimension-member-as-the-allocation-base"></a>Przykład 1: Używanie elementu członkowskiego wymiaru składnika kosztu jako podstawy alokacji
W tym przykładzie pokazano, jak utworzyć regułę alokacji kosztów w celu przydzielania składnika kosztu 10002 (Ubezpieczenia pracowników) do salda rejestrowanego w składniku kosztu 10001 (Wynagrodzenia). Reguła alokacji jest definiowana na podstawie stosunku wynagrodzeń w poszczególnych działach firmy do sumy wynagrodzeń. (Potrzeba weryfikacja!)

W księdze głównej plan kont jest zdefiniowany w następujący sposób.

| Plan kont | Konto główne | opis        | Typ konta głównego |
|------------------|--------------|--------------------|-------------------|
| Współdzielony           | 10001        | Wynagrodzenia           | Wydatki           |
| Współdzielony           | 10002        | Ubezpieczenia pracowników | Wydatki           |

Zdefiniuj wymiar składnika kosztu i skonfiguruj łącznik danych. Po zaimportowaniu danych następujące wpisy są tworzone w module Rachunek kosztów.

**Elementy członkowskie wymiaru składnika kosztu**

| Nazwa wymiaru składnika kosztu | Składnik kosztu |  opis       | Typ    |
|-----------------------------|--------------|--------------------|---------|
| Składniki kosztów               | 10001        | Wynagrodzenia           | Główne |
| Składniki kosztów               | 10002        | Ubezpieczenia pracowników | Główne |

**Podstawy alokacji wstępnie zdefiniowanych elementów członkowskich wymiarów** 

| Nazwisko  | opis        | Wymiar składnika kosztu |
|-------|--------------------|------------------------|
| 10001 | Wynagrodzenia           | Składniki kosztów          |
| 10002 | Ubezpieczenia pracowników | Składniki kosztów          |

W księdze głównej zostały zaksięgowane następujące wpisy:

- Wpisy z kontem głównym Wynagrodzenia pochodzą z systemu listy płac i są księgowane w centrach kosztów.
- Wydatek na ubezpieczenie pracownika jest księgowany ręcznie w domyślnym centrum kosztów.

| Data księgowania | Centrum kosztu |  opis        | Konto główne |  opis       | Kwota w walucie rozliczeniowej |
|-----------------|-------------|---------------------|--------------|--------------------|-------------------------------|
| 03-01-2017      | CC001       | Zasoby ludzkie                  | 10001        | Wynagrodzenia           | 2000,00                      |
| 03-01-2017      | CC002       | FI                  | 10001        | Wynagrodzenia           | 5000,00                      |
| 03-01-2017      | CC003       | MM                  | 10001        | Wynagrodzenia           | 3000,00                      |
| 03-01-2017      | CC099       | Domyślne centrum kosztu | 10002        | Ubezpieczenia pracowników | 1000,00                      |

Po przetworzeniu danych źródłowych księgi głównej następujące wpisy są tworzone w module Rachunek kosztów.

**Wpisy kosztów**

| Obiekt kosztów |  opis        | Składnik kosztu  |  opis       | Zachowanie kosztów   |Ilość|Data księgowania|
|-------------|---------------------|---------------|--------------------|-----------------|------|---------------|
| CC001       | Zasoby ludzkie                  | 10001         | Wynagrodzenia           | Niesklasyfikowane    |2000,00|  03-01-2017    |
| CC002       | FI                  | 10001         | Wynagrodzenia           | Niesklasyfikowane    |5000,00|     03-01-2017         |
| CC003       | MM                  | 10001         | Wynagrodzenia           | Niesklasyfikowane    |3000,00|      03-01-2017        |
| CC099       | Domyślne centrum kosztu | 10002         | Ubezpieczenia pracowników | Niesklasyfikowane    |1000,00|      03-01-2017       |

W tym uproszczonym przykładzie jest tworzona reguła alokacji kosztów w celu przydzielania składnika kosztu 10002 (Ubezpieczenia pracowników) względem salda rejestrowanego w składniku kosztu 10001 (Wynagrodzenia).

**Reguła dystrybucji kosztów**

| Węzeł hierarchii wymiarów obiektów kosztów | Węzeł hierarchii wymiarów składników kosztów | Zachowanie kosztów | Podstawa alokacji |
|--------------------------------------|---------------------------------------|---------------|-----------------|
| CC099                                | 10002                                 | Niesklasyfikowane  | 10001           |

**Obliczanie kosztów ogólnych**

Po zastosowaniu składnika kosztu 10001 (Wynagrodzenia) jako podstawy alokacji kosztów wynik obliczania kosztów ogólnych jest następujący:

| Obiekt kosztów | opis | Wartość |   Współczynnik alokacji         | Ilość |
|-------------|-------------|-----------|-----------------------------|--------|
| CC001       | Zasoby ludzkie          | 2 000     | (2000 ÷ 10 000) × 1000,00 | 200,00 |
| CC002       | FI          | 5000     | (5000 ÷ 10 000) × 1000,00 | 500.00 |
| CC003       | MM          | 3000     | (3000 ÷ 10 000) × 1000,00 | 300,00 |

**Arkusz**

| W arkuszu | Typ arkusza                          | Kalendarzowy okres obrachunkowy | Rok | Okres   | Wersja                                                                 |
|---------|---------------------------------------|------------------------|------|----------|-------------------------------------------------------------------------|
| 00001   | Arkusz obliczania dystrybucji kosztów | Fiskalny                 | 2017 | Okres 1 | Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1 |

**Wpisy w arkuszu dotyczące salda obiektów kosztów**

| Data księgowania | Obiekt kosztów | opis         | Składnik kosztu | opis        | Zachowanie kosztów |  Ilość  |
|-----------------|-------------|---------------------|--------------|--------------------|---------------|----------|
| 31-01-2017      | CC099       | Domyślne centrum kosztu | 10002        | Ubezpieczenia pracowników | Niesklasyfikowane  | 1000,00 |

**Wpisy kosztów**

| Obiekt kosztów |  opis        | Składnik kosztu |    opis     | Zachowanie kosztów | Ilość    | Data księgowania |
|-------------|---------------------|--------------|--------------------|---------------|-----------|-----------------|
| CC099       | Domyślne centrum kosztu | 10002        | Ubezpieczenia pracowników | Niesklasyfikowane  | -1000,00 | 31-01-2017      |
| CC001       | Zasoby ludzkie                  | 10002        | Ubezpieczenia pracowników | Niesklasyfikowane  | 200,00    | 31-01-2017      |
| CC002       | FI                  | 10002        | Ubezpieczenia pracowników | Niesklasyfikowane  | 500.00    | 31-01-2017      |
| CC099       | MM                  | 10002        | Ubezpieczenia pracowników | Niesklasyfikowane  | 300,00    | 31-01-2017      |

### <a name="example-2-use-a-statistical-dimension-member-as-the-allocation-base"></a>Przykład 2: Używanie elementu członkowskiego wymiaru statystycznego jako podstawy alokacji

Elementy członkowskie wymiaru statystycznego mogą służyć jako podstawy alokacji w celu definiowania zasad lub raportowania zużycia niepieniężnego z podziałem na obiekty kosztów. Można ręcznie utworzyć elementy członkowskie wymiaru statystycznego lub zaimportować je z pliku przy użyciu narzędzia importu/eksportu Zarządzanie danymi.

**Elementy członkowskie wymiaru statystycznego**

| Nazwa wymiaru statystycznego | Element statystyczny | opis               | Jednostka |
|----------------------------|---------------------|---------------------------|------|
| Elementy statystyczne       | Pracownik pełnoetatowy                 | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu       | Szt.   |
| Elementy statystyczne       | Elektryczność         | Zużycie energii elektrycznej   | kWh  |

Po zapisaniu elementu członkowskiego wymiaru statystycznego jest tworzony odpowiedni rekord we wstępnie zdefiniowanych podstawach alokacji elementu członkowskiego wymiaru.

**Podstawy alokacji wstępnie zdefiniowanych elementów członkowskich wymiarów**

| Nazwisko        | opis             | Element członkowski wymiaru statystycznego |
|-------------|-------------------------|-------------------------------|
| Pracownik pełnoetatowy         | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu     | Elementy statystyczne          |
| Elektryczność | Zużycie energii elektrycznej | Elementy statystyczne          |

Miary statystyczne mogą pochodzić z różnych źródeł:

- Zużycie prądu może być mierzone przez liczniki zamontowane w różnych miejscach w firmie.
- Miary statystyczne są zapisane w tabelach. Na przykład tabela HcmEmployment zawiera listę wszystkich pracowników oraz centrów kosztów, w których pracują.

| Nazwisko       | Centrum kosztu |  opis  | Typ pracownika |
|------------|-------------|----|-------------|
| Pracownik A | CC001       | Zasoby ludzkie | Pracownik    |
| Pracownik B | CC002       | FI | Pracownik    |
| Pracownik C | CC002       | FI | Pracownik    |
| Pracownik D | CC003       | MM | Pracownik    |
| Pracownik F | CC003       | MM | Pracownik    |

> [!NOTE]
> Wszystkie tabele zawierające wymiary finansowe mogą służyć jako źródła dla miar statystycznych.

Moduł Rachunek kosztów obsługuje kolekcję miar statystycznych przy użyciu następujących połączeń danych:

- Narzędzie importu/eksportu Zarządzanie danymi
- Miary statystyczne

Aby można było pobrać miary statystyczne z systemu, jest wymagany szablon dostawcy miar statystycznych. Więcej informacji zawiera temat Szablon dostawcy miar statystycznych. (Łącze zostanie dodane po zredagowaniu tematu).

**Szablony dostawców miar statystycznych**

| Nazwisko  | Funkcja | Tabela źródłowa  | Pole sumy      | Pole daty     |
|-------|----------|---------------|----------------|----------------|
| Pracownicy pełnoetatowi | Zliczanie    | HcmEmployment | Nie dotyczy | Nie dotyczy |

Po przetworzeniu danych źródłowych miar statystycznych następujące wpisy zostaną utworzone w module Rachunek kosztów.

**Wpisy statystyczne**

| Obiekt kosztów | opis      | Data księgowania | Element członkowski wymiaru statystycznego | opis         | Wartość |
|-------------|------------------|-----------------|------------------------------|---------------------|-----------|
| CC001       | Zasoby ludzkie               | 31-01-2017      | Pracownicy pełnoetatowi                        | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | 1.00      |
| CC002       | FI               | 31-01-2017      | Pracownicy pełnoetatowi                        | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | 2.00      |
| CC003       | MM               | 31-01-2017      | Pracownicy pełnoetatowi                        | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | 2.00      |

Oto przykład reguły dystrybucji kosztów, gdy jako podstawę alokacji ma przypisaną wstępnie zdefiniowaną podstawę alokacji elementu członkowskiego wymiaru Pracownicy pełnoetatowi.

| Obiekt kosztów | opis  | Wartość | Współczynnik alokacji |
|-------------|------|-----------|-------------------|
| CC001       | Zasoby ludzkie   | 1.00      | (1/5) × kwota    |
| CC002       | FI   | 2.00      | (2/5) × kwota    |
| CC003       | MM   | 2.00      | (2/5) × kwota    |

Można użyć jednostki danych Importowane miary statystyczne, aby zaimportować miary statystyczne do rachunku kosztów. Można również użyć narzędzia importu/eksportu Zarządzanie danymi. W programie Excel zużycie energii elektrycznej jest rejestrowane w następujący sposób.

| Data księgowania | Element członkowski wymiaru | Wartość | Identyfikator źródła |
|-----------------|------------------|-----------|-------------------|
| 31-01-2017      | CC001            | 2,450.00  | Elektryczność       |
| 31-01-2017      | CC002            | 4,100.00  | Elektryczność       |
| 31-01-2017      | CC003            | 15,000.00 | Elektryczność       |

Po przetworzeniu danych źródłowych miar statystycznych następujące wpisy zostaną utworzone w module Rachunek kosztów.

**Wpisy statystyczne**

| Obiekt kosztów |    | Data księgowania | Element członkowski wymiaru statystycznego |    opis          | Wartość |
|-------------|----|-----------------|------------------------------|-------------------------|-----------|
| CC001       | Zasoby ludzkie | 31-01-2017      | Elektryczność                  | Zużycie energii elektrycznej | 2,450.00  |
| CC002       | FI | 31-01-2017      | Elektryczność                  | Zużycie energii elektrycznej | 4,100.00  |
| CC003       | MM | 31-01-2017      | Elektryczność                  | Zużycie energii elektrycznej | 15,000.00 |

Oto przykład reguły dystrybucji kosztów, gdy jako podstawę alokacji ma przypisaną wstępnie zdefiniowaną podstawę alokacji elementu członkowskiego wymiaru Elektryczność.

| Obiekt kosztów | opis  | Wartość | Współczynnik alokacji          |
|-------------|------|-----------|----------------------------|
| CC001       | Zasoby ludzkie   | 2,450.00  | (2450 ÷ 21 550) × kwota  |
| CC002       | FI   | 4,100.00  | (4100 ÷ 21 550) × kwota  |
| CC003       | MM   | 15,000.00 | (15 000 ÷ 21 550) × kwota |

## <a name="hierarchy-allocation-bases"></a>Podstawy alokacji hierarchii

Księgowi kosztów mogą ręcznie utworzyć podstawy alokacji hierarchii poprzez zastosowanie węzła hierarchii wymiarów obiektu kosztów do istniejącej podstawy alokacji. W ten sposób można ograniczyć zakres pierwotnej wstępnie zdefiniowanej podstawy alokacji elementu członkowskiego wymiaru. Jedna wstępnie zdefiniowana podstawa alokacji elementu członkowskiego wymiaru może służyć do tworzenia kilku podstaw alokacji w hierarchii. Zakresy mogą być prowadzone w hierarchii wymiarów obiektów kosztów skojarzonej z podstawami alokacji hierarchii.

### <a name="example-hierarchy-allocation-bases-that-are-based-on-full-time-employees-in-the-organization"></a>Przykład: Podstawy alokacji hierarchii oparte na pracownikach pełnoetatowych w organizacji
Poniżej przedstawiono przykład hierarchii wymiarów obiektów kosztów, które można utworzyć w celu opisania uproszczonej organizacji.

| Nazwa hierarchii | Poziom węzła 0 | Poziom węzła 1 | Poziom węzła 2 | Elementy członkowskie wymiaru |
|----------------|--------------|--------------|--------------|-------------------|
| Organizacja   | Dyrektor generalny          | Dyrektor finansowy          | FICO         | CC001             |
| Organizacja   | Dyrektor generalny          | Dyrektor finansowy          | Zasoby ludzkie           | CC002             |
| Organizacja   | Dyrektor generalny          | Dyrektor ds. informatyki          | MM           | CC003             |

Wstępnie zdefiniowana podstawa alokacji elementu członkowskiego wymiaru Pracownicy pełnoetatowi utworzona w poprzedniej sekcji zawiera następujące wpisy.

**Wpisy statystyczne**

| Obiekt kosztów | opis  | Data księgowania | Element członkowski wymiaru statystycznego | opis | Wartość |
|-------------|------|-----------------|------------------------------|---------------------|-----------|
| CC001       | Zasoby ludzkie   | 31-01-2017      | Pracownicy pełnoetatowi                        | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | 1.00      |
| CC002       | FI   | 31-01-2017      | Pracownicy pełnoetatowi                        | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | 2.00      |
| CC003       | MM   | 31-01-2017      | Pracownicy pełnoetatowi                        | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | 2.00      |

Koszt musi być rozdzielony między centra kosztów podległe dyrektorowi finansowemu (CFO) w organizacji. Poprawnym wskaźnikiem alokacji jest liczba pracowników pełnoetatowych (FTE) w poszczególnych centrach kosztów.

**Podstawy alokacji hierarchii**

| Nazwisko                  | Podstawa alokacji | Hierarchia wymiarów obiektów kosztów | Węzeł hierarchii wymiarów obiektów kosztów |
|-----------------------|-----------------|---------------------------------|--------------------------------------|
| Liczba FTE podległych CFO | Pracownicy pełnoetatowi           | Organizacja                    | Dyrektor finansowy                                  |

Funkcja podglądu umożliwia sprawdzanie poprawności tworzonej podstawy alokacji hierarchii w oparciu o wpisy statystyczne istniejące w systemie.

**Szczegóły podstawy alokacji**

| Obiekt kosztów | opis  |  Wartość |
|-------------|------|------------|
| CC001       | Zasoby ludzkie   | 1.00       |
| CC002       | FI   | 2.00       |

Oto przykład reguły dystrybucji kosztów, gdy jako podstawę alokacji ma przypisaną podstawę alokacji hierarchii Liczba FTE podległych CFO.

| Obiekt kosztów | opis  | Wartość | Współczynnik alokacji |
|-------------|------|-----------|-------------------|
| CC001       | Zasoby ludzkie   | 1.00      | (1/3) × kwota    |
| CC002       | FI   | 2.00      | (2/3) × kwota    |

## <a name="formula-allocation-bases"></a>Podstawy alokacji formuły

Podstawy alokacji formuły umożliwiają definiowanie zaawansowanych formuł w celu osiągnięcia poprawnej podstawy alokacji. Można ręcznie tworzyć podstawy alokacji formuły.

Tworząc podstawę alokacji formuły, należy wybrać wymiar statystyczny i wymiar składnika kosztu, które mają być bazą dla formuły. W podstawie alokacji formuły mogą być używane wszystkie podstawy alokacji pochodzące z uprzednio wybranych wymiarów.

> [!NOTE]
> Uprzednio zdefiniowane podstawy alokacji formuły mogą służyć do zdefiniowania nowej podstawy alokacji formuły.

We współczynnikach podstawy alokacji formuły tworzy się aliasy, a następnie kojarzy je z podstawą alokacji lub stałą. Aliasy są następnie używane do definiowania formuły.

Następujące operatory służą do definiowania formuły.

| Symbole | Tekst           |
|---------|----------------|
| ( )     | Nawiasy    |
| \<      | Mniejsze niż   |
| \>      | Większe niż    |
| +       | Dodanie       |
| –       | Odejmowanie    |
| \*      | Mnożenie |

Tradycyjne instrukcje **IF** nie są obsługiwane. Można jednak tworzyć instrukcje i sprawdzać, czy określone w nich warunki są spełnione.

| Instrukcja | Weryfikacja | Wynik |
|-----------|------------|--------|
| a \> b    | Prawda       | 1      |
| a \> b    | Fałsz      | 0      |

### <a name="example-1-a-simple-formula"></a>Przykład 1: Prosta formuła

Rachunki za energię elektryczną często składają się z dwóch części:

- Stała opłata za przyłączenie do sieci
- Koszt zużycia określonej liczby kWh energii

Wstępnie zdefiniowana podstawa alokacji elementu członkowskiego wymiaru Elektryczność została już utworzona i zawiera te wartości.

**Wpisy statystyczne**

| Obiekt kosztów | Nazwisko | Data księgowania | Element członkowski wymiaru statystycznego | opis             | Wartość |
|-------------|------|-----------------|------------------------------|-------------------------|-----------|
| CC001       | Zasoby ludzkie   | 31-01-2017      | Elektryczność                  | Zużycie energii elektrycznej | 2,450.00  |
| CC002       | FI   | 31-01-2017      | Elektryczność                  | Zużycie energii elektrycznej | 4,100.00  |
| CC003       | MM   | 31-01-2017      | Elektryczność                  | Zużycie energii elektrycznej | 15,000.00 |

Jeśli stała opłata musi teraz zostać równomiernie rozdzielona między obiekty kosztów zużywające energię elektryczną, masz dwie opcje przydzielenia tego kosztu:

- Utworzenie nowej wstępnie zdefiniowanej podstawy alokacji Opłata stała za prąd, a następnie zastosowanie miary statystycznej 1,00 do każdego obiektu kosztów zużywającego energię elektryczną.
- Utworzenie podstawy alokacji formuły Opłata stała za prąd, która wykorzystuje podstawę alokacji Opłata stała za prąd już zdefiniowaną w systemie. Zaleta tej opcji polega na tym, że dane muszą zostać załadowane do modułu Rachunek kosztów tylko dla jednego elementu członkowskiego wymiaru statystycznego Elektryczność.

**Podstawa alokacji formuły** 

| Nazwisko              | Wymiar składnika kosztu | Wymiar statystyczny | Wzór |
|-------------------|------------------------|-----------------------|---------|
| Opłata stała za prąd |                        | Elementy statystyczne  |         |

Zanim będzie można wypełnić pole **Formuła**, należy określić alias, który powinien być używany w formule.

**Współczynniki podstawy alokacji formuły**

| Alias | Stała | Podstawa alokacji |
|-------|----------|-----------------|
| a     |          | Elektryczność     |
| b     | 0,01     |                 |

Należy zauważyć, że wartość 0 (zero) nie jest obsługiwana jako stała.

**Podstawa alokacji formuły**

| Nazwisko              | Wymiar składnika kosztu | Wymiar statystyczny | Wzór |
|-------------------|------------------------|-----------------------|---------|
| Opłata stała za prąd |                        | Elementy statystyczne  | a \> b  |

Funkcja podglądu umożliwia sprawdzanie poprawności tworzonej podstawy alokacji formuły w oparciu o wpisy statystyczne istniejące w systemie.

**Szczegóły podstawy alokacji**

| Obiekt kosztów | opis  | Wzór           | Wartość |
|-------------|------|-------------------|-----------|
| CC001       | Zasoby ludzkie   | 2.450,00 \> 0,01  | 1.00      |
| CC002       | FI   | 4.100,00 \> 0,01  | 1.00      |
| CC003       | MM   | 15.000,00 \> 0,01 | 1.00      |

Oto przykład reguły dystrybucji kosztów, gdy jako podstawę alokacji ma przypisaną podstawę alokacji formuły Elektryczność.

**Współczynnik alokacji wielkości obiektu kosztów**

| Obiekt kosztów | Nazwisko | Wartość |  Współczynnik alokacji |
|-------------|------|-----------|--------------------|
| CC001       | Zasoby ludzkie   | 1.00      | (1/3) × kwota     |
| CC002       | FI   | 1.00      | (1/3) × kwota     |
| CC003       | MM   | 1.00      | (1/3) × kwota     |

### <a name="example-2-an-advanced-formula"></a>Przykład 2: Zaawansowana formuła
W tym przykładzie koszt energii elektrycznej nie powinien jedynie odzwierciedlać faktycznego zużycia prądu w kWh. Kierownictwo chce dodać zachęty do obniżania zużycia energii elektrycznej. 

| Reguła              | Kurs | 
|-------------------|------|
| a <= 10 000,00 kWh | 0.75 |
| a > 10 000,00 kWh  | 1.15 |

Jest tworzona nowa podstawa alokacji formuły Zużycie energii elektrycznej.

**Podstawa alokacji formuły**

| Nazwisko              | Wymiar składnika kosztu | Wymiar statystyczny | Wzór |
|-------------------|------------------------|-----------------------|---------|
| Zużycie energii elektrycznej |                        | Elementy statystyczne  |         |

Zanim będzie można wypełnić pole **Formuła**, należy określić alias, który powinien być używany w formule.

**Współczynniki podstawy alokacji formuły**

| Alias | Stała  | Podstawa alokacji |
|-------|-----------|-----------------|
| a     |           | Elektryczność     |
| b     | 10,000.00 |                 |
| c     | 0.75      |                 |
| d     | 1.15      |                 |

**Podstawa alokacji formuły**

| Nazwisko              | Wymiar składnika kosztu | Wymiar statystyczny | Wzór                                                    |
|-------------------|------------------------|-----------------------|------------------------------------------------------------|
| Opłata stała za prąd |                        | Elementy statystyczne  | ((a \> b) × ((b × c) + (a – b) × d)) + ((a \<= b] × a × c) |

Funkcja podglądu umożliwia sprawdzanie poprawności tworzonej podstawy alokacji formuły w oparciu o wpisy statystyczne istniejące w systemie.

**Szczegóły podstawy alokacji**

| Obiekt kosztów |    | Wzór                                                                                                                             | Wartość |
|-------------|----|-------------------------------------------------------------------------------------------------------------------------------------|-----------|
| CC001       | Zasoby ludzkie | ((2450,00 \> 10 000,00) × ((10 000,00 × 0,75) + (2450,00 – 10 000,00) × 1,15)) + ((2450,00 \<= 10 000,00) × 2450,00 × 0,75)     | 1,837.50  |
| CC002       | FI | ((2450,00 \> 10 000,00) × ((10 000,00 × 0,75) + (2450,00 – 10 000,00) × 1,15)) + ((2450,00 \<= 10 000,00) × 2450,00 × 0,75)     | 3,075.00  |
| CC003       | MM | ((2450,00 \> 10 000,00) × ((10 000,00 × 0,75) + (2450,00 – 10 000,00) × 1,15)) + ((2450,00 \<= 10 000,00) × 2450,00 × 0,75) | 1,3250.00 |

Oto zbliżenie na formułę obiektu kosztów CC003 (IT):

((15 000,00 \> 10 000,00) × ((10 000,00 × 0,75) + (15 000,00 – 10 000,00) × 1,15)) + ((15 000,00 \<= 10 000,00) × 15 000,00 × 0,75) = 13 250,00

(1 × (7500,00 + 5000,00 × 1,15)) + (0 × 15 000,00 × 0,75)            

1 × 7500,00 + 5750,00 + 0 

Oto przykład reguły dystrybucji kosztów, gdy jako podstawę alokacji ma przypisaną podstawę alokacji formuły Opłata stała za prąd.


| Obiekt kosztów | opis | Wartość |        Współczynnik alokacji         |
|-------------|-------------|-----------|----------------------------------|
|    CC001    |     Zasoby ludzkie      | 1,837.50  | (1,837.50 ÷ 18,162.50) × kwota  |
|    CC002    |     FI      | 3,075.00  | (3,075.00 ÷ 18,162.50) × kwota  |
|    CC003    |     MM      | 13,250.00 | (13 250,00 ÷ 18 162,50) × kwota |

