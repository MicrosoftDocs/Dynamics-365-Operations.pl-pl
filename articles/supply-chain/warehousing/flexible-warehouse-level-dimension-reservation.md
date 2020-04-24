---
title: Zasada rezerwacji wymiarów na poziomie magazynu elastycznego
description: W tym temacie opisano zasady rezerwacji zapasów, które umożliwiają firmom sprzedaż produktów śledzonych partiami i uruchamianie ich zagadnień logistycznych w miarę operacji obsługujących WMS, rezerwując określone partie dla zamówień sprzedaży odbiorców, nawet jeśli hierarchia rezerwacji jest skojarzone z produktami nie zezwalają na rezerwację konkretnych partii.
author: omulvad
manager: tfehr
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 0fe9ed9f2bebe8683f3b8bb37b33e8a63b9521f6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205674"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a><span data-ttu-id="c4b43-103">Zasada rezerwacji wymiarów na poziomie magazynu elastycznego</span><span class="sxs-lookup"><span data-stu-id="c4b43-103">Flexible warehouse-level dimension reservation policy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4b43-104">Jeśli hierarchia rezerwacji zapasów typu „Lokalizacja towaru\[poniżej\]” jest skojarzona z produktami, firmy, które sprzedają produkty śledzone partiami i uruchamiają ich logistykę jako operacje włączone dla systemu zarządzania Microsoft Dynamics 365 Warehouse Management System (WMS), nie mogą zarezerwować określonych partii tych produktów dla zamówień sprzedaży odbiorców.</span><span class="sxs-lookup"><span data-stu-id="c4b43-104">When an inventory reservation hierarchy of the "Batch-below\[location\]" type is associated with products, businesses that sell batch-tracked products and run their logistics as operations that are enabled for the Microsoft Dynamics 365 Warehouse Management System (WMS) can't reserve specific batches of those products for customer sales orders.</span></span> <span data-ttu-id="c4b43-105">W tym temacie opisano zasady rezerwacji zapasów, które pozwalają tym firmom zarezerwować określone partie, nawet jeśli produkty są skojarzone z hierarchią rezerwacji "Lokalizacja towaru\[poniżej\].</span><span class="sxs-lookup"><span data-stu-id="c4b43-105">This topic describes the inventory reservation policy that lets these businesses reserve specific batches, even when the products are associated with a "Batch-below\[location\]" reservation hierarchy.</span></span>

## <a name="inventory-reservation-hierarchy"></a><span data-ttu-id="c4b43-106">Hierarchie rezerwacji zapasów</span><span class="sxs-lookup"><span data-stu-id="c4b43-106">Inventory reservation hierarchy</span></span>

<span data-ttu-id="c4b43-107">Ta sekcja podsumowuje istniejącą hierarchię rezerwacji zapasów.</span><span class="sxs-lookup"><span data-stu-id="c4b43-107">This section summarizes the existing inventory reservation hierarchy.</span></span> <span data-ttu-id="c4b43-108">Koncentruje się na sposobie obsługi śledzonych i prześledzonych towarów w partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-108">It focuses on the way that batch-tracked and serial-tracked items are handled.</span></span>

<span data-ttu-id="c4b43-109">Hierarchia rezerwacji zapasów określa, że w zakresie, w jakim dotyczy to wymiarów przechowywania, zamówienie wymaga obowiązkowych wymiarów oddziału, magazynu i stanu zapasów, podczas gdy logika magazynu jest odpowiedzialna za przypisanie lokalizacji do wnioskowane ilości i rezerwowanie lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-109">The inventory reservation hierarchy dictates that, as far as storage dimensions are concerned, the demand order carries the mandatory dimensions of site, warehouse, and inventory status, whereas the warehouse logic is responsible for assigning a location to the requested quantities and reserving the location.</span></span> <span data-ttu-id="c4b43-110">Innymi słowy, w interakcjach między zamówieniem popytu a operacjami magazynowymi, oczekuje się, że zamówienie musi być wysłane z magazynu (czyli oddziału i magazynu).</span><span class="sxs-lookup"><span data-stu-id="c4b43-110">In other words, in the interactions between the demand order and the warehouse operations, the demand order is expected to indicate where the order must be shipped from (that is, what site and warehouse).</span></span> <span data-ttu-id="c4b43-111">Następnie magazynpolega na logice, aby znaleźć wymaganą ilość miejsca w pomieszczeniu magazynowym.</span><span class="sxs-lookup"><span data-stu-id="c4b43-111">The warehouse then relies on its logic to find the required quantity in the warehouse premises.</span></span>

<span data-ttu-id="c4b43-112">Jednak w celu odzwierciedlenia modelu operacyjnego firmy, wymiary śledzenia (numery partii i numery seryjne) podlegają większej elastyczności.</span><span class="sxs-lookup"><span data-stu-id="c4b43-112">However, to reflect the operational model of the business, tracking dimensions (batch and serial numbers) are subject to more flexibility.</span></span> <span data-ttu-id="c4b43-113">Hierarchia rezerwacji zapasów może uwzględniać scenariusze, w których obowiązują następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="c4b43-113">An inventory reservation hierarchy can accommodate scenarios where the following conditions apply:</span></span>

- <span data-ttu-id="c4b43-114">Firma korzysta z operacji magazynowych w celu zarządzania pobieraniem ilości o numerach partii lub seryjnych po znalezieniu ilości w przestrzeni magazynowej.</span><span class="sxs-lookup"><span data-stu-id="c4b43-114">The business relies on its warehouse operations to manage picking of quantities that have batch or serial numbers after the quantities have been found in the warehousing storage space.</span></span> <span data-ttu-id="c4b43-115">Ten model jest często określany mianem *lokalizacji towaru\[poniżej\]*.</span><span class="sxs-lookup"><span data-stu-id="c4b43-115">This model is often referred to as *Batch-below\[location\]*.</span></span> <span data-ttu-id="c4b43-116">Jest zwykle używany w przypadku, gdy identyfikacja numeru partii produktu lub numeru seryjnego nie ma znaczenia dla odbiorców, którzy nakładają popyt na firmę sprzedającą.</span><span class="sxs-lookup"><span data-stu-id="c4b43-116">It's typically used when a product's batch or serial number identification isn't important to the customers who place the demand with the selling company.</span></span>
- <span data-ttu-id="c4b43-117">Jeśli numery partii lub numerów seryjnych są częścią specyfikacji zamówienia odbiorcy i są rejestrowane na zamówieniu popytu, operacje magazynowe, które wyszukują ilości w magazynie, są ograniczone przez określone żądane numery i nie mogą być zmieniane.</span><span class="sxs-lookup"><span data-stu-id="c4b43-117">If batch or serial numbers are part of a customer's order specification, and they are recorded on the demand order, the warehouse operations that find the quantities in the warehouse are constrained by the specific requested numbers and aren't allowed to change them.</span></span> <span data-ttu-id="c4b43-118">Ten model jest często określany mianem *lokalizacji towaru\[powyżejj\]*.</span><span class="sxs-lookup"><span data-stu-id="c4b43-118">This model is referred to as *Batch-above\[location\]*.</span></span>

<span data-ttu-id="c4b43-119">W tych scenariuszach wyzwanie polega na tym, że tylko jedna hierarchia rezerwacji zapasów może być przypisana do każdego zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="c4b43-119">In these scenarios, the challenge is that only one inventory reservation hierarchy can be assigned to each released product.</span></span> <span data-ttu-id="c4b43-120">Dlatego w przypadku modułu WMS do obsługi śledzonych elementów, gdy przypisanie hierarchii określa, kiedy numer partii lub seryjny ma zostać zarezerwowany (gdy zamówienie jest wykonywane lub w trakcie pracy pobrania magazynowego), nie można zmienić tego chronometrażu na zasadzie ad hoc.</span><span class="sxs-lookup"><span data-stu-id="c4b43-120">Therefore, for the WMS to handle tracked items, after the hierarchy assignment determines when the batch or serial number should be reserved (either when the demand order is taken or during the warehouse picking work), this timing can't be changed on an ad-hoc basis.</span></span>

## <a name="flexible-reservation-for-batch-tracked-items"></a><span data-ttu-id="c4b43-121">Rezerwacja elastyczna dla pozycji śledzonych w partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-121">Flexible reservation for batch-tracked items</span></span>

### <a name="business-scenario"></a><span data-ttu-id="c4b43-122">Scenariusz biznesowy</span><span class="sxs-lookup"><span data-stu-id="c4b43-122">Business scenario</span></span>

<span data-ttu-id="c4b43-123">W tym scenariuszu firma korzysta z strategii zapasów, w której gotowe towary są śledzone według numerów partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-123">In this scenario, a company uses an inventory strategy where finished goods are tracked by batch numbers.</span></span> <span data-ttu-id="c4b43-124">Ta firma również korzysta z obciążenia pracą WMS.</span><span class="sxs-lookup"><span data-stu-id="c4b43-124">This company also uses the WMS workload.</span></span> <span data-ttu-id="c4b43-125">Ponieważ w ramach tego obciążenia istnieje dobrze wyposażona logika planowania i uruchamiania operacji pobierania i wysyłania magazynowych dla towarów z włączonym przetwarzaniem wsadowym, większość gotowych towarów jest skojarzona z hierarchią rezerwacji "zapasów poniżej\[lokalizacji\]".</span><span class="sxs-lookup"><span data-stu-id="c4b43-125">Because this workload has well-equipped logic for planning and running warehouse picking and shipping operations for batch-enabled items, most of the finished items are associated with a "Batch-below\[location\]" inventory reservation hierarchy.</span></span> <span data-ttu-id="c4b43-126">Zaletą tego typu konfiguracji operacyjnej jest to, że decyzje (które są skutecznymi decyzjami dotyczącymi rezerwacji), które partie do pobrania i miejsca, gdzie mają zostać umieszczone w magazynie, są odkładane do momentu rozpoczęcia operacji pobrania z magazynu.</span><span class="sxs-lookup"><span data-stu-id="c4b43-126">The advantage of this type of operational setup is that decisions (which are effectively reservation decisions) about which batches to pick and where to put them in the warehouse are postponed until the warehouse picking operations start.</span></span> <span data-ttu-id="c4b43-127">Nie zostają one wykonane, gdy zamówienie odbiorcy zostanie złożone.</span><span class="sxs-lookup"><span data-stu-id="c4b43-127">They aren't made when the customer's order is placed.</span></span>

<span data-ttu-id="c4b43-128">Mimo że hierarchia rezerwacji "Lokalizacji towaru\[poniżej\]" obsługuje również cele biznesowe firmy, wiele odbiorców z firmy prowadzącej działalność w firmie wymaga tej samej partii, którą zostały wcześniej zakupione podczas zamawiania produktów.</span><span class="sxs-lookup"><span data-stu-id="c4b43-128">Although the "Batch-below\[location\]" reservation hierarchy serves the company's business goals well, many of the company's established customers require the same batch that they previously purchased when they reorder products.</span></span> <span data-ttu-id="c4b43-129">Z tego względu firma poszukuje elastyczności w sposobie obsługi reguł rezerwacji partii, dzięki czemu w zależności od zapotrzebowania klienta dla tego samego towaru mają miejsce następujące zachowania:</span><span class="sxs-lookup"><span data-stu-id="c4b43-129">Therefore, the company is looking for flexibility in the way that the batch reservation rules are handled, so that, depending on the customers' demand for the same item, the following behaviors occur:</span></span>

- <span data-ttu-id="c4b43-130">Numer partii może zostać zarejestrowany i zarezerwowany, gdy zamówienie jest wykonywane przez przetwórcę sprzedaży, i nie można go zmienić podczas operacji magazynowych i/lub w przypadku innych zapotrzebowań.</span><span class="sxs-lookup"><span data-stu-id="c4b43-130">A batch number can be recorded and reserved when the order is taken by the sales processor, and it can't be changed during warehouse operations and/or taken by other demands.</span></span> <span data-ttu-id="c4b43-131">To zachowanie pomaga zagwarantować, że zamówiony numer partii jest wysyłany do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-131">This behavior helps guarantee that the batch number that was ordered is shipped to the customer.</span></span>
- <span data-ttu-id="c4b43-132">Jeśli numer partii nie jest ważny dla odbiorcy, operacje magazynowe mogą określać numer partii podczas pracy pobierania, po zakończeniu rejestracji i rezerwacji zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c4b43-132">If the batch number isn't important to the customer, the warehouse operations can determine a batch number during picking work, after sales order registration and reservation have been done.</span></span>

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a><span data-ttu-id="c4b43-133">Umożliwienie rezerwacji konkretnej partii w zamówieniu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c4b43-133">Allowing reservation of a specific batch on the sales order</span></span>

