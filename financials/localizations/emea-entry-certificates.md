---
title: "Świadectwa wywozowe UE"
description: "Ten artykuł zawiera informacje dotyczące świadectw wywozowych umożliwiających wprowadzanie towarów na teren Unii Europejskiej (UE)."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 11464
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 6856a52ce85d31c4ef8225e56159e8a7ec698fd7
ms.contentlocale: pl-pl
ms.lasthandoff: 06/29/2017


---

# <a name="eu-entry-certificates"></a><span data-ttu-id="078ab-103">Świadectwa wywozowe UE</span><span class="sxs-lookup"><span data-stu-id="078ab-103">EU entry certificates</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="078ab-104">Ten artykuł zawiera informacje dotyczące świadectw wywozowych umożliwiających wprowadzanie towarów na teren Unii Europejskiej (UE).</span><span class="sxs-lookup"><span data-stu-id="078ab-104">This article provides information about European Union (EU) entry certificates.</span></span>

<span data-ttu-id="078ab-105">Można wykonać następujące zadania dla świadectwa wywozowego Unii Europejskiej (UE):</span><span class="sxs-lookup"><span data-stu-id="078ab-105">You can complete the following tasks for a European Union (EU) entry certificate:</span></span>

-   <span data-ttu-id="078ab-106">Tworzenie i wystawianie świadectwa wywozowego UE wraz z dokumentem faktury odbiorcy lub dokumentem dostawy towarów lub świadczenia usług do krajów/regionów UE.</span><span class="sxs-lookup"><span data-stu-id="078ab-106">Create and issue an EU entry certificate together with a packing slip or customer invoice for the delivery of items or services to EU countries/regions.</span></span>
-   <span data-ttu-id="078ab-107">Odbieranie świadectwa wywozowego UE podpisanego przez odbiorcę z UE.</span><span class="sxs-lookup"><span data-stu-id="078ab-107">Receive the EU entry certificate that is signed by an EU customer.</span></span>
-   <span data-ttu-id="078ab-108">Przesyłanie podpisanego świadectwa wywozowego UE otrzymanego od odbiorcy lub od osób trzecich, które są odpowiedzialne za dostarczanie towarów do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="078ab-108">Upload the signed EU entry certificate that is received either from the customer or from a third party who is responsible for delivering items to the customer.</span></span>
-   <span data-ttu-id="078ab-109">Kojarzenie przesłanego świadectwa wywozowego UE z fakturą dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="078ab-109">Associate the uploaded EU entry certificate with a customer invoice.</span></span>
-   <span data-ttu-id="078ab-110">Aktualizowanie stanu przesłanego świadectwa wywozowego UE.</span><span class="sxs-lookup"><span data-stu-id="078ab-110">Update the status of the uploaded EU entry certificate.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="078ab-111">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="078ab-111">Prerequisites</span></span>
<span data-ttu-id="078ab-112">W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="078ab-112">The following table shows the prerequisites that must be in place before you start.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="078ab-113">Kategoria</span><span class="sxs-lookup"><span data-stu-id="078ab-113">Category</span></span></th>
<th><span data-ttu-id="078ab-114">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="078ab-114">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="078ab-115">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="078ab-115">Country/region</span></span></td>
<td><span data-ttu-id="078ab-116">Podstawowy adres firmy musi być w Unii Europejskiej.</span><span class="sxs-lookup"><span data-stu-id="078ab-116">The primary address of the legal entity must be in a EU member state.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="078ab-117">Powiązane zadania konfiguracji</span><span class="sxs-lookup"><span data-stu-id="078ab-117">Related set up tasks</span></span></td>
<td><ul>
<li><span data-ttu-id="078ab-118">Na stronie <strong>Parametry modułu rozrachunków z odbiorcami</strong> wybierz opcje <strong>Włącz zarządzanie świadectwami wywozowymi</strong> i <strong>Włącz opcję wystawiania świadectwa wywozowego</strong>.</span><span class="sxs-lookup"><span data-stu-id="078ab-118">On the <strong>Accounts receivable parameters</strong> page, select the <strong>Enable entry certificate management</strong> and <strong>Enable entry certificate issuing</strong> options.</span></span></li>
<li><span data-ttu-id="078ab-119">Na stronie <strong>Odbiorcy</strong> na skróconej karcie <strong>Faktura i dostawa</strong> wybierz opcję <strong>Wymagane jest świadectwo wywozowe</strong>, aby wskazać, że świadectwo wywozowe UE jest wymagane dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="078ab-119">On the <strong>Customers</strong> page, on the <strong>Invoice and delivery</strong> FastTab, select the <strong>Entry certificate required</strong> option to indicate that an EU entry certificate is mandatory for the customer.</span></span> <span data-ttu-id="078ab-120">Zaznacz opcję <strong>Wystaw świadectwo wywozowe</strong>, aby wystawić świadectwo wywozowe UE firmy dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="078ab-120">Select the <strong>Issue entry certificate</strong> option to issue an EU entry certificate of the legal entity to the customer.</span></span></li>
<li><span data-ttu-id="078ab-121">Na stronie <strong>Parametry modułu rozrachunków z odbiorcami</strong> wybierz kod sekwencji identyfikatorów dla odwołania <strong>Świadectwo wywozowe</strong>.</span><span class="sxs-lookup"><span data-stu-id="078ab-121">On the <strong>Accounts receivable parameters</strong> page, select a number sequence code for the <strong>Entry certificate</strong> reference.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="078ab-122">Powiązane transakcje</span><span class="sxs-lookup"><span data-stu-id="078ab-122">Related transactions</span></span></td>
<td><ul>
<li><span data-ttu-id="078ab-123">Tworzenie konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="078ab-123">Create a customer account.</span></span></li>
<li><span data-ttu-id="078ab-124">Utwórz zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="078ab-124">Create a sales order.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a><span data-ttu-id="078ab-125">Tworzenie, rejestrowania i przekazywanie świadectwa wywozowego UE</span><span class="sxs-lookup"><span data-stu-id="078ab-125">Creating, registering, and uploading an EU entry certificate</span></span>
<span data-ttu-id="078ab-126">Świadectwo wywozowe UE można utworzyć automatycznie lub ręcznie.</span><span class="sxs-lookup"><span data-stu-id="078ab-126">You can create an EU entry certificate automatically or manually.</span></span> <span data-ttu-id="078ab-127">Świadectwo wywozowe UE jest tworzone i drukowane automatycznie podczas księgowania dokumentu dostawy lub faktury dla odbiorcy przy użyciu strony **Księgowanie dokumentu dostawy** lub **Księgowanie faktury**.</span><span class="sxs-lookup"><span data-stu-id="078ab-127">An EU entry certificate is created and printed automatically when you post a packing slip or invoice for a customer by using the **Packing slip posting** page or the **Posting invoice** page.</span></span> <span data-ttu-id="078ab-128">Aby ręcznie utworzyć lub ponownie wydrukować świadectwo wywozowe UE dla faktury dla odbiorcy, należy użyć strony **Arkusz faktur**.</span><span class="sxs-lookup"><span data-stu-id="078ab-128">To manually create or reprint an EU entry certificate for a customer invoice, use the **Invoice journal** page.</span></span> <span data-ttu-id="078ab-129">Można też użyć strony **Arkusz świadectwa wywozowego**, aby podać szczegóły dotyczące świadectwa wywozowego UE wystawionego przez inną firmę.</span><span class="sxs-lookup"><span data-stu-id="078ab-129">Additionally, you can use the **Entry certificate journal** page to enter details about an EU entry certificate that is issued by a third party.</span></span>

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a><span data-ttu-id="078ab-130">Tworzenie świadectwa wywozowego UE automatycznie lub ręcznie</span><span class="sxs-lookup"><span data-stu-id="078ab-130">Creating an EU entry certificate automatically or manually</span></span>

