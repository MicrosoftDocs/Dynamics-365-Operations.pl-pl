---
title: Natychmiastowe uzupełnianie zapasów
description: W tym temacie opisano, jak wykorzystywać funkcję natychmiastowego uzupełniania zapasów do uzupełnienia zapasów, gdy dyrektywa lokalizacji nie alokuje zapasów.
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: ab1f06951d5daceaf002b2cc23236dd818457985
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "348602"
---
# <a name="immediate-replenishment"></a><span data-ttu-id="82e88-103">Natychmiastowe uzupełnianie zapasów</span><span class="sxs-lookup"><span data-stu-id="82e88-103">Immediate replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82e88-104">Funkcja natychmiastowego uzupełniania zapasów pozwala błyskawicznie uzupełnić zapasy, gdy wiersz dyrektywy lokalizacji nie jest w stanie przydzielić zapasów.</span><span class="sxs-lookup"><span data-stu-id="82e88-104">Immediate replenishment lets you replenish inventory immediately after a location directive line fails to allocate inventory.</span></span> <span data-ttu-id="82e88-105">Uzupełnienie zapasów opiera się na jednym wierszu w konfiguracji dyrektywy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="82e88-105">The replenishment is based on a single line in the setup of the location directive.</span></span> <span data-ttu-id="82e88-106">Jeśli zapasy nie są dostępne w jednostce miary określonej za pomocą tego wiersza, uzupełnienie zapasów w tej jednostce miary odbywa się natychmiast.</span><span class="sxs-lookup"><span data-stu-id="82e88-106">If inventory isn't on hand in the unit of measure that is specified by that line, replenishment of that unit of measure occurs immediately.</span></span>

<span data-ttu-id="82e88-107">Natychmiastowe uzupełnianie zapasów jest alternatywą dla metody, w której alokacja zapasów bazuje na większej liczbie wierszy w dyrektywie lokalizacji, a popyt jest sumowany na koniec alokacji i uzupełniany w jednostce miary określonej przez ostatni wiersz w dyrektywie lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="82e88-107">Immediate replenishment provides an alternative to the method where the allocation of inventory is based on more lines in the location directive, and where the demand is summed at the end of the allocation and replenished in the unit of measure that is specified by the last line in the location directive.</span></span>

<span data-ttu-id="82e88-108">Zaletami używania natychmiastowego uzupełnienia zapasów jest to, że uzupełnianie może być ograniczone przez określone jednostki, a ilość można skierować do określonej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="82e88-108">The benefits of using immediate replenishment are that replenishment can be limited by specific units and the quantity can be directed to specific locations.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="82e88-109">Scenariusz biznesowy</span><span class="sxs-lookup"><span data-stu-id="82e88-109">Business scenario</span></span>

<span data-ttu-id="82e88-110">Na przykład masz magazyn, który ma oddzielne obszary pobrania dla jednostek miary „pudełko” i „sztuka”.</span><span class="sxs-lookup"><span data-stu-id="82e88-110">For example, you have a warehouse that has separate picking areas for the "box" and "each" units of measure.</span></span> <span data-ttu-id="82e88-111">Chcesz zoptymalizować proces pobierania, tak aby była pobierana maksymalna możliwa liczba pudełek, a następnie brakująca ilość mniejsza niż zawartość pudełka była dobierana z obszaru „sztuka”.</span><span class="sxs-lookup"><span data-stu-id="82e88-111">You want to optimize the picking process by picking as many boxes as possible and then picking any remaining quantity that is less than a box from the "each" area.</span></span>