<span data-ttu-id="c4b43-134">Aby określić wymaganą elastyczność w zachowaniu rezerwacji partii dla towarów skojarzonych z hierarchią rezerwacji magazynowej "Lokalizacji towaru\[poniżej\], menedżerowie magazynów muszą zaznaczyć pole wyboru **Zezwalaj na rezerwację na zamówieniu** na zapotrzebowaniu dla **Numeru partii** na stronie **hierarchie rezerwacji zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-134">To accommodate the desired flexibility in the batch reservation behavior for items that are associated with a "Batch-below\[location\]" inventory reservation hierarchy, inventory managers must select the **Allow reservation on demand order** check box for the **Batch number** level on the **Inventory reservation hierarchies** page.</span></span>

![Uczynienie hierarchii rezerwacji zapasów elastyczną](media/Flexible-inventory-reservation-hierarchy.png)

<span data-ttu-id="c4b43-136">W przypadku wybrania poziomu **Numeru partii** w hierarchii wszystkie wymiary powyżej tego poziomu i na poziomie **Lokalizacji** zostaną wybrane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="c4b43-136">When the **Batch number** level in the hierarchy is selected, all dimensions above that level and up through the **Location** level will be automatically selected.</span></span> <span data-ttu-id="c4b43-137">(Domyślnie zaznaczone są wszystkie wymiary powyżej poziomu **Lokalizacji**). To zachowanie odzwierciedla logikę, w której wszystkie wymiary w zakresie między numerem partii i lokalizacją są również automatycznie rezerwowane po zarezerwowaniu określonego numeru partii w wierszu zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c4b43-137">(By default, all dimensions above the **Location** level are preselected.) This behavior reflects the logic where all dimensions in the range between the batch number and location are also automatically reserved after you reserve a specific batch number on the order line.</span></span>

> [!NOTE]
> <span data-ttu-id="c4b43-138">Pole wyboru **Zezwalaj na rezerwację na zamówieniu popytu** dotyczy tylko poziomów hierarchii rezerwacji poniżej wymiaru lokalizacji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="c4b43-138">The **Allow reservation on demand order** check box applies only to reservation hierarchy levels that are below the warehouse location dimension.</span></span>
>
> <span data-ttu-id="c4b43-139">**Numer partii** jest jedynym poziomem hierarchii otwartym dla elastycznych zasad rezerwacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-139">**Batch number** is the only level in the hierarchy that is open for the flexible reservation policy.</span></span> <span data-ttu-id="c4b43-140">Innymi słowy, nie można zaznaczyć pola wyboru **Zezwalaj na rezerwację na zamówieniu popytu** dla **Lokalizacji**, **numeru identyfikacyjnego** lub **numeru seryjnego**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-140">In other words, you can't select the **Allow reservation on demand order** check box for the **Location**, **License plate**, or **Serial number** level.</span></span>
>
> <span data-ttu-id="c4b43-141">Jeśli hierarchia rezerwacji zawiera wymiar numeru seryjnego (który musi być zawsze poniżej poziomu **numeru partii**), a w przypadku rezerwacji specyficznej dla danej partii dla numeru partii, system będzie kontynuował obsługę rezerwacji numerów seryjnych i operacji pobrania na podstawie reguł dotyczących zasad rezerwacji „Numer poniżej\[lokalizacji\]”.</span><span class="sxs-lookup"><span data-stu-id="c4b43-141">If your reservation hierarchy includes the serial number dimension (which must always be below the **Batch number** level), and if you've turned on batch-specific reservation for the batch number, the system will continue to handle serial number reservation and picking operations, based on the rules that apply to the "Serial-below\[location\]" reservation policy.</span></span>

<span data-ttu-id="c4b43-142">W dowolnym momencie można zezwolić na przetwarzanie specyficznego przetwarzania wsadowego istniejącej hierarchii rezerwacji „Lokalizacja towaru\[poniżej\]” w rozmieszczeniu.</span><span class="sxs-lookup"><span data-stu-id="c4b43-142">At any point, you can allow batch-specific reservation for an existing "Batch-below\[location\]" reservation hierarchy in your deployment.</span></span> <span data-ttu-id="c4b43-143">Ta zmiana nie wpłynie na rezerwacje i otwarte prace magazynowe, które zostały utworzone przed zmianą.</span><span class="sxs-lookup"><span data-stu-id="c4b43-143">This change won't affect any reservations and open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="c4b43-144">Nie można jednak wyczyścić pola wyboru **Zezwalaj na rezerwację na zamówienie popytu**, jeśli dla jednego lub większej liczby towarów skojarzonych z tą hierarchią rezerwacji istnieją transakcje magazynowe typu **zamówione**, **zarezerwowane fizycznie** lub **zamówione**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-144">However, the **Allow reservation on demand order** check box can't be cleared if inventory transactions of the **Reserved ordered**, **Reserved physical**, or **Ordered** issue type exist for one or more items that are associated with that reservation hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="c4b43-145">Jeśli istniejąca hierarchia rezerwacji dla towaru nie zezwala na specyfikację partii w zamówieniu, można ją ponownie przypisać do hierarchii rezerwacji, która pozwala na określenie partii, pod warunkiem że struktura poziomu hierarchii jest taka sama w obu hierarchiach.</span><span class="sxs-lookup"><span data-stu-id="c4b43-145">If an item's existing reservation hierarchy doesn't allow batch specification on the order, you can reassign it to a reservation hierarchy that does allow batch specification, provided that the hierarchy level structure is the same in both hierarchies.</span></span> <span data-ttu-id="c4b43-146">Aby wykonać ponowne przypisanie, należy skorzystać z funkcji **Zmień rezerwację pozycji**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-146">Use the **Change reservation hierarchy for items** function to do the reassignment.</span></span> <span data-ttu-id="c4b43-147">Ta zmiana może być odpowiednia, jeśli chcesz zapobiec elastycznej rezerwacji wsadowej dla podzestawu pozycji śledzonych wsadowo, ale zezwól na to w pozostałej części teczki produktów.</span><span class="sxs-lookup"><span data-stu-id="c4b43-147">This change might be relevant when you want to prevent flexible batch reservation for a subset of batch-tracked items but allow it for the rest of the product portfolio.</span></span>

<span data-ttu-id="c4b43-148">Niezależnie od tego, czy zaznaczono pole wyboru **Zezwalaj na rezerwację na zamówieniu zapotrzebowania**, jeśli nie chcesz zarezerwować określonego numeru partii dla towaru w wierszu zamówienia, będzie nadal obowiązywała domyślna logika operacji magazynowych obowiązująca dla hierarchii rezerwacji "lokalizacja towaru \[poniżej\]”.</span><span class="sxs-lookup"><span data-stu-id="c4b43-148">Regardless of whether you've selected the **Allow reservation on demand order** check box, if you don't want to reserve a specific batch number for the item on an order line, default warehouse operations logic that is valid for a "Batch-below\[location\]" reservation hierarchy will still apply.</span></span>

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a><span data-ttu-id="c4b43-149">Rezerwacja określonego numeru partii dla zamówienia odbiorcy</span><span class="sxs-lookup"><span data-stu-id="c4b43-149">Reserve a specific batch number for a customer order</span></span>

<span data-ttu-id="c4b43-150">Po skonfigurowaniu śledzonej partii pozycji „Lokalizacja towaru\[ poniżej\]” w hierarchii rezerwacji zapasów można zezwolić na rezerwacje określonych numerów partii w zamówieniach sprzedaży, jednak przetwórcy zamówień sprzedaży mogą przyjmować zamówienia odbiorców dla tego samego towaru w jeden z następujących sposobów, w zależności od wniosku klienta:</span><span class="sxs-lookup"><span data-stu-id="c4b43-150">After a batch-tracked item's "Batch-below\[location\]" inventory reservation hierarchy is set up to allow reservation of specific batch numbers on sales orders, sales order processors can take customer orders for the same item in one of the following ways, depending on the customer's request:</span></span>

- <span data-ttu-id="c4b43-151">**Wprowadź szczegóły zamówienia bez określania numeru partii** — to podejście należy stosować w przypadku, gdy specyfikacja partii produktu nie jest ważna dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-151">**Enter order details without specifying a batch number** – This approach should be used when the product's batch specification isn't important to the customer.</span></span> <span data-ttu-id="c4b43-152">Wszystkie istniejące procesy skojarzone z obsługą zamówienia tego typu System pozostają niezmienione.</span><span class="sxs-lookup"><span data-stu-id="c4b43-152">All existing processes that are associated with handling an order of this type in the system remain unchanged.</span></span> <span data-ttu-id="c4b43-153">Część użytkowników nie wymaga żadnych dodatkowych okoliczności.</span><span class="sxs-lookup"><span data-stu-id="c4b43-153">No additional considerations are required on the part of users.</span></span>
- <span data-ttu-id="c4b43-154">**Wprowadź szczegóły zamówienia i Zarezerwuj określony numer partii** — tego podejścia należy użyć w przypadku, gdy odbiorca zażąda konkretnej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-154">**Enter order details and reserve a specific batch number** – This approach should be used when the customer requests a specific batch.</span></span> <span data-ttu-id="c4b43-155">Zazwyczaj odbiorcy zażądają konkretnej partii, gdy będą zamawiali produkty uprzednio nabyte.</span><span class="sxs-lookup"><span data-stu-id="c4b43-155">Typically, customers will request a specific batch when they are reordering a product that they previously purchased.</span></span> <span data-ttu-id="c4b43-156">Ten typ rezerwacji specyficznej dla danej partii jest określany mianem *rezerwacji do zamówienia*.</span><span class="sxs-lookup"><span data-stu-id="c4b43-156">This type of batch-specific reservation is referred to as *order-committed reservation*.</span></span>

<span data-ttu-id="c4b43-157">Następujący zbiór reguł jest ważny podczas przetwarzania ilości, a numer partii jest zatwierdzany w określonym zamówieniu:</span><span class="sxs-lookup"><span data-stu-id="c4b43-157">The following set of rules is valid when quantities are processed, and a batch number is committed to a specific order:</span></span>

- <span data-ttu-id="c4b43-158">Aby zezwolić na rezerwację określonego numeru partii towaru w zasadzie rezerwacji „Lokalizacja towaru \[poniżej\]”, system musi zarezerwować wszystkie wymiary w górę w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-158">To allow reservation of a specific batch number for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="c4b43-159">Ten zakres zazwyczaj zawiera wymiar numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="c4b43-159">This range typically includes the license plate dimension.</span></span>
- <span data-ttu-id="c4b43-160">Dyrektywy lokalizacji nie są używane, gdy jest tworzona praca pobrania dla wiersza sprzedaży, w którym jest używana rezerwacja partii zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c4b43-160">Location directives aren't used when picking work is created for a sales line that uses order-committed batch reservation.</span></span>
- <span data-ttu-id="c4b43-161">Podczas przetwarzania magazynu pracy dla partii zakontraktowanych na zamówienie ani użytkownik, ani systemow nie mogą zmieniać numeru partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-161">During warehouse processing of work for order-committed batches, neither the user nor the system is allowed to change the batch number.</span></span> <span data-ttu-id="c4b43-162">(Przetwarzanie obejmuje obsługę wyjątków)</span><span class="sxs-lookup"><span data-stu-id="c4b43-162">(This processing includes exception handling.)</span></span>

<span data-ttu-id="c4b43-163">W poniższym przykładzie pokazano przepływ typu end-to-end.</span><span class="sxs-lookup"><span data-stu-id="c4b43-163">The following example shows the end-to-end flow.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c4b43-164">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="c4b43-164">Example scenario</span></span>

<span data-ttu-id="c4b43-165">W tym przukładzie trzeba mieć zainstalowane dane demonstracyjne oraz musi być używana wersja demonstracyjna **USMF** danych firmy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-165">For this example, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><span data-ttu-id="c4b43-166">Skonfiguruj hierarchię rezerwacji zapasów w celu umożliwienia rezerwacji specyficznej dla partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-166">Set up an inventory reservation hierarchy to allow batch-specific reservation</span></span>

