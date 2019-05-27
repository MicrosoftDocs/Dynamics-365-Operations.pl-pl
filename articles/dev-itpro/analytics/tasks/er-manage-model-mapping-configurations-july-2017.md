---
title: Zarządzanie mapowaniem modelu ER w oddzielnych konfiguracjach ER
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może zarządzać mapowaniami modelu raportowania elektronicznego (ER) w osobnych konfiguracjach ER.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24ca4124d190df94e7ca9ac31c2ea757fe9ff242
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551214"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a><span data-ttu-id="87606-103">Zarządzanie mapowaniem modelu ER w oddzielnych konfiguracjach ER</span><span class="sxs-lookup"><span data-stu-id="87606-103">Manage ER model mapping in separate ER configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="87606-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może zarządzać mapowaniami modelu raportowania elektronicznego (ER) w osobnych konfiguracjach ER.</span><span class="sxs-lookup"><span data-stu-id="87606-104">The following steps explain how a user assigned to the System administrator or Electronic reporting developer role can manage Electronic reporting (ER) model mappings in separate ER configurations.</span></span> <span data-ttu-id="87606-105">W tym przewodniku po zadaniu utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Aby wykonać kroki podane w tym przewodniku, należy najpierw wykonać czynności z przewodnika po zadaniu „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="87606-105">In this task guide, you will create required ER configurations for the sample company, Litware, Inc. To complete this task guide, you must first complete the steps in the task guide, “ER Create a configuration provider” and mark it as active.</span></span> 

<span data-ttu-id="87606-106">Ponieważ konfiguracje raportowania elektronicznego są współużytkowane przez firmy, można wykonać ten przewodnik po zadaniu przy użyciu zestawu danych firmowych wybranego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="87606-106">Because ER configurations are shared among companies, you can complete this task guide using the company data set of your choice.</span></span> <span data-ttu-id="87606-107">Funkcjonalność tego przewodnika po zadaniu jest dostępna po zainstalowaniu jednej z następujących poprawek: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 dla wersji Dynamics AX 7.0 lub https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 dla wersji Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="87606-107">The functionality for this task guide is available if you have installed one of the following hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 for the Dynamics AX 7.0 version or https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 for the Dynamics 365 for Operations version.</span></span>

1. <span data-ttu-id="87606-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="87606-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="87606-109">Sprawdź, czy dostawca konfiguracji przykładowej firmy „Litware, Inc.” jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="87606-109">Verify that the configuration provider for the sample company Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="87606-110">Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać czynności z przewodnika po zadaniu „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="87606-110">If you don’t see this configuration provider, you must first complete the steps in the task guide, Create a configuration provider and mark it as active.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="87606-111">Dodawanie nowej konfiguracji modelu ER</span><span class="sxs-lookup"><span data-stu-id="87606-111">Add a new ER model configuration</span></span>
1. <span data-ttu-id="87606-112">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="87606-112">Click Reporting configurations.</span></span>
    * <span data-ttu-id="87606-113">Dodaj nową konfigurację modelu.</span><span class="sxs-lookup"><span data-stu-id="87606-113">Add a new model configuration.</span></span> <span data-ttu-id="87606-114">Nazwa musi być unikatowa w drzewie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="87606-114">The name must be unique in the configurations tree.</span></span>  
2. <span data-ttu-id="87606-115">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="87606-115">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="87606-116">W polu Nazwa wpisz „Przykładowy model danych”.</span><span class="sxs-lookup"><span data-stu-id="87606-116">In the Name field, type 'Sample data model'.</span></span>
    * <span data-ttu-id="87606-117">Przykładowy model danych</span><span class="sxs-lookup"><span data-stu-id="87606-117">Sample data model</span></span>  
4. <span data-ttu-id="87606-118">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="87606-118">Click Create configuration.</span></span>
5. <span data-ttu-id="87606-119">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="87606-119">Click Designer.</span></span>
6. <span data-ttu-id="87606-120">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="87606-120">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="87606-121">W polu Nazwa wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="87606-121">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="87606-122">Element główny</span><span class="sxs-lookup"><span data-stu-id="87606-122">Root</span></span>  
8. <span data-ttu-id="87606-123">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="87606-123">Click Add.</span></span>
9. <span data-ttu-id="87606-124">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="87606-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="87606-125">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="87606-125">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="87606-126">Firma</span><span class="sxs-lookup"><span data-stu-id="87606-126">Company</span></span>  
11. <span data-ttu-id="87606-127">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="87606-127">Click Add.</span></span>
12. <span data-ttu-id="87606-128">W polu Opis wprowadź tekst opisujący podmiot prawny lub firmę, do której użytkownik jest zalogowany w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="87606-128">In the Description field, enter the text, Description of the legal entity or company in which a user logged at run-time.</span></span> 
    * <span data-ttu-id="87606-129">Opis podmiotu prawnego lub firmy, w której użytkownik był zalogowany w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="87606-129">Description of the legal entity or company in which a user logged at run-time.</span></span>  
