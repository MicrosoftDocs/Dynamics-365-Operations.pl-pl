---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 4 — Wykonanie raportu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ae9f72df5d6ff6add4eb97836cf32509aebd511
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141978"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="c3581-103">ER Używanie wymiarów finansowych jako źródła danych (Część 4 — Wykonanie raportu)</span><span class="sxs-lookup"><span data-stu-id="c3581-103">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c3581-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="c3581-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="c3581-105">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="c3581-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="c3581-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 3: Projektowanie raportu)”.</span><span class="sxs-lookup"><span data-stu-id="c3581-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="c3581-107">Należy także skonfigurować domyślne typy dokumentów na stronie Parametry raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="c3581-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="c3581-108">Domyślne typy dokumentów również są ustawiane podczas pobierania i importowania każdej konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="c3581-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="c3581-109">Generowanie raportu</span><span class="sxs-lookup"><span data-stu-id="c3581-109">Run report</span></span>
1. <span data-ttu-id="c3581-110">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="c3581-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="c3581-111">W drzewie rozwiń węzeł „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="c3581-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="c3581-112">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu\Raport arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="c3581-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="c3581-113">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="c3581-113">Click Run.</span></span>
5. <span data-ttu-id="c3581-114">W polu Nazwa wymiaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c3581-114">In the Dimension name field, In the Dimension name field, enter or select a value..</span></span>
    * <span data-ttu-id="c3581-115">Aby zaznaczyć wszystkie wymiary w bieżącej firmie, wprowadź następujące wyrażenie: BusinessUnit;CostCenter;Dział;ItemGroup;MainAccount;Projekt</span><span class="sxs-lookup"><span data-stu-id="c3581-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="c3581-116">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="c3581-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="c3581-117">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="c3581-117">Click Filter.</span></span>
8. <span data-ttu-id="c3581-118">Zaznacz wiersz z tabelą Arkusz księgi i polem Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="c3581-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="c3581-119">W polu Kryteria wpisz wartość „00057”.</span><span class="sxs-lookup"><span data-stu-id="c3581-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="c3581-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c3581-120">Click OK.</span></span>
11. <span data-ttu-id="c3581-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c3581-121">Click OK.</span></span>
    * <span data-ttu-id="c3581-122">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="c3581-122">Review the generated output.</span></span> <span data-ttu-id="c3581-123">Należy zauważyć, że dla każdej transakcji wybranej partii są przedstawiane wymiary finansowe z odpowiedniego zestawu wymiarów.</span><span class="sxs-lookup"><span data-stu-id="c3581-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="c3581-124">Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia .</span><span class="sxs-lookup"><span data-stu-id="c3581-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  

