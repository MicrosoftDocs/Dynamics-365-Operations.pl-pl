---
title: Elementy członkowskie wymiaru statystycznego i szablony dostawców miar statystycznych
description: Ten temat zawiera informacje o elementach członkowskich wymiaru statystycznego i szablonach dostawców miar statystycznych. Elementy członkowskie wymiaru statystycznego mogą służyć jako podstawa alokacji w zasadach, na przykład dystrybucji kosztów i alokacji kosztów. Mogą być również używane do raportowania zużycia kosztów niepieniężnych.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerSourceEntryProvider, CAMStatisticalDimension, CAMAXStatisticalMeasureProviderTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c46a9e042482ad66e769383b4e81e2df85a5e97b
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124527"
---
# <a name="statistical-dimension-members-and-statistical-measure-provider-templates"></a>Elementy członkowskie wymiaru statystycznego i szablony dostawców miar statystycznych

[!include [banner](../includes/banner.md)]

Wymiar statystyczny i jego elementy członkowskie są używane do rejestrowania i kontrolowania wpisów niepieniężnych w rachunku kosztów. Elementy członkowskie wymiaru statystycznego mogą służyć do dwóch celów:

- Jako podstawa alokacji w zasadach, na przykład dystrybucji kosztów lub alokacji kosztów
- Do raportowania zużycia niepieniężnego

## <a name="statistical-dimension"></a>Wymiar statystyczny

Wymiar statystyczny ma unikatową nazwę i zbiór unikatowych elementów członkowskich wymiaru. Wymiar statystyczny jest przypisany do identyfikatora księgi rachunku kosztów. Ta relacja wiąże wszystkie odnośne elementy członkowskie wymiaru statystycznego z księgą rachunku kosztów. W związku z tym wszystkie wpisy statystyczne będą tworzone w kontekście księgi rachunku kosztów.

> [!NOTE]
> Wymiar statystyczny może być przypisany do więcej niż jednej księgi rachunku kosztów.

Oto przykład wymiaru statystycznego.

| Nazwisko                        | Łącznik danych dla elementów członkowskich wymiarów |
|-----------------------------|--------------------------------------|
| Współdzielone elementy statystyczne | Importowane elementy członkowskie wymiaru           |

Oto przykład wymiaru statystycznego przypisanego do księgi rachunku kosztów.

| Nazwisko                  | Waluta rozliczeniowa | Typ kursu wymiany | Kalendarz obrachunkowy | Wymiar składnika kosztu | Wymiar statystyczny       |
|-----------------------|---------------------|--------------------|-----------------|------------------------|-----------------------------|
| Księgowość zarządcza | USD                 | Stały kurs wymiany  | Okres obrachunkowy   | Współdzielone składniki kosztów   | Współdzielone elementy statystyczne |

## <a name="statistical-dimension-members"></a>Elementy członkowskie wymiaru statystycznego

Element członkowski wymiaru statystycznego jednostkę, dla której mają zostać zarejestrowane miary niepieniężne. Te miary mogą służyć jako podstawa alokacji albo tylko do raportowania wartości niepieniężnych.

Elementy członkowskie wymiaru statystycznego mogą być tworzone ręcznie. Ewentualnie można je zaimportować z pliku przy użyciu narzędzia importu/eksportu Zarządzanie danymi.

Element członkowski wymiaru statystycznego automatycznie staje się wstępnie zdefiniowaną podstawą alokacji. Może służyć jako podstawa alokacji w zasadach lub jako dane wejściowe w innych typach podstaw alokacji.

Oto kilka przykładów typowych elementów członkowskich wymiaru statystycznego.

| Nazwa wymiaru statystycznego  | Elementy statystyczne | opis             | Jednostka |
|-----------------------------|----------------------|-------------------------|------|
| Współdzielone elementy statystyczne | Pracownik pełnoetatowy                  | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu     | Szt.  |
| Współdzielone elementy statystyczne | Elektryczność          | Zużycie energii elektrycznej | kWh  |
| Współdzielone elementy statystyczne | Pack CC              | Centrum kosztów Pakowanie   | Godz. |

