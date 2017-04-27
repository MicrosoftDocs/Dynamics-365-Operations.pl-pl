---
title: "Pakiet zawartości usługi Power BI Wyniki finansowe"
description: "W tym temacie opisano pakiet zawartości Wyniki finansowe dla narzędzia usługi Microsoft Power BI należący do programu Microsoft Dynamics 365 for Operations. Omówiono pulpit nawigacyjny i raporty znajdujące się w pakiecie zawartości oraz zamieszczono informacje o modelu i jednostkach danych, które zostały użyte do zbudowania pakietu zawartości."
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

# <a name="financial-performance-power-bi-content"></a>Pakiet zawartości usługi Power BI Wyniki finansowe

[!include[banner](../includes/banner.md)]


W tym temacie opisano pakiet zawartości Wyniki finansowe dla narzędzia usługi Microsoft Power BI należący do programu Microsoft Dynamics 365 for Operations. Omówiono pulpit nawigacyjny i raporty znajdujące się w pakiecie zawartości oraz zamieszczono informacje o modelu i jednostkach danych, które zostały użyte do zbudowania pakietu zawartości.

<a name="accessing-the-content-pack"></a>Przechodzenie do pakietu zawartości
--------------------------

Dostępne są dwie wersje pakietu zawartości Wyniki finansowe. Jedną wersję można pobrać z usługi Microsoft Dynamics Lifecycle Services (LCS), a drugą z witryny PowerBI.com.

-   **Wersja dostępna w usłudze LCS:** Pakiet zawartości Wyniki finansowe dostępny w usłudze LCS współpracuje z oprogramowaniem Microsoft Dynamics 365 for Operations w wersji 1611. Pakiet znajduje się w bibliotece zasobów wspólnych w usłudze LCS. Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i łączeniu go z danymi usługi Microsoft Dynamics 365 for Operations, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md).
-   **Wersja dostępna w witrynie PowerBI.com:** Pakiet zawartości Wyniki finansowe dostępny w witrynie PowerBI.com współpracuje z oprogramowaniem Microsoft Dynamics AX w wersjach 7.0 i 7.0.1. Aby uzyskać więcej informacji o tworzeniu połączenia z danymi programu Dynamics 365 for Operations i ich ładowaniu, zobacz [Dostęp do pakietu zawartości usługi Power BI z witryny Microsoft Dynamics 365 for Operations](power-bi-home-page.md).

