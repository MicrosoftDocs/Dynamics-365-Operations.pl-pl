---
title: Poziom i opis usługi
description: W tym temacie wyjaśniono poziomy usług i opisy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 647358fcdd53ba95b571185ae269bc8d6b869c18
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889392"
---
# <a name="service-level-and-description"></a><span data-ttu-id="3a488-103">Poziom i opis usługi</span><span class="sxs-lookup"><span data-stu-id="3a488-103">Service level and description</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="3a488-104">Podczas tworzenia zlecenia pracy można określić dla niego poziomy usług i dodać do niego ogólny opis.</span><span class="sxs-lookup"><span data-stu-id="3a488-104">When you create a work order, you might want to define the service levels for it and add a general description to it.</span></span> <span data-ttu-id="3a488-105">Poziomy usługi zlecenia pracy można utworzyć na stronie **Poziomy usługi zlecenia pracy** i opisy na stronie **Opis zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="3a488-105">You can create work order service levels on the **Work order service levels** page and descriptions on the **Work order description** page.</span></span>

## <a name="create-a-service-level"></a><span data-ttu-id="3a488-106">Tworzenie poziomu serwisu</span><span class="sxs-lookup"><span data-stu-id="3a488-106">Create a service level</span></span>

1. <span data-ttu-id="3a488-107">Wybierz **Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Poziom usług**.</span><span class="sxs-lookup"><span data-stu-id="3a488-107">Select **Asset management** \> **Setup** \> **Work orders** \> **Service level**.</span></span>
2. <span data-ttu-id="3a488-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="3a488-108">Select **New**.</span></span>
3. <span data-ttu-id="3a488-109">W polu **Poziom usług** wprowadź poziom usług (na przykład numer).</span><span class="sxs-lookup"><span data-stu-id="3a488-109">In the **Service level** field, enter the service level (for example, a number).</span></span>
4. <span data-ttu-id="3a488-110">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="3a488-110">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="3a488-111">W skróconej karcie **zlecenia pracy** można zdefiniować oczekiwane daty rozpoczęcia i zakończenia oraz godziny.</span><span class="sxs-lookup"><span data-stu-id="3a488-111">On the **Work orders** FastTab, you can define expected start and end dates and times.</span></span> <span data-ttu-id="3a488-112">Pola na skróconej karcie definiują okres, w którym zlecenia pracy powinny zostać rozpoczęte i zakończone.</span><span class="sxs-lookup"><span data-stu-id="3a488-112">The fields on this FastTab define the period that work orders should be started and ended during.</span></span> <span data-ttu-id="3a488-113">Są one używane dla ręcznie tworzonych zleceń pracy i zleceń roboczych tworzonych na podstawie zgłoszeń obsługi.</span><span class="sxs-lookup"><span data-stu-id="3a488-113">They are used for work orders that are manually created and work orders that are created based on maintenance requests.</span></span> 

5. <span data-ttu-id="3a488-114">W polu **Dzień rozpoczęcia** wprowadź liczbę dni określającą okres, w którym ma się rozpocząć zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="3a488-114">In the **Start day** field, enter a number of days to define the period that the work order should start during.</span></span> <span data-ttu-id="3a488-115">Liczba dni jest obliczana na podstawie daty utworzenia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="3a488-115">The number of days is calculated from the creation date of the work order.</span></span> <span data-ttu-id="3a488-116">Jeśli na przykład zlecenie pracy powinno zostać rozpoczęte po jego utworzeniu, należy wprowadzić **wartość**0.</span><span class="sxs-lookup"><span data-stu-id="3a488-116">For example, if the work order should start when it's created, enter **0**.</span></span> <span data-ttu-id="3a488-117">Jeśli na przykład zlecenie pracy powinno zostać rozpoczęte w ciągu tygodnia po jego utworzeniu, należy wprowadzić **7**.</span><span class="sxs-lookup"><span data-stu-id="3a488-117">If the work order should start within one week after it's created, enter **7**.</span></span>
6. <span data-ttu-id="3a488-118">Aby określić godzinę rozpoczęcia zlecenia pracy oprócz daty początkowej, należy w polu **Ustaw godzinę rozpoczęcia** wybrać opcję **tak**.</span><span class="sxs-lookup"><span data-stu-id="3a488-118">To set a start time for the work order, in addition to a start date, set the **Set start time** option to **Yes**.</span></span> <span data-ttu-id="3a488-119">Następnie wprowadź godzinę rozpoczęcia w polu **Godzina rozpoczęcia**.</span><span class="sxs-lookup"><span data-stu-id="3a488-119">Then enter the start time in the **Start time** field.</span></span> <span data-ttu-id="3a488-120">Ustawienie opcji na wartość **nie** spowoduje, że zostanie użyta bieżąca godzina dnia.</span><span class="sxs-lookup"><span data-stu-id="3a488-120">If you set the option to **No**, the current time of day is used.</span></span>
7. <span data-ttu-id="3a488-121">W polu **Dzień zakończenia** wprowadź liczbę dni określającą okres, w którym ma się zakończyć zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="3a488-121">In the **End day** field, enter a number of days to define the period that the work order should end during.</span></span> <span data-ttu-id="3a488-122">Liczba dni jest obliczana na podstawie daty rozpoczęcia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="3a488-122">The number of days is calculated from the start date of the work order.</span></span> <span data-ttu-id="3a488-123">Jeśli na przykład zlecenie pracy powinno zakończyć się w ciągu jednego tygodnia od daty rozpoczęcia, należy wprowadzić **7**.</span><span class="sxs-lookup"><span data-stu-id="3a488-123">For example, if the work order should end within one week of its start date, enter **7**.</span></span>
8. <span data-ttu-id="3a488-124">Aby określić godzinę zakończenia zlecenia pracy oprócz daty zakończenia, należy w polu **Ustaw godzinę zakończenia** wybrać opcję **tak**.</span><span class="sxs-lookup"><span data-stu-id="3a488-124">To set an end time for the work order, in addition to an end date, set the **Set end time** option to **Yes**.</span></span> <span data-ttu-id="3a488-125">Następnie wprowadź godzinę zakończenia w polu **Godzina zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="3a488-125">Then enter the end time in the **End time** field.</span></span> <span data-ttu-id="3a488-126">Ustawienie opcji na wartość **nie** spowoduje, że zostanie użyta bieżąca godzina dnia.</span><span class="sxs-lookup"><span data-stu-id="3a488-126">If you set the option to **No**, the current time of day is used.</span></span>
9. <span data-ttu-id="3a488-127">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="3a488-127">Select **Save**.</span></span>

![Strona Poziom usługi zleceń pracy](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a><span data-ttu-id="3a488-129">Stwórz opis</span><span class="sxs-lookup"><span data-stu-id="3a488-129">Create a description</span></span>

1. <span data-ttu-id="3a488-130">Wybierz **Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Opisy**.</span><span class="sxs-lookup"><span data-stu-id="3a488-130">Select **Asset management** \> **Setup** \> **Work orders** \> **Descriptions**.</span></span>
2. <span data-ttu-id="3a488-131">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="3a488-131">Select **New**.</span></span>
3. <span data-ttu-id="3a488-132">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="3a488-132">In the **Description** field, enter the description.</span></span>
4. <span data-ttu-id="3a488-133">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="3a488-133">Select **Save**.</span></span>
