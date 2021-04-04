---
title: Modyfikowanie modeli i mapowań w celu generowania dokumentów zawierających dane aplikacji
description: W tym temacie opisano sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego i aktualizowania danych aplikacji. (część 2 — generowanie dokumentów).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64bcf885fe2f5fca6b91589171b5e539eff2c3e5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567099"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="f1b5a-104">Modyfikowanie modeli i mapowań w celu generowania dokumentów zawierających dane aplikacji</span><span class="sxs-lookup"><span data-stu-id="f1b5a-104">Modify models and mappings to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f1b5a-105">Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 2: Generowanie dokumentów)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-105">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 2: Generate documents)".</span></span> 

<span data-ttu-id="f1b5a-106">Etapy w tej procedurze wyjaśniają sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego i aktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="f1b5a-107">W tej procedurze zmodyfikujesz konfiguracje ER, aby zacząć ich używać do generowania dokumentów elektronicznych i aktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-107">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="f1b5a-108">Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="f1b5a-109">Kroki można wykonać przy użyciu zestawu danych firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-109">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="f1b5a-110">Modyfikowanie modelu danych</span><span class="sxs-lookup"><span data-stu-id="f1b5a-110">Modify data model</span></span>
1. <span data-ttu-id="f1b5a-111">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f1b5a-112">W drzewie zaznacz element „Intrastat (model)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-112">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="f1b5a-113">Rozszerzysz zakres stosowania modelu danych.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-113">You will extend how you use the data model.</span></span> <span data-ttu-id="f1b5a-114">Oprócz używania jako źródło danych do generowania raportu Intrastat model danych będzie również wykorzystywany do zbierania szczegółów o procesie raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-114">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="f1b5a-115">Szczegóły zostaną następnie użyte do zaktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-115">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="f1b5a-116">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-116">Click Designer.</span></span>
4. <span data-ttu-id="f1b5a-117">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-117">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="f1b5a-118">W polu Nowy węzeł jako wpisz „Element główny modelu”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-118">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="f1b5a-119">W polu Nazwa wpisz „W celu aktualizacji danych aplikacji”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-119">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="f1b5a-120">W celu aktualizacji danych aplikacji</span><span class="sxs-lookup"><span data-stu-id="f1b5a-120">For application data update</span></span>  
7. <span data-ttu-id="f1b5a-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-121">Click Add.</span></span>
8. <span data-ttu-id="f1b5a-122">W drzewie zaznacz element „W celu aktualizacji danych aplikacji”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-122">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="f1b5a-123">Ta nowa pozycja główna jest dodawana w celu określenia przepływu przenoszenia danych z raportu Intrastat (używanego jako źródło danych) do tabel aplikacji (lokalizacji docelowej aktualizacji).</span><span class="sxs-lookup"><span data-stu-id="f1b5a-123">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="f1b5a-124">Należy zauważyć, że muszą być stosowane różne pozycje główne do pobierania danych, które są księgowane w dokumencie wychodzącym, i do pobierania danych z dokumentu używanego do aktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-124">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="f1b5a-125">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-125">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="f1b5a-126">W polu Nazwa wpisz „Nagłówek archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-126">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="f1b5a-127">Nagłówek archiwum</span><span class="sxs-lookup"><span data-stu-id="f1b5a-127">Archive header</span></span>  
11. <span data-ttu-id="f1b5a-128">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-128">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="f1b5a-129">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-129">Click Add.</span></span>
    * <span data-ttu-id="f1b5a-130">Ponieważ utworzysz rekord dla każdego generowanego raportu Intrastat, należy utworzyć do tego nową pozycję.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-130">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="f1b5a-131">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-131">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="f1b5a-132">W polu Nazwa wpisz „Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-132">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="f1b5a-133">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="f1b5a-133">File name</span></span>  
