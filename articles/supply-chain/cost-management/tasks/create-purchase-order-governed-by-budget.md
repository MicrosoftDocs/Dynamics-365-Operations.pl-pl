---
title: Tworzenie zamówienia zakupu regulowanego budżetem
description: Ta procedura służy do tworzenia zamówienia zakupu sprawdzanego pod kątem dostępnego budżetu.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0054745394d6a21599d8f07605f78ffdd7f575ab
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150546"
---
# <a name="create-a-purchase-order-governed-by-budget"></a><span data-ttu-id="0d4ff-103">Tworzenie zamówienia zakupu regulowanego budżetem</span><span class="sxs-lookup"><span data-stu-id="0d4ff-103">Create a purchase order governed by budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0d4ff-104">Ta procedura służy do tworzenia zamówienia zakupu sprawdzanego pod kątem dostępnego budżetu.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-104">Use this procedure to create a purchase order that is checked for available budget.</span></span> <span data-ttu-id="0d4ff-105">Nagranie wykorzystuje dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-105">This recording uses the USMF demo data company.</span></span>


## <a name="review-the-budget-control-configuration"></a><span data-ttu-id="0d4ff-106">Przeglądanie konfiguracji kontroli budżetu</span><span class="sxs-lookup"><span data-stu-id="0d4ff-106">Review the budget control configuration</span></span>
1. <span data-ttu-id="0d4ff-107">Wybierz kolejno opcje Budżetowanie > Ustawienia > Kontrola budżetu > Konfiguracja kontroli budżetu.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-107">Go to Budgeting > Setup > Budget control > Budget control configuration.</span></span>
2. <span data-ttu-id="0d4ff-108">Kliknij kartę Dostępne środki budżetowe.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-108">Click the Budget funds available tab.</span></span>
3. <span data-ttu-id="0d4ff-109">Kliknij kartę Dokumenty i arkusze.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-109">Click the Documents and journals tab.</span></span>
4. <span data-ttu-id="0d4ff-110">Kliknij kartę Definiowanie reguł kontroli budżetu.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-110">Click the Define budget control rules tab.</span></span>
5. <span data-ttu-id="0d4ff-111">Kliknij kartę Zdefiniuj grupy budżetu.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-111">Click the Define budget groups tab.</span></span>
6. <span data-ttu-id="0d4ff-112">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-112">Close the page.</span></span>

## <a name="create-the-purchase-order-header"></a><span data-ttu-id="0d4ff-113">Tworzenie nagłówka zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="0d4ff-113">Create the purchase order header</span></span>
1. <span data-ttu-id="0d4ff-114">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-114">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="0d4ff-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-115">Click New.</span></span>
3. <span data-ttu-id="0d4ff-116">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-116">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="0d4ff-117">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-117">Expand the General section.</span></span>
5. <span data-ttu-id="0d4ff-118">W polu Data księgowania ustaw datę „2016-01-01”.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-118">In the Accounting date field, set the date to '2016-01-01'.</span></span>
6. <span data-ttu-id="0d4ff-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-119">Click OK.</span></span>

## <a name="add-a-purchase-order-line"></a><span data-ttu-id="0d4ff-120">Dodawanie wiersza zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="0d4ff-120">Add a purchase order line</span></span>
1. <span data-ttu-id="0d4ff-121">W polu Kategoria zaopatrzenia wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-121">In the Procurement category field, enter or select a value.</span></span>
2. <span data-ttu-id="0d4ff-122">Ustaw ilość na 2.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-122">Set Quantity to '2'.</span></span>
3. <span data-ttu-id="0d4ff-123">W polu Jednostka wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-123">In the Unit field, enter or select a value.</span></span>
4. <span data-ttu-id="0d4ff-124">Ustaw cenę jednostkowa na „10000”.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-124">Set Unit price to '10000'.</span></span>
5. <span data-ttu-id="0d4ff-125">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-125">Click Financials.</span></span>
6. <span data-ttu-id="0d4ff-126">Kliknij opcję Rozdziel kwoty.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-126">Click Distribute amounts.</span></span>
7. <span data-ttu-id="0d4ff-127">W polu Konto księgowe wpisz wartość „601300-001-023--”.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-127">In the Ledger account field, specify the value '601300-001-023--'.</span></span>
8. <span data-ttu-id="0d4ff-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-128">Close the page.</span></span>

## <a name="perform-budget-checking"></a><span data-ttu-id="0d4ff-129">Wykonaj kontrolę budżetu</span><span class="sxs-lookup"><span data-stu-id="0d4ff-129">Perform budget checking</span></span>
1. <span data-ttu-id="0d4ff-130">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-130">Click Financials.</span></span>
2. <span data-ttu-id="0d4ff-131">Kliknij opcję Wykonaj kontrolę budżetu.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-131">Click Perform budget checking.</span></span>
3. <span data-ttu-id="0d4ff-132">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-132">Click Financials.</span></span>
4. <span data-ttu-id="0d4ff-133">Kliknij opcję Błędy lub ostrzeżenia dotyczące sprawdzania budżetu.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-133">Click Budget check errors or warnings.</span></span>
5. <span data-ttu-id="0d4ff-134">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="0d4ff-134">Click Close.</span></span>

