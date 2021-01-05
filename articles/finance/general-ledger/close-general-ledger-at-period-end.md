---
title: Zamknięcie księgi głównej na koniec okresu
description: W tym temacie opisano zadania, które zazwyczaj są wykonywane podczas wykonywania operacji zamknięcia okresu w księdze głównej.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5cabdce5e23704fbf12e631a138235174ebc5772
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446794"
---
# <a name="close-the-general-ledger-at-period-end"></a><span data-ttu-id="939b0-103">Zamknięcie księgi głównej na koniec okresu</span><span class="sxs-lookup"><span data-stu-id="939b0-103">Close the general ledger at period end</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="939b0-104">W tym temacie opisano zadania, które zazwyczaj są wykonywane podczas wykonywania operacji zamknięcia okresu w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="939b0-104">This topic describes the tasks that are typically completed when performing a period closing for General ledger.</span></span> 

<span data-ttu-id="939b0-105">W księdze głównej można wykonać procedury zamykania dla okresu lub roku.</span><span class="sxs-lookup"><span data-stu-id="939b0-105">In General ledger, you can complete closing procedures for a period or a year.</span></span> <span data-ttu-id="939b0-106">Procesy zamknięcia przygotowują system do nowego okresu.</span><span class="sxs-lookup"><span data-stu-id="939b0-106">Closing processes prepare the system for a new period.</span></span> <span data-ttu-id="939b0-107">Aby przygotować system do nowego roku, należy uruchomić proces zamknięcia roku.</span><span class="sxs-lookup"><span data-stu-id="939b0-107">To prepare the system for a new year, you must run the year end close process.</span></span> <span data-ttu-id="939b0-108">Każda organizacja ma różne procesy i czynności wykonywane na koniec okresu.</span><span class="sxs-lookup"><span data-stu-id="939b0-108">Each organization has different processes and steps that it performs for the end of a period.</span></span> <span data-ttu-id="939b0-109">Oto kilka kroków opcjonalnych na koniec okresu:</span><span class="sxs-lookup"><span data-stu-id="939b0-109">Here are some optional steps for period ends:</span></span>

-   <span data-ttu-id="939b0-110">Ukończenie wszystkie zadań dla wszystkich innych modułów, takich jak Rozrachunki z odbiorcami, Rozrachunki z dostawcami i Zapasy.</span><span class="sxs-lookup"><span data-stu-id="939b0-110">Complete all the tasks for all other modules, such as Accounts receivable, Accounts payable, and Inventory.</span></span>
-   <span data-ttu-id="939b0-111">Sprawdzenie, czy wszystkie arkusze są zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="939b0-111">Verify that all journals are posted.</span></span>
-   <span data-ttu-id="939b0-112">Wykonanie przeszacowania w walucie obcej w celu wygenerowania wszelkiej niezrealizowanej dodatniej lub ujemnej różnicy kursowej.</span><span class="sxs-lookup"><span data-stu-id="939b0-112">Run foreign currency revaluation to generate any unrealized gain or loss amounts.</span></span>
-   <span data-ttu-id="939b0-113">Rozliczenie transakcji dla każdego konta księgowego.</span><span class="sxs-lookup"><span data-stu-id="939b0-113">Settle transactions for each ledger account.</span></span>
-   <span data-ttu-id="939b0-114">Przetworzenie wszelkich wymaganych alokacji.</span><span class="sxs-lookup"><span data-stu-id="939b0-114">Process any required allocations.</span></span>
-   <span data-ttu-id="939b0-115">Ręczne zaksięgowanie korekt na koniec roku.</span><span class="sxs-lookup"><span data-stu-id="939b0-115">Manually post period-end adjustments.</span></span>
-   <span data-ttu-id="939b0-116">Zapis transakcji do arkusza i sprawdzenie raportu **Arkusz księgi**.</span><span class="sxs-lookup"><span data-stu-id="939b0-116">Journalize transactions, and review the **Ledger journal** report.</span></span>
-   <span data-ttu-id="939b0-117">Wykonywanie konsolidacji przy użyciu konsolidowanej firmy lub raportów finansowych.</span><span class="sxs-lookup"><span data-stu-id="939b0-117">Perform a consolidation by using a consolidation company or Financial reporting.</span></span>
-   <span data-ttu-id="939b0-118">Generowanie sprawozdań finansowych na koniec okresu przy użyciu raportów finansowych.</span><span class="sxs-lookup"><span data-stu-id="939b0-118">Generate period-end financial statements by using Financial reporting.</span></span>
-   <span data-ttu-id="939b0-119">Ustawianie stanu **Zablokowany** dla okresów księgowych, by dalsze księgowania nie występowały.</span><span class="sxs-lookup"><span data-stu-id="939b0-119">Set ledger periods to **On hold**, so that no further posting occurs.</span></span> <span data-ttu-id="939b0-120">Można również ograniczyć okres do określonej grupy użytkowników, gdy występują czynności związane z końcem okresu. Pozwala to zachować większą kontrolę.</span><span class="sxs-lookup"><span data-stu-id="939b0-120">You can also restrict a period to a specific user group while period-end activities are occurring, for better control.</span></span> <span data-ttu-id="939b0-121">Dobrze jest ustawić dla okresów stan **Trwale zamknięty**, ponieważ nie można ponownie otworzyć okresu, który został zamknięty.</span><span class="sxs-lookup"><span data-stu-id="939b0-121">It's not a good idea to set periods to **Permanently closed**, because you can't reopen a period that has been closed.</span></span>

<span data-ttu-id="939b0-122">W obszarze roboczym Zamknięcie okresu obrachunkowego można porządkować i śledzić zadania wymagane do różnych procesów zamknięcia okresu.</span><span class="sxs-lookup"><span data-stu-id="939b0-122">The Financial period close workspace can be used to organize and track the tasks required for various period end processes.</span></span> 


<span data-ttu-id="939b0-123">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="939b0-123">For more information, see the following topics for more information:</span></span>
- [<span data-ttu-id="939b0-124">Obszar roboczy Zamknięcie okresu obrachunkowego</span><span class="sxs-lookup"><span data-stu-id="939b0-124">Financial period close workspace</span></span>](financial-period-close-workspace.md) 
- [<span data-ttu-id="939b0-125">Zamknięcie na koniec roku</span><span class="sxs-lookup"><span data-stu-id="939b0-125">Year-end close</span></span>](Year-end-close.md)  
- [<span data-ttu-id="939b0-126">Zbiorowe zamykanie okresów obrachunkowych</span><span class="sxs-lookup"><span data-stu-id="939b0-126">Mass financial period close</span></span>](tasks/mass-financial-period-close.md)




