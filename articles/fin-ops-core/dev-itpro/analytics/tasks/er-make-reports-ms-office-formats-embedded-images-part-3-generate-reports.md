---
title: Generowanie raportów w formatach pakietu Office z osadzonymi obrazami
description: W poniższych krokach wyjaśniono, jak użytkownik odtwarzający rolę „Administrator systemu” lub „Deweloper raportowania elektronicznego” może projektować konfiguracje raportowania elektronicznego (ER) w celu generowania dokumentów elektronicznych w formatach dokumentów pakietu MS Office (Excel i Word) zawierających osadzone obrazy.
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
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
ms.openlocfilehash: 78dcdbd83dc717104d437662f7f451c9ecb714cf
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684386"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="d9595-103">Generowanie raportów w formatach pakietu Office z osadzonymi obrazami</span><span class="sxs-lookup"><span data-stu-id="d9595-103">Generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d9595-104">W poniższych krokach wyjaśniono, jak użytkownik odtwarzający rolę „Administrator systemu” lub „Deweloper raportowania elektronicznego” może projektować konfiguracje raportowania elektronicznego (ER) w celu generowania dokumentów elektronicznych w formatach dokumentów pakietu MS Office (Excel i Word) zawierających osadzone obrazy.</span><span class="sxs-lookup"><span data-stu-id="d9595-104">The following steps explain how a user playing either 'System administrator' or 'Electronic reporting developer' role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="d9595-105">W tym przykładzie użyjesz utworzonych konfiguracji ER dla przykładowej firmy „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="d9595-105">In this example, you will use created ER configurations for sample company, 'Litware, Inc.'.</span></span>  <span data-ttu-id="d9595-106">Aby wykonać te kroki, należy najpierw wykonać kroki z przewodnika po zadaniu „ER Tworzenie raportów w formatach programu MS Office z osadzonymi obrazami (Część 2: Przegląd konfiguracji)”.</span><span class="sxs-lookup"><span data-stu-id="d9595-106">To complete these steps, you must first complete the steps in the "ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)" task guide.</span></span> <span data-ttu-id="d9595-107">Kroki można wykonać na danych firmy „USMF”.</span><span class="sxs-lookup"><span data-stu-id="d9595-107">These steps can be performed in 'USMF' company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="d9595-108">Uruchamianie formatu z początkowym mapowaniem modelu</span><span class="sxs-lookup"><span data-stu-id="d9595-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="d9595-109">Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.</span><span class="sxs-lookup"><span data-stu-id="d9595-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="d9595-110">Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „USMF OPER”.</span><span class="sxs-lookup"><span data-stu-id="d9595-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="d9595-111">W okienku akcji kliknij pozycję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="d9595-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="d9595-112">Kliknij przycisk Sprawdź.</span><span class="sxs-lookup"><span data-stu-id="d9595-112">Click Check.</span></span>
5. <span data-ttu-id="d9595-113">Kliknij opcję Drukowanie testu.</span><span class="sxs-lookup"><span data-stu-id="d9595-113">Click Print test.</span></span>
    * <span data-ttu-id="d9595-114">Uruchom format do celów testowych.</span><span class="sxs-lookup"><span data-stu-id="d9595-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="d9595-115">W polu Format czeku zbywalnego wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="d9595-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="d9595-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d9595-116">Click OK.</span></span>
    * <span data-ttu-id="d9595-117">Przejrzyj produkt wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="d9595-117">Review the created output.</span></span> <span data-ttu-id="d9595-118">W raporcie jest przedstawiane logo firmy oraz podpis osoby upoważnionej.</span><span class="sxs-lookup"><span data-stu-id="d9595-118">The company logo is presented in the report as well as the authorized person's signature.</span></span> <span data-ttu-id="d9595-119">Obraz podpisu jest pobierany z pola danych typu „Kontener” w rekordzie układu czeku skojarzonym z wybranym kontem bankowym.</span><span class="sxs-lookup"><span data-stu-id="d9595-119">The signature image is taken from the field of the 'Container' data type of the cheque layout record that is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="d9595-120">Rozwiń sekcję Kopie.</span><span class="sxs-lookup"><span data-stu-id="d9595-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="d9595-121">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="d9595-121">Click Edit.</span></span>
10. <span data-ttu-id="d9595-122">W polu Znak wodny wprowadź tekst „Drukuj znak wodny jako unieważniony”.</span><span class="sxs-lookup"><span data-stu-id="d9595-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="d9595-123">Zmień ustawienie znaku wodnego, aby był pokazywany tekst znaku wodnego podczas generowania dokumentu w elemencie kształtu programu Excel.</span><span class="sxs-lookup"><span data-stu-id="d9595-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="d9595-124">Kliknij opcję Drukowanie testu.</span><span class="sxs-lookup"><span data-stu-id="d9595-124">Click Print test.</span></span>
12. <span data-ttu-id="d9595-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d9595-125">Click OK.</span></span>
    * <span data-ttu-id="d9595-126">Przejrzyj produkt wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="d9595-126">Review the created output.</span></span> <span data-ttu-id="d9595-127">Znak wodny jest widoczny w utworzonym raporcie zgodnie z wybraną opcją.</span><span class="sxs-lookup"><span data-stu-id="d9595-127">The watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="d9595-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-128">Close the page.</span></span>
