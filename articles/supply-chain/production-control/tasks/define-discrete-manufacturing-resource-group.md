---
title: Definiowanie odrębnych grup zasobów produkcyjnych
description: Grupa zasobów to zbiór zasobów operacyjnych, które zazwyczaj odpowiadają fizycznej organizacji komórek roboczych zdefiniowanej przez żółte linie w wydziale produkcji.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eaccb566c04d6d4b91ea8cb046931e750a4c6eed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434927"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="9794c-103">Definiowanie odrębnych grup zasobów produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="9794c-103">Define discrete manufacturing resource group</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9794c-104">Grupa zasobów to zbiór zasobów operacyjnych, które zazwyczaj odpowiadają fizycznej organizacji komórek roboczych zdefiniowanej przez żółte linie w wydziale produkcji.</span><span class="sxs-lookup"><span data-stu-id="9794c-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="9794c-105">W tej procedurze pokazano sposób definiowania grupy zasobów do wykorzystania w produkcji dyskretnej.</span><span class="sxs-lookup"><span data-stu-id="9794c-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="9794c-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="9794c-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="9794c-107">Przejdź do okna Grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="9794c-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="9794c-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="9794c-108">Click New.</span></span>
3. <span data-ttu-id="9794c-109">W polu Grupa zasobów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9794c-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="9794c-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="9794c-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9794c-111">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9794c-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="9794c-112">W polu Jednostka produkcyjna wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9794c-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="9794c-113">Definiowanie domyślnych parametrów operacyjnych</span><span class="sxs-lookup"><span data-stu-id="9794c-113">Define default operational parameters</span></span>
1. <span data-ttu-id="9794c-114">Rozwiń sekcję Operacja.</span><span class="sxs-lookup"><span data-stu-id="9794c-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="9794c-115">W polu Procent odpadków wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="9794c-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="9794c-116">W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9794c-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="9794c-117">W polu Kategoria czasu procesu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9794c-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="9794c-118">W polu Planowanie operacji — procent wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="9794c-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="9794c-119">Definiowanie godzin pracy</span><span class="sxs-lookup"><span data-stu-id="9794c-119">Define operating hours</span></span>
1. <span data-ttu-id="9794c-120">Rozwiń sekcję Kalendarze.</span><span class="sxs-lookup"><span data-stu-id="9794c-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="9794c-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9794c-121">Click Add.</span></span>
3. <span data-ttu-id="9794c-122">W polu Kalendarz wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9794c-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="9794c-123">Dodawanie zasobów operacyjnych</span><span class="sxs-lookup"><span data-stu-id="9794c-123">Add operations resources</span></span>
1. <span data-ttu-id="9794c-124">Rozwiń sekcję Zasoby.</span><span class="sxs-lookup"><span data-stu-id="9794c-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="9794c-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9794c-125">Click Add.</span></span>
3. <span data-ttu-id="9794c-126">W polu Zasób wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9794c-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="9794c-127">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9794c-127">Click Add.</span></span>
5. <span data-ttu-id="9794c-128">W polu Zasób wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9794c-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="9794c-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9794c-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="9794c-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9794c-130">In the list, click the link in the selected row.</span></span>

