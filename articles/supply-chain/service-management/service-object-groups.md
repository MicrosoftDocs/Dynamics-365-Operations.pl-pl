---
title: Grupy przedmiotów serwisu
description: Grupy przedmiotów serwisu są przydatne do sortowania i filtrowania danych o przedmiotach serwisu do wykorzystania w raportach i statystykach.
author: ShylaThompson
manager: tfehr
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4438487fa234cf093b557bca9455717b2cd3ca0b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434911"
---
# <a name="service-object-groups"></a><span data-ttu-id="68cda-103">Grupy przedmiotów serwisu</span><span class="sxs-lookup"><span data-stu-id="68cda-103">Service object groups</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="68cda-104">Grupy przedmiotów serwisu są przydatne do sortowania i filtrowania danych o przedmiotach serwisu do wykorzystania w raportach i statystykach.</span><span class="sxs-lookup"><span data-stu-id="68cda-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="68cda-105">Na przykład można grupować obiekty według lokalizacji geograficznej lub według typu.</span><span class="sxs-lookup"><span data-stu-id="68cda-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="68cda-106">Grupowanie według lokalizacji geograficznych</span><span class="sxs-lookup"><span data-stu-id="68cda-106">Group by geographical location</span></span>

<span data-ttu-id="68cda-107">Tej metody grupowania można użyć w celu pokazania, gdzie są zlokalizowane różne przedmioty serwisowane przez firmę.</span><span class="sxs-lookup"><span data-stu-id="68cda-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="68cda-108">Grupowanie przedmiotów serwisu według lokalizacji geograficznych może być również przydatne, jeśli na przykład trzeba wskazać przedmioty, które firma już serwisuje w określonym kraju/regionie.</span><span class="sxs-lookup"><span data-stu-id="68cda-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="68cda-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="68cda-109">Example</span></span>

<span data-ttu-id="68cda-110">Klient z Belgii dzwoni do centrum serwisowego i chce zawrzeć umowę serwisową dotyczącą przedmiotu ABC.</span><span class="sxs-lookup"><span data-stu-id="68cda-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="68cda-111">Grupę przedmiotów serwisu odpowiadającą lokalizacji geograficznej Belgia dołączono do wszystkich obiektów serwisowanych w Belgii.</span><span class="sxs-lookup"><span data-stu-id="68cda-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="68cda-112">Używając tej grupy jako filtru, można szybko stwierdzić, czy przedmiot ABC już istnieje jako rekord w programie lub czy trzeba skonfigurować nowy przedmiot.</span><span class="sxs-lookup"><span data-stu-id="68cda-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="68cda-113">Grupowanie według typów</span><span class="sxs-lookup"><span data-stu-id="68cda-113">Group by type</span></span>

<span data-ttu-id="68cda-114">Tej metody grupowania można użyć w celu pokazania typów przedmiotów serwisowanych przez firmę.</span><span class="sxs-lookup"><span data-stu-id="68cda-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="68cda-115">Grupowanie przedmiotów serwisu według typów może być również przydatne do tworzenia nowych przedmiotów na podstawie podobnych przedmiotów już istniejących w programie.</span><span class="sxs-lookup"><span data-stu-id="68cda-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="68cda-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="68cda-116">Example</span></span>

<span data-ttu-id="68cda-117">Klient dzwoni w sprawie zawarcia umowy serwisowej dotyczącej urządzenia do klimatyzacji, HIJ.</span><span class="sxs-lookup"><span data-stu-id="68cda-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="68cda-118">Nie masz jeszcze rekordu dla tej maszyny.</span><span class="sxs-lookup"><span data-stu-id="68cda-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="68cda-119">Jednak skonfigurowano już grupę przedmiotów serwisu o nazwie Klimatyzatory i dołączono tę grupę do wszystkich przedmiotów związanych z klimatyzacją.</span><span class="sxs-lookup"><span data-stu-id="68cda-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="68cda-120">W związku z tym można szybko wyszukać i zidentyfikować wszystkie urządzenia do klimatyzacji oraz użyć informacji o tych przedmiotach jako szablonu do utworzenia wierszy umowy serwisowej dotyczącej urządzenia HIJ.</span><span class="sxs-lookup"><span data-stu-id="68cda-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="68cda-121">Korzystanie z grup przedmiotów w ten sposób pozwala szybko konfigurować nowe przedmioty serwisu i ustalać zadania serwisowe, które trzeba na nich wykonywać.</span><span class="sxs-lookup"><span data-stu-id="68cda-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 

## <a name="create-service-object-groups"></a><span data-ttu-id="68cda-122">Tworzenie grup przedmiotów serwisu</span><span class="sxs-lookup"><span data-stu-id="68cda-122">Create service object groups</span></span>

<span data-ttu-id="68cda-123">Można utworzyć grupy, do których będą przypisywane przedmioty serwisu.</span><span class="sxs-lookup"><span data-stu-id="68cda-123">Create groups that you can assign service objects to.</span></span> <span data-ttu-id="68cda-124">Przedmioty serwisu są pozycjami magazynowymi i innymi produktami, dla których usługi są wykonywane.</span><span class="sxs-lookup"><span data-stu-id="68cda-124">Service objects are inventory items and other products for which services are performed.</span></span> <span data-ttu-id="68cda-125">Grupowanie przedmiotów serwisu umożliwia tworzenie raportów dotyczących podobnych i powiązanych przedmiotów serwisu.</span><span class="sxs-lookup"><span data-stu-id="68cda-125">By grouping service objects, you can create reports for similar and related service objects.</span></span> <span data-ttu-id="68cda-126">Na przykład, grupa przedmiotów serwisu może składać się z dwóch przedmiotów serwisu: jeden przedmiot serwisu jest zestawem, a drugi przedmiotu serwisu jest usługą montażu zestawu.</span><span class="sxs-lookup"><span data-stu-id="68cda-126">For example, a service object group might consist of two service objects: One service object is a kit, and the second service object is the service to install the kit.</span></span>

<span data-ttu-id="68cda-127">Aby utworzyć grupy przedmiotów serwisu, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="68cda-127">To create service object groups, follow these steps:</span></span>

1. <span data-ttu-id="68cda-128">Kliknij kolejno opcje **Zarządzanie serwisem > Ustawienia > Przedmioty serwisu > Grupy przedmiotów serwisu**.</span><span class="sxs-lookup"><span data-stu-id="68cda-128">Click **Service management > Setup > Service objects > Service object groups**.</span></span>

2. <span data-ttu-id="68cda-129">Kliknij przycisk **Nowy**, aby utworzyć nową grupę przedmiotów serwisu.</span><span class="sxs-lookup"><span data-stu-id="68cda-129">Click **New** to create a new service object group.</span></span>

3. <span data-ttu-id="68cda-130">Wprowadź niepowtarzalną nazwę grupy przedmiotów serwisu oraz jej opis (opcjonalny).</span><span class="sxs-lookup"><span data-stu-id="68cda-130">Enter a unique name for the service object group and, optionally, a description.</span></span>

<span data-ttu-id="68cda-131">Przedmioty serwisu można przypisać do grupy za pomocą formularza **Przedmioty serwisu**.</span><span class="sxs-lookup"><span data-stu-id="68cda-131">You can assign service objects to the group by using the **Service objects** form.</span></span> 

## <a name="see-also"></a><span data-ttu-id="68cda-132">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="68cda-132">See also</span></span>

[<span data-ttu-id="68cda-133">Tworzenie przedmiotów serwisu</span><span class="sxs-lookup"><span data-stu-id="68cda-133">Create service objects</span></span>](create-service-objects.md)


