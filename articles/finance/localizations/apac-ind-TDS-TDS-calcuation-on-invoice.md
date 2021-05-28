---
title: Obliczanie TDS dla faktur
description: Ten temat zawiera odwołanie do transakcji, w których podatek potrącony w źródle (TDS) jest obliczany na poziomie faktury.
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
ms.openlocfilehash: 496e87e3028025f738d2f0a697d91c18b77ad1c9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023512"
---
# <a name="tds-calculation-on-invoices"></a><span data-ttu-id="81dde-103">Obliczanie TDS dla faktur</span><span class="sxs-lookup"><span data-stu-id="81dde-103">TDS calculation on invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81dde-104">Ten temat zawiera odwołanie do transakcji, w których podatek potrącony w źródle (TDS) jest obliczany na poziomie faktury.</span><span class="sxs-lookup"><span data-stu-id="81dde-104">This topic provides a reference for transactions where the Tax Deducted at Source (TDS) is calculated at the invoice level.</span></span>

| <span data-ttu-id="81dde-105">Numer seryjny</span><span class="sxs-lookup"><span data-stu-id="81dde-105">Serial number</span></span> | <span data-ttu-id="81dde-106">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="81dde-106">Transaction type</span></span>                                 | <span data-ttu-id="81dde-107">Kwota transakcji</span><span class="sxs-lookup"><span data-stu-id="81dde-107">Transaction amount</span></span> | <span data-ttu-id="81dde-108">Nazwa strony i ścieżka wyboru</span><span class="sxs-lookup"><span data-stu-id="81dde-108">Page name and selection path</span></span>                                 | <span data-ttu-id="81dde-109">Typ konta i typ konta przeciwstawnego</span><span class="sxs-lookup"><span data-stu-id="81dde-109">Account type and offset account type</span></span>                         |
| ------------- | ------------------------------------------------ | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| <span data-ttu-id="81dde-110">1.</span><span class="sxs-lookup"><span data-stu-id="81dde-110">1.</span></span>            | <span data-ttu-id="81dde-111">Zakup dokonany od dostawcy/z rejestrowaniem wydatków</span><span class="sxs-lookup"><span data-stu-id="81dde-111">Purchase made from vendor / recording expenses</span></span>   | <span data-ttu-id="81dde-112">Debet czy Kredyt</span><span class="sxs-lookup"><span data-stu-id="81dde-112">Debit  Or  Credit</span></span>  | <span data-ttu-id="81dde-113">Strona Arkuszy finansowych (Księga główna > Wpisy w arkuszu > Arkusze finansowe), strona arkusza zatwierdzania faktur (Rozrachunki z dostawcami > Faktury > Zatwierdzenie faktury), strona arkusza faktur (Rozrachunki z dostawcami > Faktury > Arkusz faktur)</span><span class="sxs-lookup"><span data-stu-id="81dde-113">General journals page (General ledger >  Journal entries > General journals), Invoice approval journal page (Accounts payable > Invoices > Invoice approval), Invoice journal page (Accounts payable >  Invoices > Invoice journal)</span></span> | <span data-ttu-id="81dde-114">Dostawca (dr.), dostawca (Cr.).</span><span class="sxs-lookup"><span data-stu-id="81dde-114">Ledger (Dr.)  Vendor (Cr.).</span></span>  <span data-ttu-id="81dde-115">Potrącona zaliczka na podatek jest obliczana dla kombinacji Dostawca-Księga tylko wtedy, gdy konto księgowe ma typ księgowania **Zakup** **gotówką**.</span><span class="sxs-lookup"><span data-stu-id="81dde-115">Withholding tax is calculated for the Vendor-Ledger  combination only when the Ledger account has the posting type **Purchase**  **cash**.</span></span> |
| <span data-ttu-id="81dde-116">2.</span><span class="sxs-lookup"><span data-stu-id="81dde-116">2.</span></span>            | <span data-ttu-id="81dde-117">Zakup dokonany od odbiorcy/z rejestrowaniem wydatków</span><span class="sxs-lookup"><span data-stu-id="81dde-117">Purchase made from customer / recording expenses</span></span> | <span data-ttu-id="81dde-118">Debet czy Kredyt</span><span class="sxs-lookup"><span data-stu-id="81dde-118">Debit  Or  Credit</span></span>  | <span data-ttu-id="81dde-119">Strona arkuszy finansowych (Księga główna > Wpisy w arkuszu > Arkusze finansowe), strona arkusza faktur (Rozrachunki z dostawcami > Faktury > Arkusz faktur)</span><span class="sxs-lookup"><span data-stu-id="81dde-119">General journals page (General ledger >  Journal entries > General journals), Invoice journal page (Accounts payable >  Invoices > Invoice journal)</span></span> | <span data-ttu-id="81dde-120">Dostawca (Dr.), odbiorca (Cr.)</span><span class="sxs-lookup"><span data-stu-id="81dde-120">Ledger (Dr.)  Customer (Cr.)</span></span>                                 |
| <span data-ttu-id="81dde-121">3.</span><span class="sxs-lookup"><span data-stu-id="81dde-121">3.</span></span>            | <span data-ttu-id="81dde-122">Zakup środka trwałego od dostawcy</span><span class="sxs-lookup"><span data-stu-id="81dde-122">Purchase of fixed asset from vendor</span></span>              | <span data-ttu-id="81dde-123">Debet czy Kredyt</span><span class="sxs-lookup"><span data-stu-id="81dde-123">Debit  Or  Credit</span></span>  | <span data-ttu-id="81dde-124">Strona Arkuszy finansowych (Księga główna > Wpisy w arkuszu > Arkusze finansowe), strona arkusza rejestru faktur (Rozrachunki z dostawcami > Faktury > Rejestr faktur), strona arkusza faktur (Rozrachunki z dostawcami > Faktury > Arkusz faktur)</span><span class="sxs-lookup"><span data-stu-id="81dde-124">General journals page (General ledger >  Journal entries > General journals), Invoice register journal page (Accounts payable > Invoices > Invoice register), Invoice journal page (Accounts payable >  Invoices > Invoice journal)</span></span> | <span data-ttu-id="81dde-125">Środki trwałe (Dr.) Dostawca (Cr.)</span><span class="sxs-lookup"><span data-stu-id="81dde-125">Fixed assets (Dr.)  Vendor (Cr.)</span></span>                             |
| <span data-ttu-id="81dde-126">4.</span><span class="sxs-lookup"><span data-stu-id="81dde-126">4.</span></span>            | <span data-ttu-id="81dde-127">Zakup środka trwałego od odbiorcy</span><span class="sxs-lookup"><span data-stu-id="81dde-127">Purchase of fixed asset from customer</span></span>            | <span data-ttu-id="81dde-128">Debet czy Kredyt</span><span class="sxs-lookup"><span data-stu-id="81dde-128">Debit  Or  Credit</span></span>  | <span data-ttu-id="81dde-129">Strona arkuszy finansowych (Księga główna > Wpisy w arkuszu > Arkusze finansowe), strona arkusza faktur (Rozrachunki z dostawcami > Faktury > Arkusz faktur)</span><span class="sxs-lookup"><span data-stu-id="81dde-129">General journals page (General ledger >  Journal entries > General journals), Invoice journal page (Accounts payable >  Invoices > Invoice journal)</span></span> | <span data-ttu-id="81dde-130">Środki trwałe (Dr.) Odbiorca (Cr.)</span><span class="sxs-lookup"><span data-stu-id="81dde-130">Fixed assets (Dr.)  Customer (Cr.)</span></span>                           |
| <span data-ttu-id="81dde-131">5.</span><span class="sxs-lookup"><span data-stu-id="81dde-131">5.</span></span>            | <span data-ttu-id="81dde-132">Faktura zakupu (TDS zobowiązań)</span><span class="sxs-lookup"><span data-stu-id="81dde-132">Purchase invoice  (TDS payable)</span></span>                  |                    | <span data-ttu-id="81dde-133">Strona zamówienia zakupu (Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu)</span><span class="sxs-lookup"><span data-stu-id="81dde-133">Purchase order page (Accounts payable > Purchase orders > All purchase orders)</span></span> |                                                              |
| <span data-ttu-id="81dde-134">6.</span><span class="sxs-lookup"><span data-stu-id="81dde-134">6.</span></span>            | <span data-ttu-id="81dde-135">Faktura sprzedaży (należności TDS)</span><span class="sxs-lookup"><span data-stu-id="81dde-135">Sales invoice  (TDS receivable)</span></span>                  |                    | <span data-ttu-id="81dde-136">Strona zamówienia sprzedaży (Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży), strona faktury elektronicznej (Rozrachunki z odbiorcami > Faktury > Wszystkie faktury niezależne)</span><span class="sxs-lookup"><span data-stu-id="81dde-136">Sales order page (Accounts receivable > Orders > All sales orders), Free text invoice page (Accounts receivable > Invoices > All free text invoices)</span></span> |                                                              |