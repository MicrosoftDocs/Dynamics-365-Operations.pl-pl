---
title: Określanie hipotezy i ustalanie metryki eksperymentu
description: W tym temacie opisano sposób identyfikowania hipotez i metryk sukcesu dla eksperymentu, który zostanie przeprowadzony na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 99642861d69b7545f03c6ed2c2650eadeb377534
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930266"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a><span data-ttu-id="209f9-103">Określanie hipotezy i ustalanie metryki sukcesu eksperymentu</span><span class="sxs-lookup"><span data-stu-id="209f9-103">Identify a hypothesis and determine success metrics for an experiment</span></span>
<span data-ttu-id="209f9-104">Pierwsza faza cyklu życia eksperymentowania obejmuje określenie hipotezy dotyczącej eksperymentu i określenie metryk, które będą śledzone w celu oceny sukcesu.</span><span class="sxs-lookup"><span data-stu-id="209f9-104">The first phase in the experimentation lifecycle includes identifying the hypothesis for the experiment and determining the metrics you'll track to evaluate success.</span></span> <span data-ttu-id="209f9-105">Na poniższym diagramie przedstawiono wszystkie kroki związane z [konfigurowaniem i przeprowadzaniem eksperymentu](experimentation-overview.md) na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="209f9-105">The following diagram shows all of the steps involved in [setting up and running an experiment](experimentation-overview.md) on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="209f9-106">Dodatkowe kroki są zawarte w odrębnych tematach.</span><span class="sxs-lookup"><span data-stu-id="209f9-106">Additional steps are covered in separate topics.</span></span> 

<span data-ttu-id="209f9-107">[ ![Proces użytkownika eksperymentu — identyfikacja](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="209f9-107">[ ![Experimentation user journey - Identify](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span></span>

<span data-ttu-id="209f9-108">Hipoteza jest deklaracją, w której przewidywany jest wynik eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="209f9-108">A hypothesis is a statement where you predict the outcome of the experiment.</span></span> <span data-ttu-id="209f9-109">Wiele czynników umożliwia zdefiniowanie hipotezy, na przykład badanie zachowań użytkownika i zebranych danych z witryn sieci Web.</span><span class="sxs-lookup"><span data-stu-id="209f9-109">Many factors go into defining a hypothesis, for example, research about user behavior and website data you've collected.</span></span> <span data-ttu-id="209f9-110">W przypadku hipotezy należy zdefiniować założenie lub teorię, które mają być zweryfikowane przez doświadczenie.</span><span class="sxs-lookup"><span data-stu-id="209f9-110">With the hypothesis, you'll define the assumption or theory you want to validate with your experiment.</span></span> <span data-ttu-id="209f9-111">Przykładem hipotezy dotyczącej eksperymentu może być „ *zdjęcie białej koszulki na stronie głównej w lecie spowoduje więcej kliknięć w niż zdjęcie granatowa swetra, ponieważ ludzie chcą latem nosić lekkie ubrania w jasnych kolorach*”.</span><span class="sxs-lookup"><span data-stu-id="209f9-111">An example of a hypothesis for your experiment may be "*a picture of a white t-shirt on my home page will drive a higher clickthrough rate than a navy sweater during summer months because people want to wear something lightweight and light colored in the summer.*"</span></span> <span data-ttu-id="209f9-112">W takim przypadku użytkownik utworzy odmiany, które zawierają białe koszulkę i granatowy sweter i opublikuje je jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="209f9-112">In that case, you'll create variations that include a white t-shirt and a navy sweater, and publish both at the same time.</span></span>

<span data-ttu-id="209f9-113">Aby sprawdzić hipotezę, sukces lub niepowodzenie eksperymentu powinno być bezpośrednio powiązane z akcjami użytkownika; na przykład, czy użytkownik serwisu witryny internetowej kliknie łącze lub przycisk.</span><span class="sxs-lookup"><span data-stu-id="209f9-113">To validate a hypothesis, the success or failure of an experiment should be directly tied to user actions; for example, if the website user clicks a link or button.</span></span> <span data-ttu-id="209f9-114">Te akcje muszą odpowiadać zdarzeniom, które będą raportowane usłudze firmy zewnętrznej do śledzenia doświadczeń.</span><span class="sxs-lookup"><span data-stu-id="209f9-114">These actions must correspond with events that will be reported to the third-party service tracking the experiment.</span></span> <span data-ttu-id="209f9-115">W miarę upływu czasu procent użytkowników, którzy podejmą akcję, zostanie podliczony jako metryka, która może być używana do generowania raportów i przeprowadzania analiz.</span><span class="sxs-lookup"><span data-stu-id="209f9-115">Over time, the percentage of users that take the action will be tallied as a metric you can use to generate reports and conduct analyses.</span></span> <span data-ttu-id="209f9-116">Patrz temat [Zdarzenia komponentów Commerce do diagnostyki i rozwiązywania problemów](dev-itpro/retail-component-events-diagnostics-troubleshooting.md), aby przejrzeć wszystkie dostępne zdarzenia i atrybuty.</span><span class="sxs-lookup"><span data-stu-id="209f9-116">Refer to the [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md) topic to review all of the available events and attributes.</span></span>

## <a name="previous-step"></a><span data-ttu-id="209f9-117">Poprzedni krok</span><span class="sxs-lookup"><span data-stu-id="209f9-117">Previous step</span></span>
[<span data-ttu-id="209f9-118">Eksperymentowanie w programie Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="209f9-118">Experimentation in Dynamics 365 Commerce</span></span>](experimentation-overview.md)


## <a name="next-step"></a><span data-ttu-id="209f9-119">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="209f9-119">Next step</span></span>
[<span data-ttu-id="209f9-120">Konfigurowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="209f9-120">Set up an experiment</span></span>](experimentation-setup.md)
