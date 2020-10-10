---
title: Rozwiązywanie problemów z zamówieniami zakupu
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zamówieniami zakupu.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
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
ms.openlocfilehash: e55974f65577170880e60095f1ba74ea7366e592
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834410"
---
# <a name="troubleshoot-purchase-orders"></a><span data-ttu-id="7fb02-103">Rozwiązywanie problemów z zamówieniami zakupu</span><span class="sxs-lookup"><span data-stu-id="7fb02-103">Troubleshoot purchase orders</span></span>

<span data-ttu-id="7fb02-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zamówieniami zakupu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-104">This topic describes how to fix issues that you might encounter while you work with purchase orders.</span></span>

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a><span data-ttu-id="7fb02-105">Akcję można wykonać tylko po pełnym rozdzieleniu numeru wiersza.</span><span class="sxs-lookup"><span data-stu-id="7fb02-105">An action can be completed only after the line number is fully distributed.</span></span>

<span data-ttu-id="7fb02-106">Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-106">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="7fb02-107">Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="7fb02-107">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="7fb02-108">Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="7fb02-108">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a><span data-ttu-id="7fb02-109">Gdy zamówienia zakupu są importowane za pomocą zarządzania danymi, numery wierszy zamówienia nie są zgodne z przyrostem zdefiniowanym w parametrach systemu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-109">When purchase orders are imported through data management, purchase order line numbers don't follow the increment that defined in system parameters.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7fb02-110">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="7fb02-110">Issue description</span></span>

<span data-ttu-id="7fb02-111">Domyślnie automatycznie generowane numery wierszy zamówień zakupu, które są importowane za pomocą jednostki danych *Wiersze zamówienia zakupu V2*, nie używaj przyrostu numeru wiersza systemowego określonego w parametrach systemowych.</span><span class="sxs-lookup"><span data-stu-id="7fb02-111">By default, automatically generated line numbers for purchase order lines that are imported through the *Purchase order lines V2* data entity don't use the system line number increment that is specified in system parameters.</span></span> <span data-ttu-id="7fb02-112">Jeśli ręcznie utworzysz zamówienie zakupu i dodasz wiersze za pośrednictwem interfejsu użytkownika (UI), numery wierszy zostaną poprawnie zwiększone.</span><span class="sxs-lookup"><span data-stu-id="7fb02-112">If you manually create a purchase order and add lines through the user interface (UI), the line numbers are incremented correctly.</span></span> <span data-ttu-id="7fb02-113">Jeśli jednak używasz struktury zarządzania danymi (DMF), nie są one poprawnie zwiększane.</span><span class="sxs-lookup"><span data-stu-id="7fb02-113">However, if you use the Data management framework (DMF), they aren't incremented correctly.</span></span>

<span data-ttu-id="7fb02-114">Ten problem występuje, ponieważ podczas importowania wierszy przez DMF, jeśli numery wierszy nie są jeszcze przypisane w importowanej encji, system używa metody DMF do ich przypisywania.</span><span class="sxs-lookup"><span data-stu-id="7fb02-114">This issue occurs because, when you import lines via DMF, if line numbers aren't already assigned in the imported entity, the system uses DMF's method for assigning them.</span></span> <span data-ttu-id="7fb02-115">Ta metoda zawsze zwiększa liczbę wierszy o jeden.</span><span class="sxs-lookup"><span data-stu-id="7fb02-115">That method always increments line numbers by one.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="7fb02-116">Obejście problemu</span><span class="sxs-lookup"><span data-stu-id="7fb02-116">Issue workaround</span></span>

<span data-ttu-id="7fb02-117">Upewnij się, że żądane numery wierszy są już podane w polach numeru wiersza jednostki danych podczas importowania wierszy zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-117">Make sure that the desired line numbers are already given in the data entity line number fields when you import the purchase order lines.</span></span> <span data-ttu-id="7fb02-118">W takim przypadku DMF nie zastąpi numerów wierszy.</span><span class="sxs-lookup"><span data-stu-id="7fb02-118">In this case, DMF won't overwrite the line numbers.</span></span>

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a><span data-ttu-id="7fb02-119">Domyślna grupa podatków i domyślny rabat gotówkowy nie są wypełniane na podstawie konta płatnika.</span><span class="sxs-lookup"><span data-stu-id="7fb02-119">A default tax group and a default cash discount aren't filled in from the invoice account.</span></span>

