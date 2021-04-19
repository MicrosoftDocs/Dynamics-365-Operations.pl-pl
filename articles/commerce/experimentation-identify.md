---
title: Określanie hipotezy i ustalanie metryki eksperymentu
description: W tym temacie opisano sposób identyfikowania hipotez i metryk sukcesu dla eksperymentu, który zostanie przeprowadzony na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: a3f5d44e008e4092557d75c8f5d830d5ae36a091
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799061"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a><span data-ttu-id="96bd6-103">Określanie hipotezy i ustalanie metryki sukcesu eksperymentu</span><span class="sxs-lookup"><span data-stu-id="96bd6-103">Identify a hypothesis and determine success metrics for an experiment</span></span>
<span data-ttu-id="96bd6-104">Pierwsza faza cyklu życia eksperymentowania obejmuje określenie hipotezy dotyczącej eksperymentu i określenie metryk, które będą śledzone w celu oceny sukcesu.</span><span class="sxs-lookup"><span data-stu-id="96bd6-104">The first phase in the experimentation lifecycle includes identifying the hypothesis for the experiment and determining the metrics you'll track to evaluate success.</span></span> <span data-ttu-id="96bd6-105">Na poniższym diagramie przedstawiono wszystkie kroki związane z [konfigurowaniem i przeprowadzaniem eksperymentu](experimentation-overview.md) na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="96bd6-105">The following diagram shows all of the steps involved in [setting up and running an experiment](experimentation-overview.md) on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="96bd6-106">Dodatkowe kroki są zawarte w odrębnych tematach.</span><span class="sxs-lookup"><span data-stu-id="96bd6-106">Additional steps are covered in separate topics.</span></span> 

<span data-ttu-id="96bd6-107">[ ![Proces użytkownika eksperymentu — identyfikacja](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="96bd6-107">[ ![Experimentation user journey - Identify](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span></span>

<span data-ttu-id="96bd6-108">Hipoteza jest deklaracją, w której przewidywany jest wynik eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="96bd6-108">A hypothesis is a statement where you predict the outcome of the experiment.</span></span> <span data-ttu-id="96bd6-109">Wiele czynników umożliwia zdefiniowanie hipotezy, na przykład badanie zachowań użytkownika i zebranych danych z witryn sieci Web.</span><span class="sxs-lookup"><span data-stu-id="96bd6-109">Many factors go into defining a hypothesis, for example, research about user behavior and website data you've collected.</span></span> <span data-ttu-id="96bd6-110">W przypadku hipotezy należy zdefiniować założenie lub teorię, które mają być zweryfikowane przez doświadczenie.</span><span class="sxs-lookup"><span data-stu-id="96bd6-110">With the hypothesis, you'll define the assumption or theory you want to validate with your experiment.</span></span> <span data-ttu-id="96bd6-111">Przykładem hipotezy dotyczącej eksperymentu może być „ *zdjęcie białej koszulki na stronie głównej w lecie spowoduje więcej kliknięć w niż zdjęcie granatowa swetra, ponieważ ludzie chcą latem nosić lekkie ubrania w jasnych kolorach*”.</span><span class="sxs-lookup"><span data-stu-id="96bd6-111">An example of a hypothesis for your experiment may be "*a picture of a white t-shirt on my home page will drive a higher clickthrough rate than a navy sweater during summer months because people want to wear something lightweight and light colored in the summer.*"</span></span> <span data-ttu-id="96bd6-112">W takim przypadku użytkownik utworzy odmiany, które zawierają białe koszulkę i granatowy sweter i opublikuje je jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="96bd6-112">In that case, you'll create variations that include a white t-shirt and a navy sweater, and publish both at the same time.</span></span>

<span data-ttu-id="96bd6-113">Aby sprawdzić hipotezę, sukces lub niepowodzenie eksperymentu powinno być bezpośrednio powiązane z akcjami użytkownika; na przykład, czy użytkownik serwisu witryny internetowej kliknie łącze lub przycisk.</span><span class="sxs-lookup"><span data-stu-id="96bd6-113">To validate a hypothesis, the success or failure of an experiment should be directly tied to user actions; for example, if the website user clicks on a link or button.</span></span> <span data-ttu-id="96bd6-114">Te akcje muszą odpowiadać zdarzeniom, które będą raportowane usłudze firmy zewnętrznej do śledzenia doświadczeń.</span><span class="sxs-lookup"><span data-stu-id="96bd6-114">These actions must correspond with events that will be reported to the third-party service tracking the experiment.</span></span> <span data-ttu-id="96bd6-115">W miarę upływu czasu procent użytkowników, którzy podejmą akcję, zostanie podliczony jako metryka, która może być używana do generowania raportów i przeprowadzania analiz.</span><span class="sxs-lookup"><span data-stu-id="96bd6-115">Over time, the percentage of users that take the action will be tallied as a metric you can use to generate reports and conduct analyses.</span></span> <span data-ttu-id="96bd6-116">Aby przejrzeć wszystkie dostępne zdarzenia i atrybuty, zobacz [Zdarzenia komponentów Commerce do diagnostyki i rozwiązywania problemów](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="96bd6-116">To review all of the available events and attributes, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>

## <a name="previous-step"></a><span data-ttu-id="96bd6-117">Poprzedni krok</span><span class="sxs-lookup"><span data-stu-id="96bd6-117">Previous step</span></span>
[<span data-ttu-id="96bd6-118">Eksperymentowanie w programie Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="96bd6-118">Experimentation in Dynamics 365 Commerce</span></span>](experimentation-overview.md)


## <a name="next-step"></a><span data-ttu-id="96bd6-119">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="96bd6-119">Next step</span></span>
[<span data-ttu-id="96bd6-120">Konfigurowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="96bd6-120">Set up an experiment</span></span>](experimentation-setup.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]