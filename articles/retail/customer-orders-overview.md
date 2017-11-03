---
title: "Omówienie zamówień odbiorców"
description: "Ten temat zawiera informacje o funkcjonalności zamówień odbiorców w programie Retail Modern POS (MPOS). Zamówienia odbiorców są również nazywane zamówieniami specjalnymi. Temat przedstawia powiązane parametry i przepływy transakcji."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ce6774ede836eb29e6ef2cd8d4baa9efb931020c
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="customer-orders-overview"></a><span data-ttu-id="d8b60-105">Omówienie zamówień odbiorców</span><span class="sxs-lookup"><span data-stu-id="d8b60-105">Customer orders overview</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="d8b60-106">Ten temat zawiera informacje o funkcjonalności zamówień odbiorców w programie Retail Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="d8b60-106">This topic provides information about customer orders in Retail Modern POS (MPOS).</span></span> <span data-ttu-id="d8b60-107">Zamówienia odbiorców są również nazywane zamówieniami specjalnymi.</span><span class="sxs-lookup"><span data-stu-id="d8b60-107">Customer orders are also known as special orders.</span></span> <span data-ttu-id="d8b60-108">Temat przedstawia powiązane parametry i przepływy transakcji.</span><span class="sxs-lookup"><span data-stu-id="d8b60-108">The topic includes a discussion of related parameters and transaction flows.</span></span>

<span data-ttu-id="d8b60-109">W świecie wielokanałowego handlu detalicznego wielu sprzedawców udostępnia opcję składania zamówień przez odbiorców, inaczej zamówień specjalnych, które pomagają spełnić różne wymagania dotyczące produktów i realizacji dostaw.</span><span class="sxs-lookup"><span data-stu-id="d8b60-109">In an omni-channel retail world, many retailers provide the option of customer orders, or special orders, to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="d8b60-110">Poniżej przedstawiono niektóre typowe scenariusze:</span><span class="sxs-lookup"><span data-stu-id="d8b60-110">Here are some typical scenarios:</span></span>

-   <span data-ttu-id="d8b60-111">Klient chce, aby produkty zostały dostarczane pod określony adres w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="d8b60-111">A customer wants products to be delivered to a specific address on a specific date.</span></span>
-   <span data-ttu-id="d8b60-112">Klient chce odebrać produkty ze sklepu lub lokalizacji innej niż ta, w której kupił produkty.</span><span class="sxs-lookup"><span data-stu-id="d8b60-112">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span>
-   <span data-ttu-id="d8b60-113">Klient chce, aby ktoś inny odebrał kupione przez niego produkty.</span><span class="sxs-lookup"><span data-stu-id="d8b60-113">A customer wants someone else to pick up products that the customer purchased.</span></span>

<span data-ttu-id="d8b60-114">Sprzedawcy detaliczni wykorzystują również zamówienia odbiorców, aby minimalizować utraconą sprzedaż, jaką mogą powodować przestoje w zaopatrzeniu, ponieważ towar może być dostarczany lub odbierany w różnych miejscach i czasie.</span><span class="sxs-lookup"><span data-stu-id="d8b60-114">Retailers also use customer orders to minimize lost sales that stock outages might otherwise cause, because the merchandise can be delivered or picked up at a different time or place.</span></span>

## <a name="set-up-customer-orders"></a><span data-ttu-id="d8b60-115">Konfigurowanie zamówień odbiorców</span><span class="sxs-lookup"><span data-stu-id="d8b60-115">Set up customer orders</span></span>
<span data-ttu-id="d8b60-116">Oto kilka parametrów, które można skonfigurować na stronie **Parametry sieci sprzedaży** w celu zdefiniowania sposobu realizacji zamówień odbiorców:</span><span class="sxs-lookup"><span data-stu-id="d8b60-116">Here are some of the parameters that can be set on the **Retail parameters** page to define how customer orders are fulfilled:</span></span>

