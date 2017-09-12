--- 
title: "Zarządzanie jednostką miary"
description: "W tej procedurze pokazano sposób definiowania jednostki miary, wprowadzania tłumaczenia i opisu jednostki oraz określania reguł konwersji względem powiązanych jednostek."
author: sorenva
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
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6bb7a5133e9412f4ed6fb74f0d3ee595c07a0c4b
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="09b39-103">Zarządzanie jednostką miary</span><span class="sxs-lookup"><span data-stu-id="09b39-103">Manage unit of measure</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="09b39-104">W tej procedurze pokazano sposób definiowania jednostki miary, wprowadzania tłumaczenia i opisu jednostki oraz określania reguł konwersji względem powiązanych jednostek.</span><span class="sxs-lookup"><span data-stu-id="09b39-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="09b39-105">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="09b39-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="09b39-106">Przejdź do okna Obsługa zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="09b39-106">Go to Released product maintenance.</span></span>
2. <span data-ttu-id="09b39-107">Kliknij opcję Jednostki.</span><span class="sxs-lookup"><span data-stu-id="09b39-107">Click Units.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="09b39-108">Tworzenie jednostki miary</span><span class="sxs-lookup"><span data-stu-id="09b39-108">Create a unit of measure</span></span>
1. <span data-ttu-id="09b39-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="09b39-109">Click New.</span></span>
2. <span data-ttu-id="09b39-110">W polu Jednostka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="09b39-110">In the Unit field, type a value.</span></span>
    * <span data-ttu-id="09b39-111">Wprowadź identyfikator lub symbol, który ma być używany przy odwoływaniu się do jednostki miary.</span><span class="sxs-lookup"><span data-stu-id="09b39-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="09b39-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="09b39-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="09b39-113">Wprowadź opisową nazwę jednostki miary w wersji językowej systemu.</span><span class="sxs-lookup"><span data-stu-id="09b39-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="09b39-114">W polu Klasa jednostek wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="09b39-114">In the Unit class field, select an option.</span></span>
    * <span data-ttu-id="09b39-115">Klasa jednostki określa grupę logiczną, taką jak obszar, masa lub ilość, której jednostka miary jest częścią.</span><span class="sxs-lookup"><span data-stu-id="09b39-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="09b39-116">W polu Dokładność po przecinku wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="09b39-116">In the Decimal precision field, enter a number.</span></span>
    * <span data-ttu-id="09b39-117">Określ liczbę miejsc po przecinku, do jakiej musi zostać zaokrąglona przekonwertowana jednostka miary po wykonaniu na niej obliczeń.</span><span class="sxs-lookup"><span data-stu-id="09b39-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="09b39-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="09b39-118">Click Save.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="09b39-119">Definiowanie tłumaczeń jednostek</span><span class="sxs-lookup"><span data-stu-id="09b39-119">Define unit translations</span></span>
1. <span data-ttu-id="09b39-120">Kliknij opcję Opisy jednostek.</span><span class="sxs-lookup"><span data-stu-id="09b39-120">Click Unit texts.</span></span>
2. <span data-ttu-id="09b39-121">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="09b39-121">Click New.</span></span>
    * <span data-ttu-id="09b39-122">Użyj opisu jednostki w celu utworzenia tłumaczenie identyfikatora lub symbolu reprezentującego jednostkę miary z przeznaczeniem do używania w dokumentach zewnętrznych w językach określonych odbiorców lub dostawców.</span><span class="sxs-lookup"><span data-stu-id="09b39-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="09b39-123">W polu Język wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="09b39-123">In the Language field, enter or select a value.</span></span>
4. <span data-ttu-id="09b39-124">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="09b39-124">In the Text field, type a value.</span></span>
5. <span data-ttu-id="09b39-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="09b39-125">Click Save.</span></span>
6. <span data-ttu-id="09b39-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="09b39-126">Close the page.</span></span>
7. <span data-ttu-id="09b39-127">Kliknij opcję Przetłumaczone opisy jednostki.</span><span class="sxs-lookup"><span data-stu-id="09b39-127">Click Translated unit descriptions.</span></span>
8. <span data-ttu-id="09b39-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="09b39-128">Click New.</span></span>
    * <span data-ttu-id="09b39-129">Utwórz opisy jednostki miary w różnych językach.</span><span class="sxs-lookup"><span data-stu-id="09b39-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="09b39-130">W polu Język wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="09b39-130">In the Language field, enter or select a value.</span></span>
10. <span data-ttu-id="09b39-131">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="09b39-131">In the Description field, type a value.</span></span>
11. <span data-ttu-id="09b39-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="09b39-132">Click Save.</span></span>
12. <span data-ttu-id="09b39-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="09b39-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="09b39-134">Definiowanie reguł konwersji jednostek</span><span class="sxs-lookup"><span data-stu-id="09b39-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="09b39-135">Kliknij opcję Konwersje jednostek.</span><span class="sxs-lookup"><span data-stu-id="09b39-135">Click Unit conversions.</span></span>
    * <span data-ttu-id="09b39-136">Zdefiniuj reguły konwersji jednostki miary na i z innych jednostek miary w wybranej klasie jednostek.</span><span class="sxs-lookup"><span data-stu-id="09b39-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="09b39-137">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="09b39-137">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="09b39-138">W polu Współczynnik wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="09b39-138">In the Factor field, enter a number.</span></span>
    * <span data-ttu-id="09b39-139">Wskaźnik konwersji między jednostkami źródłową i docelową.</span><span class="sxs-lookup"><span data-stu-id="09b39-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="09b39-140">Na przykład współczynnik konwersji centymetra na metr wynosi 100, ponieważ w jednym metrze jest 100 centymetrów.</span><span class="sxs-lookup"><span data-stu-id="09b39-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="09b39-141">W polu Do jednostki wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="09b39-141">In the To unit field, enter or select a value.</span></span>
5. <span data-ttu-id="09b39-142">W polu Zaokrąglanie wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="09b39-142">In the Rounding field, select an option.</span></span>
    * <span data-ttu-id="09b39-143">Określ sposób zaokrąglania skonwertowanej wartości.</span><span class="sxs-lookup"><span data-stu-id="09b39-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="09b39-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="09b39-144">Click OK.</span></span>
7. <span data-ttu-id="09b39-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="09b39-145">Close the page.</span></span>


