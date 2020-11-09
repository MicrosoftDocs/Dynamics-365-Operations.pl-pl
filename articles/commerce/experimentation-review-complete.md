---
title: Podwyższanie poziomu odmiany i kończenie eksperymentu
description: W tym temacie opisano sposób podnoszenia poziomu udanej odmiany i zakończenia eksperymentu w systemie Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
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
ms.openlocfilehash: c7da601323663d4c1ea76f7cad7bdab8e7632d1c
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097100"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="03b42-103">Podwyższanie poziomu odmiany i kończenie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="03b42-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="03b42-104">W tym temacie opisano sposób podnoszenia poziomu odmian, które wywołały najlepsze wyniki w eksperymencie, oraz sposobu zakończenia eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="03b42-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="03b42-105">Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="03b42-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="03b42-106">Dodatkowe kroki są zawarte w odrębnych tematach.</span><span class="sxs-lookup"><span data-stu-id="03b42-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="03b42-107">[ ![Proces użytkownika eksperymentu — przegląd i zakończenie](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="03b42-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="03b42-108">Po [wykonaniu eksperymentu](experimentation-run-monitor.md) i zebraniu odpowiednich danych w celu ustalenia, które odmiany mają być używane w działającej witrynie można podwyższyć poziom odmiany i zakończyć eksperyment.</span><span class="sxs-lookup"><span data-stu-id="03b42-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="03b42-109">Podwyższanie poziomu odmiany</span><span class="sxs-lookup"><span data-stu-id="03b42-109">Promote a variation</span></span>
<span data-ttu-id="03b42-110">Użyj danych i analiz związanych z eksperymentem w usłudze innej firmy w celu określenia, które odmiany dają najlepsze wyniki.</span><span class="sxs-lookup"><span data-stu-id="03b42-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="03b42-111">Następnie możesz ją promować, zamieniając bieżącą zawartość w działającej witrynie na zwycięską odmianę, tak aby była dostępna dla wszystkich użytkowników witryny internetowej.</span><span class="sxs-lookup"><span data-stu-id="03b42-111">You can then promote it by replacing the current content on the live site with the winning variation so that it's available to all users of your website.</span></span>

<span data-ttu-id="03b42-112">Aby promować wygrywającą odmianę, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="03b42-112">To promote the winning variation, follow these steps.</span></span> 

1. <span data-ttu-id="03b42-113">W konstruktorze witryn Commerce wybierz **Eksperymenty** w lewym okienku nawigacji, a następnie wybierz doświadczenie.</span><span class="sxs-lookup"><span data-stu-id="03b42-113">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span>
1. <span data-ttu-id="03b42-114">Na pasku poleceń wybierz **Zakończ eksperyment**.</span><span class="sxs-lookup"><span data-stu-id="03b42-114">On the command bar, select **Complete experiment**.</span></span>
1. <span data-ttu-id="03b42-115">W oknie dialogowym **Zakończ eksperyment** wybierz opcję **Zrecenzuj dane eksperymentu**.</span><span class="sxs-lookup"><span data-stu-id="03b42-115">In the **Complete the experiment** dialog box, select **Review the experiment data**.</span></span> <span data-ttu-id="03b42-116">Otwiera się usługa innej firmy otwiera się, można sprawdzić poprawność metryk i określić, które odmiany były najskuteczniejsze.</span><span class="sxs-lookup"><span data-stu-id="03b42-116">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="03b42-117">W okienku dialogowym **Zakończ eksperyment** wybierz zwycięską odmianę, a następnie wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="03b42-117">In the **Complete the experiment** dialog box, select the winning variation, and then select **Next**.</span></span>
1. <span data-ttu-id="03b42-118">Otwórz usługę innej firmy i zatrzymaj eksperyment.</span><span class="sxs-lookup"><span data-stu-id="03b42-118">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="03b42-119">W konstruktorze witryn wybierz opcję **Zakończ** , aby zastąpić oryginalną działającą stronę i opublikować zwycięską odmianę, tak aby była dostępna dla wszystkich użytkowników witryny internetowej.</span><span class="sxs-lookup"><span data-stu-id="03b42-119">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="03b42-120">Jeśli zostanie wybrana opcja zachowania bieżącej działające strony i nie zostanie opublikowana odmiana, wybierz opcję **Ponownie opublikuj oryginalną stronę**.</span><span class="sxs-lookup"><span data-stu-id="03b42-120">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="03b42-121">Usuwanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="03b42-121">Delete your experiment</span></span>
<span data-ttu-id="03b42-122">Jeśli nie jest wymagane usuwanie ukończonego eksperymentu w systemie Commerce, można go usunąć, aby zaoszczędzić miejsce lub oczyścić obszar roboczy.</span><span class="sxs-lookup"><span data-stu-id="03b42-122">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> 

<span data-ttu-id="03b42-123">Aby usunąć eksperyment w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="03b42-123">To delete an experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="03b42-124">Wybierz **Eksperymenty** w lewym okienku nawigacji, a następnie wybierz doświadczenie.</span><span class="sxs-lookup"><span data-stu-id="03b42-124">Select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="03b42-125">Jeśli eksperyment jest nadal aktywny, przed kontynuowaniem zatrzymaj eksperyment w usłudze innej firmy.</span><span class="sxs-lookup"><span data-stu-id="03b42-125">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="03b42-126">Wybierz opcję **Cofnij publikowanie** na pasku poleceń, aby usunąć zawartość odmiany z działającej witryny.</span><span class="sxs-lookup"><span data-stu-id="03b42-126">On the command bar, select **Unpublish**  to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="03b42-127">Wybierz przycisk **Usuń** , aby usunąć eksperyment.</span><span class="sxs-lookup"><span data-stu-id="03b42-127">Select **Delete** to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="03b42-128">Poprzedni krok</span><span class="sxs-lookup"><span data-stu-id="03b42-128">Previous step</span></span>
[<span data-ttu-id="03b42-129">Uruchamianie i monitorowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="03b42-129">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