## <a name="statistical-measure-provider-template"></a>Szablon dostawcy miar statystycznych

Miary statystyczne mogą pochodzić z wielu rodzajów źródeł. Usługa Dynamics 365 Finance jest świetnym źródłem, z którego można wyodrębniać miary statystyczne. Szablon dostawcy miar statystycznych pozwala w prosty sposób skonfigurować miary statystyczne, które mają zostać wyodrębniane.

Definicja szablonu dostawcy miar statystycznych jest standardowa i może być wykorzystywana w wielu różnych elementach członkowskich wymiaru statystycznego.

> [!NOTE]
> Wszystkie tabele zawierające wymiary finansowe mogą służyć jako źródła dla miar statystycznych.

**Przykład: Liczba pracowników z podziałem na centra kosztów**

Liczba pracowników z podziałem na centra kosztów jest miarą statystyczną, która może być wykorzystywana do różnych celów związanych z prezentowaniem informacji kierownictwu:

- Miara sprawozdawczości statystycznej z podziałem na centra kosztów
- Podstawa alokacji dla różnych typów wydatków
- Wewnętrzne stawki kosztów wg centrum kosztu:

    - Koszt wg pracownika
    - Przychód wg pracownika

Tabela HcmEmployment zawiera listę wszystkich pracowników istniejących w wystąpieniu. Jest to tabela globalna. W związku z tym rekordy nie są powiązane z konkretnym identyfikatorem obszaru danych.

Oto przykład pracowników w tabeli HcmEmployment.

| Nazwisko       | Centrum kosztu | opis   | Typ pracownika |
|------------|-------------|----|-------------|
| Pracownik 1 | CC001       | Zasoby ludzkie | Pracownik    |
| Pracownik 2 | CC002       | FI | Pracownik    |
| Pracownik 3 | CC002       | FI | Pracownik    |
| Pracownik 4 | CC003       | MM | Pracownik    |
| Pracownik 5 | CC003       | MM | Pracownik    |
| Pracownik 6 | CC002       | FI | Zleceniobiorca  |

Podczas tworzenia rekordu **Szablon dostawcy miar statystycznych** należy zdecydować, która funkcja ma być używana:

- **Zliczanie** — jest przenoszona liczba rekordów dla każdego obiektu kosztów.
- **Suma** — jest przenoszona suma rekordów dla każdego obiektu kosztów. (Pola **Suma** i **Data** są wymagane).

## <a name="using-the-count-function"></a>Używanie funkcji Zliczanie

Na przykład szablon dostawcy miar statystycznych można skonfigurować w następujący sposób.

| Nazwisko  | Funkcja | Tabela źródłowa  | Pole sumy      | Pole daty     |
|-------|----------|---------------|----------------|----------------|
| Pracownicy pełnoetatowi  | Zliczanie    | HcmEmployment | Nie dotyczy | Nie dotyczy |

Można również dodać jeden lub kilka zakresów, aby zawęzić zbiór miar pobieranych z tabeli źródłowej.

W tym przykładzie jeśli chcesz tylko zliczyć wszystkich pracowników pełnoetatowych (FTE), można dodać zakres w polu **Typ pracownika**. W polu **Kryteria** zaznacz opcję **Pracownik**, aby ograniczyć zakres danych wyjściowych w następujący sposób.

**Zakresy**

| Tabela źródłowa  | Pole       | Kryterium |
|---------------|-------------|----------|
| HcmEmployment | Typ pracownika | Pracownik |

Zanim będzie można pobrać miary statystyczne do modułu Rachunek kosztów, należy ustanowić relację między szablonem dostawcy miar statystycznych a elementem członkowskim wymiaru statystycznego. Ta relacja jest tworzona dla księgi rachunku kosztów i wersji. Relacja składa się z łącznika danych i dostawcy danych. Dla jednego elementu członkowskiego wymiaru statystycznego może istnieć kilka łączników danych i dostawców danych.

> [!NOTE]
> W tym przykładzie zostanie utworzona relacja tylko wersji **Wersja rzeczywista**.