14. <span data-ttu-id="d9595-129">W okienku akcji kliknij pozycję Zarządzanie płatnościami.</span><span class="sxs-lookup"><span data-stu-id="d9595-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="d9595-130">Kliknij przycisk Czeki.</span><span class="sxs-lookup"><span data-stu-id="d9595-130">Click Checks.</span></span>
16. <span data-ttu-id="d9595-131">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="d9595-131">Click Show filters.</span></span>
17. <span data-ttu-id="d9595-132">Zastosuj następujące filtry: wprowadź wartość filtru „381”,„385”,„389” w polu „Numer czeku”, stosując operator filtru „jest jednym z”.</span><span class="sxs-lookup"><span data-stu-id="d9595-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="d9595-133">Na liście zaznacz wszystkie wiersze.</span><span class="sxs-lookup"><span data-stu-id="d9595-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="d9595-134">Kliknij opcję Drukuj kopię czeku.</span><span class="sxs-lookup"><span data-stu-id="d9595-134">Click Print check copy.</span></span>
    * <span data-ttu-id="d9595-135">Uruchom format, aby ponownie wydrukować wybrane czeki.</span><span class="sxs-lookup"><span data-stu-id="d9595-135">Run the format to reprint the selected cheques.</span></span>  
    * <span data-ttu-id="d9595-136">Przejrzyj produkt wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="d9595-136">Review the created output.</span></span> <span data-ttu-id="d9595-137">Wybrane czeki zostały ponownie wydrukowane.</span><span class="sxs-lookup"><span data-stu-id="d9595-137">The selected cheques have been reprinted.</span></span> <span data-ttu-id="d9595-138">Logo firmy i etykiety nie są drukowane, ponieważ znajdują się na formularzu z nadrukiem.</span><span class="sxs-lookup"><span data-stu-id="d9595-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="d9595-139">Modyfikowanie mapowania zaimportowanego modelu danych</span><span class="sxs-lookup"><span data-stu-id="d9595-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="d9595-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-140">Close the page.</span></span>
2. <span data-ttu-id="d9595-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-141">Close the page.</span></span>
3. <span data-ttu-id="d9595-142">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="d9595-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="d9595-143">W drzewie zaznacz element „Model czeków”.</span><span class="sxs-lookup"><span data-stu-id="d9595-143">In the tree, select 'Model for cheques'.</span></span>
5. <span data-ttu-id="d9595-144">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="d9595-144">Click Designer.</span></span>
6. <span data-ttu-id="d9595-145">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="d9595-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="d9595-146">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="d9595-146">Click Designer.</span></span>
    * <span data-ttu-id="d9595-147">Zmienimy powiązanie elementu podpisu modelu danych, tak aby obraz podpisu był pobierany z pliku dołączonego do rekordu układu czeku skojarzonego z wybranym kontem bankowym.</span><span class="sxs-lookup"><span data-stu-id="d9595-147">We will change the binding of the data model's signature item to get the signature image from the file that has been attached to the cheque layout record that is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="d9595-148">Wyłącz opcję Pokaż szczegóły.</span><span class="sxs-lookup"><span data-stu-id="d9595-148">Turn off Show details.</span></span>
