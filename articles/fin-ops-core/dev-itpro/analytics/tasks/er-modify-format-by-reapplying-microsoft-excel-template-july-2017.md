---
title: Modyfikowanie formatów przez ponowne zastosowanie szablonów programu Excel
description: W celu wykonania kroków w tej procedurze należy najpierw wykonać procedurę „ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML”.
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
ms.openlocfilehash: 73f2c10d7462c4b52a2b36dd5f221593707d2f4f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184676"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a><span data-ttu-id="f336d-103">Modyfikowanie formatów przez ponowne zastosowanie szablonów programu Excel</span><span class="sxs-lookup"><span data-stu-id="f336d-103">Modify formats by reapplying Excel templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f336d-104">W celu wykonania kroków w tej procedurze należy najpierw wykonać procedurę „ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML”.</span><span class="sxs-lookup"><span data-stu-id="f336d-104">To complete the steps in this procedure, you must first complete the procedure, ER - Design a configuration for generating reports in OPENXML format.</span></span>

<span data-ttu-id="f336d-105">W tej procedurze wyjaśniono sposób modyfikowania konfiguracji formatu raportowania elektronicznego (ER) przez ponowne zastosowanie szablonu programu Microsoft Excel, który został zmodyfikowany.</span><span class="sxs-lookup"><span data-stu-id="f336d-105">This procedure explains how to modify an Electronic reporting (ER) format configuration by reapplying a Microsoft Excel template that has been modified.</span></span> <span data-ttu-id="f336d-106">W tej procedurze zaimportujesz zmodyfikowany szablon programu Excel do konfiguracji formatu raportowania elektronicznego, które zostały utworzone dla przykładowej firmy Litware, Inc., a następnie wygenerujesz dokumenty elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="f336d-106">In this procedure, you will import a modified Excel template into ER format configurations that have been created for the sample company, Litware, Inc., and then generate electronic documents.</span></span> <span data-ttu-id="f336d-107">Ta procedura jest przeznaczona dla użytkowników posiadających rolę administratora systemu lub dewelopera raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="f336d-107">This procedure is intended for users who have the system administrator or electronic reporting developer role.</span></span> <span data-ttu-id="f336d-108">Kroki można wykonać przy użyciu zestawu danych firmy GBSI.</span><span class="sxs-lookup"><span data-stu-id="f336d-108">These steps can be completed by using the GBSI dataset.</span></span> <span data-ttu-id="f336d-109">Przed rozpoczęciem pobierz i zapisz plik SampleVendPaymWsReport2.xlsx, która jest wyświetlany w temacie Pomocy Modyfikowanie formatu raportowania elektronicznego przez ponowne zastosowanie szablonu programu Excel (modify-electronic-reporting-format-reapply-excel-template/).</span><span class="sxs-lookup"><span data-stu-id="f336d-109">Before you begin, download and save the file, SampleVendPaymWsReport2.xlsx, which is listed in the Help topic, Modify Electronic reporting format by reapplying an Excel template (modify-electronic-reporting-format-reapply-excel-template/).</span></span>

1. <span data-ttu-id="f336d-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="f336d-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="f336d-111">Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny.</span><span class="sxs-lookup"><span data-stu-id="f336d-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="f336d-112">Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego.</span><span class="sxs-lookup"><span data-stu-id="f336d-112">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  

## <a name="select-the-er-format"></a><span data-ttu-id="f336d-113">Wybieranie formatu ER</span><span class="sxs-lookup"><span data-stu-id="f336d-113">Select the ER format</span></span>
1. <span data-ttu-id="f336d-114">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="f336d-114">Click Reporting configurations.</span></span>
2. <span data-ttu-id="f336d-115">W drzewie rozwiń „model płatności”.</span><span class="sxs-lookup"><span data-stu-id="f336d-115">In the tree, expand 'Payment model'.</span></span>
3. <span data-ttu-id="f336d-116">W drzewie zaznacz węzeł „Model płatności\Przykładowy raport arkusza”.</span><span class="sxs-lookup"><span data-stu-id="f336d-116">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
4. <span data-ttu-id="f336d-117">Kliknij opcję Załączniki.</span><span class="sxs-lookup"><span data-stu-id="f336d-117">Click Attachments.</span></span>
    * <span data-ttu-id="f336d-118">Należy zauważyć, że plik programu Excel SampleVendPaymWsReport.xlsx jest aktualnie używany jako szablon do przetwarzania arkusza płatności.</span><span class="sxs-lookup"><span data-stu-id="f336d-118">Note that the SampleVendPaymWsReport.xlsx Excel file is currently used as a template for payment journal processing.</span></span>   
