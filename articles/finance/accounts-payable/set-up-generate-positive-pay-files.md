---
title: Konfigurowanie i generowanie plików płatności dodatnich
description: W tym temacie wyjaśniono, jak konfigurować płatności dodatnie i generować pliki płatności dodatnich.
author: panolte
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 9f96e34b8d94f9e83afb39d6ad97aca85386b458
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830719"
---
# <a name="set-up-and-generate-positive-pay-files"></a><span data-ttu-id="ad0e7-103">Konfigurowanie i generowanie plików płatności dodatnich</span><span class="sxs-lookup"><span data-stu-id="ad0e7-103">Set up and generate positive pay files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad0e7-104">W tym temacie wyjaśniono, jak konfigurować płatności dodatnie i generować pliki płatności dodatnich.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-104">This topic explains how to set up positive pay and generate positive pay files.</span></span> 

<span data-ttu-id="ad0e7-105">Konfigurowanie płatności dodatnich w celu generowania elektronicznej listy czeków dostarczanych do banku.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-105">Set up positive pay to generate an electronic list of checks that is provided to the bank.</span></span> <span data-ttu-id="ad0e7-106">Gdy czek zostanie przekazany do banku, bank porównuje go z listą czeków.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-106">Then, when a check is presented to the bank, the bank compares it with the list of checks.</span></span> <span data-ttu-id="ad0e7-107">Jeśli czek pasuje do czeku na liście, wówczas bank rozlicza czek.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-107">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="ad0e7-108">Jeśli czek nie pasuje do czeku na liście, bank wstrzymuje czek w celu sprawdzenia.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-108">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

