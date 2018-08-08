---
title: "Częściowa płatność dostawcy"
description: "Czasami płatność dokonywana na rzecz dostawcy jest mniejsza od kwoty faktury. W tym artykule opisano różne opcje postępowania w takiej sytuacji."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2644e0a27eff3e45ddcddb89c9aac9230190788f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="vendor-payments-for-a-partial-amount"></a><span data-ttu-id="2c139-104">Częściowe płatności dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="2c139-104">Vendor payments for a partial amount</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c139-105">Czasami płatność dokonywana na rzecz dostawcy jest mniejsza od kwoty faktury.</span><span class="sxs-lookup"><span data-stu-id="2c139-105">Sometimes, you might make a payment to a vendor that is less than the amount of an invoice.</span></span> <span data-ttu-id="2c139-106">W tym artykule opisano różne opcje postępowania w takiej sytuacji.</span><span class="sxs-lookup"><span data-stu-id="2c139-106">This article describes the various options for handling this situation.</span></span> <span data-ttu-id="2c139-107">Faktycznie dostępne opcje zależą od konkretnych wymagań biznesowych i istniejącej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2c139-107">The options that are available to you depend on your business requirements and configuration.</span></span> 

<a name="cash-discount-amounts"></a><span data-ttu-id="2c139-108">Kwoty rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="2c139-108">Cash discount amounts</span></span>
---------------------

<span data-ttu-id="2c139-109">Dostawca może zaoferować Ci rabat za rozliczenie faktury przed datą należności.</span><span class="sxs-lookup"><span data-stu-id="2c139-109">A vendor can offer you a cash discount for paying an invoice before the due date.</span></span> <span data-ttu-id="2c139-110">Załóżmy, że wprowadzasz fakturę na kwotę 100,00, na którą odbiorca może uzyskać 2-procentowy rabat gotówkowy, jeśli zapłaci ją w ciągu 10 dni.</span><span class="sxs-lookup"><span data-stu-id="2c139-110">For example, you enter an invoice for 100.00 that specifies a 2-percent cash discount if the invoice is paid within 10 days.</span></span> <span data-ttu-id="2c139-111">Okres płatności wynosi 30 dni.</span><span class="sxs-lookup"><span data-stu-id="2c139-111">The due date terms are 30 days.</span></span> <span data-ttu-id="2c139-112">Jeśli propozycja płatności rabatu gotówkowego używa jako kryterium wyboru faktury i jeśli propozycja zostanie uruchomiona w dniu lub przed datą rabatu gotówkowego, wybrana faktura do zapłaty i płatność są tworzone na kwotę 98,00.</span><span class="sxs-lookup"><span data-stu-id="2c139-112">If a payment proposal uses the cash discount as a criterion for selecting an invoice, and if the proposal is run on or before the cash discount date, the invoice is selected for payment, and the payment is created for 98.00.</span></span> <span data-ttu-id="2c139-113">Rabat gotówkowy może być również uwzględniony dla jednorazowej płatności, która została utworzona ręcznie.</span><span class="sxs-lookup"><span data-stu-id="2c139-113">A cash discount can also be taken for a one-off payment that was created manually.</span></span>

## <a name="partial-payments-with-cash-discounts"></a><span data-ttu-id="2c139-114">Płatności częściowe z rabatem gotówkowym</span><span class="sxs-lookup"><span data-stu-id="2c139-114">Partial payments with cash discounts</span></span>
<span data-ttu-id="2c139-115">Kiedy dokonujesz płatności częściowej, możesz zaplanować dokonanie dodatkowej zapłaty częściowej, by rozliczyć fakturę w całości.</span><span class="sxs-lookup"><span data-stu-id="2c139-115">When you make a partial payment, you might plan to make an additional partial payment to fully settle the invoice.</span></span> <span data-ttu-id="2c139-116">Aby podjąć rabat gotówkowy dla płatności częściowej, musisz ustawić w opcji **Oblicz rabaty gotówkowe dla częściowych zapłat** wartość **Tak** na stronie **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="2c139-116">To take a cash discount for a partial payment, you must set the **Calculate cash discounts for partial payments** option to **Yes** on the **Account payable parameters** page.</span></span> 

<span data-ttu-id="2c139-117">Na przykład możesz otrzymać 2-procentowy rabat gotówkowy, jeśli faktura zostanie zapłacona w ciągu 10 dni po wystawieniu.</span><span class="sxs-lookup"><span data-stu-id="2c139-117">For example, you receive a 2-percent cash discount if the invoice is paid within 10 days after it's issued.</span></span> <span data-ttu-id="2c139-118">Faktura jest księgowana na wartość 100,00.</span><span class="sxs-lookup"><span data-stu-id="2c139-118">An invoice is posted for 100.00.</span></span> <span data-ttu-id="2c139-119">Jeśli w ciągu 10 dni dokonasz płatności w wysokości 49,00, wpisujesz debet w wysokości 49,00 w arkuszu płatności.</span><span class="sxs-lookup"><span data-stu-id="2c139-119">If you make a payment of 49.00 within 10 days, you enter a debit of 49.00 in a payment journal.</span></span> <span data-ttu-id="2c139-120">Po rozliczeniu płatności częściowej na stronie **Rozliczanie otwartych transakcji** w polu **Kwota rabatu gotówkowego do pobrania** pojawia się wartość **1,00**.</span><span class="sxs-lookup"><span data-stu-id="2c139-120">When you settle the partial payment on the **Settle open transactions** page, **1.00** appears in the **Cash discount amount to take** field.</span></span> 

