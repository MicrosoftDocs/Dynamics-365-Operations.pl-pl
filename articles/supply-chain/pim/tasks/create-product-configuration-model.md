---
title: Tworzenie modelu konfiguracji produktu
description: W tej procedurze pokazano sposób tworzenia modelu konfiguracji produktu i wprowadzania podstawowych informacji, takich jak atrybuty i podskładniki.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cb9e33d7bab6ca9cd378ec40baa796d1a933ece
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921372"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="3dce6-103">Tworzenie modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="3dce6-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3dce6-104">W tej procedurze pokazano sposób tworzenia modelu konfiguracji produktu i wprowadzania podstawowych informacji, takich jak atrybuty i podskładniki.</span><span class="sxs-lookup"><span data-stu-id="3dce6-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="3dce6-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3dce6-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="3dce6-106">Tworzenie modelu produktu</span><span class="sxs-lookup"><span data-stu-id="3dce6-106">Create a product model</span></span>

1. <span data-ttu-id="3dce6-107">Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="3dce6-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-108">Select **New**.</span></span>
1. <span data-ttu-id="3dce6-109">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-109">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="3dce6-110">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-110">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="3dce6-111">W polu **Strategia zmiennej** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="3dce6-111">In the **Solver strategy** field, select an option.</span></span>
    * <span data-ttu-id="3dce6-112">Strategia zmiennej określa sposób przetwarzania ograniczeń w modelu konfiguracji produktu opartej na ograniczeniach.</span><span class="sxs-lookup"><span data-stu-id="3dce6-112">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="3dce6-113">Wybranie tej opcji może mieć wpływ na działanie modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="3dce6-113">This selection can have an impact on the performance of the product configuration model.</span></span>  
1. <span data-ttu-id="3dce6-114">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-114">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="3dce6-115">Składnik główny reprezentuje modelu konfiguracji produktu, ale może być używany również w innych modelach produktów.</span><span class="sxs-lookup"><span data-stu-id="3dce6-115">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
1. <span data-ttu-id="3dce6-116">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-116">Select **OK**.</span></span>
1. <span data-ttu-id="3dce6-117">W polu **Użyj ponownie konfiguracji** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="3dce6-117">In the **Reuse configurations** field, select an option.</span></span>
    * <span data-ttu-id="3dce6-118">Jeśli parametr Użyj ponownie konfiguracji jest ustawiony na Tak, system będzie sprawdzał istnienie identycznych konfiguracji po każdej sesji konfigurowania i wykorzystywał je, jeśli znajdzie dokładne odpowiedniki.</span><span class="sxs-lookup"><span data-stu-id="3dce6-118">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="3dce6-119">Dodaj atrybuty</span><span class="sxs-lookup"><span data-stu-id="3dce6-119">Add attributes</span></span>

1. <span data-ttu-id="3dce6-120">Rozwiń sekcję **Atrybuty**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-120">Expand the **Attributes** section.</span></span>
2. <span data-ttu-id="3dce6-121">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-121">Select **Add**.</span></span>
3. <span data-ttu-id="3dce6-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3dce6-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="3dce6-123">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-123">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3dce6-124">W polu **Nazwa zmiennej** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-124">In the **Solver name** field, type a value.</span></span>
    * <span data-ttu-id="3dce6-125">Nazwa zmiennej jest używana przez solver ograniczeń w konfiguratorze produktów.</span><span class="sxs-lookup"><span data-stu-id="3dce6-125">The solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="3dce6-126">Nie może zawierać spacji ani znaków specjalnych, z wyjątkiem _(podkreślenia).</span><span class="sxs-lookup"><span data-stu-id="3dce6-126">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="3dce6-127">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-127">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="3dce6-128">Tekst opisu jest wyświetlany użytkownikowi konfiguracji i dlatego może służyć jako pomoc przy wyborze odpowiedniej wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="3dce6-128">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="3dce6-129">W polu **Typ atrybutu** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-129">In the **Attribute type** field, enter or select a value.</span></span>
    * <span data-ttu-id="3dce6-130">Typ atrybutu określa, które wartości są dostępne dla atrybutu.</span><span class="sxs-lookup"><span data-stu-id="3dce6-130">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="3dce6-131">Zaznacz pole wyboru **Uwzględnij w ponownym użyciu**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-131">Select the **Include in reuse** check box.</span></span>
    * <span data-ttu-id="3dce6-132">Ta opcja jest dostępna tylko po zaznaczeniu opcji Użyj ponownie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="3dce6-132">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="3dce6-133">Zaznaczenie pola wyboru Uwzględnij w ponownym użyciu spowoduje, że atrybut będzie brany pod uwagę, gdy system szuka dokładnie pasującego elementu.</span><span class="sxs-lookup"><span data-stu-id="3dce6-133">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="3dce6-134">Dodawanie podskładników</span><span class="sxs-lookup"><span data-stu-id="3dce6-134">Add subcomponents</span></span>

