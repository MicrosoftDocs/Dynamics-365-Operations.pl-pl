---
title: Koszt własny dla zwrotu i identyfikator partii zwrotu
description: Czasami jest potrzebna sytuacja, aby koszt zwróconych produktów był równy kosztowi produktów w momencie, gdy były sprzedawane odbiorcy. Można to uzyskać za pomocą ustawienia **Identyfikator partii zwrotu**.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnInventTransIdLookup, ReturnItemNumLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6206dea0665d479ce8dc6a7526a85414296e6935
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830411"
---
# <a name="return-cost-price-and-return-lot-id"></a><span data-ttu-id="09a4e-104">Koszt własny dla zwrotu i identyfikator partii zwrotu</span><span class="sxs-lookup"><span data-stu-id="09a4e-104">Return cost price and return lot ID</span></span>        

[!include [banner](../includes/banner.md)]



<span data-ttu-id="09a4e-105">Koszt produktów zwracanych do zapasów jest obliczany przy użyciu bieżącego kosztu produktów.</span><span class="sxs-lookup"><span data-stu-id="09a4e-105">The cost of products that are returned to inventory is calculated by using the current cost of the products.</span></span> <span data-ttu-id="09a4e-106">Jednak czasami jest potrzebna sytuacja, aby koszt zwróconych produktów był równy kosztowi produktów w momencie, gdy były sprzedawane odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="09a4e-106">However, you might want the cost of the returned products to equal the cost of the products at the time when you sold the products to the customer.</span></span> <span data-ttu-id="09a4e-107">Można to uzyskać za pomocą pola **Identyfikator partii zwrotu** znajdującego się na skróconej karcie **Szczegóły wiersza** w formularzu **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-107">You can do this by using the **Return lot ID** field on the **Line details** FastTab in the **Sales order** form.</span></span>

<span data-ttu-id="09a4e-108">Na przykład rozważmy następujący scenariusz.</span><span class="sxs-lookup"><span data-stu-id="09a4e-108">For example, consider the following scenario.</span></span> <span data-ttu-id="09a4e-109">Wystawiasz odbiorcy fakturę.</span><span class="sxs-lookup"><span data-stu-id="09a4e-109">You invoice a customer.</span></span> <span data-ttu-id="09a4e-110">Następnie odbiorca zwraca Ci otrzymane produkty.</span><span class="sxs-lookup"><span data-stu-id="09a4e-110">Then, the customer returns the delivered products to you.</span></span> <span data-ttu-id="09a4e-111">Ty zwracasz produkty do zapasów.</span><span class="sxs-lookup"><span data-stu-id="09a4e-111">You return the products to stock.</span></span> <span data-ttu-id="09a4e-112">W takim przypadku kiedy uznajesz konto odbiorcy za zwrócone produkty, koszt tych produktów jest obliczany przy użyciu bieżącego kosztu produktów.</span><span class="sxs-lookup"><span data-stu-id="09a4e-112">In this case, when you credit the customer for the returned products, the cost of those products is calculated by using the current cost of the products.</span></span> <span data-ttu-id="09a4e-113">Jednak jeśli użyjesz pola **Identyfikator partii zwrotu**, koszt zwróconych produktów jest obliczany przy użyciu kosztu z faktury za pierwotną sprzedaż do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="09a4e-113">However, if you use the **Return lot ID** field, the cost of the returned products is calculated by using the cost on the invoice of the original sale to the customer.</span></span>

<span data-ttu-id="09a4e-114">Aby do zwrotów od odbiorcy zastosować koszt inny niż bieżący, należy użyć jednej z następujących metod.</span><span class="sxs-lookup"><span data-stu-id="09a4e-114">To use a cost other than the current cost for returns from a customer, use one of the following methods.</span></span>

## <a name="method-1-manually-enter-the-return-cost-price"></a><span data-ttu-id="09a4e-115">Metoda 1: Ręczne wprowadzenie kosztu własnego zwrotu</span><span class="sxs-lookup"><span data-stu-id="09a4e-115">Method 1: Manually enter the return cost price</span></span>

<span data-ttu-id="09a4e-116">Domyślnie podczas dodawania towarów do zamówienia zwrotu towary są zwracane do zapasów według bieżącego kosztu własnego.</span><span class="sxs-lookup"><span data-stu-id="09a4e-116">By default, when you add items to a return order, the items are returned to inventory at the current cost price.</span></span> <span data-ttu-id="09a4e-117">Aby określić inny koszt własny zwrotu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="09a4e-117">To specify a different return cost price, follow these steps.</span></span>

