---
title: Konfigurowanie reguł i parametrów dla przeładunku komplementacyjnego i dystrybucji od kupującego
description: Ta procedura pokazuje kolejne kroki tworzenia reguł uzupełnienia.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a22756279ba316a7efd4d09c48c55e8cc98ba29d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "366335"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="3c549-103">Konfigurowanie reguł i parametrów dla przeładunku komplementacyjnego i dystrybucji od kupującego</span><span class="sxs-lookup"><span data-stu-id="3c549-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="3c549-104">Ta procedura pokazuje kolejne kroki tworzenia reguł uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="3c549-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="3c549-105">Reguły uzupełnienia mogą służyć do kontrolowania sposobu rozdzielania produktów do sklepów podczas korzystania z funkcji przeładunku kompletacyjnego i dystrybucji na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="3c549-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="3c549-106">Reguły uzupełnienia mogą być skonfigurowane dla sklepów lub grup sklepów.</span><span class="sxs-lookup"><span data-stu-id="3c549-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="3c549-107">Waga zdefiniowana dla każdego wiersza w regule będzie określać sposób rozdziału ilości produktów między sklepy, jeśli reguły uzupełnienia są używane jako metoda dystrybucji w przeładunku kompletacyjnym lub dystrybucji na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="3c549-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="3c549-108">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="3c549-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="3c549-109">Przejdź do okna Reguły uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="3c549-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="3c549-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3c549-110">Click New.</span></span>
3. <span data-ttu-id="3c549-111">W polu Reguła uzupełnienia wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c549-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="3c549-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="3c549-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3c549-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3c549-113">Click Save.</span></span>
6. <span data-ttu-id="3c549-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="3c549-114">Click Add.</span></span>
7. <span data-ttu-id="3c549-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3c549-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3c549-116">W polu typu można wybrać Hierarchia uzupełnienia lub Kanał.</span><span class="sxs-lookup"><span data-stu-id="3c549-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="3c549-117">Ta wartość określa, czy opcja wybrana w polu Nazwa jest hierarchią kanałów, czy określonym kanałem.</span><span class="sxs-lookup"><span data-stu-id="3c549-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="3c549-118">W tym przykładzie należy pozostawić to ustawienie jako Hierarchia uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="3c549-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="3c549-119">W polu Nazwa wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c549-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="3c549-120">Wartość domyślnej wagi jest ustawiana na podstawie wagi zdefiniowanej w magazynie.</span><span class="sxs-lookup"><span data-stu-id="3c549-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="3c549-121">Ta waga może być używana dla reguły uzupełnienia lub też można wpisać nową wagę w polu Waga.</span><span class="sxs-lookup"><span data-stu-id="3c549-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="3c549-122">W polu Waga wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="3c549-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="3c549-123">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="3c549-123">Click Add.</span></span>
11. <span data-ttu-id="3c549-124">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3c549-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="3c549-125">W polu Typ wybierz opcję „Kanał”.</span><span class="sxs-lookup"><span data-stu-id="3c549-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="3c549-126">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c549-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="3c549-127">W polu Waga wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="3c549-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="3c549-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3c549-128">Click Save.</span></span>

