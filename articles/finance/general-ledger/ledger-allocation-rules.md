---
title: Reguły alokacji księgi
description: Ten artykuł zawiera informacje o regułach alokacji księgi. Opisano w nim różne składniki tych reguł alokacji oraz metody alokacji, których można do nich używać.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31e01046d22c3b7a598386d5621d020339f44cb4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249006"
---
# <a name="ledger-allocation-rules"></a><span data-ttu-id="a8cb2-104">Reguły alokacji księgi</span><span class="sxs-lookup"><span data-stu-id="a8cb2-104">Ledger allocation rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8cb2-105">Ten artykuł zawiera informacje o regułach alokacji księgi.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-105">This article provides information about ledger allocation rules.</span></span> <span data-ttu-id="a8cb2-106">Opisano w nim różne składniki tych reguł alokacji oraz metody alokacji, których można do nich używać.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-106">It describes the various components of these allocation rules and the allocation methods that can be used for them.</span></span>

<span data-ttu-id="a8cb2-107">Reguły alokacji księgi są używane do automatycznego obliczania i generowania arkuszy alokacji i zapisów na kontach dla alokacji sald księgi lub kwot stałych.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-107">Ledger allocation rules are used to automatically calculate and generate allocation journals and account entries for the allocation of ledger balances or fixed amounts.</span></span> <span data-ttu-id="a8cb2-108">Metody alokacji mogą być stałe lub zmienne.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-108">Allocation methods can be variable or fixed.</span></span> <span data-ttu-id="a8cb2-109">Dla reguł alokacji księgi można użyć następujących metod alokacji:</span><span class="sxs-lookup"><span data-stu-id="a8cb2-109">The following allocation methods can be used for ledger allocation rules:</span></span>

-   <span data-ttu-id="a8cb2-110">**Podstawy** — ta zmienna metoda jest używana, gdy alokacja zależy od rzeczywistego salda księgi na podstawie kryteriów filtra.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-110">**Basis** – This variable method is used when the allocation depends on the actual ledger balance, based on filter criteria.</span></span> <span data-ttu-id="a8cb2-111">Na przykład można alokować wydatki firmy na reklamę proporcjonalnie do udziału wielkości sprzedaży poszczególnych działów w łącznej wielkości sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-111">For example, advertising expenses can be allocated based on each department's sales in proportion to the total departmental sales.</span></span>
-   <span data-ttu-id="a8cb2-112">**Stały procent** i **Stała waga** — dla tych metod procent alokacji lub waga są zdefiniowane bezpośrednio dla reguły.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-112">**Fixed percentage** and **Fixed weight** – For these methods, the allocation percentage or weight is defined directly for the rule.</span></span> <span data-ttu-id="a8cb2-113">Na przykład wydatki na reklamę można alokować w taki sposób, by Dział A miał przypisane 70 procent wydatków na reklamę, a Dział B miał 30 procent.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-113">For example, advertising expenses can be allocated so that Department A receives 70 percent of the advertising expense and Department B receives 30 percent.</span></span>
-   <span data-ttu-id="a8cb2-114">**Równo** — ta metoda rozprowadza kwotę równomiernie do każdego zdefiniowanego miejsca docelowego.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-114">**Equally** – This method distributes the amount equally to each defined destination.</span></span> <span data-ttu-id="a8cb2-115">Jeśli na przykład zdefiniowano miejsca docelowe dla Działu A i Działu B, wydatki na reklamę można alokować, tak aby do obu działów zostało przypisane po 50% wydatków na reklamę.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-115">For example, if destinations are defined for Department A and Department B, advertising expenses can be allocated so that both Department A and Department B receive 50 percent of the advertising expense.</span></span>

<span data-ttu-id="a8cb2-116">Jeśli dla reguły alokacji używana jest metoda Podstawa, to trzeba też zdefiniować oddzielne reguły podstawy alokacji w księgowaniu.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-116">If Basis is used as the allocation method for an allocation rule, you must also define separate ledger allocation basis rules.</span></span> <span data-ttu-id="a8cb2-117">Proces „Przetwarzanie żądania alokacji” pozwala użytkownikom przetwarzać regułę alokacji księgi i wyświetlać podgląd wynikowych wpisów arkusza przed zaksięgowaniem lub usunięciem obliczonych alokacji.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-117">The "Process allocation request" process lets users process the ledger allocation rule and preview the resulting allocation journal entries before they either post or delete the calculated allocations.</span></span>

