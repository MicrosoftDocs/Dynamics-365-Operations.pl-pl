---
title: Tworzenie budżetu konserwacji
description: W tym temacie wyjaśniono, jak utworzyć budżet konserwacji w zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 593a03e3317de5759427dfc61093530c4b7ef7e9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253501"
---
# <a name="create-maintenance-budgets"></a><span data-ttu-id="e8031-103">Tworzenie budżetu konserwacji</span><span class="sxs-lookup"><span data-stu-id="e8031-103">Create maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 



<span data-ttu-id="e8031-104">Budżety konserwacji są używane w celu uzyskania przeglądu oczekiwanych kosztów konserwacji profilaktycznej.</span><span class="sxs-lookup"><span data-stu-id="e8031-104">Maintenance budgets are used to provide an overview of expected costs for preventive maintenance.</span></span> <span data-ttu-id="e8031-105">Wiersze budżetu są obliczane na podstawie wierszy harmonogramu konserwacji, w których oczekiwana jest data rozpoczęcia w okresie budżetowym.</span><span class="sxs-lookup"><span data-stu-id="e8031-105">Budget lines are calculated based on maintenance schedule lines that have an expected start date during the budget period.</span></span>

<span data-ttu-id="e8031-106">Budżety obsługi są oparte na typach kosztów używanych w module Zarządzanie środkami trwałymi: **Zapobiegawcze**, **Korygujące** i **Inwestycyjne**.</span><span class="sxs-lookup"><span data-stu-id="e8031-106">Maintenance budgets are based on the cost types that are used in Asset Management: **Preventive**, **Corrective**, and **Investment**.</span></span> <span data-ttu-id="e8031-107">Koszty budżetowe związane z obsługą inwestycji są uwzględniane w aktywnych składnikach majątku, które mają datę wymiany w okresie budżetu oraz powiązaną wartość zamienną.</span><span class="sxs-lookup"><span data-stu-id="e8031-107">Budget costs for investment maintenance are included for active assets that have a replacement date during the budget period and a related replacement value.</span></span> <span data-ttu-id="e8031-108">Koszty budżetowe dotyczące konserwacji są uwzględniane, jeśli w obliczeniu budżetu jest uwzględniona wcześniejsza data korekty.</span><span class="sxs-lookup"><span data-stu-id="e8031-108">Budget costs for corrective maintenance are included if a past corrective date is included in the budget calculation.</span></span> <span data-ttu-id="e8031-109">W takim przypadku koszty korygujące z wcześniejszego okresu są obliczane dla tego samego przyszłego okresu, dla którego jest obliczany budżet konserwacji.</span><span class="sxs-lookup"><span data-stu-id="e8031-109">In that case, corrective costs from an earlier period are calculated for the same future period that you calculate the maintenance budget for.</span></span>

## <a name="create-a-maintenance-budget"></a><span data-ttu-id="e8031-110">Stwórz budżet konserwacji</span><span class="sxs-lookup"><span data-stu-id="e8031-110">Create a maintenance budget</span></span>