<span data-ttu-id="078ab-131">Świadectwo wywozowe UE można utworzyć automatycznie za pomocą dokumentu dostawy na stronie **Wszystkie zamówienia sprzedaży** lub za pomocą faktury na stronie **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="078ab-131">You can create an EU entry certificate automatically by using a packing slip on the **All sales orders** page or by using an invoice on the **Sales order** page.</span></span> <span data-ttu-id="078ab-132">Aby ręcznie utworzyć świadectwo wywozowe UE, można użyć faktury na stronie **Arkusz faktur**.</span><span class="sxs-lookup"><span data-stu-id="078ab-132">To manually create an EU entry certificate, you can use an invoice on the **Invoice journal** page.</span></span> <span data-ttu-id="078ab-133">Przed ręcznym utworzeniem świadectwa wywozowego UE trzeba jednak zmienić stan certyfikacji faktury.</span><span class="sxs-lookup"><span data-stu-id="078ab-133">However, you must change the certification status of the invoice before you manually create an EU entry certificate.</span></span>

### <a name="registering-an-eu-entry-certificate"></a><span data-ttu-id="078ab-134">Rejestrowanie świadectwa wywozowego UE</span><span class="sxs-lookup"><span data-stu-id="078ab-134">Registering an EU entry certificate</span></span>

