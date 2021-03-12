---
title: Rabaty gotówkowe
description: Rabaty gotówkowe są skonfigurowane i udostępnione dla modułów Rozrachunki z odbiorcami i Rozrachunki z dostawcami.  Dostępny rabat gotówkowy można zdefiniować na fakturze dla odbiorcy lub fakturze od dostawcy. Zostanie on uwzględniony w przypadku zapłaty faktury w terminie obowiązywania rabatu gotówkowego.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CashDisc
audience: Application User
ms.reviewer: roschlom
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d4f6d5bdf4f2fdc4529d9f51515ed2ac4b5b3b5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985319"
---
# <a name="cash-discounts"></a><span data-ttu-id="833a6-104">Rabaty gotówkowe</span><span class="sxs-lookup"><span data-stu-id="833a6-104">Cash discounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="833a6-105">Rabaty gotówkowe są skonfigurowane i udostępnione dla modułów Rozrachunki z odbiorcami i Rozrachunki z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="833a6-105">Cash discounts are setup and shared for Accounts payable and Accounts receivable.</span></span>  <span data-ttu-id="833a6-106">Dostępny rabat gotówkowy można zdefiniować na fakturze dla odbiorcy lub fakturze od dostawcy. Zostanie on uwzględniony w przypadku zapłaty faktury w terminie obowiązywania rabatu gotówkowego.</span><span class="sxs-lookup"><span data-stu-id="833a6-106">The cash discount available can be defined on the customer invoice or vendor invoice, and will be taken if the invoice is paid within the cash discount date.</span></span> 

## <a name="cash-discounts"></a><span data-ttu-id="833a6-107">Rabaty gotówkowe</span><span class="sxs-lookup"><span data-stu-id="833a6-107">Cash discounts</span></span>

<span data-ttu-id="833a6-108">Rabaty gotówkowe, które będą obowiązywały dla odbiorców lub dostawców można tworzyć na stronie Rabaty gotówkowe.</span><span class="sxs-lookup"><span data-stu-id="833a6-108">Cash discounts for both customers or vendors can be created in the Cash discounts page.</span></span> <span data-ttu-id="833a6-109">Ponadto w polu Następny kod rabatu można zdefiniować serię rabatów gotówkowych następujących po sobie w zależności od terminu faktury.</span><span class="sxs-lookup"><span data-stu-id="833a6-109">You can also define, by using the Next discount code field, a series of cash discounts that succeed each other as previous cash discount dates expire.</span></span> <span data-ttu-id="833a6-110">Aby uzyskać więcej informacji, zobacz „Przykład: Seria rabatów gotówkowych” dalej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="833a6-110">For more information, see “Example: Series of cash discounts” later in this topic.</span></span> <span data-ttu-id="833a6-111">Jeśli faktura i/lub transakcja kredytowa (płatność lub faktura korygująca) zostały wprowadzone w walucie innej niż waluta rozliczeniowa firmy, rabat gotówkowy jest obliczany według kursu wymiany, na podstawie daty płatności lub faktury korygującej.</span><span class="sxs-lookup"><span data-stu-id="833a6-111">If the invoice, credit transaction (either a payment or a credit note), or both are entered in a currency other than the accounting currency of the legal entity, the cash discount is calculated using the exchange rate based on the date of the payment or credit note.</span></span> <span data-ttu-id="833a6-112">Jeśli faktura i dokument kredytowy zostały wprowadzone w innych firmach i jeśli waluty księgowania dla firm są różne, kurs wymiany jest brany z firmy na fakturze, począwszy od daty dokumentu faktury.</span><span class="sxs-lookup"><span data-stu-id="833a6-112">If the invoice and credit document are entered in different legal entities, and if the accounting currencies for the legal entities differ, the exchange rate is taken from the legal entity of the invoice, as of the date of the credit document.</span></span> <span data-ttu-id="833a6-113">Aby uzyskać więcej informacji, zobacz „Przykład: Kursy wymiany dla rabatów gotówkowych” dalej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="833a6-113">For more information, see “Example: Exchange rates for cash discounts” later in this topic.</span></span>

## <a name="defaulting-order-of-cash-discount-main-account"></a><span data-ttu-id="833a6-114">Kolejność domyślności dla rabatów gotówkowych na koncie głównym</span><span class="sxs-lookup"><span data-stu-id="833a6-114">Defaulting order of cash discount main account</span></span>

