---
title: "Opcje transakcji środków trwałych"
description: "W tym artykule opisano różne dostępne metody tworzenia transakcji na środkach trwałych."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9be300652e3de23554e1e61e32f1b0070e08099b
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="fixed-asset-transaction-options"></a><span data-ttu-id="a0ee4-103">Opcje transakcji środków trwałych</span><span class="sxs-lookup"><span data-stu-id="a0ee4-103">Fixed asset transaction options</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0ee4-104">W tym artykule opisano różne dostępne metody tworzenia transakcji na środkach trwałych.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-104">This article describes the different methods available to create fixed asset transactions.</span></span>

<span data-ttu-id="a0ee4-105">Istnieje możliwość skonfigurowania modułu Środki trwałe w celu integracji z modułami Księga główna, Rozrachunki z dostawcami, Rozrachunki z odbiorcami i Zaopatrzenie i sourcing.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-105">You can set up Fixed assets for integration with Accounts payable, Accounts receivable, Procurement and sourcing, and General ledger.</span></span> <span data-ttu-id="a0ee4-106">Ponadto towary w module Zarządzanie zapasami można przenieść do modułu Środki trwałeh, aby można było używać tych towarów wewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-106">You can also transfer items in Inventory management to Fixed assets if you want to use those items internally.</span></span>

## <a name="accounts-payable"></a><span data-ttu-id="a0ee4-107">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="a0ee4-107">Accounts payable</span></span>
<span data-ttu-id="a0ee4-108">Istnieje możliwość wprowadzania transakcji środków trwałych na stronie Załącznik arkusza.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-108">You can enter Fixed assets transactions in the Journal voucher page.</span></span> <span data-ttu-id="a0ee4-109">Ta strona może być otwierana ze strony Arkusz faktur.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-109">This page can be opened from the Invoice journal page.</span></span> <span data-ttu-id="a0ee4-110">Stronę załącznika arkusza można też otworzyć ze strony arkusza zatwierdzania faktur.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-110">You can also open the Journal voucher page from the Invoice approval journal page.</span></span> <span data-ttu-id="a0ee4-111">W polu Typ konta przeciwstawnego wybierz Środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-111">In the Offset account type field, select Fixed assets.</span></span> <span data-ttu-id="a0ee4-112">Następnie w polu Konto przeciwstawne wybierz numer środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-112">Then, in the Offset account field, select a fixed asset number.</span></span> <span data-ttu-id="a0ee4-113">Na karcie Środki trwałe wprowadź wartości w polach Typ transakcji i Księga.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-113">On the Fixed assets tab, enter values in the Transaction type and Book fields.</span></span>

## <a name="accounts-receivable"></a><span data-ttu-id="a0ee4-114">Rozrachunki z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="a0ee4-114">Accounts receivable</span></span>
<span data-ttu-id="a0ee4-115">Istnieje możliwość wprowadzania transakcji środków trwałych na stronie Faktura niezależna.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-115">You can enter Fixed assets transactions in the Free text invoice page.</span></span>  <span data-ttu-id="a0ee4-116">Na stronie Faktura niezależna w siatce Wiersze faktury wybierz pozycję w wierszu.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-116">In the Free text invoice page, in the Invoice lines grid, select a line item.</span></span> <span data-ttu-id="a0ee4-117">Kliknij skróconą kartę Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-117">Click the Line details FastTab.</span></span> <span data-ttu-id="a0ee4-118">Wprowadź numer środka trwałego i księgę dla transakcji likwidacji.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-118">Enter the fixed asset number and book for the disposal transaction.</span></span> <span data-ttu-id="a0ee4-119">W przypadku faktur niezależnych, transakcja środków trwałych jest zawsze typu Likwidacja — sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-119">For free text invoices, the fixed asset transaction type is always Disposal - sale.</span></span>

