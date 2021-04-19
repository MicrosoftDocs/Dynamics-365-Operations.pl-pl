---
title: Zatwierdzanie zamówień planowanych
description: W tym temacie opisano zatwierdzanie zamówień planowanych, które są obsługiwane podczas optymalizacji planowania.
author: ChristianRytt
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 6c215a89403f16336caae5c62cde6df469c4091c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825898"
---
# <a name="approve-planned-orders"></a><span data-ttu-id="3a000-103">Zatwierdzanie zamówień planowanych</span><span class="sxs-lookup"><span data-stu-id="3a000-103">Approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3a000-104">Ten temat zawiera informacje dotyczące aktualizowania stanu zamówień planowanych w optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="3a000-104">This topic provides information about how to update the status of planned orders in Planning Optimization.</span></span>

<span data-ttu-id="3a000-105">Należy zauważyć, że zatwierdzanie zamówień planowanych jest opcjonalnym krokiem w celu utworzenia zaakceptowanego zamówienia na podstawie zamówienia planowanego.</span><span class="sxs-lookup"><span data-stu-id="3a000-105">Note that approval of planned orders is an optional step, on the way to create a firmed order from a planned order.</span></span> <span data-ttu-id="3a000-106">Zaleca się zatwierdzanie zmodyfikowanych zamówień planowanych, w przeciwnym razie zmiany zostaną zignorowane i zastąpione przez następny przebieg planowania.</span><span class="sxs-lookup"><span data-stu-id="3a000-106">It is recommended to approve modified planned orders, otherwise the edits will be ignored and overwritten by the next planning run.</span></span>

![Przepływ zamówienia planowanego](media/approved-planned-orders-1.png)

<span data-ttu-id="3a000-108">**Pole stanu** umożliwia oznakowanie postępu przy użyciu następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="3a000-108">The **Status** field helps you tack your progress using the following values:</span></span>

- <span data-ttu-id="3a000-109">**Nieprzetworzone:** Zamówienia planowane generowane podczas planowania głównego mają stan *Nieprzetworzone*.</span><span class="sxs-lookup"><span data-stu-id="3a000-109">**Unprocessed:** When master planning generates planned orders, the planned orders have a status of *Unprocessed*.</span></span> <span data-ttu-id="3a000-110">Zamówienia planowane o tym stanie zostaną usunięte podczas następnego uruchomienia planowania.</span><span class="sxs-lookup"><span data-stu-id="3a000-110">Planned orders with this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="3a000-111">**Ukończono:** Jeśli użytkownik zdecyduje się nie akceptować zamówienia planowanego, może zmienić stan na *Zakończone*, aby zaznaczyć, że zakończyła się ocena tego zamówienia planowanego.</span><span class="sxs-lookup"><span data-stu-id="3a000-111">**Completed:** If you decide not to firm a planned order, you can change the status to *Completed* to indicate that you completed evaluating this planned order.</span></span> <span data-ttu-id="3a000-112">Należy zauważyć, że stan *Nieprzetworzone* i *Zakończone* jest traktowany tak samo przez system.</span><span class="sxs-lookup"><span data-stu-id="3a000-112">Note that a status of *Unprocessed* and *Completed* are treated the same by the system.</span></span>
- <span data-ttu-id="3a000-113">**Zatwierdzone:** Jeśli chcesz zachować zmiany lub zaakceptować zamówienie planowane, zmień stan na *Zatwierdzone*.</span><span class="sxs-lookup"><span data-stu-id="3a000-113">**Approved:** If you want to keep edits or are planning to firm a planned order, change the status to *Approved*.</span></span> <span data-ttu-id="3a000-114">Zamówienia planowane ze stanem *Zatwierdzone* są uważane za ustalone w określonej ilości w planowaniu głównym, więc nie można ich modyfikować ani usuwać podczas późniejszego przebiegu planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="3a000-114">Planned orders with *Approved* status are considered as fixed and expected supply by master planning, so they are not modified or deleted during later master planning runs.</span></span> <span data-ttu-id="3a000-115">Aby to osiągnąć, logika planowania kopiuje *zatwierdzone* zamówienia planowane ze starej wersji planu do nowej wersji planu podczas planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="3a000-115">To achieve this, the planning logic copies the *Approved* planned orders from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="3a000-116">Należy zauważyć, że *Zatwierdzone* zamówienia planowane są uznawane za dostawę tylko w ramach określonego planu głównego.</span><span class="sxs-lookup"><span data-stu-id="3a000-116">Note that *Approved* planned orders are only considered supply within the specific master plan.</span></span>

<span data-ttu-id="3a000-117">Można zarządzać planowanymi zamówieniami z obszaru roboczego **Planowanie główne**, listy **Zamówienie planowane** lub list **Planowane zamówienia zakupu**, **Planowane zlecenia produkcyjne** i **Planowane przeniesienie**.</span><span class="sxs-lookup"><span data-stu-id="3a000-117">You can manage planned orders from the  **Master planning**  workspace, the  **Planned order**  list, or the  **Planned production orders**,  **Planned purchase orders**, and  **Planned transfer**  lists.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]