<span data-ttu-id="7fb02-120">Jeśli używasz konta faktury, które różni się od konta odbiorcy, domyślna grupa podatkowa i domyślny rabat gotówkowy nie są wypełniane z konta faktury podczas tworzenia zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-120">If you're using an invoice account that differs from the customer account, a default tax group and a default cash discount aren't filled in from the invoice account when a purchase order is created.</span></span>

<span data-ttu-id="7fb02-121">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="7fb02-121">This behavior is by design.</span></span> <span data-ttu-id="7fb02-122">Domyślne wartości grupy podatków, rabatów gotówkowych i innych informacji o cenie są oparte na koncie odbiorcy, a nie na koncie faktury.</span><span class="sxs-lookup"><span data-stu-id="7fb02-122">The default values for the tax group, cash discounts, and other price information are based on the customer account, not the invoice account.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="7fb02-123">Otrzymuję komunikat o błędzie „Nie ustawiono odwołania do obiektu” podczas potwierdzania zamówienia zakupu lub podczas księgowania faktury od dostawcy zgłoszony został wyjątek „Obiekt docelowy wywołania” zgłosił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="7fb02-123">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="7fb02-124">Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-124">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="7fb02-125">Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="7fb02-125">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="7fb02-126">Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="7fb02-126">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="7fb02-127">Co najmniej jedna dystrybucja księgowa jest rozproszona lub niepełna.</span><span class="sxs-lookup"><span data-stu-id="7fb02-127">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7fb02-128">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="7fb02-128">Issue description</span></span>

<span data-ttu-id="7fb02-129">Pojawia się następujący błąd: „Co najmniej jedna dystrybucja rozliczeń jest rozprowadzana nadmiernie lub niedostatecznie dystrybuowana”.</span><span class="sxs-lookup"><span data-stu-id="7fb02-129">You receive the following error: "One or more accounting distributions is either over-distributed or under-distributed."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7fb02-130">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="7fb02-130">Issue resolution</span></span>

<span data-ttu-id="7fb02-131">Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-131">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="7fb02-132">Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="7fb02-132">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="7fb02-133">Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="7fb02-133">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="can-i-show-only-purchase-orders-that-i-created"></a><span data-ttu-id="7fb02-134">Czy mogę wyświetlić utworzone przeze mnie zamówienia zakupu?</span><span class="sxs-lookup"><span data-stu-id="7fb02-134">Can I show only purchase orders that I created?</span></span>

<span data-ttu-id="7fb02-135">Ta funkcja jest obecnie niedostępna.</span><span class="sxs-lookup"><span data-stu-id="7fb02-135">This functionality isn't currently available.</span></span>

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a><span data-ttu-id="7fb02-136">Czy mogę zarezerwować zapasy i utworzyć transakcje dla zarejestrowanych zapasów w zamówieniu zakupu?</span><span class="sxs-lookup"><span data-stu-id="7fb02-136">Can I reserve inventory and create transactions against registered inventory on a purchase order?</span></span>

### <a name="issue-description"></a><span data-ttu-id="7fb02-137">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="7fb02-137">Issue description</span></span>

<span data-ttu-id="7fb02-138">Nawet jeśli towary znajdują się w stanie *Zarejestrowano* zamówienia zakupu, nadal można zarezerwować zapasy.</span><span class="sxs-lookup"><span data-stu-id="7fb02-138">Even when items are in a *Registered* state on a purchase order, you can still reserve the inventory.</span></span> <span data-ttu-id="7fb02-139">Innymi słowy, transakcje można tworzyć na podstawie zarejestrowanych zapasów.</span><span class="sxs-lookup"><span data-stu-id="7fb02-139">In other words, you can create transactions against the registered inventory.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="7fb02-140">Odtwórz ten błąd</span><span class="sxs-lookup"><span data-stu-id="7fb02-140">Reproduce the issue</span></span>

