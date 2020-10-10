---
title: Rozwiązywanie problemów z przepływami pracy związanymi z zaopatrzeniem i sourcingiem
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zaopatrzeniem i sourcingiem.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 940a6c39ac83e7388d4e1a08b656b75df81ed801
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834408"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a><span data-ttu-id="3a5d5-103">Rozwiązywanie problemów z przepływami pracy związanymi z zaopatrzeniem i sourcingiem</span><span class="sxs-lookup"><span data-stu-id="3a5d5-103">Troubleshoot procurement and sourcing workflows</span></span>

<span data-ttu-id="3a5d5-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zaopatrzeniem i sourcingiem.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-104">This topic describes how to fix issues that you might encounter while you work with procurement and sourcing workflows.</span></span>

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a><span data-ttu-id="3a5d5-105">Błąd podczas ponownego przesyłania zamówienia zakupu do przepływu pracy po zmianie: „Zmiany w zamówieniu X są dozwolone tylko w stanie Wersja robocza, gdy zarządzanie zmianami jest aktywne”</span><span class="sxs-lookup"><span data-stu-id="3a5d5-105">Error when re-submitting a purchase order to the workflow after a change: "Changes to purchase order X are allowed only in a Draft state when change management is activated"</span></span>

<span data-ttu-id="3a5d5-106">Ten problem występuje tylko wtedy, gdy zamówienie zakupu było w stanie *Potwierdzonym* przed zapisaniem zmian.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-106">This issue occurs only if the purchase order was in a *Confirmed* state before you requested changes.</span></span> <span data-ttu-id="3a5d5-107">Jeśli zażądasz zmian w czasie, gdy zamówienie zakupu znajduje się w stanie *Zatwierdzone*, przepływ pracy może zostać przetworzony pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-107">If you request changes while the purchase order is in an *Approved* state, the workflow can be processed successfully.</span></span>

### <a name="error-description"></a><span data-ttu-id="3a5d5-108">Opis błędu</span><span class="sxs-lookup"><span data-stu-id="3a5d5-108">Error description</span></span>

<span data-ttu-id="3a5d5-109">Następujący błąd występuje w przepływie pracy, gdy zamówienie zakupu zostanie ponownie przesłane po zmianie:</span><span class="sxs-lookup"><span data-stu-id="3a5d5-109">The following error occurs in the workflow when a purchase order is resubmitted after a change:</span></span>

> <span data-ttu-id="3a5d5-110">Zatrzymane (błąd): X++ Wyjątek: zmiany w zamówieniu zakupu 0000569 są dozwolone tylko w stanie wersji roboczej, gdy uaktywnione jest zarządzanie zmianami na</span><span class="sxs-lookup"><span data-stu-id="3a5d5-110">Stopped (error): X++ Exception: Changes to purchase order PO0000569 are only allowed in state Draft when change management is activated at</span></span><br>
<span data-ttu-id="3a5d5-111">SysWorkflowParticipantProvider-resolve</span><span class="sxs-lookup"><span data-stu-id="3a5d5-111">SysWorkflowParticipantProvider-resolve</span></span><br>
<span data-ttu-id="3a5d5-112">SysWorkflowParticipantProvider-resolveParticipants</span><span class="sxs-lookup"><span data-stu-id="3a5d5-112">SysWorkflowParticipantProvider-resolveParticipants</span></span><br>
<span data-ttu-id="3a5d5-113">SysWorkflowServiceProvider-resolveParticipant</span><span class="sxs-lookup"><span data-stu-id="3a5d5-113">SysWorkflowServiceProvider-resolveParticipant</span></span><br>
<span data-ttu-id="3a5d5-114">SysWorkflowQueue-resume</span><span class="sxs-lookup"><span data-stu-id="3a5d5-114">SysWorkflowQueue-resume</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a5d5-115">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="3a5d5-115">Issue resolution</span></span>

<span data-ttu-id="3a5d5-116">Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-116">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="3a5d5-117">Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-117">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="3a5d5-118">Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="3a5d5-118">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

