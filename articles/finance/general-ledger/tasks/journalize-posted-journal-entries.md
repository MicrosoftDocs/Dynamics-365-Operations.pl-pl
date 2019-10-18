---
title: Zapisywanie zaksięgowanych zapisów arkusza w arkuszu
description: W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu.
author: aprilolson
manager: AnnBe
ms.date: 08/09/2019
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
ms.openlocfilehash: e20229ca910aa0d7d820434c22edf5a27030bba5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175583"
---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="3931a-103">Zapisywanie zaksięgowanych zapisów arkusza w arkuszu</span><span class="sxs-lookup"><span data-stu-id="3931a-103">Journalize posted journal entries</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3931a-104">W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="3931a-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="3931a-105">Procedura wykorzystuje dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3931a-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="3931a-106">Przejdź do **Okienko nawigacji**, następnie **Moduły > Księga główna > Ustawienia księgi > Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="3931a-106">In the **Navigation pane**, go to **Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="3931a-107">Pole **Rozszerzony arkusz księgi** można ustawić na wartość Tak lub Nie.</span><span class="sxs-lookup"><span data-stu-id="3931a-107">The **Extended ledger journal** field can be set to Yes or No.</span></span> <span data-ttu-id="3931a-108">Jeśli zaznaczysz wartość Tak, dane wyjściowe raportu będą inne.</span><span class="sxs-lookup"><span data-stu-id="3931a-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="3931a-109">Określ, czy okres może zostać zamknięty, jeśli nie został wykonany proces zapisywania w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="3931a-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span> <span data-ttu-id="3931a-110">Jeśli ta opcja jest ustawiona na wartość Tak, nie można zamknąć okresu do czasu zakończenia procesu zapisywania w arkuszu dla tego okresu.</span><span class="sxs-lookup"><span data-stu-id="3931a-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="3931a-111">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3931a-111">Close the page.</span></span>
5. <span data-ttu-id="3931a-112">W **Okienku nawigacji** otwórz **Moduły > Księga główna > Zadania okresowe > Generowanie arkuszy**.</span><span class="sxs-lookup"><span data-stu-id="3931a-112">In the **Navigation pane**, go to **Modules > General ledger > Periodic tasks > Journalizing**.</span></span>
6. <span data-ttu-id="3931a-113">Kliknij przycisk **Filtr**.</span><span class="sxs-lookup"><span data-stu-id="3931a-113">Click **Filter**.</span></span>
7. <span data-ttu-id="3931a-114">Zaznacz wiersz z kryteriami filtrowania, które chcesz zdefiniować.</span><span class="sxs-lookup"><span data-stu-id="3931a-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="3931a-115">W polu **Kryteria** wprowadź lub wybierz kryteria filtrowania.</span><span class="sxs-lookup"><span data-stu-id="3931a-115">In the **Criteria** field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="3931a-116">Kliknij przycisk **OK**, aby zamknąć stronę filtru.</span><span class="sxs-lookup"><span data-stu-id="3931a-116">Click **OK** to close the filter page.</span></span>
10. <span data-ttu-id="3931a-117">Kliknij przycisk **OK**, aby rozpocząć proces generowania arkuszy.</span><span class="sxs-lookup"><span data-stu-id="3931a-117">Click **OK** to start the journalizing process.</span></span> <span data-ttu-id="3931a-118">Po zakończeniu procesu zostanie wygenerowany raport.</span><span class="sxs-lookup"><span data-stu-id="3931a-118">A report will be generated after the process is complete.</span></span>  

