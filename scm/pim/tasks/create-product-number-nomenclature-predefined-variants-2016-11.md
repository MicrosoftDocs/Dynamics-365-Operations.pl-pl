--- 
title: "Tworzenie numeru produktu dla wstępnie zdefiniowanych wariantów produktu"
description: "Ten przewodnik pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu."
author: BibiSp
manager: AnnBe
ms.date: 09/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6294e4608b31c37aa713e3a7a2028b409b5a8366
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a><span data-ttu-id="eba98-103">Tworzenie numeru produktu dla wstępnie zdefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="eba98-103">Create a product number for predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eba98-104">Ten przewodnik pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="eba98-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="eba98-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="eba98-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="eba98-106">Nowa konwencja nazewnictwa numerów produktu jest przypisana do grupy wymiarów koloru i rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="eba98-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="eba98-107">Zazwyczaj zadanie wykonuje projektant produktów.</span><span class="sxs-lookup"><span data-stu-id="eba98-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="eba98-108">Tworzenie konwencji nazewnictwa numerów produktu</span><span class="sxs-lookup"><span data-stu-id="eba98-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="eba98-109">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="eba98-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="eba98-110">Kliknij opcję Nazewnictwo produktów.</span><span class="sxs-lookup"><span data-stu-id="eba98-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="eba98-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="eba98-111">Click New.</span></span>
4. <span data-ttu-id="eba98-112">W polu Nazwa wprowadź nazwę konwencji nazewnictwa, która pomoże w identyfikacji docelowej grupy wymiarów produktu, na przykład KolorRozmiar.</span><span class="sxs-lookup"><span data-stu-id="eba98-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="eba98-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="eba98-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="eba98-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="eba98-114">Click Add.</span></span>
7. <span data-ttu-id="eba98-115">Kliknij opcję Numer produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="eba98-115">Click Product master number.</span></span>
8. <span data-ttu-id="eba98-116">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="eba98-116">Click Add.</span></span>
9. <span data-ttu-id="eba98-117">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="eba98-117">Click Text constant.</span></span>
10. <span data-ttu-id="eba98-118">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="eba98-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="eba98-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="eba98-119">Click Add.</span></span>
12. <span data-ttu-id="eba98-120">Kliknij opcję Kolor.</span><span class="sxs-lookup"><span data-stu-id="eba98-120">Click Color.</span></span>
13. <span data-ttu-id="eba98-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="eba98-121">Click Add.</span></span>
14. <span data-ttu-id="eba98-122">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="eba98-122">Click Text constant.</span></span>
15. <span data-ttu-id="eba98-123">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="eba98-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="eba98-124">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="eba98-124">Click Add.</span></span>
17. <span data-ttu-id="eba98-125">Kliknij opcję Rozmiar.</span><span class="sxs-lookup"><span data-stu-id="eba98-125">Click Size.</span></span>
18. <span data-ttu-id="eba98-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="eba98-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="eba98-127">Przypisywanie konwencji nazewnictwa do produktu głównego</span><span class="sxs-lookup"><span data-stu-id="eba98-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="eba98-128">Kliknij opcję Grupy wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="eba98-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="eba98-129">Zaznacz grupę wymiarów produktu SizeCol.</span><span class="sxs-lookup"><span data-stu-id="eba98-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="eba98-130">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="eba98-130">Click Edit.</span></span>
4. <span data-ttu-id="eba98-131">W polu Użyj nazewnictwa zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="eba98-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="eba98-132">W polu Nazewnictwo numerów wariantów produktu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="eba98-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="eba98-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="eba98-133">Close the page.</span></span>


