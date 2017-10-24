---
title: "Pakiet zawartości usługi Power BI Wartości rzeczywiste a budżet"
description: "W tym temacie opisano pakiet zawartość Wartości rzeczywiste a budżet dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: ryansandness
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: afa8e07505283531c97663f35b208d82d69d2b42
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="actual-vs-budget-power-bi-content"></a>Pakiet zawartości usługi Power BI Wartości rzeczywiste a budżet

[!include[banner](../includes/banner.md)]


W tym temacie opisano pakiet zawartość **Wartości rzeczywiste a budżet** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu. 

# <a name="overview"></a>Przegląd

Pakiet zawartości usługi Power BI **Wartości rzeczywiste a budżet** jest przeznaczony dla osób odpowiedzialnych za monitorowanie wartości rzeczywistych w porównaniu z zabudżetowanymi w swoich organizacjach. Pakiet zawartość usługi Power BI **Wartości rzeczywiste a budżet** zapewnia wgląd w odchylenia budżetu. Można analizować budżet dla bieżącego roku według kategorii kont, kodów budżetu, kont głównych, opisów konta głównego lub okresów obrachunkowych, aby lepiej zrozumieć przyczyny wszelkich odchyleń . 

# <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017 r.), raporty z pakietu zawartości usługi Power BI **Wartości rzeczywiste a budżet** są wyświetlane w obszarach roboczych **Budżet księgi i prognozy** oraz **Dyrektor finansowy**.

# <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty umieszczone w pakiecie zawartości usługi Power BI
W poniższej tabeli przedstawiono szczegóły dotyczące mierników, które znajdują się na każdej stronie raportu w pakiecie zawartości dla usługi Power BI **Wartości rzeczywiste a budżet** .

| Raport                      | Metryki |
|-----------------------------|---------|
| Wydatki — wartości rzeczywiste a budżet | <ul><li>Łączne wydatki w roku</li><li>Łączne zabudżetowane wydatki w roku</li></ul> |
| Przychody — wartości rzeczywiste a budżet  | <ul><li>Łączne przychody w roku</li><li>Łączne zabudżetowane przychody w roku</li><ul> |
| Wydatki                     | <ul><li>Łączne wydatki w roku</li><li>Cel wydatków założony w budżecie </li><ul> |
| Przychód                     | <ul><li>Łączne przychody w roku</li><li>Cel przychodów założony w budżecie </li><ul> |
| Dochód netto                  | <ul><li>Dochód netto w roku</li><li>Cel dochodu netto założony w budżecie </li><ul> |

## <a name="extending-the-power-bi-content"></a>Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI
Za pomocą pakietów zawartości dostępnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) można dostarczać zaawansowane funkcje analityczne osobom, które się nie logują w programie Microsoft Dynamics 365. Te pakiety zawartości można modyfikować, tak aby zawierały inne raporty lub wizualizacje, a następnie publikować je w swojej dzierżawie usługi Power BI.com na potrzeby wykonywania analiz. 

Pakiet zawartości usługi Power BI **Wartości rzeczywiste a budżet** znajduje się w bibliotece zasobów wspólnych w usłudze LCS. Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md). Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

# <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

| Jednostka                    | Zawartość |
|---------------------------|----------|
| Działania na księdze głównej | Kwoty transakcji w księdze głównej |
| Działania na budżecie         | Kwoty transakcji w rejestrze budżetu |
| Konta główne             | Konta główne, według których będą filtrowane raporty |
| Kalendarze obrachunkowe          | Kalendarze obrachunkowe, według których będą filtrowane raporty |
| Księgi                   | Księgi, które można wyfiltrować jako bieżące księgi dla raportu |
| Kody budżetu              | Kody budżetu, według których będą filtrowane raporty |
| Firmy            | Firmy, które można wyfiltrować jako bieżące firmy dla raportu |

