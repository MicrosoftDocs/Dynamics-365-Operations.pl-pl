---
title: Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego
description: Ważne jest, aby plik wyciągu bankowego z banku pracował do układu obsługiwanego przez Microsoft Dynamics 365 Finance. Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie. Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki. Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego. W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy.
author: panolte
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adea87b6341860a9aa1625811270274e02a88b26
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978946"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="57bcf-107">Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego</span><span class="sxs-lookup"><span data-stu-id="57bcf-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57bcf-108">Ważne jest, aby plik wyciągu bankowego z banku pracował do układu obsługiwanego przez Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="57bcf-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="57bcf-109">Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie.</span><span class="sxs-lookup"><span data-stu-id="57bcf-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="57bcf-110">Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki.</span><span class="sxs-lookup"><span data-stu-id="57bcf-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="57bcf-111">Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="57bcf-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="57bcf-112">W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy.</span><span class="sxs-lookup"><span data-stu-id="57bcf-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="57bcf-113">Na czym polega błąd?</span><span class="sxs-lookup"><span data-stu-id="57bcf-113">What is the error?</span></span>
------------------

<span data-ttu-id="57bcf-114">Po próbie zaimportowania pliku wyciągu bankowego przejdź do historii zadania zarządzania danymi i szczegółów wykonania operacji, aby znaleźć błąd.</span><span class="sxs-lookup"><span data-stu-id="57bcf-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="57bcf-115">Błąd może pomóc poprzez wskazane wyciągu, salda lub wiersza wyciągu.</span><span class="sxs-lookup"><span data-stu-id="57bcf-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="57bcf-116">Jednak prawdopodobnie dostarczy za mało informacji, aby pomóc w zidentyfikowaniu pola lub elementu, który jest przyczyną problemu.</span><span class="sxs-lookup"><span data-stu-id="57bcf-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="57bcf-117">Jakie są różnice?</span><span class="sxs-lookup"><span data-stu-id="57bcf-117">What are the differences?</span></span>
<span data-ttu-id="57bcf-118">Porównaj definicję układu pliku bankowego z definicją importu w programie Finance i zapisz wszelkie różnice w polach i elementach.</span><span class="sxs-lookup"><span data-stu-id="57bcf-118">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="57bcf-119">Porównaj plik wyciągu bankowego z powiązanym przykładowym plikiem programu Finance.</span><span class="sxs-lookup"><span data-stu-id="57bcf-119">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="57bcf-120">W plikach ISO20022 wszelkie różnice powinny być dobrze widoczne.</span><span class="sxs-lookup"><span data-stu-id="57bcf-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="57bcf-121">Różnice stref czasowych dla zaimportowanych wyciągów bankowych</span><span class="sxs-lookup"><span data-stu-id="57bcf-121">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="57bcf-122">Wartości daty i godziny w pliku importu mogą się różnić od wartości daty i godziny wyświetlanej w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="57bcf-122">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="57bcf-123">Aby uniknąć tej rozbieżności, należy wprowadzić preferencję dotyczącą strefy czasowej na stronie **Konfigurowanie źródeł danych**.</span><span class="sxs-lookup"><span data-stu-id="57bcf-123">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="57bcf-124">Aby uzyskać więcej informacji o wprowadzaniu preferencji dotyczących strefy czasowej, zapoznaj się z tematem [Konfigurowanie zaawansowanego procesu importu uzgodnień bankowych](set-up-advanced-bank-reconciliation-import-process.md).</span><span class="sxs-lookup"><span data-stu-id="57bcf-124">See [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md) for more information about entering a time zone preference.</span></span>

## <a name="transformations"></a><span data-ttu-id="57bcf-125">Przekształcenia</span><span class="sxs-lookup"><span data-stu-id="57bcf-125">Transformations</span></span>
<span data-ttu-id="57bcf-126">Zazwyczaj zmiany należy dokonać w jednym z trzech przekształceń.</span><span class="sxs-lookup"><span data-stu-id="57bcf-126">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="57bcf-127">Każde przekształcenie jest zapisywane dla określonego standardu.</span><span class="sxs-lookup"><span data-stu-id="57bcf-127">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="57bcf-128">Nazwa zasobu</span><span class="sxs-lookup"><span data-stu-id="57bcf-128">Resource name</span></span>                                         | <span data-ttu-id="57bcf-129">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="57bcf-129">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="57bcf-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="57bcf-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="57bcf-131">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="57bcf-131">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="57bcf-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="57bcf-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="57bcf-133">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="57bcf-133">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="57bcf-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="57bcf-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="57bcf-135">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="57bcf-135">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="57bcf-136">Debugowanie przekształceń</span><span class="sxs-lookup"><span data-stu-id="57bcf-136">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="57bcf-137">Korygowanie plików BAI2 i MT940</span><span class="sxs-lookup"><span data-stu-id="57bcf-137">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="57bcf-138">Pliki BAI2 i MT940 są plikami tekstowymi i wymagają skorygowania, aby umożliwić debugowanie przekształceń Extensible Stylesheet Language Transformation (XSLT).</span><span class="sxs-lookup"><span data-stu-id="57bcf-138">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="57bcf-139">Program dokonuje tej korekty podczas importowania pliku.</span><span class="sxs-lookup"><span data-stu-id="57bcf-139">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="57bcf-140">Utwórz plik XML i skopiuj do niego następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="57bcf-140">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="57bcf-141">Skopiuj zawartość pliku wyciągu bankowego i wkleić ją do pliku XML, tak aby zastąpiła fragment **TUWKLEJPLIKINSTRUKCJI**.</span><span class="sxs-lookup"><span data-stu-id="57bcf-141">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="57bcf-142">Debugowanie przekształcenia XSLT</span><span class="sxs-lookup"><span data-stu-id="57bcf-142">Debug the XSLT</span></span>