<span data-ttu-id="82e88-112">W takim przypadku można użyć funkcji natychmiastowego uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="82e88-112">In this case, you can use immediate replenishment.</span></span> <span data-ttu-id="82e88-113">W dyrektywie lokalizacji można skonfigurować natychmiastowe uzupełnienie zapasów pudełkami, tak aby uzupełnienie zapasów popytu ładunku następowało natychmiast po wystąpieniu niedoboru pudełek, które można pobrać dla ilości popytu.</span><span class="sxs-lookup"><span data-stu-id="82e88-113">In the location directive, you can set up immediate replenishment for boxes so that demand replenishment is used as soon as there is a shortage of boxes that can be picked for the demand quantity.</span></span> <span data-ttu-id="82e88-114">W ten sposób optymalizujesz proces pobierania, ponieważ zostanie pobrana maksymalna możliwa liczba pudełek.</span><span class="sxs-lookup"><span data-stu-id="82e88-114">In this way, you optimize the picking process so that picking includes as many boxes as possible.</span></span> <span data-ttu-id="82e88-115">Funkcja natychmiastowego uzupełniania zapasów spowoduje uzupełnienie pudełkami, a popyt nie zostanie przekazany dalej w celu pobrania ilości w jednostce miary „sztuka”.</span><span class="sxs-lookup"><span data-stu-id="82e88-115">Immediate replenishment will generate replenishment of the boxes, and the demand won't be passed on so that the quantities are picked in the "each" unit of measure.</span></span> <span data-ttu-id="82e88-116">Innymi słowy z obszaru „sztuka” zostaną pobrane tylko ilości, które powinny być pobierane w jednostka miary „sztuka” (czyli ilości mniejsze niż całe pudełko).</span><span class="sxs-lookup"><span data-stu-id="82e88-116">In other words, only the quantities that are supposed to be picked in the "each" unit of measure (that is, quantities that are less than a box) will be picked from the "each" area.</span></span> <span data-ttu-id="82e88-117">Jeśli wystąpi niedobór w obszarze „pudełko”, można pobrać maksymalną możliwą liczbę pudełek w granicach łącznego popytu.</span><span class="sxs-lookup"><span data-stu-id="82e88-117">If a shortage occurs in the "box" area, you can pick as many boxes as possible out of the total demand.</span></span> <span data-ttu-id="82e88-118">Pozostałe ilości zostaną następnie pobrane z obszaru „sztuka”.</span><span class="sxs-lookup"><span data-stu-id="82e88-118">The remaining quantities will then be picked from the "each" area.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="82e88-119">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="82e88-119">Where it applies</span></span>

<span data-ttu-id="82e88-120">Funkcja natychmiastowego uzupełniania zapasów jest używana podczas wykonywania grupy czynności, jeżeli alokacja nie powiedzie się dla wiersza dyrektywy lokalizacji, dla której jest ustawiony szablon uzupełnienia zapasów.</span><span class="sxs-lookup"><span data-stu-id="82e88-120">Immediate replenishment is used during wave execution if allocation fails for a location directive line that a replenishment template is set for.</span></span>

## <a name="set-up-immediate-replenishment"></a><span data-ttu-id="82e88-121">Konfigurowanie natychmiastowego uzupełniania zapasów</span><span class="sxs-lookup"><span data-stu-id="82e88-121">Set up immediate replenishment</span></span>

- <span data-ttu-id="82e88-122">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Dyrektywy lokalizacji**, a następnie na karcie **Wiersze** na liście **Szablon natychmiastowego uzupełniania zapasów** wybierz szablon uzupełnienia zapasów dla popytu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="82e88-122">Go to **Warehouse management** \> **Setup** \> **Location directives**, and then, on the **Lines** tab, in the **Immediate replenishment template** list, select a replenishment template for wave demand.</span></span>

<span data-ttu-id="82e88-123">Szablon uzupełniania zapasów zostanie zastosowany, jeśli wiersz dyrektywy lokalizacji nie przydzieli w ustawionej jednostce miary.</span><span class="sxs-lookup"><span data-stu-id="82e88-123">The replenishment template is applied if the location directive line fails to allocate a dedicated unit of measure.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="82e88-124">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="82e88-124">Troubleshooting</span></span>

<span data-ttu-id="82e88-125">Jeśli funkcja natychmiastowego uzupełniania zapasów jest wybrana dla wiersza dyrektywy lokalizacji, ale żadna praca uzupełniania zapasów nie zostanie wygenerowana podczas korzystania z szablonów uzupełniania zapasów popytu dla tego wiersza dyrektywy lokalizacji, należy zbadać dwie możliwe główne przyczyny:</span><span class="sxs-lookup"><span data-stu-id="82e88-125">If immediate replenishment is selected for a location directive line, but no replenishment work is generated when you use demand replenishment templates for that location directive line, two main causes must be investigated:</span></span>

- <span data-ttu-id="82e88-126">Upewnij się, że zastosowany szablon uzupełnienia zapasów popytu jest skonfigurowany tak, aby używał poprawnych szablonów lokalizacji i szablonów pracy typu **Uzupełnianie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="82e88-126">Make sure that the demand replenishment template that is applied is set up to use the correct location templates and work templates of the **Replenishment** type.</span></span>
- <span data-ttu-id="82e88-127">Upewnij się, że jest wystarczająca ilość dostępnych zapasów w lokalizacjach, gdzie szablon uzupełniania zapasów popytu szuka dostępnych zapasów dla uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="82e88-127">Make sure that there is enough on-hand inventory at the locations where the demand replenishment template searches for on-hand inventory for replenishment.</span></span>
