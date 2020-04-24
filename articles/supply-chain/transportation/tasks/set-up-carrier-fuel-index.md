---
title: Konfigurowanie indeksu paliwowego przewoźnika
description: W tym przewodniku przedstawiono sposób tworzenia regionu indeksu paliwowego, indeksu paliwowego i indeksu paliwowego przewoźnika.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69bf6e3a896e560b1dbb96c8f997f6ee8dbb9ec1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214925"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="2803a-103">Konfigurowanie indeksu paliwowego przewoźnika</span><span class="sxs-lookup"><span data-stu-id="2803a-103">Set up a carrier fuel index</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2803a-104">W tym przewodniku przedstawiono sposób tworzenia regionu indeksu paliwowego, indeksu paliwowego i indeksu paliwowego przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="2803a-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="2803a-105">Region indeksu paliwowego określa, do którego regionu powinien być stosowany indeks paliwowy, a indeks paliwowy określa cenę paliwa w określonym przedziale czasu.</span><span class="sxs-lookup"><span data-stu-id="2803a-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="2803a-106">W celu odzwierciedlenia zmian w cenach paliwa w czasie można skojarzyć wiele indeksów paliwowych z przewoźnikiem.</span><span class="sxs-lookup"><span data-stu-id="2803a-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="2803a-107">Te zadania są zwykle wykonywane przez koordynatora transportu.</span><span class="sxs-lookup"><span data-stu-id="2803a-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="2803a-108">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="2803a-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="2803a-109">Tworzenie regionu indeksu paliwowego</span><span class="sxs-lookup"><span data-stu-id="2803a-109">Create a fuel index region</span></span>
1. <span data-ttu-id="2803a-110">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Indeksy paliwowe > Regiony indeksów paliwowych.</span><span class="sxs-lookup"><span data-stu-id="2803a-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="2803a-111">Najpierw należy utworzyć różne regiony, gdzie firma działa, i obliczyć różne dopłaty za paliwo.</span><span class="sxs-lookup"><span data-stu-id="2803a-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="2803a-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2803a-112">Click New.</span></span>
3. <span data-ttu-id="2803a-113">W polu Region wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2803a-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="2803a-114">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2803a-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2803a-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2803a-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="2803a-116">Tworzenie indeksu paliwowego</span><span class="sxs-lookup"><span data-stu-id="2803a-116">Create a fuel index</span></span>
1. <span data-ttu-id="2803a-117">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Indeksy paliwowe > Indeksy paliwowe.</span><span class="sxs-lookup"><span data-stu-id="2803a-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="2803a-118">Dla skonfigurowanych regionów należy wprowadzić bieżące ceny dla paliwa.</span><span class="sxs-lookup"><span data-stu-id="2803a-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="2803a-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2803a-119">Click New.</span></span>
3. <span data-ttu-id="2803a-120">W polu Region kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2803a-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="2803a-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2803a-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="2803a-122">W polu Cena na galon wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="2803a-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="2803a-123">W polu Obowiązująca data i godzina rozpoczęcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="2803a-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="2803a-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2803a-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="2803a-125">Tworzenie indeksu paliwowego przewoźnika</span><span class="sxs-lookup"><span data-stu-id="2803a-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="2803a-126">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Indeksy paliwowe > Indeksy paliwowe przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="2803a-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="2803a-127">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2803a-127">Click New.</span></span>
3. <span data-ttu-id="2803a-128">W polu Indeks paliwa przewoźnika wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2803a-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="2803a-129">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="2803a-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2803a-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2803a-130">Click New.</span></span>
6. <span data-ttu-id="2803a-131">W polu Obowiązująca data i godzina rozpoczęcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="2803a-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="2803a-132">W polu Cena na galon od wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="2803a-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="2803a-133">W tym przykładzie w polu Cena na galon od ustawiono wartość 1,95.</span><span class="sxs-lookup"><span data-stu-id="2803a-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="2803a-134">W polu Cena na galon do wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="2803a-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="2803a-135">W tym przykładzie w polu Cena na galon do ustawiono wartość 2.</span><span class="sxs-lookup"><span data-stu-id="2803a-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="2803a-136">W polu Wartość procentowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="2803a-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="2803a-137">W tym przykładzie można ustawić procent 3.</span><span class="sxs-lookup"><span data-stu-id="2803a-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="2803a-138">W polu Waluta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2803a-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="2803a-139">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2803a-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="2803a-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2803a-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="2803a-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2803a-141">Click Save.</span></span>

