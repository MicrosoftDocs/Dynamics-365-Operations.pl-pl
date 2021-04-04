---
title: Tworzenie hierarchii organizacyjnej
description: Użyj poniższej procedury, aby utworzyć hierarchię organizacyjną.
author: sericks007
manager: AnnBe
ms.date: 12/15/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMHierarchyPurposeAssociation, OMHierarchySelection, HierarchyDesigner
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d61d6eee3b55087d633a8416fbed3a6192e82b2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560586"
---
# <a name="create-an-organization-hierarchy"></a><span data-ttu-id="ffacd-103">Tworzenie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="ffacd-103">Create an organization hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ffacd-104">Użyj poniższej procedury, aby utworzyć hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="ffacd-104">Use the following procedure to create an organizational hierarchy.</span></span> <span data-ttu-id="ffacd-105">Hierarchie organizacyjne umożliwiają przeglądanie i raportowanie działalności biznesowej z różnych perspektyw.</span><span class="sxs-lookup"><span data-stu-id="ffacd-105">You can use organizational hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="ffacd-106">Można na przykład skonfigurować jedną hierarchię na potrzeby tworzenia raportów podatkowych, statutowych i ustawowych.</span><span class="sxs-lookup"><span data-stu-id="ffacd-106">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="ffacd-107">Następnie można ustawić inną hierarchię do raportowania informacji finansowych nie wymaganych przez prawo, ale używanych w raportach wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="ffacd-107">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span> 

<span data-ttu-id="ffacd-108">Przed utworzeniem hierarchii organizacyjnej należy utworzyć organizacje.</span><span class="sxs-lookup"><span data-stu-id="ffacd-108">Before you create an organizational hierarchy, you must create organizations.</span></span> <span data-ttu-id="ffacd-109">Aby uzyskać więcej informacji, zobacz zadania „Tworzenie firmy” lub „Tworzenie jednostki operacyjnej”.</span><span class="sxs-lookup"><span data-stu-id="ffacd-109">For more information, see the "Create a legal entity" or "Create an operating unit" tasks.</span></span> <span data-ttu-id="ffacd-110">Można też tworzyć działy i zespoły.</span><span class="sxs-lookup"><span data-stu-id="ffacd-110">You can also create departments and teams.</span></span> 

<span data-ttu-id="ffacd-111">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ffacd-111">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-hierarchy"></a><span data-ttu-id="ffacd-112">Tworzenie hierarchii</span><span class="sxs-lookup"><span data-stu-id="ffacd-112">Create a hierarchy</span></span>
1. <span data-ttu-id="ffacd-113">Otwórz **Okienko nawigacji > Moduły > Administrowanie organizacją > Organizacje > Hierarchie organizacyjne**.</span><span class="sxs-lookup"><span data-stu-id="ffacd-113">Go to **Navigation pane > Modules > Organization administration > Organizations > Organization hierarchies**.</span></span>
2. <span data-ttu-id="ffacd-114">W **okienku akcji** kliknij **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ffacd-114">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="ffacd-115">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ffacd-115">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="ffacd-116">W sekcji **Cel** kliknij przycisk **Przypisywanie celu**.</span><span class="sxs-lookup"><span data-stu-id="ffacd-116">In the **Purpose** section, click **Assign purpose**.</span></span>
5. <span data-ttu-id="ffacd-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ffacd-117">In the list, find and select the desired record.</span></span> <span data-ttu-id="ffacd-118">Wybierz cel, który zostanie przypisany do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="ffacd-118">Select a purpose to assign to your organization hierarchy.</span></span>  
6. <span data-ttu-id="ffacd-119">W sekcji **Przypisane hierarchie** kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="ffacd-119">In the **Assigned hierarchies** section, click **Add**.</span></span>
7. <span data-ttu-id="ffacd-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ffacd-120">In the list, mark the selected row.</span></span> <span data-ttu-id="ffacd-121">Znajdź właśnie utworzoną hierarchię.</span><span class="sxs-lookup"><span data-stu-id="ffacd-121">Find the hierarchy you just created.</span></span>  
8. <span data-ttu-id="ffacd-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffacd-122">Click **OK**.</span></span>

## <a name="add-organizations-to-the-hierarchy"></a><span data-ttu-id="ffacd-123">Dodawanie organizacji do hierarchii</span><span class="sxs-lookup"><span data-stu-id="ffacd-123">Add organizations to the hierarchy</span></span>
1. <span data-ttu-id="ffacd-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ffacd-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="ffacd-125">Zaznacz hierarchię.</span><span class="sxs-lookup"><span data-stu-id="ffacd-125">Select your hierarchy.</span></span>  
2. <span data-ttu-id="ffacd-126">W sekcji **Przypisane hierarchie** kliknij przycisk **Wyświetl hierarchię**.</span><span class="sxs-lookup"><span data-stu-id="ffacd-126">In the **Assigned hierarchies** section, click **View hierarchy**.</span></span>
    - <span data-ttu-id="ffacd-127">W razie potrzeby dodaj organizację.</span><span class="sxs-lookup"><span data-stu-id="ffacd-127">Add organizations, as necessary.</span></span>  
    - <span data-ttu-id="ffacd-128">Aby dodać organizację, kliknij przycisk **Edytuj**, a następnie opcję **Wstaw** , aby dodać organizację.</span><span class="sxs-lookup"><span data-stu-id="ffacd-128">To add an organization, click **Edit** and then **Insert** to add the organization.</span></span> <span data-ttu-id="ffacd-129">Po zakończeniu wprowadzania zmian można **zapisać** wersję roboczą i/lub **opublikować** zmiany.</span><span class="sxs-lookup"><span data-stu-id="ffacd-129">When you are done making changes you can **Save** a draft and/or **Publish** the changes.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]