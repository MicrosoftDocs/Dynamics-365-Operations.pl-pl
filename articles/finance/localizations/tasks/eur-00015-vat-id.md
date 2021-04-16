---
title: EUR-00015 Konfigurowanie identyfikatora VAT
description: Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxRegistrationType, TaxRegistrationTypeCreate, TaxRegistrationLegislationTypes
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5488bb020209d6bf6fb39ae0b4f897f5513bdf93
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821807"
---
# <a name="eur-00015-set-up-vat-id"></a><span data-ttu-id="0beed-103">EUR-00015 Konfigurowanie identyfikatora VAT</span><span class="sxs-lookup"><span data-stu-id="0beed-103">EUR-00015 Set up VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0beed-104">Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji.</span><span class="sxs-lookup"><span data-stu-id="0beed-104">This procedure walks you through VAT ID registration prerequisites, such as setting up a registration type and assigning it to a registration category.</span></span> <span data-ttu-id="0beed-105">Dodatkowe informacje dotyczące identyfikatorów rejestracji i ich przetwarzania, w tym wymagań wstępnych, można znaleźć w temacie pomocy o rejestrowaniu identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="0beed-105">You can find additional information about registration IDs and registration ID processing, including required prerequisites, in the Registration IDs help topic.</span></span> 

<span data-ttu-id="0beed-106">Zawarte tu informacje dotyczą wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="0beed-106">The information here applies to all European countries/regions.</span></span> <span data-ttu-id="0beed-107">Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="0beed-107">The task was created using the demo data company DEMF with Germany as the legal entity primary address.</span></span> <span data-ttu-id="0beed-108">To zadanie jest przeznaczone dla administratorów systemu.</span><span class="sxs-lookup"><span data-stu-id="0beed-108">This task is intended for system administrators.</span></span> <span data-ttu-id="0beed-109">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="0beed-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="0beed-110">Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Typy rejestracji > Typy rejestracji.</span><span class="sxs-lookup"><span data-stu-id="0beed-110">Go to Organization administration > Global address book > Registration types > Registration types.</span></span>
2. <span data-ttu-id="0beed-111">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="0beed-111">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="0beed-112">W polu Nazwa wpisz „Identyfikator VAT”.</span><span class="sxs-lookup"><span data-stu-id="0beed-112">In the Name field, type 'VAT ID'.</span></span>
4. <span data-ttu-id="0beed-113">W polu Opis wpisz „Numer VAT”.</span><span class="sxs-lookup"><span data-stu-id="0beed-113">In the Description field, VAT number.</span></span>
5. <span data-ttu-id="0beed-114">W polu Kraj/region wprowadź lub wybierz wartość DEU.</span><span class="sxs-lookup"><span data-stu-id="0beed-114">In the Country/region field, enter or select a value DEU</span></span>
6. <span data-ttu-id="0beed-115">W polu Unikatowe wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="0beed-115">Select Yes in the Unique field.</span></span>
    * <span data-ttu-id="0beed-116">Zaznacz to pole wyboru, aby sprawdzać, czy identyfikator VAT jest unikatowy.</span><span class="sxs-lookup"><span data-stu-id="0beed-116">Select this check box to verify if the VAT ID is unique.</span></span>  
7. <span data-ttu-id="0beed-117">W polu Podstawowy dla kraju wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="0beed-117">Select Yes in the Primary for country field.</span></span>
    * <span data-ttu-id="0beed-118">To pole wyboru należy zaznaczyć, jeśli identyfikator VAT ma obowiązywać dla wszystkich adresów należących do określonego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="0beed-118">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
8. <span data-ttu-id="0beed-119">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="0beed-119">Click Create.</span></span>
9. <span data-ttu-id="0beed-120">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="0beed-120">Click Add.</span></span>
10. <span data-ttu-id="0beed-121">W polu Kraj/region wprowadź lub wybierz wartość ITA.</span><span class="sxs-lookup"><span data-stu-id="0beed-121">In the Country/region field, enter or select a value ITA</span></span>
11. <span data-ttu-id="0beed-122">W polu Format wpisz wartość „###########”.</span><span class="sxs-lookup"><span data-stu-id="0beed-122">In the Format field, type '###########'.</span></span>
    * <span data-ttu-id="0beed-123">Po wprowadzeniu identyfikator rejestracji tego typu dla wybranego kraju/regionu identyfikator rejestracji będzie weryfikowany względem tego formatu.</span><span class="sxs-lookup"><span data-stu-id="0beed-123">When you enter a registration ID of this type for the selected country/region, the registration ID will be verified against this format.</span></span>  
12. <span data-ttu-id="0beed-124">Zaznacz pole wyboru Unikatowe.</span><span class="sxs-lookup"><span data-stu-id="0beed-124">Select the Unique check box.</span></span>
    * <span data-ttu-id="0beed-125">Zaznacz to pole wyboru, aby sprawdzać, czy identyfikator VAT jest unikatowy.</span><span class="sxs-lookup"><span data-stu-id="0beed-125">Select this check box to verify if the VAT ID is unique.</span></span>  
13. <span data-ttu-id="0beed-126">Zaznacz pole wyboru Podstawowy dla kraju.</span><span class="sxs-lookup"><span data-stu-id="0beed-126">Select the Primary for country check box.</span></span>
    * <span data-ttu-id="0beed-127">To pole wyboru należy zaznaczyć, jeśli identyfikator VAT ma obowiązywać dla wszystkich adresów należących do określonego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="0beed-127">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
14. <span data-ttu-id="0beed-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0beed-128">Click Save.</span></span>
15. <span data-ttu-id="0beed-129">Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Typy rejestracji > Kategorie rejestracji.</span><span class="sxs-lookup"><span data-stu-id="0beed-129">Go to Organization administration > Global address book > Registration types > Registration categories.</span></span>
16. <span data-ttu-id="0beed-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0beed-130">Click New.</span></span>
17. <span data-ttu-id="0beed-131">W polu Kraj/region wprowadź lub wybierz wartość Identyfikator VAT, DEU.</span><span class="sxs-lookup"><span data-stu-id="0beed-131">In the Country/region field, enter or select a value VAT ID, DEU</span></span>
18. <span data-ttu-id="0beed-132">W polu Kategoria rejestracji wybierz wartość „Identyfikator VAT”.</span><span class="sxs-lookup"><span data-stu-id="0beed-132">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="0beed-133">Przypisz utworzony wcześniej typ rejestracji do wstępnie zdefiniowanej kategorii rejestracji.</span><span class="sxs-lookup"><span data-stu-id="0beed-133">Assign the registration type that you created earlier to a predefined Registration category.</span></span>  
19. <span data-ttu-id="0beed-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0beed-134">Click New.</span></span>
20. <span data-ttu-id="0beed-135">W polu Kraj/region wprowadź lub wybierz wartość Identyfikator VAT, ITA.</span><span class="sxs-lookup"><span data-stu-id="0beed-135">In the Country/region field, enter or select a value VAT ID, ITA</span></span>
21. <span data-ttu-id="0beed-136">W polu Kategoria rejestracji wybierz wartość „Identyfikator VAT”.</span><span class="sxs-lookup"><span data-stu-id="0beed-136">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="0beed-137">Przypisz utworzony typ rejestracji do wstępnie zdefiniowanej kategorii rejestracji.</span><span class="sxs-lookup"><span data-stu-id="0beed-137">Assign the registration type that you created to a predefined registration category.</span></span>  
22. <span data-ttu-id="0beed-138">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0beed-138">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]