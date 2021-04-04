---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1 — Przygotowanie modelu danych)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego (ER) do używania plików zarządzania dokumentami (załączników) w danych wyjściowych ER. (część 1)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35bffd6d3688a9887fcdaf4edbd89c344cb9b18d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559804"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a><span data-ttu-id="ff8f1-104">ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1 — Przygotowanie modelu danych)</span><span class="sxs-lookup"><span data-stu-id="ff8f1-104">ER Use Document Management files in format outputs (Part 1 - Prepare data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ff8f1-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="ff8f1-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="ff8f1-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="ff8f1-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="ff8f1-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="ff8f1-109">Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="ff8f1-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="ff8f1-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="ff8f1-111">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="ff8f1-111">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="ff8f1-112">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-112">provider is available and marked as active.</span></span>  

2. <span data-ttu-id="ff8f1-113">Zaznacz dostawcę „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-113">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="ff8f1-114"> </span><span class="sxs-lookup"><span data-stu-id="ff8f1-114">provider.</span></span>
3. <span data-ttu-id="ff8f1-115">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-115">Click Repositories.</span></span>

    <span data-ttu-id="ff8f1-116">Jeśli repozytorium typu „Zasoby operacyjne” już istnieje, należy pominąć pozostałe kroki bieżącego zadania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-116">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  

4. <span data-ttu-id="ff8f1-117">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="ff8f1-118">W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="ff8f1-119">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-119">Click Create repository.</span></span>
7. <span data-ttu-id="ff8f1-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-120">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="ff8f1-121">Pobieranie konfiguracje modelu faktur sprzedaży dostarczonych przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="ff8f1-121">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="ff8f1-122">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-122">Click Show filters.</span></span>
2. <span data-ttu-id="ff8f1-123">Zastosuj następujące filtry: w polu „Nazwa” wprowadź wartość filtru „Zasoby operacyjne”, używając operatora filtru „zaczyna się od”; w polu „Opis” wprowadź wartość filtru "", używając operatora filtru „zaczyna się od”</span><span class="sxs-lookup"><span data-stu-id="ff8f1-123">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="ff8f1-124">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-124">Click Show filters.</span></span>
4. <span data-ttu-id="ff8f1-125">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-125">Click Open.</span></span>
5. <span data-ttu-id="ff8f1-126">W drzewie zaznacz element „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-126">In the tree, select 'Customer invoice model'.</span></span>

    <span data-ttu-id="ff8f1-127">Zaznacz konfigurację modelu „Model faktur sprzedaży”, aby ją zaimportować.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-127">Select the model configuration 'Customer invoice model' to import it.</span></span>  

6. <span data-ttu-id="ff8f1-128">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-128">Click Import.</span></span>

    <span data-ttu-id="ff8f1-129">Kliknij przycisk Importuj dla wersji 1 wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-129">Click Import for version 1 of the selected configuration.</span></span>  

7. <span data-ttu-id="ff8f1-130">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-130">Click Yes.</span></span>
8. <span data-ttu-id="ff8f1-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-131">Close the page.</span></span>
9. <span data-ttu-id="ff8f1-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-132">Close the page.</span></span>
10. <span data-ttu-id="ff8f1-133">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-133">Click Reporting configurations.</span></span>
11. <span data-ttu-id="ff8f1-134">W drzewie zaznacz element „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-134">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="ff8f1-135">Utwórz pochodny model w celu umożliwienia dostępu do plików zarządzania dokumentami.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-135">Create the derived model to support access to the Document Management files.</span></span>
<span data-ttu-id="ff8f1-136">Utworzysz własną konfigurację modelu faktur sprzedaży na podstawie konfiguracji dostarczonej przez firmę Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-136">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="ff8f1-137">Użyjesz tej konfiguracji w celu zaimplementowania dostępu do plików zarządzania dokumentami oraz udostępnienia ich dla dokumentów elektronicznych, które zostaną utworzone na podstawie tego modelu.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-137">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="ff8f1-138">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="ff8f1-139">W polu Nowy wprowadź wyrażenie „Pochodzi od nazwy: Model faktur sprzedaży, Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-139">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="ff8f1-140">W polu Nazwa wpisz „Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-140">In the Name field, type 'Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="ff8f1-141">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="ff8f1-141">Click Create configuration.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]