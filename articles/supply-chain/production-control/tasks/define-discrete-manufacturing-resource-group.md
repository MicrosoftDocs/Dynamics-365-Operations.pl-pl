---
title: Definiowanie odrębnych grup zasobów produkcyjnych
description: Grupa zasobów to zbiór zasobów operacyjnych, które zazwyczaj odpowiadają fizycznej organizacji komórek roboczych zdefiniowanej przez żółte linie w wydziale produkcji.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40a0638662cbace147aeb24bd20d3ae34a0c1670
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837678"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="1733d-103">Definiowanie odrębnych grup zasobów produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="1733d-103">Define discrete manufacturing resource group</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1733d-104">Grupa zasobów to zbiór zasobów operacyjnych, które zazwyczaj odpowiadają fizycznej organizacji komórek roboczych zdefiniowanej przez żółte linie w wydziale produkcji.</span><span class="sxs-lookup"><span data-stu-id="1733d-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="1733d-105">W tej procedurze pokazano sposób definiowania grupy zasobów do wykorzystania w produkcji dyskretnej.</span><span class="sxs-lookup"><span data-stu-id="1733d-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="1733d-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="1733d-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="1733d-107">Przejdź do okna Grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="1733d-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="1733d-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1733d-108">Click New.</span></span>
3. <span data-ttu-id="1733d-109">W polu Grupa zasobów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1733d-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="1733d-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="1733d-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1733d-111">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1733d-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="1733d-112">W polu Jednostka produkcyjna wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1733d-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="1733d-113">Definiowanie domyślnych parametrów operacyjnych</span><span class="sxs-lookup"><span data-stu-id="1733d-113">Define default operational parameters</span></span>
1. <span data-ttu-id="1733d-114">Rozwiń sekcję Operacja.</span><span class="sxs-lookup"><span data-stu-id="1733d-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="1733d-115">W polu Procent odpadków wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1733d-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="1733d-116">W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1733d-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="1733d-117">W polu Kategoria czasu procesu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1733d-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="1733d-118">W polu Planowanie operacji — procent wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1733d-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="1733d-119">Definiowanie godzin pracy</span><span class="sxs-lookup"><span data-stu-id="1733d-119">Define operating hours</span></span>
1. <span data-ttu-id="1733d-120">Rozwiń sekcję Kalendarze.</span><span class="sxs-lookup"><span data-stu-id="1733d-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="1733d-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1733d-121">Click Add.</span></span>
3. <span data-ttu-id="1733d-122">W polu Kalendarz wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1733d-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="1733d-123">Dodawanie zasobów operacyjnych</span><span class="sxs-lookup"><span data-stu-id="1733d-123">Add operations resources</span></span>
1. <span data-ttu-id="1733d-124">Rozwiń sekcję Zasoby.</span><span class="sxs-lookup"><span data-stu-id="1733d-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="1733d-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1733d-125">Click Add.</span></span>
3. <span data-ttu-id="1733d-126">W polu Zasób wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1733d-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="1733d-127">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1733d-127">Click Add.</span></span>
5. <span data-ttu-id="1733d-128">W polu Zasób wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1733d-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="1733d-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1733d-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="1733d-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1733d-130">In the list, click the link in the selected row.</span></span>

