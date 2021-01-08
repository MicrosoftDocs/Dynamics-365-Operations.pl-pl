---
title: Wyświetlanie opłat związanych z wytworzonym towarem
description: Stałe koszty wytworzonego towaru odzwierciedlają czas przezbrajania dla danej operacji oraz składniki o stałej ilości lub stałą ilość odpadków.
author: AndersGirke
manager: tfehr
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: c5e0175e5743c800d8f04723d03ae503cff3a67a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435426"
---
# <a name="display-charges-for-a-manufactured-item"></a><span data-ttu-id="9c303-103">Wyświetlanie opłat związanych z wytworzonym towarem</span><span class="sxs-lookup"><span data-stu-id="9c303-103">Display charges for a manufactured item</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c303-104">Stałe koszty wytworzonego towaru odzwierciedlają czas przezbrajania dla danej operacji oraz składniki o stałej ilości lub stałą ilość odpadków.</span><span class="sxs-lookup"><span data-stu-id="9c303-104">The constant costs of a manufactured item reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span>

<span data-ttu-id="9c303-105">Obliczona kwota zamortyzowanych opłat za towar może być wyświetlana w kosztach jednostkowych towaru.</span><span class="sxs-lookup"><span data-stu-id="9c303-105">The calculated amount of an item's charges can be displayed with the item's unit costs.</span></span> <span data-ttu-id="9c303-106">Jednak opłaty są czasami wyświetlane w oddzielnych polach i nie są uwzględniane w kosztach jednostkowych towaru.</span><span class="sxs-lookup"><span data-stu-id="9c303-106">However, the charges are sometimes displayed as separate fields, and they are not included in the item's unit costs.</span></span> <span data-ttu-id="9c303-107">Gdy opłaty są wyświetlane w oddzielnych polach, jedno z nich przedstawia całkowitą kwotę, a drugie wielkość partii do wyceny używaną na potrzeby amortyzowania kwoty.</span><span class="sxs-lookup"><span data-stu-id="9c303-107">When the charges appear as separate fields, one field displays the total amount of charges, and another field displays the costing lot size that is used to amortize the amount.</span></span> <span data-ttu-id="9c303-108">Na przykład na stronie Cena pozycji są wyświetlane opłaty w dwóch oddzielnych polach.</span><span class="sxs-lookup"><span data-stu-id="9c303-108">The Item price page, for example, displays the charges as two separate fields.</span></span> <span data-ttu-id="9c303-109">Jednak na stronie Pełna informacja jest wyświetlany całkowity koszt jednostki towaru, a zamortyzowane koszty są uwzględniane w kosztach jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="9c303-109">However, the Complete page displays the item's total cost per unit, and the amortized costs are included in the unit costs.</span></span>

<span data-ttu-id="9c303-110">Opłaty za wytwarzany towar są zawsze uwzględniane w koszcie jednostkowym tego towaru na potrzeby obliczania kosztu standardowego.</span><span class="sxs-lookup"><span data-stu-id="9c303-110">The charges for a manufactured item are always included in the item's unit cost for standard cost purposes.</span></span> <span data-ttu-id="9c303-111">Opcjonalnie mogą być też uwzględniane w planowaniu kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c303-111">They can optionally be included for planned cost purposes.</span></span> <span data-ttu-id="9c303-112">Zasada w wersji wyceny wymusza uwzględnienie opłat w koszcie wytwarzanego towaru.</span><span class="sxs-lookup"><span data-stu-id="9c303-112">A policy in the costing version enforces the inclusion of charges in the cost of a manufactured item.</span></span> <span data-ttu-id="9c303-113">Po aktywowaniu rekordu kosztów towaru aktualizujesz opłaty w informacjach o koszcie podstawowym towaru, które są wyświetlane na stronie Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="9c303-113">When you activate an item's cost record, you update the charges for the item's base cost information, which is displayed in the Item price page.</span></span> <span data-ttu-id="9c303-114">Opłaty są wyświetlane w dwóch oddzielnych polach i nie są uwzględniane w koszcie jednostkowym towaru.</span><span class="sxs-lookup"><span data-stu-id="9c303-114">The charges are displayed as two separate fields, and they are not included in the item's unit cost.</span></span> <span data-ttu-id="9c303-115">Po każdym aktywowaniu nastąpi aktualizacja informacji o koszcie podstawowym towaru, nawet jeśli aktywacja odzwierciedla dane z różnych oddziałów.</span><span class="sxs-lookup"><span data-stu-id="9c303-115">Each activation updates the item's base cost information, even if the activation reflects different sites.</span></span> <span data-ttu-id="9c303-116">W związku z tym informacje o kosztach podstawowych powinny być traktowane jako dane referencyjne.</span><span class="sxs-lookup"><span data-stu-id="9c303-116">Therefore, you should view the base cost information as reference information.</span></span>