<span data-ttu-id="7fb02-141">Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-141">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="7fb02-142">Umożliwia tworzenie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-142">Create a purchase order.</span></span>
2. <span data-ttu-id="7fb02-143">Zarejestruj wiersz zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-143">Register the purchase order line.</span></span>
3. <span data-ttu-id="7fb02-144">Zauważ, że można generować rezerwacje lub transakcje dla zarejestrowanych zapasów.</span><span class="sxs-lookup"><span data-stu-id="7fb02-144">Notice that you can generate reservations or transactions against the registered inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7fb02-145">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="7fb02-145">Issue resolution</span></span>

<span data-ttu-id="7fb02-146">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="7fb02-146">This behavior is by design.</span></span> <span data-ttu-id="7fb02-147">Oczekuje się, że zarejestrowane towary zostały fizycznie odebrane w magazynie lub zapasach i dlatego są one dostępne do rezerwacji.</span><span class="sxs-lookup"><span data-stu-id="7fb02-147">The expectation is that the registered items have physically arrived in the warehouse or inventory, and that they are therefore available for reservation.</span></span>

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a><span data-ttu-id="7fb02-148">Zamówienia zakupu nie odzwierciedlają ustawień języka firmy.</span><span class="sxs-lookup"><span data-stu-id="7fb02-148">Purchase orders don't reflect the language settings of the legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7fb02-149">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="7fb02-149">Issue description</span></span>

<span data-ttu-id="7fb02-150">Nazwa produktu w zamówieniu zakupu jest wyświetlana w wersji językowej systemu, a nie w języku określonym dla firmy, w której utworzono zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-150">The product name on a purchase order is shown in the system language instead of the language that is set for the legal entity where the purchase order was created.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="7fb02-151">Odtwórz ten błąd</span><span class="sxs-lookup"><span data-stu-id="7fb02-151">Reproduce the issue</span></span>

<span data-ttu-id="7fb02-152">Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-152">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="7fb02-153">Określ język systemowy jako *EN-US* (Język angielski Stany Zjednoczone).</span><span class="sxs-lookup"><span data-stu-id="7fb02-153">Set the system language to *EN-US* (US English).</span></span>
1. <span data-ttu-id="7fb02-154">Upewnij się, że istnieje produkt, w którym obsługiwane są języki *EN-US* i *DE* (Niemiecki) dla tłumaczeń nazw produktów.</span><span class="sxs-lookup"><span data-stu-id="7fb02-154">Make sure that there is a product where the *EN-US* and *DE* (German) languages are maintained for translations of the product name.</span></span>
1. <span data-ttu-id="7fb02-155">Zmień język firmy na *DE*.</span><span class="sxs-lookup"><span data-stu-id="7fb02-155">Change the language of a legal entity to *DE*.</span></span>
1. <span data-ttu-id="7fb02-156">W firmie, w której jako język jest ustawiona wartość *DE*, utwórz zamówienie zakupu zawierające produkt.</span><span class="sxs-lookup"><span data-stu-id="7fb02-156">In the legal entity where *DE* is set as the language, create a purchase order that includes the product.</span></span>
1. <span data-ttu-id="7fb02-157">Zauważ, że nazwa produktu nadal jest wyświetlana w języku angielskim, USA (język systemowy).</span><span class="sxs-lookup"><span data-stu-id="7fb02-157">Notice that the product name is still shown in US English (the system language).</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7fb02-158">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="7fb02-158">Issue resolution</span></span>

