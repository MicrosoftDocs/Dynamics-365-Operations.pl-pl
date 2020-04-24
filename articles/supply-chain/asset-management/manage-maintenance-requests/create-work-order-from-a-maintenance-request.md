---
title: Tworzenie zleceń pracy z żądań konserwacji
description: W tym temacie wyjaśniono, jak utworzyć zlecenie pracy z żądania konserwacji w zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b6bd98796140ab7aa3e7813ff1526413504554c5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205214"
---
# <a name="create-work-orders-from-maintenance-requests"></a><span data-ttu-id="3f9ec-103">Tworzenie zleceń pracy z żądań konserwacji</span><span class="sxs-lookup"><span data-stu-id="3f9ec-103">Create work orders from maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="3f9ec-104">Po utworzeniu żądań konserwacji można łatwo przekonwertować je na zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-104">After you've created maintenance requests, you can easily convert them to work orders.</span></span> <span data-ttu-id="3f9ec-105">W tym temacie opisano najszybszy sposób pracy z żądaniami konserwacji, aktualizowania kilku żądań konserwacji w tym samym czasie oraz tworzenia zleceń pracy dla kilku żądań konserwacji w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-105">This topic describes the quickest way to work with maintenance requests, update several maintenance requests at the same time, and then create a work order for several maintenance requests at the same time.</span></span> <span data-ttu-id="3f9ec-106">Na stronie **Aktywne żądania konserwacji** lub **Żądania konserwacji mojej lokalizacji czynności konserwacyjnych** można również pracować z jednym żądaniem konserwacji jednocześnie i przekonwertować jedno żądanie konserwacji na zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-106">On the **Active maintenance requests** or **My functional location maintenance requests** page, you can also work with one maintenance request at a time and convert one maintenance request to a work order.</span></span>

> [!NOTE]
> <span data-ttu-id="3f9ec-107">Każde żądanie konserwacji może być związane tylko z jednym zleceniem pracy.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-107">Every maintenance request can be related to only one work order.</span></span> <span data-ttu-id="3f9ec-108">Wiele żądań konserwacji można jednak umieścić na jednym zleceniu pracy, nawet jeśli żądania konserwacji mają różne składniki majątku.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-108">However, multiple maintenance requests can be included in one work order, even if the maintenance requests have different assets.</span></span>

1. <span data-ttu-id="3f9ec-109">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **żądania konserwacji** \> **Wszystkie żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-109">Select **Asset management** \> **Common** \> **maintenance requests** \> **All maintenance requests**.</span></span>
2. <span data-ttu-id="3f9ec-110">Aby można było tworzyć zlecenie pracy z żądań konserwacji, należy wybrać co najmniej typ zadania konserwacji dla żądań konserwacji, a także wariant i rodzaj typu zadania konserwacji, jeśli te informacje są istotne.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-110">Before you can create a work order from maintenance requests, you must select, at a minimum, a maintenance job type for the maintenance requests, and also a maintenance job type variant and trade, if this information is relevant.</span></span> <span data-ttu-id="3f9ec-111">W widoku siatki można łatwo aktualizować informacje dotyczące żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-111">In the grid view, you can easily update information for a maintenance request.</span></span>
3. <span data-ttu-id="3f9ec-112">Gdy wszystko będzie gotowe do utworzenia zlecenia pracy, wybierz żądania konserwacji do uwzględnienia w nim.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-112">When you're ready to create a work order, select the maintenance requests to include in it.</span></span>

    - <span data-ttu-id="3f9ec-113">Jeśli wybierzesz kilka żądań konserwacji do przekonwertowania na zlecenie pracy, zarówno pole **Składnik majątku** i pole **Typ zadania konserwacji** muszą być ustawione przed utworzeniem zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-113">If you select several maintenance requests to convert to a work order, both the **Asset** field and the **Maintenance job type** field must be set before you create the work order.</span></span>
    - <span data-ttu-id="3f9ec-114">Jeśli wybierzesz jedno żądanie konserwacji do przekonwertowania na zlecenie pracy, przed utworzeniem zlecenia pracy należy ustawić tylko pole **Składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-114">If you select one maintenance request to convert to a work order, only the **Asset** field must be set before you create the work order.</span></span> <span data-ttu-id="3f9ec-115">Jednak podczas tworzenia zlecenia pracy, można wybrać typ zadania konserwacji (i związane z typem zadania konserwacji wariant i rodzaj, jeśli te informacje są istotne) w oknie dialogowym **Tworzenie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-115">However, when you create the work order, you can select a maintenance job type (and a related maintenance job type variant and trade, if this information is relevant) in the **Create work order** dialog box.</span></span>

4. <span data-ttu-id="3f9ec-116">Wybierz **Zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-116">Select **Work order**.</span></span>
5. <span data-ttu-id="3f9ec-117">W oknie dialogowym **Tworzenie zlecenia pracy** ustaw pola, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-117">In the **Create work order** dialog box, set the fields, and then select **OK**.</span></span>

    <span data-ttu-id="3f9ec-118">Pasek komunikatów może powiadomić, że utworzono nowe zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-118">A message bar might notify you that a new work order has been created.</span></span>

    <span data-ttu-id="3f9ec-119">Ponadto podczas tworzenia zlecenia pracy opartego na żądaniu konserwacji, jeśli składnik majątku, który jest powiązany z żądaniem konserwacji znajduje się w umowie gwarancyjnej, pasek komunikatów powiadamia użytkownika o umowie gwarancyjnej.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-119">Additionally, when you create a work order that is based on a maintenance request, if the asset that is related to the maintenance request is included in a warranty agreement, a message bar notifies you about the warranty agreement.</span></span>

6. <span data-ttu-id="3f9ec-120">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Zlecenia pracy** \> **Wszystkie zlecenia pracy** i otwórz nowe zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="3f9ec-120">Select **Asset management** \> **Common** \> **Work orders** \> **All work orders**, and open the new work order.</span></span>

    ![Otwieranie nowego zlecenia pracy](media/05-manage-maintenance-requests.png)

