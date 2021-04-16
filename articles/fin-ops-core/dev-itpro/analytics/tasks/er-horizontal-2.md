---
title: ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 2 — Inicjowanie formatu)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego w celu generowania raportów jako plików arkuszy OPENXML (Excel). (część 2)
author: NickSelin
ms.date: 08/29/2018
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
ms.openlocfilehash: a62bad6ca241a2372a72e312ec5a707008a5fc09
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744994"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a><span data-ttu-id="f01ab-104">ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 2 — Inicjowanie formatu)</span><span class="sxs-lookup"><span data-stu-id="f01ab-104">ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 2 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f01ab-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może skonfigurować format raportowania elektronicznego (ER) do generowania raportów jako plików arkuszy OPENXML(Excel), w których wymagane kolumny mogą być tworzone dynamicznie jako poziomo rozszerzalne zakresy.</span><span class="sxs-lookup"><span data-stu-id="f01ab-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="f01ab-106">Kroki można wykonać na danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="f01ab-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="f01ab-107">Aby wykonać te kroki, należy najpierw wykonać kroki procedury „ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 1: Projektowanie formatu)”.</span><span class="sxs-lookup"><span data-stu-id="f01ab-107">To complete these steps, you must first complete the steps in the "ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)" procedure.</span></span>

<span data-ttu-id="f01ab-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="f01ab-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="f01ab-109">Znajdowanie utworzonego formatu</span><span class="sxs-lookup"><span data-stu-id="f01ab-109">Find created format</span></span>
1. <span data-ttu-id="f01ab-110">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="f01ab-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f01ab-111">W drzewie rozwiń węzeł „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="f01ab-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="f01ab-112">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu\Przykładowy raport z poziomo rozszerzalnymi zakresami”.</span><span class="sxs-lookup"><span data-stu-id="f01ab-112">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="f01ab-113">Wykonanie formatu w celu utworzenia danych wyjściowych programu Excel</span><span class="sxs-lookup"><span data-stu-id="f01ab-113">Execute format to create Excel output</span></span>
1. <span data-ttu-id="f01ab-114">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="f01ab-114">Click Run.</span></span>
2. <span data-ttu-id="f01ab-115">W polu Nazwa wymiaru wpisz „BusinessUnit;CostCenter;Dział”.</span><span class="sxs-lookup"><span data-stu-id="f01ab-115">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="f01ab-116">Wprowadź lub wybierz wartość w polu Nazwa wymiaru.</span><span class="sxs-lookup"><span data-stu-id="f01ab-116">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="f01ab-117">Aby zaznaczyć wszystkie wymiary w bieżącej firmie, wprowadź następujące wyrażenie: BusinessUnit;CostCenter;Dział;ItemGroup;MainAccount;Projekt</span><span class="sxs-lookup"><span data-stu-id="f01ab-117">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="f01ab-118">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="f01ab-118">Expand the Records to include section.</span></span>
4. <span data-ttu-id="f01ab-119">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="f01ab-119">Click Filter.</span></span>
5. <span data-ttu-id="f01ab-120">Zaznacz wiersz z tabelą Arkusz księgi i polem Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="f01ab-120">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="f01ab-121">W polu Kryteria wpisz wartość „00057..00058”.</span><span class="sxs-lookup"><span data-stu-id="f01ab-121">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="f01ab-122">00057..00058</span><span class="sxs-lookup"><span data-stu-id="f01ab-122">00057..00058</span></span>  
7. <span data-ttu-id="f01ab-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f01ab-123">Click OK.</span></span>
8. <span data-ttu-id="f01ab-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f01ab-124">Click OK.</span></span>
    * <span data-ttu-id="f01ab-125">Przejrzyj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="f01ab-125">Review the generated output.</span></span> <span data-ttu-id="f01ab-126">Należy zauważyć, że nowo utworzony plik programu Excel zawiera taką samą liczbę kolumn, jak wybrana dla wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="f01ab-126">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="f01ab-127">Nagłówek raportu w tych kolumnach reprezentuje nazwy wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="f01ab-127">The report header in those columns represents financial dimensions' names.</span></span> <span data-ttu-id="f01ab-128">Wiersze transakcji w tych kolumnach reprezentują wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="f01ab-128">The transactions' lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="f01ab-129">Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia .</span><span class="sxs-lookup"><span data-stu-id="f01ab-129">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]