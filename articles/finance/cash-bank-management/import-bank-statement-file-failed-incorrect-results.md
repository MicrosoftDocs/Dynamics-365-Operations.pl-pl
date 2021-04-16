---
title: Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego
description: Ważne jest, aby plik wyciągu bankowego z banku pracował do układu obsługiwanego przez Microsoft Dynamics 365 Finance. Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie. Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki. Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego. W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f0e01881a6b68526479d27014d49a718069cffc9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815891"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="d2e21-107">Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego</span><span class="sxs-lookup"><span data-stu-id="d2e21-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2e21-108">Ważne jest, aby plik wyciągu bankowego z banku pracował do układu obsługiwanego przez Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="d2e21-108">It's important that the bank statement file from the bank matches the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="d2e21-109">Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie.</span><span class="sxs-lookup"><span data-stu-id="d2e21-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="d2e21-110">Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki.</span><span class="sxs-lookup"><span data-stu-id="d2e21-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="d2e21-111">Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="d2e21-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="d2e21-112">W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy.</span><span class="sxs-lookup"><span data-stu-id="d2e21-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="d2e21-113">Na czym polega błąd?</span><span class="sxs-lookup"><span data-stu-id="d2e21-113">What is the error?</span></span>
------------------

<span data-ttu-id="d2e21-114">Po próbie zaimportowania pliku wyciągu bankowego przejdź do historii zadania zarządzania danymi i szczegółów wykonania operacji, aby znaleźć błąd.</span><span class="sxs-lookup"><span data-stu-id="d2e21-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="d2e21-115">Błąd może pomóc poprzez wskazane wyciągu, salda lub wiersza wyciągu.</span><span class="sxs-lookup"><span data-stu-id="d2e21-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="d2e21-116">Jednak prawdopodobnie dostarczy za mało informacji, aby pomóc w zidentyfikowaniu pola lub elementu, który jest przyczyną problemu.</span><span class="sxs-lookup"><span data-stu-id="d2e21-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="d2e21-117">Importowane wyciągi bankowe mogą się nakładać tylko dla pojedynczego punktu w czasie.</span><span class="sxs-lookup"><span data-stu-id="d2e21-117">Imported bank statements can overlap only for single a point in time.</span></span>  <span data-ttu-id="d2e21-118">Na przykład, jeśli zestawienie kończy się 1 stycznia 2021 o godzinie 24:00, to datą rozpoczęcia następnego zestawienia może być 12:00 w dniu 1 stycznia 2021 24:00.</span><span class="sxs-lookup"><span data-stu-id="d2e21-118">For example, if a statement ends at 12:00 AM on January 1, 2021, then beginning date for the next statement can be 12:00 AM on Jarnuary 1, 2021 12:00:00 AM.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="d2e21-119">Jakie są różnice?</span><span class="sxs-lookup"><span data-stu-id="d2e21-119">What are the differences?</span></span>
<span data-ttu-id="d2e21-120">Porównaj definicję układu pliku bankowego z definicją importu w programie Finance i zapisz wszelkie różnice w polach i elementach.</span><span class="sxs-lookup"><span data-stu-id="d2e21-120">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="d2e21-121">Porównaj plik wyciągu bankowego z powiązanym przykładowym plikiem programu Finance.</span><span class="sxs-lookup"><span data-stu-id="d2e21-121">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="d2e21-122">W plikach ISO20022 wszelkie różnice powinny być dobrze widoczne.</span><span class="sxs-lookup"><span data-stu-id="d2e21-122">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="d2e21-123">Różnice stref czasowych dla zaimportowanych wyciągów bankowych</span><span class="sxs-lookup"><span data-stu-id="d2e21-123">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="d2e21-124">Wartości daty i godziny w pliku importu mogą się różnić od wartości daty i godziny wyświetlanej w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d2e21-124">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="d2e21-125">Aby uniknąć tej rozbieżności, należy wprowadzić preferencję dotyczącą strefy czasowej na stronie **Konfigurowanie źródeł danych**.</span><span class="sxs-lookup"><span data-stu-id="d2e21-125">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="d2e21-126">Aby uzyskać więcej informacji, zapoznaj się z tematem [Konfigurowanie zaawansowanego procesu importu uzgodnień bankowych](set-up-advanced-bank-reconciliation-import-process.md).</span><span class="sxs-lookup"><span data-stu-id="d2e21-126">For more information about entering a time zone preference, see [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md).</span></span>

