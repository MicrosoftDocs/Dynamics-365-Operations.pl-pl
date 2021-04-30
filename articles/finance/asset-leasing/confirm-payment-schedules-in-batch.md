---
title: Potwierdzanie harmonogramów płatności wynajmu składnika majątku w partii
description: W tym temacie opisano sposób zatwierdzania wielu harmonogramów płatności w partii.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymConfirmationDetails
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: eaff604b92c412cd35c5c2aeadb2d9ed8dc77706
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881259"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a><span data-ttu-id="b9353-103">Potwierdzanie harmonogramów płatności wynajmu składnika majątku w partii</span><span class="sxs-lookup"><span data-stu-id="b9353-103">Confirm Asset leasing payment schedules in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9353-104">W tym temacie opisano sposób zatwierdzania wielu harmonogramów płatności w partii.</span><span class="sxs-lookup"><span data-stu-id="b9353-104">This topic explains how to confirm multiple payment schedules in a batch.</span></span> <span data-ttu-id="b9353-105">Harmonogramy płatności są potwierdzane na zasadzie od wynajmu do wynajmu lub w procesie wsadowym potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="b9353-105">Payment schedules are confirmed either on a lease-to-lease basis or through the confirmation batch process.</span></span> <span data-ttu-id="b9353-106">Wpis w arkuszu może być księgowany tylko w odniesieniu do wynajmu o potwierdzonym harmonogramie płatności.</span><span class="sxs-lookup"><span data-stu-id="b9353-106">A journal entry can be posted only against a lease that has a confirmed payment schedule.</span></span> <span data-ttu-id="b9353-107">Potwierdzenie harmonogramu płatności służy jako ostateczne zatwierdzenie informacji finansowych dotyczących wynajmu.</span><span class="sxs-lookup"><span data-stu-id="b9353-107">Confirmation of the payment schedule serves as a final approval of the financial information for the lease.</span></span> <span data-ttu-id="b9353-108">Wszystkie przyszłe zmiany informacji finansowych dotyczących wynajmu, takie jak płatności i okres wynajmu, stanowią korektę wynajmu i powinny być przetwarzane w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="b9353-108">All future changes to the financial information for the lease, such as payments and the lease term, constitute a lease adjustment and should be processed in that way.</span></span>

<span data-ttu-id="b9353-109">Aby potwierdzić wiele harmonogramów płatności, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b9353-109">To confirm multiple payment schedules, follow these steps.</span></span>

1. <span data-ttu-id="b9353-110">Przejdź do **Wynajem składnika majątku \> Okresowe \> Potwierdzenie w partii**.</span><span class="sxs-lookup"><span data-stu-id="b9353-110">Go to **Asset leasing \> Periodic \> Confirmation batch**.</span></span>
2. <span data-ttu-id="b9353-111">Na stronie **Potwierdzenie w partii** wybierz pozycję **Potwierdzenie w partii**.</span><span class="sxs-lookup"><span data-stu-id="b9353-111">On the **Confirmation batch** page, select **Confirmation batch**.</span></span>
3. <span data-ttu-id="b9353-112">W wyświetlonym oknie dialogowym odfiltruj księgi, które chcesz potwierdzić.</span><span class="sxs-lookup"><span data-stu-id="b9353-112">In the dialog box that appears, filter for the books that you want to confirm.</span></span>

    - <span data-ttu-id="b9353-113">Aby potwierdzić wszystkie księgi z danej grupy wynajmu, zaznacz tę grupę w polu **Grupa wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="b9353-113">To confirm all the books in a specific lease group, select the group in the **Lease group** field.</span></span>
    - <span data-ttu-id="b9353-114">Aby potwierdzić określone księgi, wybierz księgi w polu **Identyfikator księgi**.</span><span class="sxs-lookup"><span data-stu-id="b9353-114">To confirm specific books, select the books in the **Book ID** field.</span></span>
    - <span data-ttu-id="b9353-115">Aby potwierdzić wszystkie księgi, włącz parametr **Dla wszystkich ksiąg**.</span><span class="sxs-lookup"><span data-stu-id="b9353-115">To confirm all books, turn on the **For all books** parameter.</span></span>

<span data-ttu-id="b9353-116">Informacje dotyczące nowo potwierdzonych ksiąg są wyświetlane na stronie **Potwierdzone księgi**.</span><span class="sxs-lookup"><span data-stu-id="b9353-116">Information for the newly confirmed books is shown on the **Confirmed books** page.</span></span> <span data-ttu-id="b9353-117">Po potwierdzeniu harmonogramów płatności początkowe wpisy w arkuszu rozpoznawania mogą być księgowane za wynajmy.</span><span class="sxs-lookup"><span data-stu-id="b9353-117">After the payment schedules are confirmed, the initial recognition journal entries can be posted against the leases.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
