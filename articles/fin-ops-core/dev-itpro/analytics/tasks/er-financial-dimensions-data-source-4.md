---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 4 — Wykonanie raportu)
description: W tym temacie opisano sposób konfigurowania modelu raportowania elektronicznego w celu używania wymiarów finansowych jako źródła danych dla raportów ER. (część 4)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a06936da71d7b05f312a99c8c11d148403d29c3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752395"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="6c875-104">ER Używanie wymiarów finansowych jako źródła danych (Część 4 — Wykonanie raportu)</span><span class="sxs-lookup"><span data-stu-id="6c875-104">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6c875-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="6c875-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="6c875-106">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="6c875-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="6c875-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 3: Projektowanie raportu)”.</span><span class="sxs-lookup"><span data-stu-id="6c875-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="6c875-108">Należy także skonfigurować domyślne typy dokumentów na stronie Parametry raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="6c875-108">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="6c875-109">Domyślne typy dokumentów również są ustawiane podczas pobierania i importowania każdej konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="6c875-109">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="6c875-110">Generowanie raportu</span><span class="sxs-lookup"><span data-stu-id="6c875-110">Run report</span></span>
1. <span data-ttu-id="6c875-111">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="6c875-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="6c875-112">W drzewie rozwiń węzeł „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="6c875-112">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="6c875-113">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu\Raport arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="6c875-113">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="6c875-114">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="6c875-114">Click Run.</span></span>
<span data-ttu-id="6c875-115">![Strona konfiguracji raportowania elektronicznego](../media/er-financial-dimensions-guides-run1.png)</span><span class="sxs-lookup"><span data-stu-id="6c875-115">![ER configurations page](../media/er-financial-dimensions-guides-run1.png)</span></span>
5. <span data-ttu-id="6c875-116">Wprowadź lub wybierz wartość w polu Nazwa wymiaru.</span><span class="sxs-lookup"><span data-stu-id="6c875-116">In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="6c875-117">Aby zaznaczyć wszystkie wymiary w bieżącej firmie, wprowadź następujące dane: BusinessUnit;CostCenter;Dział;ItemGroup;MainAccount;Projekt</span><span class="sxs-lookup"><span data-stu-id="6c875-117">To select all dimensions in the current company, enter the following information:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
![Strona konfiguracji raportowania elektronicznego](../media/er-financial-dimensions-guides-run2.png)
6. <span data-ttu-id="6c875-119">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="6c875-119">Expand the Records to include section.</span></span>
7. <span data-ttu-id="6c875-120">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="6c875-120">Click Filter.</span></span>
8. <span data-ttu-id="6c875-121">Zaznacz wiersz z tabelą Arkusz księgi i polem Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="6c875-121">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="6c875-122">W polu Kryteria wpisz wartość „00057”.</span><span class="sxs-lookup"><span data-stu-id="6c875-122">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="6c875-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6c875-123">Click OK.</span></span>
11. <span data-ttu-id="6c875-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6c875-124">Click OK.</span></span>
<span data-ttu-id="6c875-125">![Strona konfiguracji raportowania elektronicznego](../media/er-financial-dimensions-guides-run3.png)</span><span class="sxs-lookup"><span data-stu-id="6c875-125">![ER configurations page](../media/er-financial-dimensions-guides-run3.png)</span></span>
    * <span data-ttu-id="6c875-126">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="6c875-126">Review the generated output.</span></span> <span data-ttu-id="6c875-127">Dla każdej transakcji wybranej partii są przedstawiane wymiary finansowe z odpowiedniego zestawu wymiarów.</span><span class="sxs-lookup"><span data-stu-id="6c875-127">For each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="6c875-128">Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia .</span><span class="sxs-lookup"><span data-stu-id="6c875-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  
![Strona konfiguracji raportowania elektronicznego](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]