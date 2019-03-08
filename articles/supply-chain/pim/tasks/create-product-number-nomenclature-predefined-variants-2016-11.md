---
title: Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu
description: Ten przewodnik pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "364886"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="b6d61-103">Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="b6d61-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b6d61-104">Ten przewodnik pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="b6d61-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="b6d61-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b6d61-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="b6d61-106">Nowa konwencja nazewnictwa numerów produktu jest przypisana do grupy wymiarów koloru i rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="b6d61-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="b6d61-107">Zazwyczaj zadanie wykonuje projektant produktów.</span><span class="sxs-lookup"><span data-stu-id="b6d61-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="b6d61-108">Tworzenie konwencji nazewnictwa numerów produktu</span><span class="sxs-lookup"><span data-stu-id="b6d61-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="b6d61-109">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="b6d61-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="b6d61-110">Kliknij opcję Nazewnictwo produktów.</span><span class="sxs-lookup"><span data-stu-id="b6d61-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="b6d61-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b6d61-111">Click New.</span></span>
4. <span data-ttu-id="b6d61-112">W polu Nazwa wprowadź nazwę konwencji nazewnictwa, która pomoże w identyfikacji docelowej grupy wymiarów produktu, na przykład KolorRozmiar.</span><span class="sxs-lookup"><span data-stu-id="b6d61-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="b6d61-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="b6d61-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="b6d61-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b6d61-114">Click Add.</span></span>
7. <span data-ttu-id="b6d61-115">Kliknij opcję Numer produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="b6d61-115">Click Product master number.</span></span>
8. <span data-ttu-id="b6d61-116">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b6d61-116">Click Add.</span></span>
9. <span data-ttu-id="b6d61-117">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="b6d61-117">Click Text constant.</span></span>
10. <span data-ttu-id="b6d61-118">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b6d61-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="b6d61-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b6d61-119">Click Add.</span></span>
12. <span data-ttu-id="b6d61-120">Kliknij opcję Kolor.</span><span class="sxs-lookup"><span data-stu-id="b6d61-120">Click Color.</span></span>
13. <span data-ttu-id="b6d61-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b6d61-121">Click Add.</span></span>
14. <span data-ttu-id="b6d61-122">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="b6d61-122">Click Text constant.</span></span>
15. <span data-ttu-id="b6d61-123">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b6d61-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="b6d61-124">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b6d61-124">Click Add.</span></span>
17. <span data-ttu-id="b6d61-125">Kliknij opcję Rozmiar.</span><span class="sxs-lookup"><span data-stu-id="b6d61-125">Click Size.</span></span>
18. <span data-ttu-id="b6d61-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b6d61-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="b6d61-127">Przypisywanie konwencji nazewnictwa do produktu głównego</span><span class="sxs-lookup"><span data-stu-id="b6d61-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="b6d61-128">Kliknij opcję Grupy wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="b6d61-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="b6d61-129">Zaznacz grupę wymiarów produktu SizeCol.</span><span class="sxs-lookup"><span data-stu-id="b6d61-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="b6d61-130">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="b6d61-130">Click Edit.</span></span>
4. <span data-ttu-id="b6d61-131">W polu Użyj nazewnictwa zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b6d61-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="b6d61-132">W polu Nazewnictwo numerów wariantów produktu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b6d61-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="b6d61-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b6d61-133">Close the page.</span></span>

