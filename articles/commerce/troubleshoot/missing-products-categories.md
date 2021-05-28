---
title: Brakuje produktów i kategorii po skopiowaniu środowiska
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku braku produktów i kategorii po skopiowaniu witryny do jednego środowiska lub w tym samym środowisku.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4964b9623a91286d4f8260bcae7941feb48f8962
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022405"
---
# <a name="products-and-categories-missing-after-environment-copy"></a><span data-ttu-id="3e7b1-103">Brakuje produktów i kategorii po skopiowaniu środowiska</span><span class="sxs-lookup"><span data-stu-id="3e7b1-103">Products and categories missing after environment copy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3e7b1-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku braku produktów i kategorii po skopiowaniu witryny do jednego środowiska lub w tym samym środowisku.</span><span class="sxs-lookup"><span data-stu-id="3e7b1-104">This topic provides troubleshooting guidance that can help when products and categories are missing after a site is copied between environments or within the same environment.</span></span>

## <a name="description"></a><span data-ttu-id="3e7b1-105">opis</span><span class="sxs-lookup"><span data-stu-id="3e7b1-105">Description</span></span>

<span data-ttu-id="3e7b1-106">Gdy witryna zostanie skopiowana z jednego środowiska do innego lub w tym samym środowisku, w tej samej witrynie brakuje produktów i kategorii.</span><span class="sxs-lookup"><span data-stu-id="3e7b1-106">After a site is copied from one environment to another, or within the same environment, the products and categories are missing from the site.</span></span> <span data-ttu-id="3e7b1-107">Brak produktów i kategorii z witryny sklepu handlu elektronicznego i karty **Produkty** w Konstruktorze witryn portalu Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e7b1-107">The products and categories will be missing from the e-commerce storefront and from the **Products** tab in Commerce site builder.</span></span>

## <a name="resolution"></a><span data-ttu-id="3e7b1-108">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="3e7b1-108">Resolution</span></span>

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a><span data-ttu-id="3e7b1-109">Mapowanie numeru jednostki operacyjnej kanału na nowo skopiowaną witrynę w Konstruktorze witryn Commerce</span><span class="sxs-lookup"><span data-stu-id="3e7b1-109">Map the channel operating unit number to a newly copied site in Commerce site builder</span></span>

<span data-ttu-id="3e7b1-110">Aby zmapować numer jednostki operacyjnej kanału (OUN) do nowo skopiowanej witryny w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3e7b1-110">To map the channel operating unit number (OUN) to a newly copied site in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e7b1-111">Wybierz nowo skopiowaną witrynę.</span><span class="sxs-lookup"><span data-stu-id="3e7b1-111">Select the newly copied site.</span></span>
1. <span data-ttu-id="3e7b1-112">W obszarze **Ustawienia witryny** wybierz opcję **kanały**.</span><span class="sxs-lookup"><span data-stu-id="3e7b1-112">Under **Site settings**, select **Channels**.</span></span>
1. <span data-ttu-id="3e7b1-113">Obok nazwy kanału wybierz wielokropek (**...**), a następnie wybierz pozycję **Zmień kanał sklepu internetowego**.</span><span class="sxs-lookup"><span data-stu-id="3e7b1-113">Next to the channel name, select the ellipsis (**...**), and then select **Change online store channel**.</span></span>
1. <span data-ttu-id="3e7b1-114">W oknie dialogowym **Zmiana kanału sklepu internetowego** wybierz kanał do mapowania na nowo skopiowaną witrynę, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e7b1-114">In the **Change online store channel** dialog box, select the channel to map to the newly copied site, and then select **OK**.</span></span>
1. <span data-ttu-id="3e7b1-115">Wybierz **Zapisz i opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="3e7b1-115">Select **Save and publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e7b1-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3e7b1-116">Additional resources</span></span>

[<span data-ttu-id="3e7b1-117">Kojarzenie witryny Dynamics 365 Commerce z kanałem online</span><span class="sxs-lookup"><span data-stu-id="3e7b1-117">Associate a Dynamics 365 Commerce site with an online channel</span></span>](../associate-site-online-store.md)
