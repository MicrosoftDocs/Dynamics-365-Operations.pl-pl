---
title: Amortyzacja środków trwałych dla Polski
description: Ten temat zawiera informacje o amortyzowaniu środków trwałych dla firm w Polsce.
author: ShylaThompson
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBook, AssetDepreciationGroup_W, AssetParameters, AssetPosting
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264274
ms.search.region: Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 2ffad7cd5ecc2c32bb3ca482ef176b524e8275a3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175172"
---
# <a name="fixed-assets-depreciation-for-poland"></a><span data-ttu-id="99b05-103">Amortyzacja środków trwałych dla Polski</span><span class="sxs-lookup"><span data-stu-id="99b05-103">Fixed assets depreciation for Poland</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99b05-104">Ten temat zawiera informacje o amortyzowaniu środków trwałych dla firm w Polsce.</span><span class="sxs-lookup"><span data-stu-id="99b05-104">This topic provides information about fixed assets depreciation for legal entities in Poland.</span></span>

<span data-ttu-id="99b05-105">Funkcje amortyzacji środków trwałych oparte na wymaganiach prawnych w Polsce obejmują następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="99b05-105">The Fixed assets depreciation features that are based on legal requirements in Poland include:</span></span>

-   <span data-ttu-id="99b05-106">Metody amortyzacji</span><span class="sxs-lookup"><span data-stu-id="99b05-106">Depreciation methods</span></span>
-   <span data-ttu-id="99b05-107">Poziom procentu amortyzacji</span><span class="sxs-lookup"><span data-stu-id="99b05-107">Depreciation percent level</span></span>
-   <span data-ttu-id="99b05-108">Grupy amortyzacji</span><span class="sxs-lookup"><span data-stu-id="99b05-108">Depreciation groups</span></span>
-   <span data-ttu-id="99b05-109">Ta sama data, co jest opcją w propozycji amortyzacji. Powoduje ona wypełnianie pola **Data** we wszystkich wierszach arkusza wartością z pola **Do dnia** zdefiniowanego w propozycji amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="99b05-109">The same date, which is an option in the depreciation proposal to fill in the **Date** field value in all journal lines with a **To date** value that is defined in the Depreciation proposal.</span></span>

