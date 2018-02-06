---
title: "Włączanie procesu listy płac obliczanej na podstawie czasu i frekwencji"
description: "W tej procedurze pokazano sposób włączania procesu listy płac dla modułu Czas i frekwencja."
author: johanhoffmann
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 16d8fc2120dfb7b356b238957019a29d05963f9a
ms.contentlocale: pl-pl
ms.lasthandoff: 02/06/2018

---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="506a9-103">Włączanie procesu listy płac obliczanej na podstawie czasu i frekwencji</span><span class="sxs-lookup"><span data-stu-id="506a9-103">Enable the payroll process for time and attendance</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="506a9-104">W tej procedurze pokazano sposób włączania procesu listy płac dla modułu Czas i frekwencja.</span><span class="sxs-lookup"><span data-stu-id="506a9-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="506a9-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="506a9-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="506a9-106">Tworzenie typu płacy z powiązaną stawką płacy</span><span class="sxs-lookup"><span data-stu-id="506a9-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="506a9-107">Czas i frekwencja > Ustawienia > Lista płac > Typy płac</span><span class="sxs-lookup"><span data-stu-id="506a9-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="506a9-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="506a9-108">Click New.</span></span>
3. <span data-ttu-id="506a9-109">W polu Typ płacy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="506a9-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="506a9-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="506a9-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="506a9-111">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="506a9-111">Click Save.</span></span>
6. <span data-ttu-id="506a9-112">Kliknij przycisk Stawki.</span><span class="sxs-lookup"><span data-stu-id="506a9-112">Click Rates.</span></span>
    * <span data-ttu-id="506a9-113">Stawki dla typów płac są konfigurowane w odniesieniu do określonych przedziałów czasowych, a dla poszczególnych pracowników można tworzyć indywidualne stawki.</span><span class="sxs-lookup"><span data-stu-id="506a9-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="506a9-114">Nie zawsze jest konieczne tworzenie stawek dla typów płacy w module Czas i frekwencja.</span><span class="sxs-lookup"><span data-stu-id="506a9-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="506a9-115">Te informacje mogą już istnieć w systemie listy płac, który służy do generowania pensji.</span><span class="sxs-lookup"><span data-stu-id="506a9-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="506a9-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="506a9-116">Click New.</span></span>
8. <span data-ttu-id="506a9-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="506a9-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="506a9-118">W polu Stawka wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="506a9-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="506a9-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="506a9-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="506a9-120">Tworzenie umowy płacowych</span><span class="sxs-lookup"><span data-stu-id="506a9-120">Create a pay agreement</span></span>
1. <span data-ttu-id="506a9-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="506a9-121">Close the page.</span></span>
2. <span data-ttu-id="506a9-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="506a9-122">Close the page.</span></span>
3. <span data-ttu-id="506a9-123">Przejdź do okna Umowy płacowe.</span><span class="sxs-lookup"><span data-stu-id="506a9-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="506a9-124">Czas i frekwencja > Ustawienia > Umowy płacowe</span><span class="sxs-lookup"><span data-stu-id="506a9-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="506a9-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="506a9-125">Click New.</span></span>
5. <span data-ttu-id="506a9-126">W polu Umowa płacowa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="506a9-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="506a9-127">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="506a9-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="506a9-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="506a9-128">Click Save.</span></span>
8. <span data-ttu-id="506a9-129">Kliknij przycisk Wiersze umowy.</span><span class="sxs-lookup"><span data-stu-id="506a9-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="506a9-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="506a9-130">Click New.</span></span>
10. <span data-ttu-id="506a9-131">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="506a9-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="506a9-132">W polu Typ profilu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="506a9-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="506a9-133">W polu Typ płacy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="506a9-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="506a9-134">Konfigurowanie umowy płacowej dla pracownika rozliczanego według czasu i rejestracji</span><span class="sxs-lookup"><span data-stu-id="506a9-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="506a9-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="506a9-135">Close the page.</span></span>
2. <span data-ttu-id="506a9-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="506a9-136">Close the page.</span></span>
3. <span data-ttu-id="506a9-137">Przejdź do okna Pracownicy odpowiedzialni za rejestrację czasu.</span><span class="sxs-lookup"><span data-stu-id="506a9-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="506a9-138">Czas i frekwencja > Ustawienia > Pracownicy odpowiedzialni za rejestrację czasu</span><span class="sxs-lookup"><span data-stu-id="506a9-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="506a9-139">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="506a9-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="506a9-140">Kliknij kartę Zatrudnienie.</span><span class="sxs-lookup"><span data-stu-id="506a9-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="506a9-141">Rozwiń sekcję Rejestracja czasu.</span><span class="sxs-lookup"><span data-stu-id="506a9-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="506a9-142">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="506a9-142">Click Edit.</span></span>
8. <span data-ttu-id="506a9-143">W polu Umowa płacowa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="506a9-143">In the Pay agreement field, enter or select a value.</span></span>

