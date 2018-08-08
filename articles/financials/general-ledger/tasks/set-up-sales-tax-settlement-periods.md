--- 
title: "Ustawianie okresów rozliczania podatku"
description: "Okresy rozliczania podatków zawierają informacje o interwałach okresu, za które należy zgłosić i zapłacić podatki."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: d30a3271114574d2776921fb31b360389a1b3466
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="25d73-103">Ustawianie okresów rozliczania podatku</span><span class="sxs-lookup"><span data-stu-id="25d73-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25d73-104">Okresy rozliczania podatków zawierają informacje o interwałach okresu, za które należy zgłosić i zapłacić podatki.</span><span class="sxs-lookup"><span data-stu-id="25d73-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="25d73-105">Proces rozliczania można wykonać dla okresu rozliczeniowego za określony zakres dat.</span><span class="sxs-lookup"><span data-stu-id="25d73-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="25d73-106">Rozliczenie obejmie wszystkie kody podatków skojarzone z okresem rozliczeniowym.</span><span class="sxs-lookup"><span data-stu-id="25d73-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="25d73-107">W zależności od ustawień odnośnego urzędu skarbowego zobowiązania podatkowe zostaną zaksięgowana na koncie dostawcy lub Księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="25d73-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="25d73-108">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="25d73-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="25d73-109">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Okresy rozliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="25d73-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="25d73-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="25d73-110">Click New.</span></span>
3. <span data-ttu-id="25d73-111">W polu Okres rozliczeniowy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="25d73-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="25d73-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="25d73-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="25d73-113">W polu Organ wybierz urząd podatkowy otrzymujący deklaracje podatkowe i płatności za ten okres rozliczeniowy.</span><span class="sxs-lookup"><span data-stu-id="25d73-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="25d73-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="25d73-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="25d73-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="25d73-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="25d73-116">W polu Warunki płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="25d73-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="25d73-117">Odpowiedni urząd skarbowy można skonfigurować jako dostawcę, a wtedy funkcja rozliczania podatku utworzy otwartą fakturę od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="25d73-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="25d73-118">Warunki płatności decydują o terminie płatności otwartej faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="25d73-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="25d73-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="25d73-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="25d73-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="25d73-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="25d73-121">Wybierz typ interwałów okresu rozliczeniowego.</span><span class="sxs-lookup"><span data-stu-id="25d73-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="25d73-122">Wprowadź liczbę jednostek interwału okresu w okresie.</span><span class="sxs-lookup"><span data-stu-id="25d73-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="25d73-123">Na przykład kwartał ma 3 miesiące.</span><span class="sxs-lookup"><span data-stu-id="25d73-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="25d73-124">Zaznacz lub wyczyść pole wyboru Użyj przetwarzania wsadowego w celu rozliczenia podatku.</span><span class="sxs-lookup"><span data-stu-id="25d73-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="25d73-125">Proces rozliczania dla okresu rozliczeniowego może być wykonywany w trybie wsadowym w tle.</span><span class="sxs-lookup"><span data-stu-id="25d73-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="25d73-126">Jest to zalecane dla dużej liczby transakcji podatkowych w interwale okresu.</span><span class="sxs-lookup"><span data-stu-id="25d73-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="25d73-127">Rozwiń kartę Interwały okresu.</span><span class="sxs-lookup"><span data-stu-id="25d73-127">Expand the Period intervals tab.</span></span>
15. <span data-ttu-id="25d73-128">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="25d73-128">Click Add.</span></span>
16. <span data-ttu-id="25d73-129">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="25d73-129">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="25d73-130">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="25d73-130">In the From date field, enter a date.</span></span>
18. <span data-ttu-id="25d73-131">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="25d73-131">In the To date field, enter a date.</span></span>
19. <span data-ttu-id="25d73-132">Kliknij przycisk Nowy interwał okresu.</span><span class="sxs-lookup"><span data-stu-id="25d73-132">Click New period interval.</span></span>
    * <span data-ttu-id="25d73-133">Po wprowadzeniu pierwszego interwału okresu nowe okresy mogą być tworzone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="25d73-133">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="25d73-134">Później można wrócić i dodawać nowe interwały okresu zgodnie z wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="25d73-134">You can come back and add new period intervals as required.</span></span>  
20. <span data-ttu-id="25d73-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="25d73-135">Close the page.</span></span>


