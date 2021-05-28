---
title: Profil lokalizacji nie zezwala na ujemne zapasy, ale ujemne wartości dostępnych zapasów są dozwolone
description: Opcja Zezwalaj na ujemny stan zapasów dla profilu lokalizacji ma wartość Nie, ale system nadal zezwala na ujemne wartości dostępnych zapasów.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026811"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a><span data-ttu-id="c198d-103">Profil lokalizacji nie zezwala na ujemne zapasy, ale ujemne wartości dostępnych zapasów są dozwolone</span><span class="sxs-lookup"><span data-stu-id="c198d-103">Location profile disallows negative inventory, but negative on-hand inventory is permitted</span></span>

<span data-ttu-id="c198d-104">Numer artykułu z bazy wiedzy: 4613622</span><span class="sxs-lookup"><span data-stu-id="c198d-104">KB number: 4613622</span></span>

## <a name="symptoms"></a><span data-ttu-id="c198d-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="c198d-105">Symptoms</span></span>

<span data-ttu-id="c198d-106">Opcja **Zezwalaj na ujemny stan zapasów** dla profilu lokalizacji ma wartość *Nie*, ale system nadal zezwala na ujemne wartości dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="c198d-106">The **Allow negative inventory** option for the location profile is set to *No*, but the system still allows negative on-hand inventory.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c198d-107">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="c198d-107">Example scenario</span></span>

<span data-ttu-id="c198d-108">W przypadku transakcji regulowanych przez rząd system musi mieć możliwość notowania ujemnych wartości zapasów w celu zarezerwowania strat.</span><span class="sxs-lookup"><span data-stu-id="c198d-108">For government-regulated transactions, the system must be able to record negative inventory to book losses.</span></span> <span data-ttu-id="c198d-109">Towar ma mieć możliwość pokazywania ujemnego stanu magazynowego, ale tylko w wyznaczonych lokalizacjach, np. w magazynie.</span><span class="sxs-lookup"><span data-stu-id="c198d-109">You want an item to be able to show negative inventory, but only in designated locations, such as tanks.</span></span> <span data-ttu-id="c198d-110">Jeśli jednak grupa modeli pozycji zezwala na ujemne wartości zapasów, okazuje się, że w lokalizacji jest ustawiona opcja zezwalania na ujemne zapasy.</span><span class="sxs-lookup"><span data-stu-id="c198d-110">However, if the item model group allows negative inventory, you find that it doesn't matter whether the location is set to allow negative inventory.</span></span> <span data-ttu-id="c198d-111">Jeśli towar jest tak ustawiony, że ujemne zapasy nie są dozwolone, nie ma znaczenia, jak jest ustawiony profil lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c198d-111">If the item is set up so that negative inventory isn't allowed, it doesn't matter how the location profile is set up.</span></span>

## <a name="resolution"></a><span data-ttu-id="c198d-112">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="c198d-112">Resolution</span></span>

<span data-ttu-id="c198d-113">Ustawienie **Zezwalaj na ujemny stan zapasów** w profilu lokalizacji dotyczy tylko procesów magazynowych, takich jak pobieranie.</span><span class="sxs-lookup"><span data-stu-id="c198d-113">The **Allow negative inventory** setting from the location profile applies only to warehouse processes, such as picking.</span></span> <span data-ttu-id="c198d-114">Grupy modeli pozycji ustawione tak, aby zezwalały na ujemne zapasy, wpływają jednak na wszystkie procesy z modułów Zarządzanie zapasami i Zarządzanie magazynem, a profil lokalizacji nie zastąpi ustawienia.</span><span class="sxs-lookup"><span data-stu-id="c198d-114">However, item model groups that are set to allow negative inventory affect all processes from the Inventory management and Warehouse management modules, and the location profile won't override the setting.</span></span>

<span data-ttu-id="c198d-115">Istnieje możliwość kontrolowania, czy magazyn może przenosić ujemne zapasy.</span><span class="sxs-lookup"><span data-stu-id="c198d-115">You can control whether a warehouse is allowed to carry negative inventory.</span></span> <span data-ttu-id="c198d-116">Należy ustawić grupy modeli pozycji, aby nie zezwalać na ujemne wartości magazynu fizycznego, i ustawić tylko odpowiedni magazyn, aby zezwalać na ujemne zapasy.</span><span class="sxs-lookup"><span data-stu-id="c198d-116">Set your item model groups to disallow negative physical inventory, and set only the relevant warehouse to allow negative inventory.</span></span>
