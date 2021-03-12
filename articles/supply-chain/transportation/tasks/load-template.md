---
title: Szablony ładunku
description: W tym temacie opisano sposób konfigurowania szablonów ładunków i kojarzenia szablonu ładunku z nowym ładunkiem.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0a4070a1dd5d53bb502ba2ab0c91dbdc90ded34d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005059"
---
# <a name="load-templates"></a><span data-ttu-id="1ba01-103">Szablony ładunku</span><span class="sxs-lookup"><span data-stu-id="1ba01-103">Load templates</span></span>

<span data-ttu-id="1ba01-104">Podczas tworzenia nowego ładunku można przypisać szablon ładunku.</span><span class="sxs-lookup"><span data-stu-id="1ba01-104">When you create a new load, you can assign a load template.</span></span> <span data-ttu-id="1ba01-105">Szablon ładunku zawiera informacje dotyczące sprzętu oraz miary, takie jak wysokość, szerokość, głębokość i objętość ładunku.</span><span class="sxs-lookup"><span data-stu-id="1ba01-105">The load template contains information about equipment, and about measures such as the height, width, depth, and volume of the load.</span></span>

<span data-ttu-id="1ba01-106">W tym temacie opisano sposób konfigurowania szablonów ładunków i kojarzenia szablonu ładunku z nowym ładunkiem.</span><span class="sxs-lookup"><span data-stu-id="1ba01-106">This topic describes how to set up load templates, and how to associate a load template with a new load.</span></span>

## <a name="set-up-a-load-template"></a><span data-ttu-id="1ba01-107">Ustawianie szablonu ładunku</span><span class="sxs-lookup"><span data-stu-id="1ba01-107">Set up a load template</span></span>

1. <span data-ttu-id="1ba01-108">Wybierz kolejno **Zarządzanie transportem \> Ustawienia \> Kompilowanie ładunku \> Szablon ładunku**.</span><span class="sxs-lookup"><span data-stu-id="1ba01-108">Go to **Transportation management \> Setup \> Load Building \> Load template**.</span></span>
1. <span data-ttu-id="1ba01-109">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy szablon, lub wybierz **Edytuj**, aby edytować istniejący.</span><span class="sxs-lookup"><span data-stu-id="1ba01-109">On the Action Pane, select **New** to add a new template or **Edit** to edit an existing template.</span></span>
1. <span data-ttu-id="1ba01-110">W wierszu nowego lub istniejącego szablonu należy określić następujące pola:</span><span class="sxs-lookup"><span data-stu-id="1ba01-110">In the row for the new or existing template, set the following fields:</span></span>

    - <span data-ttu-id="1ba01-111">**Identyfikator szablonu ładunku** – wprowadź unikatowy identyfikator (ID) tworzonego szablonu ładunku.</span><span class="sxs-lookup"><span data-stu-id="1ba01-111">**Load template ID** – Enter a unique identifier (ID) for the load template.</span></span>
    - <span data-ttu-id="1ba01-112">**Sprzęt** – wybierz sprzęt, który należy użyć do wysłania ładunku.</span><span class="sxs-lookup"><span data-stu-id="1ba01-112">**Equipment** – Select the equipment that should be used to ship the load.</span></span>
    - <span data-ttu-id="1ba01-113">**Wysokość ładunku**, **Szerokość ładunku** i **Głębokość ładunku** – wprowadź wymiary ładunku.</span><span class="sxs-lookup"><span data-stu-id="1ba01-113">**Load height**, **Load width**, and **Load depth** – Enter the dimensions of the load.</span></span>
    - <span data-ttu-id="1ba01-114">**Maks. dozwolona objętość ładunku** i **Maks. dozwolona waga ładunku** – wprowadź maksymalną dozwoloną objętość i wagę ładunku.</span><span class="sxs-lookup"><span data-stu-id="1ba01-114">**Max. allowed load volume** and **Max. allowed load weight** – Enter the maximum allowed volume and weight of the load.</span></span>
    - <span data-ttu-id="1ba01-115">**Maksymalna dozwolona waga brutto** — wprowadź maksymalną dozwoloną wagę brutto ładunku.</span><span class="sxs-lookup"><span data-stu-id="1ba01-115">**Maximum allowed gross weight** – Enter the maximum allowed gross weight of the load.</span></span> <span data-ttu-id="1ba01-116">Masa brutto ładunku obejmuje zarówno tarę, jak i masę ładunku.</span><span class="sxs-lookup"><span data-stu-id="1ba01-116">A load's gross weight includes both its tare weight and its loading weight.</span></span>
    - <span data-ttu-id="1ba01-117">**Maksymalna dozwolona liczba części frachtu** – wprowadź maksymalną liczbę części frachtu, jaką może zawierać ładunek.</span><span class="sxs-lookup"><span data-stu-id="1ba01-117">**Maximum number of freight pieces allowed** – Enter the maximum number of freight pieces that the load can contain.</span></span>
    - <span data-ttu-id="1ba01-118">**Załadowana stertami podłoga ładunkowa** – wybierz to pole wyboru, aby użyć ładowania podłogowego.</span><span class="sxs-lookup"><span data-stu-id="1ba01-118">**Stack load on floor** – Select this check box to use floor loading.</span></span> <span data-ttu-id="1ba01-119">W scenariuszu ładowania podłogowego, pudła są ułożone od podłogi do sufitu i od ściany do ściany wewnątrz kontenera, aby zmaksymalizować wewnętrzną pojemność.</span><span class="sxs-lookup"><span data-stu-id="1ba01-119">In a floor loading scenario, boxes are stacked floor to ceiling and wall to wall inside the container, to maximize capacity.</span></span>

