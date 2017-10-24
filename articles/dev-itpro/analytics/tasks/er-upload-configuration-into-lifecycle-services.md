--- 
title: "Przekazywanie konfiguracji do usługi Lifecycle Services na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfiguracji raportowania elektronicznego (ER) i przekazać ją do usługi Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
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
ms.openlocfilehash: d24679a380ec824fe08c56aacb4bc348ff40440a
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="upload-a-configuration-into-lifecycle-services-for-electronic-reporting-er"></a><span data-ttu-id="caeba-103">Przekazywanie konfiguracji do usługi Lifecycle Services na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="caeba-103">Upload a configuration into Lifecycle Services for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="caeba-104">W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfiguracji raportowania elektronicznego (ER) i przekazać ją do usługi Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="caeba-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration and upload it into Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="caeba-105">W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. i przekażesz ją do usługi LCS. Podane kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="caeba-105">In this example, you will create a configuration and upload it to LCS for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="caeba-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="caeba-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="caeba-107">W celu wykonania tych kroków jest również wymagany dostęp do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="caeba-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="caeba-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="caeba-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="caeba-109">Wybierz firmę „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="caeba-109">Select ‘Litware, Inc.’</span></span> <span data-ttu-id="caeba-110">i ustaw ją jako aktywną.</span><span class="sxs-lookup"><span data-stu-id="caeba-110">and set it as active.</span></span>
3. <span data-ttu-id="caeba-111">Kliknij opcję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="caeba-111">Click Configurations.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="caeba-112">Tworzenie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="caeba-112">Create a new data model configuration</span></span>
1. <span data-ttu-id="caeba-113">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="caeba-113">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="caeba-114">Utworzysz konfigurację, która zawiera przykładowy model danych dla dokumentów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="caeba-114">You will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="caeba-115">Ta konfiguracja modelu danych zostanie później przekazana do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="caeba-115">This data model configuration will be uploaded into LCS later.</span></span>  
2. <span data-ttu-id="caeba-116">W polu Nazwa wpisz „Konfiguracja przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="caeba-116">In the Name field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="caeba-117">Konfiguracja przykładowego modelu</span><span class="sxs-lookup"><span data-stu-id="caeba-117">Sample model configuration</span></span>  
3. <span data-ttu-id="caeba-118">W polu Opis wpisz „Konfiguracja przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="caeba-118">In the Description field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="caeba-119">Konfiguracja przykładowego modelu</span><span class="sxs-lookup"><span data-stu-id="caeba-119">Sample model configuration</span></span>  
4. <span data-ttu-id="caeba-120">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="caeba-120">Click Create configuration.</span></span>
5. <span data-ttu-id="caeba-121">Kliknij opcję Projektant modeli.</span><span class="sxs-lookup"><span data-stu-id="caeba-121">Click Model designer.</span></span>
6. <span data-ttu-id="caeba-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="caeba-122">Click New.</span></span>
7. <span data-ttu-id="caeba-123">W polu Nazwa wpisz „Punkt wejścia”.</span><span class="sxs-lookup"><span data-stu-id="caeba-123">In the Name field, type 'Entry point'.</span></span>
    * <span data-ttu-id="caeba-124">Punkt wejścia</span><span class="sxs-lookup"><span data-stu-id="caeba-124">Entry point</span></span>  
8. <span data-ttu-id="caeba-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="caeba-125">Click Add.</span></span>
9. <span data-ttu-id="caeba-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="caeba-126">Click Save.</span></span>
10. <span data-ttu-id="caeba-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="caeba-127">Close the page.</span></span>
11. <span data-ttu-id="caeba-128">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="caeba-128">Click Change status.</span></span>
12. <span data-ttu-id="caeba-129">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="caeba-129">Click Complete.</span></span>
13. <span data-ttu-id="caeba-130">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="caeba-130">Click OK.</span></span>

## <a name="register-a-new--repository"></a><span data-ttu-id="caeba-131">Rejestrowanie nowego repozytorium</span><span class="sxs-lookup"><span data-stu-id="caeba-131">Register a new  repository</span></span>
1. <span data-ttu-id="caeba-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="caeba-132">Close the page.</span></span>
2. <span data-ttu-id="caeba-133">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="caeba-133">Click Repositories.</span></span>
    * <span data-ttu-id="caeba-134">Dzięki temu można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="caeba-134">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
3. <span data-ttu-id="caeba-135">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="caeba-135">Click Add to open the drop dialog.</span></span>
    * <span data-ttu-id="caeba-136">Dzięki temu można dodać nowe repozytorium.</span><span class="sxs-lookup"><span data-stu-id="caeba-136">This allows you to add a new repository.</span></span>  
4. <span data-ttu-id="caeba-137">W polu Typ repozytorium konfiguracji zaznacz usługę LCS.</span><span class="sxs-lookup"><span data-stu-id="caeba-137">In the Configuration repository type field, select LCS.</span></span>
5. <span data-ttu-id="caeba-138">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="caeba-138">Click Create repository.</span></span>
6. <span data-ttu-id="caeba-139">W polu Projekt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="caeba-139">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="caeba-140">Wybierz żądany projekt usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="caeba-140">Select the desired LCS project.</span></span> <span data-ttu-id="caeba-141">Trzeba mieć dostęp do projektu.</span><span class="sxs-lookup"><span data-stu-id="caeba-141">You must have access to the project.</span></span>  
7. <span data-ttu-id="caeba-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="caeba-142">Click OK.</span></span>
    * <span data-ttu-id="caeba-143">Wypełnij wpis nowego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="caeba-143">Complete a new repository entry.</span></span>  
