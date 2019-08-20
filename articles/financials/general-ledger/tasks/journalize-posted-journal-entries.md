---
title: Zapisywanie zaksięgowanych zapisów arkusza w arkuszu
description: W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cbf7ee8063487303cd4c8d2b76a8b44bacc86193
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846398"
---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="499de-103">Zapisywanie zaksięgowanych zapisów arkusza w arkuszu</span><span class="sxs-lookup"><span data-stu-id="499de-103">Journalize posted journal entries</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="499de-104">W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="499de-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="499de-105">Procedura wykorzystuje dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="499de-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="499de-106">Sprawdź poprawność ustawień zapisywania w arkuszu w obszarze Księga główna > Ustawienia księgi > Parametry księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="499de-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="499de-107">Pole Rozszerzony arkusz księgi można ustawić na wartość Tak lub Nie.</span><span class="sxs-lookup"><span data-stu-id="499de-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="499de-108">Jeśli zaznaczysz wartość Tak, dane wyjściowe raportu będą inne.</span><span class="sxs-lookup"><span data-stu-id="499de-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="499de-109">Określ, czy okres może zostać zamknięty, jeśli nie został wykonany proces zapisywania w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="499de-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="499de-110">Jeśli ta opcja jest ustawiona na wartość Tak, nie można zamknąć okresu do czasu zakończenia procesu zapisywania w arkuszu dla tego okresu.</span><span class="sxs-lookup"><span data-stu-id="499de-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="499de-111">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="499de-111">Close the page.</span></span>
5. <span data-ttu-id="499de-112">Wybierz kolejno opcje Księga główna > Zadania okresowe > Generowanie arkuszy.</span><span class="sxs-lookup"><span data-stu-id="499de-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="499de-113">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="499de-113">Click Filter.</span></span>
7. <span data-ttu-id="499de-114">Zaznacz wiersz z kryteriami filtrowania, które chcesz zdefiniować.</span><span class="sxs-lookup"><span data-stu-id="499de-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="499de-115">W polu Kryteria wprowadź lub wybierz kryteria filtrowania.</span><span class="sxs-lookup"><span data-stu-id="499de-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="499de-116">Kliknij przycisk OK, aby zamknąć stronę filtru.</span><span class="sxs-lookup"><span data-stu-id="499de-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="499de-117">Kliknij przycisk OK, aby rozpocząć proces zapisywania w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="499de-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="499de-118">Po zakończeniu procesu zostanie wygenerowany raport.</span><span class="sxs-lookup"><span data-stu-id="499de-118">A report will be generated after the process is complete.</span></span>  

