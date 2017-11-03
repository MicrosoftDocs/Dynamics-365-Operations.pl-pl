---
title: "Zastosowanie rabatu większego niż obliczony dla płatności dla dostawcy"
description: "Ten artykuł prowadzi przez scenariusz, w którym do kwoty jest stosowany rabat gotówkowy większy niż rabat pierwotnie dostępny na fakturze. Taki scenariusz może wystąpić, jeśli organizacja zawrze z dostawcą umowę, aby zapłacić kwotę mniejszą niż podana na fakturze."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0c9e4bccb6e38e2e6d50256bc609b1552d9b21c5
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="b6985-104">Zastosowanie rabatu większego niż obliczony dla płatności dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="b6985-104">Take a discount that is more than the calculated discount for a vendor payment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b6985-105">Ten artykuł prowadzi przez scenariusz, w którym do kwoty jest stosowany rabat gotówkowy większy niż rabat pierwotnie dostępny na fakturze.</span><span class="sxs-lookup"><span data-stu-id="b6985-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="b6985-106">Taki scenariusz może wystąpić, jeśli organizacja zawrze z dostawcą umowę, aby zapłacić kwotę mniejszą niż podana na fakturze.</span><span class="sxs-lookup"><span data-stu-id="b6985-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="b6985-107">Dostawca 3051 daje firmie Fabrikam rabat gotówkowy w wysokości 4%, jeżeli faktura zostanie opłacona w ciągu 7 dni.</span><span class="sxs-lookup"><span data-stu-id="b6985-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="b6985-108">29 czerwca April wprowadza fakturę na kwotę 1000,00.</span><span class="sxs-lookup"><span data-stu-id="b6985-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="b6985-109">Dostawca zgadza się na przyznanie rabatu w wysokości 60,00 zamiast kwoty 40,00 dostępnej dla tej faktury.</span><span class="sxs-lookup"><span data-stu-id="b6985-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="b6985-110">April rejestruje jednorazową płatność za pomocą arkusza płatności rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="b6985-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="b6985-111">Wprowadza dostawcę dla płatności, a następnie otwiera stronę **Rozliczanie transakcji**.</span><span class="sxs-lookup"><span data-stu-id="b6985-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="b6985-112">Oznacza fakturę i zmienia wartość w polu **Kwota rabatu gotówkowego** na **-60,00**.</span><span class="sxs-lookup"><span data-stu-id="b6985-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>
| <span data-ttu-id="b6985-113">Zaznacz</span><span class="sxs-lookup"><span data-stu-id="b6985-113">Mark</span></span>     | <span data-ttu-id="b6985-114">Użyj rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="b6985-114">Use cash discount</span></span> | <span data-ttu-id="b6985-115">Załącznik</span><span class="sxs-lookup"><span data-stu-id="b6985-115">Voucher</span></span>   | <span data-ttu-id="b6985-116">Konto</span><span class="sxs-lookup"><span data-stu-id="b6985-116">Account</span></span> | <span data-ttu-id="b6985-117">Data</span><span class="sxs-lookup"><span data-stu-id="b6985-117">Date</span></span>      | <span data-ttu-id="b6985-118">Data wymagalności</span><span class="sxs-lookup"><span data-stu-id="b6985-118">Due date</span></span>  | <span data-ttu-id="b6985-119">Faktura</span><span class="sxs-lookup"><span data-stu-id="b6985-119">Invoice</span></span> | <span data-ttu-id="b6985-120">Kwota w walucie transakcji</span><span class="sxs-lookup"><span data-stu-id="b6985-120">Amount in transaction currency</span></span> | <span data-ttu-id="b6985-121">Waluta</span><span class="sxs-lookup"><span data-stu-id="b6985-121">Currency</span></span> | <span data-ttu-id="b6985-122">Kwota do rozliczenia</span><span class="sxs-lookup"><span data-stu-id="b6985-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="b6985-123">Wybrano</span><span class="sxs-lookup"><span data-stu-id="b6985-123">Selected</span></span> | <span data-ttu-id="b6985-124">Normalna</span><span class="sxs-lookup"><span data-stu-id="b6985-124">Normal</span></span>            | <span data-ttu-id="b6985-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="b6985-125">Inv-10040</span></span> | <span data-ttu-id="b6985-126">3051</span><span class="sxs-lookup"><span data-stu-id="b6985-126">3051</span></span>    | <span data-ttu-id="b6985-127">6/29/2015</span><span class="sxs-lookup"><span data-stu-id="b6985-127">6/29/2015</span></span> | <span data-ttu-id="b6985-128">7/29/2015</span><span class="sxs-lookup"><span data-stu-id="b6985-128">7/29/2015</span></span> | <span data-ttu-id="b6985-129">10040</span><span class="sxs-lookup"><span data-stu-id="b6985-129">10040</span></span>   | <span data-ttu-id="b6985-130">1000,00</span><span class="sxs-lookup"><span data-stu-id="b6985-130">1,000.00</span></span>                       | <span data-ttu-id="b6985-131">USD</span><span class="sxs-lookup"><span data-stu-id="b6985-131">USD</span></span>      | <span data-ttu-id="b6985-132">940,00</span><span class="sxs-lookup"><span data-stu-id="b6985-132">940.00</span></span>           |

<span data-ttu-id="b6985-133">Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie transakcji**.</span><span class="sxs-lookup"><span data-stu-id="b6985-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>
|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="b6985-134">Data rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="b6985-134">Cash discount date</span></span>           | <span data-ttu-id="b6985-135">7/12/2015</span><span class="sxs-lookup"><span data-stu-id="b6985-135">7/12/2015</span></span> |
| <span data-ttu-id="b6985-136">Kwota rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="b6985-136">Cash discount amount</span></span>         | <span data-ttu-id="b6985-137">60,00</span><span class="sxs-lookup"><span data-stu-id="b6985-137">60.00</span></span>     |
| <span data-ttu-id="b6985-138">Użyj rabatu gotówkowego</span><span class="sxs-lookup"><span data-stu-id="b6985-138">Use cash discount</span></span>            | <span data-ttu-id="b6985-139">Normalna</span><span class="sxs-lookup"><span data-stu-id="b6985-139">Normal</span></span>    |
| <span data-ttu-id="b6985-140">Pobrany rabat gotówkowy</span><span class="sxs-lookup"><span data-stu-id="b6985-140">Cash discount taken</span></span>          | <span data-ttu-id="b6985-141">0,00</span><span class="sxs-lookup"><span data-stu-id="b6985-141">0.00</span></span>      |
| <span data-ttu-id="b6985-142">Kwota rabatu gotówkowego do pobrania</span><span class="sxs-lookup"><span data-stu-id="b6985-142">Cash discount amount to take</span></span> | <span data-ttu-id="b6985-143">60,00</span><span class="sxs-lookup"><span data-stu-id="b6985-143">60.00</span></span>     |

<span data-ttu-id="b6985-144">Następnie April arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="b6985-144">April posts the payment journal.</span></span> <span data-ttu-id="b6985-145">Faktura jest całkowicie rozliczona przy użyciu płatności 940,00 i rabatu 60,00.</span><span class="sxs-lookup"><span data-stu-id="b6985-145">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>




