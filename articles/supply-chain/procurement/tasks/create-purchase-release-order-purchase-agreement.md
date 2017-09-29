--- 
title: "Tworzenie zlecenia wydania zakupu na podstawie umów zakupu"
description: "W tej procedurze pokazano sposób korzystania z umowy zakupu podczas tworzenia zamówienia zakupu."
author: mkirknel
manager: AnnBe
ms.date: 12/04/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: cecda03dd4d224d4319f2b0b196560389bb54195
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a><span data-ttu-id="a6aa7-103">Tworzenie zlecenia wydania zakupu na podstawie umów zakupu</span><span class="sxs-lookup"><span data-stu-id="a6aa7-103">Create a purchase release order from a purchase agreement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a6aa7-104">W tej procedurze pokazano sposób korzystania z umowy zakupu podczas tworzenia zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-104">This procedure shows how to use a purchase agreement when you create a purchase order.</span></span> <span data-ttu-id="a6aa7-105">Umowa zakupu musi być stosowana podczas tworzenia zamówienia zakupu, ponieważ istnieją ogólne warunki, które powinny być skopiowane do nagłówka zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-105">The purchase agreement has to be applied when you create the purchase order because there are general terms that should be copied to the purchase order header.</span></span> <span data-ttu-id="a6aa7-106">To zadanie zazwyczaj wykonuje pracownik działu zakupów.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-106">Typically this task would be carried out by a purchasing agent.</span></span> <span data-ttu-id="a6aa7-107">Warunkiem wstępnym wykonania zadań z tego przewodnika jest istnienie ważnej umowy zakupu ze zobowiązaniem co do ilości produktu dla dostawcy i towarów.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-107">As a prerequisite for this guide, you must have an effective purchase agreement with a product quantity commitment for a vendor and items.</span></span> <span data-ttu-id="a6aa7-108">Tej samej procedury można użyć w przypadku umowy zakupu z innymi typami zobowiązań.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-108">The same procedure can be used if you have a purchase agreement with other types of commitments.</span></span> <span data-ttu-id="a6aa7-109">Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-109">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="a6aa7-110">Jeśli używasz firmy USMF, można najpierw wykonać zadania z przewodnika „Tworzenie umowy zakupu” i skonfigurować warunki wstępne konieczne dla tego przewodnika.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-110">If you’re using USMF, you can run the “Create a purchase agreement” guide first to set up the necessary preconditions for this guide.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="a6aa7-111">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="a6aa7-111">Create a purchase order</span></span>
1. <span data-ttu-id="a6aa7-112">Otwórz obszar roboczy Przygotowanie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-112">Open the purchase order preparation workspace.</span></span>
2. <span data-ttu-id="a6aa7-113">Kliknij opcję Nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-113">Click New purchase order.</span></span>
3. <span data-ttu-id="a6aa7-114">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-114">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a6aa7-115">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-115">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="a6aa7-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="a6aa7-117">Przełącz rozwinięcie sekcji Ogólne.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-117">Toggle the expansion of the General section.</span></span>
7. <span data-ttu-id="a6aa7-118">W polu Umowa zakupu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-118">In the Purchase agreement field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a6aa7-119">Wszystkie dostępne umowy z dostawcą są wymienione w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-119">All available agreements for the vendor are listed here.</span></span> <span data-ttu-id="a6aa7-120">Znajdź obowiązującą umowę, której chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-120">Find the effective agreement that you want to use.</span></span>  
8. <span data-ttu-id="a6aa7-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="a6aa7-122">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-122">Click Yes.</span></span>
10. <span data-ttu-id="a6aa7-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-123">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="a6aa7-124">Dodawanie wiersza</span><span class="sxs-lookup"><span data-stu-id="a6aa7-124">Add a line</span></span>
1. <span data-ttu-id="a6aa7-125">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-125">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="a6aa7-126">Jeśli w zobowiązaniu istnieją określone wymiary magazynowe lub wymiary lokalizacji, te same wartości należy wprowadzić w wierszu zamówienia zakupu, aby umowa była używana.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-126">If there are specific inventory or location dimensions on the commitment you must enter the same values on the purchase order line to make use of the agreement.</span></span>  
2. <span data-ttu-id="a6aa7-127">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-127">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a6aa7-128">Pole oddziału może już być wypełnione wartością domyślną z zamówienia lub od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-128">The site may already be populated with the default value from the order, or from the vendor.</span></span> <span data-ttu-id="a6aa7-129">W takim przypadku pomiń ten krok.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-129">If this is the case, skip this step.</span></span>  
3. <span data-ttu-id="a6aa7-130">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-130">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="a6aa7-131">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-131">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a6aa7-132">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-132">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="a6aa7-133">Sprawdź, czy cena została skopiowana ze zobowiązania.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-133">Validate that the price is copied from the commitment.</span></span>  

## <a name="look-up-the-commitment"></a><span data-ttu-id="a6aa7-134">Wyszukiwanie zobowiązania</span><span class="sxs-lookup"><span data-stu-id="a6aa7-134">Look up the commitment</span></span>
1. <span data-ttu-id="a6aa7-135">Kliknij opcję Aktualizuj wiersz.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-135">Click Update line.</span></span>
2. <span data-ttu-id="a6aa7-136">Kliknij opcję Powiązany.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-136">Click Attached.</span></span>
    * <span data-ttu-id="a6aa7-137">W tym miejscu można uzyskać szczegółowe informacje dotyczące umowy zakupu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-137">Here you can get details for the purchase agreement.</span></span> <span data-ttu-id="a6aa7-138">Na przykład można wyświetlić cenę i sprawdzić, czy cena i rabat są stałe, co oznacza, że jeśli zmienisz cenę lub rabat w zamówieniu zakupu na inną wartość niż podana w zobowiązaniu, system usunie łącze, w związku z czym wiersz zamówienia zakupu nie będzie spełniał zobowiązania.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-138">For example, you can see the price and whether the price and discount are fixed, which means that if you change price or discount on the purchase order to a different value than on the commitment, the system will remove the link so the purchase order line does not fulfill the commitment.</span></span> <span data-ttu-id="a6aa7-139">Można również sprawdzić, czy jest zaznaczona opcja Wymuszono maks., która oznacza, że ilość w zobowiązaniu nie może zostać przekroczona po zsumowaniu wszystkich zakupów spełniających zobowiązanie.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-139">You can also see if the Max is enforced option is selected, which means that the quantity on the commitment cannot be exceeded by summing all of the purchases that fulfill the commitment.</span></span>  
3. <span data-ttu-id="a6aa7-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-140">Close the page.</span></span>

## <a name="look-up-the-purchase-agreement"></a><span data-ttu-id="a6aa7-141">Wyszukiwanie umowy zakupu</span><span class="sxs-lookup"><span data-stu-id="a6aa7-141">Look up the purchase agreement</span></span>
1. <span data-ttu-id="a6aa7-142">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-142">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="a6aa7-143">Kliknij opcję Umowa zakupu.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-143">Click Purchase agreement.</span></span>
3. <span data-ttu-id="a6aa7-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-144">Close the page.</span></span>
4. <span data-ttu-id="a6aa7-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a6aa7-145">Close the page.</span></span>


