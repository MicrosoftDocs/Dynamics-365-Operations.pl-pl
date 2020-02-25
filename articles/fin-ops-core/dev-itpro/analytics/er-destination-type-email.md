---
title: Typ miejsca docelowego raportowania elektronicznego (ER)
description: Ten temat zawiera informacje dotyczące konfigurowania lokalizacji docelowej e-mail dla poszczególnych składników FOLDER lub FILE formatu sprawozdawczości elektronicznej (ER) skonfigurowanych do generowania dokumentów wychodzących.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 086114d6a8d425ca01521d9607e4a70ec5aa766b
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019946"
---
# <span data-ttu-id="d1900-103"><a name="EmailDestinationType">Pocztowe miejsce docelowe</a></span><span class="sxs-lookup"><span data-stu-id="d1900-103"><a name="EmailDestinationType">Email destination</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1900-104">Możesz konfigurować lokalizacje docelową e-mail dla poszczególnych składników FOLDER lub FILE formatu sprawozdawczości elektronicznej (ER) skonfigurowanych do generowania dokumentów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="d1900-104">You can configure an email destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="d1900-105">Na podstawie ustawienia lokalizacji docelowej wygenerowany dokument jest dostarczony jako załącznik do rekordu listy zadań ER.</span><span class="sxs-lookup"><span data-stu-id="d1900-105">Based on the destination setting, a generated document is delivered as an attachment of an electronic mail.</span></span>

<span data-ttu-id="d1900-106">W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać plik wyjściowy pocztą e-mail.</span><span class="sxs-lookup"><span data-stu-id="d1900-106">Set **Enabled** to **Yes** to send an output file by email.</span></span> <span data-ttu-id="d1900-107">Po włączeniu tej opcji można określić adresatów wiadomości e-mail oraz edytować jej temat i treść.</span><span class="sxs-lookup"><span data-stu-id="d1900-107">After this option is enabled, you can specify the email recipients and edit the subject and body of the email message.</span></span> <span data-ttu-id="d1900-108">Można zdefiniować stałe teksty tematu i treści wiadomości e-mail lub używać [formuł](er-formula-language.md) ER w celu dynamicznego tworzenia tekstów wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="d1900-108">You can set up constant texts for the email subject and body, or you can use ER [formulas](er-formula-language.md) to dynamically create email texts.</span></span> 

<span data-ttu-id="d1900-109">Adresy e-mail dla modułu ER można konfigurować na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="d1900-109">You can configure email addresses for ER in two ways.</span></span> <span data-ttu-id="d1900-110">Konfigurację można wykonać w taki sam sposób, aby funkcja zarządzania drukowaniem kończyła się lub można było rozpoznać adres e-mail za pomocą bezpośredniego odwołania do konfiguracji ER, korzystając z formuły.</span><span class="sxs-lookup"><span data-stu-id="d1900-110">The configuration can be completed in the same way that the Print management feature completes it, or you can resolve an email address by using a direct reference to the ER configuration through a formula.</span></span>

