---
title: Aktualizacja kosztów standardowych w środowisku nieprodukcyjnym
description: Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych w środowisku nieprodukcyjnym.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 164c6257d9cd076fd8f91beafb6b797e3e999420
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830155"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a><span data-ttu-id="7f3a9-103">Aktualizacja kosztów standardowych w środowisku nieprodukcyjnym</span><span class="sxs-lookup"><span data-stu-id="7f3a9-103">Update standard costs in a non-manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7f3a9-104">Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych w środowisku nieprodukcyjnym.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-104">This article provides guidance for updating standard costs in a non-manufacturing environment.</span></span>

<span data-ttu-id="7f3a9-105">W poniższych wytycznych założono, że aktualizowanie kosztu standardowego obejmuje tworzenie dwóch wersji.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-105">The following guidelines assume that you use a two-version approach to update standard cost.</span></span> <span data-ttu-id="7f3a9-106">W tej metodzie jedna wersja wyceny zawiera koszty standardowe zdefiniowane pierwotnie dla okresu zamrożenia, a druga wersja wyceny zawiera przyrostowe aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-106">In this approach, one costing version contains the standard costs that were originally defined for the frozen period, and the second costing version contains the incremental updates.</span></span> <span data-ttu-id="7f3a9-107">Każdą aktualizację wprowadza się jako rekord kosztu umieszczony w drugiej wersji wyceny i na końcu włączany.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-107">Each update is entered as a cost record that is enclosed in the second costing version, and eventually it's enabled.</span></span> <span data-ttu-id="7f3a9-108">W alternatywnym podejściu z jedną wersją jest używany zbiór standardowych kosztów, które pierwotnie zdefiniowano.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-108">An alternative, one-version approach uses the set of standard costs that was originally defined.</span></span> <span data-ttu-id="7f3a9-109">Podejście z dwoma wersjami wymagana zdefiniowania drugiej wersji wyceny.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-109">The two-version approach requires that you define a second costing version.</span></span> <span data-ttu-id="7f3a9-110">Poniżej przedstawiono wytyczne dotyczące definiowania tej wersji wyceny:</span><span class="sxs-lookup"><span data-stu-id="7f3a9-110">Here are the guidelines for defining this costing version:</span></span>

-   <span data-ttu-id="7f3a9-111">Przypisz typ wyceny **Koszty standardowe**.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-111">Assign a costing type of **Standard costs**.</span></span>
-   <span data-ttu-id="7f3a9-112">Przypisz sugestywny identyfikator wskazujący zawartość wersji wyceny, np. **2016-AKTUALIZACJE**.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-112">Assign a meaningful identifier that indicates the contents of the costing version, such as **2016-UPDATES**.</span></span>
-   <span data-ttu-id="7f3a9-113">Upewnij się, że zawartość obejmuje rekordy kosztów.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-113">Make sure that the content includes cost records.</span></span>
-   <span data-ttu-id="7f3a9-114">Zezwól na wprowadzanie rekordów kosztów we wszystkich oddziałach.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-114">Allow cost records to be entered for all sites.</span></span> <span data-ttu-id="7f3a9-115">Jeśli określisz oddział, rekordy kosztów można wprowadzić tylko w tym oddziale.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-115">If you specify a site, cost records can be entered only for that site.</span></span>
-   <span data-ttu-id="7f3a9-116">W polu zasady alternatywnego źródła ustaw **Brak**.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-116">Indicate a fallback principle of **None**.</span></span> <span data-ttu-id="7f3a9-117">Zasada alternatywnego źródła ma zastosowanie tylko do obliczeń kosztów produkowanych towarów.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-117">The fallback principle applies only to cost calculations for manufactured items.</span></span>

<span data-ttu-id="7f3a9-118">Aby skorygować, dopasować lub zaktualizować standardowe koszty nowych towarów, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-118">To correct, adjust, or update standard costs for new items, follow these steps.</span></span>

