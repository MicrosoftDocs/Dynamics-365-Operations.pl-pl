---
title: Projektowanie konfiguracji służących do generowania raportów w formatach pakietu Office z osadzonymi obrazami
description: W tym temacie opisano sposób projektowania konfiguracji generujących dokumenty elektroniczne w formatach programów Excel i Word z osadzonymi obrazami.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5eea178a351716425706f481ae66c5b5183a52e5
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944564"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="1e6b7-103">Projektowanie konfiguracji służących do generowania raportów w formatach pakietu Office z osadzonymi obrazami</span><span class="sxs-lookup"><span data-stu-id="1e6b7-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e6b7-104">Aby wykonać kroki podane w tej procedurze, należy najpierw wykonać procedurę „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="1e6b7-105">W tej procedurze wyjaśniono sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentów programów Microsoft Excel i Word zawierających osadzone obrazy.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="1e6b7-106">W tej procedurze utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Kroki można wykonać przy użyciu zestawu danych firmy USMF.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="1e6b7-107">Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="1e6b7-108">Przed rozpoczęciem musisz pobrać i zapisać następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="1e6b7-108">Before you begin, download and save the following files:</span></span> 

| <span data-ttu-id="1e6b7-109">opis</span><span class="sxs-lookup"><span data-stu-id="1e6b7-109">Description</span></span>                                          | <span data-ttu-id="1e6b7-110">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="1e6b7-110">File name</span></span>                   |
|------------------------------------------------------|-----------------------------|
| <span data-ttu-id="1e6b7-111">Konfiguracja modelu danych ER</span><span class="sxs-lookup"><span data-stu-id="1e6b7-111">ER data model configuration</span></span>                          | [<span data-ttu-id="1e6b7-112">Model czeków.xml</span><span class="sxs-lookup"><span data-stu-id="1e6b7-112">Model for cheques.xml</span></span>](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| <span data-ttu-id="1e6b7-113">ER format konfiguracji</span><span class="sxs-lookup"><span data-stu-id="1e6b7-113">ER format configuration</span></span>                              | [<span data-ttu-id="1e6b7-114">Format drukowania czeków.xml</span><span class="sxs-lookup"><span data-stu-id="1e6b7-114">Cheques printing format.xml</span></span>](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| <span data-ttu-id="1e6b7-115">Obraz logo firmy</span><span class="sxs-lookup"><span data-stu-id="1e6b7-115">Company logo image</span></span>                                   | [<span data-ttu-id="1e6b7-116">Logo firmy.png</span><span class="sxs-lookup"><span data-stu-id="1e6b7-116">Company logo.png</span></span>](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| <span data-ttu-id="1e6b7-117">Obraz podpisu</span><span class="sxs-lookup"><span data-stu-id="1e6b7-117">Signature image</span></span>                                      | [<span data-ttu-id="1e6b7-118">Obraz podpisu.png</span><span class="sxs-lookup"><span data-stu-id="1e6b7-118">Signature image.png</span></span>](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| <span data-ttu-id="1e6b7-119">Alternatywny obraz podpisu</span><span class="sxs-lookup"><span data-stu-id="1e6b7-119">Alternative signature image</span></span>                          | [<span data-ttu-id="1e6b7-120">Obraz podpisu 2.png</span><span class="sxs-lookup"><span data-stu-id="1e6b7-120">Signature image 2.png</span></span>](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| <span data-ttu-id="1e6b7-121">Szablon programu Microsoft Word do drukowania czeków płatności</span><span class="sxs-lookup"><span data-stu-id="1e6b7-121">Microsoft Word template for printing payment checks</span></span>  | [<span data-ttu-id="1e6b7-122">Szablon czeku Word.docx</span><span class="sxs-lookup"><span data-stu-id="1e6b7-122">Cheque template Word.docx</span></span>](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a><span data-ttu-id="1e6b7-123">Sprawdzanie wymagań</span><span class="sxs-lookup"><span data-stu-id="1e6b7-123">Verify prerequisites</span></span>  
 1. <span data-ttu-id="1e6b7-124">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-124">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="1e6b7-125">Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-125">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="1e6b7-126">Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-126">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="1e6b7-127">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-127">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="1e6b7-128">Dodawanie nowej konfiguracji modelu ER</span><span class="sxs-lookup"><span data-stu-id="1e6b7-128">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="1e6b7-129">Zamiast tworzyć nowy model, można załadować plik konfiguracji modelu ER (Model for cheques.xml), który został wcześniej zapisany.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-129">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="1e6b7-130">Plik ten zawiera przykładowy model danych dla czeków płatniczych i mapowanie modelu danych do składników danych aplikacji Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-130">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="1e6b7-131">Na skróconej karcie Wersje kliknij przycisk Import/eksport.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-131">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="1e6b7-132">Kliknij opcję Załaduj z pliku XML.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-132">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="1e6b7-133">Kliknij przycisk Przeglądaj, a następnie wybierz plik Model for cheques.xml.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-133">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="1e6b7-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-134">Click OK.</span></span>  
 6. <span data-ttu-id="1e6b7-135">Załadowany model zostanie użyty jako źródło danych informacji do generowania dokumentów, które zawierają obrazy w programie Excel i Word.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-135">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="1e6b7-136">Dodawanie nowej konfiguracji formatu ER</span><span class="sxs-lookup"><span data-stu-id="1e6b7-136">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="1e6b7-137">Zamiast tworzyć nowy format można załadować plik konfiguracji formatu ER (Cheques printing format.xml), który został wcześniej zapisany.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-137">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="1e6b7-138">Ten plik zawiera przykładowy układ formatu do drukowania czeków przy użyciu wstępnie zadrukowanego formularza i mapowanie tego formatu do modelu danych „Model czeków”.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-138">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="1e6b7-139">Kliknij opcję Import/eksport.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-139">Click Exchange.</span></span>  
 3. <span data-ttu-id="1e6b7-140">Kliknij opcję Załaduj z pliku XML.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-140">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="1e6b7-141">Kliknij przycisk Przeglądaj i wybierz plik Cheques printing format.xml.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-141">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="1e6b7-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-142">Click OK.</span></span>  
 6. <span data-ttu-id="1e6b7-143">W drzewie rozwiń węzeł „Model czeków”.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-143">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="1e6b7-144">W drzewie zaznacz element „Model czeków\Format drukowania czeków”.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-144">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="1e6b7-145">Załadowany format zostanie użyty do generowania dokumentów, które zawierają obrazy w programie Excel i Word.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-145">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="1e6b7-146">Konfigurowanie parametrów użytkownika modułu ER</span><span class="sxs-lookup"><span data-stu-id="1e6b7-146">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="1e6b7-147">W okienku akcji kliknij pozycję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-147">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="1e6b7-148">Kliknij opcję Parametry użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-148">Click User parameters.</span></span>  
 3. <span data-ttu-id="1e6b7-149">W polu Ustawienia uruchamiania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-149">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="1e6b7-150">Włącz flagę „Uruchom wersję roboczą”, aby uruchomić wersję roboczą wybranego formatu zamiast wersji ukończonej.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-150">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="1e6b7-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-151">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="1e6b7-152">Konfigurowanie parametrów modułu Zarządzanie gotówką i bankami</span><span class="sxs-lookup"><span data-stu-id="1e6b7-152">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="1e6b7-153">Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-153">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="1e6b7-154">Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „USMF OPER”.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-154">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="1e6b7-155">W okienku akcji kliknij pozycję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-155">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="1e6b7-156">Kliknij przycisk Sprawdź.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-156">Click Check.</span></span>  
 5. <span data-ttu-id="1e6b7-157">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-157">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="1e6b7-158">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-158">Click Edit.</span></span>  
 7. <span data-ttu-id="1e6b7-159">W polu Logo firmy wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-159">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="1e6b7-160">Kliknij Logo firmy.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-160">Click Company logo.</span></span>  
 9. <span data-ttu-id="1e6b7-161">Kliknij przycisk Zmień.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-161">Click Change.</span></span>  
 10. <span data-ttu-id="1e6b7-162">Kliknij przycisk Przeglądaj i wybierz pobrany wcześniej plik Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-162">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="1e6b7-163">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-163">Click Save.</span></span>  
 12. <span data-ttu-id="1e6b7-164">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-164">Close the page.</span></span>  
 13. <span data-ttu-id="1e6b7-165">Rozwiń sekcję Podpis.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-165">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="1e6b7-166">W polu Drukuj pierwszy podpis zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-166">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="1e6b7-167">Kliknij przycisk Zmień.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-167">Click Change.</span></span>  
 16. <span data-ttu-id="1e6b7-168">Kliknij przycisk Przeglądaj i wybierz pobrany wcześniej plik Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-168">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="1e6b7-169">Rozwiń sekcję Kopie.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-169">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="1e6b7-170">W polu Znak wodny wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-170">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="1e6b7-171">W polu Ogólny elektroniczny format eksportu wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-171">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="1e6b7-172">Wybierz konfigurację „Cheques printing form”.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-172">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="1e6b7-173">Teraz wybrany format ER zostanie użyty do drukowania czeków.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-173">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="1e6b7-174">Kliknij opcję Dołącz.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-174">Click Attach.</span></span>  
 23. <span data-ttu-id="1e6b7-175">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-175">Click New.</span></span>  
 24. <span data-ttu-id="1e6b7-176">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-176">Click File.</span></span>  
 25. <span data-ttu-id="1e6b7-177">Kliknij przycisk Przeglądaj i wybierz pobrany wcześniej plik Signature image 2.png.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-177">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="1e6b7-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-178">Close the page.</span></span>  
 27. <span data-ttu-id="1e6b7-179">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-179">Close the page.</span></span>  
 28. <span data-ttu-id="1e6b7-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-180">Close the page.</span></span>  
 29. <span data-ttu-id="1e6b7-181">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-181">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="1e6b7-182">W polu Zezwalaj na tworzenie przelewu testowego dla nieaktywnych kont bankowych zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-182">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="1e6b7-183">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-183">Click Save.</span></span>  
 32. <span data-ttu-id="1e6b7-184">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1e6b7-184">Close the page.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