Przejdź do okna **Księga rachunku kosztów** \> **Wersja rzeczywista** \> **Zarządzaj** \> **Miary statystyczne** i ustanów relację. W tym scenariuszu zaznacz łącznik danych **Dynamics 365 Finance — Miary statystyczne**, ponieważ chcemy wyodrębnić dane z aplikacji Finance.

**Źródło danych**

| Nazwisko        | Łącznik danych                                                                     | Element członkowski wymiaru statystycznego |
|-------------|------------------------------------------------------------------------------------|------------------------------|
| Pracownicy pełnoetatowi D365FO | Dynamics 365 Finance — Miary statystyczne | Pracownicy pełnoetatowi                         |

**Konfiguracja dostawcy danych**

| Nazwa szablonu statystycznego |
|---------------------------|
| Pracownicy pełnoetatowi                      |

Po przetworzeniu danych źródłowych miary statystycznej następujące wpisy statystyczne są tworzone w module Rachunek kosztów.

**Arkusz**

| W arkuszu | Typ arkusza                       | Kalendarzowy okres obrachunkowy | Rok   |  Okres  |  Wersja | Wpisy źródłowe łącznika danych|
|---------|------------------------------------|------------------------|--------|----------|----------|------------------------------|
| 00001   | Arkusz przeniesień wpisów statystycznych | Fiskalny                 | 2017   | Okres 1 | Księga CA firmy USMF | Pracownicy pełnoetatowi                   |

**Wpisy w arkuszu przeniesień wpisów statystycznych**

| Data księgowania | Wartość | Element statystyczny |   opis       | Centrum kosztu |
|-----------------|-----------|---------------------|---------------------|-------------|
| 31-01-2017      | 1.00      | Pracownicy pełnoetatowi                | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | CC001       |
| 31-01-2017      | 2.00      | Pracownicy pełnoetatowi                | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | CC002       |
| 31-01-2017      | 2.00      | Pracownicy pełnoetatowi                | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | CC003       |

**Wpisy statystyczne**

| Obiekt kosztów |    | Data księgowania | Element członkowski wymiaru statystycznego |  opis        | Wartość |
|-------------|----|-----------------|------------------------------|---------------------|-----------|
| CC001       | Zasoby ludzkie | 31-01-2017      | Pracownicy pełnoetatowi                         | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | 1.00      |
| CC002       | FI | 31-01-2017      | Pracownicy pełnoetatowi                         | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | 2.00      |
| CC003       | MM | 31-01-2017      | Pracownicy pełnoetatowi                         | Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu | 2.00      |

Jeśli w regule dystrybucji kosztów jako podstawę alokacji przypisano wstępnie zdefiniowaną podstawę alokacji elementu członkowskiego wymiaru Pracownicy pełnoetatowi, koszt zostanie rozdzielony przy użyciu następującego współczynnika alokacji.

| Obiekt kosztów | opis    | Wartość | Współczynnik alokacji |
|-------------|----|-----------|-------------------|
| CC001       | Zasoby ludzkie | 1.00      | (1/5) × kwota    |
| CC002       | FI | 2.00      | (2/5) × kwota    |
| CC003       | MM | 2.00      | (2/5) × kwota    |

## <a name="using-the-sum-function"></a>Używanie funkcji Suma

Produkcyjne centrum kosztów CC010 (Pakowanie) jest odpowiedzialne za pakowanie produktów, zanim zostaną one wysłane do odbiorców. Bezpośrednie koszty robocizny są dodawane do produktów za pośrednictwem listy składowej (BOM) i marszruty. Koszty pośrednie utrzymania centrum kosztów również muszą zostać przydzielone do wytwarzanych produktów. Często najlepszą miarą statystyczną dla takiej alokacji jest liczba zarejestrowanych godzin produkcji dla każdego produktu w podanym okresie.

Tabela ProdRouteTrans zawiera wszystkie transakcje robocizny produkcyjnej dla każdego obszaru DataAreadID firmy.

Oto przykład tabeli ProdRouteTrans.