## <a name="transformations"></a><span data-ttu-id="d2e21-127">Przekształcenia</span><span class="sxs-lookup"><span data-stu-id="d2e21-127">Transformations</span></span>
<span data-ttu-id="d2e21-128">Zazwyczaj zmiany należy dokonać w jednym z trzech przekształceń.</span><span class="sxs-lookup"><span data-stu-id="d2e21-128">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="d2e21-129">Każde przekształcenie jest zapisywane dla określonego standardu.</span><span class="sxs-lookup"><span data-stu-id="d2e21-129">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="d2e21-130">Nazwa zasobu</span><span class="sxs-lookup"><span data-stu-id="d2e21-130">Resource name</span></span>                                         | <span data-ttu-id="d2e21-131">Nazwa pliku</span><span class="sxs-lookup"><span data-stu-id="d2e21-131">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="d2e21-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="d2e21-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="d2e21-133">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="d2e21-133">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="d2e21-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="d2e21-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="d2e21-135">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="d2e21-135">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="d2e21-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="d2e21-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="d2e21-137">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="d2e21-137">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="d2e21-138">Debugowanie przekształceń</span><span class="sxs-lookup"><span data-stu-id="d2e21-138">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="d2e21-139">Korygowanie plików BAI2 i MT940</span><span class="sxs-lookup"><span data-stu-id="d2e21-139">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="d2e21-140">Pliki BAI2 i MT940 są plikami tekstowymi i wymagają skorygowania, aby umożliwić debugowanie przekształceń Extensible Stylesheet Language Transformation (XSLT).</span><span class="sxs-lookup"><span data-stu-id="d2e21-140">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="d2e21-141">Program dokonuje tej korekty podczas importowania pliku.</span><span class="sxs-lookup"><span data-stu-id="d2e21-141">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="d2e21-142">Utwórz plik XML i skopiuj do niego następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="d2e21-142">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="d2e21-143">Skopiuj zawartość pliku wyciągu bankowego i wkleić ją do pliku XML, tak aby zastąpiła fragment **TUWKLEJPLIKINSTRUKCJI**.</span><span class="sxs-lookup"><span data-stu-id="d2e21-143">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="d2e21-144">Debugowanie przekształcenia XSLT</span><span class="sxs-lookup"><span data-stu-id="d2e21-144">Debug the XSLT</span></span>

<span data-ttu-id="d2e21-145">Aby uzyskać więcej informacji, zobacz <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="d2e21-145">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="d2e21-146">Uruchom Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d2e21-146">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="d2e21-147">Utwórz aplikację konsoli.</span><span class="sxs-lookup"><span data-stu-id="d2e21-147">Create a console application.</span></span>
3.  <span data-ttu-id="d2e21-148">Otwórz odpowiednie przekształcenie XSLT.</span><span class="sxs-lookup"><span data-stu-id="d2e21-148">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="d2e21-149">Kliknij przekształcenie XLST i jego stronę właściwości.</span><span class="sxs-lookup"><span data-stu-id="d2e21-149">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="d2e21-150">Jako źródło danych wejściowych ustaw lokalizację pliku wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="d2e21-150">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="d2e21-151">Określ lokalizację i nazwę dla danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="d2e21-151">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="d2e21-152">Ustaw wymagane punkty przerwania.</span><span class="sxs-lookup"><span data-stu-id="d2e21-152">Set the required break points.</span></span>
8.  <span data-ttu-id="d2e21-153">W menu kliknij kolejno opcje **XML** &gt; **Rozpocznij debugowanie XSLT**.</span><span class="sxs-lookup"><span data-stu-id="d2e21-153">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="d2e21-154">Formatowanie danych wyjściowych XSLT</span><span class="sxs-lookup"><span data-stu-id="d2e21-154">Format the XSLT output</span></span>