15. <span data-ttu-id="f1b5a-134">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-134">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="f1b5a-135">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-135">Click Add.</span></span>
17. <span data-ttu-id="f1b5a-136">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-136">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="f1b5a-137">W polu Nazwa wpisz „Liczba wierszy”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-137">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="f1b5a-138">Liczba wierszy</span><span class="sxs-lookup"><span data-stu-id="f1b5a-138">Number of lines</span></span>  
19. <span data-ttu-id="f1b5a-139">W polu Typ elementu wybierz opcję „Liczba całkowita”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-139">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="f1b5a-140">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-140">Click Add.</span></span>
    * <span data-ttu-id="f1b5a-141">Dodaj tę pozycję w celu reprezentowania liczby transakcji Intrastat, które są zgłaszane podczas bieżącego procesu raportowania.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-141">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="f1b5a-142">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-142">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="f1b5a-143">W polu Nazwa wpisz „Wiersze archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-143">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="f1b5a-144">Wiersze archiwum</span><span class="sxs-lookup"><span data-stu-id="f1b5a-144">Archive lines</span></span>  
23. <span data-ttu-id="f1b5a-145">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-145">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="f1b5a-146">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-146">Click Add.</span></span>
    * <span data-ttu-id="f1b5a-147">Dodaj tę pozycję w celu reprezentowania listy transakcji Intrastat, które są zgłaszane podczas bieżącego procesu raportowania.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-147">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="f1b5a-148">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-148">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="f1b5a-149">W polu Nazwa wpisz „Kwota”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-149">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="f1b5a-150">Ilość</span><span class="sxs-lookup"><span data-stu-id="f1b5a-150">Amount</span></span>  
27. <span data-ttu-id="f1b5a-151">W polu Typ elementu wybierz opcję „Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-151">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="f1b5a-152">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-152">Click Add.</span></span>
29. <span data-ttu-id="f1b5a-153">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-153">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="f1b5a-154">W polu Nazwa wpisz „Identyfikator rekordu asortymentu”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-154">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="f1b5a-155">Identyfikator rekordu asortymentu</span><span class="sxs-lookup"><span data-stu-id="f1b5a-155">Commodity rec id</span></span>  
31. <span data-ttu-id="f1b5a-156">W polu Typ elementu wybierz opcję „Int64”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-156">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="f1b5a-157">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-157">Click Add.</span></span>
33. <span data-ttu-id="f1b5a-158">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-158">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="f1b5a-159">W polu Nazwa wpisz „Numer towaru”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-159">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="f1b5a-160">Identyfikator towaru</span><span class="sxs-lookup"><span data-stu-id="f1b5a-160">Item number</span></span>  
35. <span data-ttu-id="f1b5a-161">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-161">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="f1b5a-162">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-162">Click Add.</span></span>
37. <span data-ttu-id="f1b5a-163">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-163">Click Save.</span></span>
38. <span data-ttu-id="f1b5a-164">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-164">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="f1b5a-165">Modyfikowanie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="f1b5a-165">Modify model mapping</span></span>
1. <span data-ttu-id="f1b5a-166">W drzewie rozwiń węzeł „Intrastat (model)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-166">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="f1b5a-167">W drzewie zaznacz element „Intrastat (model)\Intrastat (mapowanie)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-167">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="f1b5a-168">Zmodyfikuj istniejące mapowanie modelu, aby rozpocząć jego używanie do aktualizowania danych aplikacji i zarchiwizować szczegóły raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-168">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="f1b5a-169">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-169">Click Designer.</span></span>
4. <span data-ttu-id="f1b5a-170">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-170">Click New.</span></span>
5. <span data-ttu-id="f1b5a-171">W polu Nazwa wpisz „Aktualizacja archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-171">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="f1b5a-172">Aktualizacja archiwum</span><span class="sxs-lookup"><span data-stu-id="f1b5a-172">Update archive</span></span>  
6. <span data-ttu-id="f1b5a-173">W polu Kierunek wybierz opcję „Do lokalizacji docelowej”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-173">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="f1b5a-174">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-174">Click Save.</span></span>
    * <span data-ttu-id="f1b5a-175">To nowe mapowanie określa przepływ przenoszenia danych (szczegółów raportowania Intrastat) z modelu danych do tabel aplikacji (miejsca docelowego aktualizacji).</span><span class="sxs-lookup"><span data-stu-id="f1b5a-175">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="f1b5a-176">Należy zauważyć, że należy użyć różnych pozycji głównych modelu do pobierania danych z aplikacji dla procesu raportowania, a następnie użyć danych z modelu danych do zaktualizowania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-176">Note that different model's root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="f1b5a-177">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-177">Click Designer.</span></span>
