---
title: Konwencje wynajmu składnika majątku
description: Ten temat opisuje konwencje wynajmowanych składników majątku.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 67c4d2b7162cf6bda2eedfecef43ff0b216e6e6c
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881815"
---
# <a name="asset-leasing-conventions"></a><span data-ttu-id="02d1f-103">Konwencje wynajmu składnika majątku</span><span class="sxs-lookup"><span data-stu-id="02d1f-103">Asset leasing conventions</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="02d1f-104">Ten temat opisuje konwencje wynajmowanych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="02d1f-104">This topic describes conventions for leased assets.</span></span> <span data-ttu-id="02d1f-105">Konwencje wynajmu są używane do określania daty rozpoczęcia księgi wynajmu.</span><span class="sxs-lookup"><span data-stu-id="02d1f-105">Leasing conventions are used to determine the commencement date of a lease book.</span></span> <span data-ttu-id="02d1f-106">Jeśli konwencja wynajmu ma wartość **Brak**, data rozpoczęcia jest taka sama jak data rozpoczęcia wynajmu (to jest wartość pola **Data rozpoczęcia wynajmu**).</span><span class="sxs-lookup"><span data-stu-id="02d1f-106">If the leasing convention is set to **None**, the commencement date is the same as the start date for the lease (that is, the value of the **Lease start date** field).</span></span> <span data-ttu-id="02d1f-107">Jeśli umowa leasingu jest ustawiona na **Pełny miesiąc**, datą rozpoczęcia jest pierwszy dzień miesiąca, w którym przypada data rozpoczęcia leasingu.</span><span class="sxs-lookup"><span data-stu-id="02d1f-107">If the leasing convention is set to **Full month**, the commencement date is the first day of the month that the lease's start date falls in.</span></span>

<span data-ttu-id="02d1f-108">Data rozpoczęcia określa datę rozpoczęcia okresu umorzenia zobowiązań i harmonogramów amortyzacji środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="02d1f-108">The commencement date determines the start date of the period for the liability amortization and asset depreciation schedules.</span></span> <span data-ttu-id="02d1f-109">Wydatki na odsetki i wydatki amortyzacyjne są księgowane w dniu zakończenia okresu odpowiednich harmonogramów.</span><span class="sxs-lookup"><span data-stu-id="02d1f-109">Interest expenses and depreciation expenses are posted on the period end date of the corresponding schedules.</span></span> <span data-ttu-id="02d1f-110">Początkowy wpis arkusza rozpoznawania i korekty jest księgowany w dniu rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="02d1f-110">The initial recognition and adjustment journal entry are posted on the commencement date.</span></span>

> [!NOTE]
> <span data-ttu-id="02d1f-111">Funkcję konwencji wynajmu należy włączyć za pomocą funkcji Zarządzanie funkcjami.</span><span class="sxs-lookup"><span data-stu-id="02d1f-111">The feature for leasing conventions must be turned on through Feature Management.</span></span> <span data-ttu-id="02d1f-112">W obszarze roboczym **Zarządzanie funkcjami** znajdź i wybierz funkcję o nazwie **Konwencja dzierżawy dla funkcji wynajmu środków trwałych**, a następnie wybierz opcję **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="02d1f-112">In the **Feature management** workspace, find and select the feature that is named **Leasing convention for asset leasing** feature, and then select **Enable now**.</span></span>

<span data-ttu-id="02d1f-113">Konfiguracje księgi środków trwałych są przypisywane do konwencji wynajmu.</span><span class="sxs-lookup"><span data-stu-id="02d1f-113">Leasing conventions are assigned to the setup for a lease asset book.</span></span>

<span data-ttu-id="02d1f-114">Aby wyświetlić lub przypisać konwencję wynajmu, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="02d1f-114">To view or assign the leasing convention, follow these steps.</span></span>

1. <span data-ttu-id="02d1f-115">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Księgi wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="02d1f-115">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="02d1f-116">W polu **Konwencja wynajmu** wybierz jedną z następujących wartości.</span><span class="sxs-lookup"><span data-stu-id="02d1f-116">In the **Leasing convention** field, select one of the following values.</span></span>

    | <span data-ttu-id="02d1f-117">Konwencja wynajmu</span><span class="sxs-lookup"><span data-stu-id="02d1f-117">Leasing convention</span></span> | <span data-ttu-id="02d1f-118">opis</span><span class="sxs-lookup"><span data-stu-id="02d1f-118">Description</span></span> |
    |--------------------|-------------|
    | <span data-ttu-id="02d1f-119">None</span><span class="sxs-lookup"><span data-stu-id="02d1f-119">None</span></span>               | <span data-ttu-id="02d1f-120">Harmonogramy umorzenia zobowiązań i amortyzacji środków trwałych rozpoczynają się od daty rozpoczęcia wynajmu, ponieważ data rozpoczęcia jest równa dacie rozpoczęcia wynajmu.</span><span class="sxs-lookup"><span data-stu-id="02d1f-120">The liability amortization and asset depreciation schedules start on the lease's start date, because the commencement date equals the lease's start date.</span></span> <span data-ttu-id="02d1f-121">Data zakończenia jest o miesiąc późniejsza.</span><span class="sxs-lookup"><span data-stu-id="02d1f-121">The end date is one month later.</span></span> <span data-ttu-id="02d1f-122">Ta konwencja wynajmu nie gwarantuje, że odsetki będą księgowane ostatniego dnia każdego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="02d1f-122">This leasing convention doesn't guarantee that the interest will be posted on the last day of each month.</span></span> |
    | <span data-ttu-id="02d1f-123">Pełny miesiąc</span><span class="sxs-lookup"><span data-stu-id="02d1f-123">Full month</span></span>         | <span data-ttu-id="02d1f-124">W przypadku dzierżaw o dacie rozpoczęcia, która ma miejsce o dowolnej godzinie w miesiącu, amortyzacja zobowiązań i plany amortyzacji środków trwałych zaczynają się do naliczania wydatków w pierwszym dniu tego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="02d1f-124">For leases that have a start date that occurs at any time during the month, the liability amortization and asset depreciation schedules start to accrue expenses on the first day of that month.</span></span> <span data-ttu-id="02d1f-125">Ta konwencja wynajmu gwarantuje naliczanie odsetek w ostatnim dniu każdego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="02d1f-125">This leasing convention ensures that interest is accrued on the last day of each month for the whole month.</span></span> |

3. <span data-ttu-id="02d1f-126">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="02d1f-126">Select **Save**.</span></span>

<span data-ttu-id="02d1f-127">Po utworzeniu wynajmu data rozpoczęcia każdej książki jest automatycznie wprowadzana na podstawie wprowadzonej daty rozpoczęcia leasingu i konwencji wynajmu określonej dla książki.</span><span class="sxs-lookup"><span data-stu-id="02d1f-127">When a lease is created, the commencement date of each book is automatically entered based on the start date that is entered for the lease and the leasing convention that is specified for the book.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