<span data-ttu-id="7fb02-159">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="7fb02-159">This behavior is by design.</span></span> <span data-ttu-id="7fb02-160">W przypadku zamówień zakupu produkt jest zawsze pokazywany w wersji językowej systemu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-160">On purchase orders, the product is always shown in the system language.</span></span> <span data-ttu-id="7fb02-161">Język zamówienia zakupu jest używany podczas tworzenia arkusza potwierdzeń.</span><span class="sxs-lookup"><span data-stu-id="7fb02-161">The purchase order language is used when a confirmation journal is created.</span></span>

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a><span data-ttu-id="7fb02-162">Lista zatwierdzonych dostawców według jednostki produktu nie zezwala na zmianę daty wprowadzenia.</span><span class="sxs-lookup"><span data-stu-id="7fb02-162">The Approved vendor list by product entity doesn't allow the effective date to be changed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7fb02-163">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="7fb02-163">Issue description</span></span>

<span data-ttu-id="7fb02-164">Produkt ma zatwierdzonego dostawcę, który ma na przykład datę wejścia w życie 11 stycznia 2018 r. (*11/01/2018*) i datę ważności *Nigdy*.</span><span class="sxs-lookup"><span data-stu-id="7fb02-164">A product has an approved vendor that has, for example, an effective date of January 11, 2018 (*01/11/2018*), and an expiration date of *Never*.</span></span> <span data-ttu-id="7fb02-165">Próba zmiany daty rozpoczęcia na 10 stycznia 2018 (*10/01/2018*) lub 12 stycznia 2018 (*12/01/2018*) powoduje wyświetlenie następującego błędu:</span><span class="sxs-lookup"><span data-stu-id="7fb02-165">If you try to change the effective date to January 10, 2018 (*01/10/2018*), or January 12, 2018 (*01/12/2018*), you receive the following error:</span></span>

> <span data-ttu-id="7fb02-166">Nie można utworzyć rekordu na liście zatwierdzonych dostawców (PdsApproveVendorList).</span><span class="sxs-lookup"><span data-stu-id="7fb02-166">Cannot create a record in Approved supplier list (PdsApproveVendorList).</span></span> <span data-ttu-id="7fb02-167">Wartość „Data ważności” musi być większa lub równa wartości „Data wejścia w życie”.</span><span class="sxs-lookup"><span data-stu-id="7fb02-167">The 'Expiration' value needs to be greater than or equal to the 'Effective' value.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7fb02-168">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="7fb02-168">Issue resolution</span></span>

<span data-ttu-id="7fb02-169">Można wydłużyć okres, dla którego dostawca został zatwierdzony.</span><span class="sxs-lookup"><span data-stu-id="7fb02-169">You can only extend the period that the vendor is approved for.</span></span> <span data-ttu-id="7fb02-170">Obowiązują następujące zasady:</span><span class="sxs-lookup"><span data-stu-id="7fb02-170">The following rules apply:</span></span>

- <span data-ttu-id="7fb02-171">Aby zmienić datę wejścia w życie, tak aby była wcześniejsza niż jakikolwiek z istniejących rekordów (okresów) dla dostawcy towaru, data wygaśnięcia nowego okresu musi być wcześniejsza niż wszystkie daty wygaśnięcia w istniejących rekordach.</span><span class="sxs-lookup"><span data-stu-id="7fb02-171">To change the effective date so that it's earlier than any of the existing records (periods) for the item vendor, the expiration date of the new period must be before all the expiration dates in the existing records.</span></span>
- <span data-ttu-id="7fb02-172">Aby zmienić datę wygaśnięcia, tak aby była późniejsza niż jakikolwiek z istniejących okresów, data wejścia w życie musi być późniejsza niż ostatnia data wygaśnięcia dowolnego istniejącego rekordu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-172">To change the expiration date so that it's later than any of the existing periods, the effective date must be after the latest expiration date in any existing record.</span></span>
- <span data-ttu-id="7fb02-173">Aby skrócić cały okres, do którego dostawca jest zatwierdzony, należy usunąć lub zmodyfikować istniejące rekordy.</span><span class="sxs-lookup"><span data-stu-id="7fb02-173">To reduce the overall period that the vendor is approved for, you must delete or modify existing records.</span></span> <span data-ttu-id="7fb02-174">Alternatywnie można skorzystać z przełącznika **obcinania** podczas importu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-174">Alternatively, you can use the **truncate** switch during import.</span></span> <span data-ttu-id="7fb02-175">Ten przełącznik powoduje usunięcie wszystkich istniejących rekordów z tabeli dla zatwierdzonych dostawców według towarów.</span><span class="sxs-lookup"><span data-stu-id="7fb02-175">This switch deletes all existing records in the table for approved vendors by item.</span></span>

