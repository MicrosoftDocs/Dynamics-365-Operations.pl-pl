---
title: Definiowanie odrębnych grup zasobów produkcyjnych
description: Grupa zasobów to zbiór zasobów operacyjnych, które zazwyczaj odpowiadają fizycznej organizacji komórek roboczych zdefiniowanej przez żółte linie w wydziale produkcji.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95a8e1c6daa78250118a8a16010ef4cc1b1ae693
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811541"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="f280a-103">Definiowanie odrębnych grup zasobów produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="f280a-103">Define discrete manufacturing resource group</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f280a-104">Grupa zasobów to zbiór zasobów operacyjnych, które zazwyczaj odpowiadają fizycznej organizacji komórek roboczych zdefiniowanej przez żółte linie w wydziale produkcji.</span><span class="sxs-lookup"><span data-stu-id="f280a-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="f280a-105">W tej procedurze pokazano sposób definiowania grupy zasobów do wykorzystania w produkcji dyskretnej.</span><span class="sxs-lookup"><span data-stu-id="f280a-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="f280a-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="f280a-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="f280a-107">Przejdź do okna Grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="f280a-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="f280a-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f280a-108">Click New.</span></span>
3. <span data-ttu-id="f280a-109">W polu Grupa zasobów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f280a-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="f280a-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="f280a-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f280a-111">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f280a-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="f280a-112">W polu Jednostka produkcyjna wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f280a-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="f280a-113">Definiowanie domyślnych parametrów operacyjnych</span><span class="sxs-lookup"><span data-stu-id="f280a-113">Define default operational parameters</span></span>
1. <span data-ttu-id="f280a-114">Rozwiń sekcję Operacja.</span><span class="sxs-lookup"><span data-stu-id="f280a-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="f280a-115">W polu Procent odpadków wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="f280a-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="f280a-116">W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f280a-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="f280a-117">W polu Kategoria czasu procesu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f280a-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="f280a-118">W polu Planowanie operacji — procent wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="f280a-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="f280a-119">Definiowanie godzin pracy</span><span class="sxs-lookup"><span data-stu-id="f280a-119">Define operating hours</span></span>
1. <span data-ttu-id="f280a-120">Rozwiń sekcję Kalendarze.</span><span class="sxs-lookup"><span data-stu-id="f280a-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="f280a-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f280a-121">Click Add.</span></span>
3. <span data-ttu-id="f280a-122">W polu Kalendarz wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f280a-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="f280a-123">Dodawanie zasobów operacyjnych</span><span class="sxs-lookup"><span data-stu-id="f280a-123">Add operations resources</span></span>
1. <span data-ttu-id="f280a-124">Rozwiń sekcję Zasoby.</span><span class="sxs-lookup"><span data-stu-id="f280a-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="f280a-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f280a-125">Click Add.</span></span>
3. <span data-ttu-id="f280a-126">W polu Zasób wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f280a-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="f280a-127">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f280a-127">Click Add.</span></span>
5. <span data-ttu-id="f280a-128">W polu Zasób wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f280a-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="f280a-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f280a-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="f280a-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f280a-130">In the list, click the link in the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]