---
title: Dystrybucja produktów z centrum dystrybucji do sklepu za pomocą dystrybucji na zamówienie
description: Ta procedura prowadzi przez kolejne kroki tworzenia i przetwarzania dystrybucji na zamówienie w celu dostarczenia produktów z jednej lokalizacji do jednego lub wielu sklepów.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPush, InventLocationIdLookup, InventItemIdLookupSimple, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bf5dc0320e16bb53dbebc9e0bea689e0125b9827
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232841"
---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a><span data-ttu-id="a5365-103">Dystrybucja produktów z centrum dystrybucji do sklepu za pomocą dystrybucji na zamówienie</span><span class="sxs-lookup"><span data-stu-id="a5365-103">Push products from distribution center to store using buyer's push</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5365-104">Ta procedura prowadzi przez kolejne kroki tworzenia i przetwarzania dystrybucji na zamówienie w celu dostarczenia produktów z jednej lokalizacji do jednego lub wielu sklepów.</span><span class="sxs-lookup"><span data-stu-id="a5365-104">This procedure walks through the steps to create and process a Buyer´s push to distribute products from one location to one or many stores.</span></span> <span data-ttu-id="a5365-105">Użytkownik może zdefiniować wiele konfiguracji i otrzymywać z systemu sugestie rozdziału produktów albo ręcznie wpisać, gdzie produkty mają być dostarczane i ile towaru trafi do każdego sklepu.</span><span class="sxs-lookup"><span data-stu-id="a5365-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="a5365-106">Procedura nie obejmuje konfigurowania danych, które mogą być używane w dystrybucji na zamówienie, takich jak reguły uzupełnienia, hierarchie organizacyjne i wagi sklepów.</span><span class="sxs-lookup"><span data-stu-id="a5365-106">This procedure doesn't include setup of data that can be used in the Buyer´s push, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="a5365-107">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="a5365-107">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="a5365-108">Przejdź do okna Dystrybucja na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="a5365-108">Go to Buyer's push.</span></span>
2. <span data-ttu-id="a5365-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a5365-109">Click New.</span></span>
3. <span data-ttu-id="a5365-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="a5365-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="a5365-111">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a5365-111">In the Site field, enter or select a value.</span></span>
5. <span data-ttu-id="a5365-112">W polu Magazyn wprowadź lub wybierz magazyn zawierający dostępne zapasy produktów.</span><span class="sxs-lookup"><span data-stu-id="a5365-112">In the Warehouse field, enter or select a warehouse that has products with on-hand quantities.</span></span>
6. <span data-ttu-id="a5365-113">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a5365-113">Click Add.</span></span>
7. <span data-ttu-id="a5365-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="a5365-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="a5365-115">W polu Numer towaru wprowadź lub wybierz produkt.</span><span class="sxs-lookup"><span data-stu-id="a5365-115">In the Item number field, enter or select a product.</span></span>
9. <span data-ttu-id="a5365-116">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a5365-116">Click Add.</span></span>
10. <span data-ttu-id="a5365-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="a5365-117">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="a5365-118">W polu Numer towaru wprowadź lub wybierz wariant produktu.</span><span class="sxs-lookup"><span data-stu-id="a5365-118">In the Item number field, enter or select a variant product.</span></span>
    * <span data-ttu-id="a5365-119">Podczas wprowadzania wariantu produktu zostaną utworzone wiersze dla każdego wariantu.</span><span class="sxs-lookup"><span data-stu-id="a5365-119">When entering a variant product, lines will be created for each variant.</span></span>  
12. <span data-ttu-id="a5365-120">Na liście zaznacz wiersz.</span><span class="sxs-lookup"><span data-stu-id="a5365-120">In the list, mark a row.</span></span>
13. <span data-ttu-id="a5365-121">W polu Ilość w transakcji push wpisz ilość wybranego produktu, którą chcesz rozesłać.</span><span class="sxs-lookup"><span data-stu-id="a5365-121">In the Pushed quantity field, type how many of the selected product you want to distribute.</span></span>
14. <span data-ttu-id="a5365-122">W polu Dodatkowa ilość do dystrybucji wprowadź ilości produktów, które są dostępne do rozesłania.</span><span class="sxs-lookup"><span data-stu-id="a5365-122">In the Additional quantity to push field, enter the quantity of the products that have available quantity to distribute.</span></span>
15. <span data-ttu-id="a5365-123">W polu Dystrybucja wpisz „Waga lokalizacji”.</span><span class="sxs-lookup"><span data-stu-id="a5365-123">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="a5365-124">Można wybrać różne typy, aby używać innych reguł dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="a5365-124">You can select the other types to use other rules for the distribution.</span></span>  
16. <span data-ttu-id="a5365-125">W polu Hierarchia uzupełnienia wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a5365-125">In the Replenishment hierarchy field, select a value.</span></span>
17. <span data-ttu-id="a5365-126">W polu Uwzględnianie asortymentów wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="a5365-126">Select Yes in the Respect assortments field.</span></span>
18. <span data-ttu-id="a5365-127">Kliknij przycisk Oblicz ilości i przejrzyj ilości, które zostały dodane do wierszy w sekcji Magazyn.</span><span class="sxs-lookup"><span data-stu-id="a5365-127">Click Calculate quantities and review the quantities that are added to the rows in the Warehouse section.</span></span>
19. <span data-ttu-id="a5365-128">Kliknij opcję Utwórz zamówienie.</span><span class="sxs-lookup"><span data-stu-id="a5365-128">Click Create order.</span></span>
20. <span data-ttu-id="a5365-129">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="a5365-129">Click Yes.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]