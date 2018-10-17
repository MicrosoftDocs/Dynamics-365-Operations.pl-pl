--- 
title: Tworzenie kalendarza i generowanie godzin pracy
description: "Kalendarze opisują zdolności produkcyjne i czasy pracy zasobów operacyjnych."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 8a556367857890acdb926ed29518cf2f2f2b92ea
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="create-calendar-and-generate-working-times"></a><span data-ttu-id="e23da-103">Tworzenie kalendarza i generowanie godzin pracy</span><span class="sxs-lookup"><span data-stu-id="e23da-103">Create calendar and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e23da-104">Kalendarze opisują zdolności produkcyjne i czasy pracy zasobów operacyjnych.</span><span class="sxs-lookup"><span data-stu-id="e23da-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="e23da-105">Ta procedura pomoże zdefiniować kalendarz pracy na podstawie szablonu czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="e23da-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="e23da-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="e23da-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="e23da-107">Wybierz kolejno opcje Wszystkie obszary robocze > Zarządzanie cyklem życia zasobu.</span><span class="sxs-lookup"><span data-stu-id="e23da-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="e23da-108">Kliknij opcję Kalendarze.</span><span class="sxs-lookup"><span data-stu-id="e23da-108">Click Calendars.</span></span>
3. <span data-ttu-id="e23da-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e23da-109">Click New.</span></span>
4. <span data-ttu-id="e23da-110">W polu Kalendarz wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e23da-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="e23da-111">Jest to identyfikator kalendarza, który jest używany jako odwołanie podczas przypisywania kalendarzy, np. do zasobu operacyjnego lub grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="e23da-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="e23da-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e23da-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="e23da-113">W Standardowy dzień roboczy w godzinach wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e23da-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="e23da-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e23da-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="e23da-115">Kliknij opcję Czasy pracy.</span><span class="sxs-lookup"><span data-stu-id="e23da-115">Click Working times.</span></span>
9. <span data-ttu-id="e23da-116">Kliknij opcję Tworzenie czasów pracy.</span><span class="sxs-lookup"><span data-stu-id="e23da-116">Click Compose working times.</span></span>
    * <span data-ttu-id="e23da-117">Wygeneruj godziny pracy dla każdego dnia w okresie, w którym chcesz mieć możliwość planowania pracy.</span><span class="sxs-lookup"><span data-stu-id="e23da-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="e23da-118">Wraz z upływem czasu można generować czasy pracy na dodatkowe okresy.</span><span class="sxs-lookup"><span data-stu-id="e23da-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="e23da-119">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="e23da-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="e23da-120">To jest pierwszy dzień, w którym ten kalendarz musi być otwarty.</span><span class="sxs-lookup"><span data-stu-id="e23da-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="e23da-121">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="e23da-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="e23da-122">To jest ostatni dzień, w którym ten kalendarz jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="e23da-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="e23da-123">W polu Szablon czasu pracy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e23da-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="e23da-124">Szablon czasu pracy definiuje godziny pracy dla każdego dnia tygodnia.</span><span class="sxs-lookup"><span data-stu-id="e23da-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="e23da-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e23da-125">Click OK.</span></span>
14. <span data-ttu-id="e23da-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e23da-126">Close the page.</span></span>