<span data-ttu-id="7fb02-176">W przykładzie scenariusza opisanego w opisie zagadnienia, gdy rekord ma datę wejścia w życie *11/01/2018* oraz datę ważności *Nigdy*, można zaimportować nowy rekord z datą wejścia w życie *10/01/2018* oraz datę ważności *Nigdy*.</span><span class="sxs-lookup"><span data-stu-id="7fb02-176">For the example scenario that is described in the issue description, where a record has an effective date of *01/11/2018* and an expiration date of *Never*, you can import a new record that has an effective date of *01/10/2018* and an expiration date of *Never*.</span></span> <span data-ttu-id="7fb02-177">Nie można jednak skrócić okresu, tak aby Data wejścia w życie była aktualizowana do *12/01/2018* za pomocą funkcji zarządzania danymi.</span><span class="sxs-lookup"><span data-stu-id="7fb02-177">However, you can't reduce the period so that the effective date is updated to *01/12/2018* via data management.</span></span> <span data-ttu-id="7fb02-178">Tę zmianę należy wprowadzić w interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7fb02-178">You must make this change through the UI.</span></span>

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-nameisnt-synced"></a><span data-ttu-id="7fb02-179">Po zmianie adresu dostawy w nagłówku zamówienia zakupu nazwa dostawy nie jest synchronizowana.</span><span class="sxs-lookup"><span data-stu-id="7fb02-179">After I change the delivery address on a purchase order header, the delivery name isn't synced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7fb02-180">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="7fb02-180">Issue description</span></span>

<span data-ttu-id="7fb02-181">Adres w nagłówku zamówienia zakupu jest aktualizowany na adres, który nie jest adresem dostawy.</span><span class="sxs-lookup"><span data-stu-id="7fb02-181">The address on the header of a purchase order is updated to an address that isn't a delivery address.</span></span> <span data-ttu-id="7fb02-182">Mimo że adres jest aktualizowany na zamówieniu zakupu, nazwa dostawy nie jest aktualizowana na podstawie zaktualizowanego adresu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-182">Although the address is updated on the purchase order, the delivery name isn't updated based on the updated address.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7fb02-183">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="7fb02-183">Issue resolution</span></span>

<span data-ttu-id="7fb02-184">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="7fb02-184">This behavior is by design.</span></span> <span data-ttu-id="7fb02-185">Wybrany adres musi być klasyfikowany jako adres dostawy.</span><span class="sxs-lookup"><span data-stu-id="7fb02-185">The selected address must be classified as a delivery address.</span></span> <span data-ttu-id="7fb02-186">W przeciwnym razie nazwa dostawy nie zostanie zaktualizowana na podstawie wybranego adresu.</span><span class="sxs-lookup"><span data-stu-id="7fb02-186">Otherwise, the delivery name isn't updated based on the selected address.</span></span>

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a><span data-ttu-id="7fb02-187">Czy mogę znaleźć użytkownika, który anulował zamówienie zakupu?</span><span class="sxs-lookup"><span data-stu-id="7fb02-187">Can I find the user who canceled a purchase order?</span></span>

<span data-ttu-id="7fb02-188">Te informacje są śledzone tylko wtedy, gdy zamówienie zakupu podlega zarządzaniu zmianami.</span><span class="sxs-lookup"><span data-stu-id="7fb02-188">This information is tracked only if the purchase order is subject to change management.</span></span> <span data-ttu-id="7fb02-189">W przypadku korzystania z zarządzania zmianami można sprawdzić, kto przesłał tę zmianę (anulowanie) i, kto ją zatwierdził.</span><span class="sxs-lookup"><span data-stu-id="7fb02-189">If you use change management, you can see who submitted the change (the cancellation), and who approved it.</span></span>