| Odwołanie        | Identyfikator | Operacja | Typ | Czas  | Data fizycznej transakcji | Grupa produktów (wymiar finansowy) | Firma |
|------------------|--------|-----------|------|-------|---------------|-------------------------------------|--------------|
| Zlecenie produkcyjne | P0001  | Opakowanie | Czas | 8.00  | 01-01-2017    | Sok pomarańczowy B2B                    | USMF         |
| Zlecenie produkcyjne | P0001  | Opakowanie | Czas | 8.00  | 02-01-2017    | Sok pomarańczowy B2B                    | USMF         |
| Zlecenie produkcyjne | P0002  | Opakowanie | Czas | 4,00  | 03-01-2017    | Sok pomarańczowy dla konsumentów               | USMF         |
| Zlecenie produkcyjne | P0003  | Opakowanie | Czas | 4,00  | 03-01-2017    | Sok pomarańczowy dla konsumentów               | USMF         |
| Zlecenie produkcyjne | P0004  | Rekonstrukcja  | Czas | 10,00 | 03-01-2017    | Sok pomarańczowy dla konsumentów               | USMF         |

Podczas tworzenia rekordu **Szablon dostawcy miar statystycznych** należy zdecydować, która funkcja ma być używana:

- **Zliczanie** — jest przenoszona liczba rekordów dla każdego obiektu kosztów.
- **Suma** — jest przenoszona suma rekordów dla każdego obiektu kosztów. (Pola **Suma** i **Data** są wymagane).

Szablon dostawcy miar statystycznych można skonfigurować w następujący sposób.

| Nazwisko    | Funkcja | Tabela źródłowa   | Pole sumy | Pole daty    |
|---------|----------|----------------|-----------|---------------|
| Pack CC | Suma      | ProdRouteTrans | Godziny     | Data fizycznej transakcji |

Można również dodać zakresy, aby zawęzić zbiór miar pobieranych z tabeli źródłowej.

W tym przykładzie aby uzyskać tylko sumę godzin związanych z centrum kosztów CC010 Pakowanie, można dodać zakres w polu **Operacja**. W polu **Kryteria** zaznacz opcję **Pakowanie**, aby ograniczyć zakres danych wyjściowych.

**Zakresy**

| Tabela źródłowa   | Pole     | Kryterium  |
|----------------|-----------|-----------|
| ProdRouteTrans | Operacja | Opakowanie |

Zanim będzie można pobrać miary statystyczne do modułu Rachunek kosztów, należy ustanowić relację między szablonem dostawcy miar statystycznych a elementem członkowskim wymiaru statystycznego. Ta relacja jest tworzona dla księgi rachunku kosztów i wersji. Relacja składa się z łącznika danych i dostawcy danych. Dla jednego elementu członkowskiego wymiaru statystycznego może istnieć kilka łączników danych i dostawców danych.

> [!NOTE]
> W tym przykładzie zostanie utworzona relacja tylko wersji **Wersja rzeczywista**.

Przejdź do okna **Księga rachunku kosztów** \> **Wersja rzeczywista** \> **Zarządzaj** \> **Miary statystyczne** i ustanów relację. W tym scenariuszu zaznacz łącznik danych **Dynamics 365 Finance — Miary statystyczne**, ponieważ chcemy wyodrębnić dane z aplikacji Finance.

**Źródło danych**

| Nazwisko           | Łącznik danych                                                                     | Element członkowski wymiaru statystycznego |
|----------------|------------------------------------------------------------------------------------|------------------------------|
| Pack CC D365FO | Dynamics 365 Finance — Miary statystyczne | Pack CC                      |

System rozpoznaje, że ProdRouteTrans jest tabelą, w której każdy rekord należy do osobnej firmy. W związku z tym zobaczysz monit o wybór firmy, z której powinny zostać zaimportowane transakcje.

**Konfiguracja dostawcy danych**

| Nazwa szablonu statystycznego | Firma |
|---------------------------|--------------|
| Pack CC                   | USMF         |

Po przetworzeniu danych źródłowych miary statystycznej następujące wpisy statystyczne są tworzone w module Rachunek kosztów.

**Arkusz**

| W arkuszu | Typ arkusza                     | Kalendarzowy okres obrachunkowy | Rok   | Okres | Wersja   |   Wpisy źródłowe łącznika danych  |
|---------|----------------------------------|------------------------|--------|---------|----------------|---------|
| 00002   | Arkusz przeniesień wpisów statystycznych | Fiskalny               | 2017    | Okres 1  | Księga CA firmy USMF | Pack CC |

