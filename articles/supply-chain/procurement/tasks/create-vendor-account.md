---
title: Utworzenie konta dostawcy
description: W tej procedurze pokazano, jak utworzyć konto dostawcy oraz dodać informacje adresowe i kontaktowe.
author: mkirknel
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aca23db2a0cc86a2c12ea74d3b1e491643b7efec
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207699"
---
# <a name="create-a-vendor-account"></a><span data-ttu-id="5aa7c-103">Utworzenie konta dostawcy</span><span class="sxs-lookup"><span data-stu-id="5aa7c-103">Create a vendor account</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5aa7c-104">W tej procedurze pokazano, jak utworzyć konto dostawcy oraz dodać informacje adresowe i kontaktowe.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-104">This procedure shows how to create a vendor account, and add an address and contact information.</span></span> <span data-ttu-id="5aa7c-105">Procedura nie pokazuje sposobu wypełnienia wszystkich pól do celów zakupowych i finansowych.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-105">The procedure does not show how to populate all fields for purchasing and financial purposes.</span></span> <span data-ttu-id="5aa7c-106">Aby uzyskać więcej informacji o tych polach, przeczytaj ich opisy.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-106">To learn more about those fields, please read the field descriptions.</span></span> <span data-ttu-id="5aa7c-107">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="5aa7c-108">Konta dostawców są zwykle tworzone przez pracownika działu zaopatrzenia lub personel działu rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-108">Vendor accounts are typically created by a procurement professional or accounts receivable personnel.</span></span>


## <a name="create-a-vendor-account"></a><span data-ttu-id="5aa7c-109">Tworzenie konta dostawcy</span><span class="sxs-lookup"><span data-stu-id="5aa7c-109">Create a vendor account</span></span>
1. <span data-ttu-id="5aa7c-110">Przejdź do **Okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy.**</span><span class="sxs-lookup"><span data-stu-id="5aa7c-110">Go to **Navigation pane > Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="5aa7c-111">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-111">Click **New**.</span></span>
3. <span data-ttu-id="5aa7c-112">W polu **Konto dostawcy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-112">In the **Vendor account** field, type a value.</span></span>
    - <span data-ttu-id="5aa7c-113">Wartość może być wprowadzana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-113">The value may be populated automatically.</span></span> <span data-ttu-id="5aa7c-114">Jeśli tak się dzieje, możesz pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-114">If so, you can skip this step.</span></span>  
    - <span data-ttu-id="5aa7c-115">Można tworzyć konta dostawców dla osób lub organizacji.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-115">You can create vendor accounts for a person or organization.</span></span> <span data-ttu-id="5aa7c-116">Wpłynie to na dostępność pól.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-116">This will affect which fields are available.</span></span> <span data-ttu-id="5aa7c-117">W tym przykładzie utworzymy konto dostawcy dla organizacji.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-117">In this example, we'll create a vendor account for an organization.</span></span>   
4. <span data-ttu-id="5aa7c-118">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-118">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="5aa7c-119">Jeśli dostawca jest już stroną zarejestrowaną w systemie, można użyć listy rozwijanej i zaznaczyć go w tym polu, a nowe konto dostawcy odziedziczy już zarejestrowane informacje adresowe i kontaktowe.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-119">If your vendor is an already a registered party in your system you can use drop down and select them in this field and the new vendor account will inherit the address and contact information that's already registered.</span></span>
5. <span data-ttu-id="5aa7c-120">W polu **Grupa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-120">In the **Group** field, enter or select a value.</span></span> <span data-ttu-id="5aa7c-121">Grupa dostawców jest używana do grupowania dostawców, którzy mają wspólny dowolny z następujących parametrów: warunki płatności, rozliczenie okresu, konta księgowe księgowania zapasów (łącznie z grupą podatków), domyślne konta księgowe, kody filtrów produktów lub konfiguracja prognoz dostaw.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-121">The vendor group is used to group vendors that have any of the following parameters in common: Terms of payment, settle period, inventory posting ledger accounts – including the sales tax group, default ledger accounts, product filter codes, or supply forecast configuration.</span></span>
6. <span data-ttu-id="5aa7c-122">W polu **Liczba pracowników** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-122">In the **Number of employees** field, enter a number.</span></span>
7. <span data-ttu-id="5aa7c-123">W polu **Numer organizacji** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-123">In the **Organization number** field, type a value.</span></span>

## <a name="add-an-address"></a><span data-ttu-id="5aa7c-124">Dodawanie adresu</span><span class="sxs-lookup"><span data-stu-id="5aa7c-124">Add an address</span></span>
1. <span data-ttu-id="5aa7c-125">Rozwiń sekcję **Adresy**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-125">Expand the **Addresses** section.</span></span>
2. <span data-ttu-id="5aa7c-126">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-126">Click **Add**.</span></span>
3. <span data-ttu-id="5aa7c-127">W polu **Cel** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-127">In the **Purpose** field, enter or select a value.</span></span> <span data-ttu-id="5aa7c-128">Można wybrać jeden lub więcej celów.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-128">You can select one or more purposes.</span></span> <span data-ttu-id="5aa7c-129">Są one używane do wybierania poprawnego adresu dla danego celu.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-129">These are used to select the correct address for a given purpose.</span></span> <span data-ttu-id="5aa7c-130">Na przykład jeśli celem jest „Faktura”, ten adres będzie używany przy wysyłaniu faktur.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-130">For example, if the purpose is "Invoice" that address will be used when you send invoices.</span></span>
4. <span data-ttu-id="5aa7c-131">W polu **Nazwa lub opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-131">In the **Name or description** field, type a value.</span></span>
5. <span data-ttu-id="5aa7c-132">W polu **Kraj/region** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-132">In the **Country/region** field, enter or select a value.</span></span> <span data-ttu-id="5aa7c-133">Podaj szczegóły adresu.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-133">Enter the address details.</span></span> <span data-ttu-id="5aa7c-134">Wybrany kraj/region zdecyduje o polach, które zostaną Ci wyświetlone, stosownie do formatu adresu kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-134">The country/region that you selected will determine the fields you are presented with, corresponding to the address format for the country/region.</span></span> 
6. <span data-ttu-id="5aa7c-135">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-135">Click **OK**.</span></span>

## <a name="add-contact-information"></a><span data-ttu-id="5aa7c-136">Dodawanie informacji kontaktowych</span><span class="sxs-lookup"><span data-stu-id="5aa7c-136">Add contact information</span></span>
1. <span data-ttu-id="5aa7c-137">Rozwiń sekcję **Informacje kontaktowe**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-137">Expand the **Contact information** section.</span></span>
2. <span data-ttu-id="5aa7c-138">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-138">Click **Add**.</span></span>
3. <span data-ttu-id="5aa7c-139">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-139">In the **Description** field, type a value.</span></span>
4. <span data-ttu-id="5aa7c-140">W polu **Typ** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-140">In the **Type** field, select an option.</span></span>
5. <span data-ttu-id="5aa7c-141">W polu **Numer/adres osoby kontaktowej** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-141">In the **Contact number/address** field, type a value.</span></span> <span data-ttu-id="5aa7c-142">Jeśli jest to podstawowa osoba kontaktowa, można zaznaczyć pole wyboru Podstawowe.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-142">You can select the Primary check box if this is the primary contact.</span></span>  
6. <span data-ttu-id="5aa7c-143">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-143">Click **Save**.</span></span>
7. <span data-ttu-id="5aa7c-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-144">Close the page.</span></span>
8. <span data-ttu-id="5aa7c-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-145">Close the page.</span></span>

