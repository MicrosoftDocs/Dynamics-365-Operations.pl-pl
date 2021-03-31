---
title: Wpisywanie danych faktury w AP za pomocą faktury od dostawcy
description: Ten przewodnik zadania pomoże utworzyć fakturę od dostawcy na podstawie zamówienia zakupu oraz wyświetlić wyniki uzgadniania zamówienia zakupu, przyjęcia i faktury (uzgadnianie trzyelementowe).
author: abruer
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20a058eb17bcab11056c91ab3570d6cd5b84b631
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227215"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a><span data-ttu-id="57243-103">Wpisywanie danych faktury w AP za pomocą faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="57243-103">Key invoice data in AP using a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="57243-104">Ten przewodnik zadania pomoże utworzyć fakturę od dostawcy na podstawie zamówienia zakupu oraz wyświetlić wyniki uzgadniania zamówienia zakupu, przyjęcia i faktury (uzgadnianie trzyelementowe).</span><span class="sxs-lookup"><span data-stu-id="57243-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="57243-105">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="57243-105">Create a purchase order</span></span>
1. <span data-ttu-id="57243-106">W okienku nawigacji wybierz kolejno **Moduły > Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="57243-106">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="57243-107">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="57243-107">Click **New**.</span></span>
3. <span data-ttu-id="57243-108">W polu **Konto dostawcy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="57243-108">In the **Vendor account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="57243-109">Znajdź dostawcę do wybrania.</span><span class="sxs-lookup"><span data-stu-id="57243-109">Find a vendor to select.</span></span> <span data-ttu-id="57243-110">Na przykład przewiń w dół do dostawcy US-104.</span><span class="sxs-lookup"><span data-stu-id="57243-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="57243-111">Wybierz dostawcę US-104.</span><span class="sxs-lookup"><span data-stu-id="57243-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="57243-112">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="57243-112">Click **OK**.</span></span>
7. <span data-ttu-id="57243-113">W polu **Numer towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="57243-113">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="57243-114">Wybierz pozycję magazynową.</span><span class="sxs-lookup"><span data-stu-id="57243-114">Select an inventory item.</span></span> <span data-ttu-id="57243-115">Na przykład zaznacz numer towaru 1000.</span><span class="sxs-lookup"><span data-stu-id="57243-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="57243-116">Rozwiń skróconą kartę **Szczegóły wiersza**.</span><span class="sxs-lookup"><span data-stu-id="57243-116">Expand the **Line details** fastTab.</span></span>
10. <span data-ttu-id="57243-117">Kliknij kartę **Ustawienia**. Można ręcznie zastąpić zasady uzgadniania i określić nieużywanie uzgadniania, używanie uzgadniania dwuelementowego lub używanie uzgadniania trzyelementowego.</span><span class="sxs-lookup"><span data-stu-id="57243-117">Click the **Setup** tab. You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="57243-118">W okienku akcji kliknij pozycję **Zakup.**</span><span class="sxs-lookup"><span data-stu-id="57243-118">On the Action Pane, click **Purchase**.</span></span>
12. <span data-ttu-id="57243-119">Kliknij przycisk **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="57243-119">Click **Confirm**.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="57243-120">Odbieranie produktów</span><span class="sxs-lookup"><span data-stu-id="57243-120">Receive the products</span></span>
1. <span data-ttu-id="57243-121">W okienku akcji kliknij pozycję **Odbierz.**</span><span class="sxs-lookup"><span data-stu-id="57243-121">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="57243-122">Kliknij opcję **Dokument przyjęcia produktów.**</span><span class="sxs-lookup"><span data-stu-id="57243-122">Click **Product receipt**.</span></span>
3. <span data-ttu-id="57243-123">W polu **Dokument przyjęcia** produktów wprowadź numer dokumentu przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="57243-123">In the **Product receipt** field, enter the product receipt number.</span></span> <span data-ttu-id="57243-124">Na przykład wpisz PR123.</span><span class="sxs-lookup"><span data-stu-id="57243-124">For example, enter PR123.</span></span>
4. <span data-ttu-id="57243-125">Kliknij przycisk **OK**, aby zaksięgować dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="57243-125">Click **OK** to post the product receipt.</span></span>
5. <span data-ttu-id="57243-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57243-126">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="57243-127">Tworzenie faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="57243-127">Create a vendor invoice</span></span>
1. <span data-ttu-id="57243-128">W okienku nawigacji wybierz kolejno **Moduły > Rozrachunki z dostawcami > Zamówienia zakupu > Niezafakturowane zamówienia zakupu o stanie Otrzymano**.</span><span class="sxs-lookup"><span data-stu-id="57243-128">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders received but not invoiced**.</span></span>
2. <span data-ttu-id="57243-129">Zaznacz utworzone przez siebie zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="57243-129">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="57243-130">W okienku akcji kliknij pozycję **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="57243-130">On the Action Pane, click **Invoice**.</span></span>
4. <span data-ttu-id="57243-131">Kliknij opcję **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="57243-131">Click **Invoice**.</span></span>
5. <span data-ttu-id="57243-132">W polu **Numer** wprowadź numer faktury.</span><span class="sxs-lookup"><span data-stu-id="57243-132">In the **Number** field, enter the invoice number.</span></span>
6. <span data-ttu-id="57243-133">Wypełnij pole **Opis faktury**.</span><span class="sxs-lookup"><span data-stu-id="57243-133">In the **Invoice description** field, type a value.</span></span>
7. <span data-ttu-id="57243-134">W polu **Data faktury** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="57243-134">In the **Invoice date** field, enter a date.</span></span>
8. <span data-ttu-id="57243-135">W polu **Cena jednostkowa** wpisz 1200.</span><span class="sxs-lookup"><span data-stu-id="57243-135">In the **Unit price** field, enter 1200.</span></span>
9. <span data-ttu-id="57243-136">Kliknij przycisk **Dodaj wiersz.**</span><span class="sxs-lookup"><span data-stu-id="57243-136">Click **Add line**.</span></span>
10. <span data-ttu-id="57243-137">W polu **Numer towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="57243-137">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="57243-138">Na liście znajdź numer towaru opłaty instalacyjnej.</span><span class="sxs-lookup"><span data-stu-id="57243-138">In the list, find the installation charge item number.</span></span> <span data-ttu-id="57243-139">Na przykład S0001.</span><span class="sxs-lookup"><span data-stu-id="57243-139">For example, S0001</span></span>
12. <span data-ttu-id="57243-140">Zaznacz numer towaru opłaty instalacyjnej.</span><span class="sxs-lookup"><span data-stu-id="57243-140">Select the installation charge item number.</span></span> <span data-ttu-id="57243-141">Zwróć uwagę, że po wprowadzeniu zmian nie wykonano uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="57243-141">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="57243-142">Kliknij przycisk **Aktualizuj stan uzgadniania**.</span><span class="sxs-lookup"><span data-stu-id="57243-142">Click **Update match status**.</span></span>
14. <span data-ttu-id="57243-143">W okienku akcji kliknij pozycję **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="57243-143">On the Action Pane, click **Review**.</span></span>
15. <span data-ttu-id="57243-144">Kliknij przycisk **Szczegóły uzgadniania**.</span><span class="sxs-lookup"><span data-stu-id="57243-144">Click **Matching details**.</span></span> <span data-ttu-id="57243-145">Nowy wiersz z usługami nie musi być uzgadniany, dlatego pozostaje stan „Nie wykonano”.</span><span class="sxs-lookup"><span data-stu-id="57243-145">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="57243-146">Zaznacz dokument przyjęcia produktów dla otrzymanej pozycji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="57243-146">Select the product receipt for the inventory item that you received.</span></span> <span data-ttu-id="57243-147">Wiersz z dokumentem przyjęcia produktów został uzgodniony, ale występuje niezgodność ilości lub ceny, dlatego operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="57243-147">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="57243-148">W polu **Cena jednostkowa** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="57243-148">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="57243-149">Teraz, gdy cena jednostkowa jest zgodna, stan został zaktualizowany na Powodzenie.</span><span class="sxs-lookup"><span data-stu-id="57243-149">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="57243-150">Jeśli zasady pozwalają na rozbieżności lub gdy uzgadnianie jest traktowane jedynie jako ostrzeżenie, można zaksięgować fakturę.</span><span class="sxs-lookup"><span data-stu-id="57243-150">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="57243-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57243-151">Close the page.</span></span>
19. <span data-ttu-id="57243-152">Kliknij przycisk **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="57243-152">Click **Post**.</span></span>
20. <span data-ttu-id="57243-153">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="57243-153">Close the form.</span></span> <span data-ttu-id="57243-154">Zwróć uwagę, że zamówienie zakupu nie jest już wyświetlane jako otrzymane, ale niezafakturowane.</span><span class="sxs-lookup"><span data-stu-id="57243-154">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]