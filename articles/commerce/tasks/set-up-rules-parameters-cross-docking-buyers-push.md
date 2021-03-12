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
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc5404e5eb1679659604a6268fa09519a7a4282e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003734"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="1db35-103">Konfigurowanie reguł i parametrów dla przeładunku komplementacyjnego i dystrybucji od kupującego</span><span class="sxs-lookup"><span data-stu-id="1db35-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1db35-104">Ta procedura pokazuje kolejne kroki tworzenia reguł uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="1db35-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="1db35-105">Reguły uzupełnienia mogą służyć do kontrolowania sposobu rozdzielania produktów do sklepów podczas korzystania z funkcji przeładunku kompletacyjnego i dystrybucji na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="1db35-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="1db35-106">Reguły uzupełnienia mogą być skonfigurowane dla sklepów lub grup sklepów.</span><span class="sxs-lookup"><span data-stu-id="1db35-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="1db35-107">Waga zdefiniowana dla każdego wiersza w regule będzie określać sposób rozdziału ilości produktów między sklepy, jeśli reguły uzupełnienia są używane jako metoda dystrybucji w przeładunku kompletacyjnym lub dystrybucji na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="1db35-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="1db35-108">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="1db35-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="1db35-109">Przejdź do okna Reguły uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="1db35-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="1db35-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1db35-110">Click New.</span></span>
3. <span data-ttu-id="1db35-111">W polu Reguła uzupełnienia wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1db35-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="1db35-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="1db35-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1db35-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1db35-113">Click Save.</span></span>
6. <span data-ttu-id="1db35-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1db35-114">Click Add.</span></span>
7. <span data-ttu-id="1db35-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="1db35-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="1db35-116">W polu typu można wybrać Hierarchia uzupełnienia lub Kanał.</span><span class="sxs-lookup"><span data-stu-id="1db35-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="1db35-117">Ta wartość określa, czy opcja wybrana w polu Nazwa jest hierarchią kanałów, czy określonym kanałem.</span><span class="sxs-lookup"><span data-stu-id="1db35-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="1db35-118">W tym przykładzie należy pozostawić to ustawienie jako Hierarchia uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="1db35-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="1db35-119">W polu Nazwa wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1db35-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="1db35-120">Wartość domyślnej wagi jest ustawiana na podstawie wagi zdefiniowanej w magazynie.</span><span class="sxs-lookup"><span data-stu-id="1db35-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="1db35-121">Ta waga może być używana dla reguły uzupełnienia lub też można wpisać nową wagę w polu Waga.</span><span class="sxs-lookup"><span data-stu-id="1db35-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="1db35-122">W polu Waga wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1db35-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="1db35-123">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1db35-123">Click Add.</span></span>
11. <span data-ttu-id="1db35-124">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="1db35-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="1db35-125">W polu Typ wybierz opcję „Kanał”.</span><span class="sxs-lookup"><span data-stu-id="1db35-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="1db35-126">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1db35-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="1db35-127">W polu Waga wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1db35-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="1db35-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1db35-128">Click Save.</span></span>

