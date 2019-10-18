---
title: Czeki postdatowane
description: Ten artykuł zawiera informacje o obsłudze czeków postdatowanych w Microsoft Dynamics 365 Finance. Czeki postdatowane są wystawiane do celów wykonywania i odbierania płatności w przyszłości. W związku z tym czeki można zrealizować dopiero od określonego dnia.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 38ee6c5b3d258c313a2066b388a83330bf696d39
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179430"
---
# <a name="postdated-checks"></a><span data-ttu-id="80e55-105">Czeki postdatowane</span><span class="sxs-lookup"><span data-stu-id="80e55-105">Postdated checks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80e55-106">Ten artykuł zawiera informacje o obsłudze czeków postdatowanych.</span><span class="sxs-lookup"><span data-stu-id="80e55-106">This article provides information about support for postdated checks.</span></span> <span data-ttu-id="80e55-107">Czeki postdatowane są wystawiane do celów wykonywania i odbierania płatności w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="80e55-107">Postdated checks are checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="80e55-108">W związku z tym czeki można zrealizować dopiero od określonego dnia.</span><span class="sxs-lookup"><span data-stu-id="80e55-108">Therefore, the check can't be cashed until the specified date.</span></span>

<span data-ttu-id="80e55-109">Dynamics 365 Finance obsługuje pełny cykl zarządzania dla czeków postdatowanych w module Rozrachunki z odbiorcami i Rozrachunki z dostawcami, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="80e55-109">Dynamics 365 Finance supports the full management cycle for postdated checks in both Accounts receivable and Accounts payable, as shown in the following table.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80e55-110">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="80e55-110">Scenario</span></span></th>
<th><span data-ttu-id="80e55-111">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="80e55-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="80e55-112">Konfigurowanie czeków postdatowanych</span><span class="sxs-lookup"><span data-stu-id="80e55-112">Set up postdated checks</span></span></td>
<td><span data-ttu-id="80e55-113">Należy utworzyć nową metodę płatności oraz określić procedurę płatności umożliwiającą rozliczanie kont czeków wystawionych, czeków otrzymanych i potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="80e55-113">You must set up a new payment method, and specify the payment routine for clearing accounts for issued checks, received checks, and withholding tax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="80e55-114">Rejestruje czek postdatowany dla dostawcy i księgowanie</span><span class="sxs-lookup"><span data-stu-id="80e55-114">Register and post a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="80e55-115">Zapisujesz szczegóły czeku postdatowanego wystawionego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="80e55-115">Register the details of a postdated check that you issue to a vendor.</span></span> <span data-ttu-id="80e55-116">Po zaksięgowaniu płatności zobowiązanie wobec dostawcy jest rozpoznawane, ale konto bankowe nie jest jeszcze uznawane.</span><span class="sxs-lookup"><span data-stu-id="80e55-116">When the payment is posted, the vendor liability is recognized, but the bank account isn’t yet credit.</span></span> <span data-ttu-id="80e55-117">Zamiast tego jest używane konto rozliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="80e55-117">Instead, a clearing account is used for this purpose.</span></span> </td>
</tr>
<tr class="odd">
<td><span data-ttu-id="80e55-118">Rejestrowanie i księgowanie czeku postdatowanego dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="80e55-118">Register and post a postdated check for a customer</span></span></td>
<td><span data-ttu-id="80e55-119">Zapisujesz szczegóły czeku postdatowanego otrzymanego od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="80e55-119">Register the details of a postdated check that you receive from a customer.</span></span> <span data-ttu-id="80e55-120">Po zaksięgowaniu płatności należność od odbiorcy jest księgowana po stronie kredytowej, ale konto bankowe nie jest jeszcze obciążane.</span><span class="sxs-lookup"><span data-stu-id="80e55-120">When the payment is posted, the customer receivable is credit, but the bank account isn’t yet debit.</span></span> <span data-ttu-id="80e55-121">Zamiast tego jest używane konto rozliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="80e55-121">Instead, a clearing account is used for this purpose.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="80e55-122">Rejestrowanie i księgowanie zastępczego czeku postdatowanego dla dostawcy lub odbiorcy</span><span class="sxs-lookup"><span data-stu-id="80e55-122">Register and post a replacement postdated check for a customer or a vendor</span></span></td>
<td>
<span data-ttu-id="80e55-123">Jeśli oryginalny czek dla dostawcy lub odbiorcy został zniszczony lub utracony, można wystawić zastępczy czek postdatowany.</span><span class="sxs-lookup"><span data-stu-id="80e55-123">If your original check to a vendor or from a customer is lost or damaged, you can issue a replacement postdated check.</span></span> <span data-ttu-id="80e55-124">Podczas rejestrowania szczegółów czeku podaj odwołanie do oryginalnego czeku oraz wskaż, że nowy czek zastępuje oryginał.</span><span class="sxs-lookup"><span data-stu-id="80e55-124">When you register the check details, provide a reference to the original check, and indicate that the new check is a replacement for the original.</span></span> <span data-ttu-id="80e55-125">Można również zaksięgować czek zastępczy.</span><span class="sxs-lookup"><span data-stu-id="80e55-125">You can also post the replacement check.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="80e55-126">Przenoszenie czeku postdatowanego odbiorcy do dostawcy</span><span class="sxs-lookup"><span data-stu-id="80e55-126">Transfer a customer postdated check to a vendor</span></span></td>
<td><span data-ttu-id="80e55-127">Po otrzymaniu czeku postdatowanego od odbiorcy można go przenieść do dostawcy jako płatność.</span><span class="sxs-lookup"><span data-stu-id="80e55-127">When you receive a postdated check from a customer, you can transfer that check to a vendor as a payment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="80e55-128">Rozliczenia postdatowanego czeku dla odbiorcy lub dostawcy</span><span class="sxs-lookup"><span data-stu-id="80e55-128">Settle a postdated check for a customer or a vendor</span></span></td>
<td><span data-ttu-id="80e55-129">Rozliczanie w dniu terminu płatności czeku postdatowanego, który został zaksięgowany na koncie pomostowym dla odbiorcy lub dostawcy.</span><span class="sxs-lookup"><span data-stu-id="80e55-129">Settle a postdated check that is posted to a bridging account for a customer or a vendor when the check finally matures.</span></span> <span data-ttu-id="80e55-130">Po rozliczeniu czeku konto bankowe jest ostatecznie obciążane lub uznawane względem użytego wcześniej konta rozliczeniowego.</span><span class="sxs-lookup"><span data-stu-id="80e55-130">When the check is settled, the bank is finally debit or credit against the clearing account that was used earlier.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="80e55-131">Anulowanie postdatowanego czeku dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="80e55-131">Cancel a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="80e55-132">Zaksięgowany czek postdatowany można anulować w następujących sytuacjach: - Czek jest zwracany przez bank.</span><span class="sxs-lookup"><span data-stu-id="80e55-132">You can cancel a posted postdated check in these situations: - The check is returned by the bank.</span></span>
<span data-ttu-id="80e55-133">- Czeku dotyczy błędna faktura.</span><span class="sxs-lookup"><span data-stu-id="80e55-133">- The check is applied to an incorrect invoice.</span></span>
<span data-ttu-id="80e55-134">- Dokonywana jest płatność gotówką względem czeku.</span><span class="sxs-lookup"><span data-stu-id="80e55-134">- A cash payment is made against the check.</span></span>
  </td>
  </tr>
  <tr class="even">
  <td><span data-ttu-id="80e55-135">Zatrzymywanie płatności czeku postdatowanego</span><span class="sxs-lookup"><span data-stu-id="80e55-135">Stop payment for a postdated check</span></span></td>
  <td><span data-ttu-id="80e55-136">Można zatrzymać zapłatę czeku postdatowanego wystawionego dostawcy, np. z powodu niewystarczających funduszy, zmiany warunków umowy z dostawcą, dostawy wadliwych towarów przez dostawcę lub zwrotu towarów do dostawcy.</span><span class="sxs-lookup"><span data-stu-id="80e55-136">You can stop payment on a postdated check that was issued to a vendor, for reasons such as not sufficient funds, changes in the terms of the agreement with the vendor, supply of defective goods by the vendor, or return of goods to the vendor.</span></span> <span data-ttu-id="80e55-137">Zatrzymać można zapłatę tylko czeków nierozliczonych.</span><span class="sxs-lookup"><span data-stu-id="80e55-137">You can stop payment only on checks that haven’t cleared.</span></span></td>
  </tr>
  </tbody>
  </table>



<span data-ttu-id="80e55-138">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="80e55-138">For more information, see the following topics:</span></span>

[<span data-ttu-id="80e55-139">Konfigurowanie czeków postdatowanych</span><span class="sxs-lookup"><span data-stu-id="80e55-139">Set up postdated checks</span></span>](tasks/set-up-postdated-checks.md)

[<span data-ttu-id="80e55-140">Rejestrowanie i księgowanie czeku postdatowanego dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="80e55-140">Register and post a postdated check for a customer</span></span>](tasks/register-post-postdated-check-customer.md)

[<span data-ttu-id="80e55-141">Rozliczanie czeku postdatowanego od odbiorcy</span><span class="sxs-lookup"><span data-stu-id="80e55-141">Settle a postdated check from a customer</span></span>](tasks/settle-postdated-check-customer.md)

[<span data-ttu-id="80e55-142">Rejestrowanie i księgowanie czeku postdatowanego dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="80e55-142">Register and post a postdated check for a vendor</span></span>](tasks/register-post-postdated-check-vendor.md) 

[<span data-ttu-id="80e55-143">Rozliczanie czeku postdatowanego dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="80e55-143">Settle a postdated check for a vendor</span></span>](tasks/settle-postdated-check-vendor.md)