<span data-ttu-id="833a6-115">Jeśli faktura rozliczana jest w czasie, w którym można uzyskać rabat gotówkowy, rabat ten jest automatycznie księgowany na koncie głównym rabatów gotówkowych zgodnie z następującą kolejnością domyślności:</span><span class="sxs-lookup"><span data-stu-id="833a6-115">If an invoice is settled in time to obtain a cash discount, the cash discount is automatically posted to a cash discount main account according to the following defaulting priority:</span></span>
1.  <span data-ttu-id="833a6-116">Konto główne określone w polu Alternatywne konto rabatu gotówkowego na stronie Rozliczanie otwartych transakcji dla odbiorcy lub Rozliczanie otwartych transakcji dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="833a6-116">The main account specified in the Alternative cash discount account field on the customer Settle open transactions page or the vendor Settle open transactions page.</span></span>
2.  <span data-ttu-id="833a6-117">Konto główne określone w polu Rabat gotówkowy odbiorcy lub w polu Rabat gotówkowy dostawcy grupy księgowania w księdze przypisanej do kodu podatków faktury.</span><span class="sxs-lookup"><span data-stu-id="833a6-117">The main account specified in the Customer cash discount field or the Vendor cash discount field of the ledger posting group that is assigned to the sales tax code of the invoice.</span></span> <span data-ttu-id="833a6-118">Ustaw grupy księgowania na stronie Grupy księgowania księgi i przypisz je do kodów podatku na stronie Kody podatków.</span><span class="sxs-lookup"><span data-stu-id="833a6-118">Set up ledger posting groups on the Ledger posting groups page and assign them to sales tax codes in the Sales tax codes page.</span></span>
3.  <span data-ttu-id="833a6-119">Konto główne księgowania na stronie Rabaty gotówkowe w polu Konto główne rabatów odbiorcy lub Konto główne rabatów dostawcy dla kodu rabatu gotówkowego na rozliczonej fakturze.</span><span class="sxs-lookup"><span data-stu-id="833a6-119">The main posting account on the Cash discounts page in either the Main account for customer discounts field or the Main account for vendor discounts field for the cash discount code that is on the settled invoice.</span></span>
4.  <span data-ttu-id="833a6-120">Konto główne rabatów gotówkowych według definicji na stronie Konta dla transakcji automatycznych.</span><span class="sxs-lookup"><span data-stu-id="833a6-120">The main account for cash discounts, as defined in the Accounts for automatic transactions page.</span></span>

## <a name="example-series-of-cash-discounts"></a><span data-ttu-id="833a6-121"> Przykład: Seria rabatów gotówkowych</span><span class="sxs-lookup"><span data-stu-id="833a6-121">Example: Series of cash discounts</span></span>
<span data-ttu-id="833a6-122">Konfiguruj następujące trzy kody rabatów gotówkowych:</span><span class="sxs-lookup"><span data-stu-id="833a6-122">Set up three cash discount codes as follows:</span></span>
-   <span data-ttu-id="833a6-123">Kod 5D10% — 10% rabat gotówkowy przy zapłacie w ciągu 5 dni.</span><span class="sxs-lookup"><span data-stu-id="833a6-123">Code 5D10% – A cash discount of 10% when the amount is paid within 5 days.</span></span>
-   <span data-ttu-id="833a6-124">Kod 10D5% — 5% rabat gotówkowy przy zapłacie w ciągu 10 dni.</span><span class="sxs-lookup"><span data-stu-id="833a6-124">Code 10D5% – A cash discount of 5% when the amount is paid within 10 days.</span></span>
-   <span data-ttu-id="833a6-125">Kod 14D2% — 2% rabat gotówkowy przy zapłacie w ciągu 14 dni.</span><span class="sxs-lookup"><span data-stu-id="833a6-125">Code 14D2% – A cash discount of 2% when the amount is paid within 14 days.</span></span>

<span data-ttu-id="833a6-126">W polu Następny kod rabatu:</span><span class="sxs-lookup"><span data-stu-id="833a6-126">In the Next discount code field:</span></span>
-   <span data-ttu-id="833a6-127">Dla kodu 5D10% wybierz opcję 10D5%.</span><span class="sxs-lookup"><span data-stu-id="833a6-127">For the 5D10% code, select 10D5%.</span></span>
-   <span data-ttu-id="833a6-128">Dla kodu 10D5% wybierz opcję 14D2%.</span><span class="sxs-lookup"><span data-stu-id="833a6-128">For the 10D5% code, select 14D2%.</span></span>
-   <span data-ttu-id="833a6-129">Dla kodu 14D2% pole Następny kod rabatu należy zostawić puste.</span><span class="sxs-lookup"><span data-stu-id="833a6-129">For the 14D2% code, leave the Next discount code field blank.</span></span>

