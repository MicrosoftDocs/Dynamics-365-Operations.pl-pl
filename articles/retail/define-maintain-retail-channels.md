---
title: Definiowanie i obsługa kanałów sprzedaży detalicznej
description: Ten artykuł zawiera omówienie procesu konfigurowania sklepów tradycyjnych (fizycznych), określanych jako „sklepy detaliczne” (sklepy sieci sprzedaży) w Dynamics 365 Retail. Znajdują się tu informacje o zadaniach, które należy wykonać przed i po skonfigurowaniu sklepu detalicznego.
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
ms.openlocfilehash: 45d0386d215da15103a417502debb245c91f6309
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934615"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="d730b-104">Definiowanie i obsługa kanałów sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="d730b-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d730b-105">Ten artykuł zawiera omówienie procesu konfigurowania sklepów tradycyjnych (fizycznych), określanych jako „sklepy detaliczne” (sklepy sieci sprzedaży) w Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="d730b-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as retail stores in Dynamics 365 Retail.</span></span> <span data-ttu-id="d730b-106">Znajdują się tu informacje o zadaniach, które należy wykonać przed i po skonfigurowaniu sklepu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="d730b-106">It includes information about the tasks that you must complete both before and after you set up a retail store.</span></span>

<span data-ttu-id="d730b-107">Retail obsługuje wiele kanałów sieci sprzedaży, takich jak sklepy internetowe, biura obsługi i sklepy tradycyjne.</span><span class="sxs-lookup"><span data-stu-id="d730b-107">Retail supports multiple retail channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="d730b-108">Sklep tradycyjny jest nazywany sklepem detalicznym.</span><span class="sxs-lookup"><span data-stu-id="d730b-108">A brick-and-mortar store is called a retail store.</span></span> <span data-ttu-id="d730b-109">Każdy sklep detaliczny ma własne metody płatności, grupy cenowe, kasy punktów sprzedaży, konta przychodów i wydatków oraz personel.</span><span class="sxs-lookup"><span data-stu-id="d730b-109">Each retail store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="d730b-110">Wszystkie te elementy sklepu detalicznego należy skonfigurować przed jego utworzeniem.</span><span class="sxs-lookup"><span data-stu-id="d730b-110">You must set up all these elements for a retail store before you create it.</span></span> <span data-ttu-id="d730b-111">Po utworzeniu sklepu detalicznego, można przypisać produkty, które mają trafić do sklepu.</span><span class="sxs-lookup"><span data-stu-id="d730b-111">After you create the retail store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="d730b-112">Rejestry, pracowników i odbiorców również można przypisać do sklepu.</span><span class="sxs-lookup"><span data-stu-id="d730b-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="d730b-113">Na koniec należy dodać nowy sklep do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="d730b-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-retail-stores"></a><span data-ttu-id="d730b-114">Konfigurowanie sklepów detalicznych</span><span class="sxs-lookup"><span data-stu-id="d730b-114">Setting up retail stores</span></span>

<span data-ttu-id="d730b-115">Przed skonfigurowaniem sklepu detalicznego w Retail należy wykonać niektóre zadania wymagań wstępnych.</span><span class="sxs-lookup"><span data-stu-id="d730b-115">Before you can set up a retail store in Retail, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="d730b-116">Następnie można utworzyć sklep detaliczny i dodać szczegóły.</span><span class="sxs-lookup"><span data-stu-id="d730b-116">You can then create the retail store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d730b-117">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="d730b-117">Prerequisites</span></span>

<span data-ttu-id="d730b-118">Przed skonfigurowaniem sklepu detalicznego należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="d730b-118">You must complete the following tasks before you can set up a retail store:</span></span>

