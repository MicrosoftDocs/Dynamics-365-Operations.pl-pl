---
title: Tworzenie konfiguracji mapowania modeli raportowania elektronicznego (ER)
description: Ta procedura umożliwia zaprojektowanie nowego mapowania modelu raportowania elektronicznego (ER) i zastosowanie wbudowanych funkcji ER w celu efektywnego obliczania agregacji.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c52f5d23f6c1cdad346a8a5e94535a4cba19057
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562887"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a><span data-ttu-id="ddd6a-103">Tworzenie konfiguracji mapowania modeli raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="ddd6a-103">Create Electronic reporting (ER) model mapping configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ddd6a-104">Ta procedura umożliwia zaprojektowanie nowego mapowania modelu raportowania elektronicznego (ER) i zastosowanie wbudowanych funkcji ER w celu efektywnego obliczania agregacji.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-104">Use this procedure to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="ddd6a-105">Ta procedura dotyczy tworzenia konfiguracji dla przykładowej firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-105">In this procedure, you will create a configuration for sample company, Litware, Inc.</span></span> 

<span data-ttu-id="ddd6a-106">Procedura ta została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-106">This procedure is created for uses with the assigned role of System administrator or Electronic reporting developer.</span></span>

<span data-ttu-id="ddd6a-107">Kroki te można wykonać przy użyciu dowolnego zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-107">These steps can be completed using any dataset.</span></span> <span data-ttu-id="ddd6a-108">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-108">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>

1. <span data-ttu-id="ddd6a-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="ddd6a-110">Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="ddd6a-111">Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-111">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>  
2. <span data-ttu-id="ddd6a-112">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="ddd6a-113">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-113">Click Show filters.</span></span>
4. <span data-ttu-id="ddd6a-114">W polu „Nazwa” wprowadź wartość filtra „Intrastat” i użyj operatora filtra „zaczyna się od”.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-114">In the "Name" field, enter the filter value, "Intrastat" and use the filter operator "begins with".</span></span>
    * <span data-ttu-id="ddd6a-115">Zastosowanie tego filtra pozwala znaleźć konfigurację modelu danych „Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-115">Apply this filter to find the 'Intrastat' data model configuration.</span></span> <span data-ttu-id="ddd6a-116">Model ten może już istnieć w drzewie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-116">This model may already exist in the configurations tree.</span></span> <span data-ttu-id="ddd6a-117">Jeśli tak, przejdź do kolejnego podzadania.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-117">If it does, skip the next sub-task.</span></span>   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a><span data-ttu-id="ddd6a-118">Pobieranie konfiguracji modelu Intrastat dostarczanej przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="ddd6a-118">Get the Intrastat model configuration provided by Microsoft</span></span>
1. <span data-ttu-id="ddd6a-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-119">Close the page.</span></span>
2. <span data-ttu-id="ddd6a-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-120">Close the page.</span></span>
3. <span data-ttu-id="ddd6a-121">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-121">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
4. <span data-ttu-id="ddd6a-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ddd6a-123">Wybierz kafelek dostawcy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-123">Select the Microsoft provider tile.</span></span>  
5. <span data-ttu-id="ddd6a-124">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-124">Click Repositories.</span></span>
    * <span data-ttu-id="ddd6a-125">Kliknij opcję Repozytoria na kafelku dostawcy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-125">Click Repositories in the Microsoft provider tile.</span></span>  
6. <span data-ttu-id="ddd6a-126">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-126">Click Show filters.</span></span>
7. <span data-ttu-id="ddd6a-127">W polu „Nazwa typu” wprowadź wartość filtra „zasoby” i użyj operatora filtra „zawiera”.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-127">In the "Type name" field, enter the filter value, "resources" and use the filter operator "contains".</span></span> 
8. <span data-ttu-id="ddd6a-128">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-128">Click Open.</span></span>
9. <span data-ttu-id="ddd6a-129">W drzewie zaznacz element „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-129">In the tree, select 'Intrastat model'.</span></span>
10. <span data-ttu-id="ddd6a-130">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-130">Click Import.</span></span>
11. <span data-ttu-id="ddd6a-131">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-131">Click Yes.</span></span>
    * <span data-ttu-id="ddd6a-132">Zaimportowana została konfiguracja modelu ER zawierająca model danych, który można teraz wykorzystać do sprawdzenia działania nowych funkcji ER.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-132">You imported the ER model configuration that contains the data model that you will use to explore how the new ER functionality can be used.</span></span>  
12. <span data-ttu-id="ddd6a-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-133">Close the page.</span></span>
13. <span data-ttu-id="ddd6a-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-134">Close the page.</span></span>
14. <span data-ttu-id="ddd6a-135">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-135">Click Reporting configurations.</span></span>

## <a name="add-a-new-model-mapping-configuration"></a><span data-ttu-id="ddd6a-136">Dodawanie nowej konfiguracji mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="ddd6a-136">Add a new model mapping configuration</span></span>
1. <span data-ttu-id="ddd6a-137">W drzewie zaznacz element „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-137">In the tree, select 'Intrastat model'.</span></span>
2. <span data-ttu-id="ddd6a-138">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-138">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="ddd6a-139">W polu Nowy wpisz „Mapowanie modelu oparte na modelu danych Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-139">In the New field, enter 'Model Mapping based on data model Intrastat'.</span></span>
4. <span data-ttu-id="ddd6a-140">W polu Nazwa wpisz „Przykładowe mapowanie Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-140">In the Name field, type 'Intrastat sample mapping'.</span></span>
    * <span data-ttu-id="ddd6a-141">Przykładowe mapowanie Intrastat</span><span class="sxs-lookup"><span data-stu-id="ddd6a-141">Intrastat sample mapping</span></span>  
5. <span data-ttu-id="ddd6a-142">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="ddd6a-142">Click Create configuration.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]