<span data-ttu-id="d1900-111">[![Uruchom miejsce docelowe e-mail](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span><span class="sxs-lookup"><span data-stu-id="d1900-111">[![Enable email destination](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span></span>

## <a name="email-address-types"></a><span data-ttu-id="d1900-112">Typy adresów e-mail</span><span class="sxs-lookup"><span data-stu-id="d1900-112">Email address types</span></span>

<span data-ttu-id="d1900-113">Po kliknięciu przycisku **Edytuj** dla pola **Do** lub **DW** pojawi się okno dialogowe **Wiadomość e-mail do**.</span><span class="sxs-lookup"><span data-stu-id="d1900-113">When you select **Edit** in the **To** or **Cc** fields, the **Email to** dialog box appears.</span></span> <span data-ttu-id="d1900-114">Następnie można wybrać typ adresu e-mail, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="d1900-114">You can then select the type of email address to use.</span></span> <span data-ttu-id="d1900-115">Typy **Wiadomości e-mail konfiguracji** oraz **Zarządzanie drukowaniem** są obecnie obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="d1900-115">The **Configuration email** and **Print Management** email types are currently supported.</span></span>

<span data-ttu-id="d1900-116">[![Wybierz typ wiadomości e-mail](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span><span class="sxs-lookup"><span data-stu-id="d1900-116">[![Select email type](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span></span>

### <a name="print-management"></a><span data-ttu-id="d1900-117">Zarządzanie drukowaniem</span><span class="sxs-lookup"><span data-stu-id="d1900-117">Print management</span></span>

<span data-ttu-id="d1900-118">Jeśli wybierzesz typ wiadomości e-mail w opcji **Zarządzania drukowaniem**, można wprowadzić stałe adresy e-mail w polu **Do**.</span><span class="sxs-lookup"><span data-stu-id="d1900-118">If you select the **Print Management** email type, you can enter fixed email addresses in the **To** field.</span></span> 

<span data-ttu-id="d1900-119">[![Konfigurowanie stałych adresów e-mail](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span><span class="sxs-lookup"><span data-stu-id="d1900-119">[![Configure fixed email addresses](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span></span>

<span data-ttu-id="d1900-120">Aby używać adresów e-mail, które nie są stałe, należy wybrać typ źródła wiadomości e-mail dla plikowego miejsca docelowego.</span><span class="sxs-lookup"><span data-stu-id="d1900-120">To use email addresses that aren't fixed, you must select the email source type for a file destination.</span></span> <span data-ttu-id="d1900-121">Obsługiwane są następujące wartości: **Odbiorca**, **Dostawca**, **Prospekt**, **Kontakt**, **Konkurent**, **Pracownik**, **Kandydat**, **Potencjalny dostawca** i **Niezatwierdzony dostawca**.</span><span class="sxs-lookup"><span data-stu-id="d1900-121">The following values are supported: **Customer**, **Vendor**, **Prospect**, **Contact**, **Competitor**, **Worker**, **Applicant**, **Prospective vendor**, and **Disallowed vendor**.</span></span> <span data-ttu-id="d1900-122">Po wybraniu typu źródła wiadomości e-mail użyj przycisku obok pola **Konto źródłowe poczty e-mail**, aby otworzyć formularz **Projektant formuł**.</span><span class="sxs-lookup"><span data-stu-id="d1900-122">After you select an email source type, use the button next to the **Email source account** field to open the **Formula designer** form.</span></span> <span data-ttu-id="d1900-123">Ten formularz umożliwia dołączenie formuły, która zwraca się w czasie wykonywania, **konta strony** wybranego typu źródła z przetworzonego dokumentu do miejsca docelowego poczty e-mail.</span><span class="sxs-lookup"><span data-stu-id="d1900-123">You can use this form to attach a formula that returns at runtime, the **party account** of the selected source type from the processed document to the email destination.</span></span>

<span data-ttu-id="d1900-124">[![Konfiguruj konto źródłowe poczty e-mail](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span><span class="sxs-lookup"><span data-stu-id="d1900-124">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span></span>

<span data-ttu-id="d1900-125">Formuły są specyficzne dla konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="d1900-125">Formulas are specific to the ER configuration.</span></span> <span data-ttu-id="d1900-126">W polu **Formuła** wprowadź specyficzne dla dokumentu odwołanie do podmiotu typu Odbiorca lub Dostawca.</span><span class="sxs-lookup"><span data-stu-id="d1900-126">In the **Formula** field, enter a document-specific reference to a customer or vendor party type.</span></span> <span data-ttu-id="d1900-127">Zamiast wpisywać informacje ręcznie, można odszukać węzeł źródła danych reprezentujący konto odbiorcy lub dostawcy, a następnie wybrać przycisk **Dodaj źródło danych**, aby zaktualizować formułę.</span><span class="sxs-lookup"><span data-stu-id="d1900-127">Instead of typing, you can find the data source node that represents the customer or vendor account, and then select **Add data source** to update the formula.</span></span> <span data-ttu-id="d1900-128">Na przykład jeśli używasz konfiguracji **przelewu bankowego ISO 20022**, węzłem reprezentującym konto dostawcy jest `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span><span class="sxs-lookup"><span data-stu-id="d1900-128">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents a vendor account is `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span></span>

<span data-ttu-id="d1900-129">Jeśli wprowadzisz wartość ciągu, na przykład `"DE-001"`, i zapiszesz formułę, wiadomość zostanie wysłana do osoby kontaktowej dla dostawcy **DE-001**.</span><span class="sxs-lookup"><span data-stu-id="d1900-129">If you enter a string value, such as `"DE-001"`, and save a formula, an email will be sent to the contact person of the vendor, **DE-001**.</span></span>


<span data-ttu-id="d1900-130">[![Strona projektanta formuł ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span><span class="sxs-lookup"><span data-stu-id="d1900-130">[![ER formula designer page](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span></span>

<span data-ttu-id="d1900-131">[![Konfiguruj konto źródłowe poczty e-mail](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span><span class="sxs-lookup"><span data-stu-id="d1900-131">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span></span>



### <a name="configuration-email"></a><span data-ttu-id="d1900-132">Adres e-mail konfiguracji</span><span class="sxs-lookup"><span data-stu-id="d1900-132">Configuration email</span></span>

<span data-ttu-id="d1900-133">Użyj tego typu wiadomości e-mail, jeśli używana konfiguracja ma w źródłach danych węzeł zwracający **adres e-mail**.</span><span class="sxs-lookup"><span data-stu-id="d1900-133">Use this email type if the configuration that you use has a node in the data sources that returns an **email address**.</span></span> <span data-ttu-id="d1900-134">W projektancie formuł można użyć źródeł danych i funkcji, aby uzyskać poprawnie sformatowany adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="d1900-134">You can use data sources and functions in the formula designer to get a correctly formatted email address.</span></span> <span data-ttu-id="d1900-135">Na przykład jeśli używasz konfiguracji **przelewu bankowego ISO 20022**, węzłem reprezentującym adres e-mail osoby kontaktowej dostawcy jest `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span><span class="sxs-lookup"><span data-stu-id="d1900-135">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents an email address of a vendor's contact person is `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span></span>

<span data-ttu-id="d1900-136">[![Konfiguruj adres źródłowy poczty e-mail](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span><span class="sxs-lookup"><span data-stu-id="d1900-136">[![Configure email address source](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d1900-137">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d1900-137">Additional resources</span></span>

- [<span data-ttu-id="d1900-138">Omówienie raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="d1900-138">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="d1900-139">Miejsca docelowe raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="d1900-139">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="d1900-140">Projektant formuł w module Raportowanie elektroniczne (ER)</span><span class="sxs-lookup"><span data-stu-id="d1900-140">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