**Wpisy w arkuszu przeniesień wpisów statystycznych**

| Data księgowania | Wartość | Element statystyczny |  opis          | Grupa produktów         |
|-----------------|-----------|---------------------|-----------------------|-----------------------|
| 31-01-2017      | 16.00     | Pack CC             | Centrum kosztów Pakowanie | Sok pomarańczowy B2B      |
| 31-01-2017      | 8.00      | Pack CC             | Centrum kosztów Pakowanie | Sok pomarańczowy dla konsumentów |

**Wpisy statystyczne**

| Obiekt kosztów           | Data księgowania | Element członkowski wymiaru statystycznego |    opis        | Wartość |
|-----------------------|-----------------|------------------------------|-----------------------|-----------|
| Sok pomarańczowy B2B      | 31-01-2017      | Pack CC                      | Centrum kosztów Pakowanie | 16.00     |
| Sok pomarańczowy dla konsumentów | 31-01-2017      | Pack CC                      | Centrum kosztów Pakowanie | 8.00      |

Jeśli w regule dystrybucji kosztów jako podstawę alokacji przypisano wstępnie zdefiniowaną podstawę alokacji elementu członkowskiego wymiaru Pack CC, koszt zostanie rozdzielony przy użyciu następującego współczynnika alokacji.

| Obiekt kosztów           | Wartość | Współczynnik alokacji  |
|-----------------------|-----------|--------------------|
| Sok pomarańczowy B2B      | 16.00     | (16 ÷ 24) × kwota |
| Sok pomarańczowy dla konsumentów | 8.00      | (8 ÷ 24) × kwota  |

## <a name="imported-statistical-measures"></a>Importowane miary statystyczne

Miar statystyczne można zaimportować do modułu Rachunek kosztów za pomocą narzędzia importu/eksportu Zarządzanie danymi.

Jednostka danych używana do importowania nazywa się Importowane miary statystyczne.

> [!NOTE]
> Ta jednostka danych jest skonstruowana w taki sposób, że obsługuje maksymalnie pięć unikatowych wartości wymiaru dla każdego wpisu.

Zużycie energii elektrycznej jest rejestrowane w programie Microsoft Excel przy użyciu wstępnie zdefiniowanego formatu jednostki danych. Oto przykład.

| Data księgowania | Nazwa elementu członkowskiego wymiaru 1 | Nazwa elementu członkowskiego wymiaru 2 | Nazwa elementu członkowskiego wymiaru 5 | Wartość  | Identyfikator źródła |
|-----------------|------------------------|------------------------|------------------------|------------|-------------------|
| 31-01-2017      | CC001                  |                        |                        | 2,450.00   | Elektryczność       |
| 31-01-2017      | CC002                  |                        |                        | 4,100.00   | Elektryczność       |
| 31-01-2017      | CC003                  |                        |                        | 15,000.00  | Elektryczność       |

Po zaimportowaniu danych za pośrednictwem narzędzia Zarządzanie danymi dane będą przechowywane w tabeli tymczasowej rachunku kosztów. W związku z tym zaimportowane dane mogą być używane w wielu księgach rachunku kosztów. Ponowne ładowanie danych nie jest wymagane.

Aby importować dane, przejdź do okna **Importowane dane** \> **Jednostka danych** \> **Importowane miary statystyczne**.

| Identyfikator źródła | Data księgowania | Wartość  | Nazwa elementu członkowskiego wymiaru 1 | Nazwa elementu członkowskiego wymiaru 2 | Nazwa elementu członkowskiego wymiaru 5 |
|-------------------|-----------------|------------|------------------------|------------------------|------------------------|
| Elektryczność       | 31-01-2017      | 2,450.00   | CC001                  |                        |                        |
| Elektryczność       | 31-01-2017      | 4,100.00   | CC002                  |                        |                        |
| Elektryczność       | 31-01-2017      | 15,000.00  | CC003                  |                        |                        |

