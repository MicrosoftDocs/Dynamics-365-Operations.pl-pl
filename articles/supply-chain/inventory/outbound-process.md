---
title: "Proces wychodzący"
description: "Ten temat zawiera omówienie procesu wychodzącego w module Zarządzanie zapasami."
author: perlynne
manager: AnnBe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 9c09a7bd314bb9005eb0b6c69d7cccad1c30cfdb
ms.openlocfilehash: 7b395cab2184f8f9f3f50a7a595c6ed782645323
ms.contentlocale: pl-pl
ms.lasthandoff: 10/04/2017

---

# <a name="outbound-process"></a><span data-ttu-id="3b5c4-103">Proces wychodzący</span><span class="sxs-lookup"><span data-stu-id="3b5c4-103">Outbound process</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3b5c4-104">Ten temat zawiera omówienie procesu wychodzącego w module Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-104">This topic provides an overview of the outbound process in Inventory management.</span></span>

## <a name="output-orders"></a><span data-ttu-id="3b5c4-105">Zamówienia wyjścia</span><span class="sxs-lookup"><span data-stu-id="3b5c4-105">Output orders</span></span>

<span data-ttu-id="3b5c4-106">Zamówienia wyjścia służą do połączenia wierszy zamówienia sprzedaży i wierszy zamówienia przeniesienia z wychodzącymi procesami pobierania, które używają list pobrania.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-106">Output orders are used to link sales order lines and transfer order lines with the outbound picking processes that use picking lists.</span></span>

<span data-ttu-id="3b5c4-107">Po wygenerowaniu list pobrania z zamówień sprzedaży lub zamówień przeniesienia, zamówienia wyjścia i wysyłki są tworzone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-107">When picking lists are generated from either sales orders or transfer orders, output orders and shipments are automatically created.</span></span> <span data-ttu-id="3b5c4-108">Lista pobierania ma relację bezpośrednią z wysyłką.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-108">A picking list has a one-to-one relationship with a shipment.</span></span> <span data-ttu-id="3b5c4-109">Wysyłkę zamówienia przeniesienia lub dokument dostawy zamówienia sprzedaży można przetworzyć z wysyłki.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-109">The transfer order shipment or the sales order packing slip can be processed from the shipment.</span></span> 

<span data-ttu-id="3b5c4-110">Poniższy schemat przedstawia przegląd procesu dotyczącego zamówień wychodzących.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-110">The following diagram shows an overview of the process for outbound orders.</span></span> 

<span data-ttu-id="3b5c4-111">[![Przegląd procesu zamówienia wychodzącego](./media/outbound-order.png)](./media/outbound-order.png)</span><span class="sxs-lookup"><span data-stu-id="3b5c4-111">[![Overview of the outbound order process](./media/outbound-order.png)](./media/outbound-order.png)</span></span>

<span data-ttu-id="3b5c4-112">Aby zdefiniować sposób obsługi przez program procesu wychodzącego, można ustawić odpowiednie reguł wychodzące.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-112">You can set up outbound rules to define how the program should handle the outbound process.</span></span> <span data-ttu-id="3b5c4-113">Tych zasad można użyć do kontroli procesu wysyłki.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-113">You can use these rules to control the shipment process.</span></span> <span data-ttu-id="3b5c4-114">W szczególności można użyć zasad do kontroli, na jakim etapie procesu ma zostać zrealizowana wysyłka.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-114">In particular, you can use the rules to control which stage in the process a shipment can be sent during.</span></span> <span data-ttu-id="3b5c4-115">Poniższe ustawienia określają sposób obsługi procesów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-115">The following settings define how the outbound processes are handled.</span></span>

## <a name="picking-route-status-for-sales-and-transfer-orders"></a><span data-ttu-id="3b5c4-116">Stan marszruty pobrania dla zamówień sprzedaży i przeniesienia</span><span class="sxs-lookup"><span data-stu-id="3b5c4-116">Picking route status for sales and transfer orders</span></span> 

<span data-ttu-id="3b5c4-117">Przejdź do okna **Rozrachunki z odbiorcami** \> **Konfiguracja** \> **Parametry modułu rozrachunków z odbiorcami**, a następnie na karcie **Aktualizacje** wybierz wartość w polu **Stan marszruty pobrania**.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-117">Go to **Account receivable** \> **Setup** \> **Account receivable parameters**, and then, on the **Updates** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="3b5c4-118">[![Pole Stan marszruty pobrania dla zamówień sprzedaży](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span><span class="sxs-lookup"><span data-stu-id="3b5c4-118">[![Picking route status field for sales orders](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span></span>

