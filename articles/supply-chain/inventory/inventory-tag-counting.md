---
title: Zliczanie znaczników zapasów
description: Ten temat zawiera informacje o procesie zliczania znaczników, który służy do porównywania rzeczywistej zawartości magazynu z zapasami dostępnymi na stanie.
author: MarkusFogelberg
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1df4a97dee3dc24856a1b40f3dc8dd095338b614
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825970"
---
# <a name="inventory-tag-counting"></a><span data-ttu-id="d4aed-103">Zliczanie znaczników zapasów</span><span class="sxs-lookup"><span data-stu-id="d4aed-103">Inventory tag counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d4aed-104">Ten temat zawiera informacje o procesie zliczania znaczników, który służy do porównywania rzeczywistej zawartości magazynu z zapasami dostępnymi na stanie.</span><span class="sxs-lookup"><span data-stu-id="d4aed-104">This topic provides information about tag counting, which you use to compare the actual contents of a warehouse with the on-hand inventory.</span></span>

<span data-ttu-id="d4aed-105">Poprzez tworzenie wierszy na stronie **Zliczanie znaczników** na każdym towarze magazynowym umieszcza się numer znacznika, np. od 1 do 500.</span><span class="sxs-lookup"><span data-stu-id="d4aed-105">By creating lines on the **Tag counting** page, you place a tag number on each inventory item, such as a number from 1 to 500.</span></span> <span data-ttu-id="d4aed-106">Podczas inwentaryzacji należy wprowadzić numer towaru i ilość związaną z odpowiednim znacznikiem.</span><span class="sxs-lookup"><span data-stu-id="d4aed-106">During the count, you enter the item number and the quantity on a corresponding tag.</span></span> <span data-ttu-id="d4aed-107">Znacznik może być później podstawą dla danych wejściowych arkusza zliczania znaczników.</span><span class="sxs-lookup"><span data-stu-id="d4aed-107">This tag can then be used as the basis for input in the tag counting journal.</span></span> <span data-ttu-id="d4aed-108">Po zaksięgowaniu arkusza zliczania znaczników na stronie **Zliczanie** tworzony jest nowy arkusz zliczania.</span><span class="sxs-lookup"><span data-stu-id="d4aed-108">After you post the tag counting journal, a new counting journal is created on the **Counting** page.</span></span> <span data-ttu-id="d4aed-109">Nowy arkusz bazuje na wierszach arkusza zliczania znaczników utworzonych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d4aed-109">The new journal is based on the tag counting journal lines that you created.</span></span> <span data-ttu-id="d4aed-110">Aby policzyć towary według znaczników w określonym wymiarze magazynu, należy wybrać wymiar na stronie **Wyświetl wymiary**, która jest wyświetlana podczas tworzenia arkusza zliczania znaczników.</span><span class="sxs-lookup"><span data-stu-id="d4aed-110">To tag-count items by a specific inventory dimension, select the dimension on the **Display dimension** page that is displayed when you create the tag counting journal.</span></span> <span data-ttu-id="d4aed-111">Na przykład aby policzyć towary w określonym magazynie, należy zaznaczyć pole wyboru **Magazyn**.</span><span class="sxs-lookup"><span data-stu-id="d4aed-111">For example, to count items in a specific warehouse, select the **Warehouse** check box.</span></span> <span data-ttu-id="d4aed-112">Jeśli suwak **Zablokuj towary podczas liczenia** na stronie **Parametry zarządzania zapasami i magazynem** jest zaznaczony, towary nie mogą być fizycznie aktualizowane podczas zliczania.</span><span class="sxs-lookup"><span data-stu-id="d4aed-112">If the **Lock items during count** slider on the **Inventory and warehouse management parameters** page is selected, items can't be physically updated during counting.</span></span> <span data-ttu-id="d4aed-113">Jednak towary w arkuszach zliczania znaczników nie są zablokowane podczas zliczania.</span><span class="sxs-lookup"><span data-stu-id="d4aed-113">However, items in tag counting journals aren't locked during counting.</span></span> <span data-ttu-id="d4aed-114">Transakcje magazynowe nie są tworzone, dopóki wiersze zliczania znaczników nie zostaną zaksięgowane ani przeniesione do arkusza zliczania.</span><span class="sxs-lookup"><span data-stu-id="d4aed-114">Inventory transactions aren't created until the tag counting lines are posted and transferred to a counting journal.</span></span> <span data-ttu-id="d4aed-115">Jeśli znaczniki są wprowadzane losowo, aby zidentyfikować brakujące znaczniki, należy kliknąć nagłówek kolumny **Znacznik**, aby posortować wiersze według znacznika.</span><span class="sxs-lookup"><span data-stu-id="d4aed-115">If tags are entered randomly, and you want to identify missing tags, click the **Tag** column header to sort the lines by tag.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d4aed-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d4aed-116">Additional resources</span></span>

[<span data-ttu-id="d4aed-117">Inwentaryzacja ciągła</span><span class="sxs-lookup"><span data-stu-id="d4aed-117">Cycle counting</span></span>](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]