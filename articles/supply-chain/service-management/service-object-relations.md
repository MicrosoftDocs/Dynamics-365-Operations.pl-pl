---
title: Relacje przedmiotów serwisu
description: Można utworzyć relacje przedmiotów serwisu oraz umowę serwisową lub zlecenie serwisowe.
author: ShylaThompson
manager: tfehr
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c196a070d1e18b2cc14c54eda0fe0aad5346d93
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215132"
---
# <a name="service-object-relations"></a><span data-ttu-id="35e95-103">Relacje przedmiotów serwisu</span><span class="sxs-lookup"><span data-stu-id="35e95-103">Service object relations</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35e95-104">Można utworzyć relacje przedmiotów serwisu oraz umowę serwisową lub zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="35e95-104">You can create service object relations between a service object and a service agreement or service order.</span></span> <span data-ttu-id="35e95-105">Podczas tworzenia relacji przedmiot serwisu łączy się z umową serwisową lub zleceniem serwisowym.</span><span class="sxs-lookup"><span data-stu-id="35e95-105">When you create a relation, you attach the service object to the service agreement or service order.</span></span>

<span data-ttu-id="35e95-106">Po utworzeniu relacji można połączyć przedmiot serwisu z dowolnymi wierszami umowy serwisowej lub zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="35e95-106">After the relation is created, you can attach the service object to any lines on the service agreement or service order.</span></span>

## <a name="template-boms"></a><span data-ttu-id="35e95-107">Szablony BOM</span><span class="sxs-lookup"><span data-stu-id="35e95-107">Template BOMs</span></span>

<span data-ttu-id="35e95-108">Można także określić szablon BOM dla relacji przedmiotu.</span><span class="sxs-lookup"><span data-stu-id="35e95-108">You can also specify a template BOM for the object relation.</span></span> <span data-ttu-id="35e95-109">Szablon BOM dotyczy przedmiotu serwisu.</span><span class="sxs-lookup"><span data-stu-id="35e95-109">The template BOM is a bill of materials for the object on which you perform service.</span></span> <span data-ttu-id="35e95-110">W przypadku wymiany części przedmiotu serwisu w czasie wizyty serwisowej można zarejestrować na liście BOM usługi serwisowej przy użyciu formularza Przedmioty serwisu.</span><span class="sxs-lookup"><span data-stu-id="35e95-110">If you replace a component part of the service object during a service visit, you can register this change in the service BOM by using the Service objects form.</span></span>

## <a name="example"></a><span data-ttu-id="35e95-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="35e95-111">Example</span></span>

<span data-ttu-id="35e95-112">Tworzona jest umowa serwisowa dotycząca serwisu dwóch wind w siedzibie klienta.</span><span class="sxs-lookup"><span data-stu-id="35e95-112">You create a service agreement for servicing two elevators at a customer site.</span></span>
<span data-ttu-id="35e95-113">Umowa serwisowa ma identyfikator ID SAL-001.</span><span class="sxs-lookup"><span data-stu-id="35e95-113">The service agreement has the identifier ID SAL-001.</span></span>

<span data-ttu-id="35e95-114">Windy skonfigurowano w formularzu Przedmioty serwisu jako obiekty EL-S/1000 i EL-L/1000.</span><span class="sxs-lookup"><span data-stu-id="35e95-114">The elevators are set up in the Service objects form as objects, EL-S/1000 and EL-L/1000.</span></span>

<span data-ttu-id="35e95-115">Przedmioty serwisu EL-S/1000 i EL-L/1000 należy połączyć z umową serwisową.</span><span class="sxs-lookup"><span data-stu-id="35e95-115">You attach the service objects, EL-S/1000 and EL-L/1000, to the service agreement.</span></span>

<span data-ttu-id="35e95-116">Zmiany dotyczące przedmiotu serwisu zostaną zarejestrowane w BOM podczas wymiany części przedmiotu, więc lista BOM usługi zostanie połączona z relacją przedmiotu serwisu zgodnie z następującą tabelą.</span><span class="sxs-lookup"><span data-stu-id="35e95-116">You want to register changes in the BOM for the service object as you replace component parts of the object, so you attach a service BOM to the service object relation, as described in the following table.</span></span>

| <span data-ttu-id="35e95-117">Przedmiot serwisu</span><span class="sxs-lookup"><span data-stu-id="35e95-117">Service object</span></span> | <span data-ttu-id="35e95-118">Relacja — Umowa serwisowa</span><span class="sxs-lookup"><span data-stu-id="35e95-118">Relation – Service agreement</span></span> | <span data-ttu-id="35e95-119">BOM serwisu</span><span class="sxs-lookup"><span data-stu-id="35e95-119">Service BOM</span></span>   |
|----------------|------------------------------|---------------|
| <span data-ttu-id="35e95-120">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-120">EL-S/1000</span></span>      | <span data-ttu-id="35e95-121">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="35e95-121">ID SAL-001</span></span>                   | <span data-ttu-id="35e95-122">BOM-EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-122">BOM-EL-S/1000</span></span> |
| <span data-ttu-id="35e95-123">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-123">EL-L/1000</span></span>      | <span data-ttu-id="35e95-124">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="35e95-124">ID SAL-001</span></span>                   | <span data-ttu-id="35e95-125">BOM-EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-125">BOM-EL-L/1000</span></span> |

<span data-ttu-id="35e95-126">Dla umowy występują relacje przedmiotów serwisu, więc można utworzyć wiersze umowy serwisowej zawierające te przedmioty, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="35e95-126">Because there are service object relations for the agreement, you can now create service agreement lines with these objects, as shown in the following table.</span></span>

