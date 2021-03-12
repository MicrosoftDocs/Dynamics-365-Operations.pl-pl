---
title: Potwierdzanie harmonogramów płatności wynajmu składnika majątku w partii
description: W tym temacie opisano sposób zatwierdzania wielu harmonogramów płatności w partii.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9c680ea16e9f64107fde081c7e7763697356dcc1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971385"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a><span data-ttu-id="77475-103">Potwierdzanie harmonogramów płatności wynajmu składnika majątku w partii</span><span class="sxs-lookup"><span data-stu-id="77475-103">Confirm Asset leasing payment schedules in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="77475-104">W tym temacie opisano sposób zatwierdzania wielu harmonogramów płatności w partii.</span><span class="sxs-lookup"><span data-stu-id="77475-104">This topic explains how to confirm multiple payment schedules in a batch.</span></span> <span data-ttu-id="77475-105">Harmonogramy płatności są potwierdzane na zasadzie od wynajmu do wynajmu lub w procesie wsadowym potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="77475-105">Payment schedules are confirmed either on a lease-to-lease basis or through the confirmation batch process.</span></span> <span data-ttu-id="77475-106">Wpis w arkuszu może być księgowany tylko w odniesieniu do wynajmu o potwierdzonym harmonogramie płatności.</span><span class="sxs-lookup"><span data-stu-id="77475-106">A journal entry can be posted only against a lease that has a confirmed payment schedule.</span></span> <span data-ttu-id="77475-107">Potwierdzenie harmonogramu płatności służy jako ostateczne zatwierdzenie informacji finansowych dotyczących wynajmu.</span><span class="sxs-lookup"><span data-stu-id="77475-107">Confirmation of the payment schedule serves as a final approval of the financial information for the lease.</span></span> <span data-ttu-id="77475-108">Wszystkie przyszłe zmiany informacji finansowych dotyczących wynajmu, takie jak płatności i okres wynajmu, stanowią korektę wynajmu i powinny być przetwarzane w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="77475-108">All future changes to the financial information for the lease, such as payments and the lease term, constitute a lease adjustment and should be processed in that way.</span></span>

<span data-ttu-id="77475-109">Aby potwierdzić wiele harmonogramów płatności, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="77475-109">To confirm multiple payment schedules, follow these steps.</span></span>

1. <span data-ttu-id="77475-110">Przejdź do **Wynajem składnika majątku \> Okresowe \> Potwierdzenie w partii**.</span><span class="sxs-lookup"><span data-stu-id="77475-110">Go to **Asset leasing \> Periodic \> Confirmation batch**.</span></span>
2. <span data-ttu-id="77475-111">Na stronie **Potwierdzenie w partii** wybierz pozycję **Potwierdzenie w partii**.</span><span class="sxs-lookup"><span data-stu-id="77475-111">On the **Confirmation batch** page, select **Confirmation batch**.</span></span>
3. <span data-ttu-id="77475-112">W wyświetlonym oknie dialogowym odfiltruj księgi, które chcesz potwierdzić.</span><span class="sxs-lookup"><span data-stu-id="77475-112">In the dialog box that appears, filter for the books that you want to confirm.</span></span>

    - <span data-ttu-id="77475-113">Aby potwierdzić wszystkie księgi z danej grupy wynajmu, zaznacz tę grupę w polu **Grupa wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="77475-113">To confirm all the books in a specific lease group, select the group in the **Lease group** field.</span></span>
    - <span data-ttu-id="77475-114">Aby potwierdzić określone księgi, wybierz księgi w polu **Identyfikator księgi**.</span><span class="sxs-lookup"><span data-stu-id="77475-114">To confirm specific books, select the books in the **Book ID** field.</span></span>
    - <span data-ttu-id="77475-115">Aby potwierdzić wszystkie księgi, włącz parametr **Dla wszystkich ksiąg**.</span><span class="sxs-lookup"><span data-stu-id="77475-115">To confirm all books, turn on the **For all books** parameter.</span></span>

<span data-ttu-id="77475-116">Informacje dotyczące nowo potwierdzonych ksiąg są wyświetlane na stronie **Potwierdzone księgi**.</span><span class="sxs-lookup"><span data-stu-id="77475-116">Information for the newly confirmed books is shown on the **Confirmed books** page.</span></span> <span data-ttu-id="77475-117">Po potwierdzeniu harmonogramów płatności początkowe wpisy w arkuszu rozpoznawania mogą być księgowane za wynajmy.</span><span class="sxs-lookup"><span data-stu-id="77475-117">After the payment schedules are confirmed, the initial recognition journal entries can be posted against the leases.</span></span>
