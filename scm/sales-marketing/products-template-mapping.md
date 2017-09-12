---
title: "Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania produktów między programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition a programem Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2f14b06b57930256f9211f2085512aa589df083e
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="d0858-103">Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="d0858-103">Synchronize products from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="d0858-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="d0858-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="d0858-105">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania produktów między programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition a programem Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="d0858-105">This topic discusses the templates and underlying tasks that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="template-and-task"></a><span data-ttu-id="d0858-106">Szablon i zadanie</span><span class="sxs-lookup"><span data-stu-id="d0858-106">Template and task</span></span>

<span data-ttu-id="d0858-107">Następujące szablony i podstawowe zadania są używane do synchronizowania produktów między programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations) a programem Microsoft Dynamics 365 for Sales (Sales).</span><span class="sxs-lookup"><span data-stu-id="d0858-107">The following templates and underlying tasks are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) to Microsoft Dynamics 365 for Sales (Sales).</span></span>

-   <span data-ttu-id="d0858-108">Nazwa szablonu: Produkty (z Fin and Ops do Sales)</span><span class="sxs-lookup"><span data-stu-id="d0858-108">Name of template: Products (Fin and Ops to Sales)</span></span>

-   <span data-ttu-id="d0858-109">Nazwa zadania w projekcie: Produkty</span><span class="sxs-lookup"><span data-stu-id="d0858-109">Name of task in project: Products</span></span>

<span data-ttu-id="d0858-110">Zadania synchronizacji wymagane przed synchronizacją produktu: brak</span><span class="sxs-lookup"><span data-stu-id="d0858-110">Sync tasks required prior to Product sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="d0858-111">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="d0858-111">Entity set</span></span>

| <span data-ttu-id="d0858-112">**Finance and Operations**</span><span class="sxs-lookup"><span data-stu-id="d0858-112">**Finance and Operations**</span></span> | <span data-ttu-id="d0858-113">**CDS**</span><span class="sxs-lookup"><span data-stu-id="d0858-113">**CDS**</span></span> | <span data-ttu-id="d0858-114">**Sprzedaż**</span><span class="sxs-lookup"><span data-stu-id="d0858-114">**Sales**</span></span>  |
|----------------------------|---------|------------|
| <span data-ttu-id="d0858-115">Zwolnione produkty możliwe do sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d0858-115">Sellable released products</span></span> | <span data-ttu-id="d0858-116">Produkt</span><span class="sxs-lookup"><span data-stu-id="d0858-116">Product</span></span> | <span data-ttu-id="d0858-117">Produkty</span><span class="sxs-lookup"><span data-stu-id="d0858-117">Products</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="d0858-118">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="d0858-118">Entity flow</span></span>

<span data-ttu-id="d0858-119">Produkty są zarządzane w programie Finance and Operations i synchronizowane z programem Sales.</span><span class="sxs-lookup"><span data-stu-id="d0858-119">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="d0858-120">Jednostka danych **Zwolnione produkty możliwe do sprzedaży** w programie Finance and Operations powoduje eksportowanie tylko produktów, które można sprzedawać, co oznacza, że produkty muszą zawierać wymagane informacje, aby można ich było używać zamówieniach sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d0858-120">The data entity **Sellable released products** in Finance and Operations only exports products that are sellable, which means that products have the information required to be used on a sales order.</span></span> <span data-ttu-id="d0858-121">Te same reguły mają zastosowanie podczas weryfikowania produktu za pomocą funkcji **Sprawdzanie poprawności** na stronie **Zwolniony produkt**.</span><span class="sxs-lookup"><span data-stu-id="d0858-121">The same rules apply when a product is validated with the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="d0858-122">Pole **Numer produktu** jest używane jako klucz, co oznacza, że warianty produktu są synchronizowane z usługą CDS i aplikacją Sales z osobnymi **identyfikatorami produktów** dla poszczególnych **wariantów produktu**.</span><span class="sxs-lookup"><span data-stu-id="d0858-122">The **Product number** is used as key, meaning that product variants are synchronized to CDS and Sales with individual **Product IDs** per **Product variant**.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="d0858-123">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="d0858-123">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="d0858-124">W aplikacji Sales dodano dla produktów nowe pole **Obsługiwane zewnętrznie**, co wskazuje, że dany produkt jest obsługiwany zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="d0858-124">In Sales, a new field on the products **Is Externally Maintained** is added to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="d0858-125">Wartość jest ustawiana na **Tak** domyślnie podczas importowania do aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="d0858-125">The value is set to **Yes** by default during import to Sales.</span></span>

