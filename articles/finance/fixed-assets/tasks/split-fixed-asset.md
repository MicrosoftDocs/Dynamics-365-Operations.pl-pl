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
ms.openlocfilehash: 40703622bc8c7a21451d31e7606596c5edbe90f7
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000300"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="86ca2-103">Rozbicie środka trwałego</span><span class="sxs-lookup"><span data-stu-id="86ca2-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="86ca2-104">W tym przewodniku po zadaniach jedna księga składników majatku zostanie podzielona procentowo w celu utworzenia nowej księgi składników majątku.</span><span class="sxs-lookup"><span data-stu-id="86ca2-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="86ca2-105">Przewodnik wykorzystuje rolę Księgowy i dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="86ca2-105">It uses the Accountant role and USMF demo data.</span></span>

## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="86ca2-106">Utwórz nowy środek trwały</span><span class="sxs-lookup"><span data-stu-id="86ca2-106">Create a new fixed asset</span></span>

1. <span data-ttu-id="86ca2-107">W okienku nawigacji przejdź do **Moduły \> Środki trwałe \> Środki trwałe \> Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-107">In the navigation pane, go to **Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="86ca2-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-108">Select **New**.</span></span>
3. <span data-ttu-id="86ca2-109">W polu **Grupa środków trwałych** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="86ca2-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="86ca2-110">Zanotuj numer środka trwałego, ponieważ trzeba go będzie później wykorzystać w procesie podziału.</span><span class="sxs-lookup"><span data-stu-id="86ca2-110">Note the fixed asset number to use in the split process later.</span></span>
4. <span data-ttu-id="86ca2-111">Wprowadź wartość w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-111">In the **Name** field, enter a value.</span></span>
5. <span data-ttu-id="86ca2-112">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="86ca2-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="86ca2-113">Rozbicie środka trwałego</span><span class="sxs-lookup"><span data-stu-id="86ca2-113">Split a fixed asset</span></span>

<span data-ttu-id="86ca2-114">Przed podziałem środka trwałego na amortyzację stan księgi środków trwałych powinien zostać zmieniony ręcznie z **Zamkniętego** na **Otwarte**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-114">Before a fully depreciated asset is split, the asset book status should be manually changed from **Closed** to **Open**.</span></span> <span data-ttu-id="86ca2-115">Ten krok jest wymagany, ponieważ stan księgi musi być **Otwarty** , jeśli konieczne jest księgowanie transakcji dla środka trwałego (np. sprzedaży za likwidację).</span><span class="sxs-lookup"><span data-stu-id="86ca2-115">This step is required because the book status has to be **Open** if you must post transactions for the asset (for example, for a disposal sale).</span></span> <span data-ttu-id="86ca2-116">Po zmianie stanu księgi środków trwałych należy wykonać poniższe kroki w celu podzielenia środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="86ca2-116">After the asset book status is changed, follow these steps to split the asset.</span></span>

1. <span data-ttu-id="86ca2-117">Na liście odszukaj i wybierz łącze środka trwałego, który ma zostać podzielony.</span><span class="sxs-lookup"><span data-stu-id="86ca2-117">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="86ca2-118">Wybierz **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-118">Select **Books**.</span></span> <span data-ttu-id="86ca2-119">Wybierz księgę, która zostanie użyta w celu wydzielenia nowego składnika aktywów.</span><span class="sxs-lookup"><span data-stu-id="86ca2-119">Select the book to split to the new asset.</span></span>
3. <span data-ttu-id="86ca2-120">Wybierz **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-120">Select **Functions**.</span></span>
4. <span data-ttu-id="86ca2-121">Wybierz **Rozbicie środka trwałego**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-121">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="86ca2-122">W polu **Do środka trwałego** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="86ca2-122">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="86ca2-123">W polu **Do księgi** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="86ca2-123">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="86ca2-124">W polu **Data transakcji** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="86ca2-124">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="86ca2-125">W polu **Procent** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="86ca2-125">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="86ca2-126">Wprowadź lub wybierz wartość w polu **Nazwa arkusza**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-126">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="86ca2-127">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-127">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="86ca2-128">Księgowanie transakcji arkusza</span><span class="sxs-lookup"><span data-stu-id="86ca2-128">Post the journal transaction</span></span>

1. <span data-ttu-id="86ca2-129">W okienku nawigacji przejdź do **Moduły \> Środki trwałe \> Wpisy w arkuszu \> Arkusz środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-129">In the navigation pane, go to **Modules \> Fixed assets \> Journal entries \> Fixed assets journal**.</span></span>
2. <span data-ttu-id="86ca2-130">Z listy wybierz arkusz utworzony za pomocą procesu podziału.</span><span class="sxs-lookup"><span data-stu-id="86ca2-130">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="86ca2-131">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-131">Select **Lines**.</span></span>

    - <span data-ttu-id="86ca2-132">Sprawdź utworzone wiersze arkusza.</span><span class="sxs-lookup"><span data-stu-id="86ca2-132">Verify the journal lines created.</span></span>
    - <span data-ttu-id="86ca2-133">Dla oryginalnego składnika aktywów jest tworzona transakcja korekty wartości początkowej, aby zmniejszyć wartość o procent określony w procesie podziału.</span><span class="sxs-lookup"><span data-stu-id="86ca2-133">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>
    - <span data-ttu-id="86ca2-134">Dla nowego składnika aktywów jest tworzona transakcja nabycia na tę samą kwotę.</span><span class="sxs-lookup"><span data-stu-id="86ca2-134">An Acquisition transaction is created for the new asset for the same amount.</span></span>

4. <span data-ttu-id="86ca2-135">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="86ca2-135">Select **Post**.</span></span>