5. <span data-ttu-id="f336d-119">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="f336d-119">Click Open.</span></span>
    * <span data-ttu-id="f336d-120">Kliknij przycisk Otwórz, aby obejrzeć układ szablonu programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f336d-120">Click Open to explore the layout of the Excel template.</span></span>  
    * <span data-ttu-id="f336d-121">Przejrzyj szablon.</span><span class="sxs-lookup"><span data-stu-id="f336d-121">Review the template.</span></span> <span data-ttu-id="f336d-122">Należy zauważyć, że obecnie zawiera on następujące dane dla każdego wiersza płatności: numer konta dostawcy, nazwa dostawcy, bank, kod banku, numer konta, saldo winien, saldo ma i waluta.</span><span class="sxs-lookup"><span data-stu-id="f336d-122">Note that it currently includes the following details for each payment line: vendor account number, vendor name, bank, routing number, account number, debit, credit, and currency.</span></span> <span data-ttu-id="f336d-123">W tym przykładzie chcemy poszerzyć tę listę, dodając szczegóły daty płatności.</span><span class="sxs-lookup"><span data-stu-id="f336d-123">For this example, we want to extend this list by adding details about the payment date.</span></span>   
6. <span data-ttu-id="f336d-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f336d-124">Close the page.</span></span>

## <a name="reapply-a-new-excel-template-to-er-format"></a><span data-ttu-id="f336d-125">Ponownie stosowanie nowego szablonu programu Excel do formatu ER</span><span class="sxs-lookup"><span data-stu-id="f336d-125">Reapply a new Excel template to ER format</span></span>
1. <span data-ttu-id="f336d-126">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="f336d-126">Click Designer.</span></span>
    * <span data-ttu-id="f336d-127">Otwórz wersję roboczą wybranego formatu ER w celu edytowania.</span><span class="sxs-lookup"><span data-stu-id="f336d-127">Open the draft version of the selected ER format for editing.</span></span>  
2. <span data-ttu-id="f336d-128">W okienku akcji kliknij pozycję Importuj.</span><span class="sxs-lookup"><span data-stu-id="f336d-128">On the Action Pane, click Import.</span></span>
3. <span data-ttu-id="f336d-129">Kliknij opcję Aktualizacja z programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f336d-129">Click Update from Excel.</span></span>
    * <span data-ttu-id="f336d-130">Kliknij przycisk „Aktualizuj szablon”, a następnie zaznacz plik SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="f336d-130">Click ‘Update template’, and then select the file, SampleVendPaymWsReport2.xlsx.</span></span>  
    * <span data-ttu-id="f336d-131">Kliknij przycisk Aktualizuj szablon i przejdź do pobranego wcześniej pliku SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="f336d-131">Click Update template and browse to get the downloaded earlier SampleVendPaymWsReport2.xlsx file.</span></span>  
4. <span data-ttu-id="f336d-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f336d-132">Click OK.</span></span>
    * <span data-ttu-id="f336d-133">Szablon SampleVendPaymWsReport2.xlsx zostanie zastosowany.</span><span class="sxs-lookup"><span data-stu-id="f336d-133">The SampleVendPaymWsReport2.xlsx template is applied.</span></span> <span data-ttu-id="f336d-134">Struktura formatu ER zostanie zsynchronizowana z zawartością szablonu, którego elementy zostaną dodane do formatu ER.</span><span class="sxs-lookup"><span data-stu-id="f336d-134">The structure of the ER format is synchronized with the content of the template, whose elements are added to the ER format.</span></span> <span data-ttu-id="f336d-135">Wszelkie istniejące elementy w formacie ER, które nie są umieszczone w szablonie, zostaną usunięte z definicji formatu.</span><span class="sxs-lookup"><span data-stu-id="f336d-135">Any existing elements in the ER format that aren’t included in the template are removed from the format definition.</span></span>  
5. <span data-ttu-id="f336d-136">W drzewie zaznacz element „Excel”.</span><span class="sxs-lookup"><span data-stu-id="f336d-136">In the tree, select 'Excel'.</span></span>
    * <span data-ttu-id="f336d-137">Należy zwrócić uwagę, że teraz pole Szablon zawiera odwołanie do nowego szablonu.</span><span class="sxs-lookup"><span data-stu-id="f336d-137">Note that the Template field now contains a reference to the new template.</span></span>   
