---
title: Rozwiązywanie problemów z cenami, promocjami, umowami i rabatami
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z cenami, promocjami, umowami i rabatami.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 14fdddabde7739cbf9ba0fcee0fa0b8b816e74dd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007373"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a><span data-ttu-id="976a1-103">Rozwiązywanie problemów z cenami, promocjami, umowami i rabatami</span><span class="sxs-lookup"><span data-stu-id="976a1-103">Troubleshoot prices, discounts, agreements, and rebates</span></span>

<span data-ttu-id="976a1-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z cenami, promocjami, umowami i rabatami.</span><span class="sxs-lookup"><span data-stu-id="976a1-104">This topic describes how to fix issues that you might encounter while you work with prices, discounts, agreements, and rebates.</span></span>

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a><span data-ttu-id="976a1-105">Nie można połączyć umowy zakupu z wierszem zamówienia zakupu po utworzeniu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-105">I can't link a purchase agreement to a purchase order line after the purchase order is created.</span></span>

<span data-ttu-id="976a1-106">Umowa zakupu musi być powiązana z zamówieniem podczas tworzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="976a1-106">A purchase agreement must be associated with a purchase order when the purchase order is created.</span></span> <span data-ttu-id="976a1-107">W przeciwnym razie wiersze zamówienia zakupu nie mogą być kojarzone z wierszami umowy zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-107">Otherwise, purchase order lines can't be associated with purchase agreement lines.</span></span>

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a><span data-ttu-id="976a1-108">Jaki czek powoduje wyświetlenie komunikatu „Zaktualizuj ceny i rabaty wprowadzone ręcznie lub na zewnętrznym dokumencie”?</span><span class="sxs-lookup"><span data-stu-id="976a1-108">What check triggers the "Update prices and discounts entered manually or external document" message?</span></span>

<span data-ttu-id="976a1-109">Po zmianie daty wysyłki może pojawić się komunikat „Zaktualizuj ceny i rabaty wprowadzone ręcznie lub dokument zewnętrzny”.</span><span class="sxs-lookup"><span data-stu-id="976a1-109">When you change the shipping date, you might receive a message that states, "Update prices and discounts entered manually or external document."</span></span> <span data-ttu-id="976a1-110">Ten komunikat jest wyświetlany, ponieważ w przypadku zmiany daty wysyłki może zostać wyzwolona inna umowa handlowa lub handlowa i spowodować zmianę ceny.</span><span class="sxs-lookup"><span data-stu-id="976a1-110">You receive this message because, if the shipping date is changed, a different trade or sales agreement might be triggered and cause a price change.</span></span> <span data-ttu-id="976a1-111">Zmiana daty wysyłki może również wpłynąć na harmonogramy magazynów i inne powiązane informacje.</span><span class="sxs-lookup"><span data-stu-id="976a1-111">A change to the shipping date can also affect warehouse schedules and other related information.</span></span>

<span data-ttu-id="976a1-112">Komunikat jest wyzwalany po każdej zmianie którejkolwiek z dat lub innych parametrów.</span><span class="sxs-lookup"><span data-stu-id="976a1-112">The message is triggered whenever any of the dates or some other parameters are changed.</span></span> <span data-ttu-id="976a1-113">Komunikat ma na celu upewnienie się, że użytkownik wie o zmianach cen, które mogą nastąpić z powodu tych zmian.</span><span class="sxs-lookup"><span data-stu-id="976a1-113">The purpose of the message is to make sure that you're aware of price changes that can occur because of those changes.</span></span>