-   <span data-ttu-id="d8b60-117">**Domyślne oprocentowanie lokaty** — Określ kwotę, jaką odbiorca musi wpłacić jako depozyt, zanim zamówienie zostanie potwierdzone.</span><span class="sxs-lookup"><span data-stu-id="d8b60-117">**Default deposit percentage** – Specify the amount that the customer must pay as a deposit before an order can be confirmed.</span></span> <span data-ttu-id="d8b60-118">Domyślna kwota kaucji jest obliczana jako procent wartości zamówienia.</span><span class="sxs-lookup"><span data-stu-id="d8b60-118">The default deposit amount is calculated as a percentage of the order value.</span></span> <span data-ttu-id="d8b60-119">W zależności od posiadanych uprawnień pracownik sklepu może być w stanie ręcznie zmienić tę kwotę za pomocą opcji **Zastąpienie wpłaty**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-119">Depending on privileges, a store associate might be able to override the amount by using **Deposit override**.</span></span>
-   <span data-ttu-id="d8b60-120">**Procent opłaty za anulowanie** — Jeśli z tytułu anulowania zamówienia odbiorcy będzie naliczana opłata, należy podać kwotę tej opłaty.</span><span class="sxs-lookup"><span data-stu-id="d8b60-120">**Cancellation charge percentage** – If a charge will be applied when a customer order is canceled, specify the amount of that charge.</span></span>
-   <span data-ttu-id="d8b60-121">**Kod opłaty za anulowanie** — Jeśli z tytułu anulowania zamówienia odbiorcy będzie naliczana opłata, ta opłata będzie wykazywana pod odpowiednim kodem opłaty w zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d8b60-121">**Cancellation charge code** – If a charge will be applied when a customer order is canceled, that charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="d8b60-122">Za pomocą tego parametru można zdefiniować kod opłaty za anulowanie.</span><span class="sxs-lookup"><span data-stu-id="d8b60-122">Use this parameter to define the cancellation charge code.</span></span>
-   <span data-ttu-id="d8b60-123">**Kod opłaty transportowej** — Sprzedawcy detaliczni mogą naliczać dodatkową opłatę za wysyłkę towarów do odbiorców.</span><span class="sxs-lookup"><span data-stu-id="d8b60-123">**Shipping charge code** – Retailers can charge an extra fee for shipping merchandise to a customer.</span></span> <span data-ttu-id="d8b60-124">Kwota tej opłaty transportowej zostanie wykazana pod odpowiednim kodem opłaty w zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d8b60-124">The amount of that shipping charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="d8b60-125">Ten parametr służy do mapowania kodu opłaty transportowej na opłaty transportowe w zamówieniu odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d8b60-125">Use this parameter to map the shipping charge code to shipping charges on the customer order.</span></span>
-   <span data-ttu-id="d8b60-126">**Zwróć opłaty transportowe** — Określ, czy opłaty transportowe skojarzone z zamówieniem odbiorcy podlegają zwrotowi.</span><span class="sxs-lookup"><span data-stu-id="d8b60-126">**Refund shipping charges** – Specify whether shipping charges that are associated with a customer order are refundable.</span></span>
-   <span data-ttu-id="d8b60-127">**Maksymalna kwota bez zatwierdzenia** — Jeśli opłaty transportowe podlegają zwrotowi, określ maksymalną kwotę takiego zwrotu dla wszystkich zamówień zwrotu.</span><span class="sxs-lookup"><span data-stu-id="d8b60-127">**Maximum amount without approval** – If shipping charges are refundable, specify the maximum amount of shipping charge refunds across return orders.</span></span> <span data-ttu-id="d8b60-128">Jeśli ta kwota zostanie przekroczona, w celu kontynuowania zwrotu jest konieczne ręczne zastąpienie przez menedżera.</span><span class="sxs-lookup"><span data-stu-id="d8b60-128">If this amount is exceeded, manager override is required in order to continue with the refund.</span></span> <span data-ttu-id="d8b60-129">Aby umożliwić realizację scenariuszy opisanych poniżej, zwrot opłaty transportowej może przekraczać pierwotnie zapłaconą kwotę:</span><span class="sxs-lookup"><span data-stu-id="d8b60-129">To accommodate the following scenarios, a refund of shipping charges can exceed the amount that was originally paid:</span></span>
    -   <span data-ttu-id="d8b60-130">Opłaty są stosowane na poziomie nagłówka zamówienia sprzedaży, a gdy pewna ilość z wiersza produktu jest zwracana, maksymalny zwrot opłat transportowych dozwolony dla produktów i ilości nie może zostać określony w sposób pasujący dla wszystkich odbiorców detalicznych.</span><span class="sxs-lookup"><span data-stu-id="d8b60-130">Charges are applied at the level of the sales order header, and when some quantity of a product line is returned, the maximum refund of shipping charges that is allowed for the products and the quantity can't be determined in way that works for all retail customers.</span></span>
    -   <span data-ttu-id="d8b60-131">Opłaty transportowe są ponoszone dla każdego zdarzenia wysyłki.</span><span class="sxs-lookup"><span data-stu-id="d8b60-131">Shipping charges are incurred for every instance of shipping.</span></span> <span data-ttu-id="d8b60-132">Jeśli odbiorca zwraca produkty wiele razy, a polityka sprzedawcy detalicznego określa, że ponosi on koszty zwrotu opłat transportowych, zwracane opłaty transportowe będą wyższe, niż faktyczne opłaty transportowe.</span><span class="sxs-lookup"><span data-stu-id="d8b60-132">If a customer returns products multiple times, and the retailer’s policy specifies that the retailer will bear the cost of return shipping charges, the return shipping charges will be more than the actual shipping charges.</span></span>

