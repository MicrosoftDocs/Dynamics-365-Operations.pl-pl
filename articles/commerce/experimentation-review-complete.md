---
title: Podwyższanie poziomu odmiany i kończenie eksperymentu
description: W tym temacie opisano sposób podnoszenia poziomu udanej odmiany i zakończenia eksperymentu w systemie Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930264"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="a2adc-103">Podwyższanie poziomu odmiany i kończenie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="a2adc-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="a2adc-104">W tym temacie opisano sposób podnoszenia poziomu odmian, które wywołały najlepsze wyniki w eksperymencie, oraz sposobu zakończenia eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="a2adc-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="a2adc-105">Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a2adc-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="a2adc-106">Dodatkowe kroki są zawarte w odrębnych tematach.</span><span class="sxs-lookup"><span data-stu-id="a2adc-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="a2adc-107">[ ![Proces użytkownika eksperymentu — przegląd i zakończenie](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a2adc-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="a2adc-108">Po [wykonaniu eksperymentu](experimentation-run-monitor.md) i zebraniu odpowiednich danych w celu ustalenia, które odmiany mają być używane w działającej witrynie można podwyższyć poziom odmiany i zakończyć eksperyment.</span><span class="sxs-lookup"><span data-stu-id="a2adc-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="a2adc-109">Podwyższanie poziomu odmiany</span><span class="sxs-lookup"><span data-stu-id="a2adc-109">Promote a variation</span></span>
<span data-ttu-id="a2adc-110">Użyj danych i analiz związanych z eksperymentem w usłudze innej firmy w celu określenia, które odmiany dają najlepsze wyniki.</span><span class="sxs-lookup"><span data-stu-id="a2adc-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="a2adc-111">Aby zamienić bieżącą zawartość w działającej witrynie na zwycięską odmianę, tak aby była dostępna dla wszystkich użytkowników witryny internetowej, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a2adc-111">To replace the current content on the live site with the winning variation so that it's available to all users of your website, do the following.</span></span> 

1. <span data-ttu-id="a2adc-112">Przejdź na kartę **Eksperymenty** w konstruktorze witryn i wybierz eksperyment.</span><span class="sxs-lookup"><span data-stu-id="a2adc-112">Go to the **Experiments** tab in site builder and select the experiment.</span></span>
1. <span data-ttu-id="a2adc-113">Wybierz opcję **Zakończ eksperyment** na górnym pasku.</span><span class="sxs-lookup"><span data-stu-id="a2adc-113">Select **Complete experiment** on the top bar.</span></span>
1. <span data-ttu-id="a2adc-114">W menu okno dialogowego **Zakończ eksperyment** wybierz opcję **Zrecenzuj dane eksperymentu**.</span><span class="sxs-lookup"><span data-stu-id="a2adc-114">In the **Complete the experiment** dialog menu, select **Review the experiment data**.</span></span> <span data-ttu-id="a2adc-115">Otwiera się usługa innej firmy otwiera się, można sprawdzić poprawność metryk i określić, które odmiany były najskuteczniejsze.</span><span class="sxs-lookup"><span data-stu-id="a2adc-115">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="a2adc-116">W menu okno dialogowego **Zakończ eksperyment** w konstruktorze witryn wybierz zwycięską odmianę, a następnie wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="a2adc-116">In the **Complete the experiment** dialog menu in site builder, select the winning variation and then select **Next**.</span></span>
1. <span data-ttu-id="a2adc-117">Otwórz usługę innej firmy i zatrzymaj eksperyment.</span><span class="sxs-lookup"><span data-stu-id="a2adc-117">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="a2adc-118">W konstruktorze witryn wybierz opcję **Zakończ**, aby zastąpić oryginalną działającą stronę i opublikować zwycięską odmianę, tak aby była dostępna dla wszystkich użytkowników witryny internetowej.</span><span class="sxs-lookup"><span data-stu-id="a2adc-118">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="a2adc-119">Jeśli zostanie wybrana opcja zachowania bieżącej działające strony i nie zostanie opublikowana odmiana, wybierz opcję **Ponownie opublikuj oryginalną stronę**.</span><span class="sxs-lookup"><span data-stu-id="a2adc-119">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="a2adc-120">Usuwanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="a2adc-120">Delete your experiment</span></span>
<span data-ttu-id="a2adc-121">Jeśli nie jest wymagane usuwanie ukończonego eksperymentu w systemie Commerce, można go usunąć, aby zaoszczędzić miejsce lub oczyścić obszar roboczy.</span><span class="sxs-lookup"><span data-stu-id="a2adc-121">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> <span data-ttu-id="a2adc-122">Aby usunąć eksperyment, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a2adc-122">To delete an experiment, do the following.</span></span>

1. <span data-ttu-id="a2adc-123">Przejdź na kartę **Eksperymenty** w konstruktorze witryn i wybierz eksperyment.</span><span class="sxs-lookup"><span data-stu-id="a2adc-123">Go to the **Experiments** tab in site builder and select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="a2adc-124">Jeśli eksperyment jest nadal aktywny, przed kontynuowaniem zatrzymaj eksperyment w usłudze innej firmy.</span><span class="sxs-lookup"><span data-stu-id="a2adc-124">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="a2adc-125">Wybierz opcję **Cofnij publikowanie** na pasku poleceń, aby usunąć zawartość odmiany z działającej witryny.</span><span class="sxs-lookup"><span data-stu-id="a2adc-125">Select **Unpublish** in the command bar to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="a2adc-126">Wybierz opcję **Usuń** z paska poleceń, aby usunąć eksperyment.</span><span class="sxs-lookup"><span data-stu-id="a2adc-126">Select **Delete** in the command bar to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="a2adc-127">Poprzedni krok</span><span class="sxs-lookup"><span data-stu-id="a2adc-127">Previous step</span></span>
[<span data-ttu-id="a2adc-128">Uruchamianie i monitorowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="a2adc-128">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
