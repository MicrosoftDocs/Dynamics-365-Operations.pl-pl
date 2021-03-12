---
title: Uruchamianie i monitorowanie eksperymentu
description: W tym temacie opisano sposób uruchamiania i monitorowania eksperymentów w usłudze innej firmy. Opisano w nim także sposób wprowadzania zmian w odmianach po rozpoczęciu eksperymentu.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: ba6fb94033e227790e01676819308bb4f0cd6868
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965228"
---
# <a name="run-and-monitor-an-experiment"></a><span data-ttu-id="27db0-104">Uruchamianie i monitorowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="27db0-104">Run and monitor an experiment</span></span>

<span data-ttu-id="27db0-105">W tym temacie opisano sposób uruchamiania i monitorowania eksperymentów w aplikacji innej firmy oraz zmiany odmian w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="27db0-105">This topic describes how to run and monitor your experiment in a third-party app, and change variations if needed.</span></span> <span data-ttu-id="27db0-106">Przed wykonaniem kroków opisanych w tym temacie najpierw należy [opublikować](experimentation-preview-publish.md) eksperyment w Commerce.</span><span class="sxs-lookup"><span data-stu-id="27db0-106">Before you complete the steps in this topic, you'll first need to [publish](experimentation-preview-publish.md) your experiment in Commerce.</span></span> 

<span data-ttu-id="27db0-107">Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="27db0-107">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="27db0-108">Dodatkowe kroki są zawarte w odrębnych tematach.</span><span class="sxs-lookup"><span data-stu-id="27db0-108">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="27db0-109">[ ![Proces użytkownika eksperymentu — uruchamianie i monitorowanie](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="27db0-109">[ ![Experimentation user journey - Run & Monitor](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span></span>

<span data-ttu-id="27db0-110">Po opublikowaniu odmian należy wykonać wszystkie kroki niezbędne do wykonania eksperymentu w Commerce.</span><span class="sxs-lookup"><span data-stu-id="27db0-110">After you publish your variations, all of the steps you need to do in Commerce to run your experiment are complete.</span></span> <span data-ttu-id="27db0-111">Następnym krokiem jest określenie, które odmiany mają być pokazywane każdemu użytkownikowi, gdy zażądają strony.</span><span class="sxs-lookup"><span data-stu-id="27db0-111">The next step is determining which variation to show to each user when they request a page.</span></span> <span data-ttu-id="27db0-112">Usługa innej firmy wymusza to określenie, ale najpierw należy aktywować eksperyment w usłudze.</span><span class="sxs-lookup"><span data-stu-id="27db0-112">The third-party service makes that determination, but first you have to activate the experiment within the service.</span></span> <span data-ttu-id="27db0-113">Ponieważ czynności wykonywane w celu aktywowania eksperymentu różnią się w zależności od usługi, należy wykonać instrukcje dostępne w usłudze lub uzyskane od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="27db0-113">Since the steps for activating an experiment vary from service to service, you'll need to follow the instructions included with your service or provider.</span></span> <span data-ttu-id="27db0-114">Jeśli eksperyment nie zostanie aktywowany, użytkownicy będą widzieć wersję domyślną strony (nie będą wyświetlane odmiany).</span><span class="sxs-lookup"><span data-stu-id="27db0-114">If the experiment is not activated, users will only see the default version of the page (no variations will be displayed).</span></span>

<span data-ttu-id="27db0-115">Aby zebrać dane na temat wyników prawidłowych statystycznie, czasu trwania eksperymentu musi być wystarczający.</span><span class="sxs-lookup"><span data-stu-id="27db0-115">You'll need to keep the experiment running long enough to gather data for statistically valid results.</span></span> <span data-ttu-id="27db0-116">Usługa innej firmy umożliwia monitorowanie danych i analiz związanych z eksperymentem podczas wykonywania eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="27db0-116">Use the third-party service to monitor the experiment-related data and analytics while the experiment is running.</span></span>

## <a name="adjust-your-variations"></a><span data-ttu-id="27db0-117">Korygowanie odmian</span><span class="sxs-lookup"><span data-stu-id="27db0-117">Adjust your variations</span></span>
<span data-ttu-id="27db0-118">Jeśli z dowolnej przyczyny konieczna jest modyfikacja odmiany, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="27db0-118">If for any reason you need to modify your variations, follow the steps below.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27db0-119">Jeśli wprowadzisz zmiany w działającym eksperymencie w Commerce lub usłudze innej firmy, może to znacząco wpłynąć na wyniki.</span><span class="sxs-lookup"><span data-stu-id="27db0-119">If you make changes to a live experiment in Commerce or the third-party service, your results may be significantly impacted.</span></span> <span data-ttu-id="27db0-120">Rozważ możliwość przeprowadzenia eksperymentu, a następnie utworzenia nowego eksperymentu dotyczącego istotnych zmian.</span><span class="sxs-lookup"><span data-stu-id="27db0-120">Consider letting the experiment run its course and then creating a new experiment for major changes.</span></span>

1. <span data-ttu-id="27db0-121">W konstruktorze witryn Commerce wybierz **Eksperymenty** w lewym okienku nawigacji, a następnie wybierz doświadczenie.</span><span class="sxs-lookup"><span data-stu-id="27db0-121">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
1. <span data-ttu-id="27db0-122">Z menu rozwijanego wybierz odmiany, które mają zostać zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="27db0-122">Select the variation you want to update from the drop-down menu.</span></span>
1. <span data-ttu-id="27db0-123">Wprowadź wszystkie wymagane zmiany, a następnie wyświetl podgląd i opublikuj odmiany.</span><span class="sxs-lookup"><span data-stu-id="27db0-123">Make any needed changes, and then preview and publish the variations.</span></span> <span data-ttu-id="27db0-124">Aby uzyskać więcej informacji, zobacz temat [Podgląd i publikowanie eksperymentu](experimentation-preview-publish.md).</span><span class="sxs-lookup"><span data-stu-id="27db0-124">For more information, see [Preview and publish an experiment](experimentation-preview-publish.md).</span></span>
1. <span data-ttu-id="27db0-125">Przejdź do usługi innej firmy, aby dokonywać wszelkich zmian związanych z konfiguracją eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="27db0-125">Go to the third-party service to make any experiment setup-related changes.</span></span>
    
## <a name="previous-step"></a><span data-ttu-id="27db0-126">Poprzedni krok</span><span class="sxs-lookup"><span data-stu-id="27db0-126">Previous step</span></span>
[<span data-ttu-id="27db0-127">Podgląd i publikowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="27db0-127">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)

## <a name="next-step"></a><span data-ttu-id="27db0-128">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="27db0-128">Next step</span></span>
[<span data-ttu-id="27db0-129">Podwyższanie poziomu odmiany i kończenie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="27db0-129">Promote a variation and complete an experiment</span></span>](experimentation-review-complete.md)