## <a name="security-for-positive-pay-files"></a><span data-ttu-id="ad0e7-109">Zabezpieczenia plików płatności dodatnich</span><span class="sxs-lookup"><span data-stu-id="ad0e7-109">Security for positive pay files</span></span>
<span data-ttu-id="ad0e7-110">Pliki płatności dodatnich mogą zawierać poufne informacje na temat odbiorców płatności i kwot czeków.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-110">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="ad0e7-111">W związku z tym musisz podjąć odpowiednie środki bezpieczeństwa od momentu wygenerowania plików aż do ich odbioru przez bank.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-111">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="ad0e7-112">Pliki płatności dodatnich są pobierane do lokalizacji określonej przez przeglądarkę internetową.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-112">Positive pay files are downloaded to the location that is specified by your web browser.</span></span> <span data-ttu-id="ad0e7-113">Ponieważ pliki płatności dodatnich mogą zawierać informacje poufne, ważne jest, aby tylko upoważnieni użytkownicy mieli dostęp umożliwiający generowanie i wyświetlanie tych informacji w usłudze Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-113">Because positive pay files can contain sensitive information, it's important that only authorized users have access to generate and view this information in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="ad0e7-114">Poniższa tabela pomaga określić uprawnienia, które są wymagane.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-114">Use the following table to help you determine the privileges that are required.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad0e7-115">Zadanie</span><span class="sxs-lookup"><span data-stu-id="ad0e7-115">Task</span></span></th>
<th><span data-ttu-id="ad0e7-116">Uprawnienie</span><span class="sxs-lookup"><span data-stu-id="ad0e7-116">Privilege</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ad0e7-117">Generowanie plików płatności dodatnich ze strony listy <strong>Konta bankowe</strong> lub strony <strong>Konta bankowe</strong>.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-117">Generate positive pay files from the <strong>Bank accounts</strong> list page or the <strong>Bank accounts</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="ad0e7-118"><strong>Obsługa informacji o bankowych płatnościach dodatnich</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="ad0e7-118"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="ad0e7-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="ad0e7-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ad0e7-120">Generowanie plików płatności dodatnich dla wielu firm i kont bankowych ze strony <strong>Generuj plik płatności dodatnich</strong>.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-120">Generate positive pay files for multiple legal entities and bank accounts from the <strong>Generate a positive pay file</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="ad0e7-121"><strong>Obsługa informacji o bankowych płatnościach dodatnich</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="ad0e7-121"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="ad0e7-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="ad0e7-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ad0e7-123">Wyświetlanie plików płatności dodatnich na stronie <strong>Podsumowanie pliku płatności dodatnich</strong>.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-123">View positive pay files on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="ad0e7-124"><strong>Wyświetl informacje o bankowych płatnościach dodatnich wielu firm</strong> (BankPositivePayView)</span><span class="sxs-lookup"><span data-stu-id="ad0e7-124"><strong>View bank positive pay information for multiple legal entities</strong> (BankPositivePayView)</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ad0e7-125">Potwierdzanie pliku płatności dodatnich na stronie <strong>Podsumowanie pliku płatności dodatnich</strong>.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-125">Confirm a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="ad0e7-126"><strong>Potwierdź plik płatności dodatnich</strong> (BankPositivePayConfirm)</span><span class="sxs-lookup"><span data-stu-id="ad0e7-126"><strong>Confirm positive payment file</strong> (BankPositivePayConfirm)</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ad0e7-127">Wycofywanie pliku płatności dodatnich na stronie <strong>Podsumowanie pliku płatności dodatnich</strong>.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-127">Recall a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="ad0e7-128"><strong>Odwołaj plik płatności dodatnich</strong> (BankPositivePayRecall)</span><span class="sxs-lookup"><span data-stu-id="ad0e7-128"><strong>Recall positive pay file</strong> (BankPositivePayRecall)</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a><span data-ttu-id="ad0e7-129">Konfigurowanie formatu płatności dodatnich</span><span class="sxs-lookup"><span data-stu-id="ad0e7-129">Set up a positive pay format</span></span>
<span data-ttu-id="ad0e7-130">Pliki płatności dodatnich tworzy się za pomocą jednostek danych.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-130">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="ad0e7-131">Zanim będzie można wygenerować plik płatności dodatnich, należy zdefiniować format danych wejściowych przekształcenia, który będzie używany do translacji danych czeku na format umożliwiający komunikację z bankiem.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-131">Before you can generate a positive pay file, you must set up a transformation input format that will be used to translate the check information into a format that can communicate with the bank.</span></span> <span data-ttu-id="ad0e7-132">Na stronie **Format płatności dodatnich** można utworzyć identyfikator i opis formatu pliku.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-132">On the **Positive pay format** page, you can create a file format identifier and a description.</span></span> <span data-ttu-id="ad0e7-133">Format danych wejściowych przekształcenia musi być typu XML</span><span class="sxs-lookup"><span data-stu-id="ad0e7-133">The transformation input format must be of the XML type.</span></span> <span data-ttu-id="ad0e7-134">Konkretny format zależy od używanego pliku przekształcenia.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-134">The specific format depends on the transformation file that you're using.</span></span> <span data-ttu-id="ad0e7-135">Na przykład dołączony testowy plik XSLT (Extensible Stylesheet Language Transformations) używa formatu **XML-Element**.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-135">For example, the sample Extensible Stylesheet Language Transformations (XSLT) file that is provided uses the **XML-Element** format.</span></span> <span data-ttu-id="ad0e7-136">Użyj akcji **Przekaż plik używany na potrzeby przekształcenia**, aby określić lokalizację pliku przekształcenia dla formatu wymaganego przez bank.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-136">Use the **Upload file used for transformation** action to specify the location of the transform file for the format that your bank requires.</span></span>

## <a name="example-xslt-file-for-positive-pay-file"></a><span data-ttu-id="ad0e7-137">Przykład: Plik płatności dodatnich typu XSLT</span><span class="sxs-lookup"><span data-stu-id="ad0e7-137">Example: XSLT file for positive pay file</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
  <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
  <xsl:template match="/">
    <xsl:value-of select="'
'" />
    <Document>
      <xsl:value-of select="'
'" />
      <!--Header Begin-->
      <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
      <xsl:value-of select="'
'" />
      <!--Header End-->
      <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
        <!--Cheque Detail begin-->
        <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
            <xsl:value-of select='string("Yes")'/>
          </xsl:when>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
            <xsl:value-of select='string("No")'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='string(" ")'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("Payment")'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='CHEQUENUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='AMOUNTCUR/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("BOA-#1812")'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
            <xsl:value-of select='VENDGROUP/text()'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='CUSTGROUP/text()'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="'
'" />
      </xsl:for-each>
    </Document>
  </xsl:template>
