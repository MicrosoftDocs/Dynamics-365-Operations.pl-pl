---
title: Synchronizacja zdolności produkcyjnych zasobu
description: Ten temat zawiera informacje o sposobach synchronizowania zdolności produkcyjnych zasobu w kalendarzach i projektach.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760632"
---
# <a name="synchronize-resource-capacity"></a><span data-ttu-id="8dc5c-103">Synchronizacja zdolności produkcyjnych zasobu</span><span class="sxs-lookup"><span data-stu-id="8dc5c-103">Synchronize resource capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8dc5c-104">Procesy synchronizacji zasobów pomagają zagwarantować, że informacje dotyczące kalendarza i kalendarza podstawowego są przekazywane do czynności planowania zasobów projektu.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-104">The processes for resource synchronization help guarantee that information for the calendar and base calendar trickles down into project resource scheduling.</span></span> <span data-ttu-id="8dc5c-105">Jeśli kalendarz zostanie zmieniony, procesy dokonują wymaganych aktualizacji harmonogramów zasobów projektu.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-105">If the calendar is changed, the processes make the required updates to the scheduling of project resources.</span></span> <span data-ttu-id="8dc5c-106">Procesy pomagają także zwiększyć wydajność, ponieważ informacje o zasobie kalendarza są synchronizowane z wyprzedzeniem.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-106">The processes also help improve performance, because the calendar's resource information is synchronized in advance.</span></span> <span data-ttu-id="8dc5c-107">Dlatego aktualizacje informacji o planowaniu zasobów są dokonywane szybciej.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-107">Therefore, updates to resource scheduling information occur more quickly.</span></span> <span data-ttu-id="8dc5c-108">Zaleca się planowanie procesów jako zadanie wsadowe, a nie jednostkowe.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-108">We recommend that you schedule the processes as a batch instead of one at a time.</span></span> <span data-ttu-id="8dc5c-109">W przeciwnym razie istnieje ryzyko, że ktoś może zapomnieć włącznych dat ostatniej synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-109">Otherwise, there is a risk that someone will forget the inclusive dates when the information was last synchronized.</span></span> <span data-ttu-id="8dc5c-110">Jeśli nie są używane daty włączne, mogą występować przerwy podczas synchronizacji dat.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-110">If inclusive dates aren't used, gaps can occur during date synchronization.</span></span>

![Synchronizacja kalendarza](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a><span data-ttu-id="8dc5c-112">Synchronizuj zestawienia zdolności produkcyjnych zasobów</span><span class="sxs-lookup"><span data-stu-id="8dc5c-112">Synchronize resource capacity roll-ups</span></span>

<span data-ttu-id="8dc5c-113">Proces synchronizacji jest zaprojektowany do synchronizowania wszystkich informacji w kalendarzu zasobów.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-113">The synchronization process is designed to synchronize all resource calendar information.</span></span> <span data-ttu-id="8dc5c-114">Informacje te obejmują dane kalendarza podstawowego o wszelkich zmianach w tabeli zdolności produkcyjnych kalendarza zasobów projektu.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-114">This information includes base calendar information about any changes to the project's Resource calendar capacity table.</span></span> <span data-ttu-id="8dc5c-115">Jeśli w projekcie są dodawane nowe zasoby, synchronizacja pomaga zagwarantować dostępność zaktualizowanych informacji kalendarza.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-115">If new resources are added in the project, synchronization helps guarantee that the updated calendar information is available.</span></span> <span data-ttu-id="8dc5c-116">Tę synchronizację można wykonać w dowolnym czasie.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-116">This synchronization can be done at any time.</span></span>

<span data-ttu-id="8dc5c-117">Zaleca się używanie procesu wsadowego.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-117">We recommend that you use a batch.</span></span> <span data-ttu-id="8dc5c-118">Odpowiednie opcje są dostępne podczas synchronizowania rezerwacji zdolności produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-118">The options are available during synchronization of capacity reservations.</span></span>

1. <span data-ttu-id="8dc5c-119">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Okresowe** &gt; **Synchronizacja zdolności produkcyjnych** &gt; **Synchronizuj zestawienia zdolności produkcyjnych zasobów**.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-119">Select **Project management and accounting** &gt; **Periodic** &gt; **Capacity synchronization** &gt; **Synchronize resources capacity roll-ups**.</span></span>
2. <span data-ttu-id="8dc5c-120">Ustaw opcje w następującej tabeli.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-120">Set the options in the following table.</span></span>

    | <span data-ttu-id="8dc5c-121">Opcja</span><span class="sxs-lookup"><span data-stu-id="8dc5c-121">Option</span></span>      | <span data-ttu-id="8dc5c-122">opis</span><span class="sxs-lookup"><span data-stu-id="8dc5c-122">Description</span></span> |
    |-------------|-------------|
    | <span data-ttu-id="8dc5c-123">Kod okresu</span><span class="sxs-lookup"><span data-stu-id="8dc5c-123">Period code</span></span> | <span data-ttu-id="8dc5c-124">Opcjonalnie wybierz kod interwału daty księgi głównej w celu ustawienia daty rozpoczęcia i zakończenia procesu synchronizacji zestawień zdolności produkcyjnych zasobów.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-124">Optionally select the General ledger date interval code to set the start and end dates for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="8dc5c-125">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="8dc5c-125">Start date</span></span>  | <span data-ttu-id="8dc5c-126">Wprowadź datę rozpoczęcia procesu synchronizacji zestawienia zdolności produkcyjnych zasobów.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-126">Enter the start date for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="8dc5c-127">Data zakończenia</span><span class="sxs-lookup"><span data-stu-id="8dc5c-127">End date</span></span>    | <span data-ttu-id="8dc5c-128">Wprowadź datę zakończenia procesu synchronizacji zestawienia zdolności produkcyjnych zasobów.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-128">Enter the end date for the synchronization process for resource capacity roll-ups.</span></span> |

<span data-ttu-id="8dc5c-129">[![Proces synchronizacji](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span><span class="sxs-lookup"><span data-stu-id="8dc5c-129">[![Synchronization process](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span></span>
