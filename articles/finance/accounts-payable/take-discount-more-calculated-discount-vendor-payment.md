---
title: Weź więcej niż obliczony rabat na płatność dostawcy
description: Ten artykuł prowadzi przez scenariusz, w którym do kwoty jest stosowany rabat gotówkowy większy niż rabat pierwotnie dostępny na fakturze. Taki scenariusz może wystąpić, jeśli organizacja zawrze z dostawcą umowę, aby zapłacić kwotę mniejszą niż podana na fakturze.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62f2088ff04a0ef5ffe6ffe47b85f47e6957264d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810253"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="397c4-104">Weź więcej niż obliczony rabat na płatność dostawcy</span><span class="sxs-lookup"><span data-stu-id="397c4-104">Take more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="397c4-105">Ten artykuł prowadzi przez scenariusz, w którym do kwoty jest stosowany rabat gotówkowy większy niż rabat pierwotnie dostępny na fakturze.</span><span class="sxs-lookup"><span data-stu-id="397c4-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="397c4-106">Taki scenariusz może wystąpić, jeśli organizacja zawrze z dostawcą umowę, aby zapłacić kwotę mniejszą niż podana na fakturze.</span><span class="sxs-lookup"><span data-stu-id="397c4-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="397c4-107">Dostawca 3051 daje firmie Fabrikam rabat gotówkowy w wysokości 4%, jeżeli faktura zostanie opłacona w ciągu 7 dni.</span><span class="sxs-lookup"><span data-stu-id="397c4-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="397c4-108">29 czerwca April wprowadza fakturę na kwotę 1000,00.</span><span class="sxs-lookup"><span data-stu-id="397c4-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="397c4-109">Dostawca zgadza się na przyznanie rabatu w wysokości 60,00 zamiast kwoty 40,00 dostępnej dla tej faktury.</span><span class="sxs-lookup"><span data-stu-id="397c4-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="397c4-110">April rejestruje jednorazową płatność za pomocą arkusza płatności rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="397c4-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="397c4-111">Wprowadza dostawcę dla płatności, a następnie otwiera stronę **Rozliczanie transakcji**.</span><span class="sxs-lookup"><span data-stu-id="397c4-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="397c4-112">Oznacza fakturę i zmienia wartość w polu **Kwota rabatu gotówkowego** na **-60,00**.</span><span class="sxs-lookup"><span data-stu-id="397c4-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="397c4-113">Zaznacz</span><span class="sxs-lookup"><span data-stu-id="397c4-113">Mark</span></span>     | <span data-ttu-id="397c4-114">Użyj rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="397c4-114">Use cash discount</span></span> | <span data-ttu-id="397c4-115">Załącznik</span><span class="sxs-lookup"><span data-stu-id="397c4-115">Voucher</span></span>   | <span data-ttu-id="397c4-116">Konto</span><span class="sxs-lookup"><span data-stu-id="397c4-116">Account</span></span> | <span data-ttu-id="397c4-117">Data</span><span class="sxs-lookup"><span data-stu-id="397c4-117">Date</span></span>      | <span data-ttu-id="397c4-118">Data wymagalności</span><span class="sxs-lookup"><span data-stu-id="397c4-118">Due date</span></span>  | <span data-ttu-id="397c4-119">Faktura</span><span class="sxs-lookup"><span data-stu-id="397c4-119">Invoice</span></span> | <span data-ttu-id="397c4-120">Kwota w walucie transakcji</span><span class="sxs-lookup"><span data-stu-id="397c4-120">Amount in transaction currency</span></span> | <span data-ttu-id="397c4-121">Waluta</span><span class="sxs-lookup"><span data-stu-id="397c4-121">Currency</span></span> | <span data-ttu-id="397c4-122">Kwota do rozliczenia</span><span class="sxs-lookup"><span data-stu-id="397c4-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="397c4-123">Wybrano</span><span class="sxs-lookup"><span data-stu-id="397c4-123">Selected</span></span> | <span data-ttu-id="397c4-124">Normalna</span><span class="sxs-lookup"><span data-stu-id="397c4-124">Normal</span></span>            | <span data-ttu-id="397c4-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="397c4-125">Inv-10040</span></span> | <span data-ttu-id="397c4-126">3051</span><span class="sxs-lookup"><span data-stu-id="397c4-126">3051</span></span>    | <span data-ttu-id="397c4-127">6/29/2015</span><span class="sxs-lookup"><span data-stu-id="397c4-127">6/29/2015</span></span> | <span data-ttu-id="397c4-128">7/29/2015</span><span class="sxs-lookup"><span data-stu-id="397c4-128">7/29/2015</span></span> | <span data-ttu-id="397c4-129">10040</span><span class="sxs-lookup"><span data-stu-id="397c4-129">10040</span></span>   | <span data-ttu-id="397c4-130">1000,00</span><span class="sxs-lookup"><span data-stu-id="397c4-130">1,000.00</span></span>                       | <span data-ttu-id="397c4-131">USD</span><span class="sxs-lookup"><span data-stu-id="397c4-131">USD</span></span>      | <span data-ttu-id="397c4-132">940,00</span><span class="sxs-lookup"><span data-stu-id="397c4-132">940.00</span></span>           |

<span data-ttu-id="397c4-133">Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie transakcji**.</span><span class="sxs-lookup"><span data-stu-id="397c4-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

| <span data-ttu-id="397c4-134">Pole</span><span class="sxs-lookup"><span data-stu-id="397c4-134">Field</span></span>                        | <span data-ttu-id="397c4-135">Wartość</span><span class="sxs-lookup"><span data-stu-id="397c4-135">Value</span></span>     |
|------------------------------|-----------|
| <span data-ttu-id="397c4-136">Data rabatu</span><span class="sxs-lookup"><span data-stu-id="397c4-136">Cash discount date</span></span>           | <span data-ttu-id="397c4-137">7/12/2015</span><span class="sxs-lookup"><span data-stu-id="397c4-137">7/12/2015</span></span> |
| <span data-ttu-id="397c4-138">Kwota rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="397c4-138">Cash discount amount</span></span>         | <span data-ttu-id="397c4-139">60.00</span><span class="sxs-lookup"><span data-stu-id="397c4-139">60.00</span></span>     |
| <span data-ttu-id="397c4-140">Użyj rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="397c4-140">Use cash discount</span></span>            | <span data-ttu-id="397c4-141">Normalna</span><span class="sxs-lookup"><span data-stu-id="397c4-141">Normal</span></span>    |
| <span data-ttu-id="397c4-142">Pobrany rabat gotówkowy</span><span class="sxs-lookup"><span data-stu-id="397c4-142">Cash discount taken</span></span>          | <span data-ttu-id="397c4-143">0,00</span><span class="sxs-lookup"><span data-stu-id="397c4-143">0.00</span></span>      |
| <span data-ttu-id="397c4-144">Kwota rabatu gotówkowego do pobrania</span><span class="sxs-lookup"><span data-stu-id="397c4-144">Cash discount amount to take</span></span> | <span data-ttu-id="397c4-145">60,00</span><span class="sxs-lookup"><span data-stu-id="397c4-145">60.00</span></span>     |

<span data-ttu-id="397c4-146">Następnie April arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="397c4-146">April posts the payment journal.</span></span> <span data-ttu-id="397c4-147">Faktura jest całkowicie rozliczona przy użyciu płatności 940,00 i rabatu 60,00.</span><span class="sxs-lookup"><span data-stu-id="397c4-147">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]