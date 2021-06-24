---
title: Nie można potwierdzić wysyłki z powodu niekompletnej lub brakującej pracy
description: Nie można potwierdzić wysyłki z powodu niekompletnej lub brakującej pracy
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123850"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a><span data-ttu-id="8238a-103">Nie można potwierdzić wysyłki z powodu niekompletnej lub brakującej pracy</span><span class="sxs-lookup"><span data-stu-id="8238a-103">You can't confirm a shipment because of incomplete or missing work</span></span>

<span data-ttu-id="8238a-104">Kod błędu: WAX515</span><span class="sxs-lookup"><span data-stu-id="8238a-104">Error code: WAX515</span></span>

## <a name="symptoms"></a><span data-ttu-id="8238a-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="8238a-105">Symptoms</span></span>

<span data-ttu-id="8238a-106">Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="8238a-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="8238a-107">Nie można potwierdzić wysyłki ładunku %1, ponieważ cała praca dla ładunku musi zostać zakończona.</span><span class="sxs-lookup"><span data-stu-id="8238a-107">The shipment for load %1 could not be confirmed because all work for the load must be complete.</span></span>

<span data-ttu-id="8238a-108">W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="8238a-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="8238a-109">Powód</span><span class="sxs-lookup"><span data-stu-id="8238a-109">Cause</span></span>

<span data-ttu-id="8238a-110">Ładunek lub wysyłka jest obecnie w stanie, w którym potwierdzenie wysyłki nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="8238a-110">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="8238a-111">Aby można było potwierdzić wysyłkę, dla ładunku musi istnieć co najmniej jedna praca, a wszystkie prace muszą mieć stan *Zamknięte* lub *Anulowane*.</span><span class="sxs-lookup"><span data-stu-id="8238a-111">Before you can confirm the shipment, at least some work must exist for the load, and all that work must have a status of *Closed* or *Canceled*.</span></span>

## <a name="resolution"></a><span data-ttu-id="8238a-112">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="8238a-112">Resolution</span></span>

<span data-ttu-id="8238a-113">Sprawdź powiązane zamówienia sprzedaży lub zamówienia przeniesienia dla ładunku lub wysyłki i upewnij się, że cała powiązana praca została zakończona lub anulowana.</span><span class="sxs-lookup"><span data-stu-id="8238a-113">Check the related sales orders or transfer orders for the load or shipment, and make sure that all the related work has been completed or canceled.</span></span>

<span data-ttu-id="8238a-114">Praca z wysyłkami i ładunkami jest możliwa na różnych stronach.</span><span class="sxs-lookup"><span data-stu-id="8238a-114">You can work with shipments and loads on several pages.</span></span> <span data-ttu-id="8238a-115">Poniższe podsekcji zawierają kilka przykładów.</span><span class="sxs-lookup"><span data-stu-id="8238a-115">The following subsections provide a few examples.</span></span>

### <a name="all-loads-page"></a><span data-ttu-id="8238a-116">Strona Wszystkie ładunki</span><span class="sxs-lookup"><span data-stu-id="8238a-116">All loads page</span></span>

1. <span data-ttu-id="8238a-117">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="8238a-117">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="8238a-118">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="8238a-118">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="8238a-119">W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.</span><span class="sxs-lookup"><span data-stu-id="8238a-119">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="8238a-120">Sprawdź stan każdego identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="8238a-120">Inspect the status of each work ID.</span></span> <span data-ttu-id="8238a-121">Skontroluj każdy identyfikator pracy, który nie ma stanu *Zamknięty* ani *Anulowany*.</span><span class="sxs-lookup"><span data-stu-id="8238a-121">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="8238a-122">Jeśli każdy identyfikator pracy ma stan *Zamknięty* lub *Anulowany*, spróbuj ponownie potwierdzić wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="8238a-122">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-shipments-page"></a><span data-ttu-id="8238a-123">Strona Wszystkie wysyłki</span><span class="sxs-lookup"><span data-stu-id="8238a-123">All shipments page</span></span>

1. <span data-ttu-id="8238a-124">Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="8238a-124">Go to **Warehouse management \> Shipments\> All shipments**.</span></span>
1. <span data-ttu-id="8238a-125">Wybierz wysyłkę, która nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="8238a-125">Select the shipment that can't be confirmed.</span></span>
1. <span data-ttu-id="8238a-126">W okienku akcji, na karcie **Wysyłki**, w grupie **Praca** wybierz pozycję **Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="8238a-126">On the Action Pane, on the **Shipments** tab, in the **Work** group, select **Work details**.</span></span>
1. <span data-ttu-id="8238a-127">Sprawdź stan każdego identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="8238a-127">Inspect the status of each work ID.</span></span> <span data-ttu-id="8238a-128">Skontroluj każdy identyfikator pracy, który nie ma stanu *Zamknięty* ani *Anulowany*.</span><span class="sxs-lookup"><span data-stu-id="8238a-128">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="8238a-129">Jeśli każdy identyfikator pracy ma stan *Zamknięty* lub *Anulowany*, spróbuj ponownie potwierdzić wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="8238a-129">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-work-page"></a><span data-ttu-id="8238a-130">Strona Wszystkie prace</span><span class="sxs-lookup"><span data-stu-id="8238a-130">All work page</span></span>

1. <span data-ttu-id="8238a-131">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca\> Wszystkie prace**.</span><span class="sxs-lookup"><span data-stu-id="8238a-131">Go to **Warehouse management \> Work\> All work**.</span></span>
1. <span data-ttu-id="8238a-132">Wybierz pracę dla numeru zamówienia, dla którego nie można potwierdzić wysyłki.</span><span class="sxs-lookup"><span data-stu-id="8238a-132">Select the work for the order number that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="8238a-133">W okienku akcji na karcie **Wysyłka** w grupie **Wysyłka** kliknij opcję **Potwierdź wysyłkę**.</span><span class="sxs-lookup"><span data-stu-id="8238a-133">On the Action Pane, on the **Shipment** tab, in the **Shipment** group, select **Confirm shipment**.</span></span>
1. <span data-ttu-id="8238a-134">Sprawdź stan każdego identyfikatora pracy.</span><span class="sxs-lookup"><span data-stu-id="8238a-134">Inspect the status of each work ID.</span></span> <span data-ttu-id="8238a-135">Skontroluj każdy identyfikator pracy, który nie ma stanu *Zamknięty* ani *Anulowany*.</span><span class="sxs-lookup"><span data-stu-id="8238a-135">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="8238a-136">Jeśli każdy identyfikator pracy ma stan *Zamknięty* lub *Anulowany*, spróbuj ponownie potwierdzić wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="8238a-136">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>
