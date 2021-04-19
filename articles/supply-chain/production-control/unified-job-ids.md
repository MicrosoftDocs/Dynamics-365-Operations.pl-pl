---
title: Zunifikowana sekwencja numerów dla identyfikatorów zadań
description: Ta funkcja udostępnia pojedynczą, ujednoliconą sekwencję numerów, która generuje identyfikatory zadań w modułach Kontrola produkcji, Wykonywanie produkcji oraz Czas i frekwencja.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824949"
---
# <a name="unified-number-sequence-for-job-ids"></a><span data-ttu-id="a62bb-103">Zunifikowana sekwencja numerów dla identyfikatorów zadań</span><span class="sxs-lookup"><span data-stu-id="a62bb-103">Unified number sequence for job IDs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a62bb-104">Ta funkcja udostępnia pojedynczą, ujednoliconą sekwencję numerów, która generuje identyfikatory zadań w modułach Kontrola produkcji, Wykonywanie produkcji oraz Czas i frekwencja.</span><span class="sxs-lookup"><span data-stu-id="a62bb-104">This feature provides a single, unified number sequence that generates job IDs for the Production control, Manufacturing execution, and Time and attendance modules.</span></span> <span data-ttu-id="a62bb-105">Wcześniej można było wybrać inną sekwencję numerów dla każdego z tych modułów, co może spowodować konflikt identyfikatorów zadań, jeśli co najmniej dwie sekwencje użyły identycznego formatu.</span><span class="sxs-lookup"><span data-stu-id="a62bb-105">Previously, you were able to choose a different number sequence for each of these modules, which could result in conflicting job IDs if two or more of these sequences used an identical format.</span></span> <span data-ttu-id="a62bb-106">Taki konflikt może spowodować uszkodzenie danych.</span><span class="sxs-lookup"><span data-stu-id="a62bb-106">Such a conflict can cause data corruption.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="a62bb-107">Włączanie funkcji w systemie</span><span class="sxs-lookup"><span data-stu-id="a62bb-107">Turn on this feature for your system</span></span>

<span data-ttu-id="a62bb-108">Jeśli Twój system nie zawiera jeszcze funkcji opisanych w tym temacie, przejdź do [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Ujednolicona sekwencja numerów dla identyfikatorów zadań*.</span><span class="sxs-lookup"><span data-stu-id="a62bb-108">If your system doesn't already include the feature described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Unified number sequence for job IDs* feature.</span></span>

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a><span data-ttu-id="a62bb-109">Skonfiguruj ujednoliconą sekwencję numerów dla identyfikatorów zadań</span><span class="sxs-lookup"><span data-stu-id="a62bb-109">Set up the unified number sequence for job IDs</span></span>

<span data-ttu-id="a62bb-110">Po włączeniu tej funkcji istniejące ustawienia sekwencji numerów **identyfikacyjnych zadania** znajdujące się na stronach parametrów dla modułów Kontrola produkcji, Realizacja produkcji oraz Czas i obecność zostaną wycofane i zostanie dodane nowe pole **Ujednoliconego identyfikatora zadania**.</span><span class="sxs-lookup"><span data-stu-id="a62bb-110">After enabling this feature, the existing **Job identification** number-sequence settings located on the parameters pages for the Production control, Manufacturing execution, and Time and attendance modules will be deprecated and a new **Unified job ID** field will be added.</span></span> <span data-ttu-id="a62bb-111">Wartość **Ujednoliconego identyfikatora zadania** jest współużytkowana przez wszystkie trzy moduły, dzięki czemu wszystkie moduły odwołują się do tej samej sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="a62bb-111">The **Unified job ID** value is shared by all three modules, thus ensuring that all modules reference the same number sequence.</span></span> <span data-ttu-id="a62bb-112">Identyfikatory zadań będą więc unikatowe we wszystkich trzech modułach i nigdy nie wystąpi konflikt.</span><span class="sxs-lookup"><span data-stu-id="a62bb-112">Job IDs will therefore be unique across all three modules and a conflict will never occur.</span></span>

<span data-ttu-id="a62bb-113">Skonfiguruj ujednoliconą sekwencję numerów dla identyfikatorów zadań:</span><span class="sxs-lookup"><span data-stu-id="a62bb-113">To set up the unified number sequence for job IDs:</span></span>

1. <span data-ttu-id="a62bb-114">Włącz tę funkcję, tak jak opisano w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="a62bb-114">Turn on the feature as described in the previous section.</span></span>
1. <span data-ttu-id="a62bb-115">Określ sekwencję numerów, która ma być użyciu dla identyfikatorów zunifikowanych zadań, lub utwórz nowy.</span><span class="sxs-lookup"><span data-stu-id="a62bb-115">Either identify the number sequence you want to use for your unified job IDs, or create a new one.</span></span> <span data-ttu-id="a62bb-116">Aby uzyskać więcej informacji, zobacz temat [Omówienie sekwencji identyfikatorów](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a62bb-116">For more information, see [Number sequences overview](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span></span>
1. <span data-ttu-id="a62bb-117">Przejdź do strony **Parametry kontroli produkcji**, **Parametry wykonania produkcji** lub **Strona parametrów czasu i frekwencji**.</span><span class="sxs-lookup"><span data-stu-id="a62bb-117">Go to the **Production control parameters**, **Manufacturing execution parameters**, or **Time and attendance parameters** page.</span></span> <span data-ttu-id="a62bb-118">Nie ma znaczenia, którą z nich wybierzesz, ponieważ po ustawieniu tego ustawienia na dowolnej z tych stron wszystkie pozostałe strony zostaną automatycznie aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="a62bb-118">It doesn't matter which one you choose because when you make this setting on any of those pages, all of the other pages will update automatically.</span></span>
1. <span data-ttu-id="a62bb-119">Otwórz kartę **Sekwencje numerów** na wybranej stronie parametrów.</span><span class="sxs-lookup"><span data-stu-id="a62bb-119">Open the **Number sequences** tab on your selected parameters page.</span></span>
1. <span data-ttu-id="a62bb-120">Przypisz **Kod sekwencji numerów**, który wcześniej określono, do wiersza **Ujednoliconych identyfikatorów zadań** w siatce.</span><span class="sxs-lookup"><span data-stu-id="a62bb-120">Assign the **Number sequence code** that you identified previously to the **Unified job IDs** row of the grid.</span></span>
