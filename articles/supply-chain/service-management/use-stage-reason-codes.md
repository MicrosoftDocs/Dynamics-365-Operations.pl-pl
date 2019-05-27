---
title: Użycie kodów przyczyn etapów
description: Kod przyczyny służy do wskazania powodu, dla którego umowa dotycząca poziomu usług została anulowana lub powodu przekroczenia terminu zamówienia usług określonego w takiej umowie.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33fa7e5f08f09fe109d0507d686315d01e043928
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557763"
---
# <a name="use-stage-reason-codes"></a><span data-ttu-id="070a6-103">Użycie kodów przyczyn etapów</span><span class="sxs-lookup"><span data-stu-id="070a6-103">Use stage reason codes</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="070a6-104">Kod przyczyny służy do wskazania powodu, dla którego umowa dotycząca poziomu usług została anulowana lub powodu przekroczenia terminu zamówienia usług określonego w takiej umowie.</span><span class="sxs-lookup"><span data-stu-id="070a6-104">You use a reason code to indicate why a service level agreement (SLA) has been canceled, or why a service order has exceeded the time limit that is you define in the SLA.</span></span>

<span data-ttu-id="070a6-105">Można również określić, że kod przyczyny jest wymagany, po anulowaniu umowy SLA lub gdy przekroczy limit czasu, który jest określony w SLA dla zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="070a6-105">You can also specify that a reason code is required when an SLA is canceled, or when the time limit exceeds the time that is specified in the SLA for the service order.</span></span>

<span data-ttu-id="070a6-106">Jeśli określono, że kod przyczyny jest wymagany, należy wprowadzić kod przyczyny w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="070a6-106">If you have specified that a reason code is required, you must enter a reason code in the following situations:</span></span>

  - <span data-ttu-id="070a6-107">gdy zlecenie serwisowe przechodzi w stan, w którym następuje zatrzymanie rejestrowania czasu w ramach umowy dotyczącej poziomu usług dla tego zlecenia;</span><span class="sxs-lookup"><span data-stu-id="070a6-107">When a service order is moved to a stage that stops time recording against the SLA for the service order.</span></span>

  - <span data-ttu-id="070a6-108">gdy zlecenie serwisowe zostanie wycofane;</span><span class="sxs-lookup"><span data-stu-id="070a6-108">When the service order is signed off.</span></span>

  - <span data-ttu-id="070a6-109">gdy rejestrowanie czasu zostanie zatrzymane ręcznie.</span><span class="sxs-lookup"><span data-stu-id="070a6-109">When time recording is manually stopped.</span></span>

## <a name="set-up-reason-codes"></a><span data-ttu-id="070a6-110">Ustaw kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="070a6-110">Set up reason codes</span></span>

1.  <span data-ttu-id="070a6-111">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Zlecenia serwisowe** \> **Kody przyczyn etapów**.</span><span class="sxs-lookup"><span data-stu-id="070a6-111">Click **Service management** \> **Setup** \> **Service orders** \> **Stage reason codes**.</span></span>

2.  <span data-ttu-id="070a6-112">W formularzu **Kody przyczyn etapów** kliknij przycisk **Nowy**, aby utworzyć nowy kod przyczyny.</span><span class="sxs-lookup"><span data-stu-id="070a6-112">In the **Stage reason codes** form, click **New** to create a new reason code.</span></span>

3.  <span data-ttu-id="070a6-113">W polu **Kod przyczyny etapów** wprowadź unikatowy kod przyczyny etapu.</span><span class="sxs-lookup"><span data-stu-id="070a6-113">In the **Stage reason code** field, enter a unique stage reason code.</span></span>

4.  <span data-ttu-id="070a6-114">W polu **Opis** wprowadź opis kodu przyczyny etapu.</span><span class="sxs-lookup"><span data-stu-id="070a6-114">In the **Description** field, enter a description of the stage reason code.</span></span>

5.  <span data-ttu-id="070a6-115">Zamknij formularz, aby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="070a6-115">Close the form to save your changes.</span></span>

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a><span data-ttu-id="070a6-116">Wymóg podawania kodu przyczyny w wypadku anulowania umowy dotyczącej poziomu usług</span><span class="sxs-lookup"><span data-stu-id="070a6-116">Require reason codes when a service level agreement is canceled</span></span>

1.  <span data-ttu-id="070a6-117">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Parametry modułu Zarządzanie serwisem**.</span><span class="sxs-lookup"><span data-stu-id="070a6-117">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="070a6-118">W formularzu **Parametry modułu Zarządzanie serwisem** kliknij łącze **Ogólne**, a następnie zaznacz pole wyboru **Kod przyczyny dotyczący anulowania**.</span><span class="sxs-lookup"><span data-stu-id="070a6-118">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on canceling** check box.</span></span>

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a><span data-ttu-id="070a6-119">Wymóg podawania kodu przyczyny w wypadku przekroczenia terminu zamówienia usług określonego w umowie dotyczącej poziomu usług</span><span class="sxs-lookup"><span data-stu-id="070a6-119">Require reason codes when the a service order exceeds the time limit that is set by the service level agreement</span></span>

1.  <span data-ttu-id="070a6-120">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Parametry modułu Zarządzanie serwisem**.</span><span class="sxs-lookup"><span data-stu-id="070a6-120">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="070a6-121">W formularzu **Parametry modułu Zarządzanie serwisem** kliknij łącze **Ogólne**, a następnie zaznacz pole wyboru **Kod przyczyny dotyczący przekroczenia czasu**.</span><span class="sxs-lookup"><span data-stu-id="070a6-121">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on exceeding time** check box.</span></span>

## <a name="see-also"></a><span data-ttu-id="070a6-122">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="070a6-122">See also</span></span>

[<span data-ttu-id="070a6-123">Rozpoczynanie i zatrzymywanie rejestrowania czasu dla zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="070a6-123">Start and stop time recording on a service order</span></span>](start-and-stop-time-recording-on-a-service-order.md)

  