## <a name="transaction-flow-for-customer-orders"></a><span data-ttu-id="d8b60-133">Przepływ transakcji w zamówieniach odbiorców</span><span class="sxs-lookup"><span data-stu-id="d8b60-133">Transaction flow for customer orders</span></span>
### <a name="create-a-customer-order-in-retail-modern-pos"></a><span data-ttu-id="d8b60-134">Tworzenie zamówienia odbiorcy w aplikacji Retail Modern POS</span><span class="sxs-lookup"><span data-stu-id="d8b60-134">Create a customer order in Retail Modern POS</span></span>

1.  <span data-ttu-id="d8b60-135">Dodaj odbiorcę do transakcji.</span><span class="sxs-lookup"><span data-stu-id="d8b60-135">Add a customer to the transaction.</span></span>
2.  <span data-ttu-id="d8b60-136">Dodaj produkty do koszyka.</span><span class="sxs-lookup"><span data-stu-id="d8b60-136">Add products to the cart.</span></span>
3.  <span data-ttu-id="d8b60-137">Kliknij opcję **Utwórz zamówienie odbiorcy**, a następnie wybierz typ zamówienia.</span><span class="sxs-lookup"><span data-stu-id="d8b60-137">Click **Create customer order**, and then select the order type.</span></span> <span data-ttu-id="d8b60-138">Typem zamówienia może być **Zamówienie odbiorcy** lub **Oferta**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-138">The order type can be either **Customer order** or **Quote**.</span></span>
4.  <span data-ttu-id="d8b60-139">Kliknij opcję **Wyślij wybrane** lub **Wyślij wszystko**, aby wysłać produkty pod adres na koncie odbiorcy, określić żądaną datę wysyłki i określić opłaty transportowe.</span><span class="sxs-lookup"><span data-stu-id="d8b60-139">Click **Ship selected** or **Ship all** to ship the products to an address on the customer account, specify the requested shipping date, and specify shipping charges.</span></span>
5.  <span data-ttu-id="d8b60-140">Kliknij opcję **Odbierz wybrane** lub **Pobierz wszystko**, aby zaznaczyć produkty, które mają zostać pobrane z bieżącego sklepu lub innego sklepu w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="d8b60-140">Click **Pick up selected** or **Pick-up all** to select products that will be picked up from the current store or a different store on a specific date.</span></span>
6.  <span data-ttu-id="d8b60-141">Jeśli jest wymagana kaucja, pobierz ją.</span><span class="sxs-lookup"><span data-stu-id="d8b60-141">Collect the deposit amount, if a deposit is required.</span></span>

### <a name="edit-an-existing-customer-order"></a><span data-ttu-id="d8b60-142">Edytowanie istniejącego zamówienia odbiorcy</span><span class="sxs-lookup"><span data-stu-id="d8b60-142">Edit an existing customer order</span></span>

1.  <span data-ttu-id="d8b60-143">Na stronie głównej kliknij opcję **Znajdź zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-143">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="d8b60-144">Znajdź i zaznacz zamówienie, które chcesz zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="d8b60-144">Find and select the order to edit.</span></span> <span data-ttu-id="d8b60-145">U dołu strony kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-145">At the bottom of the page, click the **Edit**.</span></span>

### <a name="pick-up-an-order"></a><span data-ttu-id="d8b60-146">Pobieranie zamówienia</span><span class="sxs-lookup"><span data-stu-id="d8b60-146">Pick up an order</span></span>

1.  <span data-ttu-id="d8b60-147">Na stronie głównej kliknij opcję **Znajdź zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-147">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="d8b60-148">Zaznacz zamówienie, dla którego chcesz pobrać produkty.</span><span class="sxs-lookup"><span data-stu-id="d8b60-148">Select the order to pick up.</span></span> <span data-ttu-id="d8b60-149">U dołu strony kliknij opcję **Pobieranie i pakowanie**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-149">At the bottom of the page, click **Picking and packing**.</span></span>
3.  <span data-ttu-id="d8b60-150">Kliknij przycisk **Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-150">Click **Pick up**.</span></span>

### <a name="cancel-an-order"></a><span data-ttu-id="d8b60-151">Anulowanie zamówienia</span><span class="sxs-lookup"><span data-stu-id="d8b60-151">Cancel an order</span></span>

