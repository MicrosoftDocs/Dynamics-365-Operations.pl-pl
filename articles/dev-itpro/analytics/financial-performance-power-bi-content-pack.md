---
title: "Pakiet zawartości usługi Power BI Wyniki finansowe"
description: "W tym temacie opisano pakiet zawartość Wyniki finansowe dostępny dla usługi Power BI."
author: kweekley
manager: AnnBe
ms.date: 02/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7b5c4428c8610a7b2d4cf1a28287ba2bb1f9c2ea
ms.openlocfilehash: b7cb5f2096f0be5211024fc6ecbfaa61d6c48c9a
ms.contentlocale: pl-pl
ms.lasthandoff: 02/06/2018

---

# <a name="financial-performance-power-bi-content"></a>Pakiet zawartości usługi Power BI Wyniki finansowe

[!include[banner](../includes/banner.md)]

> [!Note]
> Ten pakiet zawartości został wycofany, zgodnie z opisem w temacie [Pakiety zawartości usługi Power BI opublikowane w witrynie PowerBI.com](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features#power-bi-content-packs-published-to-powerbicom).

W tym temacie opisano pakiet zawartość **Wyniki finansowe** dostępny dla usługi Microsoft Power BI. Omówiono dostępny pulpit nawigacyjny i raporty oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="main-account-setup"></a>Konfiguracja konta głównego
Ponieważ organizacje chcą, aby kwoty zobowiązań i przychodów były wyświetlane jako kwoty dodatnie w raportach, ważne jest odpowiednie skonfigurowanie kont głównych. Aby kwoty na tych kontach głównych były wyświetlane jako dodatnie, typ konta głównego musi być ustawiony jako **Pasywa** lub **Przychód**. Gdy są używane te typy kont, sprawozdawczość za pośrednictwem usługi Power BI będzie powodowała odwracanie znaków i wyświetlanie kwot jako dodatnich.

## <a name="dashboard-and-reports-that-are-included-in-the-power-bi-content"></a>Pulpit nawigacyjny i raporty dostępne w tym pakiecie zawartości usługi Power BI
Pulpit nawigacyjny zawiera kafelki podsumowań danych oparte na źródłowych raportach. Każdy kafelek zawiera podsumowanie informacji o bieżącym roku dla wszystkich firm w organizacji. Oto kilka dostępnych kafelków:

- Kasa
- Łączne przychody w roku
- Łączne wydatki w roku
- Dochód netto w roku
- Wskaźnik szybkiej płynności
- Łączne wydatki w roku według kategorii kont
- Wskaźnik bieżącej płynności
- Zadłużenie aktywów łącznie
- Przychody rzeczywiste a prognozowane
- Zafakturowane przychody w roku
- Wskaźnik wydatków operacyjnych w roku
- Marża zysku w roku
- Wydatki rzeczywiste a zabudżetowane — wszystkie firmy

Każdy kafelek wykorzystuje pomocniczy raport. Raporty zawierają wykresy i tabele dostarczające więcej informacji. W poniższej tabeli opisano dostępne raporty.

| Raport                      | Informacje zawarte w raporcie |
|-----------------------------|--------------------------------------|
| Analiza środków pieniężnych               | Gotówka z podziałem na firmy, gotówka według kwartałów, łączna gotówka oraz gotówka z podziałem na konta<blockquote>[!NOTE]<br>Informacje o gotówce według kwartałów nie obejmują sald początkowych w sumie za pierwszy kwartał. Suma jest pokazywana dla nowych transakcji księgowanych w każdym kwartale.</blockquote> |
| Analiza wskaźnika bieżącej płynności      | Wskaźnik bieżącej płynności z podziałem na firmy, wskaźnik bieżącej płynności według kwartałów oraz salda bieżących aktywów i pasywów |
| Analiza wskaźnika szybkiej płynności        | Wskaźnik szybkiej płynności z podziałem na firmy, wskaźnik szybkiej płynności według kwartałów oraz bieżące salda gotówki, należności i zobowiązań |
| Analiza kosztów własnych sprzedaży | Koszt własny sprzedaży (KWS) z podziałem na firmy, KWS w tym i poprzednim roku według kwartałów, KWS według firm, łączny KWS oraz stosunek procentowy KWS do sprzedaży |
| Analiza kapitału obrotowego    | Kapitał obrotowy z podziałem na firmy, kapitał obrotowy według kwartałów, bieżące aktywa, bieżące pasywa i całkowity kapitał obrotowy |
| Analiza aktywów i zadłużenia     | Zwrot z całkowitych aktywów i zadłużenie do sumy aktywów z podziałem na firmy, zadłużenie do sumy aktywów i zwrot z całkowitych aktywów od początku kwartału, aktywa i pasywa |
| Analiza marży zysku      | Marża zysku rzeczywista i zabudżetowana z podziałem na firmy, marża zysku według kwartałów, procent marży zysku i marża zysku |
| Analiza dochodu netto         | Dochód netto rzeczywisty i zabudżetowany z podziałem na firmy, dochód netto w tym i poprzednim roku oraz stosunek procentowy wydatków do dochodu netto |
| Analiza dochodów           | Dochody rzeczywiste i zabudżetowane przed potrąceniem odsetek i podatków (EBIT) z podziałem na firmy, EBIT z tym i poprzednim roku, stosunek procentowy wydatków do przychodów oraz stosunek wydatków rzeczywistych i zabudżetowanych do przychodów |
| Analiza przychodów            | Suma przychodów, suma przychodów rzeczywistych a zabudżetowanych z podziałem na firmy, suma przychodów w tym i poprzednim roku, różnica zabudżetowanych przychodów z podziałem na firmy oraz i suma przychodów w tym i poprzednim okresie |
| Analiza wydatków            | Suma wydatków, suma wydatków rzeczywistych a zabudżetowanych z podziałem na firmy, suma wydatków rzeczywistych a zabudżetowanych według kwartałów, suma wydatków według kategorii kont oraz wskaźnik wydatków operacyjnych |
| Analiza zafakturowanych przychodów     | Suma rozrachunków z odbiorcami, suma rozrachunków z odbiorcami z podziałem na firmy, suma rozrachunków z odbiorcami według kwartałów oraz salda kont rozrachunków z odbiorcami<blockquote>[!NOTE]<br>Informacje nie obejmują sald początkowych kont księgowych rozrachunków z odbiorcami. Pokazują sumę dla nowych transakcji księgowanych w module Rozrachunki z odbiorcami.</blockquote> |

Wykresy i kafelki we wszystkich tych raportach można filtrować i przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Następujące jednostki zostały użyte jako podstawa w pakiecie zawartości usługi Power BI **Wyniki finansowe**:

**Jednostki zagregowanych danych**

- **GeneralLedgerActivities** — ta jednostka agreguje salda księgi głównej według kategorii kont.
- **BudgetActivities** — ta jednostka agreguje salda budżetu według kategorii kont.

**Jednostki danych**

- FiscalCalendars
- MainAccounts
- LegalEntities
- Księgi
- ChartofAccounts

Te jednostki zostały użyte do utworzenia obliczanych miar w modelu danych. Obliczane miary są używane do obliczania kluczowych wskaźników wydajności (KPI) i generowania raportów, które są używane w pakiecie zawartości. Domyślnie pakiet zawartości grupuje dane z trzech ostatnich lat i jednego roku przyszłego. Aby uwzględnić dodatkowe obliczenia w raportach i pulpicie nawigacyjnym, można zmodyfikować [skoroszyt programu Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Ten skoroszyt jest domyślnym modelem danych, który został użyty do utworzenia pakietu zawartości. 

