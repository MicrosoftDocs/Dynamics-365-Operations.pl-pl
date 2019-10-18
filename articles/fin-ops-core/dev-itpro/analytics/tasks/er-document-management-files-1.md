---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1 — Przygotowanie modelu danych)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d3bd01f7aa1ef95230c37458a5676111a5efa23c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182561"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1-prepare-data-model"></a><span data-ttu-id="fa660-103">ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1: Przygotowanie modelu danych)</span><span class="sxs-lookup"><span data-stu-id="fa660-103">ER Use Document Management files in format outputs (Part 1: Prepare data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fa660-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).</span><span class="sxs-lookup"><span data-stu-id="fa660-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="fa660-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="fa660-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="fa660-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="fa660-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="fa660-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="fa660-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="fa660-108">Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa660-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="fa660-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="fa660-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="fa660-110">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="fa660-110">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="fa660-111">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="fa660-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="fa660-112">Zaznacz dostawcę „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="fa660-112">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="fa660-113"> </span><span class="sxs-lookup"><span data-stu-id="fa660-113">provider.</span></span>
3. <span data-ttu-id="fa660-114">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="fa660-114">Click Repositories.</span></span>
    * <span data-ttu-id="fa660-115">Jeśli repozytorium typu „Zasoby operacyjne” już istnieje, należy pominąć pozostałe kroki bieżącego zadania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="fa660-115">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="fa660-116">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="fa660-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="fa660-117">W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.</span><span class="sxs-lookup"><span data-stu-id="fa660-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="fa660-118">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="fa660-118">Click Create repository.</span></span>
7. <span data-ttu-id="fa660-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="fa660-119">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="fa660-120">Pobieranie konfiguracje modelu faktur sprzedaży dostarczonych przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa660-120">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="fa660-121">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="fa660-121">Click Show filters.</span></span>
2. <span data-ttu-id="fa660-122">Zastosuj następujące filtry: w polu „Nazwa” wprowadź wartość filtru „Zasoby operacyjne”, używając operatora filtru „zaczyna się od”; w polu „Opis” wprowadź wartość filtru "", używając operatora filtru „zaczyna się od”</span><span class="sxs-lookup"><span data-stu-id="fa660-122">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="fa660-123">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="fa660-123">Click Show filters.</span></span>
4. <span data-ttu-id="fa660-124">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="fa660-124">Click Open.</span></span>
5. <span data-ttu-id="fa660-125">W drzewie zaznacz element „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="fa660-125">In the tree, select 'Customer invoice model'.</span></span>
    * <span data-ttu-id="fa660-126">Zaznacz konfigurację modelu „Model faktur sprzedaży”, aby ją zaimportować.</span><span class="sxs-lookup"><span data-stu-id="fa660-126">Select the model configuration 'Customer invoice model' to import it.</span></span>  
6. <span data-ttu-id="fa660-127">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="fa660-127">Click Import.</span></span>
    * <span data-ttu-id="fa660-128">Kliknij przycisk Importuj dla wersji 1 wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="fa660-128">Click Import for version 1 of the selected configuration.</span></span>  
7. <span data-ttu-id="fa660-129">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="fa660-129">Click Yes.</span></span>
8. <span data-ttu-id="fa660-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fa660-130">Close the page.</span></span>
9. <span data-ttu-id="fa660-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fa660-131">Close the page.</span></span>
10. <span data-ttu-id="fa660-132">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="fa660-132">Click Reporting configurations.</span></span>
11. <span data-ttu-id="fa660-133">W drzewie zaznacz element „Model faktur sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="fa660-133">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="fa660-134">Utwórz pochodny model w celu umożliwienia dostępu do plików zarządzania dokumentami.</span><span class="sxs-lookup"><span data-stu-id="fa660-134">Create the derived model to support access to the Document Management files.</span></span>
    * <span data-ttu-id="fa660-135">Utworzysz własną konfigurację modelu faktur sprzedaży na podstawie konfiguracji dostarczonej przez firmę Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa660-135">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="fa660-136">Użyjesz tej konfiguracji w celu zaimplementowania dostępu do plików zarządzania dokumentami oraz udostępnienia ich dla dokumentów elektronicznych, które zostaną utworzone na podstawie tego modelu.</span><span class="sxs-lookup"><span data-stu-id="fa660-136">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="fa660-137">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="fa660-137">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="fa660-138">W polu Nowy wprowadź wyrażenie „Pochodzi od nazwy: Model faktur sprzedaży, Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="fa660-138">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="fa660-139">W polu Nazwa wpisz „Model faktur sprzedaży (niestandardowy)”.</span><span class="sxs-lookup"><span data-stu-id="fa660-139">In the Name field, type 'Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="fa660-140">Model faktur sprzedaży (niestandardowy)</span><span class="sxs-lookup"><span data-stu-id="fa660-140">Customer invoice model (custom)</span></span>  
4. <span data-ttu-id="fa660-141">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="fa660-141">Click Create configuration.</span></span>

