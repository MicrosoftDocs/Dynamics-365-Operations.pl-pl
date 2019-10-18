---
title: Rozbicie środka trwałego
description: W tym przewodniku po zadaniach jedna księga składników majatku zostanie podzielona procentowo w celu utworzenia nowej księgi składników majątku.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4e001a6fdf390c6211ba85aa327b60dcdf16d9e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179375"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="de372-103">Rozbicie środka trwałego</span><span class="sxs-lookup"><span data-stu-id="de372-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="de372-104">W tym przewodniku po zadaniach jedna księga składników majatku zostanie podzielona procentowo w celu utworzenia nowej księgi składników majątku.</span><span class="sxs-lookup"><span data-stu-id="de372-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="de372-105">Przewodnik wykorzystuje rolę Księgowy i dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="de372-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="de372-106">Umożliwia utworzenie nowego środka trwałego</span><span class="sxs-lookup"><span data-stu-id="de372-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="de372-107">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Środki trwałe > Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="de372-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="de372-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de372-108">Select **New**.</span></span>
3. <span data-ttu-id="de372-109">W polu **Grupa środków trwałych** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="de372-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="de372-110">Zanotuj numer środka trwałego, ponieważ trzeba go będzie później wykorzystać w procesie podziału.</span><span class="sxs-lookup"><span data-stu-id="de372-110">Note the fixed asset number to use in the split process later.</span></span>  
4. <span data-ttu-id="de372-111">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="de372-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="de372-112">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="de372-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="de372-113">Rozbicie środka trwałego</span><span class="sxs-lookup"><span data-stu-id="de372-113">Split a fixed asset</span></span>
1. <span data-ttu-id="de372-114">Na liście odszukaj i wybierz łącze środka trwałego, który ma zostać podzielony.</span><span class="sxs-lookup"><span data-stu-id="de372-114">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="de372-115">Wybierz **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="de372-115">Select **Books**.</span></span> <span data-ttu-id="de372-116">Wybierz księgę, która zostanie użyta w celu wydzielenia nowego składnika aktywów.</span><span class="sxs-lookup"><span data-stu-id="de372-116">Select the book to split to the new asset.</span></span>  
3. <span data-ttu-id="de372-117">Wybierz **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="de372-117">Select **Functions**.</span></span>
4. <span data-ttu-id="de372-118">Wybierz **Rozbicie środka trwałego**.</span><span class="sxs-lookup"><span data-stu-id="de372-118">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="de372-119">W polu **Do środka trwałego** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="de372-119">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="de372-120">W polu **Do księgi** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="de372-120">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="de372-121">W polu **Data transakcji** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="de372-121">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="de372-122">W polu **Procent** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="de372-122">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="de372-123">Wprowadź lub wybierz wartość w polu **Nazwa arkusza**.</span><span class="sxs-lookup"><span data-stu-id="de372-123">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="de372-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de372-124">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="de372-125">Księgowanie transakcji arkusza</span><span class="sxs-lookup"><span data-stu-id="de372-125">Post the journal transaction</span></span>
1. <span data-ttu-id="de372-126">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="de372-126">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="de372-127">Z listy wybierz arkusz utworzony za pomocą procesu podziału.</span><span class="sxs-lookup"><span data-stu-id="de372-127">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="de372-128">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="de372-128">Select **Lines**.</span></span>

    - <span data-ttu-id="de372-129">Sprawdź utworzone wiersze arkusza.</span><span class="sxs-lookup"><span data-stu-id="de372-129">Verify the journal lines created.</span></span>  
    - <span data-ttu-id="de372-130">Dla oryginalnego składnika aktywów jest tworzona transakcja korekty wartości początkowej, aby zmniejszyć wartość o procent określony w procesie podziału.</span><span class="sxs-lookup"><span data-stu-id="de372-130">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  
    - <span data-ttu-id="de372-131">Dla nowego składnika aktywów jest tworzona transakcja nabycia na tę samą kwotę.</span><span class="sxs-lookup"><span data-stu-id="de372-131">An Acquisition transaction is created for the new asset for the same amount.</span></span>  

4. <span data-ttu-id="de372-132">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="de372-132">Select **Post**.</span></span>

