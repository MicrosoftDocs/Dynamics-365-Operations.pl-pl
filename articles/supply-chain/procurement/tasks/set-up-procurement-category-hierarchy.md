--- 
title: Ustawianie hierarchii kategorii zaopatrzenia
description: "W tej procedurze pokazano, jak utworzyć nowe węzły w hierarchii kategorii zaopatrzenia oraz jak skonfigurować kategorię zaopatrzenia, która ma być używana w procesie zaopatrzenia."
author: mkirknel
manager: AnnBe
ms.date: 11/11/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b9897b1184e8159b20a45d4cedbba56baef31a3c
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="df6fa-103">Ustawianie hierarchii kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="df6fa-103">Set up a procurement category hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="df6fa-104">W tej procedurze pokazano, jak utworzyć nowe węzły w hierarchii kategorii zaopatrzenia oraz jak skonfigurować kategorię zaopatrzenia, która ma być używana w procesie zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="df6fa-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="df6fa-105">Te zadania zazwyczaj wykonuje menedżer ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="df6fa-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="df6fa-106">Przed rozpoczęciem tej procedury musi istnieć hierarchia kategorii typu Zaopatrzenie.</span><span class="sxs-lookup"><span data-stu-id="df6fa-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="df6fa-107">Jeśli używasz danych firmy demonstracyjnej, procedurę można wykonać w firmie USMF.</span><span class="sxs-lookup"><span data-stu-id="df6fa-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="df6fa-108">Dodawanie nowej kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="df6fa-108">Add a new procurement category</span></span>
1. <span data-ttu-id="df6fa-109">Wybierz kolejno opcje Zaopatrzenie i sourcing > ..</span><span class="sxs-lookup"><span data-stu-id="df6fa-109">Go to Procurement and sourcing > ..</span></span> <span data-ttu-id="df6fa-110">> Kategorie zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="df6fa-110">> Procurement categories.</span></span>
2. <span data-ttu-id="df6fa-111">Kliknij opcję Edytuj hierarchię kategorii.</span><span class="sxs-lookup"><span data-stu-id="df6fa-111">Click Edit category hierarchy.</span></span>
    * <span data-ttu-id="df6fa-112">Bieżąca hierarchia kategorii zaopatrzenia zostanie wyświetlona przy lewej krawędzi strony.</span><span class="sxs-lookup"><span data-stu-id="df6fa-112">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="df6fa-113">Zmodyfikujesz tę hierarchię.</span><span class="sxs-lookup"><span data-stu-id="df6fa-113">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="df6fa-114">Kliknij opcję Nowy węzeł kategorii.</span><span class="sxs-lookup"><span data-stu-id="df6fa-114">Click New category node.</span></span>
    * <span data-ttu-id="df6fa-115">Domyślnie system wybiera węzeł najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="df6fa-115">The system selects the top node by default.</span></span> <span data-ttu-id="df6fa-116">Jeśli wykonujesz tę procedurę w przewodniku po zadaniach, możesz kliknąć przycisk Odblokuj i wybrać inny węzeł nadrzędny, aby wstawić tam swój nowy węzeł.</span><span class="sxs-lookup"><span data-stu-id="df6fa-116">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="df6fa-117">Po wykonaniu tej operacji ponownie zablokuj przewodnik po zadaniach, a następnie kliknij przycisk Nowy węzeł kategorii.</span><span class="sxs-lookup"><span data-stu-id="df6fa-117">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="df6fa-118">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="df6fa-118">In the Name field, type a value.</span></span>
