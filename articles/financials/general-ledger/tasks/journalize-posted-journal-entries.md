--- 
title: "Zapisywanie zaksięgowanych zapisów arkusza w arkuszu"
description: "W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 490e9a4beda43f6e32b87792b11153c3e8e322d6
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="d4fd3-103">Zapisywanie zaksięgowanych zapisów arkusza w arkuszu</span><span class="sxs-lookup"><span data-stu-id="d4fd3-103">Journalize posted journal entries</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4fd3-104">W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="d4fd3-105">Procedura wykorzystuje dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="d4fd3-106">Sprawdź poprawność ustawień zapisywania w arkuszu w obszarze Księga główna > Ustawienia księgi > Parametry księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="d4fd3-107">Pole Rozszerzony arkusz księgi można ustawić na wartość Tak lub Nie.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="d4fd3-108">Jeśli zaznaczysz wartość Tak, dane wyjściowe raportu będą inne.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="d4fd3-109">Określ, czy okres może zostać zamknięty, jeśli nie został wykonany proces zapisywania w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="d4fd3-110">Jeśli ta opcja jest ustawiona na wartość Tak, nie można zamknąć okresu do czasu zakończenia procesu zapisywania w arkuszu dla tego okresu.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="d4fd3-111">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-111">Close the page.</span></span>
5. <span data-ttu-id="d4fd3-112">Wybierz kolejno opcje Księga główna > Zadania okresowe > Generowanie arkuszy.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="d4fd3-113">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-113">Click Filter.</span></span>
7. <span data-ttu-id="d4fd3-114">Zaznacz wiersz z kryteriami filtrowania, które chcesz zdefiniować.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="d4fd3-115">W polu Kryteria wprowadź lub wybierz kryteria filtrowania.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="d4fd3-116">Kliknij przycisk OK, aby zamknąć stronę filtru.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="d4fd3-117">Kliknij przycisk OK, aby rozpocząć proces zapisywania w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="d4fd3-118">Po zakończeniu procesu zostanie wygenerowany raport.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-118">A report will be generated after the process is complete.</span></span>  