1. <span data-ttu-id="e8031-111">Wybierz **Zarządzanie składnikami majątku** \> **Zapytania** \> **Budżet konserwacji** \> **Budżet**.</span><span class="sxs-lookup"><span data-stu-id="e8031-111">Select **Asset management** \> **Inquiries** \> **Maintenance budget** \> **Budget**.</span></span>
2. <span data-ttu-id="e8031-112">Wybierz **Utwórz budżet**.</span><span class="sxs-lookup"><span data-stu-id="e8031-112">Select **Create budget**.</span></span>
3. <span data-ttu-id="e8031-113">W polu **Budżet konserwacji** wprowadź identyfikator budżetu.</span><span class="sxs-lookup"><span data-stu-id="e8031-113">In the **Maintenance budget** field, enter a budget ID.</span></span>
4. <span data-ttu-id="e8031-114">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="e8031-114">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="e8031-115">Na skróconej karcie **Okres** w polach **Od dnia** i **Do dnia**, wprowadź datę początkową i końcową okresu budżetu.</span><span class="sxs-lookup"><span data-stu-id="e8031-115">On the **Period** FastTab, in the **From date** and **To date** fields, enter the start and end dates of the budget period.</span></span>
5. <span data-ttu-id="e8031-116">Aby uwzględnić koszty z budżetu korygującego obliczone na podstawie kosztów rzeczywistych z poprzedniego okresu, w polu **Popraw od dnia** wprowadź datę początkową okresu, z którego mają być uwzględniane te koszty.</span><span class="sxs-lookup"><span data-stu-id="e8031-116">To include corrective budget costs that are calculated on the basis of actual costs from a previous period, in the **Corrective from date** field, enter the start date of the period that those costs should be included from.</span></span>
6. <span data-ttu-id="e8031-117">W zależności od poziomu szczegółowości wymaganego w budżecie należy określić odpowiednie opcje na pięciu kartach skróconych **Grupuj wg**.</span><span class="sxs-lookup"><span data-stu-id="e8031-117">Depending on the level of detail that is required in the budget, set the relevant options on the five **Group by** FastTabs.</span></span>
7. <span data-ttu-id="e8031-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8031-118">Select **OK**.</span></span>
8. <span data-ttu-id="e8031-119">Wybierz **Wiersze budżetu**, aby otworzyć stronę **Wiersze budżetu konserwacji**, na której możesz przejrzeć wszystkie wiersze budżetu, które zostały utworzone dla okresu.</span><span class="sxs-lookup"><span data-stu-id="e8031-119">Select **Budget lines** to open **Maintenance budget lines** page, where you can view all the budget lines that have been created for the period.</span></span>
9. <span data-ttu-id="e8031-120">Aby zatwierdzić budżet, wybierz go na stronie **Budżety konserwacji**, a następnie wybierz pozycję **Zatwierdź**.</span><span class="sxs-lookup"><span data-stu-id="e8031-120">To approve the budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="e8031-121">Następnie w oknie dialogowym **Zatwierdź budżet** budżetu przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8031-121">Then, in the **Approve budget** dialog box, select **OK**.</span></span> <span data-ttu-id="e8031-122">Twoja nazwa użytkownika jest wprowadzana w polu **Zatwierdzone przez** na stronie **Budżety konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="e8031-122">Your name is entered in the **Approved by** field on the **Maintenance budgets** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e8031-123">Po zatwierdzeniu budżetu konserwacji nie można ponownie obliczyć ani skorygować powiązanych wierszy na stronie **Wiersze budżetu konserwacji**, dopóki nie zostanie wcześniej usunięte zatwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="e8031-123">After you've approved a maintenance budget, you can't recalculate or adjust the related lines on the **Maintenance budget lines** page unless you first remove the approval.</span></span> <span data-ttu-id="e8031-124">Aby usunąć potwierdzenie budżetu konserwacji, wybierz go na stronie **Budżety konserwacji**, a następnie wybierz pozycję **Zatwierdź**.</span><span class="sxs-lookup"><span data-stu-id="e8031-124">To remove the approval of a maintenance budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="e8031-125">Następnie w oknie dialogowym **Zatwierdź budżet** budżetu przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8031-125">Then, in the **Approve budget** dialog box, select **OK**.</span></span>

![Budżety konserwacji](media/01-maintenance-budgets.png)

<span data-ttu-id="e8031-127">Kopiując istniejący budżet można również utworzyć nowy budżet konserwacji.</span><span class="sxs-lookup"><span data-stu-id="e8031-127">You can also create a new maintenance budget by copying an existing budget.</span></span> <span data-ttu-id="e8031-128">Na stronie **Budżety konserwacji** wybierz budżet do skopiowania, a następnie wybierz pozycję **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="e8031-128">On the **Maintenance budgets** page, select the budget to copy, and then select **Copy**.</span></span> <span data-ttu-id="e8031-129">Ta metoda jest przydatna na przykład wtedy, gdy użytkownik utworzył budżet na jeden miesiąc i chce skopiować go do innych miesięcy.</span><span class="sxs-lookup"><span data-stu-id="e8031-129">This approach is useful if, for example, you've created a budget for one month and want to copy it to other months.</span></span>

> [!NOTE]
> <span data-ttu-id="e8031-130">Budżet konserwacji oblicza tylko koszty budżetowe na podstawie wierszy harmonogramu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="e8031-130">The maintenance budget calculates only budget costs based on maintenance schedule lines.</span></span> <span data-ttu-id="e8031-131">Aby obliczyć koszty rzeczywiste za ten sam okres, można wykonać obliczenia na stronie kontrola **Formant kosztów składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="e8031-131">To calculate actual costs for the same period, you can do that calculation on the **Asset cost control** page.</span></span> 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]