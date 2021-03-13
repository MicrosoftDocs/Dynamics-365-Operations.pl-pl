---
title: Kalendarz konserwatora i planowanie
description: W tym temacie opisano kalendarze konserwatora w odniesieniu do planowania w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorker
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c8856d0c7a7b76318755dc6bcdbb1859de1fa20a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021486"
---
# <a name="maintenance-worker-calendar-and-scheduling"></a><span data-ttu-id="b8d69-103">Kalendarz konserwatora i planowanie</span><span class="sxs-lookup"><span data-stu-id="b8d69-103">Maintenance worker calendar and scheduling</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b8d69-104">Podczas planowania zleceń pracy tworzony jest harmonogram konserwatorów, narzędzi i składników majątku.</span><span class="sxs-lookup"><span data-stu-id="b8d69-104">When you schedule work orders, you create a schedule for maintenance workers, tools, and assets.</span></span> <span data-ttu-id="b8d69-105">Aby można było wykonać planowanie pracowników konserwacji, należy skonfigurować kalendarz dla każdego konserwatora.</span><span class="sxs-lookup"><span data-stu-id="b8d69-105">In order to schedule maintenance workers, a calendar must be set up for each maintenance worker.</span></span> <span data-ttu-id="b8d69-106">Konserwatorzy są związani z zasobami, a kalendarze czasu pracy są ustawiane dla zasobów.</span><span class="sxs-lookup"><span data-stu-id="b8d69-106">Maintenance workers are related to a resource, and working time calendars are set up for resources.</span></span> <span data-ttu-id="b8d69-107">Użytkownik konfiguruje zasób i kalendarz związany z pracownikiem w **Zarządzanie składnikami majątku** > **Konfiguracja** > **Pracownicy** > **Pracownicy**, które są opisane w [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b8d69-107">You set up the resource and calendar in **Asset management** > **Setup** > **Workers** > **Workers**, which is described in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

<span data-ttu-id="b8d69-108">Poniższy zrzut ekranu pokazuje przykład konserwatora, który jest powiązany z zasobem korzystającym z kalendarza czasu pracy „produkcja”.</span><span class="sxs-lookup"><span data-stu-id="b8d69-108">The screenshot below shows an example of a maintenance worker who is related to a resource that uses the working time calendar "Production".</span></span>

![Rysunek 1](media/01-work-order-scheduling.png)

<span data-ttu-id="b8d69-110">Ustawienia kalendarza dla narzędzi i składników majątku nie są potrzebne w odniesieniu do planowania zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="b8d69-110">Calendar setup for tools and assets is not needed in relation to work order scheduling.</span></span> <span data-ttu-id="b8d69-111">Założeniem jest, że narzędzia i zasoby są dostępne 24 godziny na dobę w celu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="b8d69-111">The assumption is that tools and assets are available 24 hours a day for maintenance.</span></span>

