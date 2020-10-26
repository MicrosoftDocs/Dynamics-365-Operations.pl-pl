---
title: Tworzenie modelu konfiguracji produktu
description: W tej procedurze pokazano sposób tworzenia modelu konfiguracji produktu i wprowadzania podstawowych informacji, takich jak atrybuty i podskładniki.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9c81b3af7460c636245dcc16affcb05b724fbc70
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986126"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="27b5d-103">Tworzenie modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="27b5d-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27b5d-104">W tej procedurze pokazano sposób tworzenia modelu konfiguracji produktu i wprowadzania podstawowych informacji, takich jak atrybuty i podskładniki.</span><span class="sxs-lookup"><span data-stu-id="27b5d-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="27b5d-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="27b5d-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="27b5d-106">Tworzenie modelu produktu</span><span class="sxs-lookup"><span data-stu-id="27b5d-106">Create a product model</span></span>
1. <span data-ttu-id="27b5d-107">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="27b5d-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="27b5d-108">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="27b5d-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="27b5d-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="27b5d-109">Click New.</span></span>
4. <span data-ttu-id="27b5d-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="27b5d-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="27b5d-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="27b5d-112">W polu Strategia zmiennej wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="27b5d-112">In the Solver strategy field, select an option.</span></span>
    * <span data-ttu-id="27b5d-113">Strategia zmiennej określa sposób przetwarzania ograniczeń w modelu konfiguracji produktu opartej na ograniczeniach.</span><span class="sxs-lookup"><span data-stu-id="27b5d-113">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="27b5d-114">Wybranie tej opcji może mieć wpływ na działanie modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="27b5d-114">This selection can have an impact on the performance of the product configuration model.</span></span>  
7. <span data-ttu-id="27b5d-115">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="27b5d-116">Składnik główny reprezentuje modelu konfiguracji produktu, ale może być używany również w innych modelach produktów.</span><span class="sxs-lookup"><span data-stu-id="27b5d-116">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
8. <span data-ttu-id="27b5d-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="27b5d-117">Click OK.</span></span>
9. <span data-ttu-id="27b5d-118">W polu Użyj ponownie konfiguracji wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="27b5d-118">In the Reuse configurations field, select an option.</span></span>
    * <span data-ttu-id="27b5d-119">Jeśli parametr Użyj ponownie konfiguracji jest ustawiony na Tak, system będzie sprawdzał istnienie identycznych konfiguracji po każdej sesji konfigurowania i wykorzystywał je, jeśli znajdzie dokładne odpowiedniki.</span><span class="sxs-lookup"><span data-stu-id="27b5d-119">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="27b5d-120">Dodaj atrybuty</span><span class="sxs-lookup"><span data-stu-id="27b5d-120">Add attributes</span></span>
1. <span data-ttu-id="27b5d-121">Rozwiń sekcję Atrybuty.</span><span class="sxs-lookup"><span data-stu-id="27b5d-121">Expand the Attributes section.</span></span>
2. <span data-ttu-id="27b5d-122">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="27b5d-122">Click Add.</span></span>
3. <span data-ttu-id="27b5d-123">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="27b5d-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="27b5d-124">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-124">In the Name field, type a value.</span></span>
5. <span data-ttu-id="27b5d-125">W polu Nazwa zmiennej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-125">In the Solver name field, type a value.</span></span>
    * <span data-ttu-id="27b5d-126">Nazwa zmiennej jest używana przez solver ograniczeń w konfiguratorze produktów.</span><span class="sxs-lookup"><span data-stu-id="27b5d-126">The Solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="27b5d-127">Nie może zawierać spacji ani znaków specjalnych, z wyjątkiem _(podkreślenia).</span><span class="sxs-lookup"><span data-stu-id="27b5d-127">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="27b5d-128">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="27b5d-128">In the Description field, type a value.</span></span>
    * <span data-ttu-id="27b5d-129">Tekst opisu jest wyświetlany użytkownikowi konfiguracji i dlatego może służyć jako pomoc przy wyborze odpowiedniej wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="27b5d-129">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="27b5d-130">W polu Typ atrybutu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-130">In the Attribute type field, enter or select a value.</span></span>
    * <span data-ttu-id="27b5d-131">Typ atrybutu określa, które wartości są dostępne dla atrybutu.</span><span class="sxs-lookup"><span data-stu-id="27b5d-131">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="27b5d-132">Zaznacz pole wyboru Uwzględnij w ponownym użyciu.</span><span class="sxs-lookup"><span data-stu-id="27b5d-132">Select the Include in reuse check box.</span></span>
    * <span data-ttu-id="27b5d-133">Ta opcja jest dostępna tylko po zaznaczeniu opcji Użyj ponownie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="27b5d-133">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="27b5d-134">Zaznaczenie pola wyboru Uwzględnij w ponownym użyciu spowoduje, że atrybut będzie brany pod uwagę, gdy system szuka dokładnie pasującego elementu.</span><span class="sxs-lookup"><span data-stu-id="27b5d-134">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="27b5d-135">Dodawanie podskładników</span><span class="sxs-lookup"><span data-stu-id="27b5d-135">Add subcomponents</span></span>