13. <span data-ttu-id="87606-130">Kliknij opcję Odwołanie główne.</span><span class="sxs-lookup"><span data-stu-id="87606-130">Click Root reference.</span></span>
14. <span data-ttu-id="87606-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87606-131">Click OK.</span></span>
15. <span data-ttu-id="87606-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="87606-132">Click Save.</span></span>
16. <span data-ttu-id="87606-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="87606-133">Close the page.</span></span>
17. <span data-ttu-id="87606-134">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="87606-134">Click Change status.</span></span>
18. <span data-ttu-id="87606-135">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="87606-135">Click Complete.</span></span>
19. <span data-ttu-id="87606-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87606-136">Click OK.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="87606-137">Dodawanie nowej konfiguracji mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="87606-137">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="87606-138">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="87606-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="87606-139">W polu Nowy wpisz „Mapowanie modelu oparte na modelu danych Przykładowy model danych”.</span><span class="sxs-lookup"><span data-stu-id="87606-139">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
3. <span data-ttu-id="87606-140">W polu Nazwa wpisz „Przykładowe mapowanie”.</span><span class="sxs-lookup"><span data-stu-id="87606-140">In the Name field, type 'Sample mapping'.</span></span>
    * <span data-ttu-id="87606-141">Przykładowe mapowanie</span><span class="sxs-lookup"><span data-stu-id="87606-141">Sample mapping</span></span>  
4. <span data-ttu-id="87606-142">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="87606-142">Click Create configuration.</span></span>
5. <span data-ttu-id="87606-143">Rozwiń sekcję Wymagania wstępne.</span><span class="sxs-lookup"><span data-stu-id="87606-143">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="87606-144">Należy zauważyć, że grupa wymagań wstępnych Implementacje została dodana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="87606-144">Note that the Implementations prerequisites group has been added automatically.</span></span> <span data-ttu-id="87606-145">Grupa zawiera wstępnie wymagany składnik, który odwołuje się do nadrzędnej konfiguracji modelu danych i jest oznaczona jako Implementacja.</span><span class="sxs-lookup"><span data-stu-id="87606-145">The group contains the prerequisite component that refers to the parent data model configuration and is marked as Implementation.</span></span> <span data-ttu-id="87606-146">Oznacza to, że ta konfiguracja mapowania modelu Przykładowe mapowanie jest uważana za implementację modelu danych Przykładowy model danych.</span><span class="sxs-lookup"><span data-stu-id="87606-146">This means that this Sample mapping model mapping configuration is considered the implementation of the data model, Sample data model.</span></span> <span data-ttu-id="87606-147">W związku z tym ten składnik zmusi moduł ER do pobrania konfiguracji mapowania modelu Przykładowe mapowanie z repozytorium ER podczas pobierania konfiguracji modelu Przykładowy model danych.</span><span class="sxs-lookup"><span data-stu-id="87606-147">Therefore, this component will force ER to download the model mapping configuration, Sample mapping from an ER repository when the model configuration, Sample data model, is downloaded.</span></span>   
6. <span data-ttu-id="87606-148">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="87606-148">Click Designer.</span></span>
    * <span data-ttu-id="87606-149">Należy zauważyć, że utworzona konfiguracja mapowania modelu zawiera nowe puste mapowanie o takiej samej nazwie, jak utworzona konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="87606-149">Note that the created model mapping configuration contains a new blank mapping with the same name as the created configuration.</span></span> <span data-ttu-id="87606-150">Należy pamiętać, że jeśli wybrana nadrzędna konfiguracja modelu zawiera mapowania modelu, zostaną one skopiowane do nowej konfiguracji mapowania modelu.</span><span class="sxs-lookup"><span data-stu-id="87606-150">Be aware that when a selected parent model configuration contains model mappings, they will be copied to a new model mapping configuration.</span></span>   