8. <span data-ttu-id="caeba-144">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="caeba-144">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="caeba-145">Wybierz rekord repozytorium usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="caeba-145">Select the LCS repository record.</span></span>  
    * <span data-ttu-id="caeba-146">Należy zwrócić uwagę, że zarejestrowane repozytorium jest oznaczone przez bieżącego dostawcę, co oznacza, że tylko konfiguracje posiadane przez tego dostawcę mogą być umieszczane w tym repozytorium i w związku z tym przekazywane do wybranego projektu usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="caeba-146">Note that a registered repository is marked by the current provider meaning that the only configurations owned by that provider can be placed to this repository and, consequently, uploaded into the selected LCS project.</span></span>  
9. <span data-ttu-id="caeba-147">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="caeba-147">Click Open.</span></span>
    * <span data-ttu-id="caeba-148">Otwórz repozytorium, aby wyświetlić listę konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="caeba-148">Open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="caeba-149">Będzie ona pusta, jeśli ten projekt nie był jeszcze używany w udostępnianiu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="caeba-149">It will be empty if this project has not yet been used for ER configurations sharing.</span></span>  
10. <span data-ttu-id="caeba-150">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="caeba-150">Close the page.</span></span>
11. <span data-ttu-id="caeba-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="caeba-151">Close the page.</span></span>

## <a name="upload-configuration-into-lcs"></a><span data-ttu-id="caeba-152">Przekazywanie konfiguracji do usługi LCS</span><span class="sxs-lookup"><span data-stu-id="caeba-152">Upload configuration into LCS</span></span>
1. <span data-ttu-id="caeba-153">Kliknij opcję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="caeba-153">Click Configurations.</span></span>
2. <span data-ttu-id="caeba-154">W drzewie zaznacz element „Konfiguracja przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="caeba-154">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="caeba-155">Zaznacz utworzone konfiguracje, które zostały już ukończone.</span><span class="sxs-lookup"><span data-stu-id="caeba-155">Select a created configuration that has been already completed.</span></span>  
3. <span data-ttu-id="caeba-156">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="caeba-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="caeba-157">Zaznacz wersję wybranej konfiguracji ze stanem „Zakończono”.</span><span class="sxs-lookup"><span data-stu-id="caeba-157">Select the version of the selected configuration with the status of ‘Completed’.</span></span>  
4. <span data-ttu-id="caeba-158">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="caeba-158">Click Change status.</span></span>
5. <span data-ttu-id="caeba-159">Kliknij przycisk Udostępnij.</span><span class="sxs-lookup"><span data-stu-id="caeba-159">Click Share.</span></span>
    * <span data-ttu-id="caeba-160">Po opublikowaniu konfiguracji w usłudze LCS stan konfiguracji ulegnie zmianie z „Zakończono” na „Udostępniono”.</span><span class="sxs-lookup"><span data-stu-id="caeba-160">The configuration status will change from ‘Completed’ to ‘Shared’ when it is published in LCS.</span></span>  
6. <span data-ttu-id="caeba-161">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="caeba-161">Click OK.</span></span>
7. <span data-ttu-id="caeba-162">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="caeba-162">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="caeba-163">Zaznacz wersję konfiguracji o stanie „Udostępniono”.</span><span class="sxs-lookup"><span data-stu-id="caeba-163">Select the configuration version with the status of 'Shared'.</span></span>  
    * <span data-ttu-id="caeba-164">Należy zauważyć, że stan wybranej wersji został zmieniony z „Zakończono” na „Udostępniono”.</span><span class="sxs-lookup"><span data-stu-id="caeba-164">Note that the status of the selected version has changed from ‘Completed’ to ‘Shared’.</span></span>  
8. <span data-ttu-id="caeba-165">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="caeba-165">Close the page.</span></span>
9. <span data-ttu-id="caeba-166">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="caeba-166">Click Repositories.</span></span>
    * <span data-ttu-id="caeba-167">Dzięki temu można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="caeba-167">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
10. <span data-ttu-id="caeba-168">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="caeba-168">Click Open.</span></span>
    * <span data-ttu-id="caeba-169">Zaznacz repozytorium usługi LCS i je otwórz.</span><span class="sxs-lookup"><span data-stu-id="caeba-169">Select the LCS repository and open it.</span></span>  
    * <span data-ttu-id="caeba-170">Należy zwrócić uwagę, że wybrana konfiguracja jest wyświetlana jako element zawartości wybranego projektu usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="caeba-170">Note that the selected configuration is shown as an asset of the selected LCS project.</span></span>  
    * <span data-ttu-id="caeba-171">Otwórz usługę LCS ze strony https://lcs.dynamics.com. Otwórz projekt, który został wcześniej użyty do zarejestrowania repozytorium, otwórz bibliotekę elementów zawartości tego projektu, a następnie rozwiń zawartość elementu zawartości typu „Konfiguracja GER” — przekazana konfiguracja raportowania elektronicznego będzie dostępna.</span><span class="sxs-lookup"><span data-stu-id="caeba-171">Open LCS using https://lcs.dynamics.com. Open a project that was used earlier for repository registration, open the ‘Asset library’ of this project, and expand the content of the ‘GER configuration’ asset type – the uploaded ER configuration will be available.</span></span> <span data-ttu-id="caeba-172">Należy zauważyć, że przekazaną konfigurację usługi LCS można zaimportować do innego wystąpienia programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, jeśli dostawcy mają dostęp do tego projektu usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="caeba-172">Note that the uploaded LCS configuration can be imported to another Microsoft Dynamics 365 for Finance and Operations, Enterprise edition instance if providers have access to this LCS project.</span></span>  