1. <span data-ttu-id="3dce6-135">Rozwiń sekcję **Składniki podrzędne**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-135">Expand the **Subcomponents** section.</span></span>
2. <span data-ttu-id="3dce6-136">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-136">Select **Add**.</span></span>
3. <span data-ttu-id="3dce6-137">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3dce6-137">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="3dce6-138">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3dce6-139">W polu **Nazwa zmiennej** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-139">In the **Solver name** field, type a value.</span></span>
6. <span data-ttu-id="3dce6-140">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-140">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="3dce6-141">W polu **Składnik** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-141">In the **Component** field, enter or select a value.</span></span>
    * <span data-ttu-id="3dce6-142">Każdy podskładnik musi się odwoływać do definicji składnika.</span><span class="sxs-lookup"><span data-stu-id="3dce6-142">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="3dce6-143">Ten projekt obsługuje składniki wielokrotnego użytku i zapewnia, że po zdefiniowaniu składnika będzie go może używać w wielu modelach produktów.</span><span class="sxs-lookup"><span data-stu-id="3dce6-143">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="3dce6-144">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-144">Select **Save**.</span></span>
9. <span data-ttu-id="3dce6-145">Wybierz opcję **Szczegóły wiersza BOM**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-145">Select **BOM line details**.</span></span>
    * <span data-ttu-id="3dce6-146">Formularz Szczegóły wiersza BOM pozwala użytkownikowi wybrać wymagane właściwości podskładnika.</span><span class="sxs-lookup"><span data-stu-id="3dce6-146">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="3dce6-147">Każdej właściwości można nadać stałą wartość lub zmapować ją na atrybut.</span><span class="sxs-lookup"><span data-stu-id="3dce6-147">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="3dce6-148">Mapowanie na atrybut spowoduje, że właściwość wiersza BOM będzie otrzymywać różne wartości w zależności od wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="3dce6-148">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="3dce6-149">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="3dce6-149">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="3dce6-150">Każdy podskładnik reprezentuje konfigurowalny produkt główny z technologią konfiguracji opartej na ograniczeniach.</span><span class="sxs-lookup"><span data-stu-id="3dce6-150">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="3dce6-151">Odwoływanie odbywa się za pomocą numeru towaru.</span><span class="sxs-lookup"><span data-stu-id="3dce6-151">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="3dce6-152">Zaznacz pole wyboru **Ustaw**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-152">Select the **Set** check box.</span></span>
12. <span data-ttu-id="3dce6-153">W polu **Obliczanie** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-153">Select **Yes** in the **Calculation** field.</span></span>
    * <span data-ttu-id="3dce6-154">Ustawienie opcji obliczania zapewnia, że produkt będzie uwzględniany przy wykonywaniu obliczeń kosztów dla produktu.</span><span class="sxs-lookup"><span data-stu-id="3dce6-154">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="3dce6-155">Kliknij kartę **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-155">Select the **Setup** tab.</span></span>
14. <span data-ttu-id="3dce6-156">Zaznacz pole wyboru **Ustaw**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-156">Select the **Set** check box.</span></span>
15. <span data-ttu-id="3dce6-157">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="3dce6-157">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="3dce6-158">Pole ilości określa, jaka część tego produktu będzie zużywana w skonfigurowanym produkcie.</span><span class="sxs-lookup"><span data-stu-id="3dce6-158">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="3dce6-159">Zaznacz pole wyboru **Ustaw**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-159">Select the **Set** check box.</span></span>
17. <span data-ttu-id="3dce6-160">W polu **W serii** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="3dce6-160">In the **Per series** field, enter a number.</span></span>
18. <span data-ttu-id="3dce6-161">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3dce6-161">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]