1.  <span data-ttu-id="d8b60-152">Na stronie głównej kliknij opcję **Znajdź zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-152">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="d8b60-153">Zaznacz zamówienie, które chcesz anulować.</span><span class="sxs-lookup"><span data-stu-id="d8b60-153">Select the order to cancel.</span></span> <span data-ttu-id="d8b60-154">U dołu strony kliknij przycisk **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-154">At the bottom of the page, click **Cancel**.</span></span>

#### <a name="create-a-return-order"></a><span data-ttu-id="d8b60-155">Tworzenie zamówienia zwrotu</span><span class="sxs-lookup"><span data-stu-id="d8b60-155">Create a return order</span></span>

1.  <span data-ttu-id="d8b60-156">Na stronie głównej kliknij opcję **Znajdź zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-156">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="d8b60-157">Zaznacz zamówienie, którego produkty chcesz zwrócić, zaznacz fakturę do zamówienia, a następnie zaznacz wiersz produktu, który chcesz zwrócić.</span><span class="sxs-lookup"><span data-stu-id="d8b60-157">Select the order to return, select the invoice for the order, and then select the product line for the merchandise to return.</span></span>
3.  <span data-ttu-id="d8b60-158">U dołu strony kliknij przycisk **Zwróć zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-158">At the bottom of the page, click the **Return order**.</span></span>

## <a name="asynchronous-transaction-flow-for-customer-orders"></a><span data-ttu-id="d8b60-159">Asynchroniczny przepływ transakcji w zamówieniach odbiorców</span><span class="sxs-lookup"><span data-stu-id="d8b60-159">Asynchronous transaction flow for customer orders</span></span>
<span data-ttu-id="d8b60-160">Zamówienia odbiorców mogą być tworzone w aplikacji klienckiej punktu sprzedaży (POS) w trybie synchronicznym lub asynchronicznym.</span><span class="sxs-lookup"><span data-stu-id="d8b60-160">Customer orders can be created from the point of sale (POS) client in either synchronous mode or asynchronous mode.</span></span>

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a><span data-ttu-id="d8b60-161">Włączanie funkcji tworzenia zamówień odbiorców w trybie asynchronicznym</span><span class="sxs-lookup"><span data-stu-id="d8b60-161">Enable customer orders to be created in asynchronous mode</span></span>

1.  <span data-ttu-id="d8b60-162">Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-162">Click **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profile** &gt; **Functionality profiles**.</span></span>
2.  <span data-ttu-id="d8b60-163">Na skróconej karcie **Ogólne** w opcji **Utwórz zamówienie odbiorcy w trybie asynchronicznym** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d8b60-163">On the **General** FastTab, set the **Create customer order in async mode** option to **Yes**.</span></span>

<span data-ttu-id="d8b60-164">Gdy opcja **Utwórz zamówienie odbiorcy w trybie asynchronicznym** jest ustawiona na **Tak**, zamówienia odbiorców są zawsze tworzone w trybie asynchronicznym, nawet jeśli jest dostępna usługa Retail Transaction Service (RTS).</span><span class="sxs-lookup"><span data-stu-id="d8b60-164">When the **Create customer order in async mode** option is set to **Yes**, customer orders are always created in asynchronous mode, even if Retail Transaction Service (RTS) is available.</span></span> <span data-ttu-id="d8b60-165">Jeśli ustawisz tę opcję na **Nie**, zamówienia odbiorców są zawsze tworzone w trybie synchronicznym przy użyciu usługi RTS.</span><span class="sxs-lookup"><span data-stu-id="d8b60-165">If you set this option to **No**, customer orders are always created in synchronous mode by using RTS.</span></span> <span data-ttu-id="d8b60-166">Po utworzeniu zamówień odbiorców w trybie asynchronicznym są one pobierane i wstawiane do modułu Handel detaliczny przez zadania ściągania (P).</span><span class="sxs-lookup"><span data-stu-id="d8b60-166">When customer orders are created in asynchronous mode, they are pulled and inserted into Retail by Pull (P) jobs.</span></span> <span data-ttu-id="d8b60-167">Odnośne zamówienia sprzedaży są tworzone w module Handel detaliczny podczas wykonywania operacji **Synchronizuj zamówienia** ręcznie lub w procesie wsadowym.</span><span class="sxs-lookup"><span data-stu-id="d8b60-167">The corresponding sales orders are created in Retail when **Synchronize orders** is run either manually or through a batch process.</span></span>

<a name="see-also"></a><span data-ttu-id="d8b60-168">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="d8b60-168">See also</span></span>
--------

[<span data-ttu-id="d8b60-169">Hybrydowe zamówienia odbiorców</span><span class="sxs-lookup"><span data-stu-id="d8b60-169">Hybrid customer orders</span></span>](hybrid-customer-orders.md)