1. <span data-ttu-id="c4b43-167">Przejdź do **Ustawień magazynu** \> **Ustawień** \> **Zapasów \> Hierarchii rezerwacji**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-167">Go to **Warehouse management** \> **Setup** \> **Inventory \> Reservation hierarchy**.</span></span>
2. <span data-ttu-id="c4b43-168">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-168">Select **New**.</span></span>
3. <span data-ttu-id="c4b43-169">W polu **Nazwa** wprowadź nazwę (na przykład **BatchFlex**).</span><span class="sxs-lookup"><span data-stu-id="c4b43-169">In the **Name** field, enter a name (for example, **BatchFlex**).</span></span>
4. <span data-ttu-id="c4b43-170">W polu **Opis** wprowadź opis (np. **Lokalizacja towaru poniżej dynamicznie**).</span><span class="sxs-lookup"><span data-stu-id="c4b43-170">In the **Description** field, enter a description (for example, **Batch below flexible**).</span></span>
5. <span data-ttu-id="c4b43-171">W **Zaznaczonym** polu wybierz opcję **Numer seryjny** i **Właściciel**, a następnie wybierz przycisk strzałka w lewo, aby przenieść je do **Dostępnego** pola.</span><span class="sxs-lookup"><span data-stu-id="c4b43-171">In the **Selected** field, select **Serial number** and **Owner**, and then select the left arrow button to move them to the **Available** field.</span></span>
6. <span data-ttu-id="c4b43-172">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-172">Select **OK**.</span></span>
7. <span data-ttu-id="c4b43-173">W wierszu dla poziomu wymiaru **numer partii** zaznacz pole wyboru **Zezwalaj na rezerwację na zamówieniu popytu**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-173">In the row for the **Batch number** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="c4b43-174">**Numery identyfikacyjne** i **numery lokalizacji** są wybierane automatycznie i nie można wyczyścić tych pól wyboru.</span><span class="sxs-lookup"><span data-stu-id="c4b43-174">The **License plate** and **Location** levels are automatically selected, and you can't clear the check boxes for them.</span></span>
8. <span data-ttu-id="c4b43-175">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-175">Select **Save**.</span></span>

### <a name="create-a-new-released-product"></a><span data-ttu-id="c4b43-176">Tworzenie nowego zwolnionego produktu</span><span class="sxs-lookup"><span data-stu-id="c4b43-176">Create a new released product</span></span>

1. <span data-ttu-id="c4b43-177">Aby określić trzy parametry danych głównych produktu, należy użyć następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="c4b43-177">Set the product's three master data parameters by using these values:</span></span>

    - <span data-ttu-id="c4b43-178">W polu **Grupa wymiarów magazynowania** wybierz **Towar**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-178">In the **Storage dimension group** field, select **Ware**.</span></span>
    - <span data-ttu-id="c4b43-179">W polu **Grupę wymiarów śledzenia** wybierz **Batch-Phy**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-179">In the **Tracking dimension group** field, select **Batch-Phy**.</span></span>
    - <span data-ttu-id="c4b43-180">W polu **Rezerwacja hierarchi** zaznacz opcję **BatchFlex**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-180">In the **Reservation hierarchy** field, select **BatchFlex**.</span></span>

2. <span data-ttu-id="c4b43-181">Utwórz dwa numery partii, takie jak **B11** i **B22**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-181">Create two batch numbers, such as **B11** and **B22**.</span></span>
3. <span data-ttu-id="c4b43-182">Umożliwia dodawanie ilości towarów do dostępnych zapasów przy użyciu następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="c4b43-182">Add item quantities to on-hand stock by using the following values.</span></span>

    | <span data-ttu-id="c4b43-183">Magazyn</span><span class="sxs-lookup"><span data-stu-id="c4b43-183">Warehouse</span></span> | <span data-ttu-id="c4b43-184">Numer partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-184">Batch number</span></span> | <span data-ttu-id="c4b43-185">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="c4b43-185">Location</span></span> | <span data-ttu-id="c4b43-186">Numer identyfikacyjny</span><span class="sxs-lookup"><span data-stu-id="c4b43-186">License plate</span></span> | <span data-ttu-id="c4b43-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="c4b43-187">Quantity</span></span> |
    |-----------|--------------|----------|---------------|----------|
    | <span data-ttu-id="c4b43-188">24</span><span class="sxs-lookup"><span data-stu-id="c4b43-188">24</span></span>        | <span data-ttu-id="c4b43-189">B11</span><span class="sxs-lookup"><span data-stu-id="c4b43-189">B11</span></span>          | <span data-ttu-id="c4b43-190">BULK-001</span><span class="sxs-lookup"><span data-stu-id="c4b43-190">BULK-001</span></span> | <span data-ttu-id="c4b43-191">Brak</span><span class="sxs-lookup"><span data-stu-id="c4b43-191">None</span></span>          | <span data-ttu-id="c4b43-192">10</span><span class="sxs-lookup"><span data-stu-id="c4b43-192">10</span></span>       |
    | <span data-ttu-id="c4b43-193">24</span><span class="sxs-lookup"><span data-stu-id="c4b43-193">24</span></span>        | <span data-ttu-id="c4b43-194">B11</span><span class="sxs-lookup"><span data-stu-id="c4b43-194">B11</span></span>          | <span data-ttu-id="c4b43-195">FL-001</span><span class="sxs-lookup"><span data-stu-id="c4b43-195">FL-001</span></span>   | <span data-ttu-id="c4b43-196">LP11</span><span class="sxs-lookup"><span data-stu-id="c4b43-196">LP11</span></span>          | <span data-ttu-id="c4b43-197">10</span><span class="sxs-lookup"><span data-stu-id="c4b43-197">10</span></span>       |
    | <span data-ttu-id="c4b43-198">24</span><span class="sxs-lookup"><span data-stu-id="c4b43-198">24</span></span>        | <span data-ttu-id="c4b43-199">B22</span><span class="sxs-lookup"><span data-stu-id="c4b43-199">B22</span></span>          | <span data-ttu-id="c4b43-200">FL-002</span><span class="sxs-lookup"><span data-stu-id="c4b43-200">FL-002</span></span>   | <span data-ttu-id="c4b43-201">LP22</span><span class="sxs-lookup"><span data-stu-id="c4b43-201">LP22</span></span>          | <span data-ttu-id="c4b43-202">10</span><span class="sxs-lookup"><span data-stu-id="c4b43-202">10</span></span>       |

### <a name="enter-sales-order-details"></a><span data-ttu-id="c4b43-203">Podawanie szczegółów zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c4b43-203">Enter sales order details</span></span>

1. <span data-ttu-id="c4b43-204">Przejdź kolejno do pozycji **Sprzedaż i marketing** \> **Zamówienia sprzedaży** \> **Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-204">Go to **Sales and marketing** \> **Sales orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="c4b43-205">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-205">Select **New**.</span></span>
3. <span data-ttu-id="c4b43-206">W nagłówku zamówienia sprzedaży w sekcji **Konto odbiorcy** wprowadź **US-003**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-206">On the sales order header, in the **Customer account** field, enter **US-003**.</span></span>
4. <span data-ttu-id="c4b43-207">Dodaj wiersz dla nowego produktu i wprowadź **10** jako ilość.</span><span class="sxs-lookup"><span data-stu-id="c4b43-207">Add a line for the new item, and enter **10** as the quantity.</span></span> <span data-ttu-id="c4b43-208">Upewnij się, że pole **Magazyn** zawiera wartość **24**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-208">Make sure that the **Warehouse** field is set to **24**.</span></span>
5. <span data-ttu-id="c4b43-209">W skróconej karcie **Wiersz zamówienia sprzedaży** wybierz pozycję **Zapasy**, a następnie w grupie **Obsługa** wybierz opcję **Rezerwacja partii**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-209">On the **Sales order lines** FastTab, select **Inventory**, and then, in the **Maintain** group, select **Batch reservation**.</span></span> <span data-ttu-id="c4b43-210">Na stronie **Rezerwacja partii** jest wyświetlana lista partii dostępnych do rezerwacji dla wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c4b43-210">The **Batch reservation** page shows a list of batches that are available for reservation for the order line.</span></span> <span data-ttu-id="c4b43-211">W tym przykładzie przedstawiono ilość **20** dla numeru partii **B11** i ilość **10** dla numeru partii **B22**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-211">For this example, it shows a quantity of **20** for batch number **B11** and a quantity of **10** for batch number **B22**.</span></span> <span data-ttu-id="c4b43-212">Należy pamiętać, że nie można uzyskać dostępu do strony **rezerwacja partii** z wiersza, jeśli towar w tym wierszu jest skojarzony z hierarchią rezerwacji "Lokalizacja towaru\[poniżej\], chyba że jest skonfigurowany tak, aby zezwalać na rezerwacje specyficzne dla danej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-212">Note that the **Batch reservation** page cannot be accessed from a line if the item on that line is associated with "Batch-below\[location\]" reservation hierarchy unless it is set up to allow batch-specific reservation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4b43-213">Aby zarezerwować określoną partię dla zamówienia sprzedaży, należy skorzystać ze strony **Rezerwacja partii**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-213">To reserve a specific batch for a sales order, you must use the **Batch reservation** page.</span></span>
    >
    > <span data-ttu-id="c4b43-214">Jeśli numer partii zostanie wprowadzony bezpośrednio w wierszu zamówienia sprzedaży, system zatrzyma się, tak jakby wprowadzono określoną wartość partii towaru, która podlega zasadom rezerwacji „Lokalizacja towaru\[poniżej\]”.</span><span class="sxs-lookup"><span data-stu-id="c4b43-214">If you enter the batch number directly on the sales order line, the system will behave as though you entered a specific batch value for an item that is subject to the "Batch-below\[location\]" reservation policy.</span></span> <span data-ttu-id="c4b43-215">Po zapisaniu wiersza pojawi się komunikat ostrzegawczy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-215">When you save the line, you will receive a warning message.</span></span> <span data-ttu-id="c4b43-216">Jeśli użytkownik potwierdzi, że numer partii ma być określony bezpośrednio w wierszu zamówienia, wiersz nie będzie obsługiwany przez zwykłą logikę zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="c4b43-216">If you confirm that the batch number should be specified directly on the order line, the line won't be handled by the regular warehouse management logic.</span></span>
    >
    > <span data-ttu-id="c4b43-217">Jeśli zarezerwujesz ilość na stronie **Rezerwacja**, nie zostanie zarezerwowana żadna określona partia, a wykonywanie operacji magazynowych dla wiersza będzie odbywać się zgodnie z regułami dotyczącymi rezerwacji w obszarze „Lokalizacja towaru\[poniżej\]”.</span><span class="sxs-lookup"><span data-stu-id="c4b43-217">If you reserve the quantity from the **Reservation** page, no specific batch will be reserved, and the execution of warehouse operations for the line will follow the rules that are applicable under the "Batch-below\[location\]" reservation policy.</span></span>

    <span data-ttu-id="c4b43-218">Na ogół ta strona działa i jest współdziałana w taki sam sposób, w jaki działa i jest aktywnie związana z elementami, które mają skojarzoną hierarchię rezerwacji dla typu „Lokalizacja towaru\[powyżej\]”.</span><span class="sxs-lookup"><span data-stu-id="c4b43-218">In general, this page works and is interacted with in the same way that it works and is interacted with for items that have an associated reservation hierarchy of the "Batch-above\[location\]" type.</span></span> <span data-ttu-id="c4b43-219">Obowiązują jednak następujące wyjątki:</span><span class="sxs-lookup"><span data-stu-id="c4b43-219">However, the following exceptions apply:</span></span>

    - <span data-ttu-id="c4b43-220">Numery **Partii przekazane do wiersza źródłowego** skróconej karcie są wyświetlane zgodnie z numerami partii, które są zarezerwowane dla danego wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c4b43-220">The **Batch numbers committed to source line** FastTab shows the batch numbers that are reserved for the order line.</span></span> <span data-ttu-id="c4b43-221">Wartości partii w siatce będą wyświetlane w cyklu realizacji wiersza zamówienia, w tym w etapach przetwarzania magazynu.</span><span class="sxs-lookup"><span data-stu-id="c4b43-221">The batch values in the grid will be shown throughout the fulfilment cycle of the order line, including the warehouse processing stages.</span></span> <span data-ttu-id="c4b43-222">Z drugiej strony, na **Przeglądowej** karcie skróconej, zwykła rezerwacja wiersza zamówienia (czyli rezerwacja wykonana dla wymiarów powyżej poziomu **Lokalizacji**) jest wyświetlana w siatce w górę do momentu utworzenia pracy magazynowej.</span><span class="sxs-lookup"><span data-stu-id="c4b43-222">By contrast, on the **Overview** FastTab, regular order line reservation (that is, reservation that is done for the dimensions above the **Location** level) is shown in the grid up to the point when warehouse work is created.</span></span> <span data-ttu-id="c4b43-223">Jednostka pracy przejmuje wówczas rezerwację wiersza, a rezerwacja wiersza nie jest już wyświetlana na stronie.</span><span class="sxs-lookup"><span data-stu-id="c4b43-223">The work entity then takes over the line reservation, and the line reservation no longer appears on the page.</span></span> <span data-ttu-id="c4b43-224">**Numery partii przekazane do wiersza źródłowego** na skróconej karcie ułatwiają zagwarantowanie, że moduł przetwarzający zamówienia sprzedaży może wyświetlić numery partii, które zostały przekazane do zamówienia odbiorcy w dowolnym momencie, w trakcie fakturowania.</span><span class="sxs-lookup"><span data-stu-id="c4b43-224">The **Batch numbers committed to source line** FastTab helps guarantee that the sales order processor can view the batch numbers that were committed to the customer's order at any point during its lifecycle, up through invoicing.</span></span>
    - <span data-ttu-id="c4b43-225">Oprócz rezerwowania konkretnej partii użytkownik może ręcznie wybrać lokalizację i numer identyfikacyjny danej partii, zamiast zezwalać na automatyczne wybieranie numeru identyfikacyjnego danej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-225">In addition to reserving a specific batch, a user can manually select the batch's specific location and license plate instead of letting the system automatically select them.</span></span> <span data-ttu-id="c4b43-226">Ta możliwość jest związana z projektem mechanizmu rezerwacji partii zakontraktowanego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c4b43-226">This capability is related to the design of the order-committed batch reservation mechanism.</span></span> <span data-ttu-id="c4b43-227">Tak jak wspomniano wcześniej, aby zezwolić na rezerwację określonego numeru partii towaru w zasadzie rezerwacji „Lokalizacja towaru\[poniżej\]”, system musi zarezerwować wszystkie wymiary w górę w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-227">As was mentioned earlier, when a batch number is reserved for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="c4b43-228">Z tego względu prace magazynowe będą miały te same wymiary magazynowe, które zostały zarezerwowane przez użytkowników pracujących z tymi zamówieniami i nie zawsze będą reprezentować położenie magazynu towarów, które jest wygodne, a nawet możliwe dla operacji pobierania.</span><span class="sxs-lookup"><span data-stu-id="c4b43-228">Therefore, warehouse work will carry the same storage dimensions that were reserved by the users who worked with the orders, and it might not always represent the item storage placement that is convenient, or even possible, for picking operations.</span></span> <span data-ttu-id="c4b43-229">Jeśli przetwórcy zamówień są świadomi ograniczeń magazynowych, może zaistnieć potrzeba ręcznego wybrania konkretnych lokalizacji i numerów identyfikacyjnych podczas rezerwowania partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-229">If order processors are aware of the warehouse constraints, they might want to manually select the specific locations and license plates when they reserve a batch.</span></span> <span data-ttu-id="c4b43-230">W takim przypadku użytkownik musi skorzystać z funkcji **wymiarów wyświetlanych** w nagłówku strony i musi dodać lokalizację i numer identyfikacyjny w siatce w skróconej karcie **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-230">In this case, the user must use the **Display dimensions** functionality on the page header, and must add the location and license plate in the grid on the **Overview** FastTab.</span></span>

