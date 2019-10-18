---
title: Tworzenie zlecenia pracy
description: W tym temacie opisano tworzenie zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0a348bc9b7f5a24c5a3ac57113d430a92020b893
ms.sourcegitcommit: 6476f27c8d3dced7c2e9a7344a4e378b51a1983e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2019
ms.locfileid: "1922121"
---
# <a name="creating-work-orders"></a><span data-ttu-id="94370-103">Tworzenie zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="94370-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="94370-104">W przypadku zaplanowanych zadań konserwacji zapobiegania następnym krokiem jest utworzenie zleceń pracy dla tych zadań.</span><span class="sxs-lookup"><span data-stu-id="94370-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="94370-105">Można to zrobić w jednym z harmonogramów konserwacji:</span><span class="sxs-lookup"><span data-stu-id="94370-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="94370-106">Zaplanowane zadania w harmonogramie konserwacji mogą mieć różne typy odwołań:</span><span class="sxs-lookup"><span data-stu-id="94370-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="94370-107">Typ odwołania</span><span class="sxs-lookup"><span data-stu-id="94370-107">Reference type</span></span> | <span data-ttu-id="94370-108">Opis</span><span class="sxs-lookup"><span data-stu-id="94370-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="94370-109">Plany konserwacji</span><span class="sxs-lookup"><span data-stu-id="94370-109">Maintenance plans</span></span>     | <span data-ttu-id="94370-110">Zadania profilaktycznej konserwacji oparte na planie konserwacji typu „czas” lub „licznik”</span><span class="sxs-lookup"><span data-stu-id="94370-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="94370-111">Serie czynności konserwacyjnych</span><span class="sxs-lookup"><span data-stu-id="94370-111">Maintenance rounds</span></span>    | <span data-ttu-id="94370-112">Zadania profilaktycznej obsługi technicznej zawierające kilka składników majątku, które wymagają podobnego typu obsługi.</span><span class="sxs-lookup"><span data-stu-id="94370-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="94370-113">Żądanie konserwacji</span><span class="sxs-lookup"><span data-stu-id="94370-113">Maintenance request</span></span>   | <span data-ttu-id="94370-114">Ręcznie utworzone żądanie konserwacji lub naprawy składnika majątku, które może zostać przekształcone w zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="94370-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="94370-115">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Wszystkie harmonogramy konserwacji** lub **Otwieranie wierszy harmonogramu konserwacji** lub **Otwieranie puli harmonogramów konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="94370-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="94370-116">Wybierz zaplanowane zadania konserwacyjne, dla których chcesz utworzyć zlecenie prac i kliknij pozycję **Zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="94370-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="94370-117">W okienku dialogowym **Tworzenie zlecenia pracy** łączna liczba godzin prognozowanych dla wybranych wierszy jest wyświetlana w polu **Godziny prognozy konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="94370-117">In the **Create work orders** dialog, the total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="94370-118">W sekcji **Parametry** wybierz liczbę zleceń pracy, które mają zostać utworzone.</span><span class="sxs-lookup"><span data-stu-id="94370-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="94370-119">Istnieje możliwość utworzenia jednego zlecenia pracy dla wiersza harmonogramu konserwacji lub szeregu zleceń pracy na podstawie wybranych opcji w sekcji **Jedno zlecenie pracy na**.</span><span class="sxs-lookup"><span data-stu-id="94370-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="94370-120">Wybierz **Typ zlecenia pracy**, który będzie używany we wszystkich tworzonych zleceniach pracy.</span><span class="sxs-lookup"><span data-stu-id="94370-120">Select a **Work order type** that will be used on all the work orders you create.</span></span> <span data-ttu-id="94370-121">Na poniższej ilustracji przedstawiono przykład okna dialogowego **Tworzenie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="94370-121">The illustration below shows an example of the **Create work orders** dialog.</span></span>

![Rysunek 1](media/18-preventive-maintenance.png)

5. <span data-ttu-id="94370-123">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="94370-123">Click **OK**.</span></span> <span data-ttu-id="94370-124">Utworzono co najmniej jedno zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="94370-124">One or more work orders are created.</span></span>

