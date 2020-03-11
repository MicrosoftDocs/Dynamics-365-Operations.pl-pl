---
title: Opcje blokowania rabatów na produkty detaliczne
description: Istnieją różne powody, dla których sprzedawcy detaliczni chcą uniemożliwiać stosowanie rabatów do niektórych produktów — poprzez promocję albo podczas sprzedaży w punkcie sprzedaży.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 6a683ffce487dc4388711ad160c2e8dc55a690dd
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057471"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a><span data-ttu-id="e2e42-103">Opcje blokowania rabatów na produkty detaliczne</span><span class="sxs-lookup"><span data-stu-id="e2e42-103">Options for preventing discounts for retail products</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e2e42-104">Istnieją różne powody, dla których sprzedawcy detaliczni chcą uniemożliwiać stosowanie rabatów do niektórych produktów — poprzez promocję albo podczas sprzedaży w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e2e42-104">There are various reasons why retailers may want to prevent some products from being discounted, either from a promotion or during the sale at the POS.</span></span>

<span data-ttu-id="e2e42-105">Następujące opcje, które można znaleźć na karcie **Sprzedaż** dla zwolnionych produktów, pozwalają skonfigurować blokadę stosowania wszystkich lub tylko ręcznych rabatów.</span><span class="sxs-lookup"><span data-stu-id="e2e42-105">The following options, which can be found on the **Commerce** tab of released products, will allow the product to be configured to prevent all or manual discounts.</span></span> <span data-ttu-id="e2e42-106">Te ustawienia można także określić na poziomie kategorii w hierarchii kategorii.</span><span class="sxs-lookup"><span data-stu-id="e2e42-106">The settings can also be specified at the category level from the category hierarchy.</span></span>

- <span data-ttu-id="e2e42-107">**Nie zezwalaj na żadne rabaty** — Wybierz tę opcję, aby uniemożliwić stosowanie jakichkolwiek typów rabatów do tego produktu.</span><span class="sxs-lookup"><span data-stu-id="e2e42-107">**Prevent all discounts** – Select this option to prevent all types of discounts from being applied to this product.</span></span> <span data-ttu-id="e2e42-108">Obejmuje to promocje takie jak rabat łączony, rabaty ilościowe i progowe, a także ręczne rabaty dla wiersza i transakcji stosowane podczas sprzedaży przez użytkownika punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e2e42-108">This includes promotions such as mix and match, quantity and threshold discounts, as well as manual line and transaction discounts that are applied during a sale by a POS user.</span></span>
- <span data-ttu-id="e2e42-109">**Nie zezwalaj na rabaty ręczne** — Wybierz tę opcję, aby zablokować tylko ręczne rabaty dla wierszy lub transakcji stosowane podczas sprzedaży przez użytkownika punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e2e42-109">**Prevent manual discounts** – Select this option to only prevent the manual line or transaction discounts that are applied during a sale by a POS user.</span></span> <span data-ttu-id="e2e42-110">Produkty, dla których zaznaczono tę opcję, nadal kwalifikują się do promocji, takich jak rabaty łączone i progowe.</span><span class="sxs-lookup"><span data-stu-id="e2e42-110">Products with this option selected are still eligible for promotions, such as mix and match and quantity and threshold discounts.</span></span>

> [!NOTE]
> <span data-ttu-id="e2e42-111">Te ustawienia nie ograniczają operacji ręcznej zmiany ceny, ponieważ ustawia ona podstawę ceny i nie jest traktowana jako rabat.</span><span class="sxs-lookup"><span data-stu-id="e2e42-111">These settings do not restrict the price override operation, because that sets the base price and is not treated as a discount.</span></span>

<span data-ttu-id="e2e42-112">[![Pole blokowania rabatów](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span><span class="sxs-lookup"><span data-stu-id="e2e42-112">[![Prevent discounts field](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span></span>
