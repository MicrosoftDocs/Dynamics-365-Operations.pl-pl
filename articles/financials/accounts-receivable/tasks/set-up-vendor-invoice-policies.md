---
title: Konfigurowanie zasad faktur od dostawców
description: W tym temacie wyjaśniono, jak skonfigurować zasady faktury od dostawcy w Dynamics 365 for Finance and Operatoins.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 328aafd16496fdbb963c9aa40a5c13005be7a382
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842816"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="2ee7f-103">Konfigurowanie zasad faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="2ee7f-103">Set up vendor invoice policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2ee7f-104">W tym temacie wyjaśniono, jak skonfigurować zasady faktury od dostawcy w Dynamics 365 for Finance and Operatoins.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-104">This topic explains how to set up vendor invoice policies in Dynamics 365 for Finance and Operatoins.</span></span> <span data-ttu-id="2ee7f-105">Zasady dotyczące faktur od dostawców są uruchamiane podczas księgowania faktur od dostawców przy użyciu strony Faktura od dostawcy oraz po otwarciu strony naruszeń zasad faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="2ee7f-106">Można także skonfigurować przepływ pracy faktur od dostawcy, aby uruchamiał zasady dotyczące faktur od dostawców podczas każdego przesłania faktur do przepływu.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="2ee7f-107">Zasady faktur od dostawców nie dotyczą faktur, które zostały utworzone w rejestrze faktur lub arkuszu faktur.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="2ee7f-108">Funkcja sprawdzania poprawności uzgadniania faktur nie używa zasad dotyczących faktur od dostawców, ale jest konfigurowana na stronie Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="2ee7f-109">To nagranie wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="2ee7f-110">Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="2ee7f-111">Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="2ee7f-112">Przygotowanie do tworzenia zasad dotyczących faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="2ee7f-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="2ee7f-113">Otwórz **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="2ee7f-114">Kliknij kartę **Weryfikacja faktury**</span><span class="sxs-lookup"><span data-stu-id="2ee7f-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="2ee7f-115">Zaznacz lub wyczyść pole wyboru **Automatycznie aktualizuj stan nagłówka faktury**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="2ee7f-116">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-116">Select **OK**.</span></span>
5. <span data-ttu-id="2ee7f-117">W polu **Księguj fakturę z rozbieżnościami** zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="2ee7f-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-118">Close the page.</span></span>
7. <span data-ttu-id="2ee7f-119">Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="2ee7f-120">Wybierz **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="2ee7f-121">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-121">Select **Add**.</span></span>
10. <span data-ttu-id="2ee7f-122">Zamknij tę stronę, aby powrócić do strony głównej.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="2ee7f-123">Tworzenie typów reguł dla faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="2ee7f-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="2ee7f-124">Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia zasad > Typy reguł faktur od dostawców**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="2ee7f-125">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-125">Select **New**.</span></span>
3. <span data-ttu-id="2ee7f-126">W polach **Nazwa reguły** i **Opis** wpisz wartości.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="2ee7f-127">W polu **Nazwa kwerendy** wybierz przycisk listy rozwijanej, aby otworzyć wyszukiwanie, a następnie kliknij odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-127">In the **Query name** field, select the drop-down button to open the lookup, then selec the desired record.</span></span>
5. <span data-ttu-id="2ee7f-128">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-128">Select **Save**.</span></span>
6. <span data-ttu-id="2ee7f-129">Zamknij tę stronę, aby powrócić do strony głównej.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="2ee7f-130">Definiowanie zasad dotyczących faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="2ee7f-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="2ee7f-131">Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="2ee7f-132">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-132">Select **New**.</span></span>
3. <span data-ttu-id="2ee7f-133">W polach **Nazwa** i **Opis** wpisz wartości.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="2ee7f-134">Rozwiń lub zwiń sekcję **Organizacje zasad**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="2ee7f-135">W drzewie zaznacz pozycję **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="2ee7f-136">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-136">Select **Add**.</span></span>
7. <span data-ttu-id="2ee7f-137">Rozwiń lub zwiń sekcję **Reguły zasad**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="2ee7f-138">Wybierz pozycję **Utwórz regułę**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="2ee7f-139">W polu **Opis reguły** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="2ee7f-140">Wybierz **Filtry**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-140">Select **Filter**.</span></span>
11. <span data-ttu-id="2ee7f-141">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-141">Select **Add**.</span></span> <span data-ttu-id="2ee7f-142">Wybierz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-142">Select the desired record.</span></span>
12. <span data-ttu-id="2ee7f-143">W polach **Tabela**, **Tabela pochodna** i **Pole**, wybierz lub wprowadź opcje z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="2ee7f-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-144">Close the page.</span></span>
14. <span data-ttu-id="2ee7f-145">W polu **Kryteria** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="2ee7f-146">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-146">Select **OK**.</span></span>
16. <span data-ttu-id="2ee7f-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-147">Select **OK**.</span></span>
17. <span data-ttu-id="2ee7f-148">Zamknij te strony, aby powrócić do strony głównej.</span><span class="sxs-lookup"><span data-stu-id="2ee7f-148">Close the pages to return to the home page.</span></span>