1.  <span data-ttu-id="09a4e-118">Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-118">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="09a4e-119">W **okienku akcji** w grupie **Nowy** kliknij opcję **Zamówienie zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-119">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="09a4e-120">W formularzu **Utwórz zamówienie zwrotu** wybierz konto odbiorcy, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-120">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="09a4e-121">W formularzu **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2** zaznacz towar, a następnie wprowadź ilość ujemną w polu **Ilość**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-121">In the **Return order - RMA number: %1, %2** form, select an item, and then enter a negative quantity in the **Quantity** field.</span></span>

5.  <span data-ttu-id="09a4e-122">Kliknij skróconą kartę **Szczegóły wiersza**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-122">Click the **Line details** FastTab.</span></span>

6.  <span data-ttu-id="09a4e-123">Na karcie **Ogólne** wprowadź wartość w polu **Koszt własny dla zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-123">On the **General** tab, enter a value in the **Return cost price** field.</span></span> <span data-ttu-id="09a4e-124">Ta wartość będzie używana podczas zwracania towarów do zapasów.</span><span class="sxs-lookup"><span data-stu-id="09a4e-124">This value is used when the goods are returned to inventory.</span></span> <span data-ttu-id="09a4e-125">Jeśli nie wprowadzisz wartości, podczas zwrotu towarów do zapasów będzie używany bieżący koszt własny.</span><span class="sxs-lookup"><span data-stu-id="09a4e-125">If you do not enter a value, the current cost price is used when the goods are returned to inventory.</span></span>

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a><span data-ttu-id="09a4e-126">Metoda 2: Automatyczne generowanie kosztu własnego na podstawie wiersza faktury dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="09a4e-126">Method 2: Automatically generate the cost price based on the customer invoice line</span></span>

<span data-ttu-id="09a4e-127">Jest to preferowana metoda tworzenia wierszy zwrotu.</span><span class="sxs-lookup"><span data-stu-id="09a4e-127">This is the preferred method to use to create return lines.</span></span> <span data-ttu-id="09a4e-128">Aby użyć kosztu produktów z chwili, gdy produkty były sprzedawane odbiorcy, utwórz zamówienie zwrotu i wskaż wiersz sprzedaży do zwrotu.</span><span class="sxs-lookup"><span data-stu-id="09a4e-128">To use the cost of the products at the time when you sold the products to the customer, create a return order and specify a sales line to return.</span></span>

1.  <span data-ttu-id="09a4e-129">Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-129">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="09a4e-130">W **okienku akcji** w grupie **Nowy** kliknij opcję **Zamówienie zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-130">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="09a4e-131">W formularzu **Utwórz zamówienie zwrotu** wybierz konto odbiorcy, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-131">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="09a4e-132">W formularzu **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2** w **okienku akcji** kliknij przycisk **Znajdź zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-132">In the **Return order - RMA number: %1, %2** form, on the **Action Pane**, click **Find sales order**.</span></span>

5.  <span data-ttu-id="09a4e-133">W formularzu **Znajdź zamówienie sprzedaży** wybierz wiersz faktury, z którego produkty chcesz zwrócić, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-133">In the **Find sales order** form, select the invoice line to return, and then click **OK**.</span></span>
    
    <span data-ttu-id="09a4e-134">Na skróconej karcie **Szczegóły wiersza** na karcie **Ogólne** pole **Identyfikator partii zwrotu** pokazuje wartość z oryginalnego wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="09a4e-134">On the **Line details** FastTab, on the **General** tab, the **Return lot ID** field displays the value from the original sales line.</span></span> <span data-ttu-id="09a4e-135">Ponadto pole **Koszt własny dla zwrotu** zawiera wartość kosztu z oryginalnego wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="09a4e-135">Additionally, the **Return cost price** field displays the cost value from the original sales line.</span></span>

## <a name="cost-calculation-example"></a><span data-ttu-id="09a4e-136">Przykład obliczania kosztu</span><span class="sxs-lookup"><span data-stu-id="09a4e-136">Cost calculation example</span></span>

<span data-ttu-id="09a4e-137">Jeżeli do określenia kosztu własnego zwrotu użyjesz pola **Identyfikator partii zwrotu** w wierszu zamówienia zwrotu, zostanie użyty koszt z wiersza zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="09a4e-137">When you use the **Return lot ID** field on a return order line to specify the return cost price, the cost on the return order line is used.</span></span> <span data-ttu-id="09a4e-138">Po uruchomieniu funkcji zamknięcia lub ponownego obliczania zapasów nastąpi korekta kosztu w oryginalnym wierszu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="09a4e-138">If you run the inventory close or recalculation functionality, the cost is adjusted on the original sales line.</span></span> <span data-ttu-id="09a4e-139">Koszt w wierszu zamówienia zwrotu zostanie automatycznie skorygowany, aby pokazywać ten sam koszt za sztukę.</span><span class="sxs-lookup"><span data-stu-id="09a4e-139">The cost on the return order line is automatically adjusted to reflect the same cost per piece.</span></span>

