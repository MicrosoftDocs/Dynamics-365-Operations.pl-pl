---
title: EUR-00015 Konfigurowanie identyfikatora VAT
description: Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxRegistrationType, TaxRegistrationTypeCreate, TaxRegistrationLegislationTypes
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66ee7215dc21921f9d8e405c3f77d9b5e0b89a9e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "371493"
---
# <a name="eur-00015-set-up-vat-id"></a><span data-ttu-id="e1809-103">EUR-00015 Konfigurowanie identyfikatora VAT</span><span class="sxs-lookup"><span data-stu-id="e1809-103">EUR-00015 Set up VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1809-104">Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji.</span><span class="sxs-lookup"><span data-stu-id="e1809-104">This procedure walks you through VAT ID registration prerequisites, such as setting up a registration type and assigning it to a registration category.</span></span> <span data-ttu-id="e1809-105">Dodatkowe informacje dotyczące identyfikatorów rejestracji i ich przetwarzania, w tym wymagań wstępnych, można znaleźć w temacie pomocy o rejestrowaniu identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="e1809-105">You can find additional information about registration IDs and registration ID processing, including required prerequisites, in the Registration IDs help topic.</span></span> 

<span data-ttu-id="e1809-106">Zawarte tu informacje dotyczą wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="e1809-106">The information here applies to all European countries/regions.</span></span> <span data-ttu-id="e1809-107">Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="e1809-107">The task was created using the demo data company DEMF with Germany as the legal entity primary address.</span></span> <span data-ttu-id="e1809-108">To zadanie jest przeznaczone dla administratorów systemu.</span><span class="sxs-lookup"><span data-stu-id="e1809-108">This task is intended for system administrators.</span></span> <span data-ttu-id="e1809-109">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="e1809-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="e1809-110">Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Typy rejestracji > Typy rejestracji.</span><span class="sxs-lookup"><span data-stu-id="e1809-110">Go to Organization administration > Global address book > Registration types > Registration types.</span></span>
2. <span data-ttu-id="e1809-111">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="e1809-111">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="e1809-112">W polu Nazwa wpisz „Identyfikator VAT”.</span><span class="sxs-lookup"><span data-stu-id="e1809-112">In the Name field, type 'VAT ID'.</span></span>
4. <span data-ttu-id="e1809-113">W polu Opis wpisz „Numer VAT”.</span><span class="sxs-lookup"><span data-stu-id="e1809-113">In the Description field, VAT number.</span></span>
5. <span data-ttu-id="e1809-114">W polu Kraj/region wprowadź lub wybierz wartość DEU.</span><span class="sxs-lookup"><span data-stu-id="e1809-114">In the Country/region field, enter or select a value DEU</span></span>
6. <span data-ttu-id="e1809-115">W polu Unikatowe wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e1809-115">Select Yes in the Unique field.</span></span>
    * <span data-ttu-id="e1809-116">Zaznacz to pole wyboru, aby sprawdzać, czy identyfikator VAT jest unikatowy.</span><span class="sxs-lookup"><span data-stu-id="e1809-116">Select this check box to verify if the VAT ID is unique.</span></span>  
7. <span data-ttu-id="e1809-117">W polu Podstawowy dla kraju wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e1809-117">Select Yes in the Primary for country field.</span></span>
    * <span data-ttu-id="e1809-118">To pole wyboru należy zaznaczyć, jeśli identyfikator VAT ma obowiązywać dla wszystkich adresów należących do określonego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="e1809-118">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
8. <span data-ttu-id="e1809-119">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="e1809-119">Click Create.</span></span>
9. <span data-ttu-id="e1809-120">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="e1809-120">Click Add.</span></span>
10. <span data-ttu-id="e1809-121">W polu Kraj/region wprowadź lub wybierz wartość ITA.</span><span class="sxs-lookup"><span data-stu-id="e1809-121">In the Country/region field, enter or select a value ITA</span></span>
11. <span data-ttu-id="e1809-122">W polu Format wpisz wartość „###########”.</span><span class="sxs-lookup"><span data-stu-id="e1809-122">In the Format field, type '###########'.</span></span>
    * <span data-ttu-id="e1809-123">Po wprowadzeniu identyfikator rejestracji tego typu dla wybranego kraju/regionu identyfikator rejestracji będzie weryfikowany względem tego formatu.</span><span class="sxs-lookup"><span data-stu-id="e1809-123">When you enter a registration ID of this type for the selected country/region, the registration ID will be verified against this format.</span></span>  
12. <span data-ttu-id="e1809-124">Zaznacz pole wyboru Unikatowe.</span><span class="sxs-lookup"><span data-stu-id="e1809-124">Select the Unique check box.</span></span>
    * <span data-ttu-id="e1809-125">Zaznacz to pole wyboru, aby sprawdzać, czy identyfikator VAT jest unikatowy.</span><span class="sxs-lookup"><span data-stu-id="e1809-125">Select this check box to verify if the VAT ID is unique.</span></span>  
13. <span data-ttu-id="e1809-126">Zaznacz pole wyboru Podstawowy dla kraju.</span><span class="sxs-lookup"><span data-stu-id="e1809-126">Select the Primary for country check box.</span></span>
    * <span data-ttu-id="e1809-127">To pole wyboru należy zaznaczyć, jeśli identyfikator VAT ma obowiązywać dla wszystkich adresów należących do określonego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="e1809-127">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
14. <span data-ttu-id="e1809-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e1809-128">Click Save.</span></span>
15. <span data-ttu-id="e1809-129">Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Typy rejestracji > Kategorie rejestracji.</span><span class="sxs-lookup"><span data-stu-id="e1809-129">Go to Organization administration > Global address book > Registration types > Registration categories.</span></span>
16. <span data-ttu-id="e1809-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e1809-130">Click New.</span></span>
17. <span data-ttu-id="e1809-131">W polu Kraj/region wprowadź lub wybierz wartość Identyfikator VAT, DEU.</span><span class="sxs-lookup"><span data-stu-id="e1809-131">In the Country/region field, enter or select a value VAT ID, DEU</span></span>
18. <span data-ttu-id="e1809-132">W polu Kategoria rejestracji wybierz wartość „Identyfikator VAT”.</span><span class="sxs-lookup"><span data-stu-id="e1809-132">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="e1809-133">Przypisz utworzony wcześniej typ rejestracji do wstępnie zdefiniowanej kategorii rejestracji.</span><span class="sxs-lookup"><span data-stu-id="e1809-133">Assign the registration type that you created earlier to a predefined Registration category.</span></span>  
19. <span data-ttu-id="e1809-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e1809-134">Click New.</span></span>
20. <span data-ttu-id="e1809-135">W polu Kraj/region wprowadź lub wybierz wartość Identyfikator VAT, ITA.</span><span class="sxs-lookup"><span data-stu-id="e1809-135">In the Country/region field, enter or select a value VAT ID, ITA</span></span>
21. <span data-ttu-id="e1809-136">W polu Kategoria rejestracji wybierz wartość „Identyfikator VAT”.</span><span class="sxs-lookup"><span data-stu-id="e1809-136">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="e1809-137">Przypisz utworzony typ rejestracji do wstępnie zdefiniowanej kategorii rejestracji.</span><span class="sxs-lookup"><span data-stu-id="e1809-137">Assign the registration type that you created to a predefined registration category.</span></span>  
22. <span data-ttu-id="e1809-138">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e1809-138">Click Save.</span></span>