1.  <span data-ttu-id="7f3a9-119">Na stronie **Konfiguracja wersji** **wyceny** włącz możliwość wprowadzania danych kosztów do drugiej wersji wyceny.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-119">Use the **Costing version** **setup** page to enable cost data to be entered into the second costing version.</span></span> <span data-ttu-id="7f3a9-120">Opcjonalnie zablokuj możliwość aktywacji kosztów oczekujących, tak aby aktywacja była dozwolona dopiero po całkowitym i dokładnym zdefiniowaniu tych kosztów.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-120">Optionally, prevent the activation of pending costs, so that activation will be allowed after pending costs have been completely and accurately defined.</span></span> <span data-ttu-id="7f3a9-121">Opcjonalnie można wprowadzić datę w polu **Od dnia**.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-121">You can also optionally enter a date in the **From date** field.</span></span> <span data-ttu-id="7f3a9-122">Określi ona, od kiedy zostaną włączone aktualizacje przyrostowe.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-122">As a general guideline, use the date when you intend to enable the incremental updates.</span></span> <span data-ttu-id="7f3a9-123">Alternatywnie pozostaw niewypełnione pole **Od dnia** w ustawieniach wersji wyceny, a wypełnij pole **Od dnia** w każdym rekordzie kosztu.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-123">Alternatively, leave the **From date** field blank for the costing version, and then enter a date in the **From date** field for each cost record.</span></span>
2.  <span data-ttu-id="7f3a9-124">Na stronie **Cena pozycji** wprowadź aktualizacje jako rekordy kosztów towarów umieszczone w drugiej wersji wyceny.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-124">Use the **Item price** page to enter updates as item cost records that are enclosed in the second costing version.</span></span>
3.  <span data-ttu-id="7f3a9-125">Za pomocą raportu **Ceny pozycji** zweryfikuj kompletność i dokładność rekordów kosztów towarów umieszczonych w drugiej wersji wyceny.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-125">Use the **Item prices** report to verify the completeness and accuracy of the item cost records that are enclosed in the second costing version.</span></span>
4.  <span data-ttu-id="7f3a9-126">Na stronie **Obsługa wersji wyceny** zmień flagę blokowania, aby umożliwić aktywowanie rekordów kosztów oczekujących umieszczonych w drugiej wersji wyceny.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-126">Use the **Costing version maintenance** page to change the blocking flag to allow activation of the pending cost records that are enclosed in the second costing version.</span></span>
5.  <span data-ttu-id="7f3a9-127">Na stronie **Aktywuj ceny** (którą można otworzyć ze strony **Obsługa wersji wyceny**) aktywuj wszystkie rekordy kosztów oczekujących towarów, jakie znajdują się w drugiej wersji wyceny.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-127">Use the **Activate prices** page (which you open from the **Costing version maintenance** page) to activate all pending item cost records that are enclosed in the second costing version.</span></span> <span data-ttu-id="7f3a9-128">Można również aktywować rekordy kosztów oczekujących dla poszczególnych towarów, klikając przycisk **Aktywuj oczekującą cenę** umieszczony na stronie **Cena pozycji**.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-128">You can also activate the pending cost records for individual items by clicking the **Activate pending price** button on the **Item price** page.</span></span>
6.  <span data-ttu-id="7f3a9-129">Aby uniemożliwić dalsze modyfikowanie, na stronie **Konfiguracja wersji wyceny** zmień flagi blokowania umieszczone w drugiej wersji wyceny.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-129">To prevent additional data maintenance, use the **Costing version setup** page to change the blocking flags that are enclosed in the second costing version.</span></span> <span data-ttu-id="7f3a9-130">Zasady blokowania zapobiegają wprowadzeniu nowych kosztów oczekujących i aktywowaniu kosztów oczekujących.</span><span class="sxs-lookup"><span data-stu-id="7f3a9-130">The blocking policies will prevent the entry of new pending costs and the activation of pending costs.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]