9. <span data-ttu-id="f1b5a-178">W drzewie zaznacz element „Model danych\Model danych”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-178">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="f1b5a-179">Dodaj wymagane źródło danych.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-179">Add the required data source.</span></span> <span data-ttu-id="f1b5a-180">Jest to model danych zawierający szczegóły raportowanych transakcji Intrastat, które muszą zostać zarchiwizowane.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-180">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="f1b5a-181">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-181">Click Add root.</span></span>
11. <span data-ttu-id="f1b5a-182">W polu Nazwa wpisz „model”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-182">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="f1b5a-183">model</span><span class="sxs-lookup"><span data-stu-id="f1b5a-183">model</span></span>  
12. <span data-ttu-id="f1b5a-184">W polu Definicja wprowadź lub wybierz wartość „W celu aktualizacji danych aplikacji”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-184">In the Definition field, enter or select the value 'For application data update'.</span></span>
    * <span data-ttu-id="f1b5a-185">W celu aktualizacji danych aplikacji</span><span class="sxs-lookup"><span data-stu-id="f1b5a-185">For application data update</span></span>  
13. <span data-ttu-id="f1b5a-186">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-186">Click OK.</span></span>
14. <span data-ttu-id="f1b5a-187">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="f1b5a-187">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="f1b5a-188">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-188">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="f1b5a-189">W drzewie zaznacz element „model\Nagłówek archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-189">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="f1b5a-190">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-190">Click Add.</span></span>
    * <span data-ttu-id="f1b5a-191">Ponieważ chcesz utworzyć wartości stałotekstowe dla raportowanych transakcji Intrastat w celu zarchiwizowania, trzeba dodać odpowiednie źródło danych.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-191">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="f1b5a-192">W polu Nazwa wpisz „Wiersze stałotekstowe”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-192">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="f1b5a-193">Wiersze stałotekstowe</span><span class="sxs-lookup"><span data-stu-id="f1b5a-193">Enumerated lines</span></span>  
19. <span data-ttu-id="f1b5a-194">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-194">Click Edit formula.</span></span>
20. <span data-ttu-id="f1b5a-195">W drzewie zaznacz element „Lista\ENUMERATE”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-195">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="f1b5a-196">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-196">Click Add function.</span></span>
22. <span data-ttu-id="f1b5a-197">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="f1b5a-197">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="f1b5a-198">W drzewie rozwiń węzeł „model\Nagłówek archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-198">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="f1b5a-199">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-199">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="f1b5a-200">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-200">Click Add data source.</span></span>
26. <span data-ttu-id="f1b5a-201">W polu Formuła wprowadź „ENUMERATE(model.'Nagłówek archiwum'.'Wiersze archiwum')”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-201">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="f1b5a-202">ENUMERATE(model.'Nagłówek archiwum'.'Wiersze archiwum')</span><span class="sxs-lookup"><span data-stu-id="f1b5a-202">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="f1b5a-203">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-203">Click Save.</span></span>
28. <span data-ttu-id="f1b5a-204">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-204">Close the page.</span></span>
29. <span data-ttu-id="f1b5a-205">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-205">Click OK.</span></span>
30. <span data-ttu-id="f1b5a-206">Kliknij opcję Dodaj lokalizację docelową.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-206">Click Add destination.</span></span>
    * <span data-ttu-id="f1b5a-207">Dodaj tabele aplikacji jako obowiązkowe miejsca docelowe wymagające aktualizacji, aby archiwizować szczegóły raportowanych transakcji Intrastat.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-207">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="f1b5a-208">W polu nazwa wpisz „Archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-208">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="f1b5a-209">Archiwizuj</span><span class="sxs-lookup"><span data-stu-id="f1b5a-209">Archive</span></span>  
