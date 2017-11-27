--- 
title: "Tworzenie formatu służącego do zliczania i sumowania na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.sourcegitcommit: 5d4f57ae2a309d9e15c1afe60c3e91d7d7eb3870
ms.openlocfilehash: 3c4ae958a03d4681a85f5b83d81fe64b9ac99cf5
ms.contentlocale: pl-pl
ms.lasthandoff: 11/02/2017

---
# <a name="create-format-for-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="3b6c7-103">Tworzenie formatu służącego do zliczania i sumowania na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="3b6c7-103">Create format for counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b6c7-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="3b6c7-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="3b6c7-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="3b6c7-107">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="3b6c7-108">Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b6c7-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="3b6c7-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="3b6c7-110">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="3b6c7-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="3b6c7-111">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="3b6c7-112">Zaznacz dostawcę „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="3b6c7-113"> </span><span class="sxs-lookup"><span data-stu-id="3b6c7-113">provider.</span></span>
3. <span data-ttu-id="3b6c7-114">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-114">Click Repositories.</span></span>
    * <span data-ttu-id="3b6c7-115">Jeśli repozytorium typu „Zasoby operacyjne” już istnieje, należy pominąć pozostałe kroki bieżącego zadania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="3b6c7-116">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="3b6c7-117">W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="3b6c7-118">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-118">Click Create repository.</span></span>
7. <span data-ttu-id="3b6c7-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="3b6c7-120">Pobieranie konfiguracji Intrastat dostarczanych przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b6c7-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="3b6c7-121">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-121">Click Open.</span></span>
2. <span data-ttu-id="3b6c7-122">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="3b6c7-123">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-123">Click Import.</span></span>
    * <span data-ttu-id="3b6c7-124">Kliknij przycisk Importuj dla wersji 1.1 wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="3b6c7-125">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-125">Click Yes.</span></span>
5. <span data-ttu-id="3b6c7-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-126">Close the page.</span></span>
6. <span data-ttu-id="3b6c7-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-127">Close the page.</span></span>
7. <span data-ttu-id="3b6c7-128">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="3b6c7-129">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="3b6c7-130">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="3b6c7-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>


