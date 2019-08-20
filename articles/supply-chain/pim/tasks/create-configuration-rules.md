---
title: Tworzenie reguł konfiguracji
description: W tej procedurze zostaną utworzone reguły konfiguracji, które mogą być używane w konfiguracjach opartych na wymiarach do wymuszania lub blokowania niektórych kombinacji wierszy BOM.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f15c0328e391d81c4c977f974553ae9135b207c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844904"
---
# <a name="create-configuration-rules"></a><span data-ttu-id="2a2a1-103">Tworzenie reguł konfiguracji</span><span class="sxs-lookup"><span data-stu-id="2a2a1-103">Create configuration rules</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2a2a1-104">W tej procedurze zostaną utworzone reguły konfiguracji, które mogą być używane w konfiguracjach opartych na wymiarach do wymuszania lub blokowania niektórych kombinacji wierszy BOM.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="2a2a1-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2a2a1-106">Jest to siódma z ośmiu procedur opisujących sposób tworzenia kombinacji dla konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="2a2a1-107">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Listy składowe (BOM) i formuły > BOM.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="2a2a1-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2a2a1-109">Znajdź i zaznacz listę składową konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="2a2a1-110">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="2a2a1-111">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-111">Click Change view.</span></span>
5. <span data-ttu-id="2a2a1-112">Kliknij opcję Widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-112">Click Header view.</span></span>
    * <span data-ttu-id="2a2a1-113">Otwórz widok nagłówka, aby przejść do skróconej karty Marszruta konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="2a2a1-114">Rozwiń lub zwiń sekcję Marszruta konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="2a2a1-115">Skrócona karta Marszruta konfiguracji musi być w trybie rozwiniętym.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="2a2a1-116">Kliknij opcję Reguły konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="2a2a1-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-117">Click New.</span></span>
9. <span data-ttu-id="2a2a1-118">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="2a2a1-119">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2a2a1-120">Są wyświetlane towary należące do bieżącej grupy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="2a2a1-121">Wybierz ten, który reprezentuje warunek w regule.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="2a2a1-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="2a2a1-123">W polu Metoda wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="2a2a1-124">Istnieje możliwość wymuszenia wyboru lub anulowania wyboru towaru z innej grupy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="2a2a1-125">W polu Grupa pochodna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="2a2a1-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="2a2a1-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2a2a1-128">Zaznacz żądaną grupę konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="2a2a1-129">W polu Pochodny kod towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="2a2a1-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2a2a1-131">Zaznacz numer towaru, który zostanie zaznaczony lub którego zaznaczenie zostanie anulowane, zależnie od wybranej metody.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="2a2a1-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2a2a1-132">Close the page.</span></span>

