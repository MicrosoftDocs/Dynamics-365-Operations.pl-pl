---
title: Zaplanowane wykonanie
description: W tym temacie opisano zaplanowane wykonanie w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
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
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8d9c8afc139c96e32efb3161d35fde685b8abcc5
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874677"
---
# <a name="scheduled-execution"></a><span data-ttu-id="2a402-103">Zaplanowane wykonanie</span><span class="sxs-lookup"><span data-stu-id="2a402-103">Scheduled execution</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="2a402-104">Do skonfigurowania zaplanowanego wykonania można używać poziomów usługi zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="2a402-104">You can use work order service levels to set up scheduled execution.</span></span> <span data-ttu-id="2a402-105">(Aby uzyskać więcej informacji na temat poziomów usługi zlecenia pracy, zapoznaj się z [Poziom i opis usługi](service-level-and-description.md).) Zaplanowane wykonanie zapewnia elastyczność w planowaniu pracy dla pracowników konserwacji, ponieważ istnieje możliwość skonfigurowania bardziej szczegółowych lub mniej szczegółowych wymagań dotyczących interwału, w którym zlecenie pracy powinno zostać zrealizowane.</span><span class="sxs-lookup"><span data-stu-id="2a402-105">(For more information about work order service levels, see [Service level and description](service-level-and-description.md).) Scheduled execution provides flexibility in work planning for maintenance workers, because you can set up more detailed or less detailed requirements for the interval that a work order should be completed during.</span></span> <span data-ttu-id="2a402-106">Na przykład konserwator, który wykonuje zadanie szybciej, niż oczekiwano w obiekcie produkcyjnym, może mieć możliwość przejścia do innego zaplanowanego zadania, które było planowane w bieżącym tygodniu, ale niekoniecznie w bieżącym dniu.</span><span class="sxs-lookup"><span data-stu-id="2a402-106">For example, a maintenance worker who completes a job faster than expected in a production facility might be able to move on to another nearby job that was planned for the current week but not necessarily for the current day.</span></span> <span data-ttu-id="2a402-107">Takie podejście umożliwia optymalizację planowania pracowników i ukończenia zadań.</span><span class="sxs-lookup"><span data-stu-id="2a402-107">This approach allows for optimization of worker planning and job completion.</span></span>

<span data-ttu-id="2a402-108">Konfiguracja planowania wykonania, która jest związana z zleceniami pracy, może być rodzajowa lub konkretna.</span><span class="sxs-lookup"><span data-stu-id="2a402-108">Scheduled execution setup, which is related to work orders, can be generic or specific.</span></span> <span data-ttu-id="2a402-109">Można skonfigurować wiersze ogólne, które nie są ograniczone do określonych typów zleceń pracy, typów składników majątku itd.</span><span class="sxs-lookup"><span data-stu-id="2a402-109">You can set up generic lines that aren't limited to specific work order types, asset types, and so on.</span></span> <span data-ttu-id="2a402-110">Można również utworzyć zaplanowane wiersze wykonania, które mają zastosowanie do określonego typu zlecenia, typu składnika majątku, typu zadania konserwacji itd.</span><span class="sxs-lookup"><span data-stu-id="2a402-110">Alternatively, you can create scheduled execution lines that apply to a specific work order type, asset type, maintenance job type, and so on.</span></span>

1. <span data-ttu-id="2a402-111">Wybierz **Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Zaplanowane wykonanie**.</span><span class="sxs-lookup"><span data-stu-id="2a402-111">Select **Asset management** \> **Setup** \> **Work orders** \> **Scheduled execution**.</span></span>
2. <span data-ttu-id="2a402-112">Wybierz **Nowe**, aby utworzyć nowy wiersz zaplanowanego wykonania.</span><span class="sxs-lookup"><span data-stu-id="2a402-112">Select **New** to create a scheduled execution line.</span></span>
3. <span data-ttu-id="2a402-113">W polach **Lokalizacja czynności konserwacyjnych**, **Typ zlecenia pracy**, **Typ składnika majątku**, **Producent**, **Model**, **Kategoria typu zadania konserwacji**, **Typ zadania konserwacji**, **Wariant typu zadania konserwacji** i **Handel** wybierz wymagane wartości.</span><span class="sxs-lookup"><span data-stu-id="2a402-113">In the **Functional location**, **Work order type**, **Asset type**, **Manufacturer**, **Model**, **Maintenance job type category**, **Maintenance job type**, **Maintenance job type variant**, and **Trade** fields, select values as you require.</span></span>
4. <span data-ttu-id="2a402-114">W polu **Poziom usług** wybierz poziom usługi zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="2a402-114">In the **Service level** field, select a work order service level.</span></span> <span data-ttu-id="2a402-115">Jeśli to pole pozostanie puste, będzie można utworzyć najbardziej ogólny typ wiersza zaplanowanego wykonania.</span><span class="sxs-lookup"><span data-stu-id="2a402-115">If you leave this field blank, you make the most generic type of scheduled execution line.</span></span> <span data-ttu-id="2a402-116">Aby zapoznać się z przykładowym wierszem ogólnym, należy zapoznać się z pierwszym rekordem na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="2a402-116">For an example of a generic line, see the first record in the illustration that follows.</span></span> <span data-ttu-id="2a402-117">Ten wiersz umożliwia zaplanowanie wszystkich zleceń pracy bez określonego poziomu usługi zlecenia pracy dla określonej daty i godziny.</span><span class="sxs-lookup"><span data-stu-id="2a402-117">That line enables all work orders that have no work order service level to be scheduled for a specific date and time.</span></span>
5. <span data-ttu-id="2a402-118">W polu **Zaplanowane wykonanie** wybierz interwał czasu.</span><span class="sxs-lookup"><span data-stu-id="2a402-118">In the **Scheduled execution** field, select the time interval.</span></span>
6. <span data-ttu-id="2a402-119">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2a402-119">Select **Save**.</span></span>

![Rysunek 1](media/20-setup-for-work-orders.png)