## <a name="components-of-ledger-allocation-rules"></a><span data-ttu-id="a8cb2-118">Składniki reguł alokacji księgi</span><span class="sxs-lookup"><span data-stu-id="a8cb2-118">Components of ledger allocation rules</span></span>
<span data-ttu-id="a8cb2-119">W każdej regule alokacji występują cztery składniki — ogólny, źródłowy, celu oraz przeciwstawny.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-119">Each allocation rule has four components: general, source, destination, and offset.</span></span> <span data-ttu-id="a8cb2-120">Dodatkowy składnik, zasady podstawy alokacji księgi, jest wymagany, jeśli metodą alokacji jest Podstawa.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-120">An additional component, ledger allocation bases rules, is required if Basis is used as the allocation method.</span></span> <span data-ttu-id="a8cb2-121">Każdy składnik zawiera istotne informacje niezbędne do przetwarzania alokacji.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-121">Each component provides a critical piece of the information that is required in order to process allocations.</span></span>

-   <span data-ttu-id="a8cb2-122">**Ogólne** — ten składnik określa opcje odnoszące do metody alokacji, ustawień reguł między firmami oraz aktywności reguł.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-122">**General** – This component is where the user specifies options such as the allocation method, intercompany rule settings, and whether the rule is active.</span></span>
-   <span data-ttu-id="a8cb2-123">**Źródło** — ten składnik jest używany gdy użytkownik określa dane źródłowe dla alokacji.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-123">**Source** – This component is where the user specifies the source data for the allocation.</span></span> <span data-ttu-id="a8cb2-124">Alokacja może opierać się na saldach księgi (**Źródło danych** = **Księga**) lub stałych kwotach (**Źródło danych** = **Stała wartość**).</span><span class="sxs-lookup"><span data-stu-id="a8cb2-124">Allocation can be based on ledger balances (**Data source** = **Ledger**) or fixed amounts (**Data source** = **Fixed value**).</span></span> <span data-ttu-id="a8cb2-125">Gdy **Źródło danych** ma wartość **Księga**, kryteria filtra źródła muszą być zdefiniowane dla reguły alokacji księgi (np. dla wydatków na reklamę).</span><span class="sxs-lookup"><span data-stu-id="a8cb2-125">When **Data source** is set to **Ledger**, source filter criteria must be defined for the ledger allocation rule (for example, for the advertising expenses).</span></span>
-   <span data-ttu-id="a8cb2-126">**Cel** — ten składnik określa sposób dystrybuowania i rozliczania wyniku obliczeń alokacji.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-126">**Destination** – This component defines how the result of the allocation calculation should be distributed and accounted for.</span></span> <span data-ttu-id="a8cb2-127">Można na przykład określić po jednym wierszu celu dla każdego oddziału.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-127">For example, there can be one destination line for each department.</span></span>
-   <span data-ttu-id="a8cb2-128">**Konto przeciwstawne** — ten składnik określa sposób określania kont głównych i wymiarów dla zapisów przeciwstawnych bilansujących zapisy docelowe.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-128">**Offset** – This component defines how main accounts and dimensions should be determined for the offset entries that balance the destination entries.</span></span> <span data-ttu-id="a8cb2-129">Zazwyczaj używane są opcje zdefiniowane przez użytkownika zamiast kont i wymiarów opartych na źródle.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-129">User-defined options are typically used instead of accounts and dimensions that are based on the source.</span></span> <span data-ttu-id="a8cb2-130">Jeśli **Źródło danych** ma wartość **Stała wartość**, **Źródło** nie może być używane jako opcja.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-130">When **Data source** is set to **Fixed value**, **Source** can't be used as an option.</span></span>
-   <span data-ttu-id="a8cb2-131">**Reguły podstawy alokacji księgi** — te reguły mają własne kryteria filtru źródła, które określają, które salda ksiąg powinny być używane do alokacji (np. przychód na oddział).</span><span class="sxs-lookup"><span data-stu-id="a8cb2-131">**Ledger allocation basis rules** – These rules use their own source filter criteria to determine which ledger balances should be used for allocation (for example, the revenue per department).</span></span> <span data-ttu-id="a8cb2-132">Każda reguła podstawy alokacji może być stosowana z wieloma regułami alokacji.</span><span class="sxs-lookup"><span data-stu-id="a8cb2-132">Each allocation basis rule can be used with multiple allocation rules.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]