---
title: Ustawianie okresów rozliczania podatku
description: Okresy rozliczania podatków zawierają informacje o interwałach okresu, za które należy zgłosić i zapłacić podatki.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8304d9e8997a5d31740ee1203aa4bf0603014056
ms.sourcegitcommit: d0fa8d0140fa81029527edb317623c1a7737c593
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2019
ms.locfileid: "1862995"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="54ff9-103">Ustawianie okresów rozliczania podatku</span><span class="sxs-lookup"><span data-stu-id="54ff9-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="54ff9-104">Okresy rozliczania podatków zawierają informacje o interwałach okresu, za które należy zgłosić i zapłacić podatki.</span><span class="sxs-lookup"><span data-stu-id="54ff9-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="54ff9-105">Proces rozliczania można wykonać dla okresu rozliczeniowego za określony zakres dat.</span><span class="sxs-lookup"><span data-stu-id="54ff9-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="54ff9-106">Rozliczenie obejmie wszystkie kody podatków skojarzone z okresem rozliczeniowym.</span><span class="sxs-lookup"><span data-stu-id="54ff9-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="54ff9-107">W zależności od ustawień odnośnego urzędu skarbowego zobowiązania podatkowe zostaną zaksięgowana na koncie dostawcy lub Księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="54ff9-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="54ff9-108">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="54ff9-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="54ff9-109">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Okresy rozliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="54ff9-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="54ff9-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="54ff9-110">Click New.</span></span>
3. <span data-ttu-id="54ff9-111">W polu Okres rozliczeniowy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="54ff9-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="54ff9-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="54ff9-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="54ff9-113">W polu Organ wybierz urząd podatkowy otrzymujący deklaracje podatkowe i płatności za ten okres rozliczeniowy.</span><span class="sxs-lookup"><span data-stu-id="54ff9-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="54ff9-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="54ff9-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="54ff9-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="54ff9-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="54ff9-116">W polu Warunki płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="54ff9-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="54ff9-117">Odpowiedni urząd skarbowy można skonfigurować jako dostawcę, a wtedy funkcja rozliczania podatku utworzy otwartą fakturę od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="54ff9-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="54ff9-118">Warunki płatności decydują o terminie płatności otwartej faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="54ff9-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="54ff9-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="54ff9-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="54ff9-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="54ff9-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="54ff9-121">Wybierz typ interwałów okresu rozliczeniowego.</span><span class="sxs-lookup"><span data-stu-id="54ff9-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="54ff9-122">Wprowadź liczbę jednostek interwału okresu w okresie.</span><span class="sxs-lookup"><span data-stu-id="54ff9-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="54ff9-123">Na przykład kwartał ma 3 miesiące.</span><span class="sxs-lookup"><span data-stu-id="54ff9-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="54ff9-124">Zaznacz lub wyczyść pole wyboru Użyj przetwarzania wsadowego w celu rozliczenia podatku.</span><span class="sxs-lookup"><span data-stu-id="54ff9-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="54ff9-125">Proces rozliczania dla okresu rozliczeniowego może być wykonywany w trybie wsadowym w tle.</span><span class="sxs-lookup"><span data-stu-id="54ff9-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="54ff9-126">Jest to zalecane dla dużej liczby transakcji podatkowych w interwale okresu.</span><span class="sxs-lookup"><span data-stu-id="54ff9-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="54ff9-127">Obecnie nie jest to obsługiwane w Austrii, Belgii, Hiszpanii, Włoszech, Japonii i Holandii.</span><span class="sxs-lookup"><span data-stu-id="54ff9-127">Currently this is not supported in Austria, Belgium, Spain, Italy, Japan, and the Netherlands.</span></span>
14. <span data-ttu-id="54ff9-128">Zaznacz lub wyczyść pole wyboru Zapobiegaj generowaniu transakcji podatków przeciwstawnych.</span><span class="sxs-lookup"><span data-stu-id="54ff9-128">Select or clear the Prevent generating offset tax transactions check box.</span></span>
    * <span data-ttu-id="54ff9-129">Domyślnie system generuje transakcje podatków przeciwstawnych w trakcie rozliczania, co może spowalniać działanie, jeżeli w okresie występuje duża liczba transakcji podatkowych.</span><span class="sxs-lookup"><span data-stu-id="54ff9-129">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="54ff9-130">Zaznaczenie tego pola wyboru uniemożliwi generowanie transakcji podatków przeciwstawnych.</span><span class="sxs-lookup"><span data-stu-id="54ff9-130">Select this check box to prevent generating offset tax transactions.</span></span>
15. <span data-ttu-id="54ff9-131">Rozwiń kartę Interwały okresu.</span><span class="sxs-lookup"><span data-stu-id="54ff9-131">Expand the Period intervals tab.</span></span>
16. <span data-ttu-id="54ff9-132">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="54ff9-132">Click Add.</span></span>
17. <span data-ttu-id="54ff9-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="54ff9-133">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="54ff9-134">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="54ff9-134">In the From date field, enter a date.</span></span>
19. <span data-ttu-id="54ff9-135">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="54ff9-135">In the To date field, enter a date.</span></span>
20. <span data-ttu-id="54ff9-136">Kliknij przycisk Nowy interwał okresu.</span><span class="sxs-lookup"><span data-stu-id="54ff9-136">Click New period interval.</span></span>
    * <span data-ttu-id="54ff9-137">Po wprowadzeniu pierwszego interwału okresu nowe okresy mogą być tworzone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="54ff9-137">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="54ff9-138">Później można wrócić i dodawać nowe interwały okresu zgodnie z wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="54ff9-138">You can come back and add new period intervals as required.</span></span>  
21. <span data-ttu-id="54ff9-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="54ff9-139">Close the page.</span></span>