32. <span data-ttu-id="f1b5a-210">W polu Nazwa tabeli wpisz „IntrastatArchiveGeneral”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-210">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="f1b5a-211">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="f1b5a-211">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="f1b5a-212">Zachowaj akcję rekordu „Wstaw”, aby móc dodawać rekordy w trakcie archiwizowania szczegółów każdego procesu raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-212">Keep the record action 'Insert' so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="f1b5a-213">W polu Dziennik informacyjny rekordu zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-213">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="f1b5a-214">Wybierz opcję Tak, aby uzyskać informacje o problemach z aktualizacją danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-214">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="f1b5a-215">W polu Pomiń weryfikację akcji rekordu wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-215">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="f1b5a-216">Wybierz opcję Tak, aby pomijać błędy sprawdzania poprawności o pustym polu „Identyfikator archiwum Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-216">Select Yes to suppress validation errors about the empty 'Intrastat archive ID' field.</span></span> <span data-ttu-id="f1b5a-217">Będzie się to odbywało po dodaniu rekordów na podstawie ustawień numeracji skonfigurowanych dla tej tabeli w formularzu Parametry handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-217">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="f1b5a-218">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-218">Click OK.</span></span>
    * <span data-ttu-id="f1b5a-219">Powiąż elementy dodanego źródła danych (modelu wyfiltrowanego na podstawie wybranej pozycji głównej) z elementami w dodanym miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-219">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="f1b5a-220">W drzewie rozwiń węzeł „Archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-220">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="f1b5a-221">W drzewie rozwiń węzeł „Archiwum\<Relacje”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-221">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="f1b5a-222">W drzewie rozwiń węzeł „Archiwum\<Relacje\IntrastatArchiveDetail”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-222">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="f1b5a-223">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Kwota(AmountMST)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-223">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="f1b5a-224">W drzewie rozwiń węzeł „model\Nagłówek archiwum\Wiersze stałotekstowe”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-224">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="f1b5a-225">W drzewie rozwiń węzeł „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-225">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="f1b5a-226">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość\Kwota”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-226">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="f1b5a-227">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-227">Click Bind.</span></span>
44. <span data-ttu-id="f1b5a-228">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Asortyment(IntrastatCommodity)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-228">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="f1b5a-229">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość\Identyfikator rekordu asortymentu”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-229">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="f1b5a-230">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-230">Click Bind.</span></span>
47. <span data-ttu-id="f1b5a-231">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Numer towaru(ItemId)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-231">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="f1b5a-232">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość\Numer towaru”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-232">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="f1b5a-233">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-233">Click Bind.</span></span>
50. <span data-ttu-id="f1b5a-234">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Numer wiersza(LineNumber)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-234">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="f1b5a-235">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Numer”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-235">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="f1b5a-236">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-236">Click Bind.</span></span>
53. <span data-ttu-id="f1b5a-237">W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-237">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="f1b5a-238">W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-238">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="f1b5a-239">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-239">Click Bind.</span></span>
56. <span data-ttu-id="f1b5a-240">W drzewie zaznacz element „Archiwum\Nazwa pliku(FileName)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-240">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="f1b5a-241">W drzewie zaznacz element „model\Nagłówek archiwum\Nazwa pliku”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-241">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="f1b5a-242">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-242">Click Bind.</span></span>
59. <span data-ttu-id="f1b5a-243">W drzewie zaznacz element „Archiwum\Liczba wierszy(NumberOfLines)”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-243">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="f1b5a-244">W drzewie zaznacz element „model\Nagłówek archiwum\Liczba wierszy”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-244">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="f1b5a-245">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-245">Click Bind.</span></span>
62. <span data-ttu-id="f1b5a-246">W drzewie zaznacz element „Archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-246">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="f1b5a-247">W drzewie zaznacz element „model\Nagłówek archiwum”.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-247">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="f1b5a-248">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-248">Click Bind.</span></span>
65. <span data-ttu-id="f1b5a-249">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-249">Click Save.</span></span>
66. <span data-ttu-id="f1b5a-250">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-250">Close the page.</span></span>
67. <span data-ttu-id="f1b5a-251">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f1b5a-251">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]