7. <span data-ttu-id="87606-151">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="87606-151">Click Designer.</span></span>
8. <span data-ttu-id="87606-152">W drzewie zaznacz element „Dynamics 365 for Operations\Tabela”.</span><span class="sxs-lookup"><span data-stu-id="87606-152">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="87606-153">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="87606-153">Click Add root.</span></span>
10. <span data-ttu-id="87606-154">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="87606-154">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="87606-155">Firma</span><span class="sxs-lookup"><span data-stu-id="87606-155">Company</span></span>  
11. <span data-ttu-id="87606-156">W polu Tabela wpisz „CompanyInfo”.</span><span class="sxs-lookup"><span data-stu-id="87606-156">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="87606-157">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="87606-157">CompanyInfo</span></span>  
12. <span data-ttu-id="87606-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87606-158">Click OK.</span></span>
13. <span data-ttu-id="87606-159">W drzewie rozwiń węzeł „Firma”.</span><span class="sxs-lookup"><span data-stu-id="87606-159">In the tree, expand 'Company'.</span></span>
14. <span data-ttu-id="87606-160">W drzewie rozwiń węzeł „Firma\find()”.</span><span class="sxs-lookup"><span data-stu-id="87606-160">In the tree, expand 'Company\find()'.</span></span>
15. <span data-ttu-id="87606-161">W drzewie zaznacz element „Firma\find()\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="87606-161">In the tree, select 'Company\find()\Name'.</span></span>
16. <span data-ttu-id="87606-162">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="87606-162">Click Bind.</span></span>
17. <span data-ttu-id="87606-163">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="87606-163">Click Save.</span></span>
18. <span data-ttu-id="87606-164">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="87606-164">Close the page.</span></span>
19. <span data-ttu-id="87606-165">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="87606-165">Close the page.</span></span>
20. <span data-ttu-id="87606-166">W okienku akcji kliknij pozycję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="87606-166">On the Action Pane, click Configurations.</span></span>
21. <span data-ttu-id="87606-167">Kliknij opcję Parametry użytkownika.</span><span class="sxs-lookup"><span data-stu-id="87606-167">Click User parameters.</span></span>
22. <span data-ttu-id="87606-168">W polu Ustawienia uruchamiania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="87606-168">Select Yes in the Run settings field.</span></span>
23. <span data-ttu-id="87606-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87606-169">Click OK.</span></span>
24. <span data-ttu-id="87606-170">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="87606-170">Click Edit.</span></span>
25. <span data-ttu-id="87606-171">W polu Uruchom wersję roboczą wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="87606-171">Select Yes in the Run Draft field.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="87606-172">Dodawanie nowej konfiguracji formatu ER</span><span class="sxs-lookup"><span data-stu-id="87606-172">Add a new ER format configuration</span></span>
1. <span data-ttu-id="87606-173">W drzewie zaznacz element „Przykładowy model danych”.</span><span class="sxs-lookup"><span data-stu-id="87606-173">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="87606-174">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="87606-174">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="87606-175">W polu Nowy wpisz „Format oparty na modelu danych Przykładowy model danych”.</span><span class="sxs-lookup"><span data-stu-id="87606-175">In the New field, enter 'Format based on data model Sample data model'.</span></span>
4. <span data-ttu-id="87606-176">W polu Nazwa wpisz „Przykładowy format”.</span><span class="sxs-lookup"><span data-stu-id="87606-176">In the Name field, type 'Sample format'.</span></span>
    * <span data-ttu-id="87606-177">Przykładowy format</span><span class="sxs-lookup"><span data-stu-id="87606-177">Sample format</span></span>  
5. <span data-ttu-id="87606-178">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="87606-178">Click Create configuration.</span></span>
6. <span data-ttu-id="87606-179">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="87606-179">Click Designer.</span></span>
7. <span data-ttu-id="87606-180">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="87606-180">Click Add root to open the drop dialog.</span></span>
8. <span data-ttu-id="87606-181">W drzewie zaznacz element „Tekst\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="87606-181">In the tree, select 'Text\String'.</span></span>
9. <span data-ttu-id="87606-182">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87606-182">Click OK.</span></span>
10. <span data-ttu-id="87606-183">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="87606-183">Click the Mapping tab.</span></span>
11. <span data-ttu-id="87606-184">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="87606-184">In the tree, expand 'model'.</span></span>
12. <span data-ttu-id="87606-185">W drzewie zaznacz element „model\Firma”.</span><span class="sxs-lookup"><span data-stu-id="87606-185">In the tree, select 'model\Company'.</span></span>
13. <span data-ttu-id="87606-186">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="87606-186">Click Bind.</span></span>
14. <span data-ttu-id="87606-187">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="87606-187">Click Save.</span></span>
15. <span data-ttu-id="87606-188">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="87606-188">Close the page.</span></span>
    * <span data-ttu-id="87606-189">Uruchom wersję roboczą utworzonego formatu do celów testowych.</span><span class="sxs-lookup"><span data-stu-id="87606-189">Run the draft version of the created format for testing purposes.</span></span>  
