--- 
title: "Uruchamianie raportu, w którym wymiary finansowe są używane jako źródła danych na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: cdecf5fb3f3047a56353ee6d4a8f94957f508e4b
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="run-a-report-that-uses-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="435b7-103">Uruchamianie raportu, w którym wymiary finansowe są używane jako źródła danych na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="435b7-103">Run a report that uses financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="435b7-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="435b7-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="435b7-105">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="435b7-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="435b7-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 3: Projektowanie raportu)”.</span><span class="sxs-lookup"><span data-stu-id="435b7-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="435b7-107">Należy także skonfigurować domyślne typy dokumentów na stronie Parametry raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="435b7-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="435b7-108">Domyślne typy dokumentów również są ustawiane podczas pobierania i importowania każdej konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="435b7-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="435b7-109">Generowanie raportu</span><span class="sxs-lookup"><span data-stu-id="435b7-109">Run report</span></span>
1. <span data-ttu-id="435b7-110">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="435b7-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="435b7-111">W drzewie rozwiń węzeł „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="435b7-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="435b7-112">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu\Raport arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="435b7-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="435b7-113">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="435b7-113">Click Run.</span></span>
5. <span data-ttu-id="435b7-114">W polu Nazwa wymiaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="435b7-114">In the Dimension name field, In the Dimension name field, enter or select a value..</span></span>
    * <span data-ttu-id="435b7-115">Aby zaznaczyć wszystkie wymiary w bieżącej firmie, wprowadź następujące wyrażenie: BusinessUnit;CostCenter;Dział;ItemGroup;MainAccount;Projekt</span><span class="sxs-lookup"><span data-stu-id="435b7-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="435b7-116">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="435b7-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="435b7-117">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="435b7-117">Click Filter.</span></span>
8. <span data-ttu-id="435b7-118">Zaznacz wiersz z tabelą Arkusz księgi i polem Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="435b7-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="435b7-119">W polu Kryteria wpisz wartość „00057”.</span><span class="sxs-lookup"><span data-stu-id="435b7-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="435b7-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="435b7-120">Click OK.</span></span>
11. <span data-ttu-id="435b7-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="435b7-121">Click OK.</span></span>
    * <span data-ttu-id="435b7-122">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="435b7-122">Review the generated output.</span></span> <span data-ttu-id="435b7-123">Należy zauważyć, że dla każdej transakcji wybranej partii są przedstawiane wymiary finansowe z odpowiedniego zestawu wymiarów.</span><span class="sxs-lookup"><span data-stu-id="435b7-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="435b7-124">Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia programu Dynamics 365 for Finance and Operations Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="435b7-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  


