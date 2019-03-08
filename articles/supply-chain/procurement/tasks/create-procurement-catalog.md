---
title: Tworzenie katalogu zaopatrzenia
description: W tym przewodniku pokazano sposób tworzenia katalogu zaopatrzenia.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f2a010e21f16b3908a6ee5f18d8f144c5130be7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "314700"
---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="34599-103">Tworzenie katalogu zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="34599-103">Create a procurement catalog</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="34599-104">W tym przewodniku pokazano sposób tworzenia katalogu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="34599-104">This guide shows you how to create a procurement catalog.</span></span> <span data-ttu-id="34599-105">To zadanie jest zazwyczaj wykonywane przez pracownika działu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="34599-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="34599-106">Dowiedz się także, jak pracownicy mogą używać katalogu podczas tworzenia zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="34599-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="34599-107">Aby można było utworzyć katalogu, w systemie musi istnieć hierarchia kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="34599-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="34599-108">Hierarchia, wraz ze wszystkimi znajdującymi się w niej produktami, jest dziedziczona przez nowy katalog.</span><span class="sxs-lookup"><span data-stu-id="34599-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="34599-109">Można użyć tego przewodnika z danymi firmy demonstracyjne USMF, gdzie hierarchia kategorii zaopatrzenia jest już dostępna, oraz wobec przykładów opisanych w krokach procedury.</span><span class="sxs-lookup"><span data-stu-id="34599-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="34599-110">Sprawdzanie, czy istnieje hierarchia kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="34599-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="34599-111">Wybierz kolejno opcje Zaopatrzenie i sourcing > Kategorie zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="34599-111">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="34599-112">W danych firmy demonstracyjnej USMF jest dostępna hierarchia kategorii zaopatrzenia, a produkty zostały dodane do kategorii Urządzenia biurowe/Komputery.</span><span class="sxs-lookup"><span data-stu-id="34599-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the Office machines/Computers category.</span></span> <span data-ttu-id="34599-113">Jeśli wykonujesz tę procedurę jako przewodnik po zadaniu, musisz odblokować przewodnik, aby móc przeglądać kategorię.</span><span class="sxs-lookup"><span data-stu-id="34599-113">If you’re running this procedure as a task guide, you’ll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="34599-114">Jeśli hierarchia nie była dostępna, należało ją utworzyć kliknięciem przycisku Nowy.</span><span class="sxs-lookup"><span data-stu-id="34599-114">If a hierarchy was not available, you’d create it by clicking New.</span></span> <span data-ttu-id="34599-115">Można to zrobić tylko raz.</span><span class="sxs-lookup"><span data-stu-id="34599-115">This can only be done once.</span></span>  
2. <span data-ttu-id="34599-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="34599-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="34599-117">Tworzenie katalogu</span><span class="sxs-lookup"><span data-stu-id="34599-117">Create a catalog</span></span>
1. <span data-ttu-id="34599-118">Wybierz kolejno opcje Zaopatrzenie i sourcing > Katalogi > Katalogi zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="34599-118">Go to Procurement and sourcing > Catalogs > Procurement catalogs.</span></span>
2. <span data-ttu-id="34599-119">Kliknij przycisk Nowy katalog zaopatrzenia, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="34599-119">Click New procurement catalog to open the drop dialog.</span></span>
3. <span data-ttu-id="34599-120">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="34599-120">In the Name field, type a value.</span></span>
4. <span data-ttu-id="34599-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="34599-121">Click OK.</span></span>
5. <span data-ttu-id="34599-122">W drzewie rozwiń węzeł „KATEGORIE ZAOPATRZENIA W FIRMIE”.</span><span class="sxs-lookup"><span data-stu-id="34599-122">In the tree, expand 'CORP PROCUREMENT CATEGORIES'.</span></span>
6. <span data-ttu-id="34599-123">W drzewie rozwiń węzeł „URZĄDZENIA BIUROWE”.</span><span class="sxs-lookup"><span data-stu-id="34599-123">In the tree, expand 'OFFICE MACHINES'.</span></span>
7. <span data-ttu-id="34599-124">W drzewie zaznacz pozycję „Komputery”.</span><span class="sxs-lookup"><span data-stu-id="34599-124">In the tree, select 'Computers'.</span></span>
    * <span data-ttu-id="34599-125">Produkty z kategorii zaopatrzenia są wyświetlane na liście.</span><span class="sxs-lookup"><span data-stu-id="34599-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="34599-126">Jeśli chcesz dodać produkt do kategorii, trzeba to zrobić na stronie Hierarchia kategorii zaopatrzenia lub na stronie Szczegóły pozycji.</span><span class="sxs-lookup"><span data-stu-id="34599-126">If you want to add a product to the category you need to do this on the Procurement category hierarchy page or on the Item details page.</span></span>  
    * <span data-ttu-id="34599-127">Domyślny typ aktualizacji określa, czy nowe produkty dodawane do hierarchii kategorii zaopatrzenia są natychmiast widoczne w katalogu.</span><span class="sxs-lookup"><span data-stu-id="34599-127">The Default update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="34599-128">Jeśli jako typ aktualizacji ustawiono wartość Dynamiczne, zmiany są widoczne natychmiast.</span><span class="sxs-lookup"><span data-stu-id="34599-128">If the update type is set to Dynamic, changes are visible immediately.</span></span> <span data-ttu-id="34599-129">Jeśli typem aktualizacji jest Statyczne, nowe produkty są widoczne tylko dla osób używających katalogu po jego ponownym opublikowaniu.</span><span class="sxs-lookup"><span data-stu-id="34599-129">If the update type is Static, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="34599-130">Akcja Publikuj jest dostępna w okienku akcji u góry strony.</span><span class="sxs-lookup"><span data-stu-id="34599-130">The Publish action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="34599-131">Jeśli produkty zostaną usunięte z hierarchii kategorii zaopatrzenia, zmiana jest natychmiast widoczna, niezależnie od wartości w polu Domyślny typ aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="34599-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the Default update type field.</span></span>  