6. <span data-ttu-id="c4b43-231">Na stronie **rezerwacja partii** wybierz wiersz dla **B11**wsadowego, a następnie wybierz opcję **wiersz rezerwy**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-231">On the **Batch reservation** page, select the line for batch **B11**, and then select **Reserve line**.</span></span> <span data-ttu-id="c4b43-232">Podczas automatycznej rezerwacji nie ma żadnej wskazanej logiki do przypisywania lokalizacji i numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="c4b43-232">There is no designated logic for assigning locations and license plates during automatic reservation.</span></span> <span data-ttu-id="c4b43-233">Ilość można wprowadzić ręcznie w polu **rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-233">You can manually enter the quantity in the **Reservation** field.</span></span> <span data-ttu-id="c4b43-234">Zwróć uwagę, że w przypadku skróconej karty **numerów partii przekazanych do wiersza źródłowego**, zestaw **B11** jest wyświetlany jako **Zatwierdzony**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-234">Notice that, on the **Batch numbers committed to source line** FastTab, batch **B11** is shown as **Committed**.</span></span>

    ![Zatwierdzanie określonego numeru partii do wiersza zamówienia sprzedaży na stronie rezerwacja partii](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > <span data-ttu-id="c4b43-236">Rezerwacja ilości w wierszu zamówienia sprzedaży może zostać wykonana na wielu partiach.</span><span class="sxs-lookup"><span data-stu-id="c4b43-236">Reservation of the quantity on a sales order line can be done across multiple batches.</span></span> <span data-ttu-id="c4b43-237">Ponadto rezerwacja tej samej partii może zostać wykonana dla wielu lokalizacji i numerów identyfikacyjnych (jeśli są włączone płytki rejestracyjne dla lokalizacji).</span><span class="sxs-lookup"><span data-stu-id="c4b43-237">Likewise, reservation of the same batch can be done against multiple locations and license plates (if license plates are enabled for the locations).</span></span>
    >
    > <span data-ttu-id="c4b43-238">Rezerwacja konkretnej partii dla ilości w wierszu zamówienia sprzedaży może być także częściowa.</span><span class="sxs-lookup"><span data-stu-id="c4b43-238">Reservation of a specific batch for the quantity on a sales order line can also be partial.</span></span> <span data-ttu-id="c4b43-239">Na przykład całkowita ilość 100 jednostek może zostać zarezerwowana, aby określona partia była przydzielona do 20 jednostek, natomiast jednostki 80 są rezerwowane na poziomie oddziału i magazynu dla dowolnej dostępnej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-239">For example, the total quantity of 100 units can be reserved so that a specific batch is committed to 20 units, whereas 80 units are reserved at the site and warehouse levels for any available batch.</span></span> <span data-ttu-id="c4b43-240">W tym przypadku moduł WMS będzie obsługiwał operacje pobierania za pomocą dwóch oddzielnych wierszy pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-240">In this case, the WMS will handle picking operations by using two separate work lines.</span></span>

7. <span data-ttu-id="c4b43-241">Przejdź do **Zarządzanie informacjami o produktach** \> **Produkty** \> **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-241">Go to **Product information management** \> **Products** \> **Released products**.</span></span> <span data-ttu-id="c4b43-242">Wybierz towar, a następnie wybierz pozycję **Zarządzaj zapasami** \> **Widok** \> **Transakcje**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-242">Select your item, and then select **Manage inventory** \> **View** \> **Transactions**.</span></span>

    ![Rezerwacja zamówiona jako typ transakcji magazynowej](media/Inventory-transactions-for-order-committed-reservation.png)

8. <span data-ttu-id="c4b43-244">Umożliwia przejrzenie transakcji magazynowych dotyczących danego towaru, które są powiązane z rezerwacją wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c4b43-244">Review the item's inventory transactions that are related to the sales order line reservation.</span></span>

    - <span data-ttu-id="c4b43-245">Transakcja, w której pole **Odwołania** jest ustawione na **Zamówienie** sprzedaży, a **Rozchód** ma wartość **Fizycznie zarezerwowane**, oznacza rezerwę wiersza zamówienia dla wymiarów magazynowych powyżej poziomu **lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-245">A transaction where the **Reference** field is set to **Sales order** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the inventory dimensions above the **Location** level.</span></span> <span data-ttu-id="c4b43-246">Zgodnie z hierarchią rezerwacji zapasów danego towaru, wymiary te to oddział, magazyn i stan zapasów.</span><span class="sxs-lookup"><span data-stu-id="c4b43-246">According to the item's inventory reservation hierarchy, those dimensions are site, warehouse, and inventory status.</span></span>
    - <span data-ttu-id="c4b43-247">Transakcja, w której pole **Odwołania** jest ustawione na **Rezerwacja-zamówienie sprzedaży**, a pole **Wydanie** ma wartość **Fizycznie zarezerwowane**, oznacza rezerwę wiersza zamówienia dla danej partii towaru i wszystkich zapasów ponad nią.</span><span class="sxs-lookup"><span data-stu-id="c4b43-247">A transaction where the **Reference** field is set to **Order-committed reservation** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the specific batch and all inventory dimensions above it.</span></span> <span data-ttu-id="c4b43-248">Zgodnie z hierarchią rezerwacji zapasów danego towaru, wymiary te to numer partii oraz lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="c4b43-248">According to the item's inventory reservation hierarchy, those dimensions are batch number and location.</span></span> <span data-ttu-id="c4b43-249">W tym przykładzie lokalizacja to **Bulk-001**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-249">In this example, the location is **Bulk-001**.</span></span>

9. <span data-ttu-id="c4b43-250">W nagłówku zamówienia wybierz **Magazyn** \> **Działania** \> **Zwolnij do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-250">On the sales order header, select **Warehouse** \> **Actions** \> **Release to warehouse**.</span></span> <span data-ttu-id="c4b43-251">Wiersz zamówienia jest teraz waved i jest tworzony ładunek i praca.</span><span class="sxs-lookup"><span data-stu-id="c4b43-251">The order line is now waved, and a load and work are created.</span></span>

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="c4b43-252">Służy do przeglądania i przetwarzania pracy magazynowej z numerami partii zatwierdzonych dla zamówienia</span><span class="sxs-lookup"><span data-stu-id="c4b43-252">Review and process warehouse work that has order-committed batch numbers</span></span>

1. <span data-ttu-id="c4b43-253">W skróconej karcie **Kolejność zamówień sprzedaży**, wybierz opcję **Magazyn** \> **Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-253">On the **Sales order lines** FastTab, select **Warehouse** \> **Work details**.</span></span>

    <span data-ttu-id="c4b43-254">Praca, która obsługuje operację pobrania dla ilości partii, która jest potwierdzona w wierszu zamówienia sprzedaży, ma następujące cechy:</span><span class="sxs-lookup"><span data-stu-id="c4b43-254">The work that handles the picking operation for batch quantities that are committed to the sales order line has the following characteristics:</span></span>

    - <span data-ttu-id="c4b43-255">Aby utworzyć pracę, system używa szablonów roboczych, ale nie zawiera dyrektyw lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-255">To create work, the system uses work templates but not location directives.</span></span> <span data-ttu-id="c4b43-256">Wszystkie standardowe ustawienia zdefiniowane dla szablonów pracy, takie jak Maksymalna liczba wierszy pobrania lub określony jednostka miary, zostaną zastosowane w celu ustalenia, kiedy należy utworzyć nową pracę.</span><span class="sxs-lookup"><span data-stu-id="c4b43-256">All the standard settings that are defined for work templates, such as a maximum number of pick lines or a specific unit of measure, will be applied to determine when new work should be created.</span></span> <span data-ttu-id="c4b43-257">Jednak reguły skojarzone z dyrektywami lokalizacji do identyfikowania lokalizacji pobrania nie są uwzględniane, ponieważ rezerwacja rezerwacji zamówień już określa wszystkie wymiary magazynowe.</span><span class="sxs-lookup"><span data-stu-id="c4b43-257">However, the rules that are associated with location directives for identifying pick locations aren't considered, because the order-committed reservation already specifies all the inventory dimensions.</span></span> <span data-ttu-id="c4b43-258">Te wymiary magazynowe obejmują wymiary na poziomie składowania w magazynie.</span><span class="sxs-lookup"><span data-stu-id="c4b43-258">Those inventory dimensions include the dimensions at the warehouse storage level.</span></span> <span data-ttu-id="c4b43-259">Dlatego praca dziedziczy te wymiary bez konieczności konsultowania dyrektyw lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-259">Therefore, the work inherits those dimensions without having to consult location directives.</span></span>
    - <span data-ttu-id="c4b43-260">Numer partii nie jest wyświetlany w wierszu pobrania (podobnie jak w przypadku wiersza pracy utworzonego dla towaru, który ma skojarzoną hierarchię rezerwacji z lokalizacji\[powyżej\]) zamiast tego numer partii „od” i wszystkie inne wymiary magazynowe są wyświetlane w transakcji magazynowej dla wiersza pracy, do której odwołuje się skojarzone transakcje magazynowe.</span><span class="sxs-lookup"><span data-stu-id="c4b43-260">The batch number isn't shown on the pick line (as is the case for the work line that is created for an item that has an associated "Batch-above\[location\]" reservation hierarchy.) Instead, the "from" batch number and all other storage dimensions are shown on the work line's work inventory transaction that is referenced from the associated inventory transactions.</span></span>

        ![Transakcja magazynowa magazynu dla pracy, która pochodzi z rezerwacji zamówienia](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - <span data-ttu-id="c4b43-262">Po utworzeniu pracy zostanie usunięta transakcja magazynowa towaru, w której pole **odwołania** ma ustawioną rezerwację **Rezerwacja-zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-262">After work is created, the item's inventory transaction where the **Reference** field is set to **Order-committed reservation** is removed.</span></span> <span data-ttu-id="c4b43-263">Transakcja magazynowa, w której pole **odwołania** ma wartość **praca**, zawiera rezerwę fizyczną dla wszystkich wymiarów magazynowych z ilością.</span><span class="sxs-lookup"><span data-stu-id="c4b43-263">The inventory transaction where the **Reference** field is set to **Work** now holds the physical reservation on all the quantity's inventory dimensions.</span></span>

        <span data-ttu-id="c4b43-264">Operacje magazynowe mogą być kontynuowane w celu obsługi wykonania pracy w zwykły sposób.</span><span class="sxs-lookup"><span data-stu-id="c4b43-264">Warehouse operations can proceed to handle execution of the work in the usual manner.</span></span> <span data-ttu-id="c4b43-265">Jednak instrukcje na urządzeniu przenośnym wykazują pracownikowi pobranie określonego numeru partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-265">However, the instructions on the mobile device will instruct the worker to pick a specific batch number.</span></span> <span data-ttu-id="c4b43-266">W środowiskach magazynowych, w których lokalizacje są oznaczone numerami identyfikacyjnymi, gdy pracownik osiągnie lokalizację, w której jest przechowywana taka sama partia na wielu płytach, może pobrać z dowolnego numeru identyfikacyjnego, który nie został jeszcze zarezerwowany (np. inny zadeklarowana rezerwacja zamówienia lub praca pochodząca z rezerwacji tego typu).</span><span class="sxs-lookup"><span data-stu-id="c4b43-266">In warehouse environments where locations are license plate–controlled, after a worker reaches a location that stores the same batch on multiple license plates, he or she can pick from any license plate that isn't already reserved (for example, by another order-committed reservation or work that originates from a reservation of that type.)</span></span>

        <span data-ttu-id="c4b43-267">Jeśli okaże się, że nie będzie on praktyczny do pobrania z lokalizacji określonej w wierszu pracy, operatorzy magazynu mogą używać jednej z następujących akcji do przekierowywania pobierania określonej partii z bardziej wygodnej lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="c4b43-267">If it turns out to be impractical to pick from the location that is specified on the work line, the warehouse operators can use one of the following actions to redirect picking of the specific batch from a more convenient location:</span></span>

        - <span data-ttu-id="c4b43-268">Standardowa akcja **zastępowania lokalizacji** na urządzeniu przenośnym (pod warunkiem, że włączone jest ustawienie **Zezwalaj na zastępowanie lokalizacji pobrania**)</span><span class="sxs-lookup"><span data-stu-id="c4b43-268">The standard **Override location** action on a mobile device (provided that the warehouse worker's **Allow pick location override** setting is enabled)</span></span>
        - <span data-ttu-id="c4b43-269">Akcja **zmiany lokalizacji** na stronie **Szczegóły listy prac**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-269">The **Change location** action on the **Work list details** page.</span></span> 

2. <span data-ttu-id="c4b43-270">Na urządzeniu przenośnym Zakończ pobieranie i odkładanie pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-270">On the mobile device, finish picking and putting the work.</span></span>

    <span data-ttu-id="c4b43-271">Ilość **10** dla numeru partii **B11** jest teraz pobierana dla wiersza zamówienia sprzedaży i umieszczona w lokalizacji **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-271">The quantity of **10** for batch number **B11** is now picked for the sales order line and put in the **Baydoor** location.</span></span> <span data-ttu-id="c4b43-272">W tym momencie jest gotowy do załadunku na samochód i wysyłany do adresu odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-272">At this point, it's ready to be loaded onto the truck and dispatched to the customer's address.</span></span>

## <a name="exception-handling-of-warehouse-work-thas-has-order-committed-batch-numbers"></a><span data-ttu-id="c4b43-273">Zarządzanie wyjątkami pracy magazynowej z numerami partii zatwierdzonych dla zamówienia</span><span class="sxs-lookup"><span data-stu-id="c4b43-273">Exception handling of warehouse work thas has order-committed batch numbers</span></span>

<span data-ttu-id="c4b43-274">Praca w magazynie dla zamówienia pobrania — numery partii zatwierdzonej podlegają tej samej standardowej obsłudze wyjątków magazynowych oraz działaniu zwykłej pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-274">Warehouse work for picking order-committed batch numbers is subject to the same standard warehouse exception handling and actions as regular work.</span></span> <span data-ttu-id="c4b43-275">Na ogół można anulować otwartą pracę lub wiersz pracy, ponieważ jest zapełniony, ponieważ lokalizacja użytkownika jest zapełniona, może być ona pobrana i można ją zaktualizować z powodu przesunięcia.</span><span class="sxs-lookup"><span data-stu-id="c4b43-275">In general, the open work or work line can be canceled, it can be interrupted because a user location is full, it can be short-picked, and it can be updated because of a movement.</span></span> <span data-ttu-id="c4b43-276">Podobnie pobrana ilość pracy, która została już zakończona, może zostać zmniejszona lub praca może zostać wycofana.</span><span class="sxs-lookup"><span data-stu-id="c4b43-276">Likewise, the picked quantity of work that has already been completed can be reduced, or the work can be reversed.</span></span>

<span data-ttu-id="c4b43-277">Do wszystkich tych akcji obsługi wyjątków jest stosowana następująca reguła klucza: numer partii zarezerwowany dla odbiorcy nie może zostać zastąpiony innym numerem partii, ale jego wymiary przechowywania (lokalizacja i numer identyfikacyjny) można zmienić za pomocą opcji Ręczna aktualizacja użytkownika lub automatyczna aktualizacja systemu przez system.</span><span class="sxs-lookup"><span data-stu-id="c4b43-277">The following key rule is applied to all these exception handling actions: the batch number that was reserved for the customer can never be replaced with a different batch number, but its storage dimensions (location and license plate) can be changed through either a manual update by the user or an automatic update by the system.</span></span> <span data-ttu-id="c4b43-278">Automatyczna aktualizacja jest oparta na tym samym przypisaniu losowym wymiarów magazynowych, które mają zastosowanie w przypadku, gdy określona partia została zarezerwowana automatycznie, ale nie określono wymiarów magazynowania.</span><span class="sxs-lookup"><span data-stu-id="c4b43-278">The automatic update is based on the same random assignment of storage dimensions that applied when a specific batch was automatically reserved but no storage dimensions were specified.</span></span>

### <a name="example-scenario"></a><span data-ttu-id="c4b43-279">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="c4b43-279">Example scenario</span></span>

<span data-ttu-id="c4b43-280">Przykładem tego scenariusza jest sytuacja, w której uprzednio ukończona praca jest wycofywana za pomocą funkcji **Zmniejsz ilość pobranych ilości**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-280">An example of this scenario is a situation where previously completed work is being unpicked by using the **Reduce picked quantity** function.</span></span> <span data-ttu-id="c4b43-281">W tym przykładzie jest kontynuowany poprzedni przykład w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="c4b43-281">This example continues the previous example in this topic.</span></span>

1. <span data-ttu-id="c4b43-282">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ładunki** \> **Aktywne ładunki**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-282">Go to **Warehouse management** \> **Loads** \> **Active loads**.</span></span>
2. <span data-ttu-id="c4b43-283">Umożliwia wybór ładunku utworzonego w związku z wysyłką zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c4b43-283">Select the load that was created in connection with the shipment of your sales order.</span></span>
3. <span data-ttu-id="c4b43-284">W skróconej karcie **wierszy zamówienia ładunku** wybierz opcję **Zmniejsz ilość pobraną**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-284">From the **Load order lines** FastTab, select **Reduce picked quantity**.</span></span>
4. <span data-ttu-id="c4b43-285">Na stronie **Zmniejsz ilość pobranych towarów** w polu **Przenieś do lokalizacji** zaznacz opcję **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-285">On the **Reduce picked quantity** page, in the **Move to location** field, select **FL-001**.</span></span>
5. <span data-ttu-id="c4b43-286">W polu **Przenieś do numeru identyfikacyjnego** zaznacz opcję **LP33**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-286">In the **Move to license plate** field, select **LP33**.</span></span>
6. <span data-ttu-id="c4b43-287">W polu **ilość zapasów do cofnięcia pobrania**, wprowadź wartość **10**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-287">In the grid, in the **Inventory quantity to unpick** field, enter **10**.</span></span>
7. <span data-ttu-id="c4b43-288">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-288">Select **OK**.</span></span>

<span data-ttu-id="c4b43-289">Poniżej przedstawiono wyniki cofnięcia pobrania:</span><span class="sxs-lookup"><span data-stu-id="c4b43-289">Here are the results of the unpicking action:</span></span>

- <span data-ttu-id="c4b43-290">Stan poprzednio zamkniętej pracy jest ustawiany jako **anulowany**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-290">The status of the previously closed work is set to **Canceled**.</span></span>
- <span data-ttu-id="c4b43-291">Nowa praca typu **przesunięcie zapasów** jest tworzona dla niepobranej ilości **10** dla numeru **partii B11**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-291">New work of the **Inventory movement** type is created for the unpicked quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="c4b43-292">Ta praca reprezentuje przesunięcie z lokalizacji **Baydoor** do numeru identyfikacyjnego **LP33** w lokalizacji **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-292">This work represents the movement from the **Baydoor** location to license plate **LP33** in location **FL-001**.</span></span> <span data-ttu-id="c4b43-293">Stan zostanie ustawiony na **Zamknięty**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-293">The status is set to **Closed**.</span></span>
- <span data-ttu-id="c4b43-294">System ponownie rezerwuje numer partii, który został pierwotnie zamówiony, a następnie przypisuje lokalizację i identyfikatory numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="c4b43-294">The system re-reserves the batch number that was originally ordered, and assigns the location and license plate IDs.</span></span> <span data-ttu-id="c4b43-295">(Ten proces jest równoznaczny z uruchomieniem funkcji **wiersza rezerwy** dla wiersza zamówienia dla danego numeru partii).</span><span class="sxs-lookup"><span data-stu-id="c4b43-295">(This process is equivalent to running the **Reserve line** function for the order line for a given batch number).</span></span> <span data-ttu-id="c4b43-296">W wyniku tego partia **B11** jest pokazana jako zatwierdzona na skróconej karcie **numery partii przekazanych do wiersza źródłowego**, na stronie **rezerwacja partii**, a pole **rezerwacja** zawiera ilość **10** dla numeru partii **B11**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-296">As a result, batch **B11** is shown as committed on the **Batch numbers committed to source line** FastTab of the **Batch reservation** page, and the **Reservation** field contains a quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="c4b43-297">Ponadto pole **lokalizacji** jest ustawione na **FL-001**, a pole **numeru identyfikacyjnego** jest ustawione na **LP11**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-297">Additionally, the **Location** field is set to **FL-001**, and the **License plate** field is set to **LP11**.</span></span> <span data-ttu-id="c4b43-298">(Jeśli te pola są niewidoczne, można je dodać do siatki)</span><span class="sxs-lookup"><span data-stu-id="c4b43-298">(You can add these fields to the grid if they aren't visible.)</span></span>

<span data-ttu-id="c4b43-299">Poniższe tabele zawierają przegląd, w jaki sposób system obsługuje zarezerwowaną rezerwację partii dla konkretnych akcji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="c4b43-299">The following tables provide an overview that shows how the system handles order-committed batch reservation for specific warehouse actions.</span></span> <span data-ttu-id="c4b43-300">Aby interpretować zawartość w tabelach, należy zastanowić się, że każda akcja magazynowa jest uruchamiana w kontekście istniejącej pracy magazynowej, która pochodzi z rezerwacji partii zamówienia, lub że wykonanie każdej akcji magazynowej ma wpływ na pracę tego typu.</span><span class="sxs-lookup"><span data-stu-id="c4b43-300">To interpret the content in the tables, assume that each warehouse action is run in the context of existing warehouse work that originates from an order-committed batch reservation, or that execution of each warehouse action affects work of that type.</span></span>

> [!NOTE]
> <span data-ttu-id="c4b43-301">W tych tabelach kolumna „ilość partii jest dostępna” wskazuje, czy ilość partii jest dostępna oprócz ilości, która jest już zarezerwowana dla bieżącego zamówienia — zatwierdzone rezerwacje lub już zarezerwowana przez pracę magazynową, która pochodzi z rezerwacji tego typu.</span><span class="sxs-lookup"><span data-stu-id="c4b43-301">In these tables, the "Batch quantity is available" column indicates whether a batch quantity is available in addition to the quantity that is either already reserved for the current order-committed reservations or already reserved by the warehouse work that originates from reservations of that type.</span></span>

#### <a name="override-the-pick-location-on-the-open-work"></a><span data-ttu-id="c4b43-302">Zastąpienie lokalizacji odbioru w otwartej pracy</span><span class="sxs-lookup"><span data-stu-id="c4b43-302">Override the pick location on the open work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c4b43-303">Parametry ustawień klucza</span><span class="sxs-lookup"><span data-stu-id="c4b43-303">Key setup parameter</span></span></th>
<th><span data-ttu-id="c4b43-304">Ilość partii jest dostępna</span><span class="sxs-lookup"><span data-stu-id="c4b43-304">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c4b43-305">Najważniejsze kroki użytkownika</span><span class="sxs-lookup"><span data-stu-id="c4b43-305">Key user steps</span></span></th>
<th><span data-ttu-id="c4b43-306">Praca magazynu</span><span class="sxs-lookup"><span data-stu-id="c4b43-306">Warehouse work</span></span></th>
<th><span data-ttu-id="c4b43-307">Rezerwacja-zamówienie sprzedaży partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-307">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c4b43-308">Opcja <strong>Zezwalaj na zastępowanie lokalizacji pobrania</strong> jest włączona dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="c4b43-308">The <strong>Allow pick location override</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c4b43-309">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-309">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-310">Umożliwia wybranie opcji <strong>Zastąp element menu lokalizacji</strong> w magazynie Mmobile App (WMA) po rozpoczęciu pracy pobrania.</span><span class="sxs-lookup"><span data-stu-id="c4b43-310">Select the <strong>Override location</strong> menu item on the Warehouse Mmobile App (WMA) when you start picking work.</span></span></li>
<li><span data-ttu-id="c4b43-311">Wybierz opcję <strong>Sugeruj</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-311">Select <strong>Suggest</strong>.</span></span></li>
<li><span data-ttu-id="c4b43-312">Potwierdź nową lokalizację sugerowaną na podstawie dostępności ilości partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-312">Confirm the new location that is suggested based on batch quantity availability.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c4b43-313">W bieżącej pracy wykonywane są następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="c4b43-313">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="c4b43-314">Lokalizacja w wierszu pobrania zostanie zaktualizowana do nowej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-314">The location on the pick line is updated to the new location.</span></span> <span data-ttu-id="c4b43-315">(Jeśli lokalizacja jest kontrolowana numerami identyfikacyjnymi, to losowy numer identyfikacyjny jest przypisany do transakcji magazynowej pracy, a pracownik może pobrać z dowolnego numeru identyfikacyjnego, który ma dostępną ilość.)</span><span class="sxs-lookup"><span data-stu-id="c4b43-315">(If the location is license plate–controlled, a random license plate is assigned to the work inventory transaction, and the worker can pick from any license plate that has available quantity.)</span></span></li>
<li><span data-ttu-id="c4b43-316">Jeśli ilość została znaleziona na więcej niż jednym numerze identyfikacyjnym w nowej lokalizacji, pierwotny wiersz pobrania jest podzielony na kilka wierszy w celu dopasowania do każdego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="c4b43-316">If the quantity is found on more than one license plate in the new location, the original pick line is split into multiple lines to match each license plate.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c4b43-317">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-317">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-318">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-318">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-319">Umożliwia wybranie opcji <strong>Zastąp element menu lokalizacji</strong> w magazynie Mmobile App (WMA) po rozpoczęciu pracy pobrania.</span><span class="sxs-lookup"><span data-stu-id="c4b43-319">Select the <strong>Override location</strong> menu item on the WMA when you start picking work.</span></span></li>
<li><span data-ttu-id="c4b43-320">Umożliwia ręczne wprowadzenie lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-320">Manually enter a location.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c4b43-321">Akcja <strong>zastąpienia lokalizacji</strong> nie jest możliwa.</span><span class="sxs-lookup"><span data-stu-id="c4b43-321">The <strong>Override location</strong> action isn't possible.</span></span> <span data-ttu-id="c4b43-322">Nie powiedzie się i zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="c4b43-322">It fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="c4b43-323">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-323">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a><span data-ttu-id="c4b43-324">Pełny przycisk — Podziel wiersz pracy z powodu przepełnienia w lokalizacji użytkownika</span><span class="sxs-lookup"><span data-stu-id="c4b43-324">Full button – Split a work line because of overflow on the user location</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c4b43-325">Parametry ustawień klucza</span><span class="sxs-lookup"><span data-stu-id="c4b43-325">Key setup parameter</span></span></th>
<th><span data-ttu-id="c4b43-326">Ilość partii jest dostępna</span><span class="sxs-lookup"><span data-stu-id="c4b43-326">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c4b43-327">Najważniejsze kroki użytkownika</span><span class="sxs-lookup"><span data-stu-id="c4b43-327">Key user steps</span></span></th>
<th><span data-ttu-id="c4b43-328">Praca magazynu</span><span class="sxs-lookup"><span data-stu-id="c4b43-328">Warehouse work</span></span></th>
<th><span data-ttu-id="c4b43-329">Rezerwacja-zamówienie sprzedaży partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-329">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c4b43-330">Opcja <strong>Zezwalaj na dzielenie pracy</strong> jest włączona w elemencie menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="c4b43-330">The <strong>Allow splitting of work</strong> option is enabled on the mobile device menu item.</span></span></td>
<td><span data-ttu-id="c4b43-331">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-331">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-332">Wybierz opcję <strong>Pełna</strong> w magazynie Mmobile App (WMA) po rozpoczęciu procesu pobrania pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-332">Select the <strong>Full</strong> menu item on the WMA when you process picking work.</span></span></li>
<li><span data-ttu-id="c4b43-333">W polu <strong>Ilość pobrania</strong>, wprowadź częściową ilość wymaganego pobrania, aby wskazać pełną wydajność.</span><span class="sxs-lookup"><span data-stu-id="c4b43-333">In the <strong>Pick Qty</strong> field, enter a partial quantity of the required pick to indicate the full capacity.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c4b43-334">W bieżącej pracy ilość jest aktualizowana na pozostałą ilość, która musi zostać pobrana.</span><span class="sxs-lookup"><span data-stu-id="c4b43-334">On the current work, the quantity is updated to the remaining quantity that must be picked.</span></span></li>
<li><span data-ttu-id="c4b43-335">Utworzono i zamknięto nową pracę dla pobranej ilości.</span><span class="sxs-lookup"><span data-stu-id="c4b43-335">New work for the picked quantity is created and closed.</span></span></li>
</ul></td>
<td><span data-ttu-id="c4b43-336">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-336">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a><span data-ttu-id="c4b43-337">Zmniejsz ilość pobraną ukończonej pracy (z ładunku)</span><span class="sxs-lookup"><span data-stu-id="c4b43-337">Reduce the picked quantity of completed work (from a load)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c4b43-338">Parametry ustawień klucza</span><span class="sxs-lookup"><span data-stu-id="c4b43-338">Key setup parameter</span></span></th>
<th><span data-ttu-id="c4b43-339">Ilość partii jest dostępna</span><span class="sxs-lookup"><span data-stu-id="c4b43-339">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c4b43-340">Najważniejsze kroki użytkownika</span><span class="sxs-lookup"><span data-stu-id="c4b43-340">Key user steps</span></span></th>
<th><span data-ttu-id="c4b43-341">Praca magazynu</span><span class="sxs-lookup"><span data-stu-id="c4b43-341">Warehouse work</span></span></th>
<th><span data-ttu-id="c4b43-342">Rezerwacja-zamówienie sprzedaży partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-342">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c4b43-343">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-343">Not applicable</span></span></td>
<td><span data-ttu-id="c4b43-344">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-344">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-345">Otwórz stronę <strong>Zmniejsz ilość pobraną</strong> z wiersza ładunku.</span><span class="sxs-lookup"><span data-stu-id="c4b43-345">Open the <strong>Reduce picked quantity</strong> page from the load line.</span></span></li>
<li><span data-ttu-id="c4b43-346">Wprowadź ilość, która ma zostać cofnięta.</span><span class="sxs-lookup"><span data-stu-id="c4b43-346">Enter the full quantity to unpick.</span></span></li>
<li><span data-ttu-id="c4b43-347">Wybierz pozycję „Przenieś do” w lokalizacji/numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="c4b43-347">Select a "move to" location/license plate.</span></span></li>
</ol>
</td>
<td>
<ul> 
<li><span data-ttu-id="c4b43-348">Praca skojarzona z wierszem ładunku została anulowana.</span><span class="sxs-lookup"><span data-stu-id="c4b43-348">Work that is associated with the load line is canceled.</span></span></li>
<li><span data-ttu-id="c4b43-349">Nowa praca dla zarządzania zapasami jest utworzone i zamknięte.</span><span class="sxs-lookup"><span data-stu-id="c4b43-349">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c4b43-350">Ilość jest ponownie rezerwowana dla tej samej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-350">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c4b43-351">System losowo przypisuje adres i numer identyfikacyjny (jeśli lokalizacją jest numer identyfikacyjny), gdzie dostępna jest ilość.</span><span class="sxs-lookup"><span data-stu-id="c4b43-351">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-352">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-352">No</span></span></td>
<td><span data-ttu-id="c4b43-353">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-353">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-354">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-354">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-355">Ilość jest ponownie rezerwowana dla tej samej partii i dla tej samej lokalizacji i numeru identyfikacyjnego (jeśli lokalizacją jest karta identyfikacyjna — kontrolowana), która została wprowadzona podczas niepobierania.</span><span class="sxs-lookup"><span data-stu-id="c4b43-355">The quantity is re-reserved for the same batch, and for the same location and license plate (if the location is license plate–controlled) that were entered during unpicking.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a><span data-ttu-id="c4b43-356">Przenoszenie towaru w magazynie</span><span class="sxs-lookup"><span data-stu-id="c4b43-356">Move an item within a warehouse</span></span>

> [!NOTE]
> <span data-ttu-id="c4b43-357">Tę akcję magazynową można stosować tylko do przepływu typu **Procesu tworzenia pracy**, a nie do przenoszenia według szablonów.</span><span class="sxs-lookup"><span data-stu-id="c4b43-357">This warehouse action is applicable only to movement of the **Work creation process** type, not to movement by template.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c4b43-358">Parametry ustawień klucza</span><span class="sxs-lookup"><span data-stu-id="c4b43-358">Key setup parameter</span></span></th>
<th><span data-ttu-id="c4b43-359">Ilość partii jest dostępna</span><span class="sxs-lookup"><span data-stu-id="c4b43-359">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c4b43-360">Najważniejsze kroki użytkownika</span><span class="sxs-lookup"><span data-stu-id="c4b43-360">Key user steps</span></span></th>
<th><span data-ttu-id="c4b43-361">Praca magazynu</span><span class="sxs-lookup"><span data-stu-id="c4b43-361">Warehouse work</span></span></th>
<th><span data-ttu-id="c4b43-362">Rezerwacja-zamówienie sprzedaży partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-362">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c4b43-363">Dla pracownika jest włączona opcja <strong>Zezwalaj na przenoszenie zapasów ze skojarzoną pracą</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-363">The <strong>Allow movement of inventory with associated work</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c4b43-364">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-364">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-365">Umożliwia rozpoczęcie przepływu w module WMA.</span><span class="sxs-lookup"><span data-stu-id="c4b43-365">Start a movement on the WMA.</span></span></li>
<li><span data-ttu-id="c4b43-366">Wprowadź początkową i końcową lokalizację.</span><span class="sxs-lookup"><span data-stu-id="c4b43-366">Enter "from" and "to" locations.</span></span></li>
</ol></td>
<td>
<ul>
<li><span data-ttu-id="c4b43-367">W przypadku wszystkich istniejących pracy, których dotyczy przeniesienie, lokalizacja pobrania jest aktualizowana do nowej lokalizacji „do”.</span><span class="sxs-lookup"><span data-stu-id="c4b43-367">On all existing work that is affected by the move, the pick location is updated to the new "to" location.</span></span></li>
<li><span data-ttu-id="c4b43-368">Nowa praca dla zarządzania zapasami jest utworzone i zamknięte.</span><span class="sxs-lookup"><span data-stu-id="c4b43-368">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c4b43-369">Wszystkie istniejące rezerwacje, na które ma wpływ przesunięcie ilości z danej lokalizacji, są ponownie rezerwowane dla tej samej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-369">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch.</span></span> <span data-ttu-id="c4b43-370">System losowo przypisuje adres i numer identyfikacyjny (jeśli lokalizacją jest numer identyfikacyjny), gdzie dostępna jest ilość.</span><span class="sxs-lookup"><span data-stu-id="c4b43-370">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-371">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-371">No</span></span></td>
<td><span data-ttu-id="c4b43-372">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-372">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-373">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-373">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-374">Wszystkie istniejące rezerwacje, na które ma wpływ przesunięcie ilości z danej lokalizacji, są ponownie rezerwowane dla tej samej partii oraz dla nowej lokalizacji „do” i numeru identyfikacyjnego (jeśli lokalizacją jest karta identyfikacyjna).</span><span class="sxs-lookup"><span data-stu-id="c4b43-374">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch, and for the new "to" location and license plate (if the location is license plate–controlled).</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a><span data-ttu-id="c4b43-375">Cofnij zmniejsz ilość pobraną ukończonej pracy (z ładunku lub fali)</span><span class="sxs-lookup"><span data-stu-id="c4b43-375">Reverse the picked quantity of completed work (from a load or a wave)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c4b43-376">Parametry ustawień klucza</span><span class="sxs-lookup"><span data-stu-id="c4b43-376">Key setup parameter</span></span></th>
<th><span data-ttu-id="c4b43-377">Ilość partii jest dostępna</span><span class="sxs-lookup"><span data-stu-id="c4b43-377">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c4b43-378">Najważniejsze kroki użytkownika</span><span class="sxs-lookup"><span data-stu-id="c4b43-378">Key user steps</span></span></th>
<th><span data-ttu-id="c4b43-379">Praca magazynu</span><span class="sxs-lookup"><span data-stu-id="c4b43-379">Warehouse work</span></span></th>
<th><span data-ttu-id="c4b43-380">Rezerwacja-zamówienie sprzedaży partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-380">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'><span data-ttu-id="c4b43-381">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-381">Not applicable</span></span></td>
<td><span data-ttu-id="c4b43-382">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-382">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-383">Otwórz stronę <strong>Odwróć pracę</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-383">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="c4b43-384">Na stronie żądanie wybierz opcję <strong>Pozostaw towary w bieżącej lokalizacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-384">On the request page, select the <strong>Leave items at current location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c4b43-385">Cała praca skojarzona z wierszem ładunku została anulowana.</span><span class="sxs-lookup"><span data-stu-id="c4b43-385">All work that is associated with the load is canceled.</span></span></td>
<td><span data-ttu-id="c4b43-386">Ilość jest ponownie rezerwowana dla tej samej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-386">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c4b43-387">System losowo przypisuje adres i numer identyfikacyjny (jeśli lokalizacją jest numer identyfikacyjny), gdzie dostępna jest ilość.</span><span class="sxs-lookup"><span data-stu-id="c4b43-387">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-388">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-388">No</span></span></td>
<td><span data-ttu-id="c4b43-389">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-389">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-390">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-390">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-391">Ilość jest ponownie rezerwowana dla tej samej partii oraz dla lokalizacji i numeru identyfikacyjnego, gdzie ilość została pozostawiona po wycofaniu.</span><span class="sxs-lookup"><span data-stu-id="c4b43-391">The quantity is re-reserved for the same batch, and for the location and license plate where the quantity was left upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-392">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-392">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-393">Otwórz stronę <strong>Odwróć pracę</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-393">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="c4b43-394">Na stronie żądanie wybierz opcję <strong>Przypisz towary w bieżącej lokalizacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-394">On the request page, select the <strong>Assign items to this location</strong> option.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c4b43-395">Bieżąca praca została anulowana.</span><span class="sxs-lookup"><span data-stu-id="c4b43-395">The current work is canceled.</span></span></li>
<li><span data-ttu-id="c4b43-396">Nowa praca dla zarządzania zapasami jest utworzone i zamknięte.</span><span class="sxs-lookup"><span data-stu-id="c4b43-396">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c4b43-397">Ilość jest ponownie rezerwowana dla tej samej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-397">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c4b43-398">System losowo przypisuje adres i numer identyfikacyjny (jeśli lokalizacją jest numer identyfikacyjny), gdzie dostępna jest ilość.</span><span class="sxs-lookup"><span data-stu-id="c4b43-398">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-399">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-399">No</span></span></td>
<td><span data-ttu-id="c4b43-400">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-400">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-401">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-401">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-402">Ilość jest ponownie rezerwowana dla tej samej partii oraz dla lokalizacji i numeru identyfikacyjnego, gdzie ilość została przypisana po odwróceniu.</span><span class="sxs-lookup"><span data-stu-id="c4b43-402">The quantity is re-reserved for the same batch, and for the location and license plate that the quantity was assigned to upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-403">Tak/nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-403">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-404">Otwórz stronę <strong>Odwróć pracę</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-404">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="c4b43-405">Na stronie żądanie wybierz opcję <strong>Przenieś towary w bieżącej lokalizacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-405">On the request page, select the <strong>Move items to this location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c4b43-406">Odwrócenie nie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="c4b43-406">Reversal isn't supported.</span></span></td>
<td><span data-ttu-id="c4b43-407">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-407">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-408">Tak/nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-408">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-409">Otwórz stronę <strong>Odwróć pracę</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-409">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="c4b43-410">Na stronie żądanie wybierz opcję <strong>Przenieś towary w zależności od dyrektyw lokalizacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-410">On the request page, select the <strong>Move items based on location directives</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c4b43-411">Odwrócenie nie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="c4b43-411">Reversal isn't supported.</span></span> </td>
<td><span data-ttu-id="c4b43-412">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-412">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a><span data-ttu-id="c4b43-413">Krótki — pobranie ilości — umożliwia zarejestrowanie ilości fizycznie nieznalezionej w numerze lokalizacji/numeru identyfikacyjnego podczas wykonywania prac pobrań</span><span class="sxs-lookup"><span data-stu-id="c4b43-413">Short-pick a quantity – Register the quantity as physically not found at the location/license plate while you perform picking work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c4b43-414">Parametry ustawień klucza</span><span class="sxs-lookup"><span data-stu-id="c4b43-414">Key setup parameter</span></span></th>
<th><span data-ttu-id="c4b43-415">Ilość partii jest dostępna</span><span class="sxs-lookup"><span data-stu-id="c4b43-415">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c4b43-416">Najważniejsze kroki użytkownika</span><span class="sxs-lookup"><span data-stu-id="c4b43-416">Key user steps</span></span></th>
<th><span data-ttu-id="c4b43-417">Praca magazynu</span><span class="sxs-lookup"><span data-stu-id="c4b43-417">Warehouse work</span></span></th>
<th><span data-ttu-id="c4b43-418">Rezerwacja-zamówienie sprzedaży partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-418">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c4b43-419">Skonfigurowano wyjątek pracy dla <strong>krótkiego typu pobrania</strong>, w którym jest ustawiana <strong>Ponowna alokacja towaru</strong> = <strong>None</strong>, <strong>Dopasuj zapasy</strong> = <strong>Tak</strong> oraz <strong>Usuń rezerwacje</strong> = <strong>Nie</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-419">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span></td>
<td><span data-ttu-id="c4b43-420">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-420">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-421">Wybierz opcję <strong>Krótki wybór</strong> w magazynie Mmobile App (WMA) po rozpoczęciu procesu uruchomienia pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-421">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c4b43-422">W polu <strong>Ilość pobrana</strong> wpisz wartość <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-422">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c4b43-423">W polu <strong>Powód</strong>, wpisz <strong>Brak realokacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-423">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c4b43-424">Bieżąca praca jest zamknięta, a pobrana ilość wynosi 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-424">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="c4b43-425">Zostanie utworzona transakcja magazynowa typu <strong>Inwentaryzacja</strong> oraz typ <strong>Sprzedany</strong> są wystawione w celu odzwierciedlenia korekty.</span><span class="sxs-lookup"><span data-stu-id="c4b43-425">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c4b43-426">Ilość jest ponownie rezerwowana dla tej samej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-426">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c4b43-427">System losowo przypisuje adres i numer identyfikacyjny (jeśli lokalizacją jest numer identyfikacyjny), gdzie dostępna jest ilość.</span><span class="sxs-lookup"><span data-stu-id="c4b43-427">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-428">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-428">No</span></span></td>
<td><span data-ttu-id="c4b43-429">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-429">See the previous row.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="c4b43-430">Akcja krótkiego pobrania nie powiedzie się i zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="c4b43-430">The short-picking action fails, and an error is thrown.</span></span></li>
<li><span data-ttu-id="c4b43-431">Bieżąca praca pozostanie otwarta.</span><span class="sxs-lookup"><span data-stu-id="c4b43-431">The current work remains open.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c4b43-432">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-432">Not applicable</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="c4b43-433">Skonfigurowano wyjątek pracy dla <strong>krótkiego typu pobrania</strong>, w którym jest ustawiana <strong>Ponowna alokacja towaru</strong> = <strong>None</strong>, <strong>Dopasuj zapasy</strong> = <strong>Tak</strong> oraz <strong>Usuń rezerwacje</strong> = <strong>Tak</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-433">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span></td>
<td><span data-ttu-id="c4b43-434">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-434">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-435">Wybierz opcję <strong>Krótki wybór</strong> w magazynie Mmobile App (WMA) po rozpoczęciu procesu uruchomienia pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-435">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c4b43-436">W polu <strong>Ilość pobrana</strong> wpisz wartość <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-436">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c4b43-437">W polu <strong>Powód</strong>, wpisz <strong>Brak realokacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-437">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c4b43-438">Bieżąca praca jest zamknięta, a pobrana ilość wynosi 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-438">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="c4b43-439">Zostanie utworzona transakcja magazynowa typu <strong>Inwentaryzacja</strong> oraz typ <strong>Sprzedany</strong> są wystawione w celu odzwierciedlenia korekty.</span><span class="sxs-lookup"><span data-stu-id="c4b43-439">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c4b43-440">Wszystkie istniejące rezerwacje, na które ma wpływ przesunięcie ilości z danej lokalizacji krótkiego odbioru, są ponownie rezerwowane dla tej samej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-440">All existing reservations that are affected by the quantity adjustment in the short-picked location are re-reserved for the same batch.</span></span> <span data-ttu-id="c4b43-441">System losowo przypisuje adres i numer identyfikacyjny (jeśli lokalizacją jest numer identyfikacyjny), gdzie dostępna jest ilość.</span><span class="sxs-lookup"><span data-stu-id="c4b43-441">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-442">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-442">No</span></span></td>
<td><span data-ttu-id="c4b43-443">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-443">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-444">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-444">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-445">Wszystkie istniejące rezerwacje, na które ma wpływ przesunięcie ilości z danej lokalizacji krótkiego odbioru, są usuwane.</span><span class="sxs-lookup"><span data-stu-id="c4b43-445">All existing reservations that are affected by the quantity adjustment in the short-picked location are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-446">Skonfigurowano wyjątek pracy dla <strong>krótkiego typu pobrania</strong>, w którym jest ustawiana <strong>Ponowna alokacja towaru</strong> = <strong>Ręcznie</strong>, <strong>Dopasuj zapasy</strong> = <strong>Tak</strong> oraz <strong>Usuń rezerwacje</strong> = <strong>Nie/Tak</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-446">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No/Yes</strong>.</span></span> <span data-ttu-id="c4b43-447">Ponadto dla pracownika jest włączona opcja <strong>Zezwalaj na ręczną zmianę alokacji pozycji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-447">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c4b43-448">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-448">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-449">Wybierz opcję <strong>Krótki wybór</strong> w magazynie Mmobile App (WMA) po rozpoczęciu procesu uruchomienia pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-449">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c4b43-450">W polu <strong>Ilość pobrana z krótkiego odbioru</strong> wpisz wartość <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-450">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c4b43-451">W polu <strong>przyczyna</strong> wybierz opcję <strong>krótkie pobieranie z ręczną zmianą alokacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-451">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="c4b43-452">Wybierz numer lokalizacji/numer identyfikacyjny na liście.</span><span class="sxs-lookup"><span data-stu-id="c4b43-452">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c4b43-453">W bieżącej pracy wykonywane są następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="c4b43-453">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="c4b43-454">Bieżąca linia odbioru jest zamknięta, a pobrana ilość wynosi 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-454">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="c4b43-455">Wiersz odłożenia został anulowany.</span><span class="sxs-lookup"><span data-stu-id="c4b43-455">The put line is canceled.</span></span></li>
<li><span data-ttu-id="c4b43-456">Zostanie utworzony nowy wiersz pobrania.</span><span class="sxs-lookup"><span data-stu-id="c4b43-456">A new pick line is created.</span></span> <span data-ttu-id="c4b43-457">Używa on numeru lokalizacji/licencji wybranego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c4b43-457">It uses the location/license plate that the user selected.</span></span></li>
<li><span data-ttu-id="c4b43-458">Zostanie utworzony nowy linia włożenia.</span><span class="sxs-lookup"><span data-stu-id="c4b43-458">A new put line is created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="c4b43-459">Zostanie utworzona transakcja magazynowa typu <strong>Inwentaryzacja</strong> oraz typ <strong>Sprzedany</strong> są wystawione w celu odzwierciedlenia korekty.</span><span class="sxs-lookup"><span data-stu-id="c4b43-459">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c4b43-460">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-460">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-461">Skonfigurowano wyjątek pracy dla <strong>krótkiego typu pobrania</strong>, w którym jest ustawiana <strong>Ponowna alokacja towaru</strong> = <strong>Ręcznie</strong>, <strong>Dopasuj zapasy</strong> = <strong>Tak</strong> oraz <strong>Usuń rezerwacje</strong> = <strong>Nie</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-461">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span> <span data-ttu-id="c4b43-462">Ponadto dla pracownika jest włączona opcja <strong>Zezwalaj na ręczną zmianę alokacji pozycji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-462">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c4b43-463">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-463">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-464">Wybierz opcję <strong>Krótki wybór</strong> w magazynie Mmobile App (WMA) po rozpoczęciu procesu uruchomienia pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-464">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c4b43-465">W polu <strong>Ilość pobrana z krótkiego odbioru</strong> wpisz wartość <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-465">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c4b43-466">W polu <strong>przyczyna</strong> wybierz opcję <strong>krótkie pobieranie z ręczną zmianą alokacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-466">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c4b43-467">Akcja krótkiego pobrania nie powiedzie się i zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="c4b43-467">The short-picking action fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="c4b43-468">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-468">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-469">Skonfigurowano wyjątek pracy dla <strong>krótkiego typu pobrania</strong>, w którym jest ustawiana <strong>Ponowna alokacja towaru</strong> = <strong>Ręcznie</strong>, <strong>Dopasuj zapasy</strong> = <strong>Tak</strong> oraz <strong>Usuń rezerwacje</strong> = <strong>Tak</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-469">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span> <span data-ttu-id="c4b43-470">Ponadto dla pracownika jest włączona opcja <strong>Zezwalaj na ręczną zmianę alokacji pozycji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-470">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c4b43-471">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-471">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-472">Wybierz opcję <strong>Krótki wybór</strong> w magazynie Mmobile App (WMA) po rozpoczęciu procesu uruchomienia pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-472">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c4b43-473">W polu <strong>Ilość pobrana z krótkiego odbioru</strong> wpisz wartość <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-473">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c4b43-474">W polu <strong>przyczyna</strong> wybierz opcję <strong>krótkie pobieranie z ręczną zmianą alokacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-474">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="c4b43-475">Wybierz numer lokalizacji/numer identyfikacyjny na liście.</span><span class="sxs-lookup"><span data-stu-id="c4b43-475">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c4b43-476">W bieżącej pracy wykonywane są następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="c4b43-476">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="c4b43-477">Bieżąca linia odbioru jest zamknięta, a pobrana ilość wynosi 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-477">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="c4b43-478">Wiersz odłożenia został anulowany.</span><span class="sxs-lookup"><span data-stu-id="c4b43-478">The put line is canceled.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="c4b43-479">Zostanie utworzona transakcja magazynowa typu <strong>Inwentaryzacja</strong> oraz typ <strong>Sprzedany</strong> są wystawione w celu odzwierciedlenia korekty.</span><span class="sxs-lookup"><span data-stu-id="c4b43-479">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c4b43-480">Wszystkie istniejące rezerwacje, na które ma wpływ przesunięcie ilości z danej lokalizacji krótkiego odbioru/numer identyfikacyjny, są usuwane.</span><span class="sxs-lookup"><span data-stu-id="c4b43-480">All existing reservations that are affected by the quantity adjustment in the short-picked location/license plate are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-481">Skonfigurowano wyjątek pracy dla <strong>krótkiego typu pobrania</strong>, w którym jest ustawiana <strong>Ponowna alokacja towaru</strong> = <strong>Automatycznie</strong>, <strong>Dopasuj zapasy</strong> = <strong>Tak/Nie</strong> oraz <strong>Usuń rezerwacje</strong> = <strong>Tak/Nie</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-481">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Automatic</strong>, <strong>Adjust inventory</strong> = <strong>Yes/No</strong>, and <strong>Remove reservations</strong> = <strong>Yes/No</strong>.</span></span></td>
<td><span data-ttu-id="c4b43-482">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="c4b43-482">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-483">Wybierz opcję <strong>Krótki wybór</strong> w magazynie Mmobile App (WMA) po rozpoczęciu procesu uruchomienia pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-483">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c4b43-484">W polu <strong>Ilość pobrana z krótkiego odbioru</strong> wpisz wartość <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c4b43-484">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c4b43-485">W polu <strong>przyczyna</strong> wybierz opcję <strong>krótkie pobieranie z automatyczną zmianą alokacji</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-485">In the <strong>Reason</strong> field, select <strong>Short Picking with automatic reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c4b43-486">Krótkie — pobranie obejmujące automatyczne ponowne przydzielanie nie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="c4b43-486">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
<td><span data-ttu-id="c4b43-487">Krótkie — pobranie obejmujące automatyczne ponowne przydzielanie nie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="c4b43-487">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a><span data-ttu-id="c4b43-488">Zmiana stanu zapasów</span><span class="sxs-lookup"><span data-stu-id="c4b43-488">Change the inventory status</span></span>

> [!NOTE]
> <span data-ttu-id="c4b43-489">Tę akcję magazynową można wykonać z wielu punktów wejścia.</span><span class="sxs-lookup"><span data-stu-id="c4b43-489">This warehouse action can be performed from multiple entry points.</span></span> <span data-ttu-id="c4b43-490">W przykładzie pokazano, że akcja **Zmień stan zapasów** jest używana na stronie **dostępne zapasy w ramach lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-490">The example that is shown here uses **Inventory status change** action on the **On-hand by location** page.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c4b43-491">Parametry ustawień klucza</span><span class="sxs-lookup"><span data-stu-id="c4b43-491">Key setup parameter</span></span></th>
<th><span data-ttu-id="c4b43-492">Ilość partii jest dostępna</span><span class="sxs-lookup"><span data-stu-id="c4b43-492">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c4b43-493">Najważniejsze kroki użytkownika</span><span class="sxs-lookup"><span data-stu-id="c4b43-493">Key user steps</span></span></th>
<th><span data-ttu-id="c4b43-494">Praca magazynu</span><span class="sxs-lookup"><span data-stu-id="c4b43-494">Warehouse work</span></span></th>
<th><span data-ttu-id="c4b43-495">Rezerwacja-zamówienie sprzedaży partii</span><span class="sxs-lookup"><span data-stu-id="c4b43-495">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c4b43-496">Na karcie <strong>magazyn</strong> w rekordzie <strong>Magazynu</strong> w polu<strong>Usuń rezerwacje</strong> i oznaczenia jest ustawiona wartość <strong>rezerwacje</strong> lub <strong>oznaczenia i rezerwacje</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-496">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>Reservations</strong> or <strong>Markings and reservations</strong>.</span></span></td>
<td><span data-ttu-id="c4b43-497">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-497">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-498">Wybór konkretnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-498">Select a specific location.</span></span></li>
<li><span data-ttu-id="c4b43-499">Wybierz wiersz z określonym towarem, lokalizacją i numerem identyfikacyjnym (Jeśli lokalizacja jest kontrolowana numerem identyfikacyjnym).</span><span class="sxs-lookup"><span data-stu-id="c4b43-499">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="c4b43-500">Wybierz <strong>Zmianę stanu zapasów</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-500">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="c4b43-501">Pole <strong>Stan zapasów</strong> należy skonfigurować na <strong>blokowanie</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-501">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c4b43-502">Zmiany stanu zapasów nie są dozwolone dla ilości, które są zarezerwowane dla pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-502">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="c4b43-503">Ilość jest ponownie rezerwowana dla tej samej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-503">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c4b43-504">System losowo przypisuje adres i numer identyfikacyjny (jeśli lokalizacją jest numer identyfikacyjny), gdzie dostępna jest ilość.</span><span class="sxs-lookup"><span data-stu-id="c4b43-504">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></li>
<li><span data-ttu-id="c4b43-505">Zostaną utworzone dwie transakcje magazynowe o typie <strong>zmiany stanu zapasów</strong>, reprezentujące zmianę w wymiarze stanu zapasów.</span><span class="sxs-lookup"><span data-stu-id="c4b43-505">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="c4b43-506">Tworzona jest transakcja magazynowa typu <strong>blokowania zapasów</strong> i <strong>zarezerwowany typ fizycznego</strong> wystawienia w celu reprezentowania rezerwacji zablokowanej ilości.</span><span class="sxs-lookup"><span data-stu-id="c4b43-506">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-507">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-507">No</span></span></td>
<td><span data-ttu-id="c4b43-508">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-508">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-509">Zmiany stanu zapasów nie są dozwolone dla ilości, które są zarezerwowane dla pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-509">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="c4b43-510">Rezerwacja jest usuwana.</span><span class="sxs-lookup"><span data-stu-id="c4b43-510">The reservation is removed.</span></span></li>
<li><span data-ttu-id="c4b43-511">Zostaną utworzone dwie transakcje magazynowe o typie <strong>zmiany stanu zapasów</strong>, reprezentujące zmianę w wymiarze stanu zapasów.</span><span class="sxs-lookup"><span data-stu-id="c4b43-511">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="c4b43-512">Tworzona jest transakcja magazynowa typu <strong>blokowania zapasów</strong> i <strong>zarezerwowany typ fizycznego</strong> wystawienia w celu reprezentowania rezerwacji zablokowanej ilości.</span><span class="sxs-lookup"><span data-stu-id="c4b43-512">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="c4b43-513">Na karcie magazyn w rekordzie <strong>Magazyn</strong> w polu <strong>Magazyn</strong>, pole <strong>Usuń rezerwacje i oznaczenia</strong> ma wartość <strong>Nie</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-513">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>None</strong>.</span></span></td>
<td><span data-ttu-id="c4b43-514">Tak</span><span class="sxs-lookup"><span data-stu-id="c4b43-514">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c4b43-515">Wybór konkretnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-515">Select a specific location.</span></span></li>
<li><span data-ttu-id="c4b43-516">Wybierz wiersz z określonym towarem, lokalizacją i numerem identyfikacyjnym (Jeśli lokalizacja jest kontrolowana numerem identyfikacyjnym).</span><span class="sxs-lookup"><span data-stu-id="c4b43-516">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="c4b43-517">Wybierz <strong>Zmianę stanu zapasów</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-517">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="c4b43-518">Pole <strong>Stan zapasów</strong> należy skonfigurować na <strong>blokowanie</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4b43-518">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c4b43-519">Zmiany stanu zapasów nie są dozwolone dla ilości, które są zarezerwowane dla pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-519">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="c4b43-520">Ilość jest ponownie rezerwowana dla tej samej partii.</span><span class="sxs-lookup"><span data-stu-id="c4b43-520">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c4b43-521">System losowo przypisuje adres i numer identyfikacyjny (jeśli lokalizacją jest numer identyfikacyjny), gdzie dostępna jest ilość.</span><span class="sxs-lookup"><span data-stu-id="c4b43-521">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c4b43-522">Nie</span><span class="sxs-lookup"><span data-stu-id="c4b43-522">No</span></span></td>
<td><span data-ttu-id="c4b43-523">Przejdź do poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c4b43-523">See the previous row.</span></span></td>
<td><span data-ttu-id="c4b43-524">Zmiany stanu zapasów nie są dozwolone dla ilości, które są zarezerwowane dla pracy.</span><span class="sxs-lookup"><span data-stu-id="c4b43-524">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="c4b43-525">Zmiany stanu zapasów są niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="c4b43-525">Inventory status changes aren't allowed.</span></span></td>
</tr>
</tbody>
</table>

## <a name="limitations"></a><span data-ttu-id="c4b43-526">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="c4b43-526">Limitations</span></span>

- <span data-ttu-id="c4b43-527">Funkcja rezerwacji wymiarów na poziomie magazynu elastycznego nie obsługuje następujących funkcji:</span><span class="sxs-lookup"><span data-stu-id="c4b43-527">The flexible warehouse-level dimension reservation functionality doesn't support the following features:</span></span>

    - <span data-ttu-id="c4b43-528">Zarządzanie ilością efektywną</span><span class="sxs-lookup"><span data-stu-id="c4b43-528">Catch weight management</span></span>
    - <span data-ttu-id="c4b43-529">Ujemne wartości magazynu fizycznego</span><span class="sxs-lookup"><span data-stu-id="c4b43-529">Physical negative inventory</span></span>
    - <span data-ttu-id="c4b43-530">Rezerwacja na zamówioną dostawę</span><span class="sxs-lookup"><span data-stu-id="c4b43-530">Reservation against ordered supply</span></span>
    - <span data-ttu-id="c4b43-531">Zamówienia przeniesienia i pobranie surowca</span><span class="sxs-lookup"><span data-stu-id="c4b43-531">Transfer orders and raw material picking</span></span>

- <span data-ttu-id="c4b43-532">Reguła konsolidacji kontenerów dla pakowania według jednostki dyrektywy ma pewne ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="c4b43-532">The container consolidation rule for packing by directive unit has limitations.</span></span> <span data-ttu-id="c4b43-533">W przypadku rezerwacji zamówionych zaleca się, aby nie stosować szablonów konstruowania kontenerów, w których jest włączone pole **pakowania według jednostek dyrektywy**.</span><span class="sxs-lookup"><span data-stu-id="c4b43-533">For order-committed reservations, we recommend that you not use container build templates where the **Pack by directive unit** field is enabled.</span></span> <span data-ttu-id="c4b43-534">W bieżącym projekcie dyrektywy lokalizacji nie są używane podczas tworzenia pracy magazynowej.</span><span class="sxs-lookup"><span data-stu-id="c4b43-534">In the current design, location directives aren't used when warehouse work is created.</span></span> <span data-ttu-id="c4b43-535">Dlatego tylko najniższa jednostka w grupie sekwencji jednostek (jednostka magazynowa) jest stosowana w trakcie kroku konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="c4b43-535">Therefore, only the lowest unit in the unit sequence group (the inventory unit) is applied during the containerization wave step.</span></span>
