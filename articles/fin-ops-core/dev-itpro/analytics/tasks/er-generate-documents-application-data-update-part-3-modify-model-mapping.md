---
title: Modyfikowanie modeli i mapowań w celu generowania dokumentów zawierających dane aplikacji
description: Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 2 — Generowanie dokumentów)”.
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
ms.openlocfilehash: c5df6128228b9ff620c606c550c5eb7a6039b915
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182308"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="85ece-103">Modyfikowanie modeli i mapowań w celu generowania dokumentów zawierających dane aplikacji</span><span class="sxs-lookup"><span data-stu-id="85ece-103">Modify models and mappings to generate documents that have application data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="85ece-104">Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 2: Generowanie dokumentów)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-104">To complete the steps in this procedure, you must first complete the procedure, “ER Generate documents with application data update (Part 2: Generate documents)”.</span></span> 

<span data-ttu-id="85ece-105">Etapy w tej procedurze wyjaśniają sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego i aktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="85ece-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="85ece-106">W tej procedurze zmodyfikujesz konfiguracje ER, aby zacząć ich używać do generowania dokumentów elektronicznych i aktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="85ece-106">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="85ece-107">Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="85ece-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="85ece-108">Kroki można wykonać przy użyciu zestawu danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="85ece-108">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="85ece-109">Modyfikowanie modelu danych</span><span class="sxs-lookup"><span data-stu-id="85ece-109">Modify data model</span></span>
1. <span data-ttu-id="85ece-110">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="85ece-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="85ece-111">W drzewie zaznacz element „Intrastat (model)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-111">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="85ece-112">Rozszerzysz zakres stosowania modelu danych.</span><span class="sxs-lookup"><span data-stu-id="85ece-112">You will extend how you use the data model.</span></span> <span data-ttu-id="85ece-113">Oprócz używania jako źródło danych do generowania raportu Intrastat model danych będzie również wykorzystywany do zbierania szczegółów o procesie raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="85ece-113">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="85ece-114">Szczegóły zostaną następnie użyte do zaktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="85ece-114">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="85ece-115">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="85ece-115">Click Designer.</span></span>
4. <span data-ttu-id="85ece-116">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85ece-116">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="85ece-117">W polu Nowy węzeł jako wpisz „Element główny modelu”.</span><span class="sxs-lookup"><span data-stu-id="85ece-117">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="85ece-118">W polu Nazwa wpisz „W celu aktualizacji danych aplikacji”.</span><span class="sxs-lookup"><span data-stu-id="85ece-118">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="85ece-119">W celu aktualizacji danych aplikacji</span><span class="sxs-lookup"><span data-stu-id="85ece-119">For application data update</span></span>  
7. <span data-ttu-id="85ece-120">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85ece-120">Click Add.</span></span>
8. <span data-ttu-id="85ece-121">W drzewie zaznacz element „W celu aktualizacji danych aplikacji”.</span><span class="sxs-lookup"><span data-stu-id="85ece-121">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="85ece-122">Ta nowa pozycja główna jest dodawana w celu określenia przepływu przenoszenia danych z raportu Intrastat (używanego jako źródło danych) do tabel aplikacji (lokalizacji docelowej aktualizacji).</span><span class="sxs-lookup"><span data-stu-id="85ece-122">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="85ece-123">Należy zauważyć, że muszą być stosowane różne pozycje główne do pobierania danych, które są księgowane w dokumencie wychodzącym, i do pobierania danych z dokumentu używanego do aktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="85ece-123">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="85ece-124">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85ece-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="85ece-125">W polu Nazwa wpisz „Nagłówek archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-125">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="85ece-126">Nagłówek archiwum</span><span class="sxs-lookup"><span data-stu-id="85ece-126">Archive header</span></span>  
11. <span data-ttu-id="85ece-127">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="85ece-127">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="85ece-128">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85ece-128">Click Add.</span></span>
    * <span data-ttu-id="85ece-129">Ponieważ utworzysz rekord dla każdego generowanego raportu Intrastat, należy utworzyć do tego nową pozycję.</span><span class="sxs-lookup"><span data-stu-id="85ece-129">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="85ece-130">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85ece-130">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="85ece-131">W polu Nazwa wpisz „Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="85ece-131">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="85ece-132">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="85ece-132">File name</span></span>  
