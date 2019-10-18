---
title: Tworzenie kalendarzy i generowanie godzin pracy
description: Kalendarze opisują zdolności produkcyjne i czasy pracy zasobów operacyjnych. Ten temat wyjaśnia, jak definiować kalendarz pracy na podstawie szablonu czasu pracy.
author: andreabichsel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 50b81ae228d9aee4111ce8d161508d5ed1af4f27
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190679"
---
# <a name="create-calendar-and-generate-working-times"></a><span data-ttu-id="3b226-104">Tworzenie kalendarza i generowanie godzin pracy</span><span class="sxs-lookup"><span data-stu-id="3b226-104">Create calendar and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b226-105">Kalendarze opisują zdolności produkcyjne i czasy pracy zasobów operacyjnych.</span><span class="sxs-lookup"><span data-stu-id="3b226-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="3b226-106">Ten temat wyjaśnia, jak definiować kalendarz pracy na podstawie szablonu czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="3b226-106">This topic explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="3b226-107">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="3b226-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="3b226-108">Na stronie głównej wybierz **Zarządzanie cyklem życia zasobu**.</span><span class="sxs-lookup"><span data-stu-id="3b226-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="3b226-109">Wybierz **Kalendarze**.</span><span class="sxs-lookup"><span data-stu-id="3b226-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="3b226-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="3b226-110">Select **New**.</span></span>
4. <span data-ttu-id="3b226-111">W polu **Kalendarz** należy klasyfikować kalendarz.</span><span class="sxs-lookup"><span data-stu-id="3b226-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="3b226-112">Jest to identyfikator kalendarza, który jest używany jako odwołanie podczas przypisywania kalendarzy, np. do zasobu operacyjnego lub grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="3b226-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="3b226-113">W polu **Nazwa** nazwij swój kalendarz.</span><span class="sxs-lookup"><span data-stu-id="3b226-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="3b226-114">W **Standardowy dzień roboczy w godzinach** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="3b226-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="3b226-115">Upewnij się, że wiersz jest zaznaczony, a następnie wybierz opcję **Czasy pracy** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="3b226-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="3b226-116">Wybierz **Tworzenie czasów pracy**.</span><span class="sxs-lookup"><span data-stu-id="3b226-116">Select **Compose working times**.</span></span> <span data-ttu-id="3b226-117">Wygeneruj godziny pracy dla każdego dnia w okresie, w którym chcesz mieć możliwość planowania pracy.</span><span class="sxs-lookup"><span data-stu-id="3b226-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="3b226-118">Wraz z upływem czasu można generować czasy pracy na dodatkowe okresy.</span><span class="sxs-lookup"><span data-stu-id="3b226-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="3b226-119">W polu **Od dnia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="3b226-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="3b226-120">To jest pierwszy dzień, w którym ten kalendarz musi być otwarty.</span><span class="sxs-lookup"><span data-stu-id="3b226-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="3b226-121">Wprowadź datę w polu **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="3b226-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="3b226-122">To jest ostatni dzień, w którym ten kalendarz jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="3b226-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="3b226-123">W polu **Szablon czasu pracy** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3b226-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="3b226-124">Szablon czasu pracy definiuje godziny pracy dla każdego dnia tygodnia.</span><span class="sxs-lookup"><span data-stu-id="3b226-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="3b226-125">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b226-125">Select **OK**.</span></span>
13. <span data-ttu-id="3b226-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3b226-126">Close the page.</span></span>

