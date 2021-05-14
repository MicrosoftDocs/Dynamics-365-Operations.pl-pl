---
title: Nie można potwierdzić wysyłki, ponieważ ilość jest zerowa
description: Nie można potwierdzić wysyłki, ponieważ ilość jest zerowa
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938531"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a><span data-ttu-id="505e5-103">Nie można potwierdzić wysyłki, ponieważ ilość jest zerowa</span><span class="sxs-lookup"><span data-stu-id="505e5-103">You can't confirm a shipment because there is zero quantity</span></span>

<span data-ttu-id="505e5-104">Kod błędu: LoadLineWarningUpdatedToZero</span><span class="sxs-lookup"><span data-stu-id="505e5-104">Error code: LoadLineWarningUpdatedToZero</span></span>

## <a name="symptoms"></a><span data-ttu-id="505e5-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="505e5-105">Symptoms</span></span>

<span data-ttu-id="505e5-106">Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="505e5-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="505e5-107">Wiersz obciążenia pracą dla pozycji %1 i wysyłki %2 został zaktualizowany tak, aby zawierał ilość zerową, z powodu konfiguracji niedoboru w dostawie, która zezwala na rezygnację z wysyłki dowolnych ilości dla tej pozycji.</span><span class="sxs-lookup"><span data-stu-id="505e5-107">Load line for item %1 and shipment %2 has been updated to have zero quantity due to underdelivery setup allowing not to ship any quantities for this item.</span></span>

<span data-ttu-id="505e5-108">W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="505e5-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="505e5-109">Powód</span><span class="sxs-lookup"><span data-stu-id="505e5-109">Cause</span></span>

<span data-ttu-id="505e5-110">System sprawdza, czy ilość pobrana jest w oczekiwanym zakresie na podstawie pobranej ilości, ilości w wierszu ładunku i wartości procentowej niedoboru.</span><span class="sxs-lookup"><span data-stu-id="505e5-110">The system evaluates whether the picked quantity is within the expected limits, based on the picked quantity, load line quantity, and underdelivery percentage.</span></span> <span data-ttu-id="505e5-111">Jeśli system znajdzie w wierszu ładunku ilość pobrania równą 0 (zero), nie będzie można potwierdzić wysyłki.</span><span class="sxs-lookup"><span data-stu-id="505e5-111">If the system finds that the picked quantity on the load line is 0 (zero), you can't confirm the shipment.</span></span> <span data-ttu-id="505e5-112">Ten problem może wystąpić na przykład, jeśli praca została anulowana, a wartość procentowa niedoboru w wierszu ładunku wynosi 100 procent.</span><span class="sxs-lookup"><span data-stu-id="505e5-112">For example, this issue might occur if work has been canceled, and the underdelivery percentage on the load line is 100 percent.</span></span>

## <a name="resolution"></a><span data-ttu-id="505e5-113">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="505e5-113">Resolution</span></span>

<span data-ttu-id="505e5-114">Sprawdź wiersze ładunku, aby mieć pewność, że wartość procentowa niedoboru i ilości są zgodne z pobraną pracą.</span><span class="sxs-lookup"><span data-stu-id="505e5-114">Check your load lines to make sure that the underdelivery percentage and quantities are aligned with the picked work.</span></span>

1. <span data-ttu-id="505e5-115">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="505e5-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="505e5-116">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="505e5-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="505e5-117">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent niedoboru w dostawie.</span><span class="sxs-lookup"><span data-stu-id="505e5-117">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="505e5-118">Zależnie od sytuacji skoryguj wartość pola **Niedobór** lub pola **Ilość**.</span><span class="sxs-lookup"><span data-stu-id="505e5-118">Adjust the value of the **Underdelivery** field or the **Quantity** field as required.</span></span>

> [!TIP]
> <span data-ttu-id="505e5-119">Jeśli problem nadal nie zostanie rozwiązany, może być konieczne zakończenie większej ilości prac pobierania dla powiązanych zamówień sprzedaży lub zamówień przeniesienia, aby dostępna ilość została zrównana z ładunkiem lub wysyłką.</span><span class="sxs-lookup"><span data-stu-id="505e5-119">If the issue still isn't fixed, you might have to complete more picking work for the related sales orders or transfer orders until the available quantity is aligned with the load or shipment.</span></span>
