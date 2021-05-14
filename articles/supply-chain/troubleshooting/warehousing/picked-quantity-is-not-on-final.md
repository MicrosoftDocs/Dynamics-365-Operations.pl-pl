---
title: Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary
description: Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938532"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="86142-103">Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary</span><span class="sxs-lookup"><span data-stu-id="86142-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="86142-104">Kod błędu: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="86142-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="86142-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="86142-105">Symptoms</span></span>

<span data-ttu-id="86142-106">Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="86142-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="86142-107">Niektóre towary wymagane w ładunku %1 nie zostały jeszcze pobrane i przeniesione do końcowej lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="86142-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="86142-108">W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="86142-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="86142-109">Powód</span><span class="sxs-lookup"><span data-stu-id="86142-109">Cause</span></span>

<span data-ttu-id="86142-110">Nie można potwierdzić ładunku lub wysyłki w jego bieżącym stanie, ponieważ może istnieć jeden z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="86142-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="86142-111">Powiązana praca nie została jeszcze pobrana i przeniesiona do końcowej lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="86142-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="86142-112">Ilość pobrania pracy nie odpowiada utworzonej ilości pracy w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="86142-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>

## <a name="resolution"></a><span data-ttu-id="86142-113">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="86142-113">Resolution</span></span>

<span data-ttu-id="86142-114">Sprawdź powiązane zamówienia sprzedaży lub zamówienia przeniesienia dla ładunku lub wysyłki.</span><span class="sxs-lookup"><span data-stu-id="86142-114">Check the related sales orders or transfer orders for the load or shipment.</span></span> <span data-ttu-id="86142-115">Upewnij się, że wszystkie powiązane prace zostały zakończone w końcowej lokalizacji wysyłki i czy ilości są zgodne.</span><span class="sxs-lookup"><span data-stu-id="86142-115">Make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="86142-116">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="86142-116">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="86142-117">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="86142-117">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="86142-118">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.</span><span class="sxs-lookup"><span data-stu-id="86142-118">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="86142-119">Zanotuj wartość pola **Ilość stworzonych prac**.</span><span class="sxs-lookup"><span data-stu-id="86142-119">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="86142-120">W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.</span><span class="sxs-lookup"><span data-stu-id="86142-120">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="86142-121">Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="86142-121">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="86142-122">Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.</span><span class="sxs-lookup"><span data-stu-id="86142-122">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>