## <a name="poland-specific-depreciation-methods"></a><span data-ttu-id="99b05-110">Metody amortyzacji specyficzne dla Polski</span><span class="sxs-lookup"><span data-stu-id="99b05-110">Poland-specific depreciation methods</span></span>
<span data-ttu-id="99b05-111">Dla firm w Polsce istnieją dodatkowe metody, reguły i ustawienia amortyzacji, które są używane do spełnienia określonych wymogów rachunkowości środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="99b05-111">For legal entities in Poland there are additional depreciation methods, rules, and settings that are used to meet specific fixed asset accounting requirements.</span></span> <span data-ttu-id="99b05-112">Zgodnie z polskimi przepisami amortyzacja jest obliczana przy użyciu rocznej stawki amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="99b05-112">According to Polish regulations, depreciation is calculated using a yearly depreciation rate.</span></span> <span data-ttu-id="99b05-113">Aby uzyskać więcej informacji na temat metod amortyzacji, zobacz [Amortyzacja środka trwałego](../fixed-assets/fixed-asset-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="99b05-113">For more information about depreciation methods, see [Fixed asset depreciation](../fixed-assets/fixed-asset-depreciation.md).</span></span> <span data-ttu-id="99b05-114">Dla firm w Polsce są dostępne następujące metody amortyzacji:</span><span class="sxs-lookup"><span data-stu-id="99b05-114">The following depreciation methods are available for legal entities in Poland:</span></span>

-   <span data-ttu-id="99b05-115">**Degresywna (Polska)** — Ta metoda amortyzacji uwzględnia lokalne specjalne wymogi prawne dotyczące zmiany wartości środków trwałych w trakcie roku obrachunkowego i rozpoznawania części kosztowej.</span><span class="sxs-lookup"><span data-stu-id="99b05-115">**Reducing balance (Poland)** – This depreciation method considers special local legal requirements about the value of fixed assets changing during the fiscal year and cost part recognition.</span></span> <span data-ttu-id="99b05-116">Podstawa dla tej metody amortyzacji uwzględnia następujące typy transakcji:</span><span class="sxs-lookup"><span data-stu-id="99b05-116">The base for this depreciation method includes the following transaction types:</span></span>
    -   <span data-ttu-id="99b05-117">Nabycie</span><span class="sxs-lookup"><span data-stu-id="99b05-117">Acquisition</span></span>
    -   <span data-ttu-id="99b05-118">Korekta wartości początkowej</span><span class="sxs-lookup"><span data-stu-id="99b05-118">Acquisition adjustment</span></span>
    -   <span data-ttu-id="99b05-119">Zwiększenie</span><span class="sxs-lookup"><span data-stu-id="99b05-119">Write up</span></span>
    -   <span data-ttu-id="99b05-120">Zmniejszenie</span><span class="sxs-lookup"><span data-stu-id="99b05-120">Write down</span></span>
    -   <span data-ttu-id="99b05-121">Przeszacowanie</span><span class="sxs-lookup"><span data-stu-id="99b05-121">Revaluation</span></span>
    -   <span data-ttu-id="99b05-122">Poprzednia amortyzacja</span><span class="sxs-lookup"><span data-stu-id="99b05-122">Previous depreciation</span></span>
-   <span data-ttu-id="99b05-123">**Liniowa (Polska)** — Amortyzacja jest obliczana dla pierwszego okresu na podstawie liczby dni używania środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="99b05-123">**Straight line (Poland)** – Depreciation is calculated for the first period based on the number of days that the asset was used.</span></span> <span data-ttu-id="99b05-124">Na przykład jeśli środek trwały zakupiono 15 stycznia, a okres amortyzacji rozpoczyna się 1 stycznia, amortyzacja jest obliczana dla połowy okresu.</span><span class="sxs-lookup"><span data-stu-id="99b05-124">For example, if a fixed asset was purchased on January 15 and the depreciation period starts on January 1, depreciation will be calculated for half of the period.</span></span> <span data-ttu-id="99b05-125">Podstawa dla tej metody amortyzacji uwzględnia następujące typy transakcji:</span><span class="sxs-lookup"><span data-stu-id="99b05-125">The base for this depreciation method includes the following transaction types:</span></span>
    -   <span data-ttu-id="99b05-126">Nabycie</span><span class="sxs-lookup"><span data-stu-id="99b05-126">Acquisition</span></span>
    -   <span data-ttu-id="99b05-127">Korekta wartości początkowej</span><span class="sxs-lookup"><span data-stu-id="99b05-127">Acquisition adjustment</span></span>
    -   <span data-ttu-id="99b05-128">Zwiększenie</span><span class="sxs-lookup"><span data-stu-id="99b05-128">Write up</span></span>
    -   <span data-ttu-id="99b05-129">Zmniejszenie</span><span class="sxs-lookup"><span data-stu-id="99b05-129">Write down</span></span>
    -   <span data-ttu-id="99b05-130">Przeszacowanie</span><span class="sxs-lookup"><span data-stu-id="99b05-130">Revaluation</span></span>
-   <span data-ttu-id="99b05-131">**Liniowa procentowa (Polska)** — Okres użytkowania jest obliczany przez wprowadzenie wartości procentowej i podzielenie 100% przez wprowadzony procent.</span><span class="sxs-lookup"><span data-stu-id="99b05-131">**Straight line percentage (Poland)** – The service life is calculated by entering a percentage and dividing 100 percent by the percentage entered.</span></span> <span data-ttu-id="99b05-132">Na przykład jeśli wprowadzono 20%, 100% podzielone przez 20% to 5 lat użytkowania.</span><span class="sxs-lookup"><span data-stu-id="99b05-132">For example, if you entered 20 percent, 100 percent divided by 20 percent is 5 service years.</span></span> <span data-ttu-id="99b05-133">Podstawa dla tej metody amortyzacji uwzględnia następujące typy transakcji:</span><span class="sxs-lookup"><span data-stu-id="99b05-133">The base for this depreciation method includes the following transaction types:</span></span>
    -   <span data-ttu-id="99b05-134">Nabycie</span><span class="sxs-lookup"><span data-stu-id="99b05-134">Acquisition</span></span>
    -   <span data-ttu-id="99b05-135">Korekta wartości początkowej</span><span class="sxs-lookup"><span data-stu-id="99b05-135">Acquisition adjustment</span></span>
    -   <span data-ttu-id="99b05-136">Zwiększenie</span><span class="sxs-lookup"><span data-stu-id="99b05-136">Write up</span></span>
    -   <span data-ttu-id="99b05-137">Zmniejszenie</span><span class="sxs-lookup"><span data-stu-id="99b05-137">Write down</span></span>
    -   <span data-ttu-id="99b05-138">Przeszacowanie</span><span class="sxs-lookup"><span data-stu-id="99b05-138">Revaluation</span></span>

<span data-ttu-id="99b05-139">Aby uzyskać więcej informacji na temat metod amortyzacji, zobacz [Amortyzacja środka trwałego](../fixed-assets/fixed-asset-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="99b05-139">For more information about depreciation methods, see [Fixed asset depreciation](../fixed-assets/fixed-asset-depreciation.md).</span></span>

## <a name="depreciation-percent-level-parameter"></a><span data-ttu-id="99b05-140">Parametr Poziom procentu amortyzacji</span><span class="sxs-lookup"><span data-stu-id="99b05-140">Depreciation percent level parameter</span></span>
<span data-ttu-id="99b05-141">Metody amortyzacji Degresywna (Polska) i Liniowa procentowa (Polska) używają pola **Poziom procentu amortyzacji** znajdującego się na stronie **Parametry środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="99b05-141">Reducing balance (Poland) and Straight line percentage (Poland) depreciation methods use the **Depreciation percent level** field on the **Fixed assets parameters** page.</span></span> <span data-ttu-id="99b05-142">To pole pozwala wybrać, czy na potrzeby obliczenia amortyzacji poziom procentu amortyzacji ma być pobierany z metody amortyzacji czy z konkretnego środka trwałego:</span><span class="sxs-lookup"><span data-stu-id="99b05-142">This field allows you to choose if the depreciation percent level should be taken from either the depreciation method or an individual fixed asset to calculate depreciation:</span></span>

-   <span data-ttu-id="99b05-143">**Profil (standardowy)** — Wybierz tę opcję, aby używać wartości procentowej z\*\* \*\*profilu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="99b05-143">**Profile (standard)** – Select this option to use the percentage from the\*\* \*\*depreciation profile.</span></span>
-   <span data-ttu-id="99b05-144">**Księga środków trwałych** — Wybierz tę opcję, aby używać tej samej metody amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="99b05-144">**Fixed asset book** – Select this option to use the same depreciation method.</span></span> <span data-ttu-id="99b05-145">Amortyzacja będzie obliczana przy użyciu wartości procentowej z księgi środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="99b05-145">The depreciation will be calculated using the percentage on the Fixed assets book.</span></span>

## <a name="depreciation-groups"></a><span data-ttu-id="99b05-146">Grupy amortyzacji</span><span class="sxs-lookup"><span data-stu-id="99b05-146">Depreciation groups</span></span>
<span data-ttu-id="99b05-147">Firmy w Polsce mogą łączyć środki trwałe z grupami amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="99b05-147">Legal entities in Poland can link fixed assets to depreciation groups.</span></span> <span data-ttu-id="99b05-148">Grupy amortyzacji są definiowane dla księgi środków trwałych w celu określenia szczegółów środków trwałych, takich jak współczynnik podwyższający, współczynnik alternatywny i limit kosztu.</span><span class="sxs-lookup"><span data-stu-id="99b05-148">Depreciation groups are defined for a fixed asset book to specify fixed asset details such as increasing factor, alternative factor, or cost limit.</span></span> <span data-ttu-id="99b05-149">Jeśli grupa amortyzacji jest przypisana do środka trwałego, kontroluje kwotę amortyzacji za pomocą współczynnika podwyższającego, przez który jest mnożona kwota amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="99b05-149">If a depreciation group is assigned to a fixed asset, the depreciation group controls the depreciation amount, using an increasing factor by which the depreciation amount is multiplied.</span></span> <span data-ttu-id="99b05-150">Na stronie **Grupy amortyzacji** można tworzyć i edytować następujące grupy amortyzacji:</span><span class="sxs-lookup"><span data-stu-id="99b05-150">Create or edit the following depreciation groups on the **Depreciation group** page.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="99b05-151"><strong>Nazwa pola</strong></span><span class="sxs-lookup"><span data-stu-id="99b05-151"><strong>Field name</strong></span></span></td>
<td><span data-ttu-id="99b05-152"><strong>Opis</strong></span><span class="sxs-lookup"><span data-stu-id="99b05-152"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="99b05-153"><strong>Data początkowa</strong></span><span class="sxs-lookup"><span data-stu-id="99b05-153"><strong>Start date</strong></span></span></td>
<td><span data-ttu-id="99b05-154">Dzień, w którym zostaną użyte wartości współczynnika podwyższającego i limitu kosztu.</span><span class="sxs-lookup"><span data-stu-id="99b05-154">Date that the Increasing factor and cost limit value will be used.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="99b05-155"><strong>Współczynnik podwyższający</strong></span><span class="sxs-lookup"><span data-stu-id="99b05-155"><strong>Increasing factor</strong></span></span></td>
<td><span data-ttu-id="99b05-156">Wskaźnik, przez który jest mnożona kwota amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="99b05-156">Factor which multiplies the depreciation amount.</span></span> <span data-ttu-id="99b05-157">Współczynnik podwyższający można skonfigurować, gdy jest używany profil amortyzacji alternatywnej (współczynnik alternatywny) lub profil amortyzacji dodatkowej (współczynnik dodatkowy).</span><span class="sxs-lookup"><span data-stu-id="99b05-157">An increasing factor can be set up if an alternative depreciation profile (alternative factor) or extraordinary depreciation profile (extraordinary factor) are used.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="99b05-158"><strong>Współczynnik alternatywny</strong></span><span class="sxs-lookup"><span data-stu-id="99b05-158"><strong>Alternative factor</strong></span></span></td>
<td><span data-ttu-id="99b05-159">Alternatywny współczynnik wartości amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="99b05-159">The alternative factor of the depreciation value.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="99b05-160"><strong>Limit kosztu</strong></span><span class="sxs-lookup"><span data-stu-id="99b05-160"><strong>Cost limit</strong></span></span></td>
<td><span data-ttu-id="99b05-161">Kwota ceny nabycia, która zostanie zaksięgowana na osobnym koncie amortyzacji niekosztowej.</span><span class="sxs-lookup"><span data-stu-id="99b05-161">Amount of acquisition price, which will be posted to a separate account for non-cost depreciation.</span></span> <span data-ttu-id="99b05-162">Kwoty do zaksięgowania na koncie amortyzacji niekosztowej są obliczane w trakcie formułowania propozycji amortyzacji, która dzieli pełne obliczenie amortyzacji na dwa wiersze:</span><span class="sxs-lookup"><span data-stu-id="99b05-162">Amounts to be posted to the account for non-cost depreciation are calculated during depreciation proposal, which splits the full depreciation calculation into two lines:</span></span>
<ul>
<li><span data-ttu-id="99b05-163"><strong>(Skorygowana) Amortyzacja</strong> — Pełna kwota amortyzacji obliczona na podstawie konfiguracji w księdze środków trwałych minus część związana z amortyzacją niekosztową (część = limit kosztu podzielony przez podstawę amortyzacji).</span><span class="sxs-lookup"><span data-stu-id="99b05-163"><strong>(Adjusted) Depreciation</strong> -The full depreciation amount calculated based on fixed asset book setup minus the portion related to non-cost depreciation (Portion = Cost limit divided by Depreciation base).</span></span> <span data-ttu-id="99b05-164">Ta amortyzacja jest księgowana na kontach amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="99b05-164">This depreciation is posted to accounts for depreciation.</span></span></li>
<li><span data-ttu-id="99b05-165"><strong>Część niekosztowa amortyzacji</strong> - Część amortyzacji związana z limitem kosztu.</span><span class="sxs-lookup"><span data-stu-id="99b05-165"><strong>Non-cost part of Depreciation</strong> - A portion of depreciation related to the cost limit.</span></span> <span data-ttu-id="99b05-166">Ta amortyzacja jest księgowana na kontach amortyzacji niekosztowej.</span><span class="sxs-lookup"><span data-stu-id="99b05-166">This depreciation is posted to accounts for non-cost depreciation.</span></span> <span data-ttu-id="99b05-167">Aby skonfigurować konta amortyzacji niekosztowej, wybierz kolejno opcje <strong>Środki trwałe</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Profile księgowania środków trwałych</strong>, a następnie na skróconej karcie <strong>Konto księgowe</strong> wybierz opcję <strong>Amortyzacja niekosztowa</strong>.</span><span class="sxs-lookup"><span data-stu-id="99b05-167">To set up accounts for non-cost depreciation, open <strong>Fixed assets</strong> &gt; <strong>Setup</strong> &gt; <strong>Fixed asset posting</strong> profiles, and select <strong>Non-cost depreciation</strong> in the <strong>Ledger account</strong> FastTab.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>





