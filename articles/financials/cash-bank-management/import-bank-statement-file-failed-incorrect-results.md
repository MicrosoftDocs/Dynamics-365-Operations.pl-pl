---
title: Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego
description: Ważne jest, aby plik wyciągu bankowego z banku pracował do układu obsługiwanego przez Microsoft Dynamics 365 for Finance and Operations. Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie. Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki. Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego. W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4275a4d77b03c55decbf161df8f2115183cac3d6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842408"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="55744-107">Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego</span><span class="sxs-lookup"><span data-stu-id="55744-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55744-108">Ważne jest, aby plik wyciągu bankowego z banku pracował do układu obsługiwanego przez Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55744-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 for Finance and Operations supports.</span></span> <span data-ttu-id="55744-109">Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie.</span><span class="sxs-lookup"><span data-stu-id="55744-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="55744-110">Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki.</span><span class="sxs-lookup"><span data-stu-id="55744-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="55744-111">Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="55744-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="55744-112">W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy.</span><span class="sxs-lookup"><span data-stu-id="55744-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="55744-113">Na czym polega błąd?</span><span class="sxs-lookup"><span data-stu-id="55744-113">What is the error?</span></span>
------------------

<span data-ttu-id="55744-114">Po próbie zaimportowania pliku wyciągu bankowego przejdź do historii zadania zarządzania danymi i szczegółów wykonania operacji, aby znaleźć błąd.</span><span class="sxs-lookup"><span data-stu-id="55744-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="55744-115">Błąd może pomóc poprzez wskazane wyciągu, salda lub wiersza wyciągu.</span><span class="sxs-lookup"><span data-stu-id="55744-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="55744-116">Jednak prawdopodobnie dostarczy za mało informacji, aby pomóc w zidentyfikowaniu pola lub elementu, który jest przyczyną problemu.</span><span class="sxs-lookup"><span data-stu-id="55744-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="55744-117">Jakie są różnice?</span><span class="sxs-lookup"><span data-stu-id="55744-117">What are the differences?</span></span>
<span data-ttu-id="55744-118">Porównaj definicję układu pliku bankowego z definicją importu w programie Finance and Operations i zapisz wszelkie różnice w polach i elementach.</span><span class="sxs-lookup"><span data-stu-id="55744-118">Compare the bank file layout definition to the Finance and Operations import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="55744-119">Porównaj plik wyciągu bankowego z powiązanym przykładowym plikiem programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55744-119">Compare the bank statement file to the related sample Finance and Operations file.</span></span> <span data-ttu-id="55744-120">W plikach ISO20022 wszelkie różnice powinny być dobrze widoczne.</span><span class="sxs-lookup"><span data-stu-id="55744-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="transformations"></a><span data-ttu-id="55744-121">Przekształcenia</span><span class="sxs-lookup"><span data-stu-id="55744-121">Transformations</span></span>
<span data-ttu-id="55744-122">Zazwyczaj zmiany należy dokonać w jednym z trzech przekształceń.</span><span class="sxs-lookup"><span data-stu-id="55744-122">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="55744-123">Każde przekształcenie jest zapisywane dla określonego standardu.</span><span class="sxs-lookup"><span data-stu-id="55744-123">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="55744-124">Nazwa zasobu</span><span class="sxs-lookup"><span data-stu-id="55744-124">Resource name</span></span>                                         | <span data-ttu-id="55744-125">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="55744-125">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="55744-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="55744-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="55744-127">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="55744-127">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="55744-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="55744-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="55744-129">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="55744-129">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="55744-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="55744-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="55744-131">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="55744-131">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="55744-132">Debugowanie przekształceń</span><span class="sxs-lookup"><span data-stu-id="55744-132">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="55744-133">Korygowanie plików BAI2 i MT940</span><span class="sxs-lookup"><span data-stu-id="55744-133">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="55744-134">Pliki BAI2 i MT940 są plikami tekstowymi i wymagają skorygowania, aby umożliwić debugowanie przekształceń Extensible Stylesheet Language Transformation (XSLT).</span><span class="sxs-lookup"><span data-stu-id="55744-134">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="55744-135">Program dokonuje tej korekty podczas importowania pliku.</span><span class="sxs-lookup"><span data-stu-id="55744-135">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="55744-136">Utwórz plik XML i skopiuj do niego następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="55744-136">Create an XML file, and copy the following text into it.</span></span>

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  <span data-ttu-id="55744-137">Skopiuj zawartość pliku wyciągu bankowego i wkleić ją do pliku XML, tak aby zastąpiła fragment **TUWKLEJPLIKINSTRUKCJI**.</span><span class="sxs-lookup"><span data-stu-id="55744-137">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="55744-138">Debugowanie przekształcenia XSLT</span><span class="sxs-lookup"><span data-stu-id="55744-138">Debug the XSLT</span></span>

