---
title: Używanie aparatu kalkulacji cen Dynamics 365 Commerce z rozwiązaniem Dynamics 365 Sales
description: W tym temacie opisano sposób używania aparatu kalkulacji cen w Microsoft Dynamics 365 Commerce z Dynamics 365 Sales w celu tworzenia ofert sprzedaży.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: fa93b1262049d80148ff23b3d7223ec0f6c2fe68
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941173"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a><span data-ttu-id="09a7a-103">Używanie aparatu kalkulacji cen Dynamics 365 Commerce z rozwiązaniem Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="09a7a-103">Use the Dynamics 365 Commerce pricing engine with Dynamics 365 Sales</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="09a7a-104">W tym temacie opisano sposób używania aparatu kalkulacji cen w Microsoft Dynamics 365 Commerce z Dynamics 365 Sales w celu tworzenia ofert sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="09a7a-104">This topic describes how to use the Microsoft Dynamics 365 Commerce pricing engine to create sales quotations in Dynamics 365 Sales.</span></span>

<span data-ttu-id="09a7a-105">Aparat kalkulacji cen Dynamics 365 Commerce obsługuje większość scenariuszy kalkulacji cen w relacjach B2C, takich jak ceny na poziomie sklepu, ceny oparte na przynależności i lojalności, rabaty za skład zamówienia, rabaty ilościowe i rabaty progowe.</span><span class="sxs-lookup"><span data-stu-id="09a7a-105">The Dynamics 365 Commerce pricing engine supports most business-to-consumer (B2C) pricing scenarios, such as store-level pricing, affiliation-based and loyalty-based pricing, mix-and-match discounts, quantity discounts, and threshold discounts.</span></span> <span data-ttu-id="09a7a-106">Aparat cenowy używa złożonych reguł w celu określenia najlepszej ceny dla danej oferty lub zamówienia.</span><span class="sxs-lookup"><span data-stu-id="09a7a-106">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span>

<span data-ttu-id="09a7a-107">W przypadku korzystania z funkcji [podwójnego zapisu ](./dual-write-overview.md) dostępne są trzy opcje na potrzeby kalkulacji cen.</span><span class="sxs-lookup"><span data-stu-id="09a7a-107">When you use [dual-write](./dual-write-overview.md), you have three options for your pricing needs.</span></span> <span data-ttu-id="09a7a-108">Można skorzystać z statycznej ceny, która pochodzi z cennika systemu Dynamics 365 Sales, aparatu kalkulacji cen w Dynamics 365 Supply Chain Management lub aparatu kalkulacji cen w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="09a7a-108">You can use the static pricing that comes from the price list in Dynamics 365 Sales, the pricing engine in Dynamics 365 Supply Chain Management, or the pricing engine in Dynamics 365 Commerce.</span></span> <span data-ttu-id="09a7a-109">Wśród tych opcji aparat kalkulacji cen Commerce najlepiej nadaje się do scenariuszy B2C.</span><span class="sxs-lookup"><span data-stu-id="09a7a-109">Among these options, the Commerce pricing engine is best suited to B2C scenarios.</span></span>

## <a name="use-the-commerce-pricing-engine-in-sales"></a><span data-ttu-id="09a7a-110">Korzystanie z aparatu kalkulacji cen Commerce w module Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="09a7a-110">Use the Commerce pricing engine in Sales</span></span>

> [!NOTE]
> <span data-ttu-id="09a7a-111">Obecnie aparat kalkulacji cen Commerce może być używany tylko do tworzenia ofert w module Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="09a7a-111">Currently, the Commerce pricing engine can be used only for quotation creation in the Sales.</span></span> <span data-ttu-id="09a7a-112">Integracja zamówienia sprzedaży z aparatem kalkulacji cen Commerce nie jest jeszcze dostępna.</span><span class="sxs-lookup"><span data-stu-id="09a7a-112">Sales order integration with the Commerce pricing engine isn't yet available.</span></span>

<span data-ttu-id="09a7a-113">Gdy użytkownicy inicjują ofertę w module Sprzedaż, struktura podwójnego zapisywania kopiuje szczegóły oferty do modułu Commerce.</span><span class="sxs-lookup"><span data-stu-id="09a7a-113">When users initiate a quotation in Sales, the dual-write framework copies the quotation details to Commerce.</span></span> <span data-ttu-id="09a7a-114">Wszelkie zmiany w istniejących wierszach oferty lub wszystkie nowo dodane wiersze ofert w module Sprzedaż są kopiowane do modułu Commerce.</span><span class="sxs-lookup"><span data-stu-id="09a7a-114">Any changes to existing quotation lines or any newly added quotation lines in Sales are copied to Commerce.</span></span> <span data-ttu-id="09a7a-115">Jeśli użytkownik chce użyć aparatu kalkulacji cen Commerce w celu uzyskania ceny oferty, może wybrać opcję **Oferta cenowa**, aby zaktualizować ceny oferty w oparciu o aparat kalkulacji cen w module Commerce.</span><span class="sxs-lookup"><span data-stu-id="09a7a-115">When users want to use the Commerce pricing engine to price the quotation, they can select **Price quote** to update the prices of the quotation, based on the Commerce pricing engine.</span></span> <span data-ttu-id="09a7a-116">Następnie ceny są automatycznie aktualizowane zarówno w module Sprzedaż, jak i w Commerce.</span><span class="sxs-lookup"><span data-stu-id="09a7a-116">Prices are then automatically updated in both Sales and Commerce.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="09a7a-117">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="09a7a-117">Prerequisites</span></span>

- <span data-ttu-id="09a7a-118">Zanim będzie można użyć aparatu kalkulacji cen Commerce w module Sprzedaż, należy wykonać kroki podane w sekcji [Prospekt do gotówki w podwójnym zapisie](./dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="09a7a-118">Before you can use the Commerce pricing engine in Sales, you must follow the steps in [Prospect-to-cash in dual-write](./dual-write-prospect-to-cash.md).</span></span>
- <span data-ttu-id="09a7a-119">Należy wyłączyć ocenę umowy handlowej przy wprowadzaniu ręcznym, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="09a7a-119">You must turn off trade agreement evaluation for manual entry by following these steps:</span></span>

    1. <span data-ttu-id="09a7a-120">W środowisku Commerce wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="09a7a-120">In your Commerce environment, go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    1. <span data-ttu-id="09a7a-121">Na karcie **Ceny**, na skróconej karcie **Ocena umowy handlowej** wyczyść pole wyboru **Wprowadzanie ręczne**.</span><span class="sxs-lookup"><span data-stu-id="09a7a-121">On the **Prices** tab, on the **Trade agreement evaluation** FastTab, clear the **Manual entry** check box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="09a7a-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="09a7a-122">Additional resources</span></span>

[<span data-ttu-id="09a7a-123">Od prospekta do kasy w podwójnym zapisie</span><span class="sxs-lookup"><span data-stu-id="09a7a-123">Prospect-to-cash in dual-write</span></span>](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]