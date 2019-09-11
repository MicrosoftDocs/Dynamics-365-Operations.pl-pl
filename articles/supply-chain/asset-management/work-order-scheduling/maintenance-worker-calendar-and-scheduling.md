---
title: Kalendarz konserwatora i planowanie
description: W tym temacie opisano kalendarze konserwatora w odniesieniu do planowania w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 3f86f6475e5226443f5e4d43fb91acafe2afdbb9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887395"
---
# <a name="maintenance-worker-calendar-and-scheduling"></a><span data-ttu-id="de641-103">Kalendarz konserwatora i planowanie</span><span class="sxs-lookup"><span data-stu-id="de641-103">Maintenance worker calendar and scheduling</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="de641-104">Podczas planowania zleceń pracy tworzony jest harmonogram konserwatorów, narzędzi i składników majątku.</span><span class="sxs-lookup"><span data-stu-id="de641-104">When you schedule work orders, you create a schedule for maintenance workers, tools, and assets.</span></span> <span data-ttu-id="de641-105">Aby można było wykonać planowanie pracowników konserwacji, należy skonfigurować kalendarz dla każdego konserwatora.</span><span class="sxs-lookup"><span data-stu-id="de641-105">In order to carry out scheduling on maintenance workers, a calendar must be set up for each maintenance worker.</span></span> <span data-ttu-id="de641-106">Konserwatorzy są związani z zasobami, a kalendarze czasu pracy są ustawiane na zasobach.</span><span class="sxs-lookup"><span data-stu-id="de641-106">Maintenance workers are related to a resource, and working time calendars are set up on resoures.</span></span> <span data-ttu-id="de641-107">Użytkownik konfiguruje zasób i kalendarz związany z konserwatorem w **Zarządzanie składnikami majątku** > **Konfiguracja** > **Pracownicy** > **Pracownicy**, które są opisane w [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="de641-107">You set up the resource and calendar related to a worker in **Asset management** > **Setup** > **Workers** > **Workers**, which is described in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

<span data-ttu-id="de641-108">Poniższy zrzut ekranu pokazuje przykład konserwatora, który jest powiązany z zasobem korzystającym z kalendarza czasu pracy „produkcja”.</span><span class="sxs-lookup"><span data-stu-id="de641-108">The screenshot below shows an example of a maintenance worker who is related to a resource that uses the working time calendar "Production".</span></span>

![Rysunek 1](media/01-work-order-scheduling.png)

<span data-ttu-id="de641-110">Ustawienia kalendarza dla narzędzi i składników majątku nie są potrzebne w odniesieniu do planowania zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="de641-110">Calendar setup for tools and assets is not needed in relation to work order scheduling.</span></span> <span data-ttu-id="de641-111">Założeniem jest, że narzędzia i zasoby są dostępne 24 godziny na dobę w celu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="de641-111">The assumption is that tools and assets are available 24 hours a day for maintenance.</span></span>