<span data-ttu-id="55744-139">Aby uzyskać więcej informacji, zobacz <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="55744-139">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="55744-140">Uruchom Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55744-140">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="55744-141">Utwórz aplikację konsoli.</span><span class="sxs-lookup"><span data-stu-id="55744-141">Create a console application.</span></span>
3.  <span data-ttu-id="55744-142">Otwórz odpowiednie przekształcenie XSLT.</span><span class="sxs-lookup"><span data-stu-id="55744-142">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="55744-143">Kliknij przekształcenie XLST i jego stronę właściwości.</span><span class="sxs-lookup"><span data-stu-id="55744-143">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="55744-144">Jako źródło danych wejściowych ustaw lokalizację pliku wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="55744-144">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="55744-145">Określ lokalizację i nazwę dla danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="55744-145">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="55744-146">Ustaw wymagane punkty przerwania.</span><span class="sxs-lookup"><span data-stu-id="55744-146">Set the required break points.</span></span>
8.  <span data-ttu-id="55744-147">W menu kliknij kolejno opcje **XML** &gt; **Rozpocznij debugowanie XSLT**.</span><span class="sxs-lookup"><span data-stu-id="55744-147">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="55744-148">Formatowanie danych wyjściowych XSLT</span><span class="sxs-lookup"><span data-stu-id="55744-148">Format the XSLT output</span></span>

<span data-ttu-id="55744-149">Podczas wykonywania przekształcenia jest tworzony plik wyjściowy, który można wyświetlić w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55744-149">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="55744-150">Za pomocą kombinacji klawiszy Ctrl+K, Ctrl+D i Ctrl+K można szybko sformatować plik wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="55744-150">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="55744-151">Korygowanie przekształcenia</span><span class="sxs-lookup"><span data-stu-id="55744-151">Adjust the transformation</span></span>

<span data-ttu-id="55744-152">Skoryguj przekształcenie, aby uzyskać odpowiednie pole lub element w pliku wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="55744-152">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="55744-153">Następnie zamapuj to pole lub element do odpowiedniego elementu programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55744-153">Then map that field or element to the appropriate Finance and Operations element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="55744-154">Wskaźnik debetu/kredytu</span><span class="sxs-lookup"><span data-stu-id="55744-154">Debit/credit indicator</span></span>

<span data-ttu-id="55744-155">Czasami pozycje debetowe mogą być importowane jako kredytowe, i odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="55744-155">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="55744-156">Aby rozwiązać ten problem, należy zmienić odpowiednie przekształcenie XSLT.</span><span class="sxs-lookup"><span data-stu-id="55744-156">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="55744-157">Jeśli wyciągi bankowe pochodzą z wielu banków, upewnij się, że używają takich samych zasad ustalania strony debetowej/kredytowej, albo utwórz oddzielne przekształcenia.</span><span class="sxs-lookup"><span data-stu-id="55744-157">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="55744-158">Szablon GetAmountCreditDebitIndicator BAI2XML-to-Reconciliation.xlst</span><span class="sxs-lookup"><span data-stu-id="55744-158">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="55744-159">Szablon GetCreditDebit ISO20022XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="55744-159">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="55744-160">Szablon operacji GetCreditDebitIndicator MT940XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="55744-160">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="55744-161">Przykłady formatów i układów technicznych i wyciągów bankowych</span><span class="sxs-lookup"><span data-stu-id="55744-161">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="55744-162">W tabeli poniżej przedstawiono przykłady definicji układów technicznych plików importu zaawansowanego uzgadniania konta bankowego i trzy powiązane przykładowe pliki wyciągów bankowych.</span><span class="sxs-lookup"><span data-stu-id="55744-162">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="55744-163">Przykładowe pliki i układy techniczne można pobrać stąd: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="55744-163">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="55744-164">Definicja układu technicznego</span><span class="sxs-lookup"><span data-stu-id="55744-164">Technical layout definition</span></span>                             | <span data-ttu-id="55744-165">Przykładowy plik wyciągu bankowego</span><span class="sxs-lookup"><span data-stu-id="55744-165">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="55744-166">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="55744-166">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="55744-167">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="55744-167">MT940StatementExample</span></span>                |
| <span data-ttu-id="55744-168">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="55744-168">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="55744-169">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="55744-169">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="55744-170">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="55744-170">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="55744-171">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="55744-171">BAI2StatementExample</span></span>                 |