<span data-ttu-id="833a6-130">Te trzy rabaty gotówkowe następują po sobie w miarę wygasania poprzednich rabatów gotówkowych na fakturze.</span><span class="sxs-lookup"><span data-stu-id="833a6-130">The three cash discounts succeed each other as the payment date exceeds the previous cash discount date on the invoice.</span></span> <span data-ttu-id="833a6-131">Tylko jeden rabat gotówkowy jest przyznawany w momencie zapłacenia faktury według dat ważności w sekwencji kolejnych rabatów gotówkowych.</span><span class="sxs-lookup"><span data-stu-id="833a6-131">Only one cash discount is granted when the invoice is paid, based on which cash discount date is meet in the sequence of cash discounts.</span></span>

## <a name="example-exchange-rates-for-cash-discounts"></a><span data-ttu-id="833a6-132"> Przykład: Kursy wymiany dla rabatów gotówkowych</span><span class="sxs-lookup"><span data-stu-id="833a6-132">Example: Exchange rates for cash discounts</span></span>
<span data-ttu-id="833a6-133">Waluta rozliczeniowa firmy to EUR i obowiązuj następujący kurs wymiany do USD:</span><span class="sxs-lookup"><span data-stu-id="833a6-133">Your legal entity’s accounting currency is EUR and the following exchange rates are specified for USD:</span></span>
-   <span data-ttu-id="833a6-134">1 lutego = 110</span><span class="sxs-lookup"><span data-stu-id="833a6-134">February 1 = 110</span></span>
-   <span data-ttu-id="833a6-135">1 marca = 80</span><span class="sxs-lookup"><span data-stu-id="833a6-135">March 1 = 80</span></span>

<span data-ttu-id="833a6-136">15 lutego zostanie zaksięgowana faktura za 1000 USD z warunkami rabatu gotówkowego 20D2%.</span><span class="sxs-lookup"><span data-stu-id="833a6-136">An invoice for 1000 USD with cash discount terms of 20D2% is posted on February 15.</span></span> <span data-ttu-id="833a6-137">Kwota faktury w walucie rozliczeniowej wynosi 1100 EUR.</span><span class="sxs-lookup"><span data-stu-id="833a6-137">The accounting currency amount of the invoice is 1100 EUR.</span></span> <span data-ttu-id="833a6-138">Płatność na kwotę 980 USD jest rozliczana z fakturą w dniu 1 marca.</span><span class="sxs-lookup"><span data-stu-id="833a6-138">A payment for 980 USD is settled with the invoice on March 1.</span></span> <span data-ttu-id="833a6-139">Kwota rabatu gotówkowego wynosi 20 USD.</span><span class="sxs-lookup"><span data-stu-id="833a6-139">The cash discount amount is 20 USD.</span></span> <span data-ttu-id="833a6-140">Kwota płatności w walucie rozliczeniowej wynosi 784 EUR.</span><span class="sxs-lookup"><span data-stu-id="833a6-140">The accounting currency amount of the payment is 784 EUR.</span></span> <span data-ttu-id="833a6-141">Kwota rabatu gotówkowego w walucie rozliczeniowej jest obliczana przy użyciu kursu wymiany z dnia 1 marca: 20 \* 80 / 100 = 16 EUR.</span><span class="sxs-lookup"><span data-stu-id="833a6-141">The accounting currency amount of the cash discount is calculated by using the exchange rate as of March 1: 20 \* 80 / 100 = 16 EUR.</span></span>

> [!NOTE]
> <span data-ttu-id="833a6-142">Oblicz na stronach Parametry modułu rozrachunków z odbiorcami lub Parametry modułu rozrachunków z dostawcami wybrana jest opcja Oblicz rabaty gotówkowe dla częściowych zapłat, stosowany jest kurs wymiany z dnia dokonania płatności częściowej.</span><span class="sxs-lookup"><span data-stu-id="833a6-142">If the Calculate cash discounts for partial payments option is selected in the Accounts receivable parameters or Accounts payable parameters pages, the exchange rate that is in effect on the date of each partial payment is used.</span></span> 