1. <span data-ttu-id="27b5d-136">Rozwiń sekcję Składniki podrzędne.</span><span class="sxs-lookup"><span data-stu-id="27b5d-136">Expand the Subcomponents section.</span></span>
2. <span data-ttu-id="27b5d-137">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="27b5d-137">Click Add.</span></span>
3. <span data-ttu-id="27b5d-138">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="27b5d-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="27b5d-139">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-139">In the Name field, type a value.</span></span>
5. <span data-ttu-id="27b5d-140">W polu Nazwa zmiennej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-140">In the Solver name field, type a value.</span></span>
6. <span data-ttu-id="27b5d-141">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="27b5d-141">In the Description field, type a value.</span></span>
7. <span data-ttu-id="27b5d-142">W polu Składnik wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-142">In the Component field, enter or select a value.</span></span>
    * <span data-ttu-id="27b5d-143">Każdy podskładnik musi się odwoływać do definicji składnika.</span><span class="sxs-lookup"><span data-stu-id="27b5d-143">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="27b5d-144">Ten projekt obsługuje składniki wielokrotnego użytku i zapewnia, że po zdefiniowaniu składnika będzie go może używać w wielu modelach produktów.</span><span class="sxs-lookup"><span data-stu-id="27b5d-144">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="27b5d-145">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="27b5d-145">Click Save.</span></span>
9. <span data-ttu-id="27b5d-146">Kliknij opcję Szczegóły wiersza BOM.</span><span class="sxs-lookup"><span data-stu-id="27b5d-146">Click BOM line details.</span></span>
    * <span data-ttu-id="27b5d-147">Formularz Szczegóły wiersza BOM pozwala użytkownikowi wybrać wymagane właściwości podskładnika.</span><span class="sxs-lookup"><span data-stu-id="27b5d-147">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="27b5d-148">Każdej właściwości można nadać stałą wartość lub zmapować ją na atrybut.</span><span class="sxs-lookup"><span data-stu-id="27b5d-148">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="27b5d-149">Mapowanie na atrybut spowoduje, że właściwość wiersza BOM będzie otrzymywać różne wartości w zależności od wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="27b5d-149">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="27b5d-150">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-150">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="27b5d-151">Każdy podskładnik reprezentuje konfigurowalny produkt główny z technologią konfiguracji opartej na ograniczeniach.</span><span class="sxs-lookup"><span data-stu-id="27b5d-151">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="27b5d-152">Odwoływanie odbywa się za pomocą numeru towaru.</span><span class="sxs-lookup"><span data-stu-id="27b5d-152">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="27b5d-153">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="27b5d-153">Select the Set check box.</span></span>
12. <span data-ttu-id="27b5d-154">W polu Obliczanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="27b5d-154">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="27b5d-155">Ustawienie opcji obliczania zapewnia, że produkt będzie uwzględniany przy wykonywaniu obliczeń kosztów dla produktu.</span><span class="sxs-lookup"><span data-stu-id="27b5d-155">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="27b5d-156">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="27b5d-156">Click the Setup tab.</span></span>
14. <span data-ttu-id="27b5d-157">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="27b5d-157">Select the Set check box.</span></span>
15. <span data-ttu-id="27b5d-158">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="27b5d-158">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="27b5d-159">Pole ilości określa, jaka część tego produktu będzie zużywana w skonfigurowanym produkcie.</span><span class="sxs-lookup"><span data-stu-id="27b5d-159">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="27b5d-160">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="27b5d-160">Select the Set check box.</span></span>
17. <span data-ttu-id="27b5d-161">W polu W serii wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="27b5d-161">In the Per series field, enter a number.</span></span>
18. <span data-ttu-id="27b5d-162">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="27b5d-162">Click OK.</span></span>

