--- 
title: "Konfigurowanie reguł i parametrów dla przeładunku komplementacyjnego i dystrybucji od kupującego"
description: "Ta procedura pokazuje kolejne kroki tworzenia reguł uzupełnienia."
author: josaw1
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 28f8610f429022c8e55748c8316c4c1211c17716
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="8bfd0-103">Konfigurowanie reguł i parametrów dla przeładunku komplementacyjnego i dystrybucji od kupującego</span><span class="sxs-lookup"><span data-stu-id="8bfd0-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="8bfd0-104">Ta procedura pokazuje kolejne kroki tworzenia reguł uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="8bfd0-105">Reguły uzupełnienia mogą służyć do kontrolowania sposobu rozdzielania produktów do sklepów podczas korzystania z funkcji przeładunku kompletacyjnego i dystrybucji na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="8bfd0-106">Reguły uzupełnienia mogą być skonfigurowane dla sklepów lub grup sklepów.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="8bfd0-107">Waga zdefiniowana dla każdego wiersza w regule będzie określać sposób rozdziału ilości produktów między sklepy, jeśli reguły uzupełnienia są używane jako metoda dystrybucji w przeładunku kompletacyjnym lub dystrybucji na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="8bfd0-108">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="8bfd0-109">Przejdź do okna Reguły uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="8bfd0-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-110">Click New.</span></span>
3. <span data-ttu-id="8bfd0-111">W polu Reguła uzupełnienia wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="8bfd0-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8bfd0-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-113">Click Save.</span></span>
6. <span data-ttu-id="8bfd0-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-114">Click Add.</span></span>
7. <span data-ttu-id="8bfd0-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8bfd0-116">W polu typu można wybrać Hierarchia uzupełnienia lub Kanał.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="8bfd0-117">Ta wartość określa, czy opcja wybrana w polu Nazwa jest hierarchią kanałów, czy określonym kanałem.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="8bfd0-118">W tym przykładzie należy pozostawić to ustawienie jako Hierarchia uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="8bfd0-119">W polu Nazwa wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="8bfd0-120">Wartość domyślnej wagi jest ustawiana na podstawie wagi zdefiniowanej w magazynie.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="8bfd0-121">Ta waga może być używana dla reguły uzupełnienia lub też można wpisać nową wagę w polu Waga.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="8bfd0-122">W polu Waga wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="8bfd0-123">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-123">Click Add.</span></span>
11. <span data-ttu-id="8bfd0-124">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="8bfd0-125">W polu Typ wybierz opcję „Kanał”.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="8bfd0-126">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="8bfd0-127">W polu Waga wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="8bfd0-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8bfd0-128">Click Save.</span></span>


