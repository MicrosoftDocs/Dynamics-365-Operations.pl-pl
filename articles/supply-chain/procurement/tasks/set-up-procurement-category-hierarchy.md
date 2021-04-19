---
title: Ustawianie hierarchii kategorii zaopatrzenia
description: W tej procedurze pokazano, jak utworzyć nowe węzły w hierarchii kategorii zaopatrzenia oraz jak skonfigurować kategorię zaopatrzenia, która ma być używana w procesie zaopatrzenia.
author: kamaybac
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 206dd5dc8f332268fe7665d84b005b5a7bfd1f9a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837712"
---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="c43cf-103">Ustawianie hierarchii kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="c43cf-103">Set up a procurement category hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c43cf-104">W tej procedurze pokazano, jak utworzyć nowe węzły w hierarchii kategorii zaopatrzenia oraz jak skonfigurować kategorię zaopatrzenia, która ma być używana w procesie zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="c43cf-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="c43cf-105">Te zadania zazwyczaj wykonuje menedżer ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="c43cf-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="c43cf-106">Przed rozpoczęciem tej procedury musi istnieć hierarchia kategorii typu Zaopatrzenie.</span><span class="sxs-lookup"><span data-stu-id="c43cf-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="c43cf-107">Jeśli używasz danych firmy demonstracyjnej, procedurę można wykonać w firmie USMF.</span><span class="sxs-lookup"><span data-stu-id="c43cf-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="c43cf-108">Dodawanie nowej kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="c43cf-108">Add a new procurement category</span></span>
1. <span data-ttu-id="c43cf-109">Wybierz kolejno **Okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Konsygnacja > Kategorie zaopatrzenia**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-109">Go to **Navigation pane > Modules > Procurement and sourcing > Consignment > Procurement categories**.</span></span>
2. <span data-ttu-id="c43cf-110">W okienku akcji kliknij pozycję **Edytuj hierarchię kategorii**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-110">On the Action Pane, select **Edit category hierarchy**.</span></span> <span data-ttu-id="c43cf-111">Bieżąca hierarchia kategorii zaopatrzenia zostanie wyświetlona przy lewej krawędzi strony.</span><span class="sxs-lookup"><span data-stu-id="c43cf-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="c43cf-112">Zmodyfikujesz tę hierarchię.</span><span class="sxs-lookup"><span data-stu-id="c43cf-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="c43cf-113">W okienku akcji kliknij pozycję **Nowy węzeł kategorii**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-113">On the Action Pane, select **New category node**.</span></span> <span data-ttu-id="c43cf-114">Domyślnie system wybiera węzeł najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="c43cf-114">The system selects the top node by default.</span></span> <span data-ttu-id="c43cf-115">Jeśli wykonujesz tę procedurę w przewodniku po zadaniach, możesz kliknąć przycisk Odblokuj i wybrać inny węzeł nadrzędny, aby wstawić tam swój nowy węzeł.</span><span class="sxs-lookup"><span data-stu-id="c43cf-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="c43cf-116">Po wykonaniu tej operacji ponownie zablokuj przewodnik po zadaniach, a następnie kliknij przycisk Nowy węzeł kategorii.</span><span class="sxs-lookup"><span data-stu-id="c43cf-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="c43cf-117">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c43cf-117">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="c43cf-118">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c43cf-118">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="c43cf-119">W polu **Przyjazna nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c43cf-119">In the **Friendly name** field, type a value.</span></span> <span data-ttu-id="c43cf-120">Przyjazna nazwa jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="c43cf-120">The friendly name is optional.</span></span> <span data-ttu-id="c43cf-121">Będzie wyświetlany w wyszukiwaniach kategorii wraz z nazwą kategorii.</span><span class="sxs-lookup"><span data-stu-id="c43cf-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="c43cf-122">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-122">Select **Save**.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="c43cf-123">Dodawanie produktów do nowej kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="c43cf-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="c43cf-124">Wybierz kolejno opcje **Zaopatrzenie i sourcing > Konsygnacja > Kategorie zaopatrzenia**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-124">Go to **Procurement and sourcing > Consignment > Procurement categories**.</span></span> <span data-ttu-id="c43cf-125">Zaznacz dodany właśnie węzeł.</span><span class="sxs-lookup"><span data-stu-id="c43cf-125">Select the node you just added.</span></span> <span data-ttu-id="c43cf-126">Jeśli wykonujesz tę procedurę w przewodniku po zadaniach, może być konieczne odblokowanie przewodnika po zadaniach w celu wybrania węzła.</span><span class="sxs-lookup"><span data-stu-id="c43cf-126">If you're running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="c43cf-127">Przełącz rozwinięcie sekcji **Produkty**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-127">Toggle the expansion of the **Products** section.</span></span>
3. <span data-ttu-id="c43cf-128">Kliknij przycisk **Dodaj**, aby skojarzyć produkty z kategorią zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="c43cf-128">Select **Add** to associate products with the procurement category.</span></span>
4. <span data-ttu-id="c43cf-129">Zaznacz produkty, które mają zostać dodane do kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="c43cf-129">Select the products you want to add to the procurement category.</span></span>
5. <span data-ttu-id="c43cf-130">Wybierz strzałkę, aby dodać produkty do tabeli **Wybrane**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-130">Select the arrow to add the products to the **Selected** table.</span></span>
6. <span data-ttu-id="c43cf-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]