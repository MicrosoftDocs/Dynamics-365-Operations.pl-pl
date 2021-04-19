---
title: Konfigurowanie eksperymentu
description: W tym temacie opisano sposób konfigurowania eksperymentów w usłudze innej firmy.
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
ms.openlocfilehash: 9976ca461f7e988c32b81565fa2d084709e5ad6e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792517"
---
# <a name="set-up-an-experiment"></a><span data-ttu-id="8c301-103">Konfigurowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="8c301-103">Set up an experiment</span></span>

<span data-ttu-id="8c301-104">Po [zdefiniowaniu hipotezy i określeniu, jakie metryki sukcesu mają być używane](experimentation-identify.md) należy skonfigurować eksperyment w usłudze innej firmy.</span><span class="sxs-lookup"><span data-stu-id="8c301-104">After you [define a hypothesis and determine what success metrics you want to use](experimentation-identify.md), you'll need to set up your experiment in the third-party service.</span></span> <span data-ttu-id="8c301-105">Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8c301-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="8c301-106">Dodatkowe kroki są zawarte w odrębnych tematach.</span><span class="sxs-lookup"><span data-stu-id="8c301-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="8c301-107">[ ![Proces użytkownika eksperymentu — konfiguracja](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8c301-107">[ ![Experimentation user journey - Setup](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span></span>


## <a name="set-up-your-experiment-in-the-third-party-service"></a><span data-ttu-id="8c301-108">Konfigurowanie eksperymentu w usłudze innej firmy</span><span class="sxs-lookup"><span data-stu-id="8c301-108">Set up your experiment in the third-party service</span></span>
<span data-ttu-id="8c301-109">Teraz masz już wybraną usługę innej firmy, aby uruchomić i monitorować eksperyment, a następnie skonfigurować łącznik eksperymentów.</span><span class="sxs-lookup"><span data-stu-id="8c301-109">By now you should have chosen your third-party service to run and monitor your experiment, and set up the experimentation connector.</span></span> <span data-ttu-id="8c301-110">Te wymagania wstępne wymieniono w temacie [Eksperymentowanie w systemie Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8c301-110">These prerequisites are listed in  [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="8c301-111">Wykonaj kroki wymagane do utworzenia eksperymentu w usłudze innej firmy.</span><span class="sxs-lookup"><span data-stu-id="8c301-111">Follow the steps required to create your experiment in the third-party service.</span></span> <span data-ttu-id="8c301-112">Jeśli łącznik jest skonfigurowany prawidłowo, pełna lista eksperymentów skonfigurowanych w ramach usługi innej firmy będzie widoczna w konstruktorze witryn Commerce w ciągu około 5 minut.</span><span class="sxs-lookup"><span data-stu-id="8c301-112">If the connector is configured properly, the complete list of experiments you set up in the third-party service will appear in Commerce site builder within about 5 minutes.</span></span>

## <a name="set-up-your-success-metrics"></a><span data-ttu-id="8c301-113">Konfigurowanie metryk sukcesu</span><span class="sxs-lookup"><span data-stu-id="8c301-113">Set up your success metrics</span></span>
<span data-ttu-id="8c301-114">Każdy eksperyment wymaga metryk, aby zmierzyć wpływ tych odmian i sprawdzić poprawność hipotezy.</span><span class="sxs-lookup"><span data-stu-id="8c301-114">Every experiment needs metrics to measure the impact of the variations and to validate the hypothesis.</span></span> <span data-ttu-id="8c301-115">Wykonaj poniższe kroki, aby włączyć obliczanie metryk w usłudze innej firmy przy użyciu zdarzeń aktywnych telemetrii z systemu Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8c301-115">Follow the steps below to enable the computation of metrics in the third-party service using live telemetry events from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8c301-116">Aby skonfigurować metryki sukcesu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8c301-116">To set up your success metrics, follow these steps.</span></span>

1. <span data-ttu-id="8c301-117">W konstruktorze witryn Commerce wybierz kartę **Strony** w lewym okienku nawigacji, a następnie wybierz stronę, na której mają być zbierane metryki.</span><span class="sxs-lookup"><span data-stu-id="8c301-117">In Commerce site builder, select **Pages** in the left navigation pane, and then select the page that you want to collect metrics for.</span></span> 
1. <span data-ttu-id="8c301-118">Przejdź do sekcji **Identyfikatory zdarzeń do śledzenia** w prawym okienku właściwości strony lub modułu, który chcesz śledzić.</span><span class="sxs-lookup"><span data-stu-id="8c301-118">Go to the **Event IDs to track** section in the right property pane of the page or module you want to track.</span></span>
1. <span data-ttu-id="8c301-119">Wybierz pozycję **Widok**.</span><span class="sxs-lookup"><span data-stu-id="8c301-119">Select **View**.</span></span> <span data-ttu-id="8c301-120">Zostanie wyświetlona lista wszystkich identyfikatorów zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8c301-120">A list of all event IDs is displayed.</span></span> <span data-ttu-id="8c301-121">Skopiuj zdarzenie, które chcesz śledzić, i wklej klucz zdarzenia do wskazanej lokalizacji w usłudze innej firmy.</span><span class="sxs-lookup"><span data-stu-id="8c301-121">Copy the event you want to track, and paste the event key into the designated location in the third-party service.</span></span> <span data-ttu-id="8c301-122">Jeśli potrzebne jest więcej niż jedno zdarzenie, należy skopiować klucze pojedynczo.</span><span class="sxs-lookup"><span data-stu-id="8c301-122">If you need more than one event, copy the keys one at a time.</span></span> 
    - <span data-ttu-id="8c301-123">Aby dowiedzieć się, jak wyświetlić wszystkie dostępne zdarzenia i atrybuty, w tym widoki stron i śledzenie przychodów, zobacz temat [Zdarzenia składników rozwiązania Commerce używane na potrzeby diagnostyki i rozwiązywania problemów](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="8c301-123">To learn how to view all of the available events and attributes, including page views and revenue tracking, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>
1. <span data-ttu-id="8c301-124">Wykonaj wszelkie inne kroki, aby śledzić metryki zgodnie z wymaganiami usługi innej firmy.</span><span class="sxs-lookup"><span data-stu-id="8c301-124">Take any other steps for tracking metrics as required in the third-party service.</span></span>

## <a name="previous-step"></a><span data-ttu-id="8c301-125">Poprzedni krok</span><span class="sxs-lookup"><span data-stu-id="8c301-125">Previous step</span></span>
[<span data-ttu-id="8c301-126">Określanie hipotezy i ustalanie metryki eksperymentu</span><span class="sxs-lookup"><span data-stu-id="8c301-126">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md) 


## <a name="next-step"></a><span data-ttu-id="8c301-127">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="8c301-127">Next step</span></span>
[<span data-ttu-id="8c301-128">Łączenie i edytowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="8c301-128">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]