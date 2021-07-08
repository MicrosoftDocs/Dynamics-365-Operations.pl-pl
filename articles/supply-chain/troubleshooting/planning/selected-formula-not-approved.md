---
title: Numer wybranej formuły nie jest zatwierdzony dla zamówienia partii
description: Podczas próby utworzenia planowanego zamówienia pojawia się komunikat o błędzie z informacją, że wybrany numer formuły nie jest zatwierdzony dla zamówienia wsadowego.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294151"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a><span data-ttu-id="a4ec3-103">Numer wybranej formuły nie jest zatwierdzony dla zamówienia partii</span><span class="sxs-lookup"><span data-stu-id="a4ec3-103">Selected formula number isn't approved for a batch order</span></span>

<span data-ttu-id="a4ec3-104">Kod błędu: PRO2614</span><span class="sxs-lookup"><span data-stu-id="a4ec3-104">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="a4ec3-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="a4ec3-105">Symptoms</span></span>

<span data-ttu-id="a4ec3-106">Przy próbie potwierdzenia planowanego zlecenia pojawia się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="a4ec3-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="a4ec3-107">Numer wybranej formuły nie jest zatwierdzony dla szarży produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="a4ec3-107">The selected formula number is not approved for a batch order.</span></span>

## <a name="cause"></a><span data-ttu-id="a4ec3-108">Powód</span><span class="sxs-lookup"><span data-stu-id="a4ec3-108">Cause</span></span>

<span data-ttu-id="a4ec3-109">System sprawdza poprawność operacji firmowania, aby upewnić się, że dla aktywnej pozycji dostępna jest zatwierdzona formuła.</span><span class="sxs-lookup"><span data-stu-id="a4ec3-109">The system validates the firming operation to make sure that an approved formula is available for the active item.</span></span> <span data-ttu-id="a4ec3-110">Prawdopodobnie należy zatwierdzić formułę.</span><span class="sxs-lookup"><span data-stu-id="a4ec3-110">You must probably approve the formula.</span></span>

## <a name="resolution"></a><span data-ttu-id="a4ec3-111">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="a4ec3-111">Resolution</span></span>

<span data-ttu-id="a4ec3-112">Aby zatwierdzić formułę, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a4ec3-112">To approve a formula, follow these steps.</span></span>

1. <span data-ttu-id="a4ec3-113">Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Listy składowe (BOM) i formuły \> Formuły**.</span><span class="sxs-lookup"><span data-stu-id="a4ec3-113">Go to **Product information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="a4ec3-114">Wybierz odpowiednią formułę.</span><span class="sxs-lookup"><span data-stu-id="a4ec3-114">Select the relevant formula.</span></span>
1. <span data-ttu-id="a4ec3-115">W okienku akcji na karcie **Formuła** w grupie **Obsługa** wybierz opcję **Zatwierdź formułę**.</span><span class="sxs-lookup"><span data-stu-id="a4ec3-115">On the Action Pane, on the **Formula** tab, in the **Maintain** group, select **Approve formula**.</span></span>
1. <span data-ttu-id="a4ec3-116">W oknie dialogowym **Zatwierdzanie BOM lub formuły** wybierz osobę zatwierdzającą, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4ec3-116">In the **Approve BOM or formula** dialog box, select an approver, and then select **OK**.</span></span>