1. <span data-ttu-id="1ba01-120">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1ba01-120">On the Action Pane, select **Save**.</span></span>

## <a name="associate-a-load-template-with-a-new-load"></a><span data-ttu-id="1ba01-121">Skojarz szablon ładunku z nowym ładunkiem</span><span class="sxs-lookup"><span data-stu-id="1ba01-121">Associate a load template with a new load</span></span>

1. <span data-ttu-id="1ba01-122">Wybierz kolejno opcje **Zarządzanie transportem \> Planowanie \> Warsztat planowania wysyłki ładunku**.</span><span class="sxs-lookup"><span data-stu-id="1ba01-122">Go to **Transportation management \> Planning \> Load planning workbench**.</span></span>
1. <span data-ttu-id="1ba01-123">W górnej części strony wybierz jedną z następujących zakładek, w zależności od typu dokumentu źródłowego, dla którego tworzysz ładunek: **Wysyłki**, **Wiersze sprzedaży**, **Wiersze przeniesienia** lub **Wiersze zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="1ba01-123">In the upper part of the page, select one of the following tabs, depending on the type of source document that you're creating a load for: **Shipments**, **Sales lines**, **Transfer lines**, or **Purchase order lines**.</span></span> 
1. <span data-ttu-id="1ba01-124">Wybierz konkretny dokument, dla którego chcesz zaplanować ładunek.</span><span class="sxs-lookup"><span data-stu-id="1ba01-124">Select the specific document to plan the load for.</span></span>
1. <span data-ttu-id="1ba01-125">W okienku akcji na karcie **Popyt i podaż** w grupie **Dodaj** kliknij opcję **Do nowego transportu**.</span><span class="sxs-lookup"><span data-stu-id="1ba01-125">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span>
1. <span data-ttu-id="1ba01-126">W oknie dialogowym **Szablon ładunku** w polu **Identyfikator szablonu ładunku** wybierz szablon do zastosowania.</span><span class="sxs-lookup"><span data-stu-id="1ba01-126">In the **Load template** dialog box, in the **Load template ID** field, select the template to apply.</span></span>
1. <span data-ttu-id="1ba01-127">Wybierz przycisk **OK**, aby zastosować szablon.</span><span class="sxs-lookup"><span data-stu-id="1ba01-127">Select **OK** to apply the template.</span></span>