5. <span data-ttu-id="df6fa-119">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="df6fa-119">In the Description field, type a value.</span></span>
6. <span data-ttu-id="df6fa-120">W polu Przyjazna nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="df6fa-120">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="df6fa-121">Przyjazna nazwa jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="df6fa-121">The friendly name is optional.</span></span> <span data-ttu-id="df6fa-122">Będzie wyświetlany w wyszukiwaniach kategorii wraz z nazwą kategorii.</span><span class="sxs-lookup"><span data-stu-id="df6fa-122">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="df6fa-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="df6fa-123">Click Save.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="df6fa-124">Dodawanie produktów do nowej kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="df6fa-124">Add products to your new procurement category</span></span>
1. <span data-ttu-id="df6fa-125">Wybierz kolejno opcje Zaopatrzenie i sourcing > ..</span><span class="sxs-lookup"><span data-stu-id="df6fa-125">Go to Procurement and sourcing > ..</span></span> <span data-ttu-id="df6fa-126">> Kategorie zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="df6fa-126">> Procurement categories.</span></span>
    * <span data-ttu-id="df6fa-127">Zaznacz dodany właśnie węzeł.</span><span class="sxs-lookup"><span data-stu-id="df6fa-127">Select the node you just added.</span></span> <span data-ttu-id="df6fa-128">Jeśli wykonujesz tę procedurę w przewodniku po zadaniach, może być konieczne odblokowanie przewodnika po zadaniach w celu wybrania węzła.</span><span class="sxs-lookup"><span data-stu-id="df6fa-128">If you’re running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="df6fa-129">Przełącz rozwinięcie sekcji Produkty.</span><span class="sxs-lookup"><span data-stu-id="df6fa-129">Toggle the expansion of the Products section.</span></span>
3. <span data-ttu-id="df6fa-130">Kliknij przycisk Dodaj, aby skojarzyć produkty z kategorią zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="df6fa-130">Click Add to associate products with the procurement category.</span></span>
4. <span data-ttu-id="df6fa-131">Zaznacz produkt, który ma zostać dodany do kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="df6fa-131">Select the product you want to add to the procurement category.</span></span>
5. <span data-ttu-id="df6fa-132">Kliknij strzałkę, aby wybrać produkt.</span><span class="sxs-lookup"><span data-stu-id="df6fa-132">Click the arrow to select the product.</span></span>
6. <span data-ttu-id="df6fa-133">Zaznacz kolejny produkt, który ma zostać dodany do kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="df6fa-133">Select another product to add to the procurement category.</span></span>
7. <span data-ttu-id="df6fa-134">Kliknij strzałkę, aby wybrać produkt.</span><span class="sxs-lookup"><span data-stu-id="df6fa-134">Click the arrow to select the product.</span></span>
8. <span data-ttu-id="df6fa-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="df6fa-135">Click OK.</span></span>

## <a name="add-approved-and-preferred-vendors"></a><span data-ttu-id="df6fa-136">Dodawanie zatwierdzonych i preferowanych dostawców</span><span class="sxs-lookup"><span data-stu-id="df6fa-136">Add approved and preferred vendors</span></span>
1. <span data-ttu-id="df6fa-137">Przełącz rozwinięcie sekcji Dostawcy.</span><span class="sxs-lookup"><span data-stu-id="df6fa-137">Toggle the expansion of the Vendors section.</span></span>
2. <span data-ttu-id="df6fa-138">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="df6fa-138">Click Add.</span></span>
    * <span data-ttu-id="df6fa-139">Można dodać dostawcę do kategorii zaopatrzenia i określić, czy jest on preferowany czy tylko zatwierdzony dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="df6fa-139">You can add a vendor to a procurement category and specify whether a vendor is preferred or just approved for the category.</span></span> <span data-ttu-id="df6fa-140">Usunięcie dostawcy z kategorii nie powoduje usunięcia historycznych transakcji z dostawcą w danej kategorii.</span><span class="sxs-lookup"><span data-stu-id="df6fa-140">When you delete a vendor from a category, the historical transactions with the vendor in the category are not deleted.</span></span>   
3. <span data-ttu-id="df6fa-141">Znajdź dostawcę, który ma zostać dodany do kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="df6fa-141">Find the vendor you want to add to the category.</span></span>
4. <span data-ttu-id="df6fa-142">Kliknij strzałkę, aby wybrać dostawcę.</span><span class="sxs-lookup"><span data-stu-id="df6fa-142">Click the arrow to select the vendor.</span></span>
5. <span data-ttu-id="df6fa-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="df6fa-143">Click OK.</span></span>
6. <span data-ttu-id="df6fa-144">Wybierz wiersz dostawcy, którego chcesz zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="df6fa-144">Select the vendor row that you want to modify.</span></span>
7. <span data-ttu-id="df6fa-145">W polu Stan dostawcy wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="df6fa-145">In the Vendor status field, select an option.</span></span>
    * <span data-ttu-id="df6fa-146">Ustawienie wyboru dostawcy w reguły kategorii decyduje, czy w zapotrzebowaniach na zakup są dostępni dostawcy preferowani, zatwierdzeni czy wszyscy.</span><span class="sxs-lookup"><span data-stu-id="df6fa-146">The vendor selection setting in the Category policy rule governs whether preferred, approved, or all vendors are available on purchase requisitions.</span></span>   

