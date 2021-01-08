---
title: Grupy przewoźników
description: W tym temacie opisano sposób konfigurowania danych dla grup przewoźników.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2570479edac9bc8cc7aa998a8b69f54ffc10cd61
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646426"
---
# <a name="carrier-groups"></a><span data-ttu-id="82bcf-103">Grupy przewoźników</span><span class="sxs-lookup"><span data-stu-id="82bcf-103">Carrier groups</span></span>

<span data-ttu-id="82bcf-104">Grupa przewoźnika to zbiór przewoźników i usług przewozowych.</span><span class="sxs-lookup"><span data-stu-id="82bcf-104">A carrier group is a collection of shipping carriers and carrier services.</span></span> <span data-ttu-id="82bcf-105">Każda grupa przewoźnika określa preferowaną sekwencję dla przewoźników i usług przewozowych należących do niej.</span><span class="sxs-lookup"><span data-stu-id="82bcf-105">Each carrier group specifies the preferred sequence for the shipping carriers and carrier services that belong to it.</span></span>

<span data-ttu-id="82bcf-106">Jeśli istnieje wiele przewoźników i usług przewozowych dla tego samego segmentu marszruty, można określić grupę przewoźników zamiast konkretnego przewoźnika i usługi firmy przewozowej w planie marszruty lub w przewodniku marszruty.</span><span class="sxs-lookup"><span data-stu-id="82bcf-106">When multiple shipping carriers and carrier services exist for the same route segment, you can specify a carrier group instead of a specific shipping carrier and carrier service in the route plan or route guide.</span></span>

## <a name="create-a-carrier-group"></a><span data-ttu-id="82bcf-107">Tworzenie grupy przewoźników</span><span class="sxs-lookup"><span data-stu-id="82bcf-107">Create a carrier group</span></span>

1. <span data-ttu-id="82bcf-108">Przejdź do pozycji **Zarządzanie transportem &gt; Ustawienia &gt; Przewoźnicy &gt; Firmy przewozowe**.</span><span class="sxs-lookup"><span data-stu-id="82bcf-108">Go to **Transportation management &gt; Setup &gt; Carriers &gt; Carrier group**.</span></span>
1. <span data-ttu-id="82bcf-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="82bcf-109">Select **New**.</span></span>
1. <span data-ttu-id="82bcf-110">W polu **Grupa przewoźników** wprowadź unikatowy identyfikator dla grupy.</span><span class="sxs-lookup"><span data-stu-id="82bcf-110">In the **Carrier group** field, enter a unique identifier (ID) for the group.</span></span>
1. <span data-ttu-id="82bcf-111">W polu **Nazwa** wprowadź opisową nazwę grupy.</span><span class="sxs-lookup"><span data-stu-id="82bcf-111">In the **Name** field, enter a descriptive name for the group.</span></span>
1. <span data-ttu-id="82bcf-112">Na **skróconej karcie Szczegóły** dodaj wiersz, a następnie wybierz firmę przewozową i usługę przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="82bcf-112">On the **Details** FastTab, add a row, and select a shipping carrier and a carrier service for it.</span></span> <span data-ttu-id="82bcf-113">Powtarzaj ten krok, dopóki nie dodasz tylu przewoźników, ile jest potrzebnych dla grupy.</span><span class="sxs-lookup"><span data-stu-id="82bcf-113">Repeat this step until you've added as many carriers as you require for the group.</span></span>
1. <span data-ttu-id="82bcf-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="82bcf-114">Close the page.</span></span>
