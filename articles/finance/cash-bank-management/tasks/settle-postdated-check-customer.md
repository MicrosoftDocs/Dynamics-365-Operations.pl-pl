---
title: Rozliczanie czeku postdatowanego od odbiorcy
description: Można rozliczyć czek postdatowany po jego rozliczeniu przez bank.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f714e41f47a31bce16424de18878d2f5acb5028d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834556"
---
# <a name="settle-a-postdated-check-from-a-customer"></a><span data-ttu-id="bc535-103">Rozliczanie czeku postdatowanego od odbiorcy</span><span class="sxs-lookup"><span data-stu-id="bc535-103">Settle a postdated check from a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bc535-104">Można rozliczyć czek postdatowany po jego rozliczeniu przez bank.</span><span class="sxs-lookup"><span data-stu-id="bc535-104">You can settle a postdated check after the check has been cleared by the bank.</span></span> <span data-ttu-id="bc535-105">Ta transakcja finansowa rozlicza także transakcję konta pomostowego dla czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="bc535-105">This financial transaction also clears the bridge account transaction for the postdated check.</span></span> 

<span data-ttu-id="bc535-106">Przed rozpoczęciem tego zadania muszą być ukończone następujące zadania.</span><span class="sxs-lookup"><span data-stu-id="bc535-106">The following tasks must be complete before you start this one.</span></span>

1) <span data-ttu-id="bc535-107">Konfigurowanie czeków postdatowanych</span><span class="sxs-lookup"><span data-stu-id="bc535-107">Set up postdated checks</span></span>

2) <span data-ttu-id="bc535-108">Rejestrowanie i księgowanie czeku postdatowanego dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="bc535-108">Register and post a postdated check for a customer</span></span> 



<span data-ttu-id="bc535-109">Rolą w tym przewodniku po zadaniach jest Skarbnik.</span><span class="sxs-lookup"><span data-stu-id="bc535-109">The role of this task guides is Treasurer.</span></span>



<span data-ttu-id="bc535-110">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="bc535-110">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="bc535-111">Wybierz kolejno opcje Kredyty i windykacja > Zapytania i raporty > Płatności > Czeki postdatowane odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="bc535-111">Go to Credit and collections > Inquiries and reports > Payments > Customer postdated checks.</span></span>
2. <span data-ttu-id="bc535-112">Kliknij opcję Rozlicz.</span><span class="sxs-lookup"><span data-stu-id="bc535-112">Click Settle.</span></span>
3. <span data-ttu-id="bc535-113">Kliknij opcję Rozlicz wpisy rozrachunkowe.</span><span class="sxs-lookup"><span data-stu-id="bc535-113">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="bc535-114">Rozlicz konto odbiorcy dla transakcji czekowej.</span><span class="sxs-lookup"><span data-stu-id="bc535-114">Settle the customer account for the check transaction.</span></span>  
4. <span data-ttu-id="bc535-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bc535-115">Close the page.</span></span>
5. <span data-ttu-id="bc535-116">Wybierz kolejno opcje Księga główna > Wpisy w arkuszu > Arkusze finansowe.</span><span class="sxs-lookup"><span data-stu-id="bc535-116">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="bc535-117">W polu Pokaż wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="bc535-117">In the Show field, select an option.</span></span>
7. <span data-ttu-id="bc535-118">Zaznacz lub wyczyść pole wyboru Pokaż tylko utworzone przez użytkowników.</span><span class="sxs-lookup"><span data-stu-id="bc535-118">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="bc535-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="bc535-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="bc535-120">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="bc535-120">Click Lines.</span></span>
10. <span data-ttu-id="bc535-121">Kliknij opcję Załącznik.</span><span class="sxs-lookup"><span data-stu-id="bc535-121">Click Voucher.</span></span>
11. <span data-ttu-id="bc535-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bc535-122">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]