## <a name="procurement-and-sourcing"></a><span data-ttu-id="a0ee4-120">Zaopatrzenie i sourcing</span><span class="sxs-lookup"><span data-stu-id="a0ee4-120">Procurement and sourcing</span></span>
<span data-ttu-id="a0ee4-121">Istnieje możliwość wprowadzania transakcji środków trwałych na stronie Zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-121">You can enter Fixed assets transactions in the Purchase order page.</span></span> <span data-ttu-id="a0ee4-122">Wprowadź wymagane informacje, aby utworzyć zamówienie zakupu, a następnie kliknij OK.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-122">Enter the required information to create a purchase order, and then click OK.</span></span> <span data-ttu-id="a0ee4-123">Na stronie zamówienia zakupu kliknij skróconą kartę Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-123">In the Purchase order page, click the Line details FastTab.</span></span> <span data-ttu-id="a0ee4-124">Następnie, na karcie Środki trwałe wprowadź informacje o środku trwałym.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-124">Then, on the Fixed assets tab, enter information about the fixed asset.</span></span> 

<span data-ttu-id="a0ee4-125">Aby zaksięgować transakcję nabycia istniejącego środka trwałego, należy określić numer środka trwałego, księgę i typ transakcji.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-125">To post an acquisition transaction for an existing fixed asset, specify the fixed asset number, book, and transaction type.</span></span> <span data-ttu-id="a0ee4-126">Nie można zaksięgować środka trwałego, jeśli brakuje którejkolwiek z tych informacji.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-126">The fixed asset cannot be posted if any of this information is missing.</span></span> <span data-ttu-id="a0ee4-127">Aby zaksięgować transakcję nabycia nowego środka trwałego, zaznacz opcję Nowy środek trwały?, a następnie wybierz grupę środków trwałych, do której ma zostać przypisany nowy środek.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-127">To post an acquisition transaction for a new fixed asset, select the New fixed asset? option, and then select the fixed asset group to assign the new asset to.</span></span> <span data-ttu-id="a0ee4-128">Jednak nie są dostępne żadne pola środków trwałych dla wiersza, jeśli towar należy do grupy modeli magazynu, która używa modelu magazynu z kosztem standardowym.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-128">However, no fixed asset fields are available for a line if the item is in an inventory model group that uses a standard cost inventory model.</span></span> <span data-ttu-id="a0ee4-129">Ponadto, opcje, które są zdefiniowane na stronie Parametry środków trwałych, określają, czy można księgować transakcje nabycia z modułów zakupów.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-129">Additionally, the options that are defined in the Fixed assets parameters page determine whether you can post acquisition transactions from the purchasing modules.</span></span> 

<span data-ttu-id="a0ee4-130">Jeśli do nabywania środków trwałych jest używany arkusz Zamówienie zakupu lub Środki trwałe z modułu Zapasy, ma to wpływ na wartość zapasów.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-130">When a purchase order or the Inventory to fixed assets journal is used to acquire fixed assets, the inventory value is affected.</span></span>

## <a name="general-ledger"></a><span data-ttu-id="a0ee4-131">Księga główna</span><span class="sxs-lookup"><span data-stu-id="a0ee4-131">General ledger</span></span>
<span data-ttu-id="a0ee4-132">Transakcje środków trwałych dowolnego typu można księgować na stronie Arkusz finansowy.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-132">Any fixed asset transaction type can be posted in the General journal page.</span></span> <span data-ttu-id="a0ee4-133">Można także używać arkuszy w module Środki trwałe, aby księgować transakcje środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="a0ee4-133">You can also use journals in Fixed assets to post fixed asset transactions.</span></span>

## <a name="options-for-entering-fixed-asset-transaction-types"></a><span data-ttu-id="a0ee4-134">Opcje wprowadzania typów transakcji środków trwałych</span><span class="sxs-lookup"><span data-stu-id="a0ee4-134">Options for entering fixed asset transaction types</span></span>