16. <span data-ttu-id="87606-190">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="87606-190">Click Run.</span></span>
    * <span data-ttu-id="87606-191">Na skróconej karcie Wersja kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="87606-191">On the Versions FastTab, click Run.</span></span>  
17. <span data-ttu-id="87606-192">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87606-192">Click OK.</span></span>
    * <span data-ttu-id="87606-193">Obejrzyj wyniki dla firmy, w której jest zalogowany użytkownik uruchamiający tę konfigurację formatu.</span><span class="sxs-lookup"><span data-stu-id="87606-193">Review the output that contains the name of the company in which the user who is running this format configuration is logged into.</span></span> <span data-ttu-id="87606-194">Należy zwrócić uwagę, że ta konfiguracja formatu korzysta z utworzonej konfiguracji mapowania modelu, ponieważ jest dostępna tylko jedna konfiguracja zawierająca wymagane mapowania modelu.</span><span class="sxs-lookup"><span data-stu-id="87606-194">Note that the created model mapping configuration is used by this format configuration because there is only one configuration available that contains required model mappings.</span></span>   

## <a name="add-alternative-er-model-mapping-configuration"></a><span data-ttu-id="87606-195">Dodawanie alternatywnej konfiguracji mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="87606-195">Add alternative ER model mapping configuration</span></span>
1. <span data-ttu-id="87606-196">W drzewie zaznacz element „Przykładowy model danych”.</span><span class="sxs-lookup"><span data-stu-id="87606-196">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="87606-197">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="87606-197">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="87606-198">W polu Nowy wpisz „Mapowanie modelu oparte na modelu danych Przykładowy model danych”.</span><span class="sxs-lookup"><span data-stu-id="87606-198">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
4. <span data-ttu-id="87606-199">W polu Nazwa wpisz „Przykładowe mapowanie (alternatywne)”.</span><span class="sxs-lookup"><span data-stu-id="87606-199">In the Name field, type 'Sample mapping (alternative)'.</span></span>
    * <span data-ttu-id="87606-200">Przykładowe mapowanie (alternatywne)</span><span class="sxs-lookup"><span data-stu-id="87606-200">Sample mapping (alternative)</span></span>  
