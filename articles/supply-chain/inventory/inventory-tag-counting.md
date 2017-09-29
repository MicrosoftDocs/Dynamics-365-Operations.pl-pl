---
title: "Zliczanie znaczników zapasów"
description: "Ten artykuł zawiera informacje o procesie zliczania znaczników, który służy do porównywania rzeczywistej zawartości magazynu z zapasami dostępnymi (na stanie)."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 9e129fda638cfd8cff0e40079747f7ca70fa7531
ms.contentlocale: pl-pl
ms.lasthandoff: 09/12/2017

---

# <a name="inventory-tag-counting"></a><span data-ttu-id="177dd-103">Zliczanie znaczników zapasów</span><span class="sxs-lookup"><span data-stu-id="177dd-103">Inventory tag counting</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="177dd-104">Ten artykuł zawiera informacje o procesie zliczania znaczników, który służy do porównywania rzeczywistej zawartości magazynu z zapasami dostępnymi (na stanie).</span><span class="sxs-lookup"><span data-stu-id="177dd-104">This article provides information about tag counting, which you use to compare the actual contents of a warehouse with the on-hand inventory.</span></span>

<span data-ttu-id="177dd-105">Poprzez tworzenie wierszy na stronie **Zliczanie znaczników** na każdym towarze magazynowym umieszcza się numer znacznika, np. od 1 do 500.</span><span class="sxs-lookup"><span data-stu-id="177dd-105">By creating lines on the **Tag counting** page, you place a tag number on each inventory item, such as a number from 1 to 500.</span></span> <span data-ttu-id="177dd-106">Podczas inwentaryzacji należy wprowadzić numer towaru i ilość związaną z odpowiednim znacznikiem.</span><span class="sxs-lookup"><span data-stu-id="177dd-106">During the count, you enter the item number and the quantity on a corresponding tag.</span></span> <span data-ttu-id="177dd-107">Znacznik może być później podstawą dla danych wejściowych arkusza zliczania znaczników.</span><span class="sxs-lookup"><span data-stu-id="177dd-107">This tag can then be used as the basis for input in the tag counting journal.</span></span> <span data-ttu-id="177dd-108">Po zaksięgowaniu arkusza zliczania znaczników na stronie **Zliczanie** tworzony jest nowy arkusz zliczania.</span><span class="sxs-lookup"><span data-stu-id="177dd-108">After you post the tag counting journal, a new counting journal is created on the **Counting** page.</span></span> <span data-ttu-id="177dd-109">Nowy arkusz bazuje na wierszach arkusza zliczania znaczników utworzonych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="177dd-109">The new journal is based on the tag counting journal lines that you created.</span></span> <span data-ttu-id="177dd-110">Aby policzyć towary według znaczników w określonym wymiarze magazynu, należy wybrać wymiar na stronie **Wyświetl wymiary**, która jest wyświetlana podczas tworzenia arkusza zliczania znaczników.</span><span class="sxs-lookup"><span data-stu-id="177dd-110">To tag-count items by a specific inventory dimension, select the dimension on the **Display dimension** page that is displayed when you create the tag counting journal.</span></span> <span data-ttu-id="177dd-111">Na przykład aby policzyć towary w określonym magazynie, należy zaznaczyć pole wyboru **Magazyn**.</span><span class="sxs-lookup"><span data-stu-id="177dd-111">For example, to count items in a specific warehouse, select the **Warehouse** check box.</span></span> <span data-ttu-id="177dd-112">Jeśli suwak **Zablokuj towary podczas liczenia** na stronie **Parametry zarządzania zapasami i magazynem** jest zaznaczony, towary nie mogą być fizycznie aktualizowane podczas zliczania.</span><span class="sxs-lookup"><span data-stu-id="177dd-112">If the **Lock items during count** slider on the **Inventory and warehouse management parameters** page is selected, items can't be physically updated during counting.</span></span> <span data-ttu-id="177dd-113">Jednak towary w arkuszach zliczania znaczników nie są zablokowane podczas zliczania.</span><span class="sxs-lookup"><span data-stu-id="177dd-113">However, items in tag counting journals aren't locked during counting.</span></span> <span data-ttu-id="177dd-114">Transakcje magazynowe nie są tworzone, dopóki wiersze zliczania znaczników nie zostaną zaksięgowane ani przeniesione do arkusza zliczania.</span><span class="sxs-lookup"><span data-stu-id="177dd-114">Inventory transactions aren't created until the tag counting lines are posted and transferred to a counting journal.</span></span> <span data-ttu-id="177dd-115">Jeśli znaczniki są wprowadzane losowo, aby zidentyfikować brakujące znaczniki, należy kliknąć nagłówek kolumny **Znacznik**, aby posortować wiersze według znacznika.</span><span class="sxs-lookup"><span data-stu-id="177dd-115">If tags are entered randomly, and you want to identify missing tags, click the **Tag** column header to sort the lines by tag.</span></span>

<a name="see-also"></a><span data-ttu-id="177dd-116">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="177dd-116">See also</span></span>
--------

[<span data-ttu-id="177dd-117">Inwentaryzacja ciągła</span><span class="sxs-lookup"><span data-stu-id="177dd-117">Cycle counting</span></span>](../warehousing/cycle-counting.md)

