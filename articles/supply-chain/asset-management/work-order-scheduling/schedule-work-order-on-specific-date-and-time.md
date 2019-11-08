---
title: Planowanie zlecenia pracy według konkretnej daty i godziny
description: W tym temacie opisano sposób zaplanować zlecenie pracy na określony dzień i czas w module Zarządzanie składnikami majątku.
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
ms.openlocfilehash: 634bbb4326d560848d36f579a1179187d8369087
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652041"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a><span data-ttu-id="d3fa0-103">Planowanie zlecenia pracy według konkretnej daty i godziny</span><span class="sxs-lookup"><span data-stu-id="d3fa0-103">Schedule work order on specific date and time</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d3fa0-104">Jeśli zlecenie pracy musi być zaplanowane w określonym dniu *i* o określonej godzinie, można zastąpić standardowy proces planowania w module Zarządzanie składnikami majatku i utworzyć określony harmonogram dla zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-104">If a work order must be scheduled on a specific date *and* time, you can override the standard scheduling process in Asset Management and create a specific schedule for a work order.</span></span>

1. <span data-ttu-id="d3fa0-105">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="d3fa0-106">Na liście zleceń pracy kliknij identyfikator zlecenia pracy w kolumnie **Zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-106">In the work order list, click on the Work order ID in the **Work order** column.</span></span>

3. <span data-ttu-id="d3fa0-107">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-107">Click **Edit**.</span></span>

4. <span data-ttu-id="d3fa0-108">Na karcie skróconej **Nagłówek zlecenia pracy** wstaw daty rozpoczęcia i zakończenia oraz godziny w polach **Oczekiwane rozpoczęcie** i **Oczekiwane zakończenie**.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-108">On the **Work order header** FastTab, insert start and end dates and times in the **Expected start** and **Expected end** fields.</span></span>

    ![Rysunek 1](media/05-work-order-scheduling.png)

5. <span data-ttu-id="d3fa0-110">Na karcie **Ogólne** kliknij opcję **Planowanie**, aby użyć standardowego procesu planowania, lub kliknij przycisk **Wysyłanie**, jeśli chcesz przypisać zlecenie pracy dla określonego pracownika.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-110">On the **General** tab, click **Schedule** to use the standard scheduling process, or click **Dispatch** if you want to assign the work order to a specific worker.</span></span>

6. <span data-ttu-id="d3fa0-111">W celu zastąpienia istniejących rezerwacji zdolności produkcyjnych w celu zapewnienia, że zlecenie pracy jest planowane w oczekiwanym okresie, należy wybrać opcje tak, jak to pokazano na poniższym rysunku w oknie dialogowym **Planowanie zlecenia pracy** > sekcja **Ograniczone zdolności produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-111">In order to override any existing capacity reservations to ensure that the work order is scheduled in the expected period, make the selections as shown in the figure below in the **Schedule work order** dialog > **Finite capacity** section.</span></span> <span data-ttu-id="d3fa0-112">Oznacza to, że proces planowania ignoruje istniejące rezerwacje zdolności produkcyjnych, ponieważ zlecenie pracy musi rozpocząć się w oczekiwanej godzinie rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-112">This means that the scheduling process will ignore existing capacity reservations because the work order must start on the expected start time.</span></span>

    ![Rysunek 2](media/06-work-order-scheduling.png)

7. <span data-ttu-id="d3fa0-114">Kliknij przycisk **OK**, aby rozpocząć planowanie.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-114">Click **OK** to start scheduling.</span></span>

8. <span data-ttu-id="d3fa0-115">Jeśli proces planowania powoduje utworzenie podwójnych rezerwacji, na ekranie pojawi się komunikat i można dostosować powiązane z nim zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-115">If the scheduling process results in double bookings, you will see a message on the screen, and you can adjust the related work orders.</span></span>

>[!NOTE]
><span data-ttu-id="d3fa0-116">Aby zaplanować pracownika obsługi dla zlecenia pracy, pracownik obsługi musi być dostępny w oczekiwanej dacie i godzinie rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="d3fa0-116">In order to schedule a maintenance worker for the work order, that maintenance worker must be available at the expected start date and time.</span></span> <span data-ttu-id="d3fa0-117">Dostępność pracownika jest ustawiana w [kalendarzu pracownika](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span><span class="sxs-lookup"><span data-stu-id="d3fa0-117">Worker availability is set up in the [worker calendar](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span></span> 

