---
title: Projektowanie konfiguracji służących do generowania raportów w formatach pakietu Office z osadzonymi obrazami
description: W tym temacie opisano sposób projektowania konfiguracji generujących dokumenty elektroniczne w formatach programów Excel i Word z osadzonymi obrazami.
author: NickSelin
manager: AnnBe
ms.date: 01/23/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b60ed6b07851c44ceb4b8f313bc65f04b802e646
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093677"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="7b16e-103">Projektowanie konfiguracji służących do generowania raportów w formatach pakietu Office z osadzonymi obrazami</span><span class="sxs-lookup"><span data-stu-id="7b16e-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b16e-104">Aby wykonać kroki podane w tej procedurze, należy najpierw wykonać procedurę „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="7b16e-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="7b16e-105">W tej procedurze wyjaśniono sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentów programów Microsoft Excel i Word zawierających osadzone obrazy.</span><span class="sxs-lookup"><span data-stu-id="7b16e-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="7b16e-106">W tej procedurze utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Kroki można wykonać przy użyciu zestawu danych firmy USMF.</span><span class="sxs-lookup"><span data-stu-id="7b16e-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="7b16e-107">Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="7b16e-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="7b16e-108">Zanim rozpoczniesz, pobierz i zapisz pliki wymienione w temacie pomocy [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](../electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="7b16e-108">Before you begin, download and save the files listed in the Help topic, [Embed images and shapes in documents that you generate by using ER](../electronic-reporting-embed-images-shapes.md).</span></span> <span data-ttu-id="7b16e-109">Pliki to: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png i Cheque template Word.docx.</span><span class="sxs-lookup"><span data-stu-id="7b16e-109">The files are: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png, and Cheque template Word.docx.</span></span>

