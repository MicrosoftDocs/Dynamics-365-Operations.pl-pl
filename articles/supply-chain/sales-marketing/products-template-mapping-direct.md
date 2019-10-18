---
title: Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Sales
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Dynamics 365 Supply Chain Management do Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 38f0db7db0cc4f65d46cd241f75a7274f19f62cf
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251392"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a><span data-ttu-id="c8f3f-103">Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="c8f3f-103">Synchronize products directly from Supply Chain Management to products in Sales</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="c8f3f-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="c8f3f-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="c8f3f-105">W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów bezpośrednio z Dynamics 365 Supply Chain Management do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="c8f3f-106">Przepływ danych w rozwiązaniu Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="c8f3f-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="c8f3f-107">Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="c8f3f-108">Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="c8f3f-109">Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="c8f3f-110">[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="c8f3f-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c8f3f-111">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="c8f3f-111">Templates and tasks</span></span>

<span data-ttu-id="c8f3f-112">Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="c8f3f-112">To access the available templates, open [PowerApps Admin Center](https://admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="c8f3f-113">Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="c8f3f-114">Następujący szablon i podstawowe zadanie są używane do synchronizowania kont klientów z usługi Supply Chain Management do Sales:</span><span class="sxs-lookup"><span data-stu-id="c8f3f-114">The following template and underlying tasks are used to synchronize products from Supply Chain Management to Sales.</span></span>

- <span data-ttu-id="c8f3f-115">**Nazwa szablonu w integracji danych:** Produkty (Supply Chain Management do Sales) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="c8f3f-115">**Name of the template in Data integration:** Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="c8f3f-116">**Nazwa zadania w projekcie integracji danych:** Produkty</span><span class="sxs-lookup"><span data-stu-id="c8f3f-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="c8f3f-117">Przed zsynchronizowaniem produktu nie jest wymagane wykonanie zadań synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="c8f3f-118">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="c8f3f-118">Entity set</span></span>

| <span data-ttu-id="c8f3f-119">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="c8f3f-119">Supply Chain Management</span></span>    | <span data-ttu-id="c8f3f-120">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="c8f3f-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="c8f3f-121">Zwolnione produkty możliwe do sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c8f3f-121">Sellable released products</span></span> | <span data-ttu-id="c8f3f-122">Produkty</span><span class="sxs-lookup"><span data-stu-id="c8f3f-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="c8f3f-123">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="c8f3f-123">Entity flow</span></span>

<span data-ttu-id="c8f3f-124">Produlty są zarządzane w usłudze Supply Chain Management i synchronizowane z usługą Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-124">Products are managed in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="c8f3f-125">Jednostka danych **Zwolnione produkty możliwe do sprzedaży** w rozwiązaniu Supply Chain Management eksportuje tylko produkty, które są *możliwe do sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-125">The **Sellable released products** data entity in Supply Chain Management exports only products that are *sellable*.</span></span> <span data-ttu-id="c8f3f-126">Produkty możliwe do sprzedaży to takie, które zawierają informacje wymagane w celu użycia w zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="c8f3f-127">Te same reguły mają zastosowanie podczas weryfikowania produktu przy użyciu funkcji **Sprawdzanie poprawności** na stronie **Zwolniony produkt**.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="c8f3f-128">Numer produktu jest używany jako klucz.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-128">The product number is used as a key.</span></span> <span data-ttu-id="c8f3f-129">Dlatego po zsynchronizowaniu wariantów produktu z rozwiązaniem Sales każdy wariant produktu ma indywidualny identyfikator produktu.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="c8f3f-130">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="c8f3f-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="c8f3f-131">W rozwiązaniu Sales dodano nowe pole **Obsługiwane zewnętrznie** w produktach, co wskazuje, że dany produkt jest obsługiwany zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="c8f3f-132">Domyślnie wartość jest ustawiana na **Tak** podczas importowania do rozwiązania Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="c8f3f-133">Dostępne są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c8f3f-133">The following values are available:</span></span>

- <span data-ttu-id="c8f3f-134">**Tak** — Produkt pochodził z rozwiązania Supply Chain Management i nie będzie można edytować w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-134">**Yes** – The product originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="c8f3f-135">**Nie**— produkt wprowadzono bezpośrednio w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="c8f3f-136">**(Puste)** — produkt istniał w rozwiązaniu Sales przed włączeniem rozwiązania Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="c8f3f-137">Pole **Obsługiwane zewnętrznie** pomaga zagwarantować, że z rozwiązaniem Supply Chain Management zostaną zsynchronizowane tylko oferty i zamówienia sprzedaży zawierające produkty obsługiwane zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-137">The **Is Externally Maintained** field helps ensure that only quotations and sales orders that have externally maintained products will be synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="c8f3f-138">Zewnętrznie obsługiwane produkty są automatycznie dodawane do pierwszego prawidłowego cennika o tej samej walucie.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="c8f3f-139">Cenniki są ułożone alfabetycznie według nazwy.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="c8f3f-140">Cena sprzedaży produktu z rozwiązania Supply Chain Management jest używana jako cena w cenniku.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-140">The product sales price from Supply Chain Management is used as the price on the price list.</span></span> <span data-ttu-id="c8f3f-141">Dlatego w rozwiązaniu Sales musi istnieć cennik dla każdej waluty sprzedaży produktów w rozwiązaniu Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-141">Therefore, there must be a price list in Sales for every product sales currency in Supply Chain Management.</span></span> <span data-ttu-id="c8f3f-142">Jako waluta w zwalnianych produktach możliwych do sprzedaży jest ustawiana waluta rozliczeniowa firmy, z której produkty zostały wyeksportowane.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> - <span data-ttu-id="c8f3f-143">Synchronizacja produktów nie powiedzie się, jeżeli nie będzie istniał cennik zawierający pasująca walutę.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-143">Product synchronization will not succeed unless there is a price list that has a matching currency.</span></span>
> - <span data-ttu-id="c8f3f-144">Cennikami używanymi w integracji można sterować poprzez zamapowanie elementu pricelevelid.name [Cennik domyślny (nazwa)] w projekcie narzędzia Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-144">You can control the used price list with the integration by mapping the pricelevelid.name [Default Price List (Name)] in the Data Integration project.</span></span> <span data-ttu-id="c8f3f-145">Dane wejściowe muszą zostać wprowadzone tylko małymi literami.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-145">The input has to be in all lowercase letters.</span></span> <span data-ttu-id="c8f3f-146">Na przykład w module Sales wartość domyślna cennika o nazwie „Standardowy” byłaby następująca: Pole docelowe: pricelevelid.name [Cennik domyślny (nazwa)] i typ mapowania: [ { "transformType": "Domyślnie", "defaultValue": "standardowy" } ].</span><span class="sxs-lookup"><span data-stu-id="c8f3f-146">For example, the default for a price list in Sales named ‘Standard’ would be: Destination field: pricelevelid.name [Default Price List (Name)] and Map type: [ { "transformType": "Default", "defaultValue": "standard" } ].</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="c8f3f-147">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="c8f3f-147">Preconditions and mapping setup</span></span>

- <span data-ttu-id="c8f3f-148">Przed uruchomieniem pierwszej synchronizacji należy wypełnić tabelę odrębnych produktów dla istniejących produktów w rozwiązaniu Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-148">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Supply Chain Management.</span></span> <span data-ttu-id="c8f3f-149">Istniejące produkty będą synchronizowane dopiero po zakończeniu tego zadania.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-149">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="c8f3f-150">W programie Supply Chain Management za pomocą funkcji wyszukiwania poszukaj opcji **Wypełnij tabelę odrębnych produktów**.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-150">In Supply Chain Management, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="c8f3f-151">Wybierz opcję **Wypełnij tabelę odrębnych produktów**, aby uruchomić zadanie.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-151">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="c8f3f-152">To zadanie należy uruchomić tylko raz.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-152">This job must be run only one time.</span></span>

- <span data-ttu-id="c8f3f-153">Upewnij się, że wymagana mapa wartości dla jednostki miary (JM) sprzedaży między rozwiązaniem Supply Chain Management a rozwiązaniem Sales istnieje w mapowaniu wartości **SalesUnitSymbol** na **DefaultUnit (Nazwa)**.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-153">Make sure that the required value map for the selling unit of measure (UOM) between Supply Chain Management and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="c8f3f-154">Zaktualizuj mapę wartości dla **grupy jednostek** (**defaultuomscheduleid.name**) tak, aby pasowała do **grupy jednostek** w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-154">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="c8f3f-155">Domyślna wartość szablonu to **Jednostka domyślna**.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-155">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="c8f3f-156">Upewnij się, że jednostki miar sprzedaży wszystkich produktów z rozwiązania Supply Chain Management istnieją w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-156">Make sure that the selling UOMs for all products from Supply Chain Management exist in Sales.</span></span>
- <span data-ttu-id="c8f3f-157">Upewnij się, że cenniki istnieją w rozwiązaniu Sales dla każdej waluty sprzedaży produktów w rozwiązaniu Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-157">Make sure that price lists exist in Sales for every product sales currency in Supply Chain Management.</span></span>
- <span data-ttu-id="c8f3f-158">Po utworzeniu produktów w rozwiązaniu Sales mogą mieć stan **Robocza** lub **Aktywne**.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-158">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="c8f3f-159">Zachowanie można kontrolować w oknie **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-159">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="c8f3f-160">Produkty mają stan **Robocza** po utworzeniu i należy je uaktywnić przed dodaniem do ofert lub zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-160">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c8f3f-161">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="c8f3f-161">Template mapping in Data integration</span></span>

<span data-ttu-id="c8f3f-162">Poniższa ilustracja przedstawia przykład mapowania szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-162">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="c8f3f-163">Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c8f3f-163">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

![Mapowanie szablonu w integratorze danych](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="c8f3f-165">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="c8f3f-165">Related topics</span></span>

[<span data-ttu-id="c8f3f-166">Od prospekta do gotówki</span><span class="sxs-lookup"><span data-stu-id="c8f3f-166">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="c8f3f-167">Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c8f3f-167">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="c8f3f-168">Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c8f3f-168">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="c8f3f-169">Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="c8f3f-169">Synchronize sales order headers and lines directly from Supply Chain Management to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="c8f3f-170">Synchronizowanie nagłówków faktur i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="c8f3f-170">Synchronize sales invoice headers and lines directly from Supply Chain ManagementSupply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