-   <span data-ttu-id="d0858-126">**Obsługiwane zewnętrznie = Tak**: produkt pochodzi z programu Finance and Operations i nie będzie go można edytować w programie Sales.</span><span class="sxs-lookup"><span data-stu-id="d0858-126">**Is Externally Maintained = Yes**: Product originates from Finance and Operations and will not be editable in Sales.</span></span>

-   <span data-ttu-id="d0858-127">**Obsługiwane zewnętrznie = Nie**: produkt jest wprowadzany bezpośrednio w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="d0858-127">**Is Externally Maintained = No**: Product is entered directly in Sales.</span></span>

-   <span data-ttu-id="d0858-128">**Obsługiwane zewnętrznie = puste**: produkt istnieje w programie Sprzedaż przed włączeniem rozwiązania Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="d0858-128">**Is Externally Maintained = Blank**: Product exists in Sales prior to enabling the Prospect to cash solution.</span></span>

<span data-ttu-id="d0858-129">Informacja **Obsługiwane zewnętrznie** jest używana do zagwarantowania, że tylko **oferty** i **zamówienia sprzedaży** zawierające **zewnętrznie obsługiwane produkty** będą synchronizowane z programem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d0858-129">The **Is Externally Maintained** information is used to ensure that only **Quotes** and **Sales orders** with **Externally maintained products** will sync to Finance and Operations.</span></span>

<span data-ttu-id="d0858-130">**Zewnętrznie obsługiwane produkty** są automatycznie dodawane do pierwszego prawidłowego **cennika** o tej samej walucie.</span><span class="sxs-lookup"><span data-stu-id="d0858-130">**Externally maintained products** are automatically added to the first valid **Price list** with the same currency.</span></span> <span data-ttu-id="d0858-131">Należy zauważyć, że lista jest uporządkowana w kolejności alfabetycznej według parametru **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="d0858-131">Note that the list is organized alphabetically by **Name**.</span></span> <span data-ttu-id="d0858-132">Cena sprzedaży produktu z programu Finance and Operations jest używana jako cena w **cenniku**.</span><span class="sxs-lookup"><span data-stu-id="d0858-132">The product sales price from Finance and Operations is used as price on the **Price list**.</span></span> <span data-ttu-id="d0858-133">Oznacza to, że trzeba mieć **cennik** w aplikacji Sales dla każdej **waluty sprzedaży produktu** w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d0858-133">This means that it is required to have a **Price list** in Sales for each **Product sales currency** in Finance and Operations.</span></span> <span data-ttu-id="d0858-134">Jako waluta w zwalnianych produktach możliwych do sprzedaży jest ustawiana waluta rozliczeniowa firmy, z której produkty zostały wyeksportowane.</span><span class="sxs-lookup"><span data-stu-id="d0858-134">Currency on the released sellable products is set to the accounting currency in the legal entity, from which the product is exported.</span></span>

> [!NOTE]
> <span data-ttu-id="d0858-135">Synchronizacja produktów nie uda się bez **cennika** ze zgodną walutą.</span><span class="sxs-lookup"><span data-stu-id="d0858-135">Product sync will not succeed without a **Price list** with the matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="d0858-136">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="d0858-136">Preconditions and mapping setup</span></span>

-   <span data-ttu-id="d0858-137">Przed uruchomieniem pierwszej synchronizacji należy wypełnić **tabelę odrębnych produktów** dla istniejących produktów w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d0858-137">Before you run the very first sync, you must populate the **Distinct product table** for existing products in Finance and Operations.</span></span> <span data-ttu-id="d0858-138">Istniejące produkty będą synchronizowane dopiero po zakończeniu tego zadania.</span><span class="sxs-lookup"><span data-stu-id="d0858-138">Existing products will not be synchronized until this job is completed.</span></span>

    -   <span data-ttu-id="d0858-139">W programie Finance and Operations za pomocą funkcji wyszukiwania poszukaj opcji **Wypełnij tabelę odrębnych produktów**.</span><span class="sxs-lookup"><span data-stu-id="d0858-139">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>

    -   <span data-ttu-id="d0858-140">Kliknij opcję **Wypełnij tabelę odrębnych produktów**, aby uruchomić zadanie.</span><span class="sxs-lookup"><span data-stu-id="d0858-140">Click the **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="d0858-141">To zadanie trzeba wykonać tylko raz.</span><span class="sxs-lookup"><span data-stu-id="d0858-141">This job only needs to be run once.</span></span>

-   <span data-ttu-id="d0858-142">Upewnij się, że niezbędna **mapa wartości** dla **jednostki miary** sprzedaży w programie Finance and Operations istnieje w **mapowaniu Źródło -\> CDS SalesUnitSymbol/DefaultSellingUnitOfMeasure**.</span><span class="sxs-lookup"><span data-stu-id="d0858-142">Ensure that the needed **ValueMap** for selling **Unit of measure** (UOM) in Finance and Operations exists in the **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span></span>