| <span data-ttu-id="35e95-127">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="35e95-127">Transaction type</span></span> | <span data-ttu-id="35e95-128">Kategoria</span><span class="sxs-lookup"><span data-stu-id="35e95-128">Category</span></span>           | <span data-ttu-id="35e95-129">Przedmiot serwisu</span><span class="sxs-lookup"><span data-stu-id="35e95-129">Service object</span></span> |
|------------------|--------------------|----------------|
| <span data-ttu-id="35e95-130">Godzina</span><span class="sxs-lookup"><span data-stu-id="35e95-130">Hour</span></span>             | <span data-ttu-id="35e95-131">Kontrola</span><span class="sxs-lookup"><span data-stu-id="35e95-131">Inspection</span></span>         | <span data-ttu-id="35e95-132">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-132">EL-S/1000</span></span>      |
| <span data-ttu-id="35e95-133">Godzina</span><span class="sxs-lookup"><span data-stu-id="35e95-133">Hour</span></span>             | <span data-ttu-id="35e95-134">Czyszczenie skrzynki przekładniowej</span><span class="sxs-lookup"><span data-stu-id="35e95-134">Gear box cleaning</span></span>  | <span data-ttu-id="35e95-135">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-135">EL-S/1000</span></span>      |
| <span data-ttu-id="35e95-136">Element</span><span class="sxs-lookup"><span data-stu-id="35e95-136">Item</span></span>             | <span data-ttu-id="35e95-137">Materiały czyszczące</span><span class="sxs-lookup"><span data-stu-id="35e95-137">Cleaning materials</span></span> | <span data-ttu-id="35e95-138">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-138">EL-S/1000</span></span>      |
| <span data-ttu-id="35e95-139">Godzina</span><span class="sxs-lookup"><span data-stu-id="35e95-139">Hour</span></span>             | <span data-ttu-id="35e95-140">Kontrola</span><span class="sxs-lookup"><span data-stu-id="35e95-140">Inspection</span></span>         | <span data-ttu-id="35e95-141">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-141">EL-L/1000</span></span>      |
| <span data-ttu-id="35e95-142">Godzina</span><span class="sxs-lookup"><span data-stu-id="35e95-142">Hour</span></span>             | <span data-ttu-id="35e95-143">Czyszczenie skrzynki przekładniowej</span><span class="sxs-lookup"><span data-stu-id="35e95-143">Gearbox cleaning</span></span>   | <span data-ttu-id="35e95-144">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-144">EL-L/1000</span></span>      |
| <span data-ttu-id="35e95-145">Element</span><span class="sxs-lookup"><span data-stu-id="35e95-145">Item</span></span>             | <span data-ttu-id="35e95-146">Materiały czyszczące</span><span class="sxs-lookup"><span data-stu-id="35e95-146">Cleaning materials</span></span> | <span data-ttu-id="35e95-147">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="35e95-147">EL-L/1000</span></span>      |

<span data-ttu-id="35e95-148">W czasie wizyty serwisowej należy wymienić skrzynkę przekładniową windy EL-S/1000.</span><span class="sxs-lookup"><span data-stu-id="35e95-148">On a service visit, you have to replace the gearbox for elevator EL-S/1000.</span></span> <span data-ttu-id="35e95-149">Aby wymienić część przedmiotu, należy uzyskać dostęp do Konstruktora BOM, używając relacji przedmiotu serwisu, która została skonfigurowana dla bieżącej umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="35e95-149">To replace a component part of the object, you can access the BOM Designer by using the service object relation that you set up for the current service agreement.</span></span>

<span data-ttu-id="35e95-150">Uzyskiwanie dostępu do Konstruktora BOM przy użyciu relacji przedmiotu serwisu</span><span class="sxs-lookup"><span data-stu-id="35e95-150">Access the BOM Designer by using a service object relation</span></span>

1. <span data-ttu-id="35e95-151">Umowy serwisowe</span><span class="sxs-lookup"><span data-stu-id="35e95-151">Service agreements</span></span>
2. <span data-ttu-id="35e95-152">Kliknij dwukrotnie umowę serwisową lub kliknij opcję Umowa serwisowa, aby utworzyć umowę serwisową.</span><span class="sxs-lookup"><span data-stu-id="35e95-152">Double-click a service agreement, or click Service agreement to create a service agreement.</span></span>
3. <span data-ttu-id="35e95-153">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="35e95-153">Click the Setup tab.</span></span>
4. <span data-ttu-id="35e95-154">Kliknij opcję Przedmioty serwisu, aby dołączyć szablon BOM do umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="35e95-154">Click Service objects to attach a template BOM to the service agreement.</span></span>
5. <span data-ttu-id="35e95-155">W formularzu Przedmioty serwisu kliknij opcję Projektant, aby otworzyć formularz Projektant i w nim zmodyfikować szablon BOM.</span><span class="sxs-lookup"><span data-stu-id="35e95-155">In the Service objects form, click Designer to open the Designer form to modify the template BOM.</span></span>

## <a name="automatically-created-service-orders"></a><span data-ttu-id="35e95-156">Zlecenia serwisowe tworzone automatycznie</span><span class="sxs-lookup"><span data-stu-id="35e95-156">Automatically created service orders</span></span>

<span data-ttu-id="35e95-157">W przypadku automatycznego tworzenia zleceń serwisowych dotyczących umowy serwisowej relacje przedmiotów serwisu w umowie znajdują się także w tworzonych zleceniach serwisowych.</span><span class="sxs-lookup"><span data-stu-id="35e95-157">If you automatically create service orders for a service agreement, the service object relations in the agreement are also created in the service orders.</span></span>