<span data-ttu-id="3a5d5-119">Ten błąd zostanie rozwiązany za pomocą [niniejszego artykułu z bazy wiedzy Microsoft Knowledge Base (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span><span class="sxs-lookup"><span data-stu-id="3a5d5-119">The issue will be fixed through [this Microsoft Knowledge Base (KB) article](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="3a5d5-120">Co najmniej jedna dystrybucja księgowa jest rozproszona lub niepełna.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-120">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

<span data-ttu-id="3a5d5-121">Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-121">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="3a5d5-122">Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-122">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="3a5d5-123">Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="3a5d5-123">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a><span data-ttu-id="3a5d5-124">Jeśli reszta dostawy została anulowana w zamówieniu zakupu, w którym jest włączone zarządzanie zmianami, zamówienie zakupu przechodzi do stanu potwierdzonego.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-124">If a delivery remainder is canceled on a purchase order where change management is turned on, the purchase order goes to a Confirmed state.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a5d5-125">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="3a5d5-125">Issue description</span></span>

<span data-ttu-id="3a5d5-126">W przypadku zamówienia zakupu, które jest związane z zarządzaniem zmianami, jeśli jedyną żądaną zmianą jest anulowanie reszty dostawy w jednym lub kilku wierszach, zamówienie zakupu będzie przechodzić bezpośrednio do stanu *Potwierdzone*, a arkusz nie zostanie utworzony.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-126">For a purchase order that is subject to change management, if the only change that is requested is the cancellation of a delivery remainder on one or more of the lines, the purchase order will go directly to a *Confirmed* state when it's approved, and no journal will be created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a5d5-127">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="3a5d5-127">Issue resolution</span></span>

<span data-ttu-id="3a5d5-128">Anulowanie reszty dostawy nie wpływa na zawartość arkusza potwierdzeń.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-128">Cancellation of a delivery remainder doesn't affect the contents of the confirmation journal.</span></span> <span data-ttu-id="3a5d5-129">Ta funkcja powinna być używana, gdy wiersz został częściowo odebrany, a pozostała jakość powinna zostać anulowana w kroku procesu po potwierdzeniu zamówienia zakupu u dostawcy.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-129">This functionality should be used when the line has been partially received, and the remainder quality should be canceled in the process step after the purchase order has been confirmed with the vendor.</span></span>

<span data-ttu-id="3a5d5-130">Jeśli powinno to znaleźć odzwierciedlenie w potwierdzeniu zamówienia, ilość powinna zostać dostosowana w wierszu zamówienia, tak aby potwierdzenie było wymagane.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-130">If this should be reflected on the purchase order confirmation, the quantity should be adjusted on the purchase order line so that the confirmation will be required.</span></span> <span data-ttu-id="3a5d5-131">Alternatywnie, jeśli nic nie zostało odebrane w wierszu, ilość może zostać usunięta.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-131">Alternatively, if nothing has been received on the line, the quantity can be removed.</span></span> <span data-ttu-id="3a5d5-132">W takim przypadku będzie wymagane ponowne potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-132">In this case, reconfirmation will be required.</span></span>

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a><span data-ttu-id="3a5d5-133">Anulowane zamówienia zakupu są wyświetlane na liście wersji roboczych w obszarze roboczym Przygotowywania zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-133">Canceled purchase orders appear in the draft list in the Purchase order preparation workspace.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a5d5-134">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="3a5d5-134">Issue description</span></span>

<span data-ttu-id="3a5d5-135">Po anulowaniu zamówień zakupu, które były w stanie *Potwierdzone*, anulowane zamówienia zakupu nadal są wyświetlane na liście wersji roboczych zamówień zakupu w obszarze roboczym **Przygotowanie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-135">After you cancel purchase orders that were in a *Confirmed* state, the canceled purchase orders still appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a5d5-136">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="3a5d5-136">Issue resolution</span></span>

<span data-ttu-id="3a5d5-137">Ten problem występuje tylko w przypadku zamówień zakupu, które podlegają zarządzaniu zmianami.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-137">This issue occurs only for purchase orders that are subject to change management.</span></span> <span data-ttu-id="3a5d5-138">Dzieje się tak, ponieważ anulowanie jest uznawane za zmianę, która musi zostać zatwierdzona.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-138">It occurs because the cancellation is considered a change that must be approved.</span></span> <span data-ttu-id="3a5d5-139">Zatwierdzenie może być wykonane automatycznie przez system.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-139">The approval can be done automatically by the system.</span></span> <span data-ttu-id="3a5d5-140">Dlatego procesowi jest przesłanie anulowanego zamówienia zakupu do przepływu pracy zatwierdzania, aby można było przejść do stanu *Zatwierdzone*.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-140">Therefore, the process is to submit the canceled purchase order to the approval workflow so that it can go to an *Approved* state.</span></span> <span data-ttu-id="3a5d5-141">W tym momencie zamówienie zakupu nie będzie już wyświetlane na liście wersji roboczych zamówień zakupu w obszarze roboczym **Przygotowywania zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="3a5d5-141">At that point, the purchase order will no longer appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

