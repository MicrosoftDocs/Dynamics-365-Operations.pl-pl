---
title: "Finansowe zawartości BI zasilania wydajność"
description: "W tym temacie opisano usługi Microsoft Dynamics 365 zawartości pakietu operacje finansowe wyniki dla Microsoft Power BI. Opis pulpitu nawigacyjnego i raportów, które są zawarte w pakiecie zawartości i zawiera informacje o modelu danych i podmiotów, które były użyte do utworzenia pakietu zawartości."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 227285720e7f28beeb135eea081940578531d458
ms.lasthandoff: 03/31/2017


---

# <a name="financial-performance-power-bi-content"></a>Finansowe zawartości BI zasilania wydajność

W tym temacie opisano usługi Microsoft Dynamics 365 zawartości pakietu operacje finansowe wyniki dla Microsoft Power BI. Opis pulpitu nawigacyjnego i raportów, które są zawarte w pakiecie zawartości i zawiera informacje o modelu danych i podmiotów, które były użyte do utworzenia pakietu zawartości.

<a name="accessing-the-content-pack"></a>Uzyskiwanie dostępu do zawartości pack
--------------------------

Dostępne są dwie wersje content Pack wyników finansowych. Jedna wersja jest dostępna z Microsoft Dynamics cyklu życia usługi (LCS), a druga jest dostępna z PowerBI.com.

-   **Wersja, która jest dostępna z LCS:** wyników finansowych content pack, który jest dostępny z LCS obsługuje Microsoft Dynamics 365 dla wersji operacji 1611. Content pack można znaleźć w biblioteki zasobów współużytkowanych w LCS. Aby uzyskać więcej informacji o tym, jak pobrać pakiet zawartości i podłącz go do sieci Microsoft Dynamics 365 dla danych operacji, zobacz [Power BI zawartości w LCS firmy Microsoft i jej partnerzy](power-bi-content-microsoft-partners.md).
-   **Wersja, która jest dostępna z PowerBI.com:** wyników finansowych content pack, który jest dostępny z PowerBI.com obsługuje system Microsoft Dynamics AX w wersji 7.0 i 7.0.1. Aby uzyskać więcej informacji na temat sposobu połączenia i załadować Twojego 365 Dynamics dla danych operacji, zobacz [BI zasilania dostęp do zawartości z PowerBI.com](power-bi-home-page.md).

