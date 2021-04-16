---
title: Konfigurowanie zasad faktur od dostawców
description: W tym temacie opisano sposób konfigurowania zasad płatności dla faktur od dostawcy.
author: ShivamPandey-msft
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c088f6e3fea7c218cfd2108d0f279bccf1292772
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816203"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="aa87d-103">Konfigurowanie zasad faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="aa87d-103">Set up vendor invoice policies</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aa87d-104">W tym temacie opisano sposób konfigurowania zasad płatności dla faktur od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="aa87d-104">This topic explains how to set up vendor invoice policies.</span></span> <span data-ttu-id="aa87d-105">Zasady dotyczące faktur od dostawców są uruchamiane podczas księgowania faktur od dostawców przy użyciu strony Faktura od dostawcy oraz po otwarciu strony naruszeń zasad faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="aa87d-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="aa87d-106">Można także skonfigurować przepływ pracy faktur od dostawcy, aby uruchamiał zasady dotyczące faktur od dostawców podczas każdego przesłania faktur do przepływu.</span><span class="sxs-lookup"><span data-stu-id="aa87d-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="aa87d-107">Zasady faktur od dostawców nie dotyczą faktur, które zostały utworzone w rejestrze faktur lub arkuszu faktur.</span><span class="sxs-lookup"><span data-stu-id="aa87d-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="aa87d-108">Funkcja sprawdzania poprawności uzgadniania faktur nie używa zasad dotyczących faktur od dostawców, ale jest konfigurowana na stronie Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="aa87d-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="aa87d-109">To nagranie wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="aa87d-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="aa87d-110">Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości.</span><span class="sxs-lookup"><span data-stu-id="aa87d-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="aa87d-111">Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur.</span><span class="sxs-lookup"><span data-stu-id="aa87d-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="aa87d-112">Przygotowanie do tworzenia zasad dotyczących faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="aa87d-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="aa87d-113">Otwórz **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="aa87d-114">Kliknij kartę **Weryfikacja faktury**</span><span class="sxs-lookup"><span data-stu-id="aa87d-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="aa87d-115">Zaznacz lub wyczyść pole wyboru **Automatycznie aktualizuj stan nagłówka faktury**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="aa87d-116">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-116">Select **OK**.</span></span>
5. <span data-ttu-id="aa87d-117">W polu **Księguj fakturę z rozbieżnościami** zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="aa87d-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="aa87d-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aa87d-118">Close the page.</span></span>
7. <span data-ttu-id="aa87d-119">Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="aa87d-120">Wybierz **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="aa87d-121">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-121">Select **Add**.</span></span>
10. <span data-ttu-id="aa87d-122">Zamknij tę stronę, aby powrócić do strony głównej.</span><span class="sxs-lookup"><span data-stu-id="aa87d-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="aa87d-123">Tworzenie typów reguł dla faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="aa87d-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="aa87d-124">Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia zasad > Typy reguł faktur od dostawców**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="aa87d-125">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-125">Select **New**.</span></span>
3. <span data-ttu-id="aa87d-126">W polach **Nazwa reguły** i **Opis** wpisz wartości.</span><span class="sxs-lookup"><span data-stu-id="aa87d-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="aa87d-127">W polu **Nazwa kwerendy** wybierz przycisk listy rozwijanej, aby otworzyć wyszukiwanie, a następnie kliknij odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="aa87d-127">In the **Query name** field, select the drop-down button to open the lookup, then select the desired record.</span></span>
5. <span data-ttu-id="aa87d-128">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-128">Select **Save**.</span></span>
6. <span data-ttu-id="aa87d-129">Zamknij tę stronę, aby powrócić do strony głównej.</span><span class="sxs-lookup"><span data-stu-id="aa87d-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="aa87d-130">Definiowanie zasad dotyczących faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="aa87d-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="aa87d-131">Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="aa87d-132">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-132">Select **New**.</span></span>
3. <span data-ttu-id="aa87d-133">W polach **Nazwa** i **Opis** wpisz wartości.</span><span class="sxs-lookup"><span data-stu-id="aa87d-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="aa87d-134">Rozwiń lub zwiń sekcję **Organizacje zasad**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="aa87d-135">W drzewie zaznacz pozycję **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="aa87d-136">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-136">Select **Add**.</span></span>
7. <span data-ttu-id="aa87d-137">Rozwiń lub zwiń sekcję **Reguły zasad**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="aa87d-138">Wybierz pozycję **Utwórz regułę**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="aa87d-139">W polu **Opis reguły** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="aa87d-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="aa87d-140">Wybierz **Filtry**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-140">Select **Filter**.</span></span>
11. <span data-ttu-id="aa87d-141">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-141">Select **Add**.</span></span> <span data-ttu-id="aa87d-142">Wybierz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="aa87d-142">Select the desired record.</span></span>
12. <span data-ttu-id="aa87d-143">W polach **Tabela**, **Tabela pochodna** i **Pole**, wybierz lub wprowadź opcje z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="aa87d-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="aa87d-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aa87d-144">Close the page.</span></span>
14. <span data-ttu-id="aa87d-145">W polu **Kryteria** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="aa87d-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="aa87d-146">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-146">Select **OK**.</span></span>
16. <span data-ttu-id="aa87d-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa87d-147">Select **OK**.</span></span>
17. <span data-ttu-id="aa87d-148">Zamknij te strony, aby powrócić do strony głównej.</span><span class="sxs-lookup"><span data-stu-id="aa87d-148">Close the pages to return to the home page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]