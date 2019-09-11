---
title: Środki trwałe i zlecenia pracy
description: W tym temacie opisano zlecenia pracy i środki trwałe w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f03b7fa073c4e5338b7b5681ba7b8c9fe00a657b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875834"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="b7d0c-103">Środki trwałe i zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="b7d0c-103">Work orders and fixed assets</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="b7d0c-104">W module Zarządzanie składnikami majątku, składniki majątku mogą być powiązane ze środkami trwałymi oraz można tworzyć zlecenia pracy dla tych składników.</span><span class="sxs-lookup"><span data-stu-id="b7d0c-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="b7d0c-105">W przypadku korzystania z tej funkcji można zapoznać się z ogólnym przeglądem środków trwałych, powiązanych projektów inwestycyjnych oraz kosztami zarejestrowanymi w projektach inwestycyjnych w module **Zarządzanie projektami i ich księgowanie** oraz w module **Środki trwałe** w Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b7d0c-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs registered on the investment projects in the **Project management and accounting** module and the **Fixed assets** module in Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="b7d0c-106">Pole **Numer środka trwałego** jest wypełniane tylko w projekcie zadania zlecenia pracy, jeśli w projekcie zadania zlecenia pracy jako typ projektu wybrano typ „inwestycja”.</span><span class="sxs-lookup"><span data-stu-id="b7d0c-106">The **Fixed asset number** field is only filled out on the work order job project if type "Investment" is selected as the project type on the work order job project.</span></span>

![Rysunek 1](media/24-work-orders.png)

<span data-ttu-id="b7d0c-108">Poniższa procedura opisuje relację między składnikami majątku, zleceniami pracy, projektami zadań zlecenia pracy i środkami trwałymi.</span><span class="sxs-lookup"><span data-stu-id="b7d0c-108">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="b7d0c-109">Tworzony jest składnik majątku powiązany z środkiem trwałym, co pokazano na poniższym rysunku.</span><span class="sxs-lookup"><span data-stu-id="b7d0c-109">You create an asset that you relate to a fixed asset, as shown in the figure below.</span></span>

![Rysunek 2](media/25-work-orders.png)

2. <span data-ttu-id="b7d0c-111">Podczas konfigurowania typów zleceń pracy (**Zarządzanie składnikami majątku** > **Konfiguracja** > **Zlecenia pracy** > **Typy zleceń pracy**) tworzony jest typ zlecenia pracy służący do obsługi inwestycji.</span><span class="sxs-lookup"><span data-stu-id="b7d0c-111">When you set up work order types (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="b7d0c-112">Zobacz również [Typy zleceń pracy](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="b7d0c-112">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Rysunek 3](media/26-work-orders.png)

3. <span data-ttu-id="b7d0c-114">Podczas konfigurowania grup projektów zleceń pracy (łącze **Zarządzanie składnikami majątku** > **Konfiguracja** > **Zlecenia pracy** > **Ustawienia projektu** > **Grupa projektów**), tworzy relację między typem zlecenia pracy używanym w inwestycjach a grupą projektów utworzoną dla inwestycji w module **Zarządzanie projektami i ich księgowanie** (**Zarządzanie projektami i ich księgowanie** > **Konfiguracja** > **Księgowanie** > **Grupy projektów**).</span><span class="sxs-lookup"><span data-stu-id="b7d0c-114">When you set up work order project groups (**Asset management** > **Setup** > **Work orders** > **Project setup** > **Project group** link), you create a relation between the work order type used for investments and the project group created for investments in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Rysunek 4](media/27-work-orders.png)

4. <span data-ttu-id="b7d0c-116">Podczas tworzenia zlecenia pracy związanego z obiektem środka trwałego należy wybrać typ zlecenia pracy używanego do obsługi inwestycji, na przykład „inwestycja”.</span><span class="sxs-lookup"><span data-stu-id="b7d0c-116">When you create a work order that relates to a fixed asset object, you select the work order type used for handling investments, for example, "Investment".</span></span>

5. <span data-ttu-id="b7d0c-117">Po utworzeniu zlecenia pracy typ powiązanego zlecenia jest pokazywany we **Wszystkie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="b7d0c-117">When the work order is created, the related work order type is shown in **All work orders**.</span></span>

![Rysunek 5](media/28-work-orders.png)

6. <span data-ttu-id="b7d0c-119">Po utworzeniu zlecenia pracy projekt powiązany ze zleceniem pracy jest tworzony w **Zarządzanie projektami i ich księgowanie** > **Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="b7d0c-119">When the work order is created, the project related to the work order is created in **Project management and accounting** > **All projects**.</span></span> <span data-ttu-id="b7d0c-120">Informacje związane z projektem można wyświetlić, klikając łącze **Identyfikator projektu** w zleceniu pracy (w obszarze **Zarządzanie składnikami majątku** otwórz okno zlecenie pracy w Widok szczegółów > skrócona karta **Szczegóły wiersza** > karta  **Ogólne** > pole **Identyfikator projektu**).</span><span class="sxs-lookup"><span data-stu-id="b7d0c-120">You can see project-related information by clicking the **Project ID** link on the work order (in **Asset management**, open the work order in Details view > **Line details** FastTab > **General** tab > **Project ID** field).</span></span>

![Rysunek 6](media/29-work-orders.png)

7. <span data-ttu-id="b7d0c-122">W module **Środki trwałe** można wyświetlić przegląd projektów związanych z środkiem trwałym (**Środki trwałe** > **Środki trwałe** > **Środki trwałe** > kliknij na środek trwały w polu **Numer środka trwałego** > zobacz zawartość okienka **Informacje pokrewne** > sekcja **Skojarzone projekty**).</span><span class="sxs-lookup"><span data-stu-id="b7d0c-122">In **Fixed assets**, you are able to see an overview of the projects associated with a fixed asset (**Fixed assets** > **Fixed assets** > **Fixed assets** > click on the fixed asset in the **Fixed asset number** field > view the contents in the **Related information** pane > **Associated projects** section).</span></span>