## <a name="main-account-setup"></a>Konfiguracja konta głównego
Ponieważ organizacje chcą zobowiązań oraz kwoty przychodów są wyświetlane jako kwoty dodatnie w raportach, ważne jest ustawienia kont głównych w usłudze Dynamics 365 dla operacji. Dla tych kont głównych są wyświetlane jako kwoty dodatnie, typ konta głównego musi być równa **odpowiedzialność** lub **dochodów**. Gdy używane są następujące typy kont, zgłoszenie za pośrednictwem programu Microsoft Power BI będzie odwrócić oznaki i wyświetlić wartości jako pozytywne.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>Pulpit nawigacyjny i raporty, które są zawarte w pakiecie zawartości
Gdy utworzysz połączenie między pakietem zawartości a danymi programu Dynamics 365 for Operations, w pulpicie nawigacyjnym i raportach są wyświetlone dane finansowe. Jeśli nigdy nie używane Power BI przed, można znaleźć informacje na jego temat na [stronę z przewodnikiem nauki BI zasilania](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Pulpit nawigacyjny zawiera kafelki podsumowań danych oparte na źródłowych raportach. Każdy kafelek zawiera podsumowanie informacji o bieżącym roku dla wszystkich firm w organizacji. Oto kilka fragmentów:

-   Kasa
-   Łączne przychody w roku
-   Łączne wydatki w roku
-   Dochód netto w roku
-   Wskaźnik szybkiej płynności
-   Łączne wydatki w roku według kategorii kont
-   Wskaźnik bieżącej płynności
-   Zadłużenie aktywów łącznie
-   Przychody rzeczywiste a prognozowane
-   Zafakturowane przychody w roku
-   Wskaźnik wydatków operacyjnych w roku
-   Marża zysku w roku
-   Wydatki rzeczywiste a zabudżetowane — wszystkie firmy

Każda tabliczka jest wspierany przez towarzyszące raportu. Raporty zawierają wykresy i tabele dostarczające więcej informacji. W poniższej tabeli opisano dostępne raporty.

| Raport                      | Informacje zawarte w raporcie                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Analiza środków pieniężnych               | Środków pieniężnych przez osobę prawną, środków pieniężnych według kwartałów, środków pieniężnych i środków pieniężnych przez konto **Uwaga:****środków pieniężnych według kwartałów** raport nie zawiera sald początkowych w sumie za pierwszy kwartał. Pokazuje sumę nowych transakcji, które są księgowane w każdym kwartale.                                                                                |
| Analiza wskaźnika bieżącej płynności      | Wskaźnik bieżącej płynności z podziałem na firmy, wskaźnik bieżącej płynności według kwartałów oraz salda bieżących aktywów i pasywów                                                                                                                                                                                                                              |
| Analiza wskaźnika szybkiej płynności        | Szybkie stosunek przez podmiot prawny, szybkie stosunek według kwartałów i sald dla środków pieniężnych, rozrachunków z odbiorcami i bieżące zobowiązania                                                                                                                                                                                                                      |
| Analiza kosztów własnych sprzedaży | Koszt własny sprzedaży (KWS) z podziałem na firmy, KWS w tym i poprzednim roku według kwartałów, KWS według firm, łączny KWS oraz stosunek procentowy KWS do sprzedaży                                                                                                                                                                                   |
| Analiza kapitału obrotowego    | Kapitał obrotowy z podziałem na firmy, kapitał obrotowy według kwartałów, bieżące aktywa, bieżące pasywa i całkowity kapitał obrotowy                                                                                                                                                                                                                   |
| Analiza aktywów i zadłużenia     | Zwrot z całkowitych aktywów i zadłużenie do sumy aktywów z podziałem na firmy, zadłużenie do sumy aktywów i zwrot z całkowitych aktywów od początku kwartału, aktywa i pasywa                                                                                                                                                                                     |
| Analiza marży zysku      | Marża zysku rzeczywista i zabudżetowana z podziałem na firmy, marża zysku według kwartałów, procent marży zysku i marża zysku                                                                                                                                                                                                                       |
| Analiza dochodu netto         | Dochód netto rzeczywisty i zabudżetowany z podziałem na firmy, dochód netto w tym i poprzednim roku oraz stosunek procentowy wydatków do dochodu netto                                                                                                                                                                                                                       |
| Analiza dochodów           | Dochody rzeczywiste i zabudżetowane przed potrąceniem odsetek i podatków (EBIT) z podziałem na firmy, EBIT z tym i poprzednim roku, stosunek procentowy wydatków do przychodów oraz stosunek wydatków rzeczywistych i zabudżetowanych do przychodów                                                                                                                                                          |
| Analiza przychodów            | Suma przychodów, suma przychodów rzeczywistych a zabudżetowanych z podziałem na firmy, suma przychodów w tym i poprzednim roku, różnica zabudżetowanych przychodów z podziałem na firmy oraz i suma przychodów w tym i poprzednim okresie                                                                                                                                                 |
| Analiza wydatków            | Suma wydatków, suma wydatków rzeczywistych a zabudżetowanych z podziałem na firmy, suma wydatków rzeczywistych a zabudżetowanych według kwartałów, suma wydatków według kategorii kont oraz wskaźnik wydatków operacyjnych                                                                                                                                                                 |
| Analiza zafakturowanych przychodów     | Suma rozrachunków z odbiorcami, Suma rozrachunków z odbiorcami przez podmiot prawny, Suma rozrachunków z odbiorcami według kwartałów i salda kont z odbiorcami konta **Uwaga:** raporty nie zawierają sald początkowych dla kont księgowych z odbiorcami kont. Pokazują one sumę nowych transakcji, które są księgowane na kontach należności. |

Wykresy i kafelki we wszystkich tych raportach można filtrować i przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dane, które wypełnia pulpitu nawigacyjnego i raporty w pakiecie zawartości wyników finansowych jest Dynamics 365 dla danych operacji. Następujące podmioty były używane jako podstawa content Pack: **agregowanie danych podmiotów**

-   **GeneralLedgerActivities** -tej encji agregatów salda księgi według kategorii konta.
-   **BudgetActivities** -tej encji agregatów salda budżetu według kategorii konta.

**Data entities**

-   FiscalCalendars
-   MainAccounts
-   LegalEntities
-   Księgi
-   ChartofAccounts

Podmioty te były używane do tworzenia miar obliczeniowych w modelu danych. Miary obliczeniowe są używane do obliczania kluczowych wskaźników wydajności (KPI) i raportów, które są używane w pakiecie zawartości. Domyślnie pakiet zawartości grupuje dane z trzech ostatnich lat i jednego roku przyszłego. Aby uwzględnić dodatkowe obliczenia w raportach i pulpicie nawigacyjnym, można zmodyfikować [skoroszyt programu Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Ten skoroszyt jest domyślnym modelem danych, który został użyty do utworzenia pakietu zawartości. Po wprowadzeniu wszystkich modyfikacji można utworzyć organizacyjny pakiet zawartości i pulpit nawigacyjny, który zawiera dodane informacje.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](..\data-entities\data-entities.md)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](configure-power-bi-integration.md)



