---
title: Grupy kredytowe odbiorcy
description: Ten temat zawiera informacje dotyczące przepływu pracy grup kredytowych odbiorców.
author: mikefalkner
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3cdf4f7e72a55292c64b7a9191974242aab85a90
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835323"
---
# <a name="customer-credit-groups"></a><span data-ttu-id="33eb2-103">Grupy kredytowe odbiorcy</span><span class="sxs-lookup"><span data-stu-id="33eb2-103">Customer credit groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33eb2-104">Można zdefiniować grupy odbiorców, którzy mają wspólny limit kredytu.</span><span class="sxs-lookup"><span data-stu-id="33eb2-104">You can define groups of customers who have a shared credit limit.</span></span> <span data-ttu-id="33eb2-105">Uwzględniany jest również indywidualny limit kredytu zdefiniowany na koncie płatnika faktury dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="33eb2-105">The individual credit limit that is defined on the customer invoice account is also considered.</span></span>

<span data-ttu-id="33eb2-106">Członkowie grupy kredytowej odbiorcy mogą być wybierani z różnych firm.</span><span class="sxs-lookup"><span data-stu-id="33eb2-106">Members of a customer credit group can be selected from different legal entities.</span></span> <span data-ttu-id="33eb2-107">Po dodaniu odbiorcy do listy odbiorców w grupie kredytowej odbiorcy, data ważności limitu kredytowego dla każdego odbiorcy jest zmieniana na datę wygaśnięcia przypisaną do grupy.</span><span class="sxs-lookup"><span data-stu-id="33eb2-107">When you add a customer to the list of customers in the customer credit group, the expiration date of the credit limit for each customer is changed to the expiration date that is assigned to the group.</span></span>

<span data-ttu-id="33eb2-108">Grupy kredytowe odbiorcy można skonfigurować na stronie **Grupy kredytowe odbiorcy** (**Zarządzanie kredytem \> Grupy kredytowe odbiorcy \> Grupy kredytowe odbiorcy**).</span><span class="sxs-lookup"><span data-stu-id="33eb2-108">You can set up customer credit groups on the **Customer credit groups** page (**Credit management \> Customer credit groups \> Customer credit groups**).</span></span>

1. <span data-ttu-id="33eb2-109">W polach **numer grupy** i **opis** wprowadź identyfikator i opis grupy.</span><span class="sxs-lookup"><span data-stu-id="33eb2-109">In the **Group number** and **Description** fields, enter an identifier and description for the group.</span></span>
2. <span data-ttu-id="33eb2-110">W polach **limit kredytu** i **waluta** wprowadź limit kredytu i walutę, który ma być używany, gdy system sprawdza limit kredytu każdego członka grupy.</span><span class="sxs-lookup"><span data-stu-id="33eb2-110">In the **Credit limit** and **Currency** fields, enter the credit limit and currency that should be used when the system checks the credit limit for any member of the group.</span></span>
3. <span data-ttu-id="33eb2-111">W polu **limit kredytu na dzień** wprowadź datę wygaśnięcia limitu kredytowego.</span><span class="sxs-lookup"><span data-stu-id="33eb2-111">In the **Credit limit to date** field, enter the date when the credit limit expires.</span></span> <span data-ttu-id="33eb2-112">Grupy kredytowe odbiorcy muszą mieć datę ważności.</span><span class="sxs-lookup"><span data-stu-id="33eb2-112">Customer credit groups must have an expiration date.</span></span>

<span data-ttu-id="33eb2-113">Po zakończeniu konfigurowania grupy kredytu odbiorcy można dodawać do niej odbiorców, określając ich firmę i identyfikator konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="33eb2-113">After you've finished setting up a customer credit group, you can add customers to it by specifying their legal entity and customer account ID.</span></span> <span data-ttu-id="33eb2-114">Podczas dodawania nowego odbiorcy do grupy kredytowej odbiorcy system wyszukuje to samo konto odbiorcy we wszystkich firmach i monituje o dodanie go do grupy kredytowej odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="33eb2-114">When you add a new customer to a customer credit group, the system searches for the same customer account across all legal entities and prompts you to add it to the customer credit group.</span></span>

<span data-ttu-id="33eb2-115">Aby wyświetlić szczegóły dotyczące salda wiekowania dla wszystkich odbiorców faktury w grupie kredytowej odbiorcy, należy skorzystać z menu **Wiekowane salda**.</span><span class="sxs-lookup"><span data-stu-id="33eb2-115">Use the **Aged balances** menu to view the details of the aging balance for all invoice customers in a customer credit group.</span></span> <span data-ttu-id="33eb2-116">Na stronie **Wiekowane salda** jest wyświetlane podsumowanie zawiekowania sald na kontach odbiorców faktury.</span><span class="sxs-lookup"><span data-stu-id="33eb2-116">The **Aging balance** page shows a summary of the aged balances for the invoice customer accounts.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]