1. <span data-ttu-id="d730b-119">Konfigurowanie struktury organizacji i hierarchii organizacyjnych dla asortymentów sieci sprzedaży, uzupełnień i raportowania.</span><span class="sxs-lookup"><span data-stu-id="d730b-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="d730b-120">Konfigurowanie magazynu reprezentującego sklep detaliczny.</span><span class="sxs-lookup"><span data-stu-id="d730b-120">Set up a warehouse that represents the retail store.</span></span>
3. <span data-ttu-id="d730b-121">Konfigurowanie sekwencji identyfikatorów dla sklepów detalicznych, zestawień dotyczących sklepu i załączników do zestawień.</span><span class="sxs-lookup"><span data-stu-id="d730b-121">Set up number sequences for retail stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="d730b-122">Konfigurowanie parametrów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="d730b-122">Configure parameters for Retail.</span></span>
5. <span data-ttu-id="d730b-123">Konfigurowanie metod płatności, które akceptuje sklep.</span><span class="sxs-lookup"><span data-stu-id="d730b-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="d730b-124">Do przetwarzania transakcji karty kredytowej w kasach punktów sprzedaży (POS) detalicznej można też skonfigurować usługi płatności.</span><span class="sxs-lookup"><span data-stu-id="d730b-124">To process credit card transactions at retail POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="d730b-125">Konfigurowanie grup podatków.</span><span class="sxs-lookup"><span data-stu-id="d730b-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="d730b-126">Konfigurowanie produktów sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d730b-126">Set up retail products.</span></span> <span data-ttu-id="d730b-127">W ramach tego zadania należy także skonfigurować hierarchie produktów sieci sprzedaży, asortymentów produktów i wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="d730b-127">As part of this task, you also set up retail product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="d730b-128">Konfigurowanie grup cenowych produktów.</span><span class="sxs-lookup"><span data-stu-id="d730b-128">Set up product price groups.</span></span>
10. <span data-ttu-id="d730b-129">Konfigurowanie kalkulacji cen produktu sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d730b-129">Set up retail product pricing.</span></span> <span data-ttu-id="d730b-130">W ramach tego zadania można również ustawić korekty cen, rabaty i okresy rabatu.</span><span class="sxs-lookup"><span data-stu-id="d730b-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="d730b-131">Konfigurowanie członków personelu.</span><span class="sxs-lookup"><span data-stu-id="d730b-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d730b-132">Należy również przypisać odpowiednie uprawnienia dla pracowników, tak aby mogli logować się i wykonywać zadania za pomocą systemu Retail POS.</span><span class="sxs-lookup"><span data-stu-id="d730b-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the Retail POS system.</span></span>

12. <span data-ttu-id="d730b-133">Konfigurowanie profilów Retail POS, które mają zostać przypisane do danego sklepu.</span><span class="sxs-lookup"><span data-stu-id="d730b-133">Configure the Retail POS profiles to assign to the store.</span></span> <span data-ttu-id="d730b-134">Konfigurowanie profilów obejmuje wiele zadań, takich jak konfigurowanie rejestrów, konfigurowanie profilów trybu offline i konfigurowanie profilów i formatów paragonu.</span><span class="sxs-lookup"><span data-stu-id="d730b-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="d730b-135">Przejrzyj wszystkie zadania zawarte w wymaganiach wstępnych i wykonaj tylko te, które odnoszą się do Ciebie.</span><span class="sxs-lookup"><span data-stu-id="d730b-135">Review all the tasks that are included in the prerequisite, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-retail-store"></a><span data-ttu-id="d730b-136">Konfigurowanie sklepu sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d730b-136">Set up a retail store</span></span>

<span data-ttu-id="d730b-137">Po zakończeniu zadania wymagań wstępnych wykonaj te zadania, aby skonfigurować szczegóły sklepu detalicznego:</span><span class="sxs-lookup"><span data-stu-id="d730b-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the retail store:</span></span>

1. <span data-ttu-id="d730b-138">Tworzenie sklepu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="d730b-138">Create a retail store.</span></span>
2. <span data-ttu-id="d730b-139">Przypisywanie grupy podatków do sklepu.</span><span class="sxs-lookup"><span data-stu-id="d730b-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="d730b-140">Przypisywanie akceptowanych metod płatności do sklepu.</span><span class="sxs-lookup"><span data-stu-id="d730b-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="d730b-141">Dodawanie szczegółów do opisów produktów dla produktów, które oferujesz w sklepach detalicznych.</span><span class="sxs-lookup"><span data-stu-id="d730b-141">Add details to the product descriptions for products that you offer in your retail stores.</span></span> <span data-ttu-id="d730b-142">Na przykład można dodawać obrazy i tekst sformatowany RTF.</span><span class="sxs-lookup"><span data-stu-id="d730b-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="d730b-143">Te informacje szczegółowe o produkcie są wyświetlane w różnych kontekstach, takich jak kasy w punkcie sprzedaży lub wydrukowane etykiety.</span><span class="sxs-lookup"><span data-stu-id="d730b-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="d730b-144">Dodawanie sklepu sieci sprzedaży do domyślnej hierarchii organizacyjnej przypisanej do celu **Asortyment sieci sprzedaży**, **Uzupełnianie zapasów sieci sprzedaży** lub **Raportowanie sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="d730b-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-retail-store"></a><span data-ttu-id="d730b-145">Po skonfigurowaniu sklepu detalicznego</span><span class="sxs-lookup"><span data-stu-id="d730b-145">After you set up a retail store</span></span>