5. <span data-ttu-id="87606-201">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="87606-201">Click Create configuration.</span></span>
6. <span data-ttu-id="87606-202">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="87606-202">Click Designer.</span></span>
7. <span data-ttu-id="87606-203">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="87606-203">Click Designer.</span></span>
8. <span data-ttu-id="87606-204">W drzewie zaznacz element „Dynamics 365 for Operations\Tabela”.</span><span class="sxs-lookup"><span data-stu-id="87606-204">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="87606-205">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="87606-205">Click Add root.</span></span>
10. <span data-ttu-id="87606-206">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="87606-206">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="87606-207">Firma</span><span class="sxs-lookup"><span data-stu-id="87606-207">Company</span></span>  
11. <span data-ttu-id="87606-208">W polu Tabela wpisz „CompanyInfo”.</span><span class="sxs-lookup"><span data-stu-id="87606-208">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="87606-209">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="87606-209">CompanyInfo</span></span>  
12. <span data-ttu-id="87606-210">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87606-210">Click OK.</span></span>
13. <span data-ttu-id="87606-211">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="87606-211">Click Edit.</span></span>
14. <span data-ttu-id="87606-212">W drzewie zaznacz element „Ciąg\ZŁĄCZ”.</span><span class="sxs-lookup"><span data-stu-id="87606-212">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="87606-213">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="87606-213">Click Add function.</span></span>
16. <span data-ttu-id="87606-214">W drzewie rozwiń węzeł „Firma”.</span><span class="sxs-lookup"><span data-stu-id="87606-214">In the tree, expand 'Company'.</span></span>
17. <span data-ttu-id="87606-215">W drzewie rozwiń węzeł „Firma\find()”.</span><span class="sxs-lookup"><span data-stu-id="87606-215">In the tree, expand 'Company\find()'.</span></span>
18. <span data-ttu-id="87606-216">W drzewie zaznacz element „Firma\find()\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="87606-216">In the tree, select 'Company\find()\Name'.</span></span>
19. <span data-ttu-id="87606-217">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="87606-217">Click Add data source.</span></span>
20. <span data-ttu-id="87606-218">W polu Formuła wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="87606-218">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="87606-219">CONCATENATE(Firma.'find()'.Nazwa, ";",</span><span class="sxs-lookup"><span data-stu-id="87606-219">CONCATENATE(Company.'find()'.Name, ";",</span></span>  
21. <span data-ttu-id="87606-220">W drzewie zaznacz element „Firma\find()\Firma(DataArea)”.</span><span class="sxs-lookup"><span data-stu-id="87606-220">In the tree, select 'Company\find()\Company(DataArea)'.</span></span>
22. <span data-ttu-id="87606-221">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="87606-221">Click Add data source.</span></span>
23. <span data-ttu-id="87606-222">W polu Formuła wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="87606-222">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="87606-223">CONCATENATE(Firma.'find()'.Nazwa, ";", Firma.'find()'.DataArea)</span><span class="sxs-lookup"><span data-stu-id="87606-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span></span>  
24. <span data-ttu-id="87606-224">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="87606-224">Click Save.</span></span>
25. <span data-ttu-id="87606-225">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="87606-225">Close the page.</span></span>
26. <span data-ttu-id="87606-226">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="87606-226">Click Save.</span></span>
27. <span data-ttu-id="87606-227">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="87606-227">Close the page.</span></span>
28. <span data-ttu-id="87606-228">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="87606-228">Close the page.</span></span>
29. <span data-ttu-id="87606-229">W polu Uruchom wersję roboczą wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="87606-229">Select Yes in the Run Draft field.</span></span>

## <a name="use-an-existing-er-model-mapping-configuration"></a><span data-ttu-id="87606-230">Używanie istniejącej konfiguracji mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="87606-230">Use an existing ER model mapping configuration</span></span>
1. <span data-ttu-id="87606-231">W drzewie zaznacz element „Przykładowy model danych\Przykładowy format”.</span><span class="sxs-lookup"><span data-stu-id="87606-231">In the tree, select 'Sample data model\Sample format'.</span></span>
2. <span data-ttu-id="87606-232">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="87606-232">Click Run.</span></span>
    * <span data-ttu-id="87606-233">Należy pamiętać, że wybrana wersja robocza konfiguracji formatu ER nie może zostać wykonana, ponieważ więcej niż jedna konfiguracja mapowania modelu jest dostępna dla zdefiniowanego modelu danych wybranego jako źródło danych przy uruchamianiu formatu raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="87606-233">Note that the selected draft version of the ER format configuration can’t be executed because there is more than one model mapping configuration available for the undefined data model that has been selected as the data source of the running ER format.</span></span>   
    * <span data-ttu-id="87606-234">Następnie zdefiniujesz alternatywną konfigurację mapowania modelu jako tę, z której mapowania modelu będą wykorzystywane jako źródła danych dla uruchamiania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="87606-234">Next, you will define the alternative model mapping configuration as the one from which model mappings will be used as data sources for running ER format.</span></span>   
3. <span data-ttu-id="87606-235">W drzewie zaznacz element „Przykładowy model danych\Przykładowe mapowanie (alternatywne)”.</span><span class="sxs-lookup"><span data-stu-id="87606-235">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
4. <span data-ttu-id="87606-236">Wybierz opcję Tak w polu Domyślne dla mapowania modelu.</span><span class="sxs-lookup"><span data-stu-id="87606-236">Select Yes in the Default for model mapping field.</span></span>
5. <span data-ttu-id="87606-237">W drzewie zaznacz element „Przykładowy model danych\Przykładowy format”.</span><span class="sxs-lookup"><span data-stu-id="87606-237">In the tree, select 'Sample data model\Sample format'.</span></span>
6. <span data-ttu-id="87606-238">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="87606-238">Click Run.</span></span>
7. <span data-ttu-id="87606-239">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="87606-239">Click OK.</span></span>
    * <span data-ttu-id="87606-240">Należy zwrócić uwagę, że domyślna konfiguracja mapowania modelu jest używana przez tę konfigurację formatu do generowania dokumentu elektronicznego (utworzony produkt wyjściowy zawiera kod firmy).</span><span class="sxs-lookup"><span data-stu-id="87606-240">Note that the default model mapping configuration is used by this format configuration for generating the electronic document (the created output contains the company code).</span></span>  

