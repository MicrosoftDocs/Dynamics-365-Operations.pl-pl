---
title: Tworzenie profilu lokalizacji
description: W tym temacie opisano sposób tworzenia profilu lokalizacji w Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46aa1001c21ae39c158062444303ca02c0f41a45
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2019
ms.locfileid: "1866986"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="e2f0a-103">Tworzenie profilu lokalizacji</span><span class="sxs-lookup"><span data-stu-id="e2f0a-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e2f0a-104">W tym temacie opisano sposób tworzenia profilu lokalizacji w Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-104">This topic explains how to create a location profile in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="e2f0a-105">Z każdą lokalizacją w magazynie musi być skojarzony profil lokalizacji opisujący jej właściwości, na przykład czy lokalizacji pozwala na mieszane towary.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-105">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="e2f0a-106">W tej procedurze utworzymy profil dla lokalizacji, która nie wymaga kontroli na podstawie numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-106">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="e2f0a-107">Włączymy obsługę mieszanych towarów i mieszanych stanów zapasów oraz pozwolimy na inwentaryzację ciągłą.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-107">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="e2f0a-108">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-108">You can use this procedure in the USMF demo data company.</span></span>


1. <span data-ttu-id="e2f0a-109">W okienku nawigacji przejdź do **Moduły > Zarządzanie magazynem > Ustawienia > Magazyn > Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-109">In the navigation pane, go to **Modules > Warehouse management > Setup > Warehouse > Location profiles**.</span></span>
2. <span data-ttu-id="e2f0a-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-110">Select **New**.</span></span>
3. <span data-ttu-id="e2f0a-111">W polu **Identyfikator profilu lokalizacji** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-111">In the **Location profile ID** field, type a value.</span></span>
4. <span data-ttu-id="e2f0a-112">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-112">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="e2f0a-113">W polu **Format lokalizacji** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-113">In the **Location format** field, enter or select a value.</span></span>
6. <span data-ttu-id="e2f0a-114">W polu **Typ lokalizacji** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-114">In the **Location type** field, enter or select a value.</span></span>
7. <span data-ttu-id="e2f0a-115">W polu **Identyfikator profilu zarządzania na rampie** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-115">In the **Dock management profile ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="e2f0a-116">W polu **Pozwól na mieszane pozycje** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-116">Select **Yes** in the **Allow mixed items** field.</span></span>
9. <span data-ttu-id="e2f0a-117">w polu **Pozwól na mieszane stany zapasów** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-117">Select **Yes** in the **Allow mixed inventory statuses** field.</span></span>
10. <span data-ttu-id="e2f0a-118">W polu **Pozwól na inwentaryzację ciągłą** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-118">Select **Yes** in the **Allow cycle counting** field.</span></span>
11. <span data-ttu-id="e2f0a-119">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e2f0a-119">Select **Save**.</span></span>