| <span data-ttu-id="a0ee4-135">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="a0ee4-135">Transaction type</span></span>                    | <span data-ttu-id="a0ee4-136">Moduł</span><span class="sxs-lookup"><span data-stu-id="a0ee4-136">Module</span></span>                   | <span data-ttu-id="a0ee4-137">Opcje</span><span class="sxs-lookup"><span data-stu-id="a0ee4-137">Options</span></span>                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| <span data-ttu-id="a0ee4-138">Nabycie, korekta nabycia</span><span class="sxs-lookup"><span data-stu-id="a0ee4-138">Acquisition, Acquisition adjustment</span></span> | <span data-ttu-id="a0ee4-139">Środki trwałe</span><span class="sxs-lookup"><span data-stu-id="a0ee4-139">Fixed assets</span></span>             | <span data-ttu-id="a0ee4-140">Środki trwałe, Zapasy do środków trwałych</span><span class="sxs-lookup"><span data-stu-id="a0ee4-140">Fixed assets, Inventory to fixed assets</span></span>   |
|                                     | <span data-ttu-id="a0ee4-141">Księga główna</span><span class="sxs-lookup"><span data-stu-id="a0ee4-141">General ledger</span></span>           | <span data-ttu-id="a0ee4-142">Arkusze finansowe</span><span class="sxs-lookup"><span data-stu-id="a0ee4-142">General journal</span></span>                           |
|                                     | <span data-ttu-id="a0ee4-143">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="a0ee4-143">Accounts payable</span></span>         | <span data-ttu-id="a0ee4-144">Arkusz faktury i arkusz zatwierdzania faktur</span><span class="sxs-lookup"><span data-stu-id="a0ee4-144">Invoice journal, Invoice approval journal</span></span> |
|                                     | <span data-ttu-id="a0ee4-145">Zaopatrzenie i sourcing</span><span class="sxs-lookup"><span data-stu-id="a0ee4-145">Procurement and sourcing</span></span> | <span data-ttu-id="a0ee4-146">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="a0ee4-146">Purchase order</span></span>                            |
| <span data-ttu-id="a0ee4-147">Amortyzacja</span><span class="sxs-lookup"><span data-stu-id="a0ee4-147">Depreciation</span></span>                        | <span data-ttu-id="a0ee4-148">Środki trwałe</span><span class="sxs-lookup"><span data-stu-id="a0ee4-148">Fixed assets</span></span>             | <span data-ttu-id="a0ee4-149">Środki trwałe</span><span class="sxs-lookup"><span data-stu-id="a0ee4-149">Fixed assets</span></span>                              |
|                                     | <span data-ttu-id="a0ee4-150">Księga główna</span><span class="sxs-lookup"><span data-stu-id="a0ee4-150">General ledger</span></span>           | <span data-ttu-id="a0ee4-151">Arkusze finansowe</span><span class="sxs-lookup"><span data-stu-id="a0ee4-151">General journal</span></span>                           |
| <span data-ttu-id="a0ee4-152">Likwidacja</span><span class="sxs-lookup"><span data-stu-id="a0ee4-152">Disposal</span></span>                            | <span data-ttu-id="a0ee4-153">Środki trwałe</span><span class="sxs-lookup"><span data-stu-id="a0ee4-153">Fixed assets</span></span>             | <span data-ttu-id="a0ee4-154">Środki trwałe</span><span class="sxs-lookup"><span data-stu-id="a0ee4-154">Fixed assets</span></span>                              |
| <span data-ttu-id="a0ee4-155">** **</span><span class="sxs-lookup"><span data-stu-id="a0ee4-155">** **</span></span>                               | <span data-ttu-id="a0ee4-156">Księga główna</span><span class="sxs-lookup"><span data-stu-id="a0ee4-156">General ledger</span></span>           | <span data-ttu-id="a0ee4-157">Arkusze finansowe</span><span class="sxs-lookup"><span data-stu-id="a0ee4-157">General journal</span></span>                           |
| <span data-ttu-id="a0ee4-158">** **</span><span class="sxs-lookup"><span data-stu-id="a0ee4-158">** **</span></span>                               | <span data-ttu-id="a0ee4-159">Rozrachunki z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="a0ee4-159">Accounts receivable</span></span>      | <span data-ttu-id="a0ee4-160">Faktura niezależna</span><span class="sxs-lookup"><span data-stu-id="a0ee4-160">Free text invoice</span></span>                         |



<span data-ttu-id="a0ee4-161">Aby uzyskać więcej informacji, zobacz [Integracja środków trwałych](fixed-asset-integration.md).</span><span class="sxs-lookup"><span data-stu-id="a0ee4-161">For more information, see [Fixed assets integration](fixed-asset-integration.md).</span></span>




