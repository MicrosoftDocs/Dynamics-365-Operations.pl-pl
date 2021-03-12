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
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 14a2f4c7d8d053ffd7b4b5d090113e1d9c3294c4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974117"
---
# <a name="carrier-groups"></a><span data-ttu-id="bfa78-103">Grupy przewoźników</span><span class="sxs-lookup"><span data-stu-id="bfa78-103">Carrier groups</span></span>

<span data-ttu-id="bfa78-104">Grupa przewoźnika to zbiór przewoźników i usług przewozowych.</span><span class="sxs-lookup"><span data-stu-id="bfa78-104">A carrier group is a collection of shipping carriers and carrier services.</span></span> <span data-ttu-id="bfa78-105">Każda grupa przewoźnika określa preferowaną sekwencję dla przewoźników i usług przewozowych należących do niej.</span><span class="sxs-lookup"><span data-stu-id="bfa78-105">Each carrier group specifies the preferred sequence for the shipping carriers and carrier services that belong to it.</span></span>

<span data-ttu-id="bfa78-106">Jeśli istnieje wiele przewoźników i usług przewozowych dla tego samego segmentu marszruty, można określić grupę przewoźników zamiast konkretnego przewoźnika i usługi firmy przewozowej w planie marszruty lub w przewodniku marszruty.</span><span class="sxs-lookup"><span data-stu-id="bfa78-106">When multiple shipping carriers and carrier services exist for the same route segment, you can specify a carrier group instead of a specific shipping carrier and carrier service in the route plan or route guide.</span></span>

## <a name="create-a-carrier-group"></a><span data-ttu-id="bfa78-107">Tworzenie grupy przewoźników</span><span class="sxs-lookup"><span data-stu-id="bfa78-107">Create a carrier group</span></span>

1. <span data-ttu-id="bfa78-108">Przejdź do pozycji **Zarządzanie transportem &gt; Ustawienia &gt; Przewoźnicy &gt; Firmy przewozowe**.</span><span class="sxs-lookup"><span data-stu-id="bfa78-108">Go to **Transportation management &gt; Setup &gt; Carriers &gt; Carrier group**.</span></span>
1. <span data-ttu-id="bfa78-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bfa78-109">Select **New**.</span></span>
1. <span data-ttu-id="bfa78-110">W polu **Grupa przewoźników** wprowadź unikatowy identyfikator dla grupy.</span><span class="sxs-lookup"><span data-stu-id="bfa78-110">In the **Carrier group** field, enter a unique identifier (ID) for the group.</span></span>
1. <span data-ttu-id="bfa78-111">W polu **Nazwa** wprowadź opisową nazwę grupy.</span><span class="sxs-lookup"><span data-stu-id="bfa78-111">In the **Name** field, enter a descriptive name for the group.</span></span>
1. <span data-ttu-id="bfa78-112">Na **skróconej karcie Szczegóły** dodaj wiersz, a następnie wybierz firmę przewozową i usługę przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="bfa78-112">On the **Details** FastTab, add a row, and select a shipping carrier and a carrier service for it.</span></span> <span data-ttu-id="bfa78-113">Powtarzaj ten krok, dopóki nie dodasz tylu przewoźników, ile jest potrzebnych dla grupy.</span><span class="sxs-lookup"><span data-stu-id="bfa78-113">Repeat this step until you've added as many carriers as you require for the group.</span></span>
1. <span data-ttu-id="bfa78-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bfa78-114">Close the page.</span></span>
