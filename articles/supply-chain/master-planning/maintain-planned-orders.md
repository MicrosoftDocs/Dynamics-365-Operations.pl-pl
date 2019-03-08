---
title: Obsługa zamówień planowanych
description: Ten temat zawiera informacje o metodach zarządzania zamówienia planowanymi. Opisano w nim sposób aktualizowania stanów zamówień planowanych i ich potwierdzania oraz odfiltrowywania zamówień planowanych, które mają taki sam stan jak wybrane zamówienie planowane.
author: roxanadiaconu
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf578d98abc4825c5607ec031da6ab6737c3183a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "360470"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="772a4-104">Obsługa zamówień planowanych</span><span class="sxs-lookup"><span data-stu-id="772a4-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="772a4-105">Ten temat zawiera informacje o metodach zarządzania zamówienia planowanymi.</span><span class="sxs-lookup"><span data-stu-id="772a4-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="772a4-106">Opisano w nim sposób aktualizowania stanów zamówień planowanych i ich potwierdzania oraz odfiltrowywania zamówień planowanych, które mają taki sam stan jak wybrane zamówienie planowane.</span><span class="sxs-lookup"><span data-stu-id="772a4-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="772a4-107">Można zarządzać planowanymi zamówieniami z obszaru roboczego **Planowanie główne**, listy **Zamówienie planowane** lub list **Planowane zamówienia zakupu**, **Planowane zlecenia produkcyjne** i **Planowane przeniesienie**.</span><span class="sxs-lookup"><span data-stu-id="772a4-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="772a4-108">Pole **Stan** pomaga w śledzeniu postępu zamówień.</span><span class="sxs-lookup"><span data-stu-id="772a4-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="772a4-109">Używane są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="772a4-109">The following values are used:</span></span>

-   <span data-ttu-id="772a4-110">Zamówienia planowane generowane podczas planowania głównego mają stan **Nieprzetworzone**.</span><span class="sxs-lookup"><span data-stu-id="772a4-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="772a4-111">Jeżeli nie chcesz ustalać zamówienia planowanego, możesz nadać mu stan **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="772a4-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="772a4-112">Aby ustalić zamówienie planowane, nadaj mu stan **Zatwierdzone**.</span><span class="sxs-lookup"><span data-stu-id="772a4-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="772a4-113">Ten stan oznacza, że użytkownik zatwierdza ustalanie zamówienia planowanego, ale nie jest ono jeszcze ustalone.</span><span class="sxs-lookup"><span data-stu-id="772a4-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="772a4-114">**Uwaga:** zatwierdzone zamówienie planowane jest przesyłane w aktualnym stanie do kolejnego obliczenia planu głównego.</span><span class="sxs-lookup"><span data-stu-id="772a4-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="772a4-115">Aby ustalić zamówienia planowane, należy kolejno kliknąć opcję **Akceptuj**.</span><span class="sxs-lookup"><span data-stu-id="772a4-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="772a4-116">Można ustalić następujące zamówienia planowane:</span><span class="sxs-lookup"><span data-stu-id="772a4-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="772a4-117">Wybrane zamówienie planowane.</span><span class="sxs-lookup"><span data-stu-id="772a4-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="772a4-118">Wiele zamówień planowanych.</span><span class="sxs-lookup"><span data-stu-id="772a4-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="772a4-119">Zamówienia planowane generowane przez rozłożenie ze strony **Rozkładanie**.</span><span class="sxs-lookup"><span data-stu-id="772a4-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="772a4-120">Kliknij opcję **Zamówienia planowane**, wybierz zamówienie planowane, a następnie kliknij opcję **Akceptuj**.</span><span class="sxs-lookup"><span data-stu-id="772a4-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="772a4-121">Po ustaleniu zamówienie planowane zostanie przesunięte do sekcji zamówień w odpowiednim module.</span><span class="sxs-lookup"><span data-stu-id="772a4-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> 

<a name="additional-resources"></a><span data-ttu-id="772a4-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="772a4-122">Additional resources</span></span>
--------

[<span data-ttu-id="772a4-123">Plany główne</span><span class="sxs-lookup"><span data-stu-id="772a4-123">Master plans</span></span>](master-plans.md)