1.  <span data-ttu-id="09a4e-140">Utwórz i zwolnij produkt o nazwie Test.</span><span class="sxs-lookup"><span data-stu-id="09a4e-140">Create and release a product that is named Test.</span></span> <span data-ttu-id="09a4e-141">W formularzu **Szczegóły zwolnionego produktu** określ następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="09a4e-141">In the **Released product details** form, specify the following information:</span></span>
    
    1.  <span data-ttu-id="09a4e-142">Na skróconej karcie **Zarządzanie kosztami** w polu **Grupa pozycji** zaznacz grupę **Części**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-142">On the **Manage costs** FastTab, in the **Item group** field, select the **Parts** group.</span></span>
    
    2.  <span data-ttu-id="09a4e-143">Na skróconej karcie **Ogólne** w polu **Grupa modeli pozycji** zaznacz opcję **DEF**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-143">On the **General** FastTab, in the **Item model group** field, select **DEF**.</span></span>
    
    3.  <span data-ttu-id="09a4e-144">Na skróconej karcie **Zakup** w polu **Cena** wpisz wartość 10,00 jako koszt własny towaru.</span><span class="sxs-lookup"><span data-stu-id="09a4e-144">On the **Purchase** FastTab, in the **Price** field, type 10.00 as the cost price of the item.</span></span>
    
    4.  <span data-ttu-id="09a4e-145">W **okienku akcji** kliknij pozycję **Grupy wymiarów**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-145">On the **Action Pane**, click **Dimension groups**.</span></span> <span data-ttu-id="09a4e-146">W polu **Grupa wymiarów magazynowania** zaznacz opcję **Tylko oddział i magazyn**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-146">In the **Storage dimension group** field, select **Site and Warehouse only**.</span></span> <span data-ttu-id="09a4e-147">W polu **Grupa wymiarów śledzenia** zaznacz opcję **Brak aktywnych wymiarów śledzenia**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-147">In the **Tracking dimension group** field, select **No active tracking dimensions**.</span></span>

2.  <span data-ttu-id="09a4e-148">Utwórz zamówienie zakupu na 10 sztuk towaru Test w cenie 6,00 za sztukę, a następnie zaksięguj fakturę dla zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="09a4e-148">Create a purchase order for 10 pieces of the Test item at 6.00 per piece, and then post an invoice for the purchase order.</span></span>
    
    <span data-ttu-id="09a4e-149">Utwórz drugie zamówienie zakupu na 10 sztuk towaru Test w cenie 8,00 za sztukę, a następnie zaksięguj fakturę dla zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="09a4e-149">Create a second purchase order for 10 pieces of the Test item at 8.00 per piece, and then post an invoice for the purchase order.</span></span>

3.  <span data-ttu-id="09a4e-150">Zaksięguj fakturę dla zamówienia sprzedaży dotyczącego sprzedaży 5 sztuk towaru Test.</span><span class="sxs-lookup"><span data-stu-id="09a4e-150">Post an invoice for a sales order to sell five pieces of the Test item.</span></span>
    
    <span data-ttu-id="09a4e-151">W takim przypadku wiersz zamówienia sprzedaży zostanie wyceniony na 35,00 (5 sztuk \* 7,00 średni koszt za sztukę).</span><span class="sxs-lookup"><span data-stu-id="09a4e-151">In this case, the sales order line is costed at 35.00 (5 pieces \* 7.00 average cost per piece).</span></span>

4.  <span data-ttu-id="09a4e-152">Utwórz zamówienie zwrotu dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="09a4e-152">Create a return order for the customer.</span></span> <span data-ttu-id="09a4e-153">W formularzu **Znajdź zamówienie sprzedaży** wybierz wiersz faktury, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-153">In the **Find sales order** form, select the invoice line, and then click **OK**.</span></span>