6. <span data-ttu-id="f336d-138">Kliknij opcję Załączniki.</span><span class="sxs-lookup"><span data-stu-id="f336d-138">Click Attachments.</span></span>
7. <span data-ttu-id="f336d-139">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="f336d-139">Click Open.</span></span>
    * <span data-ttu-id="f336d-140">Kliknij przycisk Otwórz, aby obejrzeć układ zmodyfikowanego szablonu programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f336d-140">Click Open to explore the layout of the modified Excel template.</span></span>  
    * <span data-ttu-id="f336d-141">Przejrzyj szablon.</span><span class="sxs-lookup"><span data-stu-id="f336d-141">Review the template.</span></span> <span data-ttu-id="f336d-142">Należy zauważyć, że teraz zawiera wiersz daty płatności.</span><span class="sxs-lookup"><span data-stu-id="f336d-142">Note that it now contains a line for the payment date.</span></span>   
8. <span data-ttu-id="f336d-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f336d-143">Close the page.</span></span>
9. <span data-ttu-id="f336d-144">W drzewie rozwiń węzeł „Excel”.</span><span class="sxs-lookup"><span data-stu-id="f336d-144">In the tree, expand 'Excel'.</span></span>
10. <span data-ttu-id="f336d-145">W drzewie rozwiń węzeł „Excel\PaymLines”.</span><span class="sxs-lookup"><span data-stu-id="f336d-145">In the tree, expand 'Excel\PaymLines'.</span></span>
11. <span data-ttu-id="f336d-146">W drzewie zaznacz element „Excel\PaymLines\PaymDate”.</span><span class="sxs-lookup"><span data-stu-id="f336d-146">In the tree, select 'Excel\PaymLines\PaymDate'.</span></span>
    * <span data-ttu-id="f336d-147">Należy zauważyć, że format ER teraz zawiera jeden element więcej.</span><span class="sxs-lookup"><span data-stu-id="f336d-147">Note that the ER format now contains one more item.</span></span> <span data-ttu-id="f336d-148">Do szablonu programu Excel została dodana komórka PaymDate.</span><span class="sxs-lookup"><span data-stu-id="f336d-148">A cell, PaymDate, has been added to the Excel template.</span></span>  
12. <span data-ttu-id="f336d-149">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="f336d-149">Click the Mapping tab.</span></span>
13. <span data-ttu-id="f336d-150">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="f336d-150">In the tree, expand 'model'.</span></span>
14. <span data-ttu-id="f336d-151">W drzewie rozwiń węzeł „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="f336d-151">In the tree, expand 'model\Payments'.</span></span>
15. <span data-ttu-id="f336d-152">W drzewie zaznacz element „model\Płatności\Data transakcji(TransactionDate)”.</span><span class="sxs-lookup"><span data-stu-id="f336d-152">In the tree, select 'model\Payments\Transaction date(TransactionDate)'.</span></span>
16. <span data-ttu-id="f336d-153">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="f336d-153">Click Bind.</span></span>
    * <span data-ttu-id="f336d-154">Określ, jakie dane będą dodawane do nowej komórki w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="f336d-154">Specify what data is added to the new cell at runtime.</span></span>  
17. <span data-ttu-id="f336d-155">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f336d-155">Click Save.</span></span>
18. <span data-ttu-id="f336d-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f336d-156">Close the page.</span></span>

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a><span data-ttu-id="f336d-157">Włączanie używania zmodyfikowanej wersji roboczej formatu ER w przetwarzaniu arkusza płatności</span><span class="sxs-lookup"><span data-stu-id="f336d-157">Enable the modified draft version of the ER format for use in payment journal processing</span></span>
1. <span data-ttu-id="f336d-158">W okienku akcji kliknij pozycję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="f336d-158">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="f336d-159">Kliknij opcję Parametry użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f336d-159">Click User parameters.</span></span>
3. <span data-ttu-id="f336d-160">W polu Ustawienia uruchamiania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="f336d-160">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="f336d-161">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f336d-161">Click OK.</span></span>
5. <span data-ttu-id="f336d-162">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="f336d-162">Click Edit.</span></span>
6. <span data-ttu-id="f336d-163">W polu Uruchom wersję roboczą wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="f336d-163">Select Yes in the Run Draft field.</span></span>

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a><span data-ttu-id="f336d-164">Używanie zmodyfikowanej wersji roboczej formatu ER w przetwarzaniu arkusza płatności</span><span class="sxs-lookup"><span data-stu-id="f336d-164">Use the modified draft version of the ER format for payment journal processing</span></span>
    * <span data-ttu-id="f336d-165">Przejrzyj utworzony arkusz, w tym nowy szczegół wierszy płatności — datę płatności.</span><span class="sxs-lookup"><span data-stu-id="f336d-165">Review the created worksheet, including new detail of payment lines – payment date.</span></span>  