15. <span data-ttu-id="85ece-133">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="85ece-133">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="85ece-134">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85ece-134">Click Add.</span></span>
17. <span data-ttu-id="85ece-135">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85ece-135">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="85ece-136">W polu Nazwa wpisz „Liczba wierszy”.</span><span class="sxs-lookup"><span data-stu-id="85ece-136">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="85ece-137">Liczba wierszy</span><span class="sxs-lookup"><span data-stu-id="85ece-137">Number of lines</span></span>  
19. <span data-ttu-id="85ece-138">W polu Typ elementu wybierz opcję „Liczba całkowita”.</span><span class="sxs-lookup"><span data-stu-id="85ece-138">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="85ece-139">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85ece-139">Click Add.</span></span>
    * <span data-ttu-id="85ece-140">Dodaj tę pozycję w celu reprezentowania liczby transakcji Intrastat, które są zgłaszane podczas bieżącego procesu raportowania.</span><span class="sxs-lookup"><span data-stu-id="85ece-140">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="85ece-141">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85ece-141">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="85ece-142">W polu Nazwa wpisz „Wiersze archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-142">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="85ece-143">Wiersze archiwum</span><span class="sxs-lookup"><span data-stu-id="85ece-143">Archive lines</span></span>  
23. <span data-ttu-id="85ece-144">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="85ece-144">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="85ece-145">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85ece-145">Click Add.</span></span>
    * <span data-ttu-id="85ece-146">Dodaj tę pozycję w celu reprezentowania listy transakcji Intrastat, które są zgłaszane podczas bieżącego procesu raportowania.</span><span class="sxs-lookup"><span data-stu-id="85ece-146">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="85ece-147">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85ece-147">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="85ece-148">W polu Nazwa wpisz „Kwota”.</span><span class="sxs-lookup"><span data-stu-id="85ece-148">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="85ece-149">Ilość</span><span class="sxs-lookup"><span data-stu-id="85ece-149">Amount</span></span>  
27. <span data-ttu-id="85ece-150">W polu Typ elementu wybierz opcję „Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="85ece-150">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="85ece-151">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85ece-151">Click Add.</span></span>
29. <span data-ttu-id="85ece-152">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85ece-152">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="85ece-153">W polu Nazwa wpisz „Identyfikator rekordu asortymentu”.</span><span class="sxs-lookup"><span data-stu-id="85ece-153">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="85ece-154">Identyfikator rekordu asortymentu</span><span class="sxs-lookup"><span data-stu-id="85ece-154">Commodity rec id</span></span>  
31. <span data-ttu-id="85ece-155">W polu Typ elementu wybierz opcję „Int64”.</span><span class="sxs-lookup"><span data-stu-id="85ece-155">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="85ece-156">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85ece-156">Click Add.</span></span>
33. <span data-ttu-id="85ece-157">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85ece-157">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="85ece-158">W polu Nazwa wpisz „Numer towaru”.</span><span class="sxs-lookup"><span data-stu-id="85ece-158">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="85ece-159">Identyfikator towaru</span><span class="sxs-lookup"><span data-stu-id="85ece-159">Item number</span></span>  
35. <span data-ttu-id="85ece-160">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="85ece-160">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="85ece-161">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85ece-161">Click Add.</span></span>
37. <span data-ttu-id="85ece-162">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85ece-162">Click Save.</span></span>
38. <span data-ttu-id="85ece-163">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85ece-163">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="85ece-164">Modyfikowanie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="85ece-164">Modify model mapping</span></span>
1. <span data-ttu-id="85ece-165">W drzewie rozwiń węzeł „Intrastat (model)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-165">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="85ece-166">W drzewie zaznacz element „Intrastat (model)\Intrastat (mapowanie)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-166">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="85ece-167">Zmodyfikuj istniejące mapowanie modelu, aby rozpocząć jego używanie do aktualizowania danych aplikacji i zarchiwizować szczegóły raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="85ece-167">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="85ece-168">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="85ece-168">Click Designer.</span></span>
4. <span data-ttu-id="85ece-169">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="85ece-169">Click New.</span></span>
5. <span data-ttu-id="85ece-170">W polu Nazwa wpisz „Aktualizacja archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-170">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="85ece-171">Aktualizacja archiwum</span><span class="sxs-lookup"><span data-stu-id="85ece-171">Update archive</span></span>  
6. <span data-ttu-id="85ece-172">W polu Kierunek wybierz opcję „Do lokalizacji docelowej”.</span><span class="sxs-lookup"><span data-stu-id="85ece-172">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="85ece-173">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85ece-173">Click Save.</span></span>
    * <span data-ttu-id="85ece-174">To nowe mapowanie określa przepływ przenoszenia danych (szczegółów raportowania Intrastat) z modelu danych do tabel aplikacji (miejsca docelowego aktualizacji).</span><span class="sxs-lookup"><span data-stu-id="85ece-174">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="85ece-175">Należy zauważyć, że należy użyć różnych pozycji głównych modelu do pobierania danych z aplikacji dla procesu raportowania, a następnie użyć danych z modelu danych do zaktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="85ece-175">Note that different model’s root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="85ece-176">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="85ece-176">Click Designer.</span></span>
