---
title: Środki trwałe i zlecenia pracy
description: W tym temacie opisano zlecenia pracy i środki trwałe w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4eadbdc452a5b7d28adfa0f102a9a727faad3c07
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016710"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="14d41-103">Środki trwałe i zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="14d41-103">Work orders and fixed assets</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="14d41-104">W module Zarządzanie składnikami majątku, składniki majątku mogą być powiązane ze środkami trwałymi oraz można tworzyć zlecenia pracy dla tych składników.</span><span class="sxs-lookup"><span data-stu-id="14d41-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="14d41-105">W przypadku korzystania z tej funkcji można zapoznać się z ogólnym przeglądem środków trwałych, powiązanych projektów inwestycyjnych oraz kosztami zarejestrowanymi w projektach inwestycyjnych w modułach **Zarządzanie projektami i ich księgowanie** oraz **Środki trwałe** w Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="14d41-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs that are registered on the investment projects in the **Project management and accounting** and **Fixed assets** modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="14d41-106">Pole **Numer środka trwałego** jest wypełniane tylko w projekcie zadania zlecenia pracy, jeśli w projekcie zadania zlecenia pracy jako typ projektu wybrano typ **Inwestycja**.</span><span class="sxs-lookup"><span data-stu-id="14d41-106">The **Fixed asset number** field on the work order job project is set only if **Investment** is selected as the project type on the work order job project.</span></span>

<span data-ttu-id="14d41-107">Poniższa ilustracja przedstawia relację między projektem inwestycyjnym w module **zarządzanie projektami i ich księgowanie** oraz projektem zadania zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="14d41-107">The illustration below shows the relation between an investment project in the **Project management and accounting** module and a work order job project.</span></span>

![Rysunek 1](media/24-work-orders.png)

<span data-ttu-id="14d41-109">Poniższa procedura opisuje relację między składnikami majątku, zleceniami pracy, projektami zadań zlecenia pracy i środkami trwałymi.</span><span class="sxs-lookup"><span data-stu-id="14d41-109">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="14d41-110">Tworzony jest składnik majątku powiązany z środkiem trwałym.</span><span class="sxs-lookup"><span data-stu-id="14d41-110">You create an asset that you relate to a fixed asset.</span></span>

![Rysunek 2](media/25-work-orders.png)

2. <span data-ttu-id="14d41-112">Podczas konfigurowania typów zleceń pracy na stronie **Typy zleceń pracy** (**Zarządzanie składnikami majątku** > **Konfiguracja** > **Zlecenia pracy** > **Typy zleceń pracy**) tworzony jest typ zlecenia pracy służący do obsługi inwestycji.</span><span class="sxs-lookup"><span data-stu-id="14d41-112">When you set up work order types on the **Work order types** page (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="14d41-113">Zobacz również [Typy zleceń pracy](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="14d41-113">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Rysunek 3](media/26-work-orders.png)

3. <span data-ttu-id="14d41-115">Podczas konfigurowania grup projektów zleceń pracy na karcie **Grupa projektów** na stronie **Ustawienia projektu zlecenia pracy** (**Zarządzanie składnikami majątku** > **Konfiguracja** > **Zlecenia pracy** > **Ustawienia projektu**), tworzy relację między typem zlecenia pracy używanym w inwestycjach a grupą projektów utworzoną dla inwestycji na stronie **Grupy projektów** w module **Zarządzanie projektami i ich księgowanie** (**Zarządzanie projektami i ich księgowanie** > **Konfiguracja** > **Księgowanie** > **Grupy projektów**).</span><span class="sxs-lookup"><span data-stu-id="14d41-115">When you set up work order project groups on the **Project group** tab of the **Work order project setup** page (**Asset management** > **Setup** > **Work orders** > **Project setup**), you create a relation between the work order type that is used for investments and the project group that was created for investments on the **Project groups** page in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Rysunek 4](media/27-work-orders.png)

4. <span data-ttu-id="14d41-117">Podczas tworzenia zlecenia pracy związanego ze środkiem trwałym należy wybrać typ zlecenia pracy używanego do obsługi inwestycji, na przykład **Inwestycja**.</span><span class="sxs-lookup"><span data-stu-id="14d41-117">When you create a work order that is related to a fixed asset, you select the work order type that is used to handle investments, such as **Investment**.</span></span>

5. <span data-ttu-id="14d41-118">Po utworzeniu zlecenia pracy typ powiązanego zlecenia jest pokazywany na stronie **Wszystkie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="14d41-118">When the work order is created, the related work order type is shown on the **All work orders** page.</span></span>

![Rysunek 5](media/28-work-orders.png)

6. <span data-ttu-id="14d41-120">Po utworzeniu zlecenia produkcyjnego projekt powiązany z danym zleceniem produkcyjnym jest tworzony na stronie **Wszystkie projekty** w module **Zarządzanie projektami i ich księgowanie** (**Zarządzanie projektami i ich księgowanie** > **Projekty** > **Wszystkie projekty**).</span><span class="sxs-lookup"><span data-stu-id="14d41-120">When the work order is created, the project that is related to the work order is created on the **All projects** page in the **Project management and accounting** module (**Project management and accounting** > **Projects** > **All projects**).</span></span> <span data-ttu-id="14d41-121">Aby wyświetlić informacje związane z projektem, należy wybrać łącze w polu **Identyfikator projektu** na karcie **Ogólne** w skróconej karcie **Szczegóły wiersza** na stronie **Wszystkie zlecenia pracy** w module **Zarządzanie składnikami majątku** (**Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy**).</span><span class="sxs-lookup"><span data-stu-id="14d41-121">To view project-related information, select the link in the **Project ID** field on the **General** tab on the **Line details** FastTab in the details view of the **All work orders** page in the **Asset management** module (**Asset management** > **Commom** > **Work orders** > **All work orders**).</span></span>

![Rysunek 6](media/29-work-orders.png)

7. <span data-ttu-id="14d41-123">Aby wyświetlić przegląd projektów skojarzonych z środkiem trwałym, należy wybrać **Środki trwałe** > **Środki trwałe** > **Środki trwałe**, a następnie w polu **Numer środka trwałego** wybrać łącze dla środka trwałego w celu otwarcia widoku szczegółów.</span><span class="sxs-lookup"><span data-stu-id="14d41-123">To see an overview of the projects associated with a fixed asset, select **Fixed assets** > **Fixed assets** > **Fixed assets**, and then, in the **Fixed asset number** field, select the link for the fixed asset to open the details view.</span></span> <span data-ttu-id="14d41-124">Rozwiń **Pokrewne okienko informacji** po prawej stronie strony i wybierz skróconą kartę **Skojarzone projekty**.</span><span class="sxs-lookup"><span data-stu-id="14d41-124">Expand the **Related information** pane on the right side of the page, and select the **Associated projects** FastTab.</span></span>