<span data-ttu-id="d2e21-155">Podczas wykonywania przekształcenia jest tworzony plik wyjściowy, który można wyświetlić w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d2e21-155">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="d2e21-156">Za pomocą kombinacji klawiszy Ctrl+K, Ctrl+D i Ctrl+K można szybko sformatować plik wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="d2e21-156">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="d2e21-157">Korygowanie przekształcenia</span><span class="sxs-lookup"><span data-stu-id="d2e21-157">Adjust the transformation</span></span>

<span data-ttu-id="d2e21-158">Skoryguj przekształcenie, aby uzyskać odpowiednie pole lub element w pliku wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="d2e21-158">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="d2e21-159">Następnie zamapuj to pole lub element do odpowiedniego elementu programu Finance.</span><span class="sxs-lookup"><span data-stu-id="d2e21-159">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="d2e21-160">Wskaźnik debetu/kredytu</span><span class="sxs-lookup"><span data-stu-id="d2e21-160">Debit/credit indicator</span></span>

<span data-ttu-id="d2e21-161">Czasami pozycje debetowe mogą być importowane jako kredytowe, i odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="d2e21-161">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="d2e21-162">Aby rozwiązać ten problem, należy zmienić odpowiednie przekształcenie XSLT.</span><span class="sxs-lookup"><span data-stu-id="d2e21-162">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="d2e21-163">Jeśli wyciągi bankowe pochodzą z wielu banków, upewnij się, że używają takich samych zasad ustalania strony debetowej/kredytowej, albo utwórz oddzielne przekształcenia.</span><span class="sxs-lookup"><span data-stu-id="d2e21-163">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="d2e21-164">Szablon GetAmountCreditDebitIndicator BAI2XML-to-Reconciliation.xlst</span><span class="sxs-lookup"><span data-stu-id="d2e21-164">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="d2e21-165">Szablon GetCreditDebit ISO20022XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="d2e21-165">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="d2e21-166">Szablon operacji GetCreditDebitIndicator MT940XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="d2e21-166">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="d2e21-167">Przykłady formatów i układów technicznych i wyciągów bankowych</span><span class="sxs-lookup"><span data-stu-id="d2e21-167">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="d2e21-168">W tabeli poniżej przedstawiono przykłady definicji układów technicznych plików importu zaawansowanego uzgadniania konta bankowego i trzy powiązane przykładowe pliki wyciągów bankowych.</span><span class="sxs-lookup"><span data-stu-id="d2e21-168">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="d2e21-169">Przykładowe pliki i układy techniczne można pobrać stąd: [Importownaie plików przykładowych](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span><span class="sxs-lookup"><span data-stu-id="d2e21-169">You can download the example files and technical layouts here: [Import file examples](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span></span>  

| <span data-ttu-id="d2e21-170">Definicja układu technicznego</span><span class="sxs-lookup"><span data-stu-id="d2e21-170">Technical layout definition</span></span>                             | <span data-ttu-id="d2e21-171">Przykładowy plik wyciągu bankowego</span><span class="sxs-lookup"><span data-stu-id="d2e21-171">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="d2e21-172">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="d2e21-172">DynamicsAXMT940Layout</span></span>                                   | [<span data-ttu-id="d2e21-173">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="d2e21-173">MT940StatementExample</span></span>](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| <span data-ttu-id="d2e21-174">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="d2e21-174">DynamicsAXISO20022Layout</span></span>                                | [<span data-ttu-id="d2e21-175">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="d2e21-175">ISO20022StatementExample</span></span>](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| <span data-ttu-id="d2e21-176">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="d2e21-176">DynamicsAXBAI2Layout</span></span>                                    | [<span data-ttu-id="d2e21-177">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="d2e21-177">BAI2StatementExample</span></span>](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