## <a name="add-additional-information-to-the-category"></a><span data-ttu-id="df6fa-147">Dodawanie uzupełniających informacji do kategorii</span><span class="sxs-lookup"><span data-stu-id="df6fa-147">Add additional information to the category</span></span>
1. <span data-ttu-id="df6fa-148">Przełącz rozwinięcie sekcji Grupy kryteriów oceny dostawców.</span><span class="sxs-lookup"><span data-stu-id="df6fa-148">Toggle the expansion of the Vendor evaluation criterion groups section.</span></span>
    * <span data-ttu-id="df6fa-149">Ta karta umożliwia określenie kryteriów, według których należy oceniać dostawców w kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="df6fa-149">This tab allows you to define which criteria the vendors in the procurement category should be rated against.</span></span> <span data-ttu-id="df6fa-150">W tym celu kliknij przycisk Dodaj, a następnie wybierz grupę oceny dostawców zawierającą żądane kryteria.</span><span class="sxs-lookup"><span data-stu-id="df6fa-150">To do this you would click Add and then select a vendor evaluation group that contains the criteria you want.</span></span>  
2. <span data-ttu-id="df6fa-151">Przełącz rozwinięcie sekcji Kwestionariusze.</span><span class="sxs-lookup"><span data-stu-id="df6fa-151">Toggle the expansion of the Questionnaires section.</span></span>
    * <span data-ttu-id="df6fa-152">Ta karta umożliwia dodawanie kwestionariuszy, które będą wyświetlane w zapotrzebowaniu, o ile w polu Typu działania zaznaczysz wartość „Zapotrzebowanie”.</span><span class="sxs-lookup"><span data-stu-id="df6fa-152">This tab allows you to add questionnaires that will appear on the requisition, as long as you set the Activity type to "Requisition".</span></span> <span data-ttu-id="df6fa-153">Wtedy zleceniodawca musi wypełnić kwestionariusz, zanim wyśle zapotrzebowanie na określony produkt lub produkty z kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="df6fa-153">The requester then has to fill out a questionnaire before they submit a requisition for the specific product or products in the procurement category.</span></span>  
3. <span data-ttu-id="df6fa-154">Przełącz rozwinięcie sekcji Grupy podatków dla towaru.</span><span class="sxs-lookup"><span data-stu-id="df6fa-154">Toggle the expansion of the Item sales tax groups section.</span></span>
4. <span data-ttu-id="df6fa-155">W polu Grupa podatków dla towaru: kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="df6fa-155">In the Item sales tax group: field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="df6fa-156">Umożliwia wybranie grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="df6fa-156">Select a sales tax group.</span></span>
6. <span data-ttu-id="df6fa-157">Przełącz rozwinięcie sekcji Strona kategorii.</span><span class="sxs-lookup"><span data-stu-id="df6fa-157">Toggle the expansion of the Category page section.</span></span>
    * <span data-ttu-id="df6fa-158">Strony kategorii tworzy się na stronie Hierarchia kategorii.</span><span class="sxs-lookup"><span data-stu-id="df6fa-158">Category pages are created in the Category hierarchy page.</span></span> <span data-ttu-id="df6fa-159">Zawierają one informacje o kategorii zaopatrzenia, takie jak typy produktów w kategorii, zdjęcia produktów w kategorii lub ogłoszenia np. o rabatach dostępnych w danej kategorii.</span><span class="sxs-lookup"><span data-stu-id="df6fa-159">They contain information about the procurement category such as information about the type of products in a category, images of products in a category, or announcements such as the discounts that are available in a category.</span></span> <span data-ttu-id="df6fa-160">Informacje na stronie kategorii są wyświetlane w zapotrzebowaniach na zakup.</span><span class="sxs-lookup"><span data-stu-id="df6fa-160">The information in a category page is displayed on purchase requisitions.</span></span>  
7. <span data-ttu-id="df6fa-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="df6fa-161">Close the page.</span></span>


