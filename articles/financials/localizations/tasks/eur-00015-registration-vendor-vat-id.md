---
title: EUR-00015 Rejestrowanie identyfikatora VAT dostawcy
description: W tej procedurze pokazano sposób dodawania identyfikatorów rejestracji VAT i numeru zwolnienia podatkowego do konta dostawcy.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68475c96e7c85cc5a4c540441a4b1f3752ecf0bd
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852691"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a><span data-ttu-id="07613-103">EUR-00015 Rejestrowanie identyfikatora VAT dostawcy</span><span class="sxs-lookup"><span data-stu-id="07613-103">EUR-00015 Registration of vendor VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="07613-104">W tej procedurze pokazano sposób dodawania identyfikatorów rejestracji VAT i numeru zwolnienia podatkowego do konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="07613-104">This procedure shows how to add VAT registration IDs and a tax except number to a vendor account.</span></span> <span data-ttu-id="07613-105">Ten proces jest podobny dla firm i odbiorców.</span><span class="sxs-lookup"><span data-stu-id="07613-105">This process is similar for legal entities and customers.</span></span> 

<span data-ttu-id="07613-106">Przed wykonaniem tej procedury należy skonfigurować identyfikatory VAT.</span><span class="sxs-lookup"><span data-stu-id="07613-106">Before you can complete this procedure you must set up VAT IDs.</span></span> <span data-ttu-id="07613-107">Ta procedura dotyczy wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="07613-107">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="07613-108">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="07613-108">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="07613-109">Procedura jest przeznaczona dla administratora zarządzającego danymi oraz kierowników odpowiedzialnych za rozliczenia z dostawcami i odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="07613-109">This procedure is intended for a data management administrator, accounts payable manager, or accounts receivable manager.</span></span> <span data-ttu-id="07613-110">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="07613-110">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="07613-111">Wybierz kolejno opcje Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawy.</span><span class="sxs-lookup"><span data-stu-id="07613-111">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="07613-112">Na liście znajdź i zaznacz dostawcę DE-01001.</span><span class="sxs-lookup"><span data-stu-id="07613-112">In the list find and select vendor DE-01001</span></span>
3. <span data-ttu-id="07613-113">Kliknij opcję Identyfikatory rejestracji.</span><span class="sxs-lookup"><span data-stu-id="07613-113">Click Registration IDs.</span></span>
4. <span data-ttu-id="07613-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="07613-114">Click Add.</span></span>
5. <span data-ttu-id="07613-115">Zaznacz opcję Identyfikator VAT.</span><span class="sxs-lookup"><span data-stu-id="07613-115">Select VAT ID.</span></span>
6. <span data-ttu-id="07613-116">W polu Numer rejestracji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="07613-116">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="07613-117">Określ identyfikator VAT w Niemczech dla wybranego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="07613-117">Specify a VAT ID in Germany for the selected vendor.</span></span> <span data-ttu-id="07613-118">Identyfikator musi odpowiadać podanemu formatowi typu rejestracji.</span><span class="sxs-lookup"><span data-stu-id="07613-118">The ID must match the specified format of the registration type.</span></span>  
7. <span data-ttu-id="07613-119">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="07613-119">Click the General tab.</span></span>
8. <span data-ttu-id="07613-120">W polu Data wprowadzenia wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="07613-120">In the Effective field, enter a date.</span></span>
9. <span data-ttu-id="07613-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="07613-121">Click Save.</span></span>
10. <span data-ttu-id="07613-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="07613-122">Click New.</span></span>
11. <span data-ttu-id="07613-123">W polu Nazwa lub opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="07613-123">In the Name or description field, type a value.</span></span>
    * <span data-ttu-id="07613-124">Na przykład wpisz ITA.</span><span class="sxs-lookup"><span data-stu-id="07613-124">For example, enter ITA.</span></span>  
12. <span data-ttu-id="07613-125">W polu kraj/region wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="07613-125">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="07613-126">Na przykład zaznacz ITA.</span><span class="sxs-lookup"><span data-stu-id="07613-126">For example, select ITA.</span></span>  
13. <span data-ttu-id="07613-127">W polu Podstawowy dla kraju wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="07613-127">Select Yes in the Primary for country field.</span></span>
14. <span data-ttu-id="07613-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="07613-128">Click Save.</span></span>
15. <span data-ttu-id="07613-129">Kliknij kartę Przegląd.</span><span class="sxs-lookup"><span data-stu-id="07613-129">Click the Overview tab.</span></span>
16. <span data-ttu-id="07613-130">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="07613-130">Click Add.</span></span>
17. <span data-ttu-id="07613-131">W polu Typ rejestracji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="07613-131">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="07613-132">Na przykład zaznacz pozycję Identyfikator VAT.</span><span class="sxs-lookup"><span data-stu-id="07613-132">For example, select VAT ID.</span></span>  
18. <span data-ttu-id="07613-133">W polu Numer rejestracji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="07613-133">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="07613-134">Na przykład określ identyfikator VAT we Włoszech.</span><span class="sxs-lookup"><span data-stu-id="07613-134">For example, specify a VAT ID in Italy.</span></span>  <span data-ttu-id="07613-135">Identyfikator musi mieć taki sam format, jak typ rejestracji.</span><span class="sxs-lookup"><span data-stu-id="07613-135">The ID must have the same format as the registration type.</span></span>  
19. <span data-ttu-id="07613-136">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="07613-136">Click Save.</span></span>
20. <span data-ttu-id="07613-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="07613-137">Close the page.</span></span>
21. <span data-ttu-id="07613-138">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="07613-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="07613-139">Na przykład zaznacz DE-01001.</span><span class="sxs-lookup"><span data-stu-id="07613-139">For example, select DE-01001.</span></span>  
22. <span data-ttu-id="07613-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="07613-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="07613-141">Rozwiń sekcję Faktura i dostawa.</span><span class="sxs-lookup"><span data-stu-id="07613-141">Expand the Invoice and delivery section.</span></span>
24. <span data-ttu-id="07613-142">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="07613-142">Click Edit.</span></span>
25. <span data-ttu-id="07613-143">W polu Numer identyfikacji podatkowej wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="07613-143">In the Tax exempt number field, enter or select a value.</span></span>
26. <span data-ttu-id="07613-144">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="07613-144">Click Save.</span></span>

