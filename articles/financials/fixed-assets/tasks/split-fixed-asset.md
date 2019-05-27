---
title: Rozbicie środka trwałego
description: W tym przewodniku po zadaniach jedna księga środków trwałych zostanie podzielona procentowo w celu utworzenia nowej księgi środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6be9de64265a4d7b5c91af3ee8acfce80c78e0f1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566899"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="ee484-103">Rozbicie środka trwałego</span><span class="sxs-lookup"><span data-stu-id="ee484-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee484-104">W tym przewodniku po zadaniach jedna księga środków trwałych zostanie podzielona procentowo w celu utworzenia nowej księgi środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="ee484-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="ee484-105">Przewodnik wykorzystuje rolę Księgowy i dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ee484-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="ee484-106">Utwórz nowy środek trwały</span><span class="sxs-lookup"><span data-stu-id="ee484-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="ee484-107">Przejdź do Środki trwałe > Środki trwałe > Środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="ee484-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="ee484-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ee484-108">Click New.</span></span>
3. <span data-ttu-id="ee484-109">W polu Grupa środków trwałych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ee484-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="ee484-110">Zanotuj numer środka trwałego, ponieważ trzeba go będzie później wykorzystać w procesie podziału.</span><span class="sxs-lookup"><span data-stu-id="ee484-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="ee484-111">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ee484-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="ee484-112">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="ee484-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="ee484-113">Rozbicie środka trwałego</span><span class="sxs-lookup"><span data-stu-id="ee484-113">Split a fixed asset</span></span>
1. <span data-ttu-id="ee484-114">Na liście odszukaj i zaznacz środek trwały, który ma zostać podzielony.</span><span class="sxs-lookup"><span data-stu-id="ee484-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="ee484-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ee484-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="ee484-116">Kliknij opcję Księgi.</span><span class="sxs-lookup"><span data-stu-id="ee484-116">Click Books.</span></span>
    * <span data-ttu-id="ee484-117">Wybierz księgę, która zostanie użyta w celu wydzielenia nowego składnika aktywów.</span><span class="sxs-lookup"><span data-stu-id="ee484-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="ee484-118">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="ee484-118">Click Functions.</span></span>
5. <span data-ttu-id="ee484-119">Kliknij opcję Rozbicie środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="ee484-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="ee484-120">W polu Do środka trwałego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ee484-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="ee484-121">W polu Do księgi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ee484-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="ee484-122">W polu Data transakcji wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="ee484-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="ee484-123">W polu Procent wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ee484-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="ee484-124">Wprowadź lub wybierz wartość w polu Nazwa arkusza.</span><span class="sxs-lookup"><span data-stu-id="ee484-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="ee484-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ee484-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="ee484-126">Księgowanie transakcji arkusza</span><span class="sxs-lookup"><span data-stu-id="ee484-126">Post the journal transaction</span></span>
1. <span data-ttu-id="ee484-127">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="ee484-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="ee484-128">Z listy wybierz arkusz utworzony za pomocą procesu podziału.</span><span class="sxs-lookup"><span data-stu-id="ee484-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="ee484-129">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="ee484-129">Click Lines.</span></span>
    * <span data-ttu-id="ee484-130">Sprawdź utworzone wiersze arkusza.</span><span class="sxs-lookup"><span data-stu-id="ee484-130">Verify the journal lines created.</span></span>  <span data-ttu-id="ee484-131">Dla oryginalnego składnika aktywów jest tworzona transakcja korekty wartości początkowej, aby zmniejszyć wartość o procent określony w procesie podziału.</span><span class="sxs-lookup"><span data-stu-id="ee484-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="ee484-132">Dla nowego składnika aktywów jest tworzona transakcja nabycia na tę samą kwotę.</span><span class="sxs-lookup"><span data-stu-id="ee484-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="ee484-133">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="ee484-133">Click Post.</span></span>