9. <span data-ttu-id="d9595-149">W drzewie rozwiń węzeł „układ”.</span><span class="sxs-lookup"><span data-stu-id="d9595-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="d9595-150">W drzewie rozwiń węzeł „układ\podpis”.</span><span class="sxs-lookup"><span data-stu-id="d9595-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="d9595-151">W drzewie zaznacz element „układ\podpis\obraz = chequesaccount.'<Relacje'.BankChequeLayout.Signature1Bmp”.</span><span class="sxs-lookup"><span data-stu-id="d9595-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="d9595-152">W drzewie rozwiń węzeł „chequesaccount”.</span><span class="sxs-lookup"><span data-stu-id="d9595-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="d9595-153">W drzewie rozwiń węzeł „chequesaccount\<Relacje”.</span><span class="sxs-lookup"><span data-stu-id="d9595-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="d9595-154">W drzewie rozwiń węzeł „chequesaccount\<Relacje\BankChequeLayout”.</span><span class="sxs-lookup"><span data-stu-id="d9595-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="d9595-155">W drzewie rozwiń węzeł „chequesaccount\<Relacje\BankChequeLayout\<Relacje”.</span><span class="sxs-lookup"><span data-stu-id="d9595-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="d9595-156">W drzewie rozwiń węzeł „chequesaccount\<Relacje\BankChequeLayout\<Relacje\<Dokumenty”.</span><span class="sxs-lookup"><span data-stu-id="d9595-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="d9595-157">W drzewie zaznacz element „chequesaccount\<Relacje\BankChequeLayout\<Relacje\<Dokumenty\getFileContentAsContainer()”.</span><span class="sxs-lookup"><span data-stu-id="d9595-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="d9595-158">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="d9595-158">Click Bind.</span></span>
19. <span data-ttu-id="d9595-159">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d9595-159">Click Save.</span></span>
20. <span data-ttu-id="d9595-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-160">Close the page.</span></span>
21. <span data-ttu-id="d9595-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-161">Close the page.</span></span>
22. <span data-ttu-id="d9595-162">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-162">Close the page.</span></span>
23. <span data-ttu-id="d9595-163">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="d9595-164">Uruchamianie formatu przy użyciu skorygowanego mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="d9595-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="d9595-165">Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.</span><span class="sxs-lookup"><span data-stu-id="d9595-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="d9595-166">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="d9595-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d9595-167">Na przykład wyfiltruj według pola Konto bankowe z wartością „USMF OPER”.</span><span class="sxs-lookup"><span data-stu-id="d9595-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="d9595-168">W okienku akcji kliknij pozycję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="d9595-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="d9595-169">Kliknij przycisk Sprawdź.</span><span class="sxs-lookup"><span data-stu-id="d9595-169">Click Check.</span></span>
5. <span data-ttu-id="d9595-170">Kliknij opcję Drukowanie testu.</span><span class="sxs-lookup"><span data-stu-id="d9595-170">Click Print test.</span></span>
6. <span data-ttu-id="d9595-171">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d9595-171">Click OK.</span></span>
    * <span data-ttu-id="d9595-172">Przejrzyj produkt wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="d9595-172">Review the created output.</span></span> <span data-ttu-id="d9595-173">Obraz z załącznika funkcji zarządzania dokumentami jest wyświetlany jako podpis osoby upoważnionej.</span><span class="sxs-lookup"><span data-stu-id="d9595-173">The image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="d9595-174">Używanie dokumentu programu MS Word jako szablonu w zaimportowanym formacie</span><span class="sxs-lookup"><span data-stu-id="d9595-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="d9595-175">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-175">Close the page.</span></span>
2. <span data-ttu-id="d9595-176">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-176">Close the page.</span></span>
3. <span data-ttu-id="d9595-177">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="d9595-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="d9595-178">W drzewie rozwiń węzeł „Model czeków”.</span><span class="sxs-lookup"><span data-stu-id="d9595-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="d9595-179">W drzewie zaznacz element „Model czeków\Format drukowania czeków”.</span><span class="sxs-lookup"><span data-stu-id="d9595-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="d9595-180">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="d9595-180">Click Designer.</span></span>
7. <span data-ttu-id="d9595-181">Kliknij opcję Załączniki.</span><span class="sxs-lookup"><span data-stu-id="d9595-181">Click Attachments.</span></span>
8. <span data-ttu-id="d9595-182">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="d9595-182">Click Delete.</span></span>
9. <span data-ttu-id="d9595-183">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="d9595-183">Click Yes.</span></span>
10. <span data-ttu-id="d9595-184">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d9595-184">Click New.</span></span>
11. <span data-ttu-id="d9595-185">Kliknij opcję Plik.</span><span class="sxs-lookup"><span data-stu-id="d9595-185">Click File.</span></span>
    * <span data-ttu-id="d9595-186">Kliknij przycisk Przeglądaj i zaznacz pobrany wcześniej plik „Cheque template Word.docx”.</span><span class="sxs-lookup"><span data-stu-id="d9595-186">Click Browse and select the downloaded in advance 'Cheque template Word.docx' file.</span></span>  
12. <span data-ttu-id="d9595-187">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-187">Close the page.</span></span>
13. <span data-ttu-id="d9595-188">W polu Szablon wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d9595-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="d9595-189">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d9595-189">Click Save.</span></span>
15. <span data-ttu-id="d9595-190">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-190">Close the page.</span></span>
16. <span data-ttu-id="d9595-191">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="d9595-191">Click Edit.</span></span>
17. <span data-ttu-id="d9595-192">W polu Uruchom wersję roboczą wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="d9595-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="d9595-193">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d9595-193">Close the page.</span></span>
19. <span data-ttu-id="d9595-194">Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.</span><span class="sxs-lookup"><span data-stu-id="d9595-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="d9595-195">Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „USMF OPER”.</span><span class="sxs-lookup"><span data-stu-id="d9595-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="d9595-196">Kliknij przycisk Sprawdź.</span><span class="sxs-lookup"><span data-stu-id="d9595-196">Click Check.</span></span>
22. <span data-ttu-id="d9595-197">Kliknij opcję Drukowanie testu.</span><span class="sxs-lookup"><span data-stu-id="d9595-197">Click Print test.</span></span>
23. <span data-ttu-id="d9595-198">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d9595-198">Click OK.</span></span>
    * <span data-ttu-id="d9595-199">Przejrzyj produkt wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="d9595-199">Review the created output.</span></span> <span data-ttu-id="d9595-200">Dane wyjściowe zostały wygenerowane jako dokument programu Word z osadzonymi obrazami prezentującymi logo firmy, podpis osoby upoważnionej i wybrany tekst znaku wodnego.</span><span class="sxs-lookup"><span data-stu-id="d9595-200">The output has been generated as a Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  

