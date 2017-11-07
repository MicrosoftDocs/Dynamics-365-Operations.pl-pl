---
title: "Pakiet zawartości usługi Power BI Przegląd środków pieniężnych"
description: "W tym temacie opisano pakiet zawartość Przegląd środków pieniężnych dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: saraschi2
manager: AnnBe
ms.date: 06/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: e891f501727842e176741953df5ef9dd0336a2d5
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="cash-overview-power-bi-content"></a>Pakiet zawartości usługi Power BI Przegląd środków pieniężnych

[!include[banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartość **Przegląd środków pieniężnych** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości usługi Power BI **Przegląd środków pieniężnych** jest przeznaczony dla osób odpowiedzialnych za zarządzanie gotówką w swoich organizacjach. Pakiet zawartości **Przegląd środków pieniężnych** dla usługi Power BI zapewnia wgląd w przepływy środków pieniężnych w firmie. Dostarcza również prognoz, które mogą pomóc podejmować lepsze decyzje i w efekcie optymalizować przepływ środków pieniężnych. Można analizować środki pieniężne według firm, walut i rachunków bankowych, aby lepiej zrozumieć przyczyny nadwyżek i niedoborów.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI

Jeśli używasz programu Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017 r.), raporty z pakietu zawartości usługi Power BI **Przegląd środków pieniężnych** są wyświetlane w obszarach roboczych **Przegląd środków pieniężnych** i **Zarządzanie rachunkami bankowymi**.

Aby wyświetlić raporty prognozowania przepływów pieniężnych z danymi, najpierw należy uruchomić proces obliczania prognozy za pomocą funkcji **Oblicz prognozy przepływów pieniężnych** z obszaru Zarządzanie gotówką i bankami.  Należy to zrobić dla każdej firmy uwzględnionej w prognozie.  Następnie należy odświeżyć zagregowaną miarę LedgerCovLiquidityMeasurement na stronie **Magazyn jednostek**.  

Dla celów demonstracyjnych można za pomocą strony **Generuj dane** dodać dane demonstracyjne prognozowania przepływów pieniężnych z modułu Dane demonstracyjne.  Ten skrypt spowoduje wstawienie danych do tabel prognozowania przepływów pieniężnych, tak aby szybko wypełnić pola informacji niezbędnych dla raportów.  Ten moduł jest dostępny tylko wtedy, gdy w środowisku masz wdrożony model pakietu danych demonstracyjnych. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty umieszczone w pakiecie zawartości usługi Power BI
W poniższej tabeli przedstawiono szczegóły dotyczące mierników, które znajdują się na każdej stronie raportu w pakiecie zawartości dla usługi Power BI **Przegląd środków pieniężnych** .

| Raport                                | Zawartość |
|---------------------------------------|----------|
| Przegląd środków pieniężnych — wszystkie firmy         | <ul><li>Przychody i rozchody w walucie systemowej</li><li>Prognozowane salda w walutach</li><li>Łączne saldo rachunków bankowych w walucie systemowej</li><li>Saldo wg firmy</li><li>Dzisiejsze saldo rzeczywiste w porównaniu z prognozowanym w walucie konta bankowego</li></ul> |
| Przegląd środków pieniężnych — bieżąca firma       | <ul><li>Przychody i rozchody w walucie rozliczeniowej</li><li>Prognozowane salda w walutach</li><li>Łączne saldo rachunków bankowych w walucie rozliczeniowej</li><li>Dzisiejsze saldo rzeczywiste w porównaniu z prognozowanym w walucie konta bankowego</li></ul> |
| Prognoza przepływów pieniężnych — wszystkie firmy    | <ul><li>Przychody i rozchody w walucie systemowej</li><li>Dzienne podsumowanie prognoz</li><li>Szczegóły prognozy</li></ul> |
| Prognoza przepływów pieniężnych — waluta firmy | <ul><li>Przychody i rozchody w walucie rozliczeniowej</li><li>Dzienne podsumowanie prognoz</li><li>Szczegóły prognozy</li></ul> |
| Prognoza dla waluty                     | <ul><li>Prognozowane salda w walutach</li><li>Dzienne podsumowanie waluty</li><li>Szczegóły prognozy</li></ul> |
| Salda rachunków bankowych                         | <ul><li>Łączne saldo rachunków bankowych w walucie systemowej</li><li>Saldo wg firmy</li><li>Dzisiejsze saldo rzeczywiste w porównaniu z prognozowanym w walucie konta bankowego</li><li>Saldo wg konta bankowego</li><li>Saldo wg waluty</li></ul> |

## <a name="extending-the-power-bi-content"></a>Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI
Za pomocą pakietów zawartości dostępnych w usłudze Lifecycle Services (LCS) można dostarczyć zaawansowane funkcje analityczne użytkownikom, którzy się nie logują w programie Dynamics 365 . Te pakiety zawartości można modyfikować, tak aby zawierały inne raporty lub wizualizacje, a następnie publikować w swojej dzierżawie usługi Power BI.com na potrzeby wykonywania analiz. 

Pakiet zawartości usługi Power BI **Przegląd środków pieniężnych** znajduje się w bibliotece zasobów wspólnych w usłudze LCS. Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](../../dev-itpro/analytics/power-bi-content-microsoft-partners.md). Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

W poniższej tabeli przedstawiono jednostki, na których bazuje pakiet zawartości **Przegląd środków pieniężnych** dostępny dla usługi Power BI.

| Jednostka                                                                          | Zawartość |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | Firmy, według których będą filtrowane raporty |
| LedgerCovLiquidityMeasurement\_Date                                             | Daty, według których będą filtrowane raporty |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Rzeczywiste saldo rachunków bankowych w porównaniu z ostatnim prognozowanym saldem rachunków bankowych |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Szczegóły prognozowanej transakcji |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Zsumowane przychody, rozchody i salda środków pieniężnych w walucie rozliczeniowej każdej firmy |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Zsumowane przychody, rozchody i salda środków pieniężnych w walucie systemowej dla wszystkich firm |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Zsumowana kwota netto transakcji oraz salda walut w walutach transakcji |

Te jednostki zostały użyte do utworzenia obliczanych miar w modelu danych. Następnie obliczone mierniki są używane do obliczeń dla wykresów i raportów używanych w pakiecie zawartości usługi Power BI **Przegląd środków pieniężnych**. Aby umieścić dodatkowe obliczenia w raportach i na pulpicie nawigacyjnym, możesz z usługi LCS pobrać plik usługi Power BI i go zmodyfikować. Ten plik jest domyślnym modelem danych, który został użyty do utworzenia pakietu zawartości. Po wprowadzeniu wszystkich modyfikacji można utworzyć organizacyjny pakiet zawartości i pulpity nawigacyjne, który zawierają dodane informacje.


