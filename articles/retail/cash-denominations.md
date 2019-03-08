---
title: Konfigurowanie stawek gotówkowych w punkcie sprzedaży (POS)
description: Nominały gotówki banknotów i monet można zdefiniować w systemach zaplecza, tak aby były używane przez kasjerów, sprzedawców i kierowników w sklepie z poziomu punktu sprzedaży.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 24775044e5a502a5615392a6a8c4030bdfafb0ab
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "343519"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a><span data-ttu-id="81a35-103">Konfigurowanie stawek gotówkowych w punkcie sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="81a35-103">Configure cash denominations for the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="81a35-104">Nominały gotówki banknotów i monet można zdefiniować w systemach zaplecza, tak aby były używane przez kasjerów, sprzedawców i kierowników w sklepie z poziomu punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="81a35-104">Cash denominations for notes and coins can be defined in the back office to be used by cashiers, sales associates, and managers at the store from within the POS.</span></span> <span data-ttu-id="81a35-105">Te nominały mogą służyć jako pomoc w podliczaniu środków pieniężnych w deklaracjach środków płatniczych na koniec dnia lub do szybkiego opłacenia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="81a35-105">These denominations can be used to aid in counting cash for end of day tender declarations or for quickly tendering a sale.</span></span>

## <a name="define-denominations"></a><span data-ttu-id="81a35-106">Definiowanie nominałów</span><span class="sxs-lookup"><span data-stu-id="81a35-106">Define denominations</span></span>

<span data-ttu-id="81a35-107">Nominały definiuje się dla konkretnego sklepu na stronie **Konfiguracja** \> **Opcja deklaracja gotówki z właściwości sklepu**.</span><span class="sxs-lookup"><span data-stu-id="81a35-107">The denominations are set up per store on the **Set up** \> **Cash declaration option from the store property** page.</span></span>

![nominały gotówki](./media/image1-denomination.png)

<span data-ttu-id="81a35-109">Aby zdefiniować nominał:</span><span class="sxs-lookup"><span data-stu-id="81a35-109">To define a denomination:</span></span>

1. <span data-ttu-id="81a35-110">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="81a35-110">Click **New**.</span></span>
1. <span data-ttu-id="81a35-111">Określ typ (moneta lub banknot).</span><span class="sxs-lookup"><span data-stu-id="81a35-111">Specify the type (coin or note).</span></span>
1. <span data-ttu-id="81a35-112">Określ kwotę (wartość).</span><span class="sxs-lookup"><span data-stu-id="81a35-112">Specify the amount (value).</span></span>

![nominały gotówki](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a><span data-ttu-id="81a35-114">Konfigurowanie profilu funkcji</span><span class="sxs-lookup"><span data-stu-id="81a35-114">Configure the functionality profile</span></span>

<span data-ttu-id="81a35-115">W trakcie płacenia gotówką w punkcie sprzedaży użytkownik może za pomocą nominałów banknotów szybko wprowadzić kwotę płaconą przez odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="81a35-115">When paying by cash in POS, the user can use the note denominations to quickly enter the amount paid by the customer.</span></span> <span data-ttu-id="81a35-116">W profilu funkcji można skonfigurować dwie opcje wyświetlania nominałów w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="81a35-116">In the functionality profile, you can configure the two options for showing the denomination in POS.</span></span>

- <span data-ttu-id="81a35-117">**Większa lub równa kwocie należnej** — Domyślnie w punkcie sprzedaży będą wyświetlane tylko nominały banknotów większe niż kwota należna, co pozwala zapłacić jednym naciśnięciem przycisku.</span><span class="sxs-lookup"><span data-stu-id="81a35-117">**Greater or equal to amount due** – By default, POS will only show the note denominations that are greater than the amount due, which allows for one-touch tendering.</span></span> <span data-ttu-id="81a35-118">Na przykład jeśli kwota należna wynosi 7,50 USD, w punkcie sprzedaży byłyby wyświetlane następujące nominały: 10 USD, 20 USD, 50 USD i 100 USD.</span><span class="sxs-lookup"><span data-stu-id="81a35-118">For example, if the amount due is $7.50, POS would show the following denominations: $10, $20, $50, and $100.</span></span> <span data-ttu-id="81a35-119">Dotknięcie dowolnej z tych kwot spowoduje automatyczną zapłatę za sprzedaż na tę kwotę.</span><span class="sxs-lookup"><span data-stu-id="81a35-119">Touching any of these amounts will automatically tender the sale for that amount.</span></span> <span data-ttu-id="81a35-120">Banknoty 1 USD i 5 USD nie są wyświetlane, ponieważ te wartości są mniejsze niż kwota należna.</span><span class="sxs-lookup"><span data-stu-id="81a35-120">The $1 and $5 notes are not shown since these amounts are less than the amount due.</span></span>
- <span data-ttu-id="81a35-121">**Wszystkie stawki** — Wybierz tę opcję, aby zawsze wyświetlać wszystkie nominały banknotów w punkcie sprzedaży, bez względu na kwotę należną.</span><span class="sxs-lookup"><span data-stu-id="81a35-121">**All denominations** – Select this option to always show all note denominations in POS, regardless of the amount due.</span></span> <span data-ttu-id="81a35-122">Oznacza to, że użytkownika może osiągnąć kwotę należną za pomocą kombinacji banknotów.</span><span class="sxs-lookup"><span data-stu-id="81a35-122">This means that the user can use a combination of notes to reach the amount due.</span></span> <span data-ttu-id="81a35-123">Na przykład jeśli kwota należna wynosi 25,00 USD, użytkownik może wybrać nominały 20 USD i 5 USD, aby sfinalizować sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="81a35-123">For example, if the amount due is $25.00, the user can choose $20 and $5 to complete the sale.</span></span>
