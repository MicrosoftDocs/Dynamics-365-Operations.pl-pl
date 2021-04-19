---
title: Tworzenie zleceń pracy z żądań konserwacji
description: W tym temacie wyjaśniono, jak utworzyć zlecenie pracy z żądania konserwacji w zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c360985509f8f1379ed4a9bd17b95f2d8c85340e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808599"
---
# <a name="create-work-orders-from-maintenance-requests"></a><span data-ttu-id="dc580-103">Tworzenie zleceń pracy z żądań konserwacji</span><span class="sxs-lookup"><span data-stu-id="dc580-103">Create work orders from maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="dc580-104">Po utworzeniu żądań konserwacji można łatwo przekonwertować je na zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="dc580-104">After you've created maintenance requests, you can easily convert them to work orders.</span></span> <span data-ttu-id="dc580-105">W tym temacie opisano najszybszy sposób pracy z żądaniami konserwacji, aktualizowania kilku żądań konserwacji w tym samym czasie oraz tworzenia zleceń pracy dla kilku żądań konserwacji w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="dc580-105">This topic describes the quickest way to work with maintenance requests, update several maintenance requests at the same time, and then create a work order for several maintenance requests at the same time.</span></span> <span data-ttu-id="dc580-106">Na stronie **Aktywne żądania konserwacji** lub **Żądania konserwacji mojej lokalizacji czynności konserwacyjnych** można również pracować z jednym żądaniem konserwacji jednocześnie i przekonwertować jedno żądanie konserwacji na zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="dc580-106">On the **Active maintenance requests** or **My functional location maintenance requests** page, you can also work with one maintenance request at a time and convert one maintenance request to a work order.</span></span>

> [!NOTE]
> <span data-ttu-id="dc580-107">Każde żądanie konserwacji może być związane tylko z jednym zleceniem pracy.</span><span class="sxs-lookup"><span data-stu-id="dc580-107">Every maintenance request can be related to only one work order.</span></span> <span data-ttu-id="dc580-108">Wiele żądań konserwacji można jednak umieścić na jednym zleceniu pracy, nawet jeśli żądania konserwacji mają różne składniki majątku.</span><span class="sxs-lookup"><span data-stu-id="dc580-108">However, multiple maintenance requests can be included in one work order, even if the maintenance requests have different assets.</span></span>

1. <span data-ttu-id="dc580-109">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **żądania konserwacji** \> **Wszystkie żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="dc580-109">Select **Asset management** \> **Common** \> **maintenance requests** \> **All maintenance requests**.</span></span>
2. <span data-ttu-id="dc580-110">Aby można było tworzyć zlecenie pracy z żądań konserwacji, należy wybrać co najmniej typ zadania konserwacji dla żądań konserwacji, a także wariant i rodzaj typu zadania konserwacji, jeśli te informacje są istotne.</span><span class="sxs-lookup"><span data-stu-id="dc580-110">Before you can create a work order from maintenance requests, you must select, at a minimum, a maintenance job type for the maintenance requests, and also a maintenance job type variant and trade, if this information is relevant.</span></span> <span data-ttu-id="dc580-111">W widoku siatki można łatwo aktualizować informacje dotyczące żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="dc580-111">In the grid view, you can easily update information for a maintenance request.</span></span>
3. <span data-ttu-id="dc580-112">Gdy wszystko będzie gotowe do utworzenia zlecenia pracy, wybierz żądania konserwacji do uwzględnienia w nim.</span><span class="sxs-lookup"><span data-stu-id="dc580-112">When you're ready to create a work order, select the maintenance requests to include in it.</span></span>

    - <span data-ttu-id="dc580-113">Jeśli wybierzesz kilka żądań konserwacji do przekonwertowania na zlecenie pracy, zarówno pole **Składnik majątku** i pole **Typ zadania konserwacji** muszą być ustawione przed utworzeniem zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="dc580-113">If you select several maintenance requests to convert to a work order, both the **Asset** field and the **Maintenance job type** field must be set before you create the work order.</span></span>
    - <span data-ttu-id="dc580-114">Jeśli wybierzesz jedno żądanie konserwacji do przekonwertowania na zlecenie pracy, przed utworzeniem zlecenia pracy należy ustawić tylko pole **Składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="dc580-114">If you select one maintenance request to convert to a work order, only the **Asset** field must be set before you create the work order.</span></span> <span data-ttu-id="dc580-115">Jednak podczas tworzenia zlecenia pracy, można wybrać typ zadania konserwacji (i związane z typem zadania konserwacji wariant i rodzaj, jeśli te informacje są istotne) w oknie dialogowym **Tworzenie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="dc580-115">However, when you create the work order, you can select a maintenance job type (and a related maintenance job type variant and trade, if this information is relevant) in the **Create work order** dialog box.</span></span>

4. <span data-ttu-id="dc580-116">Wybierz **Zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="dc580-116">Select **Work order**.</span></span>
5. <span data-ttu-id="dc580-117">W oknie dialogowym **Tworzenie zlecenia pracy** ustaw pola, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc580-117">In the **Create work order** dialog box, set the fields, and then select **OK**.</span></span>

    <span data-ttu-id="dc580-118">Pasek komunikatów może powiadomić, że utworzono nowe zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="dc580-118">A message bar might notify you that a new work order has been created.</span></span>

    <span data-ttu-id="dc580-119">Ponadto podczas tworzenia zlecenia pracy opartego na żądaniu konserwacji, jeśli składnik majątku, który jest powiązany z żądaniem konserwacji znajduje się w umowie gwarancyjnej, pasek komunikatów powiadamia użytkownika o umowie gwarancyjnej.</span><span class="sxs-lookup"><span data-stu-id="dc580-119">Additionally, when you create a work order that is based on a maintenance request, if the asset that is related to the maintenance request is included in a warranty agreement, a message bar notifies you about the warranty agreement.</span></span>

6. <span data-ttu-id="dc580-120">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Zlecenia pracy** \> **Wszystkie zlecenia pracy** i otwórz nowe zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="dc580-120">Select **Asset management** \> **Common** \> **Work orders** \> **All work orders**, and open the new work order.</span></span>

    ![Otwieranie nowego zlecenia pracy](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]