9. <span data-ttu-id="85ece-177">W drzewie zaznacz element „Model danych\Model danych”.</span><span class="sxs-lookup"><span data-stu-id="85ece-177">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="85ece-178">Dodaj wymagane źródło danych.</span><span class="sxs-lookup"><span data-stu-id="85ece-178">Add the required data source.</span></span> <span data-ttu-id="85ece-179">Jest to model danych zawierający szczegóły raportowanych transakcji Intrastat, które muszą zostać zarchiwizowane.</span><span class="sxs-lookup"><span data-stu-id="85ece-179">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="85ece-180">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="85ece-180">Click Add root.</span></span>
11. <span data-ttu-id="85ece-181">W polu Nazwa wpisz „model”.</span><span class="sxs-lookup"><span data-stu-id="85ece-181">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="85ece-182">model</span><span class="sxs-lookup"><span data-stu-id="85ece-182">model</span></span>  
12. <span data-ttu-id="85ece-183">W polu Definicja wprowadź lub wybierz wartość „W celu aktualizacji danych aplikacji”.</span><span class="sxs-lookup"><span data-stu-id="85ece-183">In the Definition field, enter or select the value ‘For application data update’.</span></span>
    * <span data-ttu-id="85ece-184">W celu aktualizacji danych aplikacji</span><span class="sxs-lookup"><span data-stu-id="85ece-184">For application data update</span></span>  
13. <span data-ttu-id="85ece-185">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="85ece-185">Click OK.</span></span>
14. <span data-ttu-id="85ece-186">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="85ece-186">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="85ece-187">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="85ece-187">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="85ece-188">W drzewie zaznacz element „model\Nagłówek archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-188">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="85ece-189">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85ece-189">Click Add.</span></span>
    * <span data-ttu-id="85ece-190">Ponieważ chcesz utworzyć wartości stałotekstowe dla raportowanych transakcji Intrastat w celu zarchiwizowania, trzeba dodać odpowiednie źródło danych.</span><span class="sxs-lookup"><span data-stu-id="85ece-190">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="85ece-191">W polu Nazwa wpisz „Wiersze stałotekstowe”.</span><span class="sxs-lookup"><span data-stu-id="85ece-191">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="85ece-192">Wiersze stałotekstowe</span><span class="sxs-lookup"><span data-stu-id="85ece-192">Enumerated lines</span></span>  
19. <span data-ttu-id="85ece-193">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="85ece-193">Click Edit formula.</span></span>
20. <span data-ttu-id="85ece-194">W drzewie zaznacz element „Lista\ENUMERATE”.</span><span class="sxs-lookup"><span data-stu-id="85ece-194">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="85ece-195">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="85ece-195">Click Add function.</span></span>
22. <span data-ttu-id="85ece-196">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="85ece-196">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="85ece-197">W drzewie rozwiń węzeł „model\Nagłówek archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-197">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="85ece-198">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-198">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="85ece-199">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="85ece-199">Click Add data source.</span></span>
26. <span data-ttu-id="85ece-200">W polu Formuła wprowadź „ENUMERATE(model.'Nagłówek archiwum'.'Wiersze archiwum')”.</span><span class="sxs-lookup"><span data-stu-id="85ece-200">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="85ece-201">ENUMERATE(model.'Nagłówek archiwum'.'Wiersze archiwum')</span><span class="sxs-lookup"><span data-stu-id="85ece-201">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="85ece-202">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85ece-202">Click Save.</span></span>
28. <span data-ttu-id="85ece-203">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85ece-203">Close the page.</span></span>
29. <span data-ttu-id="85ece-204">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="85ece-204">Click OK.</span></span>
30. <span data-ttu-id="85ece-205">Kliknij opcję Dodaj lokalizację docelową.</span><span class="sxs-lookup"><span data-stu-id="85ece-205">Click Add destination.</span></span>
    * <span data-ttu-id="85ece-206">Dodaj tabele aplikacji jako obowiązkowe miejsca docelowe wymagające aktualizacji, aby archiwizować szczegóły raportowanych transakcji Intrastat.</span><span class="sxs-lookup"><span data-stu-id="85ece-206">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="85ece-207">W polu nazwa wpisz „Archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-207">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="85ece-208">Archiwizuj</span><span class="sxs-lookup"><span data-stu-id="85ece-208">Archive</span></span>  
