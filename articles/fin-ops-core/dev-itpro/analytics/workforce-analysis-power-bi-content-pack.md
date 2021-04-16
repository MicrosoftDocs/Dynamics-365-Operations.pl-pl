---
title: Pakiet zawartości usługi Power BI Metryki pracowników
description: W tym temacie opisano pakiet zawartość Metryki pracowników dostępny dla usługi Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkforceWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 244fe5afe822c9ff7b9921d8e4e7b6904c96ad01
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754199"
---
# <a name="workforce-metrics-power-bi-content"></a>Pakiet zawartości usługi Power BI Metryki pracowników

[!include [banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartość **Metryki pracowników** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Pakiet zawartości usługi Power BI zatytułowany **Metryki pracowników** jest wyświetlany w obszarze roboczym **Zarządzanie pracownikami**, jeśli używasz jednego z następujących produktów:

- Microsoft Dynamics 365 Finance
- Microsoft Dynamics 365 Human Resources

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki umieszczone w pakiecie zawartości usługi Power BI
W poniższej tabeli pokazano mierniki dostępne na każdej stronie raportu.

| Raport                                           | Metryki |
|--------------------------------------------------|---------|
| Mierniki osób                                   | Podsumowanie innych raportów |
| Analiza stanu osobowego według firmy, działu, lokalizacji | Stan osobowy według firmy, stan osobowy według działu, stan osobowy według lokalizacji i łączny stan osobowy |
| Analiza stanu osobowego według zadania, kroku i menedżera            | Stan osobowy według zadania, stan osobowy według kroku, stan osobowy według menedżera i łączny stan osobowy |
| Analiza trendu stanu osobowego                         | Stan osobowy w tym roku w porównaniu z zeszłym rokiem z podziałem na firmy oraz skumulowany stan osobowy w ciągu ostatnich 12 miesięcy |
| Analiza FTE                                     | Suma etatów przeliczeniowych (przeliczeniu na pełne etaty), suma przypisanych etatów przeliczeniowych, etaty przeliczeniowe według działów, etaty przeliczeniowe w ciągu ostatnich 12 miesięcy oraz etaty przeliczeniowe według zadań |
| Dane demograficzne pracowników                           | Stan osobowy według wieku i płci, stan osobowy według pochodzenia etnicznego, stan osobowy według statusu weterana wojennego, stan osobowy według stanu cywilnego, liczba studentów na studiach dziennych, średni staż pracy, średni wiek, stosunek liczby kobiet do liczby mężczyzn oraz języki używane przez pracowników |
| Analiza stanowisk                                | Wolne stanowiska według działu, stanowiska wolne do obsadzenia, stosunek liczby stanowisk aktywnych do nieaktywnych oraz stanowiska według działów |
| Analiza rotacji                               | Rotacja w tym roku w porównaniu do ubiegłego, rotacja, odchodzący pracownicy według wieku i płci, średni staż pracy odchodzących pracowników, pracownicy odchodzący w tym miesiącu oraz odejścia pracowników z podziałem na przyczyny |
| Pracownicy wg działów                             | Pracownicy z numerami pracowniczymi według działów, stanowisk oraz dat rozpoczęcia i zakończenia przypisania do stanowiska |
| Analiza stażu pracy                               | Średni staż pracy, średni staż pracy według firmy, lista stażu pracy |
| Rocznice pracowników                           | Rocznice w tym miesiącu, rocznice w przyszłym miesiącu, pracownicy według stażu pracy i rocznic, staż pracy według działów |
| Urodziny pracowników                               | Urodziny w tym miesiącu, urodziny w następnym miesiącu, urodziny pracowników oraz urodziny według miesięcy i działów |
| Projekty zatrudnienia grupowego                               | Projekty zatrudnienia grupowego razem, projekty zatrudnienia grupowego według stanów, projekty zatrudnienia grupowego według działów i właścicieli, projektów zatrudnienia grupowego według zadań oraz projekty zatrudnienia grupowego |

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w usłudze Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

Uważaj, aby pobrać pakiet zawartości usługi Power BI **Metryki pracowników** mający zastosowanie do używanej wersji systemu Microsoft Dynamics 365.

> [!NOTE]
> Pliki .pbix dostępne w usłudze Lifecycle Services dotyczą tylko aplikacji Finance and Operations.

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
W poniższej tabeli przedstawiono jednostki, na których bazuje pakiet.

| Jednostka                   | Zawartość                                                                            | Powiązania z innymi jednostkami |
|--------------------------|-------------------------------------------------------------------------------------|-----------------------------------|
| Przesunięcie kalendarza          | Przesunięcia kalendarzy dla raportów wycinkowych                                                   | Przeszłe przypisania stanowisk, Trend stanowisk, Trend pracowników, Pracownik z rozwiązanym stosunkiem pracy |
| Firma                  | Firmy, według których będą filtrowane raporty                                                      | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Bieżące stanowisko         | Stanowiska na obecny dzień, etat przeliczeniowy (FTE), wolne stanowiska i stanowiska wolne do obsadzenia | Zadanie, Stanowisko |
| Bieżący pracownik etatowy         | Liczba pracowników na obecny dzień, wiek i stan osobowy                                  | Firma, Położenie geograficzne, Nazwisko pracownika etatowego, Przełożony, Tytuł pracownika, Dane demograficzne, Zadanie, Zatrudnienie, Stanowisko |
| Data                     | Dni, tygodnie, miesiące i lata                                                      | Przeszłe przypisania stanowisk, Trend stanowisk, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Dane demograficzne             | Data urodzenia, płeć, pochodzenie etniczne i stan cywilny                            | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Zatrudnienie               | Data rozpoczęcia, data zakończenia i data przejścia                                           | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Położenie geograficzne      | Miejscowość, kod pocztowy i województwo                                    | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Stanowisko                      | Funkcja, typ i tytuł                                                           | Bieżące stanowisko, Bieżący pracownik etatowy |
| Przeszłe przypisania stanowisk | Przyczyna przypisania, data rozpoczęcia, data zakończenia i zadanie                                    | Przesunięcie kalendarza, Data, Zadanie, Stanowisko |
| Pozycja                 | Dział, równoważnik pełnego etatu, stanowisko, typ stanowiska i tytuł                                 | Bieżące stanowisko, Bieżący pracownik etatowy |
| Trend stanowisk           | Stanowiska zajmowane w okresie, równoważnik pełnego etatu i zadanie                                                   | Przesunięcie kalendarza, Data, Zadanie, Stanowisko |
| Przełożony               | Imię, drugie imię i nazwisko                                                | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Pracownik z rozwiązanym stosunkiem pracy      | Zwolnieni pracownicy, data rozwiązania stosunku pracy, tytuł, stanowisko i zadanie                      | Firma, Położenie geograficzne, Nazwisko pracownika etatowego, Przełożony, Przesunięcie kalendarza, Data, Tytuł pracownika, Dane demograficzne, Zatrudnienie, Zadanie, Stanowisko |
| Nazwisko pracownika etatowego            | Imię, drugie imię i nazwisko                                                | Bieżący pracownik, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Tytuł pracownika           | Tytuł i data ustalenia stażu pracy                                                            | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Trend pracowników           | Liczba pracowników w okresie, stan osobowy, firma i stanowisko                                 | Firma, Położenie geograficzne, Nazwisko pracownika etatowego, Przełożony, Przesunięcie kalendarza, Data, Tytuł pracownika, Dane demograficzne, Zatrudnienie, Zadanie |
| Projekt zatrudnienia grupowego        | Liczba projektów zatrudnienia grupowego, właściciel projektu oraz stan projektu                     | Firma, Wiersz zatrudnienia grupowego |
| Wiersz zatrudnienia grupowego           | Dział, typ zatrudnienia i stanowisko                                           | Data, Zadanie, Projekt zatrudnienia grupowego |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]