---
title: Generowanie i uruchamianie gotowych raportów
description: Użyj tego przewodnika po zadaniach, aby generować standardowe raporty w centrali z różnych obszarów roboczych i okna Zapytania i raporty o sprzedaży dostępnego z okna Handel detaliczny i inny.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailCategoryAndProductWorkspace, RetailOrgHierarchyTreeLookup, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b42f86fc243312d18654b1a048f9dffb29afd187
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550077"
---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="2df72-103">Generowanie i uruchamianie gotowych raportów</span><span class="sxs-lookup"><span data-stu-id="2df72-103">Generate and run out of box reports</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="2df72-104">Użyj tego przewodnika po zadaniach, aby generować standardowe raporty w centrali z różnych obszarów roboczych i okna Zapytania i raporty o sprzedaży dostępnego z okna Handel detaliczny i inny.</span><span class="sxs-lookup"><span data-stu-id="2df72-104">Use this task guide to run out of box reports in headquarters from different workspaces and Inquiries & Sales reports located under Retail & Commerce.</span></span>



<span data-ttu-id="2df72-105">Dane wykorzystane do stworzenia tego nagrania pochodzą z firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="2df72-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="2df72-106">To nagranie jest przeznaczone dla roli Administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="2df72-106">This recording is intended for the System administrator role.</span></span>


## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="2df72-107">Uruchamianie raportów z obszarów roboczych</span><span class="sxs-lookup"><span data-stu-id="2df72-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="2df72-108">Wybierz kolejno opcje Handel detaliczny i inny > Produkty i kategorie > Zarządzanie kategoriami i produktami.</span><span class="sxs-lookup"><span data-stu-id="2df72-108">Go to Retail and commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="2df72-109">Kliknij strzałkę, aby rozwinąć lub zwinąć sekcję Raporty.</span><span class="sxs-lookup"><span data-stu-id="2df72-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="2df72-110">Kliknij opcję Raport najlepszych produktów.</span><span class="sxs-lookup"><span data-stu-id="2df72-110">Click Top products report.</span></span>
4. <span data-ttu-id="2df72-111">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="2df72-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="2df72-112">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="2df72-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="2df72-113">W polu Kanał kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2df72-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="2df72-114">W drzewie zaznacz element „Contoso Retail\Contoso Retail USA\Central\Houston”.</span><span class="sxs-lookup"><span data-stu-id="2df72-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="2df72-115">Pokazuje to domyślną hierarchię organizacji sieci sprzedaży na potrzeby raportowania sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2df72-115">This shows the default retail organization hierarchy for Retail reporting purpose.</span></span>   <span data-ttu-id="2df72-116">Wybierz kolejno opcje Administrowanie organizacją >Organizacje > Cele hierarchii organizacji, wybierz opcję Raportowanie sieci sprzedaży i w obszarze Przypisane hierarchie sprawdź nazwę hierarchii, dla której jest zaznaczona kolumna Domyślnie.</span><span class="sxs-lookup"><span data-stu-id="2df72-116">Go to Organization administration >Organizations >Organization hierarchy purposes and choose Retail reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span>      <span data-ttu-id="2df72-117">W danych demonstracyjnych (używanych w tym nagraniu zadania) zauważysz, że Sklepy sieci sprzedaży według regionów to domyślna hierarchia organizacyjna dla raportowania sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2df72-117">As part of demo data (used for this task recording) you would notice, Retail Stores by Region, is the default organization hierarchy for the Retail reporting purpose.</span></span>     
8. <span data-ttu-id="2df72-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2df72-118">Click OK.</span></span>
9. <span data-ttu-id="2df72-119">W polu Widok wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="2df72-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="2df72-120">W polu Przez wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="2df72-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="2df72-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2df72-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports-located-under-retail--commerce-app-link"></a><span data-ttu-id="2df72-122">Uruchamianie raportów z okna Zapytania i raporty o sprzedaży dostępnego po kliknięciu łącza aplikacji Handel detaliczny i inny</span><span class="sxs-lookup"><span data-stu-id="2df72-122">Launch reports from the inquiries and sales reports located under Retail & Commerce app link.</span></span>
1. <span data-ttu-id="2df72-123">Wybierz kolejno opcje Handel detaliczny i inny > Zapytania i raporty > Raporty sprzedaży > Raport sprzedaży w kategorii.</span><span class="sxs-lookup"><span data-stu-id="2df72-123">Go to Retail and commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="2df72-124">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="2df72-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="2df72-125">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="2df72-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="2df72-126">W polu Kanał kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2df72-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2df72-127">W drzewie zaznacz element „Contoso Retail\Contoso Retail USA\West\Seattle”.</span><span class="sxs-lookup"><span data-stu-id="2df72-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="2df72-128">Pokazuje to domyślną hierarchię organizacji sieci sprzedaży na potrzeby raportowania sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2df72-128">This shows the default retail organization hierarchy for Retail reporting purpose.</span></span>   <span data-ttu-id="2df72-129">Wybierz kolejno opcje Administrowanie organizacją >Organizacje > Cele hierarchii organizacji, wybierz opcję Raportowanie sieci sprzedaży i w obszarze Przypisane hierarchie sprawdź nazwę hierarchii, dla której jest zaznaczona kolumna Domyślnie.</span><span class="sxs-lookup"><span data-stu-id="2df72-129">Go to Organization administration >Organizations >Organization hierarchy purposes and choose Retail reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span>      <span data-ttu-id="2df72-130">W danych demonstracyjnych (używanych w tym nagraniu zadania) zauważysz, że Sklepy sieci sprzedaży według regionów to domyślna hierarchia organizacyjna dla raportowania sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2df72-130">As part of demo data (used for this task recording) you would notice, Retail Stores by Region, is the default organization hierarchy for the Retail reporting purpose.</span></span>     
6. <span data-ttu-id="2df72-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2df72-131">Click OK.</span></span>
7. <span data-ttu-id="2df72-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2df72-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="2df72-133">Eksportowanie raportów aplikacji HQ</span><span class="sxs-lookup"><span data-stu-id="2df72-133">Export an HQ reports</span></span>
1. <span data-ttu-id="2df72-134">Wybierz kolejno opcje Handel detaliczny i inny > Zapytania i raporty > Raporty sprzedaży > Raport sprzedaży organizacji.</span><span class="sxs-lookup"><span data-stu-id="2df72-134">Go to Retail and commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="2df72-135">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="2df72-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="2df72-136">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="2df72-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="2df72-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2df72-137">Click OK.</span></span>
5. <span data-ttu-id="2df72-138">Kliknij przycisk Eksportuj.</span><span class="sxs-lookup"><span data-stu-id="2df72-138">Click Export.</span></span>
6. <span data-ttu-id="2df72-139">Kliknij opcję PDF.</span><span class="sxs-lookup"><span data-stu-id="2df72-139">Click PDF.</span></span>

