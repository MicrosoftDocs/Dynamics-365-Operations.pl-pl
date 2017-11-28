---
title: "Pakiet zawartości usługi Power BI Metryki pracowników"
description: "W tym temacie opisano pakiet zawartość Metryki pracowników dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Talent, Core
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1a94eb68d017a334ae0246b50813de9add0ea82a
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="workforce-metrics-power-bi-content"></a>Pakiet zawartości usługi Power BI Metryki pracowników

[!include[banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartość **Metryki pracowników** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Pakiet zawartości usługi Power BI zatytułowany **Metryki pracowników** jest wyświetlany w obszarze roboczym **Zarządzanie pracownikami**, jeśli używasz jednego z następujących produktów:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017)
- Microsoft Dynamics 365 for Talent

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki umieszczone w pakiecie zawartości usługi Power BI
W poniższej tabeli pokazano mierniki dostępne na każdej stronie raportu.

| Raport                                           | Metryki                                                                                                                                                                                                            |
|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mierniki osób                                   | Podsumowanie innych raportów                                                                                                                           |
| Analiza stanu osobowego według firmy, działu, lokalizacji | Stan osobowy według firmy, stan osobowy według działu, stan osobowy według lokalizacji i łączny stan osobowy                                                                                                                           |
| Analiza stanu osobowego według zadania, kroku i menedżera            | Stan osobowy według zadania, stan osobowy według kroku, stan osobowy według menedżera i łączny stan osobowy                                                                                                                                      |
| Analiza trendu stanu osobowego                         | Stan osobowy w tym roku w porównaniu z zeszłym rokiem z podziałem na firmy oraz skumulowany stan osobowy w ciągu ostatnich 12 miesięcy                                                                                                                        |
| Analiza FTE                                     | Suma etatów przeliczeniowych (przeliczeniu na pełne etaty), suma przypisanych etatów przeliczeniowych, etaty przeliczeniowe według działów, etaty przeliczeniowe w ciągu ostatnich 12 miesięcy oraz etaty przeliczeniowe według zadań |
| Dane demograficzne pracowników                           | Stan osobowy według wieku i płci, stan osobowy według pochodzenia etnicznego, stan osobowy według statusu weterana wojennego, stan osobowy według stanu cywilnego, liczba studentów na studiach dziennych, średni staż pracy, średni wiek, stosunek liczby kobiet do liczby mężczyzn oraz języki używane przez pracowników |
| Analiza stanowisk                                | Wolne stanowiska według działu, stanowiska wolne do obsadzenia, stosunek liczby stanowisk aktywnych do nieaktywnych oraz stanowiska według działów                                                                                                   |
| Analiza rotacji                               | Rotacja w tym roku w porównaniu do ubiegłego, rotacja, odchodzący pracownicy według wieku i płci, średni staż pracy odchodzących pracowników, pracownicy odchodzący w tym miesiącu oraz odejścia pracowników z podziałem na przyczyny                                                                   |
| Pracownicy wg działów                             | Pracownicy z numerami pracowniczymi według działów, stanowisk oraz dat rozpoczęcia i zakończenia przypisania do stanowiska                                                                                                                       |
| Analiza stażu pracy                               | Średni staż pracy, średni staż pracy według firmy, lista stażu pracy                                                                                                                                                              |
| Rocznice pracowników                           | Rocznice w tym miesiącu, rocznice w przyszłym miesiącu, pracownicy według stażu pracy i rocznic, staż pracy według działów                                                                                                                                                                    |
| Urodziny pracowników                               | Urodziny w tym miesiącu, urodziny w następnym miesiącu, urodziny pracowników oraz urodziny według miesięcy i działów                                                                                                                                                                    |
| Projekty zatrudnienia grupowego                               | Projekty zatrudnienia grupowego razem, projekty zatrudnienia grupowego według stanów, projekty zatrudnienia grupowego według działów i właścicieli, projektów zatrudnienia grupowego według zadań oraz projekty zatrudnienia grupowego                                                                                                                                                                    |

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="extending-the-power-bi-content"></a>Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI
Za pomocą pakietów zawartości dostępnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) można dostarczać zaawansowane funkcje analityczne osobom, które się nie logują w programie Finance and Operations. Te pakiety zawartości można modyfikować, tak aby zawierały inne raporty lub wizualizacje, a następnie publikować je w swojej dzierżawie usługi Power BI.com na potrzeby wykonywania analiz.

Pakiet zawartości usługi Power BI **Metryki pracowników** znajduje się w bibliotece zasobów wspólnych w usłudze LCS. Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md). Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

Uważaj, aby pobrać pakiet zawartości usługi Power BI **Metryki pracowników** mający zastosowanie do używanej wersji systemu Microsoft Dynamics 365.

>[!NOTE]
>Pliki .pbix dostępne w usłudze Lifecycle Services dotyczą tylko modułu Finance and Operations.

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

Te jednostki zostały użyte do utworzenia obliczanych miar w modelu danych. Następnie obliczane miary są używane do obliczania kluczowych wskaźników wydajności (KPI) i generowania raportów, które są używane w pakiecie zawartości usługi Power BI. Jeśli chcesz umieścić dodatkowe obliczenia w raportach i na pulpicie nawigacyjnym, możesz z usługi LCS pobrać plik .pbix i go zmodyfikować. Ten plik jest domyślnym modelem danych, który został użyty do utworzenia pakietu zawartości usługi Power BI. Po wprowadzeniu wszystkich modyfikacji można utworzyć organizacyjny pakiet zawartości i pulpit nawigacyjny, który zawiera dodane informacje.

