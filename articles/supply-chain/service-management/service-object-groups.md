---
title: "Grupy przedmiotów serwisu"
description: "Grupy przedmiotów serwisu są przydatne do sortowania i filtrowania danych o przedmiotach serwisu do wykorzystania w raportach i statystykach."
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 221b9dae7e83e7f4a535ac60f2a2011533d7861c
ms.openlocfilehash: fa503ac82286099a0eafc7034d169e165b538e2c
ms.contentlocale: pl-pl
ms.lasthandoff: 02/21/2018

---

# <a name="service-object-groups"></a><span data-ttu-id="e1cda-103">Grupy przedmiotów serwisu</span><span class="sxs-lookup"><span data-stu-id="e1cda-103">Service object groups</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e1cda-104">Grupy przedmiotów serwisu są przydatne do sortowania i filtrowania danych o przedmiotach serwisu do wykorzystania w raportach i statystykach.</span><span class="sxs-lookup"><span data-stu-id="e1cda-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="e1cda-105">Na przykład można grupować obiekty według lokalizacji geograficznej lub według typu.</span><span class="sxs-lookup"><span data-stu-id="e1cda-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="e1cda-106">Grupowanie według lokalizacji geograficznych</span><span class="sxs-lookup"><span data-stu-id="e1cda-106">Group by geographical location</span></span>

<span data-ttu-id="e1cda-107">Tej metody grupowania można użyć w celu pokazania, gdzie są zlokalizowane różne przedmioty serwisowane przez firmę.</span><span class="sxs-lookup"><span data-stu-id="e1cda-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="e1cda-108">Grupowanie przedmiotów serwisu według lokalizacji geograficznych może być również przydatne, jeśli na przykład trzeba wskazać przedmioty, które firma już serwisuje w określonym kraju/regionie.</span><span class="sxs-lookup"><span data-stu-id="e1cda-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="e1cda-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="e1cda-109">Example</span></span>

<span data-ttu-id="e1cda-110">Klient z Belgii dzwoni do centrum serwisowego i chce zawrzeć umowę serwisową dotyczącą przedmiotu ABC.</span><span class="sxs-lookup"><span data-stu-id="e1cda-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="e1cda-111">Grupę przedmiotów serwisu odpowiadającą lokalizacji geograficznej Belgia dołączono do wszystkich obiektów serwisowanych w Belgii.</span><span class="sxs-lookup"><span data-stu-id="e1cda-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="e1cda-112">Używając tej grupy jako filtru, można szybko stwierdzić, czy przedmiot ABC już istnieje jako rekord w programie lub czy trzeba skonfigurować nowy przedmiot.</span><span class="sxs-lookup"><span data-stu-id="e1cda-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="e1cda-113">Grupowanie według typów</span><span class="sxs-lookup"><span data-stu-id="e1cda-113">Group by type</span></span>

<span data-ttu-id="e1cda-114">Tej metody grupowania można użyć w celu pokazania typów przedmiotów serwisowanych przez firmę.</span><span class="sxs-lookup"><span data-stu-id="e1cda-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="e1cda-115">Grupowanie przedmiotów serwisu według typów może być również przydatne do tworzenia nowych przedmiotów na podstawie podobnych przedmiotów już istniejących w programie.</span><span class="sxs-lookup"><span data-stu-id="e1cda-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="e1cda-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="e1cda-116">Example</span></span>

<span data-ttu-id="e1cda-117">Klient dzwoni w sprawie zawarcia umowy serwisowej dotyczącej urządzenia do klimatyzacji, HIJ.</span><span class="sxs-lookup"><span data-stu-id="e1cda-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="e1cda-118">Nie masz jeszcze rekordu dla tej maszyny.</span><span class="sxs-lookup"><span data-stu-id="e1cda-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="e1cda-119">Jednak skonfigurowano już grupę przedmiotów serwisu o nazwie Klimatyzatory i dołączono tę grupę do wszystkich przedmiotów związanych z klimatyzacją.</span><span class="sxs-lookup"><span data-stu-id="e1cda-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="e1cda-120">W związku z tym można szybko wyszukać i zidentyfikować wszystkie urządzenia do klimatyzacji oraz użyć informacji o tych przedmiotach jako szablonu do utworzenia wierszy umowy serwisowej dotyczącej urządzenia HIJ.</span><span class="sxs-lookup"><span data-stu-id="e1cda-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="e1cda-121">Korzystanie z grup przedmiotów w ten sposób pozwala szybko konfigurować nowe przedmioty serwisu i ustalać zadania serwisowe, które trzeba na nich wykonywać.</span><span class="sxs-lookup"><span data-stu-id="e1cda-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 




