---
title: "Zgłaszanie zleceń produkcyjnych jako gotowych"
description: "Zgłoszenie wyrobów gotowych to etap produkcji. Na tym etapie produkt gotowy jest zgłaszany i przenoszony ze zlecenia produkcyjnego do zapasów."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fa40733e3f1310869ead8b0ac774bb621637e250
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="report-production-orders-as-finished"></a><span data-ttu-id="d4878-104">Zgłaszanie zleceń produkcyjnych jako gotowych</span><span class="sxs-lookup"><span data-stu-id="d4878-104">Report production orders as finished</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="d4878-105">Zgłoszenie wyrobów gotowych to etap produkcji.</span><span class="sxs-lookup"><span data-stu-id="d4878-105">Report as finished is a production stage.</span></span> <span data-ttu-id="d4878-106">Na tym etapie produkt gotowy jest zgłaszany i przenoszony ze zlecenia produkcyjnego do zapasów.</span><span class="sxs-lookup"><span data-stu-id="d4878-106">At this stage, a finished product is reported and moved from the production order to the inventory.</span></span>

<span data-ttu-id="d4878-107">Kiedy ilości wyprodukowanych towarów zostanie zgłoszona jako ukończona w zleceniu produkcyjnym, jest ona aktualizowana w magazynie.</span><span class="sxs-lookup"><span data-stu-id="d4878-107">When a quantity of the finished goods is reported as finished on a production order it is updated as on-hand in the inventory.</span></span> <span data-ttu-id="d4878-108">Ilości częściowe pierwotnie zaplanowanego zamówienia mogą być zgłaszane jako gotowe.</span><span class="sxs-lookup"><span data-stu-id="d4878-108">Partial quantities of the originally planned order quantity can be reported as finished.</span></span> <span data-ttu-id="d4878-109">Można też zgłaszać błędne ilości razem ze skojarzonym powodem błędu podczas raportowania ilości jako gotowych.</span><span class="sxs-lookup"><span data-stu-id="d4878-109">It is also possible to report error quantities with an associated error reason when reporting quantities as finished.</span></span> <span data-ttu-id="d4878-110">Gdy zlecenie produkcyjne osiągnie etap „Zgłoszone jako gotowe”, wskazuje ono, że dalsze ilości nie będą zgłaszane w zleceniu produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="d4878-110">When the production order reach the stage Reported as finished it indicates that no more quantity is going to be reported at the production  order.</span></span>
<span data-ttu-id="d4878-111">Z procesem **zgłaszania gotowych wyrobów** wiążą się następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="d4878-111">The following characteristics are also associated with the **Report as finished** process:</span></span>
-   <span data-ttu-id="d4878-112">Można ustawić zużycie surowców i czas proporcjonalnie do zgłoszonych ilości (kalkulacja zużycia wstecz)</span><span class="sxs-lookup"><span data-stu-id="d4878-112">It is possible to set up consumption of raw material and time that are proportional to the reported quantity (back-flushing)</span></span>
-   <span data-ttu-id="d4878-113">Można generować odłożenia dla towarów, które są włączone dla procesów magazynu.</span><span class="sxs-lookup"><span data-stu-id="d4878-113">Put-away work can be generated for items that are enabled for warehouse processes.</span></span>
-   <span data-ttu-id="d4878-114">Planowana lub standardowa wartość koszty wyrobów gotowych można skonfigurować w taki sposób, by były zgłaszane na kontach księgowych.</span><span class="sxs-lookup"><span data-stu-id="d4878-114">The planned or standard cost value of the finished goods can be set up to be reported to ledger accounts.</span></span>
-   <span data-ttu-id="d4878-115">Można utworzyć zlecenie kontroli jakości dla zgłoszonej ilości na podstawie konfiguracji skojarzenia jakości.</span><span class="sxs-lookup"><span data-stu-id="d4878-115">A quality order can be created for the reported quantity based on the setup of a quality association.</span></span>

<span data-ttu-id="d4878-116">Ilość jest zgłaszana do lokalizacji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="d4878-116">The quantity is reported to the output location.</span></span> <span data-ttu-id="d4878-117">Następnie generowana jest praca magazynowa w celu przeniesienia ilości z lokalizacji wyjściowej do miejsca docelowego zdefiniowanego przez dyrektywę lokalizacji dla odłożeń.</span><span class="sxs-lookup"><span data-stu-id="d4878-117">Warehouse work is then generated to move the quantity from the output location to its final destination defined by the location directive for the put-away work.</span></span>

-   <span data-ttu-id="d4878-118">Zlecenie kontroli jakości może być utworzone podczas zgłaszania zlecenia produkcyjnego jako zakończonego, jeśli skojarzenie jakości zostało skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="d4878-118">A quality order can be created when a production order is reported as finished if a quality association has been set up.</span></span>

## <a name="set-a-production-order-to-reporting-as-finished"></a><span data-ttu-id="d4878-119">Ustawianie stanu zlecenia produkcyjnego na Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="d4878-119">Set a production order to Reporting as finished</span></span>
<span data-ttu-id="d4878-120">Można ustawić stan zlecenia produkcyjnego na **Zgłoszenie wyrobów gotowych** a pomocą standardowej funkcji aktualizacji zlecenia produkcyjnego lub za pomocą arkusza marszruty i karty karta zadań albo za pomocą arkusza **Zgłoszenie wyrobów gotowych**.</span><span class="sxs-lookup"><span data-stu-id="d4878-120">You can set a production order to **Report as finished** through the standard production order update function, or through the route and job card journals, or through the journal **Report as finished**.</span></span> <span data-ttu-id="d4878-121">Można także zaktualizować etap na **Zgłoszenie wyrobów gotowych** za pomocą stron terminalu karty zadań i urządzenia karty zadań podczas zgłaszania ostatniego zadania zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d4878-121">You can also update the stage to **Report as finished** through the job card terminal and job card device pages, when you report on the last job of the production order.</span></span> <span data-ttu-id="d4878-122">Wreszcie można włączyć opcję **Zgłoszenie wyrobów gotowych** jako proces dla rozwiązania urządzenia podręcznego magazynu.</span><span class="sxs-lookup"><span data-stu-id="d4878-122">Finally, you can enable the **Report as finished** option as a process for the handheld warehouse device solution.</span></span>  




