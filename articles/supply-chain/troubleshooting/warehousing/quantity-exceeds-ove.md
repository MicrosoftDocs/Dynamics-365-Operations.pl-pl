---
title: Nie można potwierdzić wysyłki, ponieważ ilość przekracza wartość procentową nadwyżki w dostawie
description: Nie można potwierdzić wysyłki, ponieważ ilość przekracza wartość procentową nadwyżki w dostawie
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
ms.openlocfilehash: c9b5ba8dedb927ee049d7e53e9a666902f563f49
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938535"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-overdelivery-percentage"></a><span data-ttu-id="51078-103">Nie można potwierdzić wysyłki, ponieważ ilość przekracza wartość procentową nadwyżki w dostawie</span><span class="sxs-lookup"><span data-stu-id="51078-103">You can't confirm a shipment because the quantity exceeds the overdelivery percentage</span></span>

<span data-ttu-id="51078-104">Kod błędu: WAX1687</span><span class="sxs-lookup"><span data-stu-id="51078-104">Error code: WAX1687</span></span>

## <a name="symptoms"></a><span data-ttu-id="51078-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="51078-105">Symptoms</span></span>

<span data-ttu-id="51078-106">Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="51078-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="51078-107">Nie można potwierdzić wysyłki ładunku %1, ponieważ ilość pozycji %2 przekracza procent określony dla nadwyżki w dostawie.</span><span class="sxs-lookup"><span data-stu-id="51078-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for overdelivery.</span></span>

<span data-ttu-id="51078-108">W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="51078-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="51078-109">Powód</span><span class="sxs-lookup"><span data-stu-id="51078-109">Cause</span></span>

<span data-ttu-id="51078-110">Ilość ładunku lub wysyłki została tylko częściowo pobrana.</span><span class="sxs-lookup"><span data-stu-id="51078-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="51078-111">Ilość przekracza obecnie ilość pobraną o procent, który jest poza dozwolonym procentem nadwyżki w dostawie.</span><span class="sxs-lookup"><span data-stu-id="51078-111">The quantity currently exceeds the picked quantity by a percentage that is outside the allowed overdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="51078-112">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="51078-112">Resolution</span></span>

<span data-ttu-id="51078-113">Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="51078-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="51078-114">Ustaw ilość w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="51078-114">Set the load line quantity.</span></span>
- <span data-ttu-id="51078-115">Ustaw wartość procentową nadwyżki w dostawie.</span><span class="sxs-lookup"><span data-stu-id="51078-115">Set the overdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="51078-116">Ustawianie ilości w wierszu ładunku</span><span class="sxs-lookup"><span data-stu-id="51078-116">Set the load line quantity</span></span>

<span data-ttu-id="51078-117">Aby ustawić ilość w wierszu ładunku, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="51078-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="51078-118">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="51078-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="51078-119">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="51078-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="51078-120">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent nadwyżki w dostawie.</span><span class="sxs-lookup"><span data-stu-id="51078-120">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="51078-121">Na skróconej karcie **Szczegóły wiersza** wybierz **Zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="51078-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="51078-122">W polu **Ilość** ustaw wartość na pobraną ilość (to jest wartość **Ilość stworzonych prac**), aby mogło dojść do potwierdzenia wysyłki.</span><span class="sxs-lookup"><span data-stu-id="51078-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-overdelivery-percentage"></a><span data-ttu-id="51078-123">Ustawianie wartości procentowej nadwyżki w dostawie</span><span class="sxs-lookup"><span data-stu-id="51078-123">Set the overdelivery percentage</span></span>

<span data-ttu-id="51078-124">Aby ustawić wartość procentową niedoboru w dostawie, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="51078-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="51078-125">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="51078-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="51078-126">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="51078-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="51078-127">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent nadwyżki w dostawie.</span><span class="sxs-lookup"><span data-stu-id="51078-127">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="51078-128">Na skróconej karcie **Szczegóły wiersza** wybierz **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="51078-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="51078-129">W polu **Nadwyżka w dostawie** ustaw większą wartość procentową, która mieści się w ilości pobrania w stosunku do ilości ładunku, aby było można potwierdzić wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="51078-129">In the **Overdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>
