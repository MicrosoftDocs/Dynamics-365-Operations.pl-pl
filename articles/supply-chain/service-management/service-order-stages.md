---
title: Etapy zleceń serwisowych
description: Definiowanie etapów zlecenia serwisowego i przypisanie ich do pracowników pozwala kontrolować przepływ zlecenia serwisowego przez zadania wykonywane przez różne osoby w dziale serwisowym.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d126b68bea8d2083fcf1d08e168b9ead1511b25c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001256"
---
# <a name="service-order-stages"></a><span data-ttu-id="2e107-103">Etapy zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="2e107-103">Service order stages</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="2e107-104">Można skonfigurować etapy zlecenia serwisowego w celu zdefiniowania zadań, które trzeba wykonać, kolejności ich wykonywania oraz pracowników odpowiedzialnych za ich przeprowadzenie.</span><span class="sxs-lookup"><span data-stu-id="2e107-104">You can set up stages for a service order to define the tasks that must be completed, the order in which they are completed, and the workers who are responsible for completing them.</span></span> <span data-ttu-id="2e107-105">Definiowanie etapów zlecenia serwisowego i przypisanie ich do pracowników pozwala kontrolować przepływ zlecenia serwisowego przez zadania wykonywane przez różne osoby w organizacji usługi.</span><span class="sxs-lookup"><span data-stu-id="2e107-105">By defining the stages for a service order and assigning them to workers, you can control the flow of a service order through the tasks that various people perform in the service organization.</span></span> <span data-ttu-id="2e107-106">Sekwencja etapów musi zawierać etap początkowy.</span><span class="sxs-lookup"><span data-stu-id="2e107-106">The sequence of stages must include an initial stage.</span></span>

<span data-ttu-id="2e107-107">Można także zdefiniować działania, które są dozwolone na każdym etapie.</span><span class="sxs-lookup"><span data-stu-id="2e107-107">You can also define the actions that are permitted at each stage.</span></span> <span data-ttu-id="2e107-108">Na przykład wyczyszczenie pola wyboru **Księguj** dla wszystkich etapów poza etapem ostatnim spowoduje, że wszelkie zlecenia serwisowe będą księgowane dopiero po przetworzeniu zleceń serwisowych na wszystkich kolejnych etapach.</span><span class="sxs-lookup"><span data-stu-id="2e107-108">For example, if you clear the **Post** check box for all stages except the final stage, you prevent any service orders from being posted before the service orders are processed through the complete sequence of stages.</span></span>

## <a name="branching-in-service-order-stages"></a><span data-ttu-id="2e107-109">Odgałęzienia na etapach zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="2e107-109">Branching in service order stages</span></span>

<span data-ttu-id="2e107-110">Konfigurując etap usługi, możesz utworzyć wiele opcji lub odgałęzień możliwych do wyboru na następnym etapie usługi.</span><span class="sxs-lookup"><span data-stu-id="2e107-110">When you set up a service stage, you can create multiple options, or branches, to select from for the next service stage.</span></span> <span data-ttu-id="2e107-111">Wszystkich utworzone odgałęzienia są dostępne do wyboru po wykonaniu etapu początkowego.</span><span class="sxs-lookup"><span data-stu-id="2e107-111">All the branches that you create are available to select from when the initial stage is completed.</span></span> <span data-ttu-id="2e107-112">Załóżmy, że etapem początkowym **Planowanie**.</span><span class="sxs-lookup"><span data-stu-id="2e107-112">For example, you set up **Planning** as an initial stage.</span></span> <span data-ttu-id="2e107-113">Tworzysz dwa etapy o nazwie **W trakcie realizacji** i **Anulowanie**, a następnie wybierasz **Planowanie** jako element nadrzędny.</span><span class="sxs-lookup"><span data-stu-id="2e107-113">You create two stages named **In process** and **Cancel**, and then select **Planning** as the parent for them.</span></span> <span data-ttu-id="2e107-114">Przypisujesz etap **Planowanie** do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2e107-114">You assign the **Planning** stage to sales order.</span></span> <span data-ttu-id="2e107-115">Kiedy etap planowania dla zamówienia sprzedaży zostanie wykonany, możesz wybrać etap **W trakcie realizacji** jeśli zamówienie sprzedaży jest gotowe do przetworzenia lub możesz wybrać etap **Anulowanie**, jeśli zamówienie sprzedaży zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="2e107-115">When the planning stage for the sales order is completed, you can select the **In process** stage if the sales order is ready to work on, or you can select the **Cancel** stage if the sales order is canceled.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e107-116">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="2e107-116">See also</span></span>

[<span data-ttu-id="2e107-117">Ustawianie etapów zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="2e107-117">Set up service order stages</span></span>](set-up-service-order-stages.md)

[<span data-ttu-id="2e107-118">Zmiana etapu zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="2e107-118">Change the service order stage</span></span>](change-service-order-stage.md)

  


