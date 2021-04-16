---
title: Rozliczanie czeku postdatowanego dla dostawcy
description: Rozlicz czek postdatowany wystawiony dostawcy, gdy bank rozliczył transakcję czekiem, który były zaległy, ale został zaakceptowany przez bank.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 89acad0c9421960ff4d07ed8eec798b9068424d5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834578"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="c8589-103">Rozliczanie czeku postdatowanego dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="c8589-103">Settle a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c8589-104">Rozlicz czek postdatowany wystawiony dostawcy, gdy bank rozliczył transakcję czekiem, który były zaległy, ale został zaakceptowany przez bank.</span><span class="sxs-lookup"><span data-stu-id="c8589-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="c8589-105">Przed rozpoczęciem tej procedury wykonaj następujące procedury.</span><span class="sxs-lookup"><span data-stu-id="c8589-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="c8589-106">Konfigurowanie czeków postdatowanych</span><span class="sxs-lookup"><span data-stu-id="c8589-106">Set up postdated checks</span></span>

2) <span data-ttu-id="c8589-107">Rejestrowanie i księgowanie czeku postdatowanego dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="c8589-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="c8589-108">Rolą w tej procedurze jest Skarbnik.</span><span class="sxs-lookup"><span data-stu-id="c8589-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="c8589-109">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="c8589-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="c8589-110">Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Czeki postdatowane odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="c8589-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="c8589-111">Kliknij opcję Rozlicz.</span><span class="sxs-lookup"><span data-stu-id="c8589-111">Click Settle.</span></span>
3. <span data-ttu-id="c8589-112">Kliknij opcję Rozlicz wpisy rozrachunkowe.</span><span class="sxs-lookup"><span data-stu-id="c8589-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="c8589-113">Rozlicz konto dostawcy dla transakcji czekowej.</span><span class="sxs-lookup"><span data-stu-id="c8589-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="c8589-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c8589-114">Close the page.</span></span>
5. <span data-ttu-id="c8589-115">Wybierz kolejno opcje Księga główna > Wpisy w arkuszu > Arkusze finansowe.</span><span class="sxs-lookup"><span data-stu-id="c8589-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="c8589-116">W polu Pokaż wybierz opcję „Wszystko”.</span><span class="sxs-lookup"><span data-stu-id="c8589-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="c8589-117">Zaznacz lub wyczyść pole wyboru Pokaż tylko utworzone przez użytkowników.</span><span class="sxs-lookup"><span data-stu-id="c8589-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="c8589-118">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c8589-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="c8589-119">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="c8589-119">Click Lines.</span></span>
10. <span data-ttu-id="c8589-120">Kliknij opcję Załącznik.</span><span class="sxs-lookup"><span data-stu-id="c8589-120">Click Voucher.</span></span>
11. <span data-ttu-id="c8589-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c8589-121">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]