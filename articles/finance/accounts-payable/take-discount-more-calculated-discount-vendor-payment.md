---
title: Weź więcej niż obliczony rabat na płatność dostawcy
description: Ten artykuł prowadzi przez scenariusz, w którym do kwoty jest stosowany rabat gotówkowy większy niż rabat pierwotnie dostępny na fakturze. Taki scenariusz może wystąpić, jeśli organizacja zawrze z dostawcą umowę, aby zapłacić kwotę mniejszą niż podana na fakturze.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: c7ee74bad071d546724f6ffe336bbe3bdf47e2a5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971910"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="c09ac-104">Weź więcej niż obliczony rabat na płatność dostawcy</span><span class="sxs-lookup"><span data-stu-id="c09ac-104">Take more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c09ac-105">Ten artykuł prowadzi przez scenariusz, w którym do kwoty jest stosowany rabat gotówkowy większy niż rabat pierwotnie dostępny na fakturze.</span><span class="sxs-lookup"><span data-stu-id="c09ac-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="c09ac-106">Taki scenariusz może wystąpić, jeśli organizacja zawrze z dostawcą umowę, aby zapłacić kwotę mniejszą niż podana na fakturze.</span><span class="sxs-lookup"><span data-stu-id="c09ac-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="c09ac-107">Dostawca 3051 daje firmie Fabrikam rabat gotówkowy w wysokości 4%, jeżeli faktura zostanie opłacona w ciągu 7 dni.</span><span class="sxs-lookup"><span data-stu-id="c09ac-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="c09ac-108">29 czerwca April wprowadza fakturę na kwotę 1000,00.</span><span class="sxs-lookup"><span data-stu-id="c09ac-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="c09ac-109">Dostawca zgadza się na przyznanie rabatu w wysokości 60,00 zamiast kwoty 40,00 dostępnej dla tej faktury.</span><span class="sxs-lookup"><span data-stu-id="c09ac-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="c09ac-110">April rejestruje jednorazową płatność za pomocą arkusza płatności rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="c09ac-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="c09ac-111">Wprowadza dostawcę dla płatności, a następnie otwiera stronę **Rozliczanie transakcji**.</span><span class="sxs-lookup"><span data-stu-id="c09ac-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="c09ac-112">Oznacza fakturę i zmienia wartość w polu **Kwota rabatu gotówkowego** na **-60,00**.</span><span class="sxs-lookup"><span data-stu-id="c09ac-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="c09ac-113">Zaznacz</span><span class="sxs-lookup"><span data-stu-id="c09ac-113">Mark</span></span>     | <span data-ttu-id="c09ac-114">Użyj rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="c09ac-114">Use cash discount</span></span> | <span data-ttu-id="c09ac-115">Załącznik</span><span class="sxs-lookup"><span data-stu-id="c09ac-115">Voucher</span></span>   | <span data-ttu-id="c09ac-116">Konto</span><span class="sxs-lookup"><span data-stu-id="c09ac-116">Account</span></span> | <span data-ttu-id="c09ac-117">Data</span><span class="sxs-lookup"><span data-stu-id="c09ac-117">Date</span></span>      | <span data-ttu-id="c09ac-118">Data wymagalności</span><span class="sxs-lookup"><span data-stu-id="c09ac-118">Due date</span></span>  | <span data-ttu-id="c09ac-119">Faktura</span><span class="sxs-lookup"><span data-stu-id="c09ac-119">Invoice</span></span> | <span data-ttu-id="c09ac-120">Kwota w walucie transakcji</span><span class="sxs-lookup"><span data-stu-id="c09ac-120">Amount in transaction currency</span></span> | <span data-ttu-id="c09ac-121">Waluta</span><span class="sxs-lookup"><span data-stu-id="c09ac-121">Currency</span></span> | <span data-ttu-id="c09ac-122">Kwota do rozliczenia</span><span class="sxs-lookup"><span data-stu-id="c09ac-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="c09ac-123">Wybrano</span><span class="sxs-lookup"><span data-stu-id="c09ac-123">Selected</span></span> | <span data-ttu-id="c09ac-124">Normalna</span><span class="sxs-lookup"><span data-stu-id="c09ac-124">Normal</span></span>            | <span data-ttu-id="c09ac-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="c09ac-125">Inv-10040</span></span> | <span data-ttu-id="c09ac-126">3051</span><span class="sxs-lookup"><span data-stu-id="c09ac-126">3051</span></span>    | <span data-ttu-id="c09ac-127">6/29/2015</span><span class="sxs-lookup"><span data-stu-id="c09ac-127">6/29/2015</span></span> | <span data-ttu-id="c09ac-128">7/29/2015</span><span class="sxs-lookup"><span data-stu-id="c09ac-128">7/29/2015</span></span> | <span data-ttu-id="c09ac-129">10040</span><span class="sxs-lookup"><span data-stu-id="c09ac-129">10040</span></span>   | <span data-ttu-id="c09ac-130">1000,00</span><span class="sxs-lookup"><span data-stu-id="c09ac-130">1,000.00</span></span>                       | <span data-ttu-id="c09ac-131">USD</span><span class="sxs-lookup"><span data-stu-id="c09ac-131">USD</span></span>      | <span data-ttu-id="c09ac-132">940,00</span><span class="sxs-lookup"><span data-stu-id="c09ac-132">940.00</span></span>           |

<span data-ttu-id="c09ac-133">Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie transakcji**.</span><span class="sxs-lookup"><span data-stu-id="c09ac-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="c09ac-134">Data rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="c09ac-134">Cash discount date</span></span>           | <span data-ttu-id="c09ac-135">7/12/2015</span><span class="sxs-lookup"><span data-stu-id="c09ac-135">7/12/2015</span></span> |
| <span data-ttu-id="c09ac-136">Kwota rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="c09ac-136">Cash discount amount</span></span>         | <span data-ttu-id="c09ac-137">60,00</span><span class="sxs-lookup"><span data-stu-id="c09ac-137">60.00</span></span>     |
| <span data-ttu-id="c09ac-138">Użyj rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="c09ac-138">Use cash discount</span></span>            | <span data-ttu-id="c09ac-139">Normalna</span><span class="sxs-lookup"><span data-stu-id="c09ac-139">Normal</span></span>    |
| <span data-ttu-id="c09ac-140">Pobrany rabat gotówkowy</span><span class="sxs-lookup"><span data-stu-id="c09ac-140">Cash discount taken</span></span>          | <span data-ttu-id="c09ac-141">0,00</span><span class="sxs-lookup"><span data-stu-id="c09ac-141">0.00</span></span>      |
| <span data-ttu-id="c09ac-142">Kwota rabatu gotówkowego do pobrania</span><span class="sxs-lookup"><span data-stu-id="c09ac-142">Cash discount amount to take</span></span> | <span data-ttu-id="c09ac-143">60,00</span><span class="sxs-lookup"><span data-stu-id="c09ac-143">60.00</span></span>     |

<span data-ttu-id="c09ac-144">Następnie April arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="c09ac-144">April posts the payment journal.</span></span> <span data-ttu-id="c09ac-145">Faktura jest całkowicie rozliczona przy użyciu płatności 940,00 i rabatu 60,00.</span><span class="sxs-lookup"><span data-stu-id="c09ac-145">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>



