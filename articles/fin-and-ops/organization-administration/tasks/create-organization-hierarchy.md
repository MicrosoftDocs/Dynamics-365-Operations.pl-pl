---
title: Tworzenie hierarchii organizacyjnej
description: Użyj poniższej procedury, aby utworzyć hierarchię organizacyjną.
author: sericks007
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMHierarchyPurposeAssociation, OMHierarchySelection, HierarchyDesigner
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 203a586b06a13a7c67f246384152d17627e22041
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "308812"
---
# <a name="create-an-organization-hierarchy"></a><span data-ttu-id="d08a5-103">Tworzenie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="d08a5-103">Create an organization hierarchy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d08a5-104">Użyj poniższej procedury, aby utworzyć hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="d08a5-104">Use the following procedure to create an organizational hierarchy.</span></span> <span data-ttu-id="d08a5-105">Hierarchie organizacyjne umożliwiają przeglądanie i raportowanie działalności biznesowej z różnych perspektyw.</span><span class="sxs-lookup"><span data-stu-id="d08a5-105">You can use organizational hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="d08a5-106">Można na przykład skonfigurować jedną hierarchię na potrzeby tworzenia raportów podatkowych, statutowych i ustawowych.</span><span class="sxs-lookup"><span data-stu-id="d08a5-106">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="d08a5-107">Następnie można ustawić inną hierarchię do raportowania informacji finansowych nie wymaganych przez prawo, ale używanych w raportach wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="d08a5-107">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span> 



<span data-ttu-id="d08a5-108">Przed utworzeniem hierarchii organizacyjnej należy utworzyć organizacje.</span><span class="sxs-lookup"><span data-stu-id="d08a5-108">Before you create an organizational hierarchy, you must create organizations.</span></span> <span data-ttu-id="d08a5-109">Aby uzyskać więcej informacji, zobacz zadania „Tworzenie firmy” lub „Tworzenie jednostki operacyjnej”.</span><span class="sxs-lookup"><span data-stu-id="d08a5-109">For more information, see the “Create a legal entity” or “Create an operating unit” tasks.</span></span> <span data-ttu-id="d08a5-110">Można też tworzyć działy i zespoły.</span><span class="sxs-lookup"><span data-stu-id="d08a5-110">You can also create departments and teams.</span></span> 



<span data-ttu-id="d08a5-111">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d08a5-111">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-hierarchy"></a><span data-ttu-id="d08a5-112">Tworzenie hierarchii</span><span class="sxs-lookup"><span data-stu-id="d08a5-112">Create a hierarchy</span></span>
1. <span data-ttu-id="d08a5-113">Wybierz kolejno opcje Administrowanie organizacją > Organizacje > Hierarchie organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="d08a5-113">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
2. <span data-ttu-id="d08a5-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d08a5-114">Click New.</span></span>
3. <span data-ttu-id="d08a5-115">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d08a5-115">In the Name field, type a value.</span></span>
4. <span data-ttu-id="d08a5-116">Kliknij przycisk Przypisywanie celu.</span><span class="sxs-lookup"><span data-stu-id="d08a5-116">Click Assign purpose.</span></span>
5. <span data-ttu-id="d08a5-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d08a5-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d08a5-118">Wybierz cel, który zostanie przypisany do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="d08a5-118">Select a purpose to assign to your organization hierarchy.</span></span>  
6. <span data-ttu-id="d08a5-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="d08a5-119">Click Add.</span></span>
7. <span data-ttu-id="d08a5-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="d08a5-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d08a5-121">Znajdź właśnie utworzoną hierarchię.</span><span class="sxs-lookup"><span data-stu-id="d08a5-121">Find the hierarchy you just created.</span></span>  
8. <span data-ttu-id="d08a5-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d08a5-122">Click OK.</span></span>

## <a name="add-organizations-to-the-hierarchy"></a><span data-ttu-id="d08a5-123">Dodawanie organizacji do hierarchii</span><span class="sxs-lookup"><span data-stu-id="d08a5-123">Add organizations to the hierarchy</span></span>
1. <span data-ttu-id="d08a5-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d08a5-124">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d08a5-125">Zaznacz hierarchię.</span><span class="sxs-lookup"><span data-stu-id="d08a5-125">Select your hierarchy.</span></span>  
2. <span data-ttu-id="d08a5-126">Kliknij opcję Wyświetl hierarchię.</span><span class="sxs-lookup"><span data-stu-id="d08a5-126">Click View hierarchy.</span></span>
    * <span data-ttu-id="d08a5-127">W razie potrzeby dodaj organizację.</span><span class="sxs-lookup"><span data-stu-id="d08a5-127">Add organizations, as necessary.</span></span>  
    * <span data-ttu-id="d08a5-128">Aby dodać organizację, kliknij przycisk Edytuj, a następnie opcję Wstaw.</span><span class="sxs-lookup"><span data-stu-id="d08a5-128">To add an organization, click Edit and then Insert to add the organization.</span></span>     <span data-ttu-id="d08a5-129">Po zakończeniu wprowadzania zmian można zapisać wersję roboczą i/lub opublikować zmiany.</span><span class="sxs-lookup"><span data-stu-id="d08a5-129">When you are done making changes you can save a draft and/or publish the changes.</span></span>  

