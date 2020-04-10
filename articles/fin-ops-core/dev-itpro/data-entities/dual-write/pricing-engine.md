---
title: Synchronizacja na żądanie z aparatem kalkulacji cen rozwiązania Dynamics 365 Supply Chain Management
description: W tym temacie opisano sposób używania aparatu kalkulacji cen w Microsoft Dynamics 365 Supply Chain Management z Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: ef4465144155130087b078f9f96911df38b62c41
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173184"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a><span data-ttu-id="cc521-103">Synchronizacja na żądanie z aparatem kalkulacji cen rozwiązania Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="cc521-103">Sync with the Dynamics 365 Supply Chain Management pricing engine on demand</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="cc521-104">Microsoft Dynamics 365 Supply Chain Management udostępnia aparat kalkulacji cen, który obsługuje umowy handlowe, cenniki, programy lojalnościowe dla klientów, promocje i rabaty.</span><span class="sxs-lookup"><span data-stu-id="cc521-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="cc521-105">Aparat cenowy używa złożonych reguł w celu określenia najlepszej ceny dla danej oferty lub zamówienia.</span><span class="sxs-lookup"><span data-stu-id="cc521-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="cc521-106">W przypadku korzystania z funkcji podwójnego odpisu na stronach oferta i zamówienie w Dynamics 365 Sales można stosować zarówno cenę statyczną, jak i aparat cenowy z Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cc521-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="cc521-107">Użycie aparatu cenowego z Supply Chain Management w Sales</span><span class="sxs-lookup"><span data-stu-id="cc521-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="cc521-108">W Sales przejdź do **Sales \> Zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="cc521-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="cc521-109">Wybierz **Nowy**, aby utworzyć nowe zamówienie lub wybierz istniejące zamówienie z listy **Moje zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="cc521-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="cc521-110">Dodaj nowy wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="cc521-110">Add a new order line.</span></span>
4. <span data-ttu-id="cc521-111">W przypadku tworzenia nowego zamówienia w okienku akcji wybierz opcję **Zamówienie cenowe**.</span><span class="sxs-lookup"><span data-stu-id="cc521-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="cc521-112">Jeśli aktualizujesz istniejące zamówienie, wybierz **Ponownie oblicz** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="cc521-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="cc521-113">Następujące pola są automatycznie wypełniane:</span><span class="sxs-lookup"><span data-stu-id="cc521-113">The following fields are automatically filled in:</span></span>

    + <span data-ttu-id="cc521-114">Szczegółowa ilość</span><span class="sxs-lookup"><span data-stu-id="cc521-114">Detail Amount</span></span>
    + <span data-ttu-id="cc521-115">Procent rabatu</span><span class="sxs-lookup"><span data-stu-id="cc521-115">Discount %</span></span>
    + <span data-ttu-id="cc521-116">Dyskonto</span><span class="sxs-lookup"><span data-stu-id="cc521-116">Discount</span></span>
    + <span data-ttu-id="cc521-117">Kwota przed frachtem</span><span class="sxs-lookup"><span data-stu-id="cc521-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="cc521-118">Kwota frachtu</span><span class="sxs-lookup"><span data-stu-id="cc521-118">Freight Amount</span></span>
    + <span data-ttu-id="cc521-119">Podatek całkowity</span><span class="sxs-lookup"><span data-stu-id="cc521-119">Total Tax</span></span>
    + <span data-ttu-id="cc521-120">Łączna kwota</span><span class="sxs-lookup"><span data-stu-id="cc521-120">Total Amount</span></span>

## <a name="how-it-works"></a><span data-ttu-id="cc521-121">Jak działa</span><span class="sxs-lookup"><span data-stu-id="cc521-121">How it works</span></span>

<span data-ttu-id="cc521-122">Po wybraniu **Zamówienia cenowego** w Sales funkcja **Sumy** na karcie **Zamówienie sprzedaży \> Widok** w Supply Chain Management jest wywoływana dla skojarzonego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cc521-122">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="cc521-123">Wartości w sumie zamówienia w Sales są używane do wypełniania odpowiednich pól w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cc521-123">The values in the order total in Sales are used to fill in the corresponding fields in Supply Chain Management.</span></span>

<span data-ttu-id="cc521-124">Jeśli suma zamówienia sprzedaży jest obliczana w Supply Chain Management, obliczenie ocenia istniejące umowy handlowe i umowy sprzedaży dla odbiorcy oraz produkty wymienione w zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cc521-124">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="cc521-125">Informacje te są używane do obliczania sum.</span><span class="sxs-lookup"><span data-stu-id="cc521-125">This information is used to calculate the totals.</span></span> <span data-ttu-id="cc521-126">W przypadku wybrania **Zamówienia cenowego** sprzedaż automatycznie odzwierciedla wszystkie ustawienia wykonane w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cc521-126">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="cc521-127">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="cc521-127">Limitations</span></span>

<span data-ttu-id="cc521-128">Po wypełnieniu pól w Sales obowiązują następujące ograniczenia:</span><span class="sxs-lookup"><span data-stu-id="cc521-128">When the fields in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="cc521-129">Konfigurowanie opłat i alokacji opłat w Supply Chain Management nie jest replikowane w Sales.</span><span class="sxs-lookup"><span data-stu-id="cc521-129">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="cc521-130">W przypadku cen nie są uwzględniane specjalne ceny detaliczne określone w polu **Kanał detaliczny** na stronie wiersz zamówienia sprzedaży w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cc521-130">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** field on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="cc521-131">Nie są brane pod uwagę rabaty zdefiniowane w sekcji **Zarządzania przydziałem handlowym** w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cc521-131">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>