8. <span data-ttu-id="34599-132">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="34599-132">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="34599-133">Kliknij przycisk Ukryj.</span><span class="sxs-lookup"><span data-stu-id="34599-133">Click Hide.</span></span>
10. <span data-ttu-id="34599-134">W okienku akcji kliknij pozycję Kategoria nawigacji.</span><span class="sxs-lookup"><span data-stu-id="34599-134">On the Action Pane, click Category navigation.</span></span>
11. <span data-ttu-id="34599-135">Kliknij przycisk Wyłącz.</span><span class="sxs-lookup"><span data-stu-id="34599-135">Click Disable.</span></span>
12. <span data-ttu-id="34599-136">W okienku akcji kliknij pozycję Kategoria nawigacji.</span><span class="sxs-lookup"><span data-stu-id="34599-136">On the Action Pane, click Category navigation.</span></span>
13. <span data-ttu-id="34599-137">Kliknij przycisk Włącz.</span><span class="sxs-lookup"><span data-stu-id="34599-137">Click Enable.</span></span>
14. <span data-ttu-id="34599-138">Kliknij opcję Uaktywnij katalog.</span><span class="sxs-lookup"><span data-stu-id="34599-138">Click Activate catalog.</span></span>
15. <span data-ttu-id="34599-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="34599-139">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="34599-140">Ustawianie widoczności katalogu</span><span class="sxs-lookup"><span data-stu-id="34599-140">Make the catalog visible</span></span>
1. <span data-ttu-id="34599-141">Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zasady > Zasady zakupów.</span><span class="sxs-lookup"><span data-stu-id="34599-141">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="34599-142">Wybierz zasadę Procurement Policy USMF.</span><span class="sxs-lookup"><span data-stu-id="34599-142">Select Procurement Policy USMF.</span></span>
    * <span data-ttu-id="34599-143">Należy wybrać zasady zakupów dla firmy, w której pracownik połączony z Twoim profilem użytkownika może zamawiać produkty.</span><span class="sxs-lookup"><span data-stu-id="34599-143">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="34599-144">W danych firmy demonstracyjnej USMF administrator jest połączony z pracownikiem Julia Funderburk. Julia domyślnie zamawia produkty w USMF.</span><span class="sxs-lookup"><span data-stu-id="34599-144">In the USMF demo data, the Admin user is connected to the worker called Julia Funderburk, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="34599-145">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="34599-145">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="34599-146">Zaznacz nowo utworzony katalog.</span><span class="sxs-lookup"><span data-stu-id="34599-146">Select the catalog that you’ve just created.</span></span>
5. <span data-ttu-id="34599-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="34599-147">Click OK.</span></span>
6. <span data-ttu-id="34599-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="34599-148">Close the page.</span></span>
7. <span data-ttu-id="34599-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="34599-149">Close the page.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="34599-150">Używanie katalogu</span><span class="sxs-lookup"><span data-stu-id="34599-150">Use the catalog</span></span>
1. <span data-ttu-id="34599-151">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Wszystkie zapotrzebowania na zakup.</span><span class="sxs-lookup"><span data-stu-id="34599-151">Go to Procurement and sourcing > Purchase requisitions > All purchase requisitions.</span></span>
2. <span data-ttu-id="34599-152">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="34599-152">Click New.</span></span>
3. <span data-ttu-id="34599-153">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="34599-153">In the Name field, type a value.</span></span>
4. <span data-ttu-id="34599-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="34599-154">Click OK.</span></span>
5. <span data-ttu-id="34599-155">Kliknij przycisk Dodaj produkty.</span><span class="sxs-lookup"><span data-stu-id="34599-155">Click Add products.</span></span>
6. <span data-ttu-id="34599-156">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="34599-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="34599-157">Do filtrowania produktów można używać hierarchii kategorii po lewej stronie lub filtru u góry listy.</span><span class="sxs-lookup"><span data-stu-id="34599-157">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="34599-158">Kliknij opcję Dodaj do wierszy.</span><span class="sxs-lookup"><span data-stu-id="34599-158">Click Add to lines.</span></span>
8. <span data-ttu-id="34599-159">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="34599-159">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="34599-160">Kliknij opcję Dodaj do wierszy.</span><span class="sxs-lookup"><span data-stu-id="34599-160">Click Add to lines.</span></span>
10. <span data-ttu-id="34599-161">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="34599-161">Click OK.</span></span>

