--- 
title: "Definiowanie odrębnych grup zasobów produkcyjnych"
description: "Grupa zasobów to zbiór zasobów operacyjnych, które zazwyczaj odpowiadają fizycznej organizacji komórek roboczych zdefiniowanej przez żółte linie w wydziale produkcji."
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
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c2423fe91d1531a326080e3a584195ea864f2e3e
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="1d366-103">Definiowanie odrębnych grup zasobów produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="1d366-103">Define discrete manufacturing resource group</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1d366-104">Grupa zasobów to zbiór zasobów operacyjnych, które zazwyczaj odpowiadają fizycznej organizacji komórek roboczych zdefiniowanej przez żółte linie w wydziale produkcji.</span><span class="sxs-lookup"><span data-stu-id="1d366-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="1d366-105">W tej procedurze pokazano sposób definiowania grupy zasobów do wykorzystania w produkcji dyskretnej.</span><span class="sxs-lookup"><span data-stu-id="1d366-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="1d366-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="1d366-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="1d366-107">Przejdź do okna Grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="1d366-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="1d366-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1d366-108">Click New.</span></span>
3. <span data-ttu-id="1d366-109">W polu Grupa zasobów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d366-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="1d366-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="1d366-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1d366-111">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d366-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="1d366-112">W polu Jednostka produkcyjna wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d366-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="1d366-113">Definiowanie domyślnych parametrów operacyjnych</span><span class="sxs-lookup"><span data-stu-id="1d366-113">Define default operational parameters</span></span>
1. <span data-ttu-id="1d366-114">Rozwiń sekcję Operacja.</span><span class="sxs-lookup"><span data-stu-id="1d366-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="1d366-115">W polu Procent odpadków wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1d366-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="1d366-116">W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d366-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="1d366-117">W polu Kategoria czasu procesu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d366-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="1d366-118">W polu Planowanie operacji — procent wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1d366-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="1d366-119">Definiowanie godzin pracy</span><span class="sxs-lookup"><span data-stu-id="1d366-119">Define operating hours</span></span>
1. <span data-ttu-id="1d366-120">Rozwiń sekcję Kalendarze.</span><span class="sxs-lookup"><span data-stu-id="1d366-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="1d366-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1d366-121">Click Add.</span></span>
3. <span data-ttu-id="1d366-122">W polu Kalendarz wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d366-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="1d366-123">Dodawanie zasobów operacyjnych</span><span class="sxs-lookup"><span data-stu-id="1d366-123">Add operations resources</span></span>
1. <span data-ttu-id="1d366-124">Rozwiń sekcję Zasoby.</span><span class="sxs-lookup"><span data-stu-id="1d366-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="1d366-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1d366-125">Click Add.</span></span>
3. <span data-ttu-id="1d366-126">W polu Zasób wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d366-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="1d366-127">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1d366-127">Click Add.</span></span>
5. <span data-ttu-id="1d366-128">W polu Zasób wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d366-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="1d366-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1d366-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="1d366-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1d366-130">In the list, click the link in the selected row.</span></span>