</xsl:stylesheet>
```

> [!NOTE]
> <span data-ttu-id="ad0e7-138">Nazwy XML w pliku XSLT muszą być zgodne z nazwami w węzłach w pliku XML.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-138">XML names in the XSLT must match the casing of the nodes in the XML.</span></span> <span data-ttu-id="ad0e7-139">Wielkość liter jest rozróżniana zarówno w plikach XSLT, jak i XML.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-139">Both the XSLT and XML files are case sensitive.</span></span> 

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a><span data-ttu-id="ad0e7-140">Przypisywanie formatu płatności dodatnich do konta bankowego</span><span class="sxs-lookup"><span data-stu-id="ad0e7-140">Assign the positive pay format to a bank account</span></span>
<span data-ttu-id="ad0e7-141">Dla każdego konta bankowego, dla którego chcesz wygenerować informacje o płatnościach dodatnich, należy przypisać format płatności dodatnich, który został określony w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-141">For each bank account that you want to generate positive pay information for, you must assign the positive pay format that you specified in the previous section.</span></span> <span data-ttu-id="ad0e7-142">Na stronie **Konta bankowe** zaznacz format płatności dodatnich odpowiadający kontu bankowemu.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-142">On the **Bank accounts** page, select the positive pay format that corresponds to the bank account.</span></span> <span data-ttu-id="ad0e7-143">W polu **Data początkowa płatności dodatnich** wprowadź pierwszą datę dla generowania plików płatności dodatnich.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-143">In the **Positive pay start date** field, enter the first date to generate positive pay files.</span></span> <span data-ttu-id="ad0e7-144">Wypełnienie tego pola jest bardzo ważne.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-144">It's important that you enter a date in this field.</span></span> <span data-ttu-id="ad0e7-145">W przeciwnym razie pierwszy generowany plik płatności dodatnich będzie obejmował wszystkie czeki, które zostały utworzone dla tego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-145">Otherwise, the first positive pay file that you generate will include all checks that have ever been created for this bank account.</span></span>

## <a name="assign-a-number-sequence-for-positive-pay-files"></a><span data-ttu-id="ad0e7-146">Konfigurowanie sekwencji identyfikatorów plików płatności dodatnich</span><span class="sxs-lookup"><span data-stu-id="ad0e7-146">Assign a number sequence for positive pay files</span></span>
<span data-ttu-id="ad0e7-147">Każdy plik płatności dodatnich musi mieć unikatowy numer.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-147">Each positive pay file must have a unique number.</span></span> <span data-ttu-id="ad0e7-148">Na karcie **Sekwencje identyfikatorów** na stronie **Parametry modułu Zarządzanie gotówką i bankami** utwórz sekwencję identyfikatorów plików płatności dodatnich.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-148">Use the **Number sequences** tab on the **Cash and bank management parameters** page to create a number sequence for positive pay files.</span></span>

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a><span data-ttu-id="ad0e7-149">Generowanie pliku płatności dodatnich dla jednego konta bankowego</span><span class="sxs-lookup"><span data-stu-id="ad0e7-149">Generate a positive pay file for a single bank account</span></span>
<span data-ttu-id="ad0e7-150">Można wygenerować plik płatności dodatnich dla pojedynczej firmy i pojedynczego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-150">You can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="ad0e7-151">Informacje o generowaniu plików płatności dodatnich dla wielu firm i kont bankowych w tym samym czasie znajdują się w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-151">For information about how to generate positive pay files for multiple legal entities and bank accounts at the same time, see the next section.</span></span> <span data-ttu-id="ad0e7-152">Aby wygenerować plik płatności dodatnich dla jednej firmy i jednego konta bankowego, ze strony **Konta bankowe** otwórz okno dialogowe **Generuj plik płatności dodatnich**.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-152">To generate a positive pay file for a single legal entity and a single bank account, open the **Generate a positive pay file** dialog box from the **Bank accounts** page.</span></span> <span data-ttu-id="ad0e7-153">W polu **Data graniczna** wprowadź ostatnią datę czeku do uwzględnienia w pliku płatności dodatnich.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-153">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="ad0e7-154">Wszystkie czeki, które jeszcze nie zostały uwzględnione w pliku płatności dodatnich do tej daty czeku, znajdą się w pliku.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-154">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a><span data-ttu-id="ad0e7-155">Generowanie pliku płatności dodatnich dla wielu kont bankowych</span><span class="sxs-lookup"><span data-stu-id="ad0e7-155">Generate a positive pay file for multiple bank accounts</span></span>
<span data-ttu-id="ad0e7-156">Aby wygenerować plik płatności dodatnich dla wielu kont bankowych, użyj zadania okresowego **Generuj plik płatności dodatnich**.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-156">To generate a positive pay file for multiple bank accounts, use the **Generate a positive pay file** periodic task.</span></span> <span data-ttu-id="ad0e7-157">Wybierz format pliku płatności dodatnich oraz określ, czy wygenerować plik dla wszystkich firm, czy tylko dla wybranej firmy.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-157">Select the positive pay format for the file, and specify whether to generate the file for all legal entities or for a selected legal entity.</span></span> <span data-ttu-id="ad0e7-158">Można również wygenerować plik płatności dodatnich dla wszystkich kont bankowych używających określonego formatu płatności dodatnich albo tylko dla wybranego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-158">You can also generate the positive pay file for all bank accounts that use the specified positive pay format or for a selected bank account.</span></span> <span data-ttu-id="ad0e7-159">W polu **Data graniczna** wprowadź ostatnią datę czeku do uwzględnienia w pliku płatności dodatnich.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-159">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="ad0e7-160">Wszystkie czeki, które jeszcze nie zostały uwzględnione w pliku płatności dodatnich do tej daty czeku, znajdą się w pliku.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-160">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="view-the-results-of-positive-pay-file-generation"></a><span data-ttu-id="ad0e7-161">Wyświetlanie wyników generowania pliku płatności dodatnich</span><span class="sxs-lookup"><span data-stu-id="ad0e7-161">View the results of positive pay file generation</span></span>
<span data-ttu-id="ad0e7-162">Po wygenerowaniu pliku płatności dodatnich wyniki można obejrzeć na stronie **Podsumowanie pliku płatności dodatnich**.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-162">After the positive pay file is generated, you can view the results on the **Positive pay file summary** page.</span></span> <span data-ttu-id="ad0e7-163">Aby wyświetlić szczegółowe informacje o poszczególnych czekach, należy użyć strony szczegółów **Plik płatności dodatnich**.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-163">To view the details of the individual checks, use the **Positive pay file** details page.</span></span>

## <a name="confirm-a-positive-pay-file"></a><span data-ttu-id="ad0e7-164">Potwierdź plik płatności dodatnich</span><span class="sxs-lookup"><span data-stu-id="ad0e7-164">Confirm a positive pay file</span></span>
<span data-ttu-id="ad0e7-165">Po zapłaceniu czeków wymienionych w pliku płatności dodatnich, otrzymasz numer potwierdzenia z banku.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-165">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="ad0e7-166">Wtedy można potwierdzić plik płatności dodatnich.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-166">You can then confirm the positive pay file.</span></span> <span data-ttu-id="ad0e7-167">Na stronie **Podsumowanie pliku płatności dodatnich** zaznacz plik płatności dodatnich, który ma stan **Utworzone**, a następnie wybierz akcję **Wprowadź potwierdzenie**.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-167">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Enter confirmation** action.</span></span> <span data-ttu-id="ad0e7-168">Po potwierdzeniu pliku płatności dodatnich następuje odnotowanie numeru potwierdzenia otrzymanego z banku.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-168">When you confirm a positive pay file, the confirmation number that you received from the bank is recorded.</span></span>

## <a name="recall-a-positive-pay-file"></a><span data-ttu-id="ad0e7-169">Odwoływanie pliku płatności dodatnich</span><span class="sxs-lookup"><span data-stu-id="ad0e7-169">Recall a positive pay file</span></span>
<span data-ttu-id="ad0e7-170">Jeśli trzeba zmodyfikować plik płatności dodatnich, można go wycofać.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-170">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="ad0e7-171">Na stronie **Podsumowanie pliku płatności dodatnich** zaznacz plik płatności dodatnich, który ma stan **Utworzone**, a następnie wybierz akcję **Wycofaj**.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-171">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Recall** action.</span></span> <span data-ttu-id="ad0e7-172">Dla każdego czeku w pliku płatności dodatnich jest resetowane pole wskazujące, czy czek jest uwzględniony w pliku płatności dodatnich.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-172">For each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span> <span data-ttu-id="ad0e7-173">Następnie można utworzyć nowy plik płatności dodatnich zawierający wycofany czek.</span><span class="sxs-lookup"><span data-stu-id="ad0e7-173">You can then create a new positive pay file that includes the check that was recalled.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
