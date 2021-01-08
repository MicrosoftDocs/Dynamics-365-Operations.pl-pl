---
title: Definiowanie i obsługa kanałów sprzedaży detalicznej
description: Ten artykuł zawiera omówienie procesu konfigurowania sklepów tradycyjnych (fizycznych), określanych jako „sklepy” w Dynamics 365 Commerce. Znajdują się tu informacje o zadaniach, które należy wykonać przed i po skonfigurowaniu sklepu.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0fbca2c9178cd372653287afdf72deaf75442604
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414858"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="0424f-104">Definiowanie i obsługa kanałów sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="0424f-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0424f-105">Ten artykuł zawiera omówienie procesu konfigurowania sklepów tradycyjnych (fizycznych), określanych jako „sklepy” w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0424f-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as stores in Dynamics 365 Commerce.</span></span> <span data-ttu-id="0424f-106">Znajdują się tu informacje o zadaniach, które należy wykonać przed i po skonfigurowaniu sklepu.</span><span class="sxs-lookup"><span data-stu-id="0424f-106">It includes information about the tasks that you must complete both before and after you set up a store.</span></span>

<span data-ttu-id="0424f-107">Commerce obsługuje wiele kanałów, takich jak sklepy internetowe, sklepy tradycyjne i biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="0424f-107">Commerce supports multiple channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="0424f-108">Sklep tradycyjny jest nazywany sklepem.</span><span class="sxs-lookup"><span data-stu-id="0424f-108">A brick-and-mortar store is called a store.</span></span> <span data-ttu-id="0424f-109">Każdy sklep ma własne metody płatności, grupy cenowe, kasy punktów sprzedaży, konta przychodów i wydatków oraz personel.</span><span class="sxs-lookup"><span data-stu-id="0424f-109">Each store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="0424f-110">Wszystkie te elementy sklepu należy skonfigurować przed jego utworzeniem.</span><span class="sxs-lookup"><span data-stu-id="0424f-110">You must set up all these elements for a store before you create it.</span></span> <span data-ttu-id="0424f-111">Po utworzeniu sklepu, można przypisać produkty, które mają trafić do sklepu.</span><span class="sxs-lookup"><span data-stu-id="0424f-111">After you create the store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="0424f-112">Rejestry, pracowników i odbiorców również można przypisać do sklepu.</span><span class="sxs-lookup"><span data-stu-id="0424f-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="0424f-113">Na koniec należy dodać nowy sklep do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="0424f-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-stores"></a><span data-ttu-id="0424f-114">Konfigurowanie sklepów</span><span class="sxs-lookup"><span data-stu-id="0424f-114">Setting up stores</span></span>

<span data-ttu-id="0424f-115">Przed skonfigurowaniem sklepu w Commerce należy wykonać niektóre zadania wymagań wstępnych.</span><span class="sxs-lookup"><span data-stu-id="0424f-115">Before you can set up a store in Commerce, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="0424f-116">Następnie można utworzyć sklep i dodać szczegóły.</span><span class="sxs-lookup"><span data-stu-id="0424f-116">You can then create the store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="0424f-117">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="0424f-117">Prerequisites</span></span>

<span data-ttu-id="0424f-118">Przed skonfigurowaniem sklepu należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="0424f-118">You must complete the following tasks before you can set up a store:</span></span>