5.  <span data-ttu-id="09a4e-154">W formularzu **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2** sprawdź, czy zostało wygenerowane zamówienie zwrotu dotyczące zwrotu towaru Test.</span><span class="sxs-lookup"><span data-stu-id="09a4e-154">In the **Return order - RMA number: %1, %2** form, verify that a return order is generated to return the Test item.</span></span> <span data-ttu-id="09a4e-155">Ilość w zamówieniu zwrotu powinna być ustawiona na -5,00.</span><span class="sxs-lookup"><span data-stu-id="09a4e-155">The quantity of the return order is set to -5.00.</span></span>
    
    <span data-ttu-id="09a4e-156">W polu **Identyfikator partii zwrotu** jest wyświetlany identyfikator partii.</span><span class="sxs-lookup"><span data-stu-id="09a4e-156">The **Return lot ID** field displays a lot ID.</span></span> <span data-ttu-id="09a4e-157">Ten identyfikator partii pochodzi z oryginalnego zamówienia sprzedaży na towar sprzedany odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="09a4e-157">This lot ID is taken from the original sales order of the item that was sold to the customer.</span></span> <span data-ttu-id="09a4e-158">Pole **Koszt własny dla zwrotu** zawiera koszt własny z oryginalnego wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="09a4e-158">The **Return cost price** field displays the cost price from the original sales line.</span></span>

6.  <span data-ttu-id="09a4e-159">Zarejestruj przyjęcie zwróconych towarów.</span><span class="sxs-lookup"><span data-stu-id="09a4e-159">Register the receipt of the returned items.</span></span>

7.  <span data-ttu-id="09a4e-160">Zaksięguj dokument dostawy zwróconych towarów.</span><span class="sxs-lookup"><span data-stu-id="09a4e-160">Post a packing slip for the returned items.</span></span>

8.  <span data-ttu-id="09a4e-161">Zaksięguj fakturę dla zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="09a4e-161">Post an invoice for the return order.</span></span> <span data-ttu-id="09a4e-162">Na stronie listy **Wszystkie zamówienia sprzedaży** wybierz zamówienie sprzedaży, dla którego typem zamówienia jest **Zwrot towaru**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-162">On the **All sales orders** list page, select a sales order for which **Returned order** is the order type.</span></span>

9.  <span data-ttu-id="09a4e-163">Otwórz formularz **Transakcje magazynowe**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-163">Open the **Inventory transactions** form.</span></span> <span data-ttu-id="09a4e-164">Sprawdź, czy zwrot jest wyceniony na 7,00 za sztukę, oglądając w tym celu wartość w polu **Koszt własny dla zwrotu**, i łącznie 35,00 w polu **Kwota kosztu**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-164">Verify that the return is costed at 7.00 per piece by using the value in the **Return cost price** field, for a total of 35.00 in the **Cost amount** field.</span></span> <span data-ttu-id="09a4e-165">Formularz **Transakcje magazynowe** można otworzyć z poziomu formularza **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-165">You can open the **Inventory transactions** form from the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="09a4e-166">W siatce **Wiersze** kliknij kolejno opcje **Zapasy** \> **Transakcje**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-166">In the **Lines** grid, click **Inventory** \> **Transactions**.</span></span>

10. <span data-ttu-id="09a4e-167">W module Zarządzanie zapasami i magazynem użyj formularza **Zamknięcie i korekta**, aby wykonać procedurę **3. Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="09a4e-167">In Inventory and warehouse management, use the **Closing and adjustment** form to run the **3. Close** procedure.</span></span>
    
    <span data-ttu-id="09a4e-168">Ta akcja spowoduje skorygowanie kosztu oryginalnego wiersza sprzedaży, który został wyceniony na -35,00 (5 sztuk \* 7,00), na -30,00 (5 sztuk \* 6,00).</span><span class="sxs-lookup"><span data-stu-id="09a4e-168">This action adjusts the cost on the original sales line that was costed at -35.00 (5 pieces \* 7.00) to -30.00 (5 pieces \* 6.00).</span></span> <span data-ttu-id="09a4e-169">Stanie się tak dlatego, że grupa modeli zapasów używa schematu Pierwszy na wejściu — pierwszy na wyjściu (First in, first out; FIFO), a 6,00 za sztukę jest kosztem FIFO z pierwszego zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="09a4e-169">This is because the inventory model group uses First in, First out (FIFO), and 6.00 per piece is the FIFO cost from the first purchase order.</span></span> <span data-ttu-id="09a4e-170">Ponadto działanie spowoduje korektę kosztu w wierszu sprzedaży zwrotu w celu dopasowania kosztu za sztukę w oryginalnym wierszu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="09a4e-170">Additionally, the action adjusts the cost on the return sales line to match the cost per piece on the original sales line.</span></span> <span data-ttu-id="09a4e-171">W efekcie koszt wiersza zwrotu zostanie skorygowany z 35,00 na 30,00.</span><span class="sxs-lookup"><span data-stu-id="09a4e-171">Therefore, the cost of the return line is adjusted from 35.00 to 30.00.</span></span>




