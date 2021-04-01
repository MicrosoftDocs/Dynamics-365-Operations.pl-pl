---
title: Zmniejszanie dni na opłaty subskrypcji
description: Aby zredukować liczbę dni w ramach już istniejącej opłaty subskrypcji, można utworzyć nową transakcję i usunąć okres, który ma nie należeć do okresu opłaty subskrypcji.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65cd852ca3ce0446550f9ac148a14bbc6bcae500
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234784"
---
# <a name="reduce-the-days-on-subscription-fees"></a><span data-ttu-id="4e6ee-103">Zmniejszanie dni na opłaty subskrypcji</span><span class="sxs-lookup"><span data-stu-id="4e6ee-103">Reduce the days on subscription fees</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="4e6ee-104">Aby zredukować liczbę dni w ramach już istniejącej opłaty subskrypcji, można utworzyć nową transakcję i usunąć okres, który ma nie należeć do okresu opłaty subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="4e6ee-104">To reduce the number of days of an existing subscription fee, you can create a new transaction in which you remove the period of time that should no longer be part of the subscription fee interval.</span></span>

## <a name="reduce-the-days-on-a-subscription-fee"></a><span data-ttu-id="4e6ee-105">Redukcja dni opłaty subskrypcji</span><span class="sxs-lookup"><span data-stu-id="4e6ee-105">Reduce the days on a subscription fee</span></span>

1.  <span data-ttu-id="4e6ee-106">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Subskrypcje serwisowe** \> **Wszystkie subskrypcje serwisu**.</span><span class="sxs-lookup"><span data-stu-id="4e6ee-106">Click **Service management** \> **Common** \> **Service subscriptions** \> **All service subscriptions**.</span></span> <span data-ttu-id="4e6ee-107">Zaznacz subskrypcję serwisu, a następnie w okienku akcji kliknij opcję **Opłaty subskrypcji**.</span><span class="sxs-lookup"><span data-stu-id="4e6ee-107">Select the service subscription, and on the Action Pane, click **Subscription fees**</span></span>

2.  <span data-ttu-id="4e6ee-108">W polu **Typ subskrypcji** zaznacz opcję **Dni redukcji**.</span><span class="sxs-lookup"><span data-stu-id="4e6ee-108">In the **Subscription type** field, select **Reduction days**.</span></span>

3.  <span data-ttu-id="4e6ee-109">W polach **Od dnia** i **Do dnia** określ przedział czasu w ramach opłaty subskrypcji, który ma zostać usunięty z okresu opłaty subskrypcji, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e6ee-109">Use the **From date** field and the **To date** fields to define the date interval of the subscription fee that you want to remove from the subscription fee period, and then click **OK**.</span></span>

<span data-ttu-id="4e6ee-110">Aby przejrzeć utworzoną transakcję, w formularzu **Subskrypcja** kliknij opcję **Transakcje opłat**.</span><span class="sxs-lookup"><span data-stu-id="4e6ee-110">To view the transaction that was created, in the **Subscription** form, click **Fee transactions**.</span></span>

## <a name="example"></a><span data-ttu-id="4e6ee-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="4e6ee-111">Example</span></span>

<span data-ttu-id="4e6ee-112">Jeśli okres transakcji subskrypcji trwa od 1 do 31 stycznia i trzeba ten okres zmniejszyć o 10 dni, to należy utworzyć nową transakcję, w której okres redukcji trwa od 1 do 10 stycznia.</span><span class="sxs-lookup"><span data-stu-id="4e6ee-112">If a subscription transaction period runs from January 1 to January 31, and you want to reduce the period by 10 days, create a new transaction in which the reduction period is January 1 to January 10.</span></span> <span data-ttu-id="4e6ee-113">(Okresem redukcji może też być przedział czasu od 5 do 15 stycznia lub dowolny inny 10-dniowy okres).</span><span class="sxs-lookup"><span data-stu-id="4e6ee-113">(The reduction period could also be January 5 to January 15, or any other ten day period).</span></span>

<span data-ttu-id="4e6ee-114">Ponadto jeśli w polu **Od dnia** dla okresu redukcji podano dzień 21 stycznia (31 minus 10), to w polu **Do dnia** można wprowadzić dowolny dzień po 31 stycznia, a nadal z okresu transakcji opłaty zostanie odjętych 10 dni.</span><span class="sxs-lookup"><span data-stu-id="4e6ee-114">Also, if the **From date** on the reduction period is January 21 (31 minus 10), you could set the **To date** to any date after January 31, and 10 days will still be removed from the fee transaction period.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e6ee-115">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4e6ee-115">See also</span></span>

[<span data-ttu-id="4e6ee-116">Przykład dni redukcji</span><span class="sxs-lookup"><span data-stu-id="4e6ee-116">Reduction days example</span></span>](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]