32. <span data-ttu-id="85ece-209">W polu Nazwa tabeli wpisz „IntrastatArchiveGeneral”.</span><span class="sxs-lookup"><span data-stu-id="85ece-209">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="85ece-210">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="85ece-210">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="85ece-211">Zachowaj akcję rekordu „Wstaw”, aby móc dodawać rekordy w trakcie archiwizowania szczegółów każdego procesu raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="85ece-211">Keep the record action ‘Insert’ so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="85ece-212">W polu Dziennik informacyjny rekordu zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="85ece-212">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="85ece-213">Wybierz opcję Tak, aby uzyskać informacje o problemach z aktualizacją danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="85ece-213">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="85ece-214">W polu Pomiń weryfikację akcji rekordu wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="85ece-214">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="85ece-215">Wybierz opcję Tak, aby pomijać błędy sprawdzania poprawności o pustym polu „Identyfikator archiwum Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="85ece-215">Select Yes to suppress validation errors about the empty ‘Intrastat archive ID’ field.</span></span> <span data-ttu-id="85ece-216">Będzie się to odbywało po dodaniu rekordów na podstawie ustawień numeracji skonfigurowanych dla tej tabeli w formularzu Parametry handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="85ece-216">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="85ece-217">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="85ece-217">Click OK.</span></span>
    * <span data-ttu-id="85ece-218">Powiąż elementy dodanego źródła danych (modelu wyfiltrowanego na podstawie wybranej pozycji głównej) z elementami w dodanym miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="85ece-218">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="85ece-219">W drzewie rozwiń węzeł „Archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-219">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="85ece-220">W drzewie rozwiń węzeł „Archiwum\<Relacje”.</span><span class="sxs-lookup"><span data-stu-id="85ece-220">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="85ece-221">W drzewie rozwiń węzeł „Archiwum\<Relacje\IntrastatArchiveDetail”.</span><span class="sxs-lookup"><span data-stu-id="85ece-221">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="85ece-222">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Kwota(AmountMST)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-222">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="85ece-223">W drzewie rozwiń węzeł „model\Nagłówek archiwum\Wiersze stałotekstowe”.</span><span class="sxs-lookup"><span data-stu-id="85ece-223">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="85ece-224">W drzewie rozwiń węzeł „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość”.</span><span class="sxs-lookup"><span data-stu-id="85ece-224">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="85ece-225">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość\Kwota”.</span><span class="sxs-lookup"><span data-stu-id="85ece-225">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="85ece-226">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="85ece-226">Click Bind.</span></span>
44. <span data-ttu-id="85ece-227">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Asortyment(IntrastatCommodity)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-227">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="85ece-228">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość\Identyfikator rekordu asortymentu”.</span><span class="sxs-lookup"><span data-stu-id="85ece-228">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="85ece-229">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="85ece-229">Click Bind.</span></span>
47. <span data-ttu-id="85ece-230">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Numer towaru(ItemId)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-230">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="85ece-231">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość\Numer towaru”.</span><span class="sxs-lookup"><span data-stu-id="85ece-231">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="85ece-232">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="85ece-232">Click Bind.</span></span>
50. <span data-ttu-id="85ece-233">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Numer wiersza(LineNumber)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-233">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="85ece-234">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Numer”.</span><span class="sxs-lookup"><span data-stu-id="85ece-234">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="85ece-235">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="85ece-235">Click Bind.</span></span>
53. <span data-ttu-id="85ece-236">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail”.</span><span class="sxs-lookup"><span data-stu-id="85ece-236">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="85ece-237">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe”.</span><span class="sxs-lookup"><span data-stu-id="85ece-237">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="85ece-238">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="85ece-238">Click Bind.</span></span>
56. <span data-ttu-id="85ece-239">W drzewie zaznacz element „Archiwum\Nazwa pliku(FileName)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-239">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="85ece-240">W drzewie zaznacz element „model\Nagłówek archiwum\Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="85ece-240">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="85ece-241">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="85ece-241">Click Bind.</span></span>
59. <span data-ttu-id="85ece-242">W drzewie zaznacz element „Archiwum\Liczba wierszy(NumberOfLines)”.</span><span class="sxs-lookup"><span data-stu-id="85ece-242">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="85ece-243">W drzewie zaznacz element „model\Nagłówek archiwum\Liczba wierszy”.</span><span class="sxs-lookup"><span data-stu-id="85ece-243">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="85ece-244">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="85ece-244">Click Bind.</span></span>
62. <span data-ttu-id="85ece-245">W drzewie zaznacz element „Archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-245">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="85ece-246">W drzewie zaznacz element „model\Nagłówek archiwum”.</span><span class="sxs-lookup"><span data-stu-id="85ece-246">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="85ece-247">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="85ece-247">Click Bind.</span></span>
65. <span data-ttu-id="85ece-248">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="85ece-248">Click Save.</span></span>
66. <span data-ttu-id="85ece-249">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85ece-249">Close the page.</span></span>
67. <span data-ttu-id="85ece-250">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="85ece-250">Close the page.</span></span>

