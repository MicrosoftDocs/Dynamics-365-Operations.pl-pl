---
title: Tworzenie zamówienia zakupu regulowanego budżetem
description: Ta procedura służy do tworzenia zamówienia zakupu sprawdzanego pod kątem dostępnego budżetu.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 100db102f74d477bcfde48a24828b817fd65e033
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239518"
---
# <a name="create-a-purchase-order-governed-by-budget"></a><span data-ttu-id="61e09-103">Tworzenie zamówienia zakupu regulowanego budżetem</span><span class="sxs-lookup"><span data-stu-id="61e09-103">Create a purchase order governed by budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61e09-104">Ta procedura służy do tworzenia zamówienia zakupu sprawdzanego pod kątem dostępnego budżetu.</span><span class="sxs-lookup"><span data-stu-id="61e09-104">Use this procedure to create a purchase order that is checked for available budget.</span></span> <span data-ttu-id="61e09-105">Nagranie wykorzystuje dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="61e09-105">This recording uses the USMF demo data company.</span></span>


## <a name="review-the-budget-control-configuration"></a><span data-ttu-id="61e09-106">Przeglądanie konfiguracji kontroli budżetu</span><span class="sxs-lookup"><span data-stu-id="61e09-106">Review the budget control configuration</span></span>
1. <span data-ttu-id="61e09-107">Wybierz kolejno opcje Budżetowanie > Ustawienia > Kontrola budżetu > Konfiguracja kontroli budżetu.</span><span class="sxs-lookup"><span data-stu-id="61e09-107">Go to Budgeting > Setup > Budget control > Budget control configuration.</span></span>
2. <span data-ttu-id="61e09-108">Kliknij kartę Dostępne środki budżetowe.</span><span class="sxs-lookup"><span data-stu-id="61e09-108">Click the Budget funds available tab.</span></span>
3. <span data-ttu-id="61e09-109">Kliknij kartę Dokumenty i arkusze.</span><span class="sxs-lookup"><span data-stu-id="61e09-109">Click the Documents and journals tab.</span></span>
4. <span data-ttu-id="61e09-110">Kliknij kartę Definiowanie reguł kontroli budżetu.</span><span class="sxs-lookup"><span data-stu-id="61e09-110">Click the Define budget control rules tab.</span></span>
5. <span data-ttu-id="61e09-111">Kliknij kartę Zdefiniuj grupy budżetu.</span><span class="sxs-lookup"><span data-stu-id="61e09-111">Click the Define budget groups tab.</span></span>
6. <span data-ttu-id="61e09-112">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="61e09-112">Close the page.</span></span>

## <a name="create-the-purchase-order-header"></a><span data-ttu-id="61e09-113">Tworzenie nagłówka zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="61e09-113">Create the purchase order header</span></span>
1. <span data-ttu-id="61e09-114">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="61e09-114">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="61e09-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="61e09-115">Click New.</span></span>
3. <span data-ttu-id="61e09-116">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61e09-116">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="61e09-117">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="61e09-117">Expand the General section.</span></span>
5. <span data-ttu-id="61e09-118">W polu Data księgowania ustaw datę „2016-01-01”.</span><span class="sxs-lookup"><span data-stu-id="61e09-118">In the Accounting date field, set the date to '2016-01-01'.</span></span>
6. <span data-ttu-id="61e09-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="61e09-119">Click OK.</span></span>

## <a name="add-a-purchase-order-line"></a><span data-ttu-id="61e09-120">Dodawanie wiersza zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="61e09-120">Add a purchase order line</span></span>
1. <span data-ttu-id="61e09-121">W polu Kategoria zaopatrzenia wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61e09-121">In the Procurement category field, enter or select a value.</span></span>
2. <span data-ttu-id="61e09-122">Ustaw ilość na 2.</span><span class="sxs-lookup"><span data-stu-id="61e09-122">Set Quantity to '2'.</span></span>
3. <span data-ttu-id="61e09-123">W polu Jednostka wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61e09-123">In the Unit field, enter or select a value.</span></span>
4. <span data-ttu-id="61e09-124">Ustaw cenę jednostkowa na „10000”.</span><span class="sxs-lookup"><span data-stu-id="61e09-124">Set Unit price to '10000'.</span></span>
5. <span data-ttu-id="61e09-125">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="61e09-125">Click Financials.</span></span>
6. <span data-ttu-id="61e09-126">Kliknij opcję Rozdziel kwoty.</span><span class="sxs-lookup"><span data-stu-id="61e09-126">Click Distribute amounts.</span></span>
7. <span data-ttu-id="61e09-127">W polu Konto księgowe wpisz wartość „601300-001-023--”.</span><span class="sxs-lookup"><span data-stu-id="61e09-127">In the Ledger account field, specify the value '601300-001-023--'.</span></span>
8. <span data-ttu-id="61e09-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="61e09-128">Close the page.</span></span>

## <a name="perform-budget-checking"></a><span data-ttu-id="61e09-129">Wykonaj kontrolę budżetu</span><span class="sxs-lookup"><span data-stu-id="61e09-129">Perform budget checking</span></span>
1. <span data-ttu-id="61e09-130">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="61e09-130">Click Financials.</span></span>
2. <span data-ttu-id="61e09-131">Kliknij opcję Wykonaj kontrolę budżetu.</span><span class="sxs-lookup"><span data-stu-id="61e09-131">Click Perform budget checking.</span></span>
3. <span data-ttu-id="61e09-132">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="61e09-132">Click Financials.</span></span>
4. <span data-ttu-id="61e09-133">Kliknij opcję Błędy lub ostrzeżenia dotyczące sprawdzania budżetu.</span><span class="sxs-lookup"><span data-stu-id="61e09-133">Click Budget check errors or warnings.</span></span>
5. <span data-ttu-id="61e09-134">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="61e09-134">Click Close.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]