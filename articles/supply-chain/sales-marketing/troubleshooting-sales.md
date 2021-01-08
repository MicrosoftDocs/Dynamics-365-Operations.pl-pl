---
title: Rozwiązywanie problemów z zamówieniami sprzedaży
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zamówieniami sprzedaży.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6e51723915892f465ce09d09ee9ed622bab9451e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435180"
---
# <a name="troubleshoot-sales-orders"></a><span data-ttu-id="c8e0d-103">Rozwiązywanie problemów z zamówieniami sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c8e0d-103">Troubleshoot sales orders</span></span>

<span data-ttu-id="c8e0d-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zamówieniami sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-104">This topic describes how to fix issues that you might encounter while you work with sales orders.</span></span>

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a><span data-ttu-id="c8e0d-105">Informacje podatkowe nie są aktualizowane, jeśli zmieniam lokalizację w nagłówku zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-105">The tax information isn't updated if I change the location on a sales order header.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c8e0d-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c8e0d-106">Issue description</span></span>

<span data-ttu-id="c8e0d-107">Jeśli oddział, magazyn lub adres dostawy został zmieniony w nagłówku zamówienia sprzedaży lub na poziomie wiersza, informacje o podatku dla tych wierszy nie są automatycznie aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-107">If the site, warehouse, or delivery address is changed either on a sales order header or at the line level, the case tax information isn't automatically updated for the lines.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c8e0d-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c8e0d-108">Issue resolution</span></span>

<span data-ttu-id="c8e0d-109">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-109">This behavior is by design.</span></span> <span data-ttu-id="c8e0d-110">Ten problem występuje, ponieważ adres dostawy, oddział i magazyn nie są automatycznie zmieniane na poziomie wiersza.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-110">The issue occurs because the delivery address, site, and warehouse aren't automatically changed at the line level either.</span></span> <span data-ttu-id="c8e0d-111">Musisz zaktualizować je ręcznie.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-111">You must update them manually.</span></span>

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a><span data-ttu-id="c8e0d-112">Jeśli istnieją dwie umowy handlowe dla tego samego okresu lub okresów pokrywających się, zawsze jest wybierany ten sam wiersz umowy.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-112">If there are two trade agreements for the same period or overlapping periods, the same agreement line is always selected.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c8e0d-113">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c8e0d-113">Issue description</span></span>

<span data-ttu-id="c8e0d-114">Jeśli dwie umowy handlowe są zdefiniowane dla tego samego okresu lub nakładających się okresów, ta sama umowa handlowa wydaje się być wybierana za każdym razem, gdy tworzysz wiersze zamówienia sprzedaży, które zawierają te towary.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-114">If two trade agreements are defined for the same period or overlapping periods, the same trade agreement seems to be selected every time when you create sales order lines that contain those items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c8e0d-115">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c8e0d-115">Issue resolution</span></span>

<span data-ttu-id="c8e0d-116">Jeśli istnieje więcej niż jedna umowa handlowa dla danego dnia, zawsze jest wybierana umowa handlowa o najniższej cenie.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-116">If there is more than one trade agreement for a given date, the trade agreement that has the lowest price is always selected.</span></span> <span data-ttu-id="c8e0d-117">Aby uzyskać więcej informacji, pobierz następujący oficjalny dokument: [Umowy handlowe w Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span><span class="sxs-lookup"><span data-stu-id="c8e0d-117">For more information, download the following white paper: [Trade agreements in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span></span>

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a><span data-ttu-id="c8e0d-118">Czy można połączyć zamówienie zakupu z zamówieniem sprzedaży, aby zrealizować zapotrzebowanie?</span><span class="sxs-lookup"><span data-stu-id="c8e0d-118">Can I link a purchase order to a sales order to fulfill demand?</span></span>

<span data-ttu-id="c8e0d-119">Można utworzyć zamówienia zakupu na podstawie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-119">You can create a purchase order from a sales order.</span></span> <span data-ttu-id="c8e0d-120">Aby uzyskać więcej informacji, zobacz [Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży](tasks/create-purchase-order-sales-order.md).</span><span class="sxs-lookup"><span data-stu-id="c8e0d-120">For more information, see [Create a purchase order from a sales order](tasks/create-purchase-order-sales-order.md).</span></span>

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a><span data-ttu-id="c8e0d-121">Nie można anulować lub usunąć zamówienia zwrotu lub zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-121">I can't cancel or delete a return order or a sales order.</span></span>

<span data-ttu-id="c8e0d-122">Można anulować tylko zamówienia sprzedaży i zamówienia zwrotu, które są w stanie *Utworzone*.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-122">You can cancel only sales orders and return orders that are in a *Created* state.</span></span> <span data-ttu-id="c8e0d-123">Aby uzyskać więcej informacji, zobacz [Anulowanie zamówienia zwrotu](../service-management/cancel-return-order.md).</span><span class="sxs-lookup"><span data-stu-id="c8e0d-123">For more information, see [Cancel a return order](../service-management/cancel-return-order.md).</span></span>

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a><span data-ttu-id="c8e0d-124">Kiedy próbuję anulować zamówienie sprzedaży, pojawia się błąd „Nie można usunąć rezerwacji, ponieważ utworzono pracę, która opiera się na rezerwacjach”.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-124">When I try to cancel a sales order, I receive a "Reservations cannot be removed because there is work created which relies on the reservations" error.</span></span>

<span data-ttu-id="c8e0d-125">Jeśli praca jest skojarzona z zamówieniem sprzedaży, nie można anulować zamówienia sprzedaży, dopóki praca nie zostanie anulowana i wycofana.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-125">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="c8e0d-126">To wymaganie ma zastosowanie nawet wtedy, gdy praca skojarzona z zamówieniem sprzedaży jest zamknięta.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-126">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

<span data-ttu-id="c8e0d-127">Aby naprawić ten problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-127">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="c8e0d-128">Anuluj pracę i umieść zapasy z powrotem w żądanej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-128">Cancel the work, and put inventory back into the desired location.</span></span> <span data-ttu-id="c8e0d-129">Umożliwia przejście do odpowiedniego ładunku zamówienia sprzedaży i wybranie opcji **Zmniejsz ilość pobraną** w wierszu ładunku lub **Cofnij pracę** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-129">Go to the relevant load of the sales order, and select either **Reduce picked quantity** on the load line or **Reverse work** on the Action Pane.</span></span>

    <span data-ttu-id="c8e0d-130">Obecnie praca ma stan *Anulowane*, a nowe prace przesunięcia zapasów są automatycznie tworzone i przetwarzane w celu przeniesienia zapasów z powrotem do lokalizacji, która została opisana w momencie wycofania.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-130">The work now has a status of *Canceled*, and new inventory movement work is automatically created and processed to put inventory back into the location that was described at the time of reversal.</span></span>

2. <span data-ttu-id="c8e0d-131">Usuń ładunek.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-131">Delete the load.</span></span> <span data-ttu-id="c8e0d-132">Wysyłka jest również usuwana.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-132">The shipment is also deleted.</span></span>
3. <span data-ttu-id="c8e0d-133">Teraz powinno być możliwe przejście do tego zamówienia sprzedaży i anulowanie go.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-133">You should now be able to go to the sales order and cancel it.</span></span>

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a><span data-ttu-id="c8e0d-134">Nie mogę anulować międzyfirmowego zamówienia zakupu połączonego z zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-134">I can't cancel an intercompany purchase order that is linked to a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c8e0d-135">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c8e0d-135">Issue description</span></span>

<span data-ttu-id="c8e0d-136">Przy próbie anulowania międzyfirmowego zamówienia zakupu połączonego z zamówieniem sprzedaży może pojawić się następujący komunikat o błędzie: „Nie można zmniejszyć ilości, ponieważ pozostała ilość aktualizacji zmienia się”.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-136">If you try to cancel an intercompany purchase order that is linked to a sales order, you might receive the following error message: "Quantity cannot be reduced because the remaining update quantity changes sign."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c8e0d-137">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c8e0d-137">Issue resolution</span></span>

<span data-ttu-id="c8e0d-138">Ten błąd został rozwiązany w wersji 10.0.13 Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-138">This issue was fixed in Microsoft Dynamics 365 Supply Chain Management version 10.0.13.</span></span> <span data-ttu-id="c8e0d-139">W tej wersji systemu i nowszych wersjach można teraz anulować międzyfirmowe zamówienie zakupu połączone z zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-139">In that version and later versions, you can now cancel an intercompany purchase order that is linked to a sales order.</span></span>

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a><span data-ttu-id="c8e0d-140">Czy można przywrócić zafakturowane zamówienie sprzedaży, które zostało usunięte?</span><span class="sxs-lookup"><span data-stu-id="c8e0d-140">Can I restore an invoiced sales order that was deleted?</span></span>

### <a name="issue-description"></a><span data-ttu-id="c8e0d-141">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c8e0d-141">Issue description</span></span>

<span data-ttu-id="c8e0d-142">Zafakturowane zamówienie sprzedaży zostało usunięte przez pomyłkę i ma zostać przywrócone lub wyświetlone jego szczegóły.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-142">An invoiced sales order was deleted by mistake, and you want to restore it or view its details.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c8e0d-143">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c8e0d-143">Issue resolution</span></span>