> [!NOTE] 
> <span data-ttu-id="2c139-121">Jeśli wpiszesz częściową płatność i zostawisz pełną wartość faktury w polu **Kwota do rozliczenia**, pole **Kwota rabatu gotówkowego do pobrania** jest automatycznie obliczane ponownie po zaksięgowaniu transakcji.</span><span class="sxs-lookup"><span data-stu-id="2c139-121">If you enter a partial payment and leave the full invoice amount in the **Amount to settle** field, the **Cash discount amount to take** field is automatically recalculated when you post the transactions.</span></span>

## <a name="credit-notes-with-cash-discounts"></a><span data-ttu-id="2c139-122">Faktury korygujące z rabatami gotówkowymi</span><span class="sxs-lookup"><span data-stu-id="2c139-122">Credit notes with cash discounts</span></span>
<span data-ttu-id="2c139-123">Możesz zwrócić część towarów znajdujących się na fakturze i otrzymać fakturę korygującą.</span><span class="sxs-lookup"><span data-stu-id="2c139-123">You might return some of the items on an invoice and receive a credit note.</span></span> <span data-ttu-id="2c139-124">Jeśli dla oryginalnej faktury został podjęty rabat gotówkowy, możesz odjąć wartość rabatu i uzyskać zwrot kosztu na odpowiednią kwotę.</span><span class="sxs-lookup"><span data-stu-id="2c139-124">If a cash discount was taken on the original invoice, you can subtract the value of the discount and receive a refund for the correct amount.</span></span> <span data-ttu-id="2c139-125">Jeśli opcja **Oblicz rabaty gotówkowe dla faktur korygujących**na stronie **Parametry modułu rozrachunków z dostawcami** ma wartość **Tak**, rabat dla faktury korygującej jest automatycznie obliczany.</span><span class="sxs-lookup"><span data-stu-id="2c139-125">If the **Calculate cash discounts for credit notes** option is set to **Yes** on the **Accounts payable parameters** page, the discount is automatically calculated for the credit note.</span></span> 

<span data-ttu-id="2c139-126">Na przykład możesz otrzymać 2-procentowy rabat gotówkowy, jeśli faktura zostanie zapłacona w ciągu 10 dni po wystawieniu.</span><span class="sxs-lookup"><span data-stu-id="2c139-126">For example, you receive a 2-percent cash discount if the invoice is paid within 10 days after it's issued.</span></span> <span data-ttu-id="2c139-127">Faktura jest księgowana na wartość 100,00.</span><span class="sxs-lookup"><span data-stu-id="2c139-127">An invoice for 100.00 is posted.</span></span> <span data-ttu-id="2c139-128">W przypadku zwrotu towarów i otrzymania faktury korygującej możesz wprowadzić fakturę korygującą dla całej kwoty oryginalnej faktury (100,00) łącznie z 2-procentowym rabatem gotówkowy zdefiniowanym na fakturze korygującej.</span><span class="sxs-lookup"><span data-stu-id="2c139-128">If you return the goods and receive a credit note, you can enter the credit note for the full amount of the original invoice, 100.00, together with the 2-percent cash discount that is also defined on the credit memo.</span></span>  <span data-ttu-id="2c139-129">Podczas wyświetlania faktury korygującej na stronie **Rozliczanie transakcji** w polu **Kwota do rozliczenia** pojawia się wartość **98,00**, a w polu **Kwota rabaty gotówkowego** pojawia się wartość **-2,00**.</span><span class="sxs-lookup"><span data-stu-id="2c139-129">When you view the credit note on the **Settle transactions** page, **98.00** appears in the **Amount to settle** field, and **-2.00** appears in the **Cash discount amount** field.</span></span> <span data-ttu-id="2c139-130">Kwota rabatu jest księgowana na koncie rabatu gotówkowego.</span><span class="sxs-lookup"><span data-stu-id="2c139-130">The discount amount is posted to a cash discount account.</span></span>

## <a name="overpaymentunderpayment-amounts"></a><span data-ttu-id="2c139-131">Kwoty nadpłaty/niedopłaty</span><span class="sxs-lookup"><span data-stu-id="2c139-131">Overpayment/underpayment amounts</span></span>
<span data-ttu-id="2c139-132">Możesz dokonać częściowej płatności, jeśli kwota pozostała do zapłacenia, jest bardzo mała.</span><span class="sxs-lookup"><span data-stu-id="2c139-132">You might make a partial payment where the amount that must still be settled is very small.</span></span> <span data-ttu-id="2c139-133">Na przykład faktura od dostawcy ma wartość 1000,00 i płacisz kwotę 999,90.</span><span class="sxs-lookup"><span data-stu-id="2c139-133">For example, the vendor invoice is for 1,000.00, and you pay 999.90.</span></span> <span data-ttu-id="2c139-134">Jeśli pozostała kwota jest mniejsza od kwoty określonej dla nadpłaty i niedopłaty w na stronie **Parametry modułu rozrachunków z dostawcami**, różnica jest automatycznie księgowana na koncie księgi niedopłaty/nadpłaty.</span><span class="sxs-lookup"><span data-stu-id="2c139-134">If the remaining amount is less than the amount that is specified for overpayments or underpayments on the **Accounts payable parameters** page, the difference is automatically posted to an overpayment/underpayment ledger account.</span></span>


<span data-ttu-id="2c139-135">Aby uzyskać więcej informacji, zobacz [Przegląd płatności dla dostawcy](../cash-bank-management/tasks/vendor-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c139-135">For more information, see [Vendor payment overview](../cash-bank-management/tasks/vendor-payment-overview.md).</span></span>

