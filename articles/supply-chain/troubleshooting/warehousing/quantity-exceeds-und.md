---
title: Nie można potwierdzić wysyłki, ponieważ ilość przekracza wartość procentową niedoboru w dostawie
description: Nie można potwierdzić wysyłki, ponieważ ilość przekracza wartość procentową niedoboru w dostawie
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm,WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 625003731485329b93f5f9454ccece580c889613
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123826"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a><span data-ttu-id="421cf-103">Nie można potwierdzić wysyłki, ponieważ ilość przekracza wartość procentową niedoboru w dostawie</span><span class="sxs-lookup"><span data-stu-id="421cf-103">You can't confirm a shipment because the quantity exceeds the underdelivery percentage</span></span>

<span data-ttu-id="421cf-104">Kod błędu: WAX1686</span><span class="sxs-lookup"><span data-stu-id="421cf-104">Error code: WAX1686</span></span>

## <a name="symptoms"></a><span data-ttu-id="421cf-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="421cf-105">Symptoms</span></span>

<span data-ttu-id="421cf-106">Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="421cf-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="421cf-107">Nie można potwierdzić wysyłki ładunku %1, ponieważ ilość pozycji %2 przekracza procent określony dla niedoboru w dostawie.</span><span class="sxs-lookup"><span data-stu-id="421cf-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for underdelivery.</span></span>

<span data-ttu-id="421cf-108">W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="421cf-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="421cf-109">Powód</span><span class="sxs-lookup"><span data-stu-id="421cf-109">Cause</span></span>

<span data-ttu-id="421cf-110">Ilość ładunku lub wysyłki została tylko częściowo pobrana.</span><span class="sxs-lookup"><span data-stu-id="421cf-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="421cf-111">Ilość jest obecnie mniejsza od ilości pobranej o procent, który jest poza dozwolonym procentem niedoboru w dostawie.</span><span class="sxs-lookup"><span data-stu-id="421cf-111">The quantity is currently less than the picked quantity by a percentage that is outside the allowed underdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="421cf-112">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="421cf-112">Resolution</span></span>

<span data-ttu-id="421cf-113">Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="421cf-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="421cf-114">Ustaw ilość w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="421cf-114">Set the load line quantity.</span></span>
- <span data-ttu-id="421cf-115">Ustaw wartość procentową niedoboru w dostawie.</span><span class="sxs-lookup"><span data-stu-id="421cf-115">Set the underdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="421cf-116">Ustawianie ilości w wierszu ładunku</span><span class="sxs-lookup"><span data-stu-id="421cf-116">Set the load line quantity</span></span>

<span data-ttu-id="421cf-117">Aby ustawić ilość w wierszu ładunku, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="421cf-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="421cf-118">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="421cf-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="421cf-119">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="421cf-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="421cf-120">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent niedoboru w dostawie.</span><span class="sxs-lookup"><span data-stu-id="421cf-120">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="421cf-121">Na skróconej karcie **Szczegóły wiersza** wybierz **Zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="421cf-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="421cf-122">W polu **Ilość** ustaw wartość na pobraną ilość (to jest wartość **Ilość stworzonych prac**), aby mogło dojść do potwierdzenia wysyłki.</span><span class="sxs-lookup"><span data-stu-id="421cf-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-underdelivery-percentage"></a><span data-ttu-id="421cf-123">Ustawianie wartości procentowej niedoboru w dostawie</span><span class="sxs-lookup"><span data-stu-id="421cf-123">Set the underdelivery percentage</span></span>

<span data-ttu-id="421cf-124">Aby ustawić wartość procentową niedoboru w dostawie, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="421cf-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="421cf-125">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="421cf-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="421cf-126">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="421cf-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="421cf-127">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent niedoboru w dostawie.</span><span class="sxs-lookup"><span data-stu-id="421cf-127">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="421cf-128">Na skróconej karcie **Szczegóły wiersza** wybierz **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="421cf-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="421cf-129">W polu **Niedobór w dostawie** ustaw większą wartość procentową, która mieści się w ilości pobrania w stosunku do ilości ładunku, aby było można potwierdzić wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="421cf-129">In the **Underdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>