<span data-ttu-id="078ab-135">Jeśli konieczna jest rejestracja, można też użyć strony **Arkusz świadectwa wywozowego**, aby zarejestrować świadectwo wywozowe UE wystawione przez inną firmę.</span><span class="sxs-lookup"><span data-stu-id="078ab-135">If registration is required, you can use the **Entry certificate journal** page to register an EU entry certificate that is issued by a third party.</span></span>

### <a name="uploading-a-received-eu-entry-certificate"></a><span data-ttu-id="078ab-136">Przekazywanie odebranego świadectwa wywozowego UE</span><span class="sxs-lookup"><span data-stu-id="078ab-136">Uploading a received EU entry certificate</span></span>

<span data-ttu-id="078ab-137">Aby przesłać odebrane świadectwo wywozowe UE podpisane przez odbiorcę z UE, użyj strony **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="078ab-137">Use the **Attachments** page to upload a received EU entry certificate that is signed by an EU customer.</span></span> <span data-ttu-id="078ab-138">Po przesłaniu świadectwa, można skojarzyć je z fakturą jako dowód na dostarczenie towarów.</span><span class="sxs-lookup"><span data-stu-id="078ab-138">After the certificate is uploaded, you can associate it with an invoice as proof that the items were delivered.</span></span> <span data-ttu-id="078ab-139">Ten dowód jest wymagany, jeśli trzeba wystawić fakturę, która nie obejmuje podatku od towarów i usług (VAT), i jest też używany podczas inspekcji.</span><span class="sxs-lookup"><span data-stu-id="078ab-139">This proof is required if you must issue an invoice that doesn't include value-added tax (VAT), and it's also used during auditing.</span></span>

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a><span data-ttu-id="078ab-140">Opcjonalnie: aktualizowanie stanu certyfikacji i drukowanie stanu faktury</span><span class="sxs-lookup"><span data-stu-id="078ab-140">Optional: Updating the certification status and printing status of an invoice</span></span>

<span data-ttu-id="078ab-141">Można zaktualizować stan świadectwa wywozowego i wydrukować stan faktury klienta za pomocą strony **Arkusz faktury**.</span><span class="sxs-lookup"><span data-stu-id="078ab-141">You can update the entry certification status and printing status of a customer invoice by using the **Invoice journal** page.</span></span>

## <a name="technical-information-for-system-administrators"></a><span data-ttu-id="078ab-142">Informacje techniczne dla administratorów systemu</span><span class="sxs-lookup"><span data-stu-id="078ab-142">Technical information for system administrators</span></span>
<span data-ttu-id="078ab-143">Jeśli nie masz dostępu do stron, które są używane do ukończenia tego zadania, skontaktuj się z administratorem systemu i podaj informacje, które przedstawiono w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="078ab-143">If you don't have access to the pages that are used to complete this task, contact your system administrator, and provide the information that is shown in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="078ab-144">Kategoria</span><span class="sxs-lookup"><span data-stu-id="078ab-144">Category</span></span></th>
<th><span data-ttu-id="078ab-145">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="078ab-145">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="078ab-146">Role zabezpieczeń i obowiązki</span><span class="sxs-lookup"><span data-stu-id="078ab-146">Security roles and duties</span></span></td>
<td><span data-ttu-id="078ab-147">Aby skonfigurować i utworzyć świadectwa wywozowe UE dla towarów lub usług, musisz być członkiem roli zabezpieczeń, która obejmuje następujące obowiązki:</span><span class="sxs-lookup"><span data-stu-id="078ab-147">To set up and create EU entry certificates for items or services, you must be a member of a security role that includes the following duties:</span></span>
<ul>
<li><span data-ttu-id="078ab-148"><strong>Pracownik ds. rozrachunków z odbiorcami</strong> (CustInvoiceAccountsReceivableClerk)</span><span class="sxs-lookup"><span data-stu-id="078ab-148"><strong>Accounts receivable clerk</strong> (CustInvoiceAccountsReceivableClerk)</span></span></li>
<li><span data-ttu-id="078ab-149"><strong>Przedstawiciel obsługi klienta</strong> (TradeCustomerServiceRepresentative)</span><span class="sxs-lookup"><span data-stu-id="078ab-149"><strong>Customer service representative</strong> (TradeCustomerServiceRepresentative)</span></span></li>
<li><span data-ttu-id="078ab-150"><strong>Pracownik ds. sprzedaży</strong> (TradeSalesClerk)</span><span class="sxs-lookup"><span data-stu-id="078ab-150"><strong>Sales clerk</strong> (TradeSalesClerk)</span></span></li>
<li><span data-ttu-id="078ab-151"><strong>Pracownik ds. spedycji</strong> (InventShippingClerk)</span><span class="sxs-lookup"><span data-stu-id="078ab-151"><strong>Shipping clerk</strong> (InventShippingClerk)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






