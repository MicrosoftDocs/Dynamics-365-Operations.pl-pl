--- 
title: Tworzenie kalendarza i generowanie godzin pracy
description: "Kalendarze opisują zdolności produkcyjne i czasy pracy zasobów operacyjnych."
author: kherr75
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a8dcef8d8ba6f6d41a997b5b0623cb9577ce00d3
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-calendar-and-generate-working-times"></a><span data-ttu-id="89c1d-103">Tworzenie kalendarza i generowanie godzin pracy</span><span class="sxs-lookup"><span data-stu-id="89c1d-103">Create a calendar and generate working times</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="89c1d-104">Kalendarze opisują zdolności produkcyjne i czasy pracy zasobów operacyjnych.</span><span class="sxs-lookup"><span data-stu-id="89c1d-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="89c1d-105">Ta procedura pomoże zdefiniować kalendarz pracy na podstawie szablonu czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="89c1d-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="89c1d-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="89c1d-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="89c1d-107">Wybierz kolejno opcje Wszystkie obszary robocze > Zarządzanie cyklem życia zasobu.</span><span class="sxs-lookup"><span data-stu-id="89c1d-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="89c1d-108">Kliknij opcję Kalendarze.</span><span class="sxs-lookup"><span data-stu-id="89c1d-108">Click Calendars.</span></span>
3. <span data-ttu-id="89c1d-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="89c1d-109">Click New.</span></span>
4. <span data-ttu-id="89c1d-110">W polu Kalendarz wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="89c1d-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="89c1d-111">Jest to identyfikator kalendarza, który jest używany jako odwołanie podczas przypisywania kalendarzy, np. do zasobu operacyjnego lub grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="89c1d-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="89c1d-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="89c1d-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="89c1d-113">W Standardowy dzień roboczy w godzinach wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="89c1d-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="89c1d-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="89c1d-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="89c1d-115">Kliknij opcję Czasy pracy.</span><span class="sxs-lookup"><span data-stu-id="89c1d-115">Click Working times.</span></span>
9. <span data-ttu-id="89c1d-116">Kliknij opcję Tworzenie czasów pracy.</span><span class="sxs-lookup"><span data-stu-id="89c1d-116">Click Compose working times.</span></span>
    * <span data-ttu-id="89c1d-117">Wygeneruj godziny pracy dla każdego dnia w okresie, w którym chcesz mieć możliwość planowania pracy.</span><span class="sxs-lookup"><span data-stu-id="89c1d-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="89c1d-118">Wraz z upływem czasu można generować czasy pracy na dodatkowe okresy.</span><span class="sxs-lookup"><span data-stu-id="89c1d-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="89c1d-119">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="89c1d-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="89c1d-120">To jest pierwszy dzień, w którym ten kalendarz musi być otwarty.</span><span class="sxs-lookup"><span data-stu-id="89c1d-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="89c1d-121">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="89c1d-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="89c1d-122">To jest ostatni dzień, w którym ten kalendarz jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="89c1d-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="89c1d-123">W polu Szablon czasu pracy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="89c1d-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="89c1d-124">Szablon czasu pracy definiuje godziny pracy dla każdego dnia tygodnia.</span><span class="sxs-lookup"><span data-stu-id="89c1d-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="89c1d-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="89c1d-125">Click OK.</span></span>
14. <span data-ttu-id="89c1d-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="89c1d-126">Close the page.</span></span>