## <a name="main-account-setup"></a>Konfiguracja konta głównego
Ponieważ organizacje chcą, aby kwoty zobowiązań i przychodów były wyświetlane jako kwoty dodatnie w raportach, ważne jest odpowiednie skonfigurowanie kont głównych w programie Dynamics 365 for Operations. Aby kwoty na tych kontach głównych były wyświetlane jako dodatnie, typ konta głównego musi być ustawiony jako **Pasywa** lub **Przychód**. Gdy są używane te typy kont, sprawozdawczość za pośrednictwem usługi Microsoft Power BI będzie powodowała odwracanie znaków i wyświetlanie kwot jako dodatnich.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>Pulpity nawigacyjne i raporty dostępne w pakiecie zawartości
Gdy utworzysz połączenie między pakietem zawartości a danymi programu Dynamics 365 for Operations, w pulpicie nawigacyjnym i raportach są wyświetlone dane finansowe. Jeśli to Twoja pierwsza styczność z usługą Power BI, możesz się o niej dowiedzieć więcej na [stronie Przewodnika z instruktażem po narzędziu Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Pulpit nawigacyjny zawiera kafelki podsumowań danych oparte na źródłowych raportach. Każdy kafelek zawiera podsumowanie informacji o bieżącym roku dla wszystkich firm w organizacji. Oto kilka dostępnych kafelków:

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

Każdy kafelek wykorzystuje pomocniczy raport. Raporty zawierają wykresy i tabele dostarczające więcej informacji. W poniższej tabeli opisano dostępne raporty.

| Raport                      | Informacje zawarte w raporcie                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Analiza środków pieniężnych               | Gotówka z podziałem na firmy, gotówka według kwartałów, łączna gotówka oraz gotówka z podziałem na konta **Uwaga:** Raport **Gotówka według kwartałów** nie zawiera sald początkowych w sumie dla pierwszego kwartału. Suma jest pokazywana dla nowych transakcji księgowanych w każdym kwartale.                                                                                |
| Analiza wskaźnika bieżącej płynności      | Wskaźnik bieżącej płynności z podziałem na firmy, wskaźnik bieżącej płynności według kwartałów oraz salda bieżących aktywów i pasywów                                                                                                                                                                                                                              |
| Analiza wskaźnika szybkiej płynności        | Wskaźnik szybkiej płynności z podziałem na firmy, wskaźnik szybkiej płynności według kwartałów oraz bieżące salda gotówki, należności i zobowiązań                                                                                                                                                                                                                      |
| Analiza kosztów własnych sprzedaży | Koszt własny sprzedaży (KWS) z podziałem na firmy, KWS w tym i poprzednim roku według kwartałów, KWS według firm, łączny KWS oraz stosunek procentowy KWS do sprzedaży                                                                                                                                                                                   |
| Analiza kapitału obrotowego    | Kapitał obrotowy z podziałem na firmy, kapitał obrotowy według kwartałów, bieżące aktywa, bieżące pasywa i całkowity kapitał obrotowy                                                                                                                                                                                                                   |
| Analiza aktywów i zadłużenia     | Zwrot z całkowitych aktywów i zadłużenie do sumy aktywów z podziałem na firmy, zadłużenie do sumy aktywów i zwrot z całkowitych aktywów od początku kwartału, aktywa i pasywa                                                                                                                                                                                     |
| Analiza marży zysku      | Marża zysku rzeczywista i zabudżetowana z podziałem na firmy, marża zysku według kwartałów, procent marży zysku i marża zysku                                                                                                                                                                                                                       |
| Analiza dochodu netto         | Dochód netto rzeczywisty i zabudżetowany z podziałem na firmy, dochód netto w tym i poprzednim roku oraz stosunek procentowy wydatków do dochodu netto                                                                                                                                                                                                                       |
| Analiza dochodów           | Dochody rzeczywiste i zabudżetowane przed potrąceniem odsetek i podatków (EBIT) z podziałem na firmy, EBIT z tym i poprzednim roku, stosunek procentowy wydatków do przychodów oraz stosunek wydatków rzeczywistych i zabudżetowanych do przychodów                                                                                                                                                          |
| Analiza przychodów            | Suma przychodów, suma przychodów rzeczywistych a zabudżetowanych z podziałem na firmy, suma przychodów w tym i poprzednim roku, różnica zabudżetowanych przychodów z podziałem na firmy oraz i suma przychodów w tym i poprzednim okresie                                                                                                                                                 |
| Analiza wydatków            | Suma wydatków, suma wydatków rzeczywistych a zabudżetowanych z podziałem na firmy, suma wydatków rzeczywistych a zabudżetowanych według kwartałów, suma wydatków według kategorii kont oraz wskaźnik wydatków operacyjnych                                                                                                                                                                 |
| Analiza zafakturowanych przychodów     | Suma rozrachunków z odbiorcami, suma rozrachunków z odbiorcami z podziałem na firmy, suma rozrachunków z odbiorcami według kwartałów oraz salda kont rozrachunków z odbiorcami **Uwaga:** Raporty nie zawierają sald początkowych kont księgowych rozrachunków z odbiorcami. Sumy są wyświetlane dla nowych transakcji księgowanych w module Rozrachunki z odbiorcami. |

Wykresy i kafelki we wszystkich tych raportach można filtrować i przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dane, które wypełniają pulpit nawigacyjny i raporty w pakiecie zawartości Wyniki finansowe, są danymi programu Dynamics 365 for Operations. Następujące jednostki zostały użyte jako podstawa w pakiecie zawartości: **Jednostki zagregowanych danych**

-   **GeneralLedgerActivities** — ta jednostka agreguje salda księgi głównej według kategorii kont.
-   **BudgetActivities** — ta jednostka agreguje salda budżetu według kategorii kont.

**Jednostki danych**

-   FiscalCalendars
-   MainAccounts
-   LegalEntities
-   Księgi
-   ChartofAccounts

Te jednostki zostały użyte do utworzenia obliczanych miar w modelu danych. Obliczane miary są używane do obliczania kluczowych wskaźników wydajności (KPI) i generowania raportów, które są używane w pakiecie zawartości. Domyślnie pakiet zawartości grupuje dane z trzech ostatnich lat i jednego roku przyszłego. Aby uwzględnić dodatkowe obliczenia w raportach i pulpicie nawigacyjnym, można zmodyfikować [skoroszyt programu Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Ten skoroszyt jest domyślnym modelem danych, który został użyty do utworzenia pakietu zawartości. Po wprowadzeniu wszystkich modyfikacji można utworzyć organizacyjny pakiet zawartości i pulpit nawigacyjny, który zawiera dodane informacje.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](..\data-entities\data-entities.md)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](configure-power-bi-integration.md)





