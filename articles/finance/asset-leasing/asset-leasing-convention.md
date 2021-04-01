---
title: Konwencje wynajmu składnika majątku
description: Ten temat opisuje konwencje wynajmowanych składników majątku.
author: moaamer
manager: Ann Beebe
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 7072c34ccbffc6bf135f55fd594cac4d9ea5a463
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237523"
---
# <a name="asset-leasing-conventions"></a><span data-ttu-id="33ef6-103">Konwencje wynajmu składnika majątku</span><span class="sxs-lookup"><span data-stu-id="33ef6-103">Asset leasing conventions</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="33ef6-104">Ten temat opisuje konwencje wynajmowanych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="33ef6-104">This topic describes conventions for leased assets.</span></span> <span data-ttu-id="33ef6-105">Konwencje wynajmu są używane do określania daty rozpoczęcia księgi wynajmu.</span><span class="sxs-lookup"><span data-stu-id="33ef6-105">Leasing conventions are used to determine the commencement date of a lease book.</span></span> <span data-ttu-id="33ef6-106">Jeśli konwencja wynajmu ma wartość **Brak**, data rozpoczęcia jest taka sama jak data rozpoczęcia wynajmu (to jest wartość pola **Data rozpoczęcia wynajmu**).</span><span class="sxs-lookup"><span data-stu-id="33ef6-106">If the leasing convention is set to **None**, the commencement date is the same as the start date for the lease (that is, the value of the **Lease start date** field).</span></span> <span data-ttu-id="33ef6-107">Jeśli umowa leasingu jest ustawiona na **Pełny miesiąc**, datą rozpoczęcia jest pierwszy dzień miesiąca, w którym przypada data rozpoczęcia leasingu.</span><span class="sxs-lookup"><span data-stu-id="33ef6-107">If the leasing convention is set to **Full month**, the commencement date is the first day of the month that the lease's start date falls in.</span></span>

<span data-ttu-id="33ef6-108">Data rozpoczęcia określa datę rozpoczęcia okresu umorzenia zobowiązań i harmonogramów amortyzacji środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="33ef6-108">The commencement date determines the start date of the period for the liability amortization and asset depreciation schedules.</span></span> <span data-ttu-id="33ef6-109">Wydatki na odsetki i wydatki amortyzacyjne są księgowane w dniu zakończenia okresu odpowiednich harmonogramów.</span><span class="sxs-lookup"><span data-stu-id="33ef6-109">Interest expenses and depreciation expenses are posted on the period end date of the corresponding schedules.</span></span> <span data-ttu-id="33ef6-110">Początkowy wpis arkusza rozpoznawania i korekty jest księgowany w dniu rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="33ef6-110">The initial recognition and adjustment journal entry are posted on the commencement date.</span></span>

> [!NOTE]
> <span data-ttu-id="33ef6-111">Funkcję konwencji wynajmu należy włączyć za pomocą funkcji Zarządzanie funkcjami.</span><span class="sxs-lookup"><span data-stu-id="33ef6-111">The feature for leasing conventions must be turned on through Feature Management.</span></span> <span data-ttu-id="33ef6-112">W obszarze roboczym **Zarządzanie funkcjami** znajdź i wybierz funkcję o nazwie **Konwencja dzierżawy dla funkcji wynajmu środków trwałych**, a następnie wybierz opcję **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="33ef6-112">In the **Feature management** workspace, find and select the feature that is named **Leasing convention for asset leasing** feature, and then select **Enable now**.</span></span>

<span data-ttu-id="33ef6-113">Konfiguracje księgi środków trwałych są przypisywane do konwencji wynajmu.</span><span class="sxs-lookup"><span data-stu-id="33ef6-113">Leasing conventions are assigned to the setup for a lease asset book.</span></span>

<span data-ttu-id="33ef6-114">Aby wyświetlić lub przypisać konwencję wynajmu, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="33ef6-114">To view or assign the leasing convention, follow these steps.</span></span>

1. <span data-ttu-id="33ef6-115">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Księgi wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="33ef6-115">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="33ef6-116">W polu **Konwencja wynajmu** wybierz jedną z następujących wartości.</span><span class="sxs-lookup"><span data-stu-id="33ef6-116">In the **Leasing convention** field, select one of the following values.</span></span>

    | <span data-ttu-id="33ef6-117">Konwencja wynajmu</span><span class="sxs-lookup"><span data-stu-id="33ef6-117">Leasing convention</span></span> | <span data-ttu-id="33ef6-118">opis</span><span class="sxs-lookup"><span data-stu-id="33ef6-118">Description</span></span> |
    |--------------------|-------------|
    | <span data-ttu-id="33ef6-119">None</span><span class="sxs-lookup"><span data-stu-id="33ef6-119">None</span></span>               | <span data-ttu-id="33ef6-120">Harmonogramy umorzenia zobowiązań i amortyzacji środków trwałych rozpoczynają się od daty rozpoczęcia wynajmu, ponieważ data rozpoczęcia jest równa dacie rozpoczęcia wynajmu.</span><span class="sxs-lookup"><span data-stu-id="33ef6-120">The liability amortization and asset depreciation schedules start on the lease's start date, because the commencement date equals the lease's start date.</span></span> <span data-ttu-id="33ef6-121">Data zakończenia jest o miesiąc późniejsza.</span><span class="sxs-lookup"><span data-stu-id="33ef6-121">The end date is one month later.</span></span> <span data-ttu-id="33ef6-122">Ta konwencja wynajmu nie gwarantuje, że odsetki będą księgowane ostatniego dnia każdego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="33ef6-122">This leasing convention doesn't guarantee that the interest will be posted on the last day of each month.</span></span> |
    | <span data-ttu-id="33ef6-123">Pełny miesiąc</span><span class="sxs-lookup"><span data-stu-id="33ef6-123">Full month</span></span>         | <span data-ttu-id="33ef6-124">W przypadku dzierżaw o dacie rozpoczęcia, która ma miejsce o dowolnej godzinie w miesiącu, amortyzacja zobowiązań i plany amortyzacji środków trwałych zaczynają się do naliczania wydatków w pierwszym dniu tego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="33ef6-124">For leases that have a start date that occurs at any time during the month, the liability amortization and asset depreciation schedules start to accrue expenses on the first day of that month.</span></span> <span data-ttu-id="33ef6-125">Ta konwencja wynajmu gwarantuje naliczanie odsetek w ostatnim dniu każdego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="33ef6-125">This leasing convention ensures that interest is accrued on the last day of each month for the whole month.</span></span> |

3. <span data-ttu-id="33ef6-126">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="33ef6-126">Select **Save**.</span></span>

<span data-ttu-id="33ef6-127">Po utworzeniu wynajmu data rozpoczęcia każdej książki jest automatycznie wprowadzana na podstawie wprowadzonej daty rozpoczęcia leasingu i konwencji wynajmu określonej dla książki.</span><span class="sxs-lookup"><span data-stu-id="33ef6-127">When a lease is created, the commencement date of each book is automatically entered based on the start date that is entered for the lease and the leasing convention that is specified for the book.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]