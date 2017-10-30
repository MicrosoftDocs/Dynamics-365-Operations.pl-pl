---
title: "Pakiet zawartości usługi Power BI Wynagrodzenia"
description: "W tym temacie opisano pakiet zawartość Wynagrodzenia dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: jcart1106
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: daf7232f13b5a2d4262a46f302bfd9e7efd60ead
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="compensation-power-bi-content"></a>Pakiet zawartości usługi Power BI Wynagrodzenia

[!include[banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartość **Wynagrodzenia** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Pakiet zawartości usługi Power BI zatytułowany **Wynagrodzenia** jest wyświetlany w obszarze roboczym **Zarządzanie wynagrodzeniami**, jeśli używasz jednego z następujących produktów:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017)
- Microsoft Dynamics 365 for Talent

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty umieszczone w pakiecie zawartości usługi Power BI
Raporty dostępne w pakiecie zawartości usługi Power BI **Wynagrodzenia** mają wykresy i tabele przedstawiające dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport                     | Zawartość |
|----------------------------|----------|
| Przegląd wynagrodzeń      | Podsumowanie innych raportów |
| Analiza wynagrodzenia      | Pracownicy na stawce godzinowej i stałej według firmy, łączna liczba pracowników według systemu wynagrodzeń, mężczyźni i kobiety według systemu wynagrodzeń oraz wynagrodzenia pracowników według działów |
| Analiza wynagrodzeń na stanowiskach      | Najwyższe i najniższe stawka godzinowe i stałe wynagrodzenia, stanowiska z najwyższą i najniższą płacą oraz stanowiska z pełnym i niepełnym wymiarem godzin |
| Analiza systemu wynagrodzeń | Rejestracje pracowników wg wybranego świadczenia |

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="extending-the-power-bi-content"></a>Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI
Jeśli używasz programu Microsoft Dynamics 365 for Operations w wersji 1611 lub Finance and Operations Enterprise Edition (lipiec 2017 r.), pakiet zawartości usługi Power BI zatytułowany **Wynagrodzenia** znajduje się w bibliotece zasobów wspólnych w usłudze LCS. Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md). Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

Uważaj, aby pobrać pakiet zawartości usługi Power BI **Wynagrodzenia** mający zastosowanie do używanej wersji systemu Microsoft Dynamics 365.

>[!NOTE]
>Pliki .pbix dostępne w usłudze Lifecycle Services dotyczą tylko modułu Finance and Operations.

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Następujące dane są używane do wypełniania raportów w pakiecie zawartości usługi Power BI **Wynagrodzenia**. W tej tabeli przedstawiono jednostki, na których bazuje pakiet.

| Jednostka                   | Zawartość                                                                                                   | Powiązania z innymi jednostkami |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Przesunięcie kalendarza          | Przesunięcia kalendarzy dla raportów wycinkowych                                                                          | Przeszłe przypisania stanowisk, Trend stanowisk, Trend pracowników, Pracownik z rozwiązanym stosunkiem pracy |
| Firma                  | Firmy, według których będą filtrowane raporty                                                                             | Bieżące wynagrodzenie, Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Wynagrodzenie             | Stawka płacy i częstotliwość wypłat w okresie                                                                           | Bieżące wynagrodzenie, Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Bieżące wynagrodzenie     | Stawka płacy i częstotliwość wypłat na obecny dzień                                                              | Firma, Wynagrodzenie, Dane demograficzne, Zadanie, Stanowisko |
| Bieżące stanowisko         | Stanowiska na obecny dzień, równoważnik pełnego etatu (FTE), wolne stanowiska i stanowiska wolne do obsadzenia | Zadanie, Stanowisko |
| Bieżący pracownik etatowy         | Liczba pracowników na obecny dzień, wiek i stan osobowy                                                         | Firma, Wynagrodzenie, Położenie geograficzne, Nazwisko pracownika etatowego, Przełożony, Tytuł pracownika, Dane demograficzne, Zadanie, Zatrudnienie, Stanowisko, Świadczenia |
| Data                     | Dni, tygodnie, miesiące i lata                                                                             | Przeszłe przypisania stanowisk, Trend stanowisk, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Dane demograficzne             | Data urodzenia, płeć, pochodzenie etniczne i stan cywilny                                                   | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Zatrudnienie               | Data rozpoczęcia, data zakończenia i data przejścia                                                                  | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Położenie geograficzne      | Miejscowość, kod pocztowy i województwo                                                           | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Stanowisko                      | Funkcja, typ i tytuł                                                                                  | Bieżące stanowisko, Bieżący pracownik etatowy |
| Przeszłe przypisania stanowisk | Przyczyna przypisania, data rozpoczęcia, data zakończenia i zadanie                                                           | Przesunięcie kalendarza, Data, Zadanie, Stanowisko |
| Pozycja                 | Dział, równoważnik pełnego etatu, stanowisko, typ stanowiska i tytuł                                                        | Bieżące stanowisko, Bieżący pracownik etatowy |
| Trend stanowisk           | Stanowiska zajmowane w okresie, równoważnik pełnego etatu i zadanie                                                                          | Przesunięcie kalendarza, Data, Zadanie, Stanowisko |
| Przełożony               | Imię, drugie imię i nazwisko                                                                       | Bieżący pracownik, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Pracownik z rozwiązanym stosunkiem pracy      | Zwolnieni pracownicy etatowi, data rozwiązania stosunku pracy, tytuł, stanowisko i zadanie                                             | Firma, Wynagrodzenie, Położenie geograficzne, Nazwisko pracownika etatowego, Przełożony, Przesunięcie kalendarza, Data, Tytuł pracownika, Dane demograficzne, Zatrudnienie, Zadanie, Stanowisko, Świadczenia |
| Świadczenia                 | Data wejścia w życie, opcja świadczenia, plan świadczeń i typ świadczenia                                             | Bieżąca nazwa, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Nazwisko pracownika etatowego            | Imię, drugie imię i nazwisko                                                                       | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Tytuł pracownika           | Tytuł i data ustalenia stażu pracy                                                                                   | Bieżący pracownik etatowy, Pracownik z rozwiązanym stosunkiem pracy, Trend pracowników |
| Trend pracowników           | Liczba pracowników w okresie, stan osobowy, firma i stanowisko                                                        | Firma, Wynagrodzenie, Położenie geograficzne, Nazwisko pracownika etatowego, Przełożony, Przesunięcie kalendarza, Data, Tytuł pracownika, Dane demograficzne, Zatrudnienie, Zadanie, Świadczenia |

Te jednostki zostały użyte do utworzenia obliczanych miar w modelu danych. Następnie obliczone mierniki są używane do obliczania kluczowych wskaźników wydajności (KPI) i generowania raportów, które są używane w pakiecie zawartości. Jeśli chcesz umieścić dodatkowe obliczenia w raportach i na pulpicie nawigacyjnym, możesz z usługi LCS pobrać plik .pbix i go zmodyfikować. Ten plik jest domyślnym modelem danych, który został użyty do utworzenia pakietu zawartości. Po wprowadzeniu wszystkich modyfikacji można utworzyć organizacyjny pakiet zawartości i pulpit nawigacyjny, który zawiera dodane informacje.
