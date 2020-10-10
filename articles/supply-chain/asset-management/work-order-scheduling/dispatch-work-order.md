---
title: Wysyłanie zlecenia pracy
description: W tym temacie opisano wysyłanie zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d46beb04923d06aa8ccec05355731aa1b3f27c5b
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889296"
---
# <a name="dispatch-work-order"></a><span data-ttu-id="a7479-103">Wysyłanie zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="a7479-103">Dispatch work order</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a7479-104">Istnieje możliwość zaplanowania jednego zadania zlecenia pracy lub zlecenia pracy dla jednego pracownika korzystającego z funkcji **wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="a7479-104">You can schedule one work order or work order jobs to one worker using the **Dispatch** functionality.</span></span>

1. <span data-ttu-id="a7479-105">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="a7479-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="a7479-106">Wybierz zlecenie pracy z listy.</span><span class="sxs-lookup"><span data-stu-id="a7479-106">Select the work order in the list.</span></span>

3. <span data-ttu-id="a7479-107">Na karcie **Ogólne** kliknij przycisk **Wysyłanie**.</span><span class="sxs-lookup"><span data-stu-id="a7479-107">On the **General** tab, click **Dispatch**.</span></span>

4. <span data-ttu-id="a7479-108">W oknie dialogowym **Zaplanuj zlecenie pracy** wybierz pracownika w polu **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="a7479-108">In the **Schedule work order** dialog, select the worker in the **Worker** field.</span></span>

5. <span data-ttu-id="a7479-109">W polu **Planowanie godzinowe** można wstawiać oczekiwane godziny pracy w przypadku, gdy oczekiwane godziny pracy różnią się od godzin prognozowanych.</span><span class="sxs-lookup"><span data-stu-id="a7479-109">In the **Schedule hours** field, you can insert expected work hours in case expected work hours differ from forecast hours.</span></span>

6. <span data-ttu-id="a7479-110">W polu **planowane rozpoczęcie** można edytować datę i godzinę rozpoczęcia, jeśli jest to wymagane.</span><span class="sxs-lookup"><span data-stu-id="a7479-110">In the **Scheduled start** field, you can edit start date and time, if required.</span></span>

7. <span data-ttu-id="a7479-111">Jeśli proces planowania powinien uwzględniać ograniczenia zdolności produkcyjnych dotyczące zasobów, które są już zaplanowane dla innych zadań, należy upewnić się, że przyciski przełączania **Składnik majątku**, **Narzędzie** i **Pracownik** zostały ustawione na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a7479-111">If the scheduling process should observe capacity limitations regarding resources already scheduled on other jobs, make sure that the **Asset**, **Tool**, and **Worker** toggle buttons are set to **Yes**.</span></span> <span data-ttu-id="a7479-112">Aby wyświetlić szczegółowe informacje o procesie planowania, wybierz wartość **Tak** w przycisku przełączania **Pełne**.</span><span class="sxs-lookup"><span data-stu-id="a7479-112">If you want to see detailed information about the scheduling process, select **Yes** on the **Verbose** toggle button.</span></span> <span data-ttu-id="a7479-113">Oznacza to, że w dzienniku informacyjnym zostaną wyświetlone szczegółowe informacje o obliczonych wynikach zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="a7479-113">This means detailed information about the calculated scores on the work order is shown in the Infolog.</span></span>

8. <span data-ttu-id="a7479-114">Wybierz wartość **Tak** na przycisku przełącznika **Ignoruj harmonogram**, aby zignorować dni zamknięte w kalendarzu (dotyczy składnika majątku, pracownika i narzędzi).</span><span class="sxs-lookup"><span data-stu-id="a7479-114">Select **Yes** on the **Ignore schedule** toggle button to ignore closed days in the calendar (applies to asset, worker, and tools).</span></span> <span data-ttu-id="a7479-115">Wybierz wartość **Tak** na przycisku przełącznika **Ignoruj zaplanowane wykonanie** w celu zignorowania ograniczeń, które mogły zostać wybrane w zleceniu pracy wymagającym planowania.</span><span class="sxs-lookup"><span data-stu-id="a7479-115">Select **Yes** on the **Ignore scheduled execution** toggle button to ignore limitations that may have been selected on the work order regarding scheduling.</span></span> 

    <span data-ttu-id="a7479-116">Aby dowiedzieć się więcej o konfiguracji zaplanowanego wykonania, zobacz sekcję [Zaplanowane wykonanie](../setup-for-work-orders/scheduled-execution.md).</span><span class="sxs-lookup"><span data-stu-id="a7479-116">For information on the setup of scheduled execution, see the [Scheduled execution](../setup-for-work-orders/scheduled-execution.md) section.</span></span>

9. <span data-ttu-id="a7479-117">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7479-117">Click **OK**.</span></span> <span data-ttu-id="a7479-118">Stan cyklu życia zlecenia pracy jest automatycznie aktualizowany do stanu cyklu życia **Zaplanowane** określonego w obszarze **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Modele cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="a7479-118">The work order lifecycle state is automatically updated to the **Scheduled** lifecycle state specified **Asset management** > **Setup** > **Work orders** > **Lifecycle models**.</span></span>

<span data-ttu-id="a7479-119">Na poniższym rysunku pokazano przykładowe opcje wysyłki w oknie dialogowym **Zaplanuj zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="a7479-119">The figure below shows an example of dispatch selections in the **Schedule work order** dialog.</span></span>

![Rysunek 1](media/04-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="a7479-121">Aby usunąć harmonogram w zleceniu pracy, wybierz zlecenie pracy w obszarze **Wszystkie zlecenia pracy** i kliknij pozycję **Usuń harmonogram** na karcie **Ogólne**. Pamiętaj, aby ręcznie zaktualizować stan cyklu życia zlecenia pracy w przypadku usuwania harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="a7479-121">If you want to delete the schedule on a work order, select the work order in **All work orders**, and then click **Delete schedule** on the **General** tab. Remember to manually update the work order lifecycle state if you delete the schedule.</span></span>