<span data-ttu-id="976a1-114">Komunikat jest monitem o ocenę umowy handlowej (TAE).</span><span class="sxs-lookup"><span data-stu-id="976a1-114">The message is the trade agreement evaluation (TAE) prompt.</span></span> <span data-ttu-id="976a1-115">Aby uzyskać pełny opis, zajrzyj do [Zasady oceny umów handlowych](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span><span class="sxs-lookup"><span data-stu-id="976a1-115">For a full description, see [Trade agreement evaluation policies](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span></span>

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a><span data-ttu-id="976a1-116">Przyjęcie zamówienia zakupu nie obejmuje wszystkich opłat.</span><span class="sxs-lookup"><span data-stu-id="976a1-116">A purchase order receipt doesn't include all charges.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="976a1-117">Odtwórz ten błąd</span><span class="sxs-lookup"><span data-stu-id="976a1-117">Reproduce the issue</span></span>

<span data-ttu-id="976a1-118">Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.</span><span class="sxs-lookup"><span data-stu-id="976a1-118">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="976a1-119">Na stronie **Parametry modułu Zaopatrzenie i sourcing** na karcie **Dostawa** upewnij się, że opcja **Generuj opłaty przy odbiorze produktu** jest ustawiona na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="976a1-119">On the **Procurement and sourcing parameters** page, on the **Delivery** tab, make sure that the **Generate charges on product receipt** option is set to *Yes*.</span></span>
1. <span data-ttu-id="976a1-120">Tworzenie zamówienia zakupu, które zawiera zmiany.</span><span class="sxs-lookup"><span data-stu-id="976a1-120">Create a purchase order that includes charges.</span></span>
1. <span data-ttu-id="976a1-121">Potwierdź zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-121">Confirm the purchase order.</span></span>
1. <span data-ttu-id="976a1-122">Odbiór zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-122">Receive the purchase order.</span></span>
1. <span data-ttu-id="976a1-123">Spójrz na sumę przychodu i porównaj ją z oczekiwaną sumą.</span><span class="sxs-lookup"><span data-stu-id="976a1-123">Look at the receipt total, and compare it to the expected total.</span></span>
1. <span data-ttu-id="976a1-124">Zauważ, że nie wszystkie opłaty są uwzględniane w przyjęciu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-124">Notice that not all the charges are included on the purchase order receipt.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="976a1-125">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="976a1-125">Issue resolution</span></span>

<span data-ttu-id="976a1-126">Rozwiązanie to zależy od sposobu, w jaki skonfigurowano opłaty dodatkowe.</span><span class="sxs-lookup"><span data-stu-id="976a1-126">The resolution depends on the way that the miscellaneous charges have been set up.</span></span> <span data-ttu-id="976a1-127">Aby uzyskać informacje o tym, jak skonfigurować różne opłaty, aby spełnić Twoje wymagania, zobacz następujący wpis na blogu: [Księguj różne opłaty w momencie przyjęcia produktów](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="976a1-127">For information about how to set up miscellaneous charges to meet your requirements, see the following blog post: [Post misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a><span data-ttu-id="976a1-128">Ceny i rabaty umowy handlowej nie są stosowane w wierszach sprzedaży lub zamówienia zakupu, które są importowane za pomocą zarządzania danymi.</span><span class="sxs-lookup"><span data-stu-id="976a1-128">Trade agreement prices and discounts aren't applied on sales or purchase order lines that are imported through data management.</span></span>

### <a name="issue-description"></a><span data-ttu-id="976a1-129">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="976a1-129">Issue description</span></span>

<span data-ttu-id="976a1-130">Umowy handlowe, które mają zastosowanie do wierszy sprzedaży lub zamówienia zakupu, nie są stosowane w wierszach importowanych za pomocą funkcji zarządzania danymi.</span><span class="sxs-lookup"><span data-stu-id="976a1-130">Trade agreements that are applicable to sales or purchase order lines aren't applied on lines that are imported through data management.</span></span> <span data-ttu-id="976a1-131">Jednak te same umowy handlowe są stosowane do wierszy sprzedaży lub zamówienia zakupu, które są tworzone ręcznie.</span><span class="sxs-lookup"><span data-stu-id="976a1-131">However, the same trade agreements are applied on sales or purchase order lines that are manually created.</span></span>

### <a name="reason-for-the-issue"></a><span data-ttu-id="976a1-132">Przyczyna problemu</span><span class="sxs-lookup"><span data-stu-id="976a1-132">Reason for the issue</span></span>

<span data-ttu-id="976a1-133">Jeśli wiersze zamówienia zakupu, które są importowane za pomocą zarządzania danymi, zawierają już informacje o cenie, umowa handlowa nie zostanie ponownie oszacowana dla tych wierszy.</span><span class="sxs-lookup"><span data-stu-id="976a1-133">If purchase order lines that are imported via data management already include price information, the trade agreement won't be reevaluated for those lines.</span></span> <span data-ttu-id="976a1-134">Na przykład, jeśli **Procent rabatu dla wiersza** lub jakakolwiek cena i wartość rabatu jest ustawiona dla wiersza, umowy handlowe nie będą wyszukiwane dla tego wiersza.</span><span class="sxs-lookup"><span data-stu-id="976a1-134">For example, if **Line discount percentage** or any of the price and discount values is set for a line, then trade agreements will not be looked up for that line.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="976a1-135">Obejście problemu</span><span class="sxs-lookup"><span data-stu-id="976a1-135">Issue workaround</span></span>

<span data-ttu-id="976a1-136">Takie zachowanie jest oczekiwane i podobne zarówno do zamówień sprzedaży, jak i zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-136">This behavior is expected, and is similar for both sales orders and purchase orders.</span></span>

<span data-ttu-id="976a1-137">Jako rozwiązanie alternatywne należy zaimportować wiersze zamówienia zakupu bez ustawiania żadnych informacji o cenach.</span><span class="sxs-lookup"><span data-stu-id="976a1-137">As a workaround, import the purchase order lines without setting any price information.</span></span> <span data-ttu-id="976a1-138">Następnie zostaną zastosowane umowy handlowe, a wiersze zamówienia zakupu zostaną zaktualizowane na podstawie zdefiniowanych umów handlowych.</span><span class="sxs-lookup"><span data-stu-id="976a1-138">The trade agreements will then be applied, and the purchase order lines will be updated based on the defined trade agreements.</span></span>

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a><span data-ttu-id="976a1-139">Rabat dostawcy nie jest kumulowany na podstawie faktur.</span><span class="sxs-lookup"><span data-stu-id="976a1-139">A vendor rebate isn't cumulated based on invoices.</span></span>

### <a name="issue-description"></a><span data-ttu-id="976a1-140">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="976a1-140">Issue description</span></span>

<span data-ttu-id="976a1-141">Jeśli faktury, które zostały zaksięgowane, mają różne terminy płatności, te faktury nie są uwzględniane w wygenerowanych rabatach dostawców.</span><span class="sxs-lookup"><span data-stu-id="976a1-141">If invoices that are posted have different due dates, those invoices aren't reflected in vendor rebates that are generated from them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="976a1-142">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="976a1-142">Issue resolution</span></span>

<span data-ttu-id="976a1-143">Zgodnie z projektem termin płatności nie jest brany pod uwagę przy obliczaniu rabatu dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="976a1-143">By design, the due date isn't considered when the vendor rebate is calculated.</span></span> <span data-ttu-id="976a1-144">Rozważ dostosowanie systemu, tak aby termin płatności i związek z fakturą były bardziej widoczne w odniesieniu do faktycznego rabatu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="976a1-144">Consider customizing the system so that the due date and the relation to the invoice are more apparent with respect to the actual vendor rebate.</span></span>

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a><span data-ttu-id="976a1-145">Ceny jednostkowe w zamówieniach zakupu nie są obliczane na podstawie konwersji jednostek.</span><span class="sxs-lookup"><span data-stu-id="976a1-145">Unit prices on purchase orders aren't calculated based on the unit conversion.</span></span>

### <a name="issue-description"></a><span data-ttu-id="976a1-146">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="976a1-146">Issue description</span></span>

<span data-ttu-id="976a1-147">Po zmianie jednostki w zamówieniu zakupu ceny umowy handlowej nie są ponownie obliczane zgodnie z definicjami konwersji jednostek.</span><span class="sxs-lookup"><span data-stu-id="976a1-147">When a unit is changed on a purchase order, trade agreement prices aren't recalculated according to unit conversion definitions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="976a1-148">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="976a1-148">Issue resolution</span></span>

<span data-ttu-id="976a1-149">Ceny są zawsze uzyskiwane z umów handlowych (lub innych ustawień cen w systemie, takich jak umowy sprzedaży lub ceny towarów) i są ustalane dla jednostki.</span><span class="sxs-lookup"><span data-stu-id="976a1-149">Prices are always obtained from trade agreements (or other price settings in the system, such as sales agreements or item prices), and they are set for a unit.</span></span>

<span data-ttu-id="976a1-150">Jeśli jednostka została zmieniona w wierszu zamówienia, system wyszukuje cenę nowej jednostki i stosuje tę cenę.</span><span class="sxs-lookup"><span data-stu-id="976a1-150">If the unit is changed on an order line, the system looks for a price for the new unit and applies that price.</span></span> <span data-ttu-id="976a1-151">Jeśli dla jednostki nie zostanie znaleziona żadna cena, system nie zastosuje ceny.</span><span class="sxs-lookup"><span data-stu-id="976a1-151">If no price is found for the unit, the system doesn't apply a price.</span></span> <span data-ttu-id="976a1-152">Konwersji jednostek nie można użyć do przeliczenia ceny na inną jednostkę.</span><span class="sxs-lookup"><span data-stu-id="976a1-152">The unit conversion can't be used to recalculate the price into another unit.</span></span> <span data-ttu-id="976a1-153">Teoretycznie cena jednego pola o wartości 10 może nie być równa dziesięć razy więcej niż cena jednego pola.</span><span class="sxs-lookup"><span data-stu-id="976a1-153">Theoretically, the price for one box of ten might not equal ten times the price of one box.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="976a1-154">Obejście problemu</span><span class="sxs-lookup"><span data-stu-id="976a1-154">Issue workaround</span></span>

<span data-ttu-id="976a1-155">Jednym ze sposobów obejścia tego problemu jest zagwarantowanie, że istnieją umowy handlowe dla oczekiwanych jednostek, które będą używane w wierszach zamówień dla towaru.</span><span class="sxs-lookup"><span data-stu-id="976a1-155">One way to work around this issue is to make sure that there are trade agreements for the units that you expect will be used on order lines for the item.</span></span>

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a><span data-ttu-id="976a1-156">Problemy z konwersją walut występują w umowach handlowych.</span><span class="sxs-lookup"><span data-stu-id="976a1-156">Currency conversion issues occur with trade agreements.</span></span>

<span data-ttu-id="976a1-157">Ceny w umowach handlowych nie są przeliczane zgodnie z walutą, jeśli waluta jest inna w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-157">Trade agreement prices aren't recalculated according to the currency when the currency differs on a purchase order.</span></span>

<span data-ttu-id="976a1-158">Funkcja *Waluty ogólnej* umożliwia definiowanie cen i rabatów tylko w jednej walucie.</span><span class="sxs-lookup"><span data-stu-id="976a1-158">The *Generic currency* feature lets you define prices and discounts in only one currency.</span></span> <span data-ttu-id="976a1-159">Następnie można dokonać konwersji na inne waluty w razie konieczności.</span><span class="sxs-lookup"><span data-stu-id="976a1-159">You can then convert to other currencies as you require.</span></span> <span data-ttu-id="976a1-160">Ponadto po zakończeniu konwersji funkcja może automatycznie stosować przyjazne zaokrąglanie.</span><span class="sxs-lookup"><span data-stu-id="976a1-160">Furthermore, after the conversion is done, the feature can automatically apply smart rounding.</span></span>

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a><span data-ttu-id="976a1-161">Kiedy otwieram stronę Umowa zakupu w trybie widoku liniowego, nie mogę spersonalizować strony, dodając pole Jednostka ceny w przeglądzie wiersza.</span><span class="sxs-lookup"><span data-stu-id="976a1-161">When I open the Purchase agreement page in a line view mode, I can't personalize the page by adding the Price unit field in the overview of the line.</span></span>

<span data-ttu-id="976a1-162">W personalizacjach nie można dołączać niektórych pól udostępnionych w strukturze umowy.</span><span class="sxs-lookup"><span data-stu-id="976a1-162">Some shared fields in the agreement framework can't be included in personalizations.</span></span> <span data-ttu-id="976a1-163">To ograniczenie występuje z powodu zaimplementowanego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="976a1-163">This limitation occurs because of the data model that is implemented.</span></span> <span data-ttu-id="976a1-164">Nie można więc personalizować pola **Jednostka cenowa**.</span><span class="sxs-lookup"><span data-stu-id="976a1-164">Therefore, you can't personalize the **Price unit** field.</span></span>

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a><span data-ttu-id="976a1-165">Maksymalny limit z umowy zakupu nie obowiązuje w zapotrzebowaniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-165">The maximum limit from a purchase agreement isn't effective on a purchase requisition.</span></span>

### <a name="issue-description"></a><span data-ttu-id="976a1-166">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="976a1-166">Issue description</span></span>

<span data-ttu-id="976a1-167">Jeśli zapotrzebowanie zakupu jest połączone z umową zakupu, maksymalny limit z umowy zakupu nie obowiązuje w zapotrzebowaniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-167">When a purchase requisition is linked to a purchase agreement, the maximum limit from the purchase agreement isn't effective on the purchase requisition.</span></span> <span data-ttu-id="976a1-168">Domyślne informacje o cenie są wprowadzane poprawnie, ale więcej niż maksymalny limit z umowy zakupu może zostać zamówiony w zapotrzebowaniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-168">The default price information is correctly entered, but more than the maximum limit from the purchase agreement can be ordered in the purchase requisition.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="976a1-169">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="976a1-169">Issue resolution</span></span>

<span data-ttu-id="976a1-170">To zachowanie jest oczekiwane.</span><span class="sxs-lookup"><span data-stu-id="976a1-170">This behavior is expected.</span></span> <span data-ttu-id="976a1-171">Zapotrzebowania nie zawsze są zatwierdzane, więc ilość lub kwota nie powinna być rezerwowana w umowie zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-171">Because requisitions aren't always approved, a quantity or amount should not be reserved on the purchase agreement.</span></span> <span data-ttu-id="976a1-172">Z tego powodu nie będzie można spełnić limitu maksymalnego z umowy zakupu.</span><span class="sxs-lookup"><span data-stu-id="976a1-172">Therefore, you won't meet the maximum limit from the purchase agreement.</span></span>

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a><span data-ttu-id="976a1-173">Umowy handlowe można tworzyć na podstawie odrzuconych zapytań ofertowych.</span><span class="sxs-lookup"><span data-stu-id="976a1-173">Trade agreements can be created from rejected RFQs.</span></span> <span data-ttu-id="976a1-174">Dlatego system nie zapobiega tworzeniu arkuszy umów handlowych, jeśli wiersz ZO nie został zaakceptowany.</span><span class="sxs-lookup"><span data-stu-id="976a1-174">Therefore, the system doesn't prevent trade agreement journals from being created if the RFQ line hasn't been accepted.</span></span>

<span data-ttu-id="976a1-175">Możesz tworzyć umowy handlowe dla dowolnych odpowiedzi na zapytanie ofertowe (ZO), niezależnie od tego, czy zostały zaakceptowane, czy odrzucone.</span><span class="sxs-lookup"><span data-stu-id="976a1-175">You can create trade agreements for any replies for a request for quotation (RFQ), regardless of whether they were accepted or rejected.</span></span> <span data-ttu-id="976a1-176">Aby uzyskać więcej informacji, zobacz [Omówienie zapytań ofertowych (ZO)](request-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="976a1-176">For more information, see [Requests for quotation (RFQs) overview](request-quotations.md).</span></span>