<span data-ttu-id="3b5c4-119">Jeżeli pole **Stan marszruty pobrania** jest ustawione na **Ukończono**, proces pobierania następuje automatycznie jako część procesu generowania list pobierania.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-119">If the **Picking route status** field is set to **Completed**, the picking process occurs automatically as part of the process of generating picking lists.</span></span> <span data-ttu-id="3b5c4-120">Jeżeli pole jest ustawione na **Aktywowane**, wiersze list pobierania należy zaktualizować ręcznie.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-120">If the field is set to **Activated**, the picking list lines must be manually updated.</span></span>

<span data-ttu-id="3b5c4-121">Ta sama konfiguracja dotyczy zamówień przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-121">The same setup applies to transfer orders.</span></span> <span data-ttu-id="3b5c4-122">Przejdź do okna**Zarządzanie zapasami** \> **Konfiguracja** \> **Parametry modułu Zarządzanie zapasami i magazynem**, a następnie na karcie **Transport** wybierz wartość w polu **Stan marszruty pobrania**.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-122">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **Transport** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="3b5c4-123">[![Pole Stan marszruty pobrania dla zamówień przeniesienia](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span><span class="sxs-lookup"><span data-stu-id="3b5c4-123">[![Picking route status field for transfer orders](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span></span>

## <a name="end-output-inventory-orders"></a><span data-ttu-id="3b5c4-124">Koniec zamówień magazynowego wyjścia</span><span class="sxs-lookup"><span data-stu-id="3b5c4-124">End output inventory orders</span></span>

<span data-ttu-id="3b5c4-125">Przejdź do okna **Zarządzanie zapasami** \> **Konfiguracja** \> **Parametry modułu Zarządzanie zapasami i magazynem**, a następnie na karcie **Ogólne** ustaw opcję **Koniec zamówienia magazynowego wyjścia**.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-125">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **General** tab, set the **End output inventory order** option.</span></span>

<span data-ttu-id="3b5c4-126">[![Opcja Koniec zamówienia magazynowego wyjścia](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span><span class="sxs-lookup"><span data-stu-id="3b5c4-126">[![End output inventory order option](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span></span>

<span data-ttu-id="3b5c4-127">Czasami niektóre towary w zapasach nie mogą zostać pobrane w ramach przetwarzania listy pobierania.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-127">Sometimes, some items in inventory can't be picked as part of the picking list process.</span></span> <span data-ttu-id="3b5c4-128">Taka sytuacja może mieć miejsce na przykład, jeżeli pracownik magazynu zmniejszy ilości w wierszach pobrania i przetworzy listy pobrania.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-128">For example, this situation might occur if a warehouse worker reduces the quantities on picking lines and processes the picking list.</span></span> <span data-ttu-id="3b5c4-129">Jeżeli opcja **Koniec zamówienia magazynowego wyjścia** jest ustawiona na **Tak**, pozostałe niepobrane ilości są zgłaszane z powrotem na poziom zamówienia.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-129">If the **End output inventory order** option is set to **Yes**, the remaining unpicked quantities are reported back to the order level.</span></span> <span data-ttu-id="3b5c4-130">Jeżeli opcja jest ustawiona na **Nie**, pozostałe niepobrane ilości są zachowywane jako otwarta ilość zamówienia wyjścia.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-130">If the option is set to **No**, the remaining unpicked quantities are kept as an open output order quantity.</span></span> <span data-ttu-id="3b5c4-131">W takim przypadku ilości pozostają zwolnione do magazynu i muszą zostać dodane do nowej listy pobrania w ramach funkcji **Otwórz zamówienia wyjścia**.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-131">In this case, the quantities remain released to the warehouse and must be added to a new picking list as part of the **Open output orders** functionality.</span></span>

<span data-ttu-id="3b5c4-132">[![Polecenie Otwórz zamówienia wyjścia w menu Funkcje](./media/open-output-order.png)](./media/open-output-order.png)</span><span class="sxs-lookup"><span data-stu-id="3b5c4-132">[![Open output orders command on the Functions menu](./media/open-output-order.png)](./media/open-output-order.png)</span></span>

<span data-ttu-id="3b5c4-133">[![Menu Funkcje na stronie Otwórz zamówienia wyjścia](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span><span class="sxs-lookup"><span data-stu-id="3b5c4-133">[![Functions menu on the Open output orders page](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span></span>

## <a name="reduce-quantity"></a><span data-ttu-id="3b5c4-134">Zmniejsz ilość</span><span class="sxs-lookup"><span data-stu-id="3b5c4-134">Reduce quantity</span></span>

<span data-ttu-id="3b5c4-135">Trzeci parametr, którego można użyć w ramach procesu generowania list pobrania to parametr **Zmniejsz ilość**.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-135">The third parameter that you can use as part of the process of generating picking lists is the **Reduce quantity** parameter.</span></span> <span data-ttu-id="3b5c4-136">Ustawienie tego parametru jest powiązane z ustawieniem **Rezerwacja**, które uruchamia proces rezerwacji w ramach zwolnienia do magazynu.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-136">The setting of this parameter works together with the **Reservation** setting that triggers a reservation process as part of the release to the warehouse.</span></span>

<span data-ttu-id="3b5c4-137">[![Parametr Zmniejsz ilość](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span><span class="sxs-lookup"><span data-stu-id="3b5c4-137">[![Reduce quantity parameter](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span></span>

## <a name="example-of-an-outbound-process-for-a-sales-order"></a><span data-ttu-id="3b5c4-138">Przykład procesu wyjścia dla zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="3b5c4-138">Example of an outbound process for a sales order</span></span>

<span data-ttu-id="3b5c4-139">W tym przykładzie występuje zamówienie sprzedaży dla dwóch towarów.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-139">For this example, there is a sales order for two items.</span></span> <span data-ttu-id="3b5c4-140">Podczas generowania listy pobrania wybierz parametr **Zmniejsz ilość**.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-140">During picking list generation, you select the **Reduce quantity** parameter.</span></span> <span data-ttu-id="3b5c4-141">Dlatego zwalniasz i tworzysz wiersze pobrania tylko dla dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-141">Therefore, you release and create picking lines only for available on-hand inventory.</span></span> <span data-ttu-id="3b5c4-142">Pobranie musi zostać zgłoszone za pomocą procesu rejestracji dla list pobrania (**Stan marszruty pobrania** = **Aktywowane**).</span><span class="sxs-lookup"><span data-stu-id="3b5c4-142">The picking must be reported via a registration process for picking lists (**Picking route status** = **Activated**).</span></span>

<span data-ttu-id="3b5c4-143">Podczas generowania listy pobrania rezerwowane są zapasy, które nie zostały już zarezerwowane.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-143">The inventory that hasn't already been reserved is reserved during picking list generation.</span></span> <span data-ttu-id="3b5c4-144">Niedostępne zapasy można usunąć z zamówienia sprzedaży lub zwolnione do magazynu do późniejszego przetworzenia wyjściowego, gdy zapasy będą dostępne do pobrania.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-144">The unavailable inventory can be either removed from the sales order or released to the warehouse for outbound processing later, when inventory is available for picking.</span></span>

<span data-ttu-id="3b5c4-145">[![Aktualizuj listę pobrania](./media/update-picking-list.png)](./media/update-picking-list.png)</span><span class="sxs-lookup"><span data-stu-id="3b5c4-145">[![Update the picking list](./media/update-picking-list.png)](./media/update-picking-list.png)</span></span>

<span data-ttu-id="3b5c4-146">Po pobraniu wszystkich wierszy pobrania na stronie **Potwierdzenie listy pobrania** skojarzona wysyłka jest ukończona.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-146">As soon as all the picking lines have been picked on the **Picking list registration** page, the associated shipment is completed.</span></span> <span data-ttu-id="3b5c4-147">Następnie można rozpocząć przetwarzanie dokumentów dostawy zamówienia sprzedaży dla odebranego towaru.</span><span class="sxs-lookup"><span data-stu-id="3b5c4-147">The process for sales order packing slips can then be initialized based on the picked inventory.</span></span>

<span data-ttu-id="3b5c4-148">[![Aktualizacja wysyłek wychodzących](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span><span class="sxs-lookup"><span data-stu-id="3b5c4-148">[![Update outbound shipments](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span></span>