Zanim będzie można pobrać miary statystyczne do modułu Rachunek kosztów, należy ustanowić relację między identyfikatorem źródła a elementem członkowskim wymiaru statystycznego. Ta relacja jest tworzona dla księgi rachunku kosztów i wersji. Relacja składa się z łącznika danych i dostawcy danych. Dla jednego elementu członkowskiego wymiaru statystycznego może istnieć kilka łączników danych i dostawców danych.

> [!NOTE]
> W tym przykładzie zostanie utworzona relacja tylko wersji **Wersja rzeczywista**.

Przejdź do okna **Księga rachunku kosztów** \> **Wersja rzeczywista** \> **Zarządzaj** \> **Miary statystyczne** i ustanów relację. W tym scenariuszu zaznacz łącznik danych **Importowane miary statystyczne**, ponieważ dane zostały zaimportowane z systemu innej firmy do modułu Rachunek kosztów za pośrednictwem programu Excel.

**Źródło danych**

| Nazwisko        | Łącznik danych                | Element członkowski wymiaru statystycznego |
|-------------|-------------------------------|------------------------------|
| Elektryczność | Importowane miary statystyczne | Elektryczność                  |

**Konfiguracja dostawcy danych**

| Identyfikator źródła importu | Funkcja | Wymiar 1   | Wymiar 2 | Wymiar 5 |
|--------------------------|----------|--------------|------------|------------|
| Elektryczność              | Suma      | Centra kosztów |            |            |

> [!NOTE]
> Podczas definiowania konfiguracji dostawcy danych należy wskazać, które wymiary obiektów kosztów mają zostać odniesione do zaimportowanych transakcji. Po przetworzeniu danych źródłowych miary statystycznej następujące wpisy statystyczne są tworzone w module Rachunek kosztów.

**Arkusz**

| W arkuszu | Typ arkusza                       | Kalendarzowy okres obrachunkowy | Rok  | Identyfikator okresu  |Wersja      |Wpisy źródłowe łącznika danych |
|---------|------------------------------------|------------------------|-------|--------|---------------|-------------|
| 00002   | Arkusz przeniesień wpisów statystycznych | Fiskalny                 | 2017  | Okres 1 | Księga CA firmy USMF | Elektryczność |

**Wpisy w arkuszu przeniesień wpisów statystycznych**

| Data księgowania | Wartość  | Składnik kosztu |   opis           | Centrum kosztu |
|-----------------|------------|--------------|-------------------------|-------------|
| 31-01-2017      | 2,450.00   | Elektryczność  | Zużycie energii elektrycznej | CC001       |
| 31-01-2017      | 4,100.00   | Elektryczność  | Zużycie energii elektrycznej | CC002       |
| 31-01-2017      | 15,000.00  | Elektryczność  | Zużycie energii elektrycznej | CC003       |

**Wpisy statystyczne**

| Obiekt kosztów |    | Data księgowania | Element członkowski wymiaru statystycznego |      opis                   | Wartość  |
|-------------|----|-----------------|------------------------------|-------------------------|------------|
| CC001       | Zasoby ludzkie | 31-01-2017      | Elektryczność                  | Zużycie energii elektrycznej | 2,450.00   |
| CC002       | FI | 31-01-2017      | Elektryczność                  | Zużycie energii elektrycznej | 4,100.00   |
| CC003       | MM | 31-01-2017      | Elektryczność                  | Zużycie energii elektrycznej | 15,000.00  |

Jeśli w regule dystrybucji kosztów jako podstawę alokacji przypisano wstępnie zdefiniowaną podstawę alokacji elementu członkowskiego wymiaru Elektryczność, koszt zostanie rozdzielony przy użyciu następującego współczynnika alokacji.

| Obiekt kosztów |    | Wartość | Współczynnik alokacji          |
|-------------|----|-----------|----------------------------|
| CC001       | Zasoby ludzkie | 2,450.00  | (2450 ÷ 21 550) × kwota  |
| CC002       | FI | 4,100.00  | (4100 ÷ 21 550) × kwota  |
| CC003       | MM | 15,000.00 | (15 000 ÷ 21 550) × kwota |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Podstawy alokacji](allocation-bases.md)
