---
title: Limit progowy i limit progowy wyjątków
description: W tym temacie opisano progi i limity wyjątków dotyczące potrącanych podatków w źródle (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1bf0d3a01ede559d288581d3b58b3777d0e608dc
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023502"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a><span data-ttu-id="bfadd-103">Limit progowy i limit progowy wyjątków</span><span class="sxs-lookup"><span data-stu-id="bfadd-103">Threshold limit and exception threshold limit</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bfadd-104">W tym temacie opisano progi i limity wyjątków dotyczące potrącanych podatków w źródle (TDS).</span><span class="sxs-lookup"><span data-stu-id="bfadd-104">This topic describes the threshold and exception limits for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="bfadd-105">IdentyfikatorY TDS faktur i płatności są zawsze obliczane z uwzględnieniem limitu progowego i limitu progu wyjątku zdefiniowanego dla składników podatku TDS na stronie **Składniki potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="bfadd-105">The TDS on invoices and payments is always calculated considering the threshold limit and exception threshold limit defined for the TDS tax components on the **Withholding tax components** page.</span></span> <span data-ttu-id="bfadd-106">Składniki podatku TDS są dołączane do kodów podatku TDS, które są zawarte w grupach podatków TDS.</span><span class="sxs-lookup"><span data-stu-id="bfadd-106">The TDS tax components are attached to TDS tax codes, which are included in the TDS tax groups.</span></span> <span data-ttu-id="bfadd-107">Grupy podatków TDS są dołączane do dostawców i odbiorców w celu obliczania TDS na poziomie faktury lub na poziomie płatności.</span><span class="sxs-lookup"><span data-stu-id="bfadd-107">The TDS tax groups are attached to vendors and customers to calculate TDS at the invoice-level or payment-level.</span></span>

<span data-ttu-id="bfadd-108">Identyfikator TDS jest obliczany, jeśli kwota transakcji lub skumulowanych transakcji zaksięgowanych z określoną grupą TDS dla dostawcy przekracza limit progowy określony na stronie **Składniki potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="bfadd-108">TDS is calculated if the amount for a transaction or the cumulative transactions posted with a specific TDS group for a vendor exceeds the threshold limit specified on the **Withholding tax components** page.</span></span> <span data-ttu-id="bfadd-109">Identyfikator TDS zostanie obliczony dopiero po przekroczeniu określonego limitu progowego skumulowanej kwoty transakcji.</span><span class="sxs-lookup"><span data-stu-id="bfadd-109">TDS will not be calculated until the cumulative transaction amount exceeds the specified threshold limit.</span></span>

<span data-ttu-id="bfadd-110">Jeśli wraz z limitem progowym dla składnika TDS zostanie określony limit progowy wyjątku, identyfikator TDS jest obliczany, gdy określona kwota transakcji przekracza limit progu wyjątku, nawet jeśli skumulowana kwota transakcji nie przekracza określonego limitu progowego.</span><span class="sxs-lookup"><span data-stu-id="bfadd-110">If an exception threshold limit is specified along with the threshold limit for a TDS component, TDS is calculated when a specific transaction amount exceeds the exception threshold limit even if the cumulative transaction amount does not exceed the specified threshold limit.</span></span>

### <a name="example"></a><span data-ttu-id="bfadd-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="bfadd-111">Example</span></span>
<span data-ttu-id="bfadd-112">Składnik podatku o nazwie TDS jest ustawiany i dołączany do grupy podatków TDS o nazwie Zleceniobiorcy.</span><span class="sxs-lookup"><span data-stu-id="bfadd-112">A tax component called TDS is set up and attached to the TDS tax group called Contractor.</span></span> <span data-ttu-id="bfadd-113">Próg został zdefiniowany jako 50 000, a próg wyjątku został zdefiniowany jako 20 000 dla składnika podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="bfadd-113">The threshold has been defined as 50,000 and exception threshold has been defined as 20,000 for TDS tax component.</span></span> <span data-ttu-id="bfadd-114">Zleceniobiorcy grupy TDS są definiowani jako domyślna grupa TDS dla dostawcy 1.</span><span class="sxs-lookup"><span data-stu-id="bfadd-114">The TDS group contractor is defined as the default TDS group for vendor 1.</span></span>

<span data-ttu-id="bfadd-115">Faktura zakupu 001 jest księgowana dla dostawcy 1 na 10000.</span><span class="sxs-lookup"><span data-stu-id="bfadd-115">A purchase invoice 001 is posted for vendor 1 for 10000.</span></span> <span data-ttu-id="bfadd-116">Identyfikator TDS nie jest obliczany dla faktury, ponieważ kwota faktury nie przekroczyła limitu progowego lub limitu progowego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="bfadd-116">TDS is not calculated for the invoice because the invoice amount has not crossed the threshold limit or exception threshold limit.</span></span> <span data-ttu-id="bfadd-117">Faktura zakupu 002 jest księgowana dla dostawcy 1 na 25,000.</span><span class="sxs-lookup"><span data-stu-id="bfadd-117">A purchase invoice 002 is posted for vendor 1 for 25,000.</span></span> <span data-ttu-id="bfadd-118">TDS jest obliczany dla faktury, ponieważ kwota faktury przekroczyła próg wyjątku.</span><span class="sxs-lookup"><span data-stu-id="bfadd-118">TDS is calculated for the invoice because the invoice amount has crossed the exception threshold limit.</span></span> <span data-ttu-id="bfadd-119">Faktura zakupu 003 jest księgowana dla Dostawcy 1 na 20 000.</span><span class="sxs-lookup"><span data-stu-id="bfadd-119">A purchase invoice 003 is posted for Vendor 1 for 20,000.</span></span> <span data-ttu-id="bfadd-120">Identyfikator TDS jest obliczany dla faktury, ponieważ łączna kwota faktury z trzech faktur wystawionych dla dostawcy przekroczyła limit progowy.</span><span class="sxs-lookup"><span data-stu-id="bfadd-120">TDS is calculated for the invoice because the total invoice amount of the three invoices that are issued for the vendor has crossed the threshold limit.</span></span> <span data-ttu-id="bfadd-121">Identyfikator TDS jest obliczany na wszystkich fakturach wystawionych dla dostawcy, dla którego nie został on wcześniej obliczony.</span><span class="sxs-lookup"><span data-stu-id="bfadd-121">TDS is calculated on all invoices that are issued for the vendor on which the TDS has not been calculated earlier.</span></span> <span data-ttu-id="bfadd-122">Dlatego też identyfikator TDS jest obliczany na kwotę 30 000, czyli łączną kwotę faktury dla faktur 001 i 003.</span><span class="sxs-lookup"><span data-stu-id="bfadd-122">Therefore, TDS is calculated on 30,000, which is the total invoice amount of invoice 001 and 003.</span></span>

<span data-ttu-id="bfadd-123">Limit progowy i limit progowy wyjątku nie są uwzględniane przy obliczaniu TDS, jeśli pole wyboru **Próg przekroczenia progu** jest zaznaczone dla kodów podatku TDS w grupie TDS, która jest dołączona do transakcji.</span><span class="sxs-lookup"><span data-stu-id="bfadd-123">The threshold limit and exception threshold limit are not considered for the TDS calculation if the **Overlook threshold** check box is selected for TDS tax codes in the TDS group that is attached to the transaction.</span></span> <span data-ttu-id="bfadd-124">Limit progowy nie będzie używany w kodach podatków TDS w grupie TDS, dla której jest używane pole wyboru **Przeoczenie progu**.</span><span class="sxs-lookup"><span data-stu-id="bfadd-124">The threshold limit won't be used in the TDS tax codes in the TDS group that the **Overlook threshold** check box is for.</span></span>

<span data-ttu-id="bfadd-125">Jeśli dla niektórych faktur jest zaznaczone pole wyboru **Przeoczenie progu**, ale nie zostało zaznaczone dla innych faktur utworzonych dla określonego dostawcy/odbiorcy, obliczenie TDS bez przeoczenia limitu progowego dla kilku faktur może mieć miejsce z uwzględnieniem kwoty skumulowanej na wszystkich fakturach, dla których nie obliczono wcześniej identyfikatorów TDS.</span><span class="sxs-lookup"><span data-stu-id="bfadd-125">If the **Overlook threshold** check box is selected for a specific TDS group for some invoices, but not selected for other invoices that were created for a specific vendor/customer, the calculation of TDS without overlooking the threshold limit for few invoices may take place considering the cumulative amount on all invoices on which TDS hasn't been calculated earlier.</span></span>

<span data-ttu-id="bfadd-126">Na przykład limit progu wynosi 25000.</span><span class="sxs-lookup"><span data-stu-id="bfadd-126">For example, the threshold limit is 25000.</span></span> <span data-ttu-id="bfadd-127">Następujące faktury są tworzone dla dostawcy A.</span><span class="sxs-lookup"><span data-stu-id="bfadd-127">The following invoices are created for Vendor A.</span></span>

- <span data-ttu-id="bfadd-128">Faktura 1 – 20000 — (Pole wyboru **Przeoczenie progu nie jest zaznaczone**). Identyfikator TDS nie jest obliczany.</span><span class="sxs-lookup"><span data-stu-id="bfadd-128">Invoice 1 – 2,0000 – (**Overlook threshold** check box is not selected): TDS is not calculated.</span></span>

- <span data-ttu-id="bfadd-129">Faktura 2 – 4000 — (Pole wyboru **Przeoczenie progu nie jest zaznaczone**). TDS jest obliczany na podstawie 4000.</span><span class="sxs-lookup"><span data-stu-id="bfadd-129">Invoice 2 – 4,000 – (**Overlook threshold** check box is selected): TDS is calculated on 4,000.</span></span>

- <span data-ttu-id="bfadd-130">Faktura 2 – 3000 — (Przeocz pole wyboru **Przeocz wartość progową** nie jest zaznaczone). Identyfikator TDS jest obliczany jako suma kwoty faktury, 27,000 (20000+4000+3000) przekracza limit progowy.</span><span class="sxs-lookup"><span data-stu-id="bfadd-130">Invoice 2 – 3,000 – (**Overlook threshold** check box is not selected): TDS is calculated as the cumulative invoice amount, that is, 27,000 (20000+4000+3000) exceeded the threshold limit.</span></span> <span data-ttu-id="bfadd-131">Identyfikator TDS jest obliczany na podstawie skumulowanej kwoty faktur, dla których identyfikator TDS nie został wcześniej obliczony, 23 000 (20000+3000).</span><span class="sxs-lookup"><span data-stu-id="bfadd-131">TDS is calculated on the cumulative amount of invoices on which the TDS has not been calculated earlier, that is, 23,000 (20000+3000).</span></span>