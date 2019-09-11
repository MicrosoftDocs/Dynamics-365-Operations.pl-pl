---
title: Planowane zadania konserwacji zlecenia pracy
description: W tym temacie zamówiono zaplanowane zadania konserwacji zleceń pracy w module Zarządzanie składnikami majątku.
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
ms.openlocfilehash: 4b3cc32d6ff263967c1ee843702c28968219ac33
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887189"
---
# <a name="scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="0a13b-103">Planowane zadania konserwacji zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="0a13b-103">Scheduled work order maintenance jobs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="0a13b-104">Strona **Zaplanowane konserwacyjne zlecania pracy** służy do uzyskiwania przeglądu zleceń przydzielonych do zasobu.</span><span class="sxs-lookup"><span data-stu-id="0a13b-104">The **Scheduled work order maintenance jobs** page is used to get an overview of the work orders allocated to a resource.</span></span> <span data-ttu-id="0a13b-105">Na liście zostaną wyświetlone zlecenia produkcyjne korzystające z typów zasobów „zasoby ludzkie”, „narzędzie” i „maszyna”.</span><span class="sxs-lookup"><span data-stu-id="0a13b-105">Work orders using resource types "Human resources", "Tool", and "Machine" are shown in the list.</span></span> <span data-ttu-id="0a13b-106">Lista może służyć do uzyskiwania przeglądu zleceń pracy alokowanych do określonego zasobu.</span><span class="sxs-lookup"><span data-stu-id="0a13b-106">The list can be used to get an overview of work orders allocated to a specific resource.</span></span> <span data-ttu-id="0a13b-107">Można go również używać do szybkiego znajdowania zlecenia pracy przydzielonego pracownikowi obsługi technicznej, który na przykład zachorował danego dnia, a następnie szybko przydzieli innemu pracownikowi obsługi to zadanie.</span><span class="sxs-lookup"><span data-stu-id="0a13b-107">You can also use it to quickly find a work order allocated to a maintenance worker who, for example, called in sick this morning, and then quickly allocate another maintenance worker to the job.</span></span>

## <a name="view-scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="0a13b-108">Zobacz zaplanowane zadania konserwacyjne zlecania pracy</span><span class="sxs-lookup"><span data-stu-id="0a13b-108">View scheduled work order maintenance jobs</span></span>

1. <span data-ttu-id="0a13b-109">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Zaplanowane konserwacyjne zlecania pracy**.</span><span class="sxs-lookup"><span data-stu-id="0a13b-109">Click **Asset management** > **Common** > **Work orders** > **Scheduled work order maintenance jobs**.</span></span> <span data-ttu-id="0a13b-110">Zostanie wyświetlona lista wszystkich zleceń pracy ustawionych dla stanu cyklu życia zlecenia pracy „zaplanowane” lub „w toku”</span><span class="sxs-lookup"><span data-stu-id="0a13b-110">You see a list of all work orders set to work order lifecycle state "Scheduled" or "In progress".</span></span>

2. <span data-ttu-id="0a13b-111">Listę można posortować, na przykład według konserwatora.</span><span class="sxs-lookup"><span data-stu-id="0a13b-111">You can sort the list, for example, by maintenance worker.</span></span> <span data-ttu-id="0a13b-112">Filtru można również używać do ograniczania listy do wyświetlania zleceń pracy przydzielonych do określonego zasobu lub konserwatora.</span><span class="sxs-lookup"><span data-stu-id="0a13b-112">You can also use the filter to limit the list to display work orders allocated to a specific resource or maintenance worker.</span></span>

3. <span data-ttu-id="0a13b-113">Notatki można wyświetlać w zleceniu pracy, a w razie potrzeby dodawać nowe notatki, zaznaczając zadanie zlecenia na liście i klikając przycisk **Notatki**.</span><span class="sxs-lookup"><span data-stu-id="0a13b-113">You can see notes on the work order and, if required, add new notes by selecting the work order job in the list and clicking **Notes**.</span></span>

4. <span data-ttu-id="0a13b-114">Aby przydzielić jednemu konserwatora do zlecenia pracy, wybierz zlecenie pracy z listy i kliknij przycisk **Zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="0a13b-114">If you want to allocate one maintenance worker to a work order, select the work order in the list, and click **Work order**.</span></span>

5. <span data-ttu-id="0a13b-115">Zostanie otwarta strona **Zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="0a13b-115">The **Work order** page opens.</span></span> <span data-ttu-id="0a13b-116">Kliknij przycisk **Wysyłania**, aby zaplanować zlecenie pracy dla określonego konserwatora.</span><span class="sxs-lookup"><span data-stu-id="0a13b-116">Click **Dispatch** to schedule the work order to a specific maintenance worker.</span></span>

>[!NOTE]
><span data-ttu-id="0a13b-117">Aby uzyskać więcej informacji o planowaniu kilku zleceń pracy lub jednego zlecenia pracy należy odwołać się do tematów [Planowanie zlecenia pracy](../work-order-scheduling/schedule-work-orders.md) i [Wysyłanie zlecenia pracy](../work-order-scheduling/dispatch-work-order.md).</span><span class="sxs-lookup"><span data-stu-id="0a13b-117">Read more about scheduling several work orders or one work order in [Schedule work orders](../work-order-scheduling/schedule-work-orders.md) and [Dispatch work order](../work-order-scheduling/dispatch-work-order.md).</span></span>

<span data-ttu-id="0a13b-118">Na poniższym rysunku pokazano przykład strony **Zaplanowane konserwacyjne zlecania pracy**.</span><span class="sxs-lookup"><span data-stu-id="0a13b-118">The figure below shows an example of the **Scheduled work order maintenance jobs** page.</span></span>

![Rysunek 1](media/07-work-order-scheduling.png)