<span data-ttu-id="d730b-146">Po wprowadzeniu szczegółów sklepu detalicznego zakończ te zadania, aby wysłać nowe dane sklepu detalicznego do Retail POS.</span><span class="sxs-lookup"><span data-stu-id="d730b-146">After you enter the details for the retail store, complete these tasks to send the new retail store data to Retail POS:</span></span>

1. <span data-ttu-id="d730b-147">Konfigurowanie kas w punkcie sprzedaży dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="d730b-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="d730b-148">Dodawanie asortymentów produktów do sklepu.</span><span class="sxs-lookup"><span data-stu-id="d730b-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="d730b-149">Przetwarzanie asortymentów, aby wygenerować listę produktów, które są uwzględnione w asortymencie i aby udostępnić produkty w sklepie detalicznym.</span><span class="sxs-lookup"><span data-stu-id="d730b-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store.</span></span>
4. <span data-ttu-id="d730b-150">Wysyłanie danych, takich jak sekwencje numerów, profile sprzętu, układy ekranu punktu sprzedaży do kas Retail POS.</span><span class="sxs-lookup"><span data-stu-id="d730b-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.</span></span>
5. <span data-ttu-id="d730b-151">Publikowanie sklepu detalicznego, aby wysyłać dane sklepu do Retail POS.</span><span class="sxs-lookup"><span data-stu-id="d730b-151">Publish the retail store to send store data to Retail POS.</span></span>
6. <span data-ttu-id="d730b-152">Uruchamianie zadań, aby wysyłać dane sklepu do Retail POS.</span><span class="sxs-lookup"><span data-stu-id="d730b-152">Run the jobs to send the store data to Retail POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="d730b-153">Hierarchie organizacyjne</span><span class="sxs-lookup"><span data-stu-id="d730b-153">Organization hierarchies</span></span>

<span data-ttu-id="d730b-154">Moduł Handel detaliczny używa hierarchii organizacji do tworzenia struktury w kanałach sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="d730b-154">Retail uses organization hierarchies to structure retail channels.</span></span> <span data-ttu-id="d730b-155">Hierarchie organizacji reprezentują relacje między organizacjami, które składają się na działalność.</span><span class="sxs-lookup"><span data-stu-id="d730b-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="d730b-156">Podczas konfigurowania sklepów, można je dodawać do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="d730b-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="d730b-157">Sklepy współdzielą wówczas dane używane do asortymentów, uzupełnienia i raportów.</span><span class="sxs-lookup"><span data-stu-id="d730b-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>

> [!NOTE]
> <span data-ttu-id="d730b-158">Aby korzystać z funkcji sprzedaży w aplikacji Retail, klucz konfiguracji dla opcji **Wielokrotna wysyłka** musi być włączony.</span><span class="sxs-lookup"><span data-stu-id="d730b-158">To use Retail sales functionality, the configuration key for **Multiple ship-to** must be enabled.</span></span> <span data-ttu-id="d730b-159">Ten klucz konfiguracji można znaleźć w kluczach **konfiguracji handlu** w obszarze **Administracja systemem**\> **Instalator** \> **Konfiguracja licencji**.</span><span class="sxs-lookup"><span data-stu-id="d730b-159">This configuration key can be found in the **Trade configuration** keys under **System Administration**\> **Setup** \> **License Configuration**.</span></span> <span data-ttu-id="d730b-160">Jest to wymagane z powodu funkcji aplikacji Retail, która wykonuje różne operacje weryfikacji na podstawie adresu dostawy skonfigurowanego na poziomie wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d730b-160">This is required due to Retail functionality that performs various validations based on the delivery address configured at the sales order line level.</span></span>
