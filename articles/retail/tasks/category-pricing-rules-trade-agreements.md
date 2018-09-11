--- 
title: "Reguły kategorii cen do tworzenia umów handlowych"
description: "Ta procedura przedstawia sposób tworzenia umów handlowych na ceny sprzedaży przy użyciu reguły cen dla kategorii."
author: scott-tucker
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPricingDiscountCategoryPriceRule, RetailCategoryPriceRule, EcoResCategorySingleLookup, RetailCategoryPriceWizard, PriceDiscAdm, PriceDiscAdmTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 454f74627bd4811fa657b0c6b06003a8fdbdb599
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="category-pricing-rules-to-create-trade-agreements"></a><span data-ttu-id="19ebe-103">Reguły kategorii cen do tworzenia umów handlowych</span><span class="sxs-lookup"><span data-stu-id="19ebe-103">Category pricing rules to create trade agreements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="19ebe-104">Ta procedura przedstawia sposób tworzenia umów handlowych na ceny sprzedaży przy użyciu reguły cen dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="19ebe-104">This procedure demonstrates how to create sales price trade agreements using a category pricing rule.</span></span> <span data-ttu-id="19ebe-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="19ebe-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="19ebe-106">To zadanie jest przeznaczone dla roli Kierownik ds. merchandisingu sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19ebe-106">This task is intended for the Retail merchandising manager role.</span></span>

1. <span data-ttu-id="19ebe-107">Kliknij opcję Zarządzanie cenami i rabatami.</span><span class="sxs-lookup"><span data-stu-id="19ebe-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="19ebe-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="19ebe-108">Click New.</span></span>
3. <span data-ttu-id="19ebe-109">Kliknij opcję Reguła cen dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="19ebe-109">Click Category price rule.</span></span>
4. <span data-ttu-id="19ebe-110">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="19ebe-110">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="19ebe-111">W polu Kod konta wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="19ebe-111">In the Account code field, select an option.</span></span>
    * <span data-ttu-id="19ebe-112">Kod konta typu „Grupa” służy do konfigurowania umów handlowych na cenę sprzedaży, które są specyficzne dla kanałów, programów lojalnościowe, katalogów i przynależności.</span><span class="sxs-lookup"><span data-stu-id="19ebe-112">A "Group" type account code is used to set up sales price trade agreements that are specific for Channels, Loyalty programs, Catalogs, and Affiliations.</span></span>  
6. <span data-ttu-id="19ebe-113">W polu Wybór konta wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="19ebe-113">In the Account selection field, enter or select a value.</span></span>
7. <span data-ttu-id="19ebe-114">W polu Kategoria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="19ebe-114">In the Category field, enter or select a value.</span></span>
8. <span data-ttu-id="19ebe-115">W polu Kwota/procent wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="19ebe-115">In the Amount/Percent field, enter a number.</span></span>
9. <span data-ttu-id="19ebe-116">W polu Wersja zaokrąglania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="19ebe-116">In the Rounding version field, enter or select a value.</span></span>
10. <span data-ttu-id="19ebe-117">Kliknij opcję Generowanie umów handlowych.</span><span class="sxs-lookup"><span data-stu-id="19ebe-117">Click Generate trade agreements.</span></span>
11. <span data-ttu-id="19ebe-118">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="19ebe-118">Click Next.</span></span>
12. <span data-ttu-id="19ebe-119">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="19ebe-119">In the From date field, enter a date.</span></span>
13. <span data-ttu-id="19ebe-120">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="19ebe-120">In the To date field, enter a date.</span></span>
14. <span data-ttu-id="19ebe-121">W polu Znajdź następny wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="19ebe-121">Select Yes in the Find next field.</span></span>
15. <span data-ttu-id="19ebe-122">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="19ebe-122">Click Next.</span></span>
16. <span data-ttu-id="19ebe-123">Kliknij przycisk Zakończ.</span><span class="sxs-lookup"><span data-stu-id="19ebe-123">Click Finish.</span></span>
    * <span data-ttu-id="19ebe-124">Spowoduje to utworzenie arkusza umów handlowych i otwarcie go do przejrzenia.</span><span class="sxs-lookup"><span data-stu-id="19ebe-124">This creates a Trade agreement journal and opens it for your review.</span></span>  
17. <span data-ttu-id="19ebe-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="19ebe-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="19ebe-126">Arkusze umów handlowych tworzone na podstawie reguł cen dla kategorii nie są księgowane.</span><span class="sxs-lookup"><span data-stu-id="19ebe-126">The trade agreement journals created from the Category pricing rules aren't posted.</span></span> <span data-ttu-id="19ebe-127">Można przeglądać i edytować wygenerowane ceny przed ich zaksięgowaniem.</span><span class="sxs-lookup"><span data-stu-id="19ebe-127">You can  review and edit the prices generated before posting them.</span></span>  
18. <span data-ttu-id="19ebe-128">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="19ebe-128">Click Edit.</span></span>
19. <span data-ttu-id="19ebe-129">W polu Kwota w walucie wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="19ebe-129">In the Amount in currency field, enter a number.</span></span>
20. <span data-ttu-id="19ebe-130">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="19ebe-130">Click Post.</span></span>
21. <span data-ttu-id="19ebe-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="19ebe-131">Click OK.</span></span>
22. <span data-ttu-id="19ebe-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="19ebe-132">Close the page.</span></span>
23. <span data-ttu-id="19ebe-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="19ebe-133">Close the page.</span></span>
24. <span data-ttu-id="19ebe-134">Kliknij kartę Reguły cen dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="19ebe-134">Click the Category price rules tab.</span></span>
    * <span data-ttu-id="19ebe-135">Na tej liście pojawią się reguły cen dla kategorii specyficzne dla kanału.</span><span class="sxs-lookup"><span data-stu-id="19ebe-135">Channel specific Category pricing rules will show in this list.</span></span>  


