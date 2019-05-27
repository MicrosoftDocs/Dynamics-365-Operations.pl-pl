---
title: Znajdowanie przestarzałych wariantów produktów
description: Ta procedura przedstawia, jak znaleźć przestarzałe zwolnione produkty lub warianty produktów i skojarzyć stan cyklu życia produktu z przestarzałymi produktami.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4641d24cfa24722f5411da8943bfe4095a9546a4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567637"
---
# <a name="find-obsolete-product-variants"></a><span data-ttu-id="1dfd4-103">Znajdowanie przestarzałych wariantów produktów</span><span class="sxs-lookup"><span data-stu-id="1dfd4-103">Find obsolete product variants</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1dfd4-104">Ta procedura przedstawia, jak znaleźć przestarzałe zwolnione produkty lub warianty produktów i skojarzyć stan cyklu życia produktu z przestarzałymi produktami.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-104">This procedure shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="1dfd4-105">Warunek wstępny: przed przystąpieniem do procedury opisanej w tym przewodniku zadania należy zdefiniować co najmniej jeden stan cyklu życia produktu nieaktywny dla planowania.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-105">Prerequisite: You need to define at least one product lifecycle state that is inactive for planning before you can play this task guide.</span></span>


## <a name="run-a-simulation"></a><span data-ttu-id="1dfd4-106">Uruchamianie symulacji</span><span class="sxs-lookup"><span data-stu-id="1dfd4-106">Run a simulation</span></span>
1. <span data-ttu-id="1dfd4-107">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Zadania okresowe > Zmiana stanu cyklu życia dla produktów przestarzałych.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-107">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
2. <span data-ttu-id="1dfd4-108">W polu Stan cyklu życia nowego produktu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-108">In the New product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="1dfd4-109">W polu Uruchom symulację bez aktualizowania danych produktów zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-109">Select Yes in the Run simulation without updating product data field.</span></span>
4. <span data-ttu-id="1dfd4-110">W polu Wyklucz produkty utworzone w ciągu tej liczby dni wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-110">In the Exclude products created within this number of days field, enter a number.</span></span>
5. <span data-ttu-id="1dfd4-111">W polu Wyklucz produkty użyte w transakcjach (w ciągu tej liczby dni) wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-111">In the Exclude products used in transactions (in number of days) field, enter a number.</span></span>
6. <span data-ttu-id="1dfd4-112">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-112">Expand the Records to include section.</span></span>
7. <span data-ttu-id="1dfd4-113">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-113">Click Filter.</span></span>
8. <span data-ttu-id="1dfd4-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-114">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="1dfd4-115">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-115">In the Criteria field, type a value.</span></span>
10. <span data-ttu-id="1dfd4-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-116">Click OK.</span></span>
11. <span data-ttu-id="1dfd4-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-117">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="1dfd4-118">Jeśli wyszukiwanie obejmie dużą liczbę produktów, zaleca się uruchamianie symulacji partiami.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-118">It is recommended to run the simulation in batch if you expect to search a large number of products.</span></span> <span data-ttu-id="1dfd4-119">Nie należy również uruchamiać symulacji w okresie największej aktywności w firmie.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-119">Also, make sure that the simulation is not run during the most active working time of the company.</span></span>  

## <a name="review-the-simulation-results"></a><span data-ttu-id="1dfd4-120">Przegląd wyników symulacji</span><span class="sxs-lookup"><span data-stu-id="1dfd4-120">Review the simulation results</span></span>
1. <span data-ttu-id="1dfd4-121">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Zapytania i raporty > Historia obsługi stanu cyklu życia produktów.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-121">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>
   
> [!NOTE]
> <span data-ttu-id="1dfd4-122">Na tej stronie można również sprawdzić, jak wyświetlić wyniki symulacji i ocenić, ile produktów i wariantów produktów będzie skojarzonych z nowym stanem cyklu życia produktu po uruchomieniu aktualizacji bez symulacji.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-122">On this page, you can review the simulation results and make an assessment of how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a><span data-ttu-id="1dfd4-123">Uruchamianie aktualizacji stanu cyklu życia produktu dla produktów przestarzałych</span><span class="sxs-lookup"><span data-stu-id="1dfd4-123">Run the update of the Product lifecycle state for obsolete products</span></span>
1. <span data-ttu-id="1dfd4-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-124">Close the page.</span></span>
2. <span data-ttu-id="1dfd4-125">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Zadania okresowe > Zmiana stanu cyklu życia dla produktów przestarzałych.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-125">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
3. <span data-ttu-id="1dfd4-126">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-126">Expand the Records to include section.</span></span>

> [!NOTE]
> <span data-ttu-id="1dfd4-127">Należy zauważyć, że ostatni wybór został zapisany.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-127">Note that the last selection has been saved.</span></span>  

4. <span data-ttu-id="1dfd4-128">W polu Uruchom symulację bez aktualizowania danych produktów zaznacz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-128">Select No in the Run simulation without updating product data field.</span></span>
5. <span data-ttu-id="1dfd4-129">Rozwiń sekcję Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-129">Expand the Run in the background section.</span></span>

> [!NOTE]
> <span data-ttu-id="1dfd4-130">W zależności od liczby produktów i wariantów produktów, których dotyczy operacja, należy rozważyć uruchamianie zadania partiami.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-130">Depending on how many products and product variants are affected, consider running this job in batch.</span></span> <span data-ttu-id="1dfd4-131">Nie należy uruchamiać dużego zadania aktualizacji w okresie największej aktywności w firmie.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-131">Make sure that you are not running a large update job during the most active working hours in the company.</span></span>  

6. <span data-ttu-id="1dfd4-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-132">Click OK.</span></span>
7. <span data-ttu-id="1dfd4-133">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Zapytania i raporty > Historia obsługi stanu cyklu życia produktów.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-133">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>

> [!NOTE]
> <span data-ttu-id="1dfd4-134">Sprawdź zwolnione produkty i warianty produktów, które zostały zmienione.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-134">Review the changed released products and product variants.</span></span>  

8. <span data-ttu-id="1dfd4-135">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1dfd4-135">In the list, find and select the desired record.</span></span>

