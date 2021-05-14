---
title: Nie można potwierdzić wysyłki z powodu problemu z kalendarzem
description: Nie można potwierdzić wysyłki z powodu problemu z kalendarzem
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
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938534"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a><span data-ttu-id="64a78-103">Nie można potwierdzić wysyłki z powodu problemu z kalendarzem</span><span class="sxs-lookup"><span data-stu-id="64a78-103">You can't confirm a shipment because of an issue with the calendar</span></span>

<span data-ttu-id="64a78-104">Kod błędu: TRX2716</span><span class="sxs-lookup"><span data-stu-id="64a78-104">Error code: TRX2716</span></span>

## <a name="symptoms"></a><span data-ttu-id="64a78-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="64a78-105">Symptoms</span></span>

<span data-ttu-id="64a78-106">Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="64a78-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="64a78-107">Typ kalendarza %1 wymaga, aby termin %2 został zaewidencjonowany i wyewidencjonowany.</span><span class="sxs-lookup"><span data-stu-id="64a78-107">The calendar type %1 requires the appointment %2 to be checked in and out.</span></span>

<span data-ttu-id="64a78-108">W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="64a78-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="64a78-109">Powód</span><span class="sxs-lookup"><span data-stu-id="64a78-109">Cause</span></span>

<span data-ttu-id="64a78-110">Istnieją aktywne terminy dla ładunku.</span><span class="sxs-lookup"><span data-stu-id="64a78-110">Active appointments for the load exist.</span></span> <span data-ttu-id="64a78-111">Na przykład istnieje reguła wymagająca zameldowania kierowcy.</span><span class="sxs-lookup"><span data-stu-id="64a78-111">For example, there is a rule that requires driver check-in.</span></span> <span data-ttu-id="64a78-112">Dlatego ładunek jest obecnie w stanie, w którym potwierdzenie wysyłki nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="64a78-112">Therefore, the load is currently in a state where shipment confirmation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="64a78-113">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="64a78-113">Resolution</span></span>

<span data-ttu-id="64a78-114">Musisz zbadać i rozwiązać wszystkie problemy związane z aktywnymi terminami, które są połączone z ładunkiem.</span><span class="sxs-lookup"><span data-stu-id="64a78-114">You must investigate and fix any issues with the active appointments that are linked to the load.</span></span>

1. <span data-ttu-id="64a78-115">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="64a78-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="64a78-116">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="64a78-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="64a78-117">W Okienku akcji na karcie **Transport** w grupie **Terminy** wybierz **Planowanie terminów**.</span><span class="sxs-lookup"><span data-stu-id="64a78-117">On the Action Pane, on the **Transportation** tab, in the **Appointments** group, select **Appointment scheduling**.</span></span>
1. <span data-ttu-id="64a78-118">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="64a78-118">Follow one of these steps:</span></span>

    - <span data-ttu-id="64a78-119">Upewnij się, że zameldowanie/wymeldowanie kierowcy zostało ukończone dla terminu.</span><span class="sxs-lookup"><span data-stu-id="64a78-119">Make sure that driver check-in/check-out is completed for the appointment.</span></span>
    - <span data-ttu-id="64a78-120">Ukończ lub anuluj termin.</span><span class="sxs-lookup"><span data-stu-id="64a78-120">Complete or cancel the appointment.</span></span>
    - <span data-ttu-id="64a78-121">Wyłącz opcję **Wymagane zameldowanie kierowcy** dla powiązanej reguły terminu.</span><span class="sxs-lookup"><span data-stu-id="64a78-121">Disable the **Driver check-in required** option for the related appointment rule.</span></span>