<span data-ttu-id="c8e0d-144">Jeśli usunięte zamówienie sprzedaży zostało już zafakturowane, przejdź do **Konto odbiorcy \> Transakcje \> Dokument oryginalny \> Wyświetl szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-144">If the deleted sales order has already been invoiced, go to **Customer account \> Transactions \> Original document \> View details**.</span></span> <span data-ttu-id="c8e0d-145">Znajdź szukaną fakturę i wybierz ją, aby wyświetlić jej szczegóły.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-145">Find the invoice that you're looking for, and select it to view its details.</span></span> <span data-ttu-id="c8e0d-146">Szczegóły zawierają odwołanie do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-146">These details include the sales order reference.</span></span> <span data-ttu-id="c8e0d-147">Należy również uzyskać dostęp do szczegółów zamówienia sprzedaży z tej strony.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-147">You should also be able to access the sales order details from that page.</span></span>

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a><span data-ttu-id="c8e0d-148">Nie można odnaleźć terminu ostatecznego nagłówka zamówienia sprzedaży w jednostce danych SalesOrderHeaderV2Entity.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-148">The deadline of a sales order header can't be found in the SalesOrderHeaderV2Entity data entity.</span></span>

<span data-ttu-id="c8e0d-149">Pole terminu ostatecznego nie istnieje w jednostce *SalesOrderHeaderV2Entity*.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-149">The deadline field doesn't exist on the *SalesOrderHeaderV2Entity* entity.</span></span>

## <a name="i-must-delete-orphaned-sales-order-records"></a><span data-ttu-id="c8e0d-150">Należy usunąć oddzielone rekordy zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-150">I must delete orphaned sales order records.</span></span>

<span data-ttu-id="c8e0d-151">Aby oczyścić rekordy oddzielonych rekordów zamówienia sprzedaży, należy uruchomić zadanie okresowe *Usuwanie zamówień sprzedaży*, przechodząc do jednej z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="c8e0d-151">To clean up orphaned sales order records, run the *Sales order deletion* periodic job by going to either of the following places:</span></span>

- <span data-ttu-id="c8e0d-152">Sprzedaż i marketing \> Zadania okresowe \> Oczyszczanie \> Usuwanie zamówień zakupu</span><span class="sxs-lookup"><span data-stu-id="c8e0d-152">Sales and marketing \> Periodic tasks \> Clean up \> Delete sales orders</span></span>
- <span data-ttu-id="c8e0d-153">Handel detaliczny i inny \> Retail i Commerce — składniki IT \> Wyczyść \> Usuwanie zamówień zakupu</span><span class="sxs-lookup"><span data-stu-id="c8e0d-153">Retail and commerce \> Retail and commerce IT \> Clean up \> Delete sales orders</span></span>

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a><span data-ttu-id="c8e0d-154">Czy istnieje sposób obliczania prowizji dla faktur, które zostały już zaksięgowane?</span><span class="sxs-lookup"><span data-stu-id="c8e0d-154">Is there a way to calculate commissions on invoices that have already been posted?</span></span>

<span data-ttu-id="c8e0d-155">Supply Chain Management nie obsługuje obecnie obliczania prowizji za zaksięgowane faktury.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-155">Supply Chain Management doesn't currently support the calculation of commissions for posted invoices.</span></span>

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a><span data-ttu-id="c8e0d-156">Element pakietu nie jest obsługiwany w procesie międzyfirmowym.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-156">A bundle item isn't supported in an intercompany process.</span></span>

<span data-ttu-id="c8e0d-157">Pozycja pakietu jest niedostępna dla zamówienia zakupu, ponieważ w przypadku zbadania wierszy zamówienia sprzedaży dla towaru pakietu można zauważyć, że ilość wynosi *0* (zero), a stan jest *Anulowany*.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-157">The bundle item isn't available for the purchase order because, if you examine the sales order lines for the bundle item, you will notice that the quantity is *0* (zero) and the status is *Cancelled*.</span></span> <span data-ttu-id="c8e0d-158">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-158">This behavior is by design.</span></span> <span data-ttu-id="c8e0d-159">Zamówienie sprzedaży kupuje tylko składniki towaru pakietu.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-159">The sales order buys only the components of the bundle item.</span></span> <span data-ttu-id="c8e0d-160">Nie powoduje to nabycia samego towaru w pakiecie.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-160">It doesn't buy the bundle item itself.</span></span>

<span data-ttu-id="c8e0d-161">Jeśli trzeba kupić pakiet, należy rozważyć, czy należy go oznaczyć jako element pakietu, ponieważ jest on obecnie przeznaczony do scenariuszy rozpoznawania przychodów.</span><span class="sxs-lookup"><span data-stu-id="c8e0d-161">If you must buy a bundle, consider whether you have to mark it as bundle item, because this functionality is actually designed for revenue recognition scenarios.</span></span> <span data-ttu-id="c8e0d-162">Aby uzyskać więcej informacji o elementach pakietów, zobacz temat [Pakiety](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span><span class="sxs-lookup"><span data-stu-id="c8e0d-162">For more information about bundle items, see [Bundles](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span></span>
