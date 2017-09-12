--- 
title: Konfigurowanie identyfikatora VAT
description: "Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ff12ab434d88471452f191cd56b630419e07b22e
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-vat-id"></a><span data-ttu-id="4590b-103">Konfigurowanie identyfikatora VAT</span><span class="sxs-lookup"><span data-stu-id="4590b-103">Set up VAT ID</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4590b-104">Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji.</span><span class="sxs-lookup"><span data-stu-id="4590b-104">This procedure walks you through VAT ID registration prerequisites, such as setting up a registration type and assigning it to a registration category.</span></span> <span data-ttu-id="4590b-105">Dodatkowe informacje dotyczące identyfikatorów rejestracji i ich przetwarzania, w tym wymagań wstępnych, można znaleźć w temacie pomocy o rejestrowaniu identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="4590b-105">You can find additional information about registration IDs and registration ID processing, including required prerequisites, in the Registration IDs help topic.</span></span> 

<span data-ttu-id="4590b-106">Zawarte tu informacje dotyczą wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="4590b-106">The information here applies to all European countries/regions.</span></span> <span data-ttu-id="4590b-107">Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="4590b-107">The task was created using the demo data company DEMF with Germany as the legal entity primary address.</span></span> <span data-ttu-id="4590b-108">To zadanie jest przeznaczone dla administratorów systemu.</span><span class="sxs-lookup"><span data-stu-id="4590b-108">This task is intended for system administrators.</span></span> <span data-ttu-id="4590b-109">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="4590b-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="4590b-110">Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Typy rejestracji > Typy rejestracji.</span><span class="sxs-lookup"><span data-stu-id="4590b-110">Go to Organization administration > Global address book > Registration types > Registration types.</span></span>
2. <span data-ttu-id="4590b-111">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4590b-111">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="4590b-112">W polu Nazwa wpisz „Identyfikator VAT”.</span><span class="sxs-lookup"><span data-stu-id="4590b-112">In the Name field, type 'VAT ID'.</span></span>
4. <span data-ttu-id="4590b-113">W polu Opis wpisz „Numer VAT”.</span><span class="sxs-lookup"><span data-stu-id="4590b-113">In the Description field, VAT number.</span></span>
5. <span data-ttu-id="4590b-114">W polu Kraj/region wprowadź lub wybierz wartość DEU.</span><span class="sxs-lookup"><span data-stu-id="4590b-114">In the Country/region field, enter or select a value DEU</span></span>
6. <span data-ttu-id="4590b-115">W polu Unikatowe wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="4590b-115">Select Yes in the Unique field.</span></span>
    * <span data-ttu-id="4590b-116">Zaznacz to pole wyboru, aby sprawdzać, czy identyfikator VAT jest unikatowy.</span><span class="sxs-lookup"><span data-stu-id="4590b-116">Select this check box to verify if the VAT ID is unique.</span></span>  
7. <span data-ttu-id="4590b-117">W polu Podstawowy dla kraju wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="4590b-117">Select Yes in the Primary for country field.</span></span>
    * <span data-ttu-id="4590b-118">To pole wyboru należy zaznaczyć, jeśli identyfikator VAT ma obowiązywać dla wszystkich adresów należących do określonego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="4590b-118">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
8. <span data-ttu-id="4590b-119">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="4590b-119">Click Create.</span></span>
9. <span data-ttu-id="4590b-120">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="4590b-120">Click Add.</span></span>
10. <span data-ttu-id="4590b-121">W polu Kraj/region wprowadź lub wybierz wartość ITA.</span><span class="sxs-lookup"><span data-stu-id="4590b-121">In the Country/region field, enter or select a value ITA</span></span>
11. <span data-ttu-id="4590b-122">W polu Format wpisz wartość „###########”.</span><span class="sxs-lookup"><span data-stu-id="4590b-122">In the Format field, type '###########'.</span></span>
    * <span data-ttu-id="4590b-123">Po wprowadzeniu identyfikator rejestracji tego typu dla wybranego kraju/regionu identyfikator rejestracji będzie weryfikowany względem tego formatu.</span><span class="sxs-lookup"><span data-stu-id="4590b-123">When you enter a registration ID of this type for the selected country/region, the registration ID will be verified against this format.</span></span>  
12. <span data-ttu-id="4590b-124">Zaznacz pole wyboru Unikatowe.</span><span class="sxs-lookup"><span data-stu-id="4590b-124">Select the Unique check box.</span></span>
    * <span data-ttu-id="4590b-125">Zaznacz to pole wyboru, aby sprawdzać, czy identyfikator VAT jest unikatowy.</span><span class="sxs-lookup"><span data-stu-id="4590b-125">Select this check box to verify if the VAT ID is unique.</span></span>  
13. <span data-ttu-id="4590b-126">Zaznacz pole wyboru Podstawowy dla kraju.</span><span class="sxs-lookup"><span data-stu-id="4590b-126">Select the Primary for country check box.</span></span>
    * <span data-ttu-id="4590b-127">To pole wyboru należy zaznaczyć, jeśli identyfikator VAT ma obowiązywać dla wszystkich adresów należących do określonego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="4590b-127">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
14. <span data-ttu-id="4590b-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="4590b-128">Click Save.</span></span>
15. <span data-ttu-id="4590b-129">Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Typy rejestracji > Kategorie rejestracji.</span><span class="sxs-lookup"><span data-stu-id="4590b-129">Go to Organization administration > Global address book > Registration types > Registration categories.</span></span>
16. <span data-ttu-id="4590b-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4590b-130">Click New.</span></span>
17. <span data-ttu-id="4590b-131">W polu Kraj/region wprowadź lub wybierz wartość Identyfikator VAT, DEU.</span><span class="sxs-lookup"><span data-stu-id="4590b-131">In the Country/region field, enter or select a value VAT ID, DEU</span></span>
18. <span data-ttu-id="4590b-132">W polu Kategoria rejestracji wybierz wartość „Identyfikator VAT”.</span><span class="sxs-lookup"><span data-stu-id="4590b-132">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="4590b-133">Przypisz utworzony wcześniej typ rejestracji do wstępnie zdefiniowanej kategorii rejestracji.</span><span class="sxs-lookup"><span data-stu-id="4590b-133">Assign the registration type that you created earlier to a predefined Registration category.</span></span>  
19. <span data-ttu-id="4590b-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4590b-134">Click New.</span></span>
20. <span data-ttu-id="4590b-135">W polu Kraj/region wprowadź lub wybierz wartość Identyfikator VAT, ITA.</span><span class="sxs-lookup"><span data-stu-id="4590b-135">In the Country/region field, enter or select a value VAT ID, ITA</span></span>
21. <span data-ttu-id="4590b-136">W polu Kategoria rejestracji wybierz wartość „Identyfikator VAT”.</span><span class="sxs-lookup"><span data-stu-id="4590b-136">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="4590b-137">Przypisz utworzony typ rejestracji do wstępnie zdefiniowanej kategorii rejestracji.</span><span class="sxs-lookup"><span data-stu-id="4590b-137">Assign the registration type that you created to a predefined registration category.</span></span>  
22. <span data-ttu-id="4590b-138">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="4590b-138">Click Save.</span></span>


