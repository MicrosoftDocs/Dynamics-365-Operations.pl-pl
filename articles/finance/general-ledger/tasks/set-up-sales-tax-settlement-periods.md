---
title: Konfigurowanie okresów rozliczania podatku
description: W tym temacie wyjaśniono sposób konfigurowania okresów rozliczenia podatku w Dynamics 365 Finance.
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
ms.openlocfilehash: 2cff84f8f6c42fd064258b8ca53e24acc8059977
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175578"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="f41fb-103">Konfigurowanie okresów rozliczania podatku</span><span class="sxs-lookup"><span data-stu-id="f41fb-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f41fb-104">W tym temacie wyjaśniono sposób konfigurowania okresów rozliczenia podatku.</span><span class="sxs-lookup"><span data-stu-id="f41fb-104">This topic explains how to set up sales tax settlement periods.</span></span> <span data-ttu-id="f41fb-105">Okresy rozliczania podatków zawierają informacje o interwałach okresu, za które należy zgłosić i zapłacić podatki.</span><span class="sxs-lookup"><span data-stu-id="f41fb-105">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="f41fb-106">Proces rozliczania można wykonać dla okresu rozliczeniowego za określony zakres dat.</span><span class="sxs-lookup"><span data-stu-id="f41fb-106">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="f41fb-107">Rozliczenie obejmie wszystkie kody podatków skojarzone z okresem rozliczeniowym.</span><span class="sxs-lookup"><span data-stu-id="f41fb-107">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="f41fb-108">W zależności od ustawień odnośnego urzędu skarbowego zobowiązania podatkowe zostaną zaksięgowana na koncie dostawcy lub Księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="f41fb-108">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>

<span data-ttu-id="f41fb-109">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="f41fb-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f41fb-110">Otwórz w okienku nawigacji otwórz **Moduły > Podatek > Podatki pośrednie > Podatek > Okresy rozliczania podatku**.</span><span class="sxs-lookup"><span data-stu-id="f41fb-110">In the navigation pane, go to **Modules > Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.</span></span>
2. <span data-ttu-id="f41fb-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f41fb-111">Select **New**.</span></span>
3. <span data-ttu-id="f41fb-112">W polu **Okres rozliczeniowy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f41fb-112">In the **Settlement period** field, type a value.</span></span>
4. <span data-ttu-id="f41fb-113">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f41fb-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="f41fb-114">W polu **Organ** wybierz urząd podatkowy otrzymujący deklaracje podatkowe i płatności za ten okres rozliczeniowy.</span><span class="sxs-lookup"><span data-stu-id="f41fb-114">In the **Authority** field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="f41fb-115">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f41fb-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="f41fb-116">W polu **Warunki płatności** wybierz odpowiedni rekord z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="f41fb-116">In the **Terms of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="f41fb-117">Odpowiedni urząd skarbowy można skonfigurować jako dostawcę, a wtedy funkcja rozliczania podatku utworzy otwartą fakturę od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="f41fb-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="f41fb-118">Warunki płatności decydują o terminie płatności otwartej faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="f41fb-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
8. <span data-ttu-id="f41fb-119">Wybierz typ interwałów okresu rozliczeniowego.</span><span class="sxs-lookup"><span data-stu-id="f41fb-119">Select a type for the settlement period intervals.</span></span>
9. <span data-ttu-id="f41fb-120">Wprowadź liczbę jednostek interwału okresu w okresie.</span><span class="sxs-lookup"><span data-stu-id="f41fb-120">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="f41fb-121">Na przykład kwartał ma 3 miesiące.</span><span class="sxs-lookup"><span data-stu-id="f41fb-121">For example, a quarter has 3 months.</span></span>
10. <span data-ttu-id="f41fb-122">Zaznacz lub wyczyść pole wyboru **Użyj przetwarzania wsadowego w celu rozliczenia podatku**.</span><span class="sxs-lookup"><span data-stu-id="f41fb-122">Select or clear the **Use batch processing for sales tax settlement** check box.</span></span> <span data-ttu-id="f41fb-123">Proces rozliczania dla okresu rozliczeniowego może być wykonywany w trybie wsadowym w tle.</span><span class="sxs-lookup"><span data-stu-id="f41fb-123">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="f41fb-124">Jest to zalecane dla dużej liczby transakcji podatkowych w interwale okresu.</span><span class="sxs-lookup"><span data-stu-id="f41fb-124">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="f41fb-125">Obecnie nie jest to obsługiwane w Austrii, Belgii, Hiszpanii, Włoszech, Japonii i Holandii.</span><span class="sxs-lookup"><span data-stu-id="f41fb-125">Currently this is not supported in Austria, Belgium, Spain, Italy, Japan, and the Netherlands.</span></span>
11. <span data-ttu-id="f41fb-126">Zaznacz lub wyczyść pole wyboru **Zapobiegaj generowaniu transakcji podatków przeciwstawnych**.</span><span class="sxs-lookup"><span data-stu-id="f41fb-126">Select or clear the **Prevent generating offset tax transactions** check box.</span></span> <span data-ttu-id="f41fb-127">Domyślnie system generuje transakcje podatków przeciwstawnych w trakcie rozliczania, co może spowalniać działanie, jeżeli w okresie występuje duża liczba transakcji podatkowych.</span><span class="sxs-lookup"><span data-stu-id="f41fb-127">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="f41fb-128">Zaznaczenie tego pola wyboru uniemożliwi generowanie transakcji podatków przeciwstawnych.</span><span class="sxs-lookup"><span data-stu-id="f41fb-128">Select this check box to prevent generating offset tax transactions.</span></span>
12. <span data-ttu-id="f41fb-129">Rozwiń kartę **Interwały okresu**.</span><span class="sxs-lookup"><span data-stu-id="f41fb-129">Expand the **Period intervals** tab.</span></span>
13. <span data-ttu-id="f41fb-130">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="f41fb-130">Select **Add**.</span></span>
14. <span data-ttu-id="f41fb-131">W polu **Od dnia** w nowym wierszu wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="f41fb-131">In the **From date** field in the new row, enter a date.</span></span>
15. <span data-ttu-id="f41fb-132">Wprowadź datę w polu **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="f41fb-132">In the **To date** field, enter a date.</span></span>
16. <span data-ttu-id="f41fb-133">Wybierz **Nowy interwał okresu**.</span><span class="sxs-lookup"><span data-stu-id="f41fb-133">Select **New period interval**.</span></span> <span data-ttu-id="f41fb-134">Po wprowadzeniu pierwszego interwału okresu nowe okresy mogą być tworzone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="f41fb-134">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="f41fb-135">Później można wrócić i dodawać nowe interwały okresu zgodnie z wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="f41fb-135">You can come back and add new period intervals as required.</span></span>  
17. <span data-ttu-id="f41fb-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f41fb-136">Close the page.</span></span>