-   <span data-ttu-id="d0858-143">Upewnij się, że **obsługiwana liczba miejsc dziesiętnych** jednostki miary jest zgodna z wymaganiami określonymi w mapowaniu **CDS -\> Miejsce docelowe**.</span><span class="sxs-lookup"><span data-stu-id="d0858-143">Ensure that **Decimals supported** for UOM match your requirements in **CDS -\> Destination**.</span></span> <span data-ttu-id="d0858-144">Jeśli wymagane są różne wartości dla różnych jednostek miary, można to zrobić za pomocą **mapy wartości** z ustawienia Jednostka, na przykład [Sztuka: 0] i [Funt: 2].</span><span class="sxs-lookup"><span data-stu-id="d0858-144">If you require different values per UOM, this can be done with **ValueMap** from Unit, for example, [Each : 0] & [Pound : 2].</span></span>

    -   <span data-ttu-id="d0858-145">Wartość domyślna w szablonie to 0.</span><span class="sxs-lookup"><span data-stu-id="d0858-145">Template value is defaulted to 0.</span></span>

-   <span data-ttu-id="d0858-146">Zaktualizuj pole **Identyfikator organizacji CDS Organization_OrganizationId** w mapowaniu **Źródło -\> CDS**.</span><span class="sxs-lookup"><span data-stu-id="d0858-146">Update the **CDS Organization ID Organization_OrganizationId** in **Source -\> CDS**.</span></span>

    -   <span data-ttu-id="d0858-147">Wartość domyślna w szablonie to ORG001.</span><span class="sxs-lookup"><span data-stu-id="d0858-147">Template value is defaulted to ORG001.</span></span>

-   <span data-ttu-id="d0858-148">Zaktualizuj **mapę wartości** dla **grupy jednostek** (**defaultuomscheduleid.name**) w mapowaniu **CDS -\> Miejsce docelowe**, aby pasowała do **grupy jednostek** w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="d0858-148">Update **ValueMap** for **Unit group** (**defaultuomscheduleid.name**) in **CDS -\> Destination** to match the **Unit groups** in Sales.</span></span>

    -   <span data-ttu-id="d0858-149">Wartość domyślna w szablonie to **Jednostka domyślna**.</span><span class="sxs-lookup"><span data-stu-id="d0858-149">Template value is defaulted to **Default unit**.</span></span>

-   <span data-ttu-id="d0858-150">Upewnij się, że jednostki miar wszystkich sprzedawanych produktów z programu Finance and Operations istnieją w aplikacji Sales z wartością **Listy wyboru w usłudze CDS**.</span><span class="sxs-lookup"><span data-stu-id="d0858-150">Ensure that all products selling UOMs from Finance and Operations exist in Sales with the **CDS picklists** value.</span></span>

-   <span data-ttu-id="d0858-151">Upewnij się, że **cenniki** istnieją w aplikacji Sales dla każdej waluty sprzedaży produktów w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d0858-151">Ensure that **Price lists** exist in Sales for each product sales currency in Finance and Operations.</span></span>

-   <span data-ttu-id="d0858-152">Produkty można tworzyć w aplikacji Sales ze stanem **Wersja robocza** lub **Aktywny**.</span><span class="sxs-lookup"><span data-stu-id="d0858-152">Products can be created in Sales with status **Draft** or **Active**.</span></span> <span data-ttu-id="d0858-153">Można to kontrolować w oknie **Ustawienia systemowe** w obszarze **Sprzedaż** w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="d0858-153">This is controlled in **System settings** under **Sales** in Sales.</span></span>

    -   <span data-ttu-id="d0858-154">Produkty utworzone w stanie Wersja robocza muszą zostać uaktywnione, zanim będzie je można dodać do **oferty** lub **zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="d0858-154">Products created with draft status need to be activated before they can be added to **Quote** or **Sales order**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="d0858-155">Mapowanie szablonu w integratorze danych</span><span class="sxs-lookup"><span data-stu-id="d0858-155">Template mapping in data integrator</span></span>

<span data-ttu-id="d0858-156">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="d0858-156">The following illustrations show an example of a template mapping in data integrator.</span></span>

![mapowanie szablonu w integratorze danych](./media/products-template-mapping-data-integrator-1.png)

![mapowanie szablonu dla produktów w integratorze danych](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="d0858-159">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="d0858-159">Related topics</span></span>

[<span data-ttu-id="d0858-160">Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d0858-160">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="d0858-161">Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d0858-161">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="d0858-162">Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d0858-162">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)