## <a name="verify-prerequisites"></a><span data-ttu-id="7b16e-110">Sprawdzanie wymagań</span><span class="sxs-lookup"><span data-stu-id="7b16e-110">Verify prerequisites</span></span>  
 1. <span data-ttu-id="7b16e-111">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="7b16e-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="7b16e-112">Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny.</span><span class="sxs-lookup"><span data-stu-id="7b16e-112">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="7b16e-113">Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="7b16e-113">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="7b16e-114">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="7b16e-114">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="7b16e-115">Dodawanie nowej konfiguracji modelu ER</span><span class="sxs-lookup"><span data-stu-id="7b16e-115">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="7b16e-116">Zamiast tworzyć nowy model, można załadować plik konfiguracji modelu ER (Model for cheques.xml), który został wcześniej zapisany.</span><span class="sxs-lookup"><span data-stu-id="7b16e-116">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="7b16e-117">Plik ten zawiera przykładowy model danych dla czeków płatniczych i mapowanie modelu danych do składników danych aplikacji Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="7b16e-117">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="7b16e-118">Na skróconej karcie Wersje kliknij przycisk Import/eksport.</span><span class="sxs-lookup"><span data-stu-id="7b16e-118">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="7b16e-119">Kliknij opcję Załaduj z pliku XML.</span><span class="sxs-lookup"><span data-stu-id="7b16e-119">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="7b16e-120">Kliknij przycisk Przeglądaj, a następnie wybierz plik Model for cheques.xml.</span><span class="sxs-lookup"><span data-stu-id="7b16e-120">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="7b16e-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7b16e-121">Click OK.</span></span>  
 6. <span data-ttu-id="7b16e-122">Załadowany model zostanie użyty jako źródło danych informacji do generowania dokumentów, które zawierają obrazy w programie Excel i Word.</span><span class="sxs-lookup"><span data-stu-id="7b16e-122">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="7b16e-123">Dodawanie nowej konfiguracji formatu ER</span><span class="sxs-lookup"><span data-stu-id="7b16e-123">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="7b16e-124">Zamiast tworzyć nowy format można załadować plik konfiguracji formatu ER (Cheques printing format.xml), który został wcześniej zapisany.</span><span class="sxs-lookup"><span data-stu-id="7b16e-124">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="7b16e-125">Ten plik zawiera przykładowy układ formatu do drukowania czeków przy użyciu wstępnie zadrukowanego formularza i mapowanie tego formatu do modelu danych „Model czeków”.</span><span class="sxs-lookup"><span data-stu-id="7b16e-125">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="7b16e-126">Kliknij opcję Import/eksport.</span><span class="sxs-lookup"><span data-stu-id="7b16e-126">Click Exchange.</span></span>  
 3. <span data-ttu-id="7b16e-127">Kliknij opcję Załaduj z pliku XML.</span><span class="sxs-lookup"><span data-stu-id="7b16e-127">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="7b16e-128">Kliknij przycisk Przeglądaj i wybierz plik Cheques printing format.xml.</span><span class="sxs-lookup"><span data-stu-id="7b16e-128">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="7b16e-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7b16e-129">Click OK.</span></span>  
 6. <span data-ttu-id="7b16e-130">W drzewie rozwiń węzeł „Model czeków”.</span><span class="sxs-lookup"><span data-stu-id="7b16e-130">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="7b16e-131">W drzewie zaznacz element „Model czeków\Format drukowania czeków”.</span><span class="sxs-lookup"><span data-stu-id="7b16e-131">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="7b16e-132">Załadowany format zostanie użyty do generowania dokumentów, które zawierają obrazy w programie Excel i Word.</span><span class="sxs-lookup"><span data-stu-id="7b16e-132">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="7b16e-133">Konfigurowanie parametrów użytkownika modułu ER</span><span class="sxs-lookup"><span data-stu-id="7b16e-133">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="7b16e-134">W okienku akcji kliknij pozycję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="7b16e-134">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="7b16e-135">Kliknij opcję Parametry użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7b16e-135">Click User parameters.</span></span>  
 3. <span data-ttu-id="7b16e-136">W polu Ustawienia uruchamiania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="7b16e-136">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="7b16e-137">Włącz flagę „Uruchom wersję roboczą”, aby uruchomić wersję roboczą wybranego formatu zamiast wersji ukończonej.</span><span class="sxs-lookup"><span data-stu-id="7b16e-137">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="7b16e-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7b16e-138">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="7b16e-139">Konfigurowanie parametrów modułu Zarządzanie gotówką i bankami</span><span class="sxs-lookup"><span data-stu-id="7b16e-139">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="7b16e-140">Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.</span><span class="sxs-lookup"><span data-stu-id="7b16e-140">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="7b16e-141">Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „USMF OPER”.</span><span class="sxs-lookup"><span data-stu-id="7b16e-141">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="7b16e-142">W okienku akcji kliknij pozycję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="7b16e-142">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="7b16e-143">Kliknij przycisk Sprawdź.</span><span class="sxs-lookup"><span data-stu-id="7b16e-143">Click Check.</span></span>  
 5. <span data-ttu-id="7b16e-144">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="7b16e-144">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="7b16e-145">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="7b16e-145">Click Edit.</span></span>  
 7. <span data-ttu-id="7b16e-146">W polu Logo firmy wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="7b16e-146">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="7b16e-147">Kliknij Logo firmy.</span><span class="sxs-lookup"><span data-stu-id="7b16e-147">Click Company logo.</span></span>  
 9. <span data-ttu-id="7b16e-148">Kliknij przycisk Zmień.</span><span class="sxs-lookup"><span data-stu-id="7b16e-148">Click Change.</span></span>  
 10. <span data-ttu-id="7b16e-149">Kliknij przycisk Przeglądaj i wybierz pobrany wcześniej plik Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="7b16e-149">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="7b16e-150">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7b16e-150">Click Save.</span></span>  
 12. <span data-ttu-id="7b16e-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7b16e-151">Close the page.</span></span>  
 13. <span data-ttu-id="7b16e-152">Rozwiń sekcję Podpis.</span><span class="sxs-lookup"><span data-stu-id="7b16e-152">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="7b16e-153">W polu Drukuj pierwszy podpis zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="7b16e-153">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="7b16e-154">Kliknij przycisk Zmień.</span><span class="sxs-lookup"><span data-stu-id="7b16e-154">Click Change.</span></span>  
 16. <span data-ttu-id="7b16e-155">Kliknij przycisk Przeglądaj i wybierz pobrany wcześniej plik Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="7b16e-155">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="7b16e-156">Rozwiń sekcję Kopie.</span><span class="sxs-lookup"><span data-stu-id="7b16e-156">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="7b16e-157">W polu Znak wodny wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="7b16e-157">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="7b16e-158">W polu Ogólny elektroniczny format eksportu wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="7b16e-158">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="7b16e-159">Wybierz konfigurację „Cheques printing form”.</span><span class="sxs-lookup"><span data-stu-id="7b16e-159">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="7b16e-160">Teraz wybrany format ER zostanie użyty do drukowania czeków.</span><span class="sxs-lookup"><span data-stu-id="7b16e-160">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="7b16e-161">Kliknij opcję Dołącz.</span><span class="sxs-lookup"><span data-stu-id="7b16e-161">Click Attach.</span></span>  
 23. <span data-ttu-id="7b16e-162">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7b16e-162">Click New.</span></span>  
 24. <span data-ttu-id="7b16e-163">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="7b16e-163">Click File.</span></span>  
 25. <span data-ttu-id="7b16e-164">Kliknij przycisk Przeglądaj i wybierz pobrany wcześniej plik Signature image 2.png.</span><span class="sxs-lookup"><span data-stu-id="7b16e-164">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="7b16e-165">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7b16e-165">Close the page.</span></span>  
 27. <span data-ttu-id="7b16e-166">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7b16e-166">Close the page.</span></span>  
 28. <span data-ttu-id="7b16e-167">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7b16e-167">Close the page.</span></span>  
 29. <span data-ttu-id="7b16e-168">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="7b16e-168">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="7b16e-169">W polu Zezwalaj na tworzenie przelewu testowego dla nieaktywnych kont bankowych zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="7b16e-169">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="7b16e-170">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7b16e-170">Click Save.</span></span>  
 32. <span data-ttu-id="7b16e-171">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7b16e-171">Close the page.</span></span>  
