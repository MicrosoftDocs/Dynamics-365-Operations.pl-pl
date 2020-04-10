---
title: ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 2 — Inicjowanie formatu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może skonfigurować format raportowania elektronicznego (ER) do generowania raportów jako plików arkuszy OPENXML(Excel), w których wymagane kolumny mogą być tworzone dynamicznie jako poziomo rozszerzalne zakresy.
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
ms.openlocfilehash: 66c2a97a068ed83f93699f14e827bdc2fb580d93
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141840"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a><span data-ttu-id="b3a0b-103">ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 2 — Inicjowanie formatu)</span><span class="sxs-lookup"><span data-stu-id="b3a0b-103">ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 2 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b3a0b-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może skonfigurować format raportowania elektronicznego (ER) do generowania raportów jako plików arkuszy OPENXML(Excel), w których wymagane kolumny mogą być tworzone dynamicznie jako poziomo rozszerzalne zakresy.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="b3a0b-105">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="b3a0b-106">Aby wykonać te kroki, należy najpierw wykonać kroki procedury „ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 1: Projektowanie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-106">To complete these steps, you must first complete the steps in the "ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)" procedure.</span></span>

<span data-ttu-id="b3a0b-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="b3a0b-108">Znajdowanie utworzonego formatu</span><span class="sxs-lookup"><span data-stu-id="b3a0b-108">Find created format</span></span>
1. <span data-ttu-id="b3a0b-109">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="b3a0b-110">W drzewie rozwiń węzeł „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-110">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="b3a0b-111">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu\Przykładowy raport z poziomo rozszerzalnymi zakresami”.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-111">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="b3a0b-112">Wykonanie formatu w celu utworzenia danych wyjściowych programu Excel</span><span class="sxs-lookup"><span data-stu-id="b3a0b-112">Execute format to create Excel output</span></span>
1. <span data-ttu-id="b3a0b-113">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-113">Click Run.</span></span>
2. <span data-ttu-id="b3a0b-114">W polu Nazwa wymiaru wpisz „BusinessUnit;CostCenter;Dział”.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-114">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="b3a0b-115">Wprowadź lub wybierz wartość w polu Nazwa wymiaru.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-115">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="b3a0b-116">Aby zaznaczyć wszystkie wymiary w bieżącej firmie, wprowadź następujące wyrażenie: BusinessUnit;CostCenter;Dział;ItemGroup;MainAccount;Projekt</span><span class="sxs-lookup"><span data-stu-id="b3a0b-116">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="b3a0b-117">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-117">Expand the Records to include section.</span></span>
4. <span data-ttu-id="b3a0b-118">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-118">Click Filter.</span></span>
5. <span data-ttu-id="b3a0b-119">Zaznacz wiersz z tabelą Arkusz księgi i polem Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-119">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="b3a0b-120">W polu Kryteria wpisz wartość „00057..00058”.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-120">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="b3a0b-121">00057..00058</span><span class="sxs-lookup"><span data-stu-id="b3a0b-121">00057..00058</span></span>  
7. <span data-ttu-id="b3a0b-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-122">Click OK.</span></span>
8. <span data-ttu-id="b3a0b-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-123">Click OK.</span></span>
    * <span data-ttu-id="b3a0b-124">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-124">Review the generated output.</span></span> <span data-ttu-id="b3a0b-125">Należy zauważyć, że nowo utworzony plik programu Excel zawiera taką samą liczbę kolumn, jak wybrana dla wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-125">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="b3a0b-126">Nagłówek raportu w tych kolumnach reprezentuje nazwy wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-126">The report header in those columns represents financial dimensions' names.</span></span> <span data-ttu-id="b3a0b-127">Wiersze transakcji w tych kolumnach reprezentują wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="b3a0b-127">The transactions' lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="b3a0b-128">Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia .</span><span class="sxs-lookup"><span data-stu-id="b3a0b-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  