1. <span data-ttu-id="0424f-119">Konfigurowanie struktury organizacji i hierarchii organizacyjnych dla asortymentów sieci sprzedaży, uzupełnień i raportowania.</span><span class="sxs-lookup"><span data-stu-id="0424f-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="0424f-120">Konfigurowanie magazynu reprezentującego sklep.</span><span class="sxs-lookup"><span data-stu-id="0424f-120">Set up a warehouse that represents the store.</span></span>
3. <span data-ttu-id="0424f-121">Konfigurowanie sekwencji identyfikatorów dla sklepów, zestawień dotyczących sklepu i załączników do zestawień.</span><span class="sxs-lookup"><span data-stu-id="0424f-121">Set up number sequences for stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="0424f-122">Konfigurowanie parametrów Commerce.</span><span class="sxs-lookup"><span data-stu-id="0424f-122">Configure parameters for Commerce.</span></span>
5. <span data-ttu-id="0424f-123">Konfigurowanie metod płatności, które akceptuje sklep.</span><span class="sxs-lookup"><span data-stu-id="0424f-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="0424f-124">Do przetwarzania transakcji karty kredytowej w kasach punktów sprzedaży (POS)można też skonfigurować usługi płatności.</span><span class="sxs-lookup"><span data-stu-id="0424f-124">To process credit card transactions at POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="0424f-125">Konfigurowanie grup podatków.</span><span class="sxs-lookup"><span data-stu-id="0424f-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="0424f-126">Konfigurowanie produktów.</span><span class="sxs-lookup"><span data-stu-id="0424f-126">Set up products.</span></span> <span data-ttu-id="0424f-127">W ramach tego zadania należy także skonfigurować hierarchie produktów, asortymentów produktów i wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="0424f-127">As part of this task, you also set up product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="0424f-128">Konfigurowanie grup cenowych produktów.</span><span class="sxs-lookup"><span data-stu-id="0424f-128">Set up product price groups.</span></span>
10. <span data-ttu-id="0424f-129">Ustawianie cen produktu.</span><span class="sxs-lookup"><span data-stu-id="0424f-129">Set up product pricing.</span></span> <span data-ttu-id="0424f-130">W ramach tego zadania można również ustawić korekty cen, rabaty i okresy rabatu.</span><span class="sxs-lookup"><span data-stu-id="0424f-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="0424f-131">Konfigurowanie członków personelu.</span><span class="sxs-lookup"><span data-stu-id="0424f-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0424f-132">Należy również przypisać odpowiednie uprawnienia dla pracowników, tak aby mogli logować się i wykonywać zadania za pomocą systemu POS.</span><span class="sxs-lookup"><span data-stu-id="0424f-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the POS system.</span></span>

12. <span data-ttu-id="0424f-133">Konfigurowanie profilów POS, które mają zostać przypisane do danego sklepu.</span><span class="sxs-lookup"><span data-stu-id="0424f-133">Configure the POS profiles to assign to the store.</span></span> <span data-ttu-id="0424f-134">Konfigurowanie profilów obejmuje wiele zadań, takich jak konfigurowanie rejestrów, konfigurowanie profilów trybu offline i konfigurowanie profilów i formatów paragonu.</span><span class="sxs-lookup"><span data-stu-id="0424f-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="0424f-135">Przejrzyj wszystkie zadania zawarte w wymaganiach wstępnych i wykonaj tylko te, które odnoszą się do Ciebie.</span><span class="sxs-lookup"><span data-stu-id="0424f-135">Review all the tasks that are included in the prerequisites, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-store"></a><span data-ttu-id="0424f-136">Ustawianie sklepu</span><span class="sxs-lookup"><span data-stu-id="0424f-136">Set up a store</span></span>

<span data-ttu-id="0424f-137">Po zakończeniu zadania wymagań wstępnych wykonaj te zadania, aby skonfigurować szczegóły sklepu:</span><span class="sxs-lookup"><span data-stu-id="0424f-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the store:</span></span>

1. <span data-ttu-id="0424f-138">Utworzyć sklep.</span><span class="sxs-lookup"><span data-stu-id="0424f-138">Create a store.</span></span>
2. <span data-ttu-id="0424f-139">Przypisywanie grupy podatków do sklepu.</span><span class="sxs-lookup"><span data-stu-id="0424f-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="0424f-140">Przypisywanie akceptowanych metod płatności do sklepu.</span><span class="sxs-lookup"><span data-stu-id="0424f-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="0424f-141">Dodawanie szczegółów do opisów produktów dla produktów, które oferujesz w sklepach.</span><span class="sxs-lookup"><span data-stu-id="0424f-141">Add details to the product descriptions for products that you offer in your stores.</span></span> <span data-ttu-id="0424f-142">Na przykład można dodawać obrazy i tekst sformatowany RTF.</span><span class="sxs-lookup"><span data-stu-id="0424f-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="0424f-143">Te informacje szczegółowe o produkcie są wyświetlane w różnych kontekstach, takich jak kasy w punkcie sprzedaży lub wydrukowane etykiety.</span><span class="sxs-lookup"><span data-stu-id="0424f-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="0424f-144">Dodawanie sklepu sieci sprzedaży do domyślnej hierarchii organizacyjnej przypisanej do celu **Asortyment sieci sprzedaży**, **Uzupełnianie zapasów sieci sprzedaży** lub **Raportowanie sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="0424f-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-store"></a><span data-ttu-id="0424f-145">Po skonfigurowaniu sklepu</span><span class="sxs-lookup"><span data-stu-id="0424f-145">After you set up a store</span></span>

