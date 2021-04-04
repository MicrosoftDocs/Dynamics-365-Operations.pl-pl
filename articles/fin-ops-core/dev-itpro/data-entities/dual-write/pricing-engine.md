---
title: Synchronizacja na żądanie z aparatem wyceny aplikacji Supply Chain Management
description: W tym temacie opisano sposób używania aparatu kalkulacji cen w Microsoft Dynamics 365 Supply Chain Management z Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: e2067e83d3f0c98e986873b8eaf1b817de912c0f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570147"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a><span data-ttu-id="f96a9-103">Synchronizacja na żądanie z aparatem wyceny aplikacji Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="f96a9-103">Sync on-demand with the Supply Chain Management pricing engine</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="f96a9-104">Microsoft Dynamics 365 Supply Chain Management udostępnia aparat kalkulacji cen, który obsługuje umowy handlowe, cenniki, programy lojalnościowe dla klientów, promocje i rabaty.</span><span class="sxs-lookup"><span data-stu-id="f96a9-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="f96a9-105">Aparat cenowy używa złożonych reguł w celu określenia najlepszej ceny dla danej oferty lub zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f96a9-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="f96a9-106">W przypadku korzystania z funkcji podwójnego odpisu na stronach oferta i zamówienie w Dynamics 365 Sales można stosować zarówno cenę statyczną, jak i aparat cenowy z Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f96a9-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="f96a9-107">Użycie aparatu cenowego z Supply Chain Management w Sales</span><span class="sxs-lookup"><span data-stu-id="f96a9-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="f96a9-108">W Sales przejdź do **Sales \> Zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="f96a9-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="f96a9-109">Wybierz **Nowy**, aby utworzyć nowe zamówienie lub wybierz istniejące zamówienie z listy **Moje zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="f96a9-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="f96a9-110">Dodaj nowy wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f96a9-110">Add a new order line.</span></span>
4. <span data-ttu-id="f96a9-111">W przypadku tworzenia nowego zamówienia w okienku akcji wybierz opcję **Zamówienie cenowe**.</span><span class="sxs-lookup"><span data-stu-id="f96a9-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="f96a9-112">Jeśli aktualizujesz istniejące zamówienie, wybierz **Ponownie oblicz** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="f96a9-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="f96a9-113">Następujące kolumny są automatycznie wypełniane:</span><span class="sxs-lookup"><span data-stu-id="f96a9-113">The following columns are automatically filled in:</span></span>

    + <span data-ttu-id="f96a9-114">Szczegółowa ilość</span><span class="sxs-lookup"><span data-stu-id="f96a9-114">Detail Amount</span></span>
    + <span data-ttu-id="f96a9-115">Procent rabatu</span><span class="sxs-lookup"><span data-stu-id="f96a9-115">Discount %</span></span>
    + <span data-ttu-id="f96a9-116">Dyskonto</span><span class="sxs-lookup"><span data-stu-id="f96a9-116">Discount</span></span>
    + <span data-ttu-id="f96a9-117">Kwota przed frachtem</span><span class="sxs-lookup"><span data-stu-id="f96a9-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="f96a9-118">Kwota frachtu</span><span class="sxs-lookup"><span data-stu-id="f96a9-118">Freight Amount</span></span>
    + <span data-ttu-id="f96a9-119">Podatek całkowity</span><span class="sxs-lookup"><span data-stu-id="f96a9-119">Total Tax</span></span>
    + <span data-ttu-id="f96a9-120">Łączna kwota</span><span class="sxs-lookup"><span data-stu-id="f96a9-120">Total Amount</span></span>
    
5. <span data-ttu-id="f96a9-121">Aby upewnić się, że system traktuje umowy handlowe i sprzedaży w celu obliczenia ceny:</span><span class="sxs-lookup"><span data-stu-id="f96a9-121">To ensure that the system considers trade and sales agreements to calculate the price:</span></span>
    1. <span data-ttu-id="f96a9-122">Przejdź do środowiska Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f96a9-122">Navigate to your Supply Chain Management environment.</span></span>
    2. <span data-ttu-id="f96a9-123">Przejdź do **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="f96a9-123">Navigate to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    3. <span data-ttu-id="f96a9-124">Wybierz kartę **Ceny** na bocznym pasku nawigacyjnym.</span><span class="sxs-lookup"><span data-stu-id="f96a9-124">Select the **Prices** tab in the side navigation bar.</span></span>
    4. <span data-ttu-id="f96a9-125">Na karcie skróconej **Ocena umowy handlowej** usuń zaznaczenie opcji **Zapis ręczny**.</span><span class="sxs-lookup"><span data-stu-id="f96a9-125">Under the **Trade agreement evaluation** fastab, uncheck the **Manual entry** option.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="f96a9-126">Jak działa</span><span class="sxs-lookup"><span data-stu-id="f96a9-126">How it works</span></span>

<span data-ttu-id="f96a9-127">Po wybraniu **Zamówienia cenowego** w Sales funkcja **Sumy** na karcie **Zamówienie sprzedaży \> Widok** w Supply Chain Management jest wywoływana dla skojarzonego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f96a9-127">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="f96a9-128">Wartości w sumie zamówienia w Sales są używane do wypełniania odpowiednich kolumn w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f96a9-128">The values in the order total in Sales are used to fill in the corresponding columns in Supply Chain Management.</span></span>

<span data-ttu-id="f96a9-129">Jeśli suma zamówienia sprzedaży jest obliczana w Supply Chain Management, obliczenie ocenia istniejące umowy handlowe i umowy sprzedaży dla odbiorcy oraz produkty wymienione w zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f96a9-129">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="f96a9-130">Informacje te są używane do obliczania sum.</span><span class="sxs-lookup"><span data-stu-id="f96a9-130">This information is used to calculate the totals.</span></span> <span data-ttu-id="f96a9-131">W przypadku wybrania **Zamówienia cenowego** sprzedaż automatycznie odzwierciedla wszystkie ustawienia wykonane w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f96a9-131">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="f96a9-132">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="f96a9-132">Limitations</span></span>

<span data-ttu-id="f96a9-133">Po wypełnieniu kolumn w Sales obowiązują następujące ograniczenia:</span><span class="sxs-lookup"><span data-stu-id="f96a9-133">When the columns in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="f96a9-134">Konfigurowanie opłat i alokacji opłat w Supply Chain Management nie jest replikowane w Sales.</span><span class="sxs-lookup"><span data-stu-id="f96a9-134">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="f96a9-135">W przypadku cen nie są uwzględniane specjalne ceny detaliczne określone w kolumnie **Kanał detaliczny** na stronie wiersz zamówienia sprzedaży w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f96a9-135">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** column on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="f96a9-136">Nie są brane pod uwagę rabaty zdefiniowane w sekcji **Zarządzania przydziałem handlowym** w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f96a9-136">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]