<span data-ttu-id="57bcf-143">Aby uzyskać więcej informacji, zobacz <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="57bcf-143">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="57bcf-144">Uruchom Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="57bcf-144">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="57bcf-145">Utwórz aplikację konsoli.</span><span class="sxs-lookup"><span data-stu-id="57bcf-145">Create a console application.</span></span>
3.  <span data-ttu-id="57bcf-146">Otwórz odpowiednie przekształcenie XSLT.</span><span class="sxs-lookup"><span data-stu-id="57bcf-146">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="57bcf-147">Kliknij przekształcenie XLST i jego stronę właściwości.</span><span class="sxs-lookup"><span data-stu-id="57bcf-147">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="57bcf-148">Jako źródło danych wejściowych ustaw lokalizację pliku wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="57bcf-148">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="57bcf-149">Określ lokalizację i nazwę dla danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="57bcf-149">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="57bcf-150">Ustaw wymagane punkty przerwania.</span><span class="sxs-lookup"><span data-stu-id="57bcf-150">Set the required break points.</span></span>
8.  <span data-ttu-id="57bcf-151">W menu kliknij kolejno opcje **XML** &gt; **Rozpocznij debugowanie XSLT**.</span><span class="sxs-lookup"><span data-stu-id="57bcf-151">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="57bcf-152">Formatowanie danych wyjściowych XSLT</span><span class="sxs-lookup"><span data-stu-id="57bcf-152">Format the XSLT output</span></span>

<span data-ttu-id="57bcf-153">Podczas wykonywania przekształcenia jest tworzony plik wyjściowy, który można wyświetlić w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="57bcf-153">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="57bcf-154">Za pomocą kombinacji klawiszy Ctrl+K, Ctrl+D i Ctrl+K można szybko sformatować plik wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="57bcf-154">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="57bcf-155">Korygowanie przekształcenia</span><span class="sxs-lookup"><span data-stu-id="57bcf-155">Adjust the transformation</span></span>

<span data-ttu-id="57bcf-156">Skoryguj przekształcenie, aby uzyskać odpowiednie pole lub element w pliku wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="57bcf-156">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="57bcf-157">Następnie zamapuj to pole lub element do odpowiedniego elementu programu Finance.</span><span class="sxs-lookup"><span data-stu-id="57bcf-157">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="57bcf-158">Wskaźnik debetu/kredytu</span><span class="sxs-lookup"><span data-stu-id="57bcf-158">Debit/credit indicator</span></span>

<span data-ttu-id="57bcf-159">Czasami pozycje debetowe mogą być importowane jako kredytowe, i odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="57bcf-159">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="57bcf-160">Aby rozwiązać ten problem, należy zmienić odpowiednie przekształcenie XSLT.</span><span class="sxs-lookup"><span data-stu-id="57bcf-160">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="57bcf-161">Jeśli wyciągi bankowe pochodzą z wielu banków, upewnij się, że używają takich samych zasad ustalania strony debetowej/kredytowej, albo utwórz oddzielne przekształcenia.</span><span class="sxs-lookup"><span data-stu-id="57bcf-161">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="57bcf-162">Szablon GetAmountCreditDebitIndicator BAI2XML-to-Reconciliation.xlst</span><span class="sxs-lookup"><span data-stu-id="57bcf-162">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="57bcf-163">Szablon GetCreditDebit ISO20022XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="57bcf-163">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="57bcf-164">Szablon operacji GetCreditDebitIndicator MT940XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="57bcf-164">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="57bcf-165">Przykłady formatów i układów technicznych i wyciągów bankowych</span><span class="sxs-lookup"><span data-stu-id="57bcf-165">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="57bcf-166">W tabeli poniżej przedstawiono przykłady definicji układów technicznych plików importu zaawansowanego uzgadniania konta bankowego i trzy powiązane przykładowe pliki wyciągów bankowych.</span><span class="sxs-lookup"><span data-stu-id="57bcf-166">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="57bcf-167">Przykładowe pliki i układy techniczne można pobrać stąd: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="57bcf-167">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="57bcf-168">Definicja układu technicznego</span><span class="sxs-lookup"><span data-stu-id="57bcf-168">Technical layout definition</span></span>                             | <span data-ttu-id="57bcf-169">Przykładowy plik wyciągu bankowego</span><span class="sxs-lookup"><span data-stu-id="57bcf-169">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="57bcf-170">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="57bcf-170">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="57bcf-171">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="57bcf-171">MT940StatementExample</span></span>                |
| <span data-ttu-id="57bcf-172">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="57bcf-172">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="57bcf-173">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="57bcf-173">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="57bcf-174">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="57bcf-174">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="57bcf-175">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="57bcf-175">BAI2StatementExample</span></span>                 |