<span data-ttu-id="0424f-146">Po wprowadzeniu szczegółów sklepu zakończ te zadania, aby wysłać nowe dane sklepu do POS:</span><span class="sxs-lookup"><span data-stu-id="0424f-146">After you enter the details for the store, complete these tasks to send the new store data to POS:</span></span>

1. <span data-ttu-id="0424f-147">Konfigurowanie kas w punkcie sprzedaży dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="0424f-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="0424f-148">Dodawanie asortymentów produktów do sklepu.</span><span class="sxs-lookup"><span data-stu-id="0424f-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="0424f-149">Przetwarzanie asortymentów, aby wygenerować listę produktów, które są uwzględnione w asortymencie i aby udostępnić produkty w sklepie.</span><span class="sxs-lookup"><span data-stu-id="0424f-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the store.</span></span>
4. <span data-ttu-id="0424f-150">Wysyłanie danych, takich jak sekwencje numerów, profile sprzętu, układy ekranu punktu sprzedaży do kas POS.</span><span class="sxs-lookup"><span data-stu-id="0424f-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the POS registers.</span></span>
5. <span data-ttu-id="0424f-151">Publikowanie sklepu, aby wysyłać dane sklepu do POS.</span><span class="sxs-lookup"><span data-stu-id="0424f-151">Publish the store to send store data to POS.</span></span>
6. <span data-ttu-id="0424f-152">Uruchamianie zadań, aby wysyłać dane sklepu do POS.</span><span class="sxs-lookup"><span data-stu-id="0424f-152">Run the jobs to send the store data to POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="0424f-153">Hierarchie organizacyjne</span><span class="sxs-lookup"><span data-stu-id="0424f-153">Organization hierarchies</span></span>

<span data-ttu-id="0424f-154">Commerce używa hierarchii organizacji do tworzenia struktury w kanałach.</span><span class="sxs-lookup"><span data-stu-id="0424f-154">Commerce uses organization hierarchies to structure channels.</span></span> <span data-ttu-id="0424f-155">Hierarchie organizacji reprezentują relacje między organizacjami, które składają się na działalność.</span><span class="sxs-lookup"><span data-stu-id="0424f-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="0424f-156">Podczas konfigurowania sklepów, można je dodawać do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="0424f-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="0424f-157">Sklepy współdzielą wówczas dane używane do asortymentów, uzupełnienia i raportów.</span><span class="sxs-lookup"><span data-stu-id="0424f-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>

> [!NOTE]
> <span data-ttu-id="0424f-158">Aby korzystać z funkcji sprzedaży w aplikacji Commerce, klucz konfiguracji dla opcji **Wielokrotna wysyłka** musi być włączony.</span><span class="sxs-lookup"><span data-stu-id="0424f-158">To use Commerce sales functionality, the configuration key for **Multiple ship-to** must be enabled.</span></span> <span data-ttu-id="0424f-159">Ten klucz konfiguracji można znaleźć w kluczach **konfiguracji handlu** w obszarze **Administracja systemem**\> **Instalator** \> **Konfiguracja licencji**.</span><span class="sxs-lookup"><span data-stu-id="0424f-159">This configuration key can be found in the **Trade configuration** keys under **System Administration**\> **Setup** \> **License Configuration**.</span></span> <span data-ttu-id="0424f-160">Jest to wymagane z powodu różnych operacji weryfikacji na podstawie adresu dostawy skonfigurowanego na poziomie wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0424f-160">This is required due to various validations based on the delivery address configured at the sales order line level.</span></span>

