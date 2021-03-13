---
title: Chronologicznie numerowanie dokumentów i załączników
description: W tym temacie wyjaśniono, jak skonfigurować i używać numerów chronologicznych dla odpowiednich dokumentów i powiązanych faktur obcych.
author: ikond
manager: AnnBe
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 31745632de7339d167ac9f18f02e6611e1a78b28
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104427"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a><span data-ttu-id="7e4bb-103">Chronologicznie numerowanie dokumentów i załączników</span><span class="sxs-lookup"><span data-stu-id="7e4bb-103">Numbering documents and vouchers chronologically</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="7e4bb-104">W niektórych krajach istnieje prawny wymóg numeracji dokumentów i powiązanych załączników w porządku chronologicznym.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-104">In some countries, there is a legal requirement to number documents and related vouchers in chronological order.</span></span> <span data-ttu-id="7e4bb-105">Chronologia musi być obsługiwana według okresów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-105">The chronology must be supported by periods.</span></span> <span data-ttu-id="7e4bb-106">Wszystkie numery należące do poprzednich okresów muszą być mniejsze od numerów należących do późniejszych okresów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-106">All of the numbers that belong to earlier periods must be less than the numbers that belong to later periods.</span></span> <span data-ttu-id="7e4bb-107">Aby spełnić to wymaganie, zaimplementowano funkcje numerowania chronologicznego.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-107">To meet this requirement, chronological numbering functionality has been implemented.</span></span> <span data-ttu-id="7e4bb-108">W tym temacie wyjaśniono, jak skonfigurować i używać numerów chronologicznych dla odpowiednich dokumentów i powiązanych faktur obcych.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-108">This topic explains how to configure and use chronological numbers for applicable documents and related vouchers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7e4bb-109">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="7e4bb-109">Prerequisites</span></span>

<span data-ttu-id="7e4bb-110">W obszarze roboczym Zarządzanie funkcjami włącz następujące funkcję **Chronologiczne numerowanie**:</span><span class="sxs-lookup"><span data-stu-id="7e4bb-110">In the Feature management workspace, turn on the **Chronological numbering** feature.</span></span> <span data-ttu-id="7e4bb-111">Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7e4bb-111">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="configure-chronological-numbering"></a><span data-ttu-id="7e4bb-112">Konfiguruj numerowanie chronologiczne</span><span class="sxs-lookup"><span data-stu-id="7e4bb-112">Configure chronological numbering</span></span>

<span data-ttu-id="7e4bb-113">Numeracja chronologicznej wpływa na następujące dokumenty.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-113">Chronological numbering affects the following documents.</span></span>

<span data-ttu-id="7e4bb-114">**Rozrachunki z odbiorcami**</span><span class="sxs-lookup"><span data-stu-id="7e4bb-114">**Accounts receivable**</span></span>
- <span data-ttu-id="7e4bb-115">Faktura dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="7e4bb-115">Customer invoice</span></span>
- <span data-ttu-id="7e4bb-116">Załącznik faktury dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="7e4bb-116">Customer invoice voucher</span></span>
- <span data-ttu-id="7e4bb-117">Faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="7e4bb-117">Sales credit note</span></span>
- <span data-ttu-id="7e4bb-118">Załącznik faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="7e4bb-118">Sales credit note voucher</span></span>
- <span data-ttu-id="7e4bb-119">Faktura niezależna</span><span class="sxs-lookup"><span data-stu-id="7e4bb-119">Free text invoice</span></span>
- <span data-ttu-id="7e4bb-120">Załącznik faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="7e4bb-120">Free text invoice voucher</span></span>
- <span data-ttu-id="7e4bb-121">Niezależna faktura korygująca</span><span class="sxs-lookup"><span data-stu-id="7e4bb-121">Free text credit note</span></span>
- <span data-ttu-id="7e4bb-122">Załącznik niezależnej faktury korygującej</span><span class="sxs-lookup"><span data-stu-id="7e4bb-122">Free text credit note voucher</span></span>
- <span data-ttu-id="7e4bb-123">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="7e4bb-123">Packing slip</span></span>
- <span data-ttu-id="7e4bb-124">Załącznik dokumentu dostawy</span><span class="sxs-lookup"><span data-stu-id="7e4bb-124">Packing slip voucher</span></span>
- <span data-ttu-id="7e4bb-125">Załącznik korekty dokumentu dostawcy</span><span class="sxs-lookup"><span data-stu-id="7e4bb-125">Packing slip correction voucher</span></span>
- <span data-ttu-id="7e4bb-126">Załącznik noty odsetkowej</span><span class="sxs-lookup"><span data-stu-id="7e4bb-126">Interest note voucher</span></span>
- <span data-ttu-id="7e4bb-127">Załącznik z ponagleniem</span><span class="sxs-lookup"><span data-stu-id="7e4bb-127">Collection letter voucher</span></span>

<span data-ttu-id="7e4bb-128">**Rozrachunki z dostawcami**</span><span class="sxs-lookup"><span data-stu-id="7e4bb-128">**Accounts payable**</span></span>
- <span data-ttu-id="7e4bb-129">Załącznik faktury</span><span class="sxs-lookup"><span data-stu-id="7e4bb-129">Invoice voucher</span></span>
- <span data-ttu-id="7e4bb-130">Załącznik faktury korygującej</span><span class="sxs-lookup"><span data-stu-id="7e4bb-130">Credit note voucher</span></span>
- <span data-ttu-id="7e4bb-131">Załącznik dokumentu przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="7e4bb-131">Product receipt voucher</span></span>

<span data-ttu-id="7e4bb-132">**Zarządzanie projektami**</span><span class="sxs-lookup"><span data-stu-id="7e4bb-132">**Project management**</span></span>
- <span data-ttu-id="7e4bb-133">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="7e4bb-133">Invoice</span></span>
- <span data-ttu-id="7e4bb-134">Załącznik faktury</span><span class="sxs-lookup"><span data-stu-id="7e4bb-134">Invoice voucher</span></span>
- <span data-ttu-id="7e4bb-135">Faktura kredytowa</span><span class="sxs-lookup"><span data-stu-id="7e4bb-135">Credit note</span></span>
- <span data-ttu-id="7e4bb-136">Załącznik faktury korygującej</span><span class="sxs-lookup"><span data-stu-id="7e4bb-136">Credit note voucher</span></span> 

### <a name="define-number-sequences"></a><span data-ttu-id="7e4bb-137">Zdefiniuj sekwencje liczb</span><span class="sxs-lookup"><span data-stu-id="7e4bb-137">Define number sequences</span></span>

<span data-ttu-id="7e4bb-138">Aby zdefiniować sekwencje numerów, przejdź do **Administrowanie organizacją** > **Numery kolejne** > **Numery kolejne**.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-138">To define number sequences, go to **Organization administration** > **Number sequences** > **Number sequences**.</span></span> <span data-ttu-id="7e4bb-139">Można zdefiniować dowolną liczbę sekwencji numerów, aby objąć odpowiednie okresy dla wymaganych dokumentów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-139">You can define as many number sequences as required to cover the affected periods for required documents.</span></span> 

<span data-ttu-id="7e4bb-140">Określ firmę dla każdej sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-140">Specify a company for each number sequence.</span></span> <span data-ttu-id="7e4bb-141">Segmenty ciągów liczbowych należy zdefiniować w taki sposób, aby zapewniały chronologiczną kolejność okresów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-141">The segments of the number sequences must be defined so that they provide chronological order for periods.</span></span> <span data-ttu-id="7e4bb-142">Na przykład nazwy segmentów mogą zawierać specjalny przedrostek identyfikujący określony okres.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-142">For example, the segment names can contain a special prefix that identifies a specific period.</span></span>

![Ustawienia sekwencji numerów](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a><span data-ttu-id="7e4bb-144">Konfigurowanie sekwencji identyfikatorów grup</span><span class="sxs-lookup"><span data-stu-id="7e4bb-144">Configure number sequence groups</span></span>

<span data-ttu-id="7e4bb-145">Aby skonfigurować grupy sekwencji numerów, przejdź do **Rozrachunki z odbiorcami** > **Konfiguracja** > **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-145">To configure number sequence groups, go to **Accounts receivable** > **Setup** > **Accounts receivable parameters**.</span></span> <span data-ttu-id="7e4bb-146">Na karcie **Sekwencje numerów** zdefiniuj wymaganą liczbę grup sekwencji numerów, aby pokryć koszty określonej liczby okresów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-146">On the **Number sequences** tab, define as many number sequences groups as required to cover the affected periods.</span></span> 

<span data-ttu-id="7e4bb-147">Dla każdej grupy w sekcji **Odwołanie** wybierz jedno z obsługiwanych odwołań do dokumentów, a w polu **Kod sekwencji numerów** odwołaj się do sekwencji numerów utworzonej wcześniej dla powiązanego okresu.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-147">For each group, in the **Reference** section, select one of the supported document references, and in the **Number sequence code** field, refer to a number sequence that was previously created for the related period.</span></span>

![Ustawienia grupy sekwencji numerów](media/chrono-num-sequence-group.jpg)

<span data-ttu-id="7e4bb-149">Podobnie skonfiguruj grupy sekwencji numerów w modułach **Rozrachunki z dostawcami** oraz **Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-149">Similarly, configure number sequence groups in **Accounts payable** and **Project management and accounting** modules.</span></span>

### <a name="configure-number-sequence-groups-chronology"></a><span data-ttu-id="7e4bb-150">Skonfiguruj chronologię grup sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="7e4bb-150">Configure number sequence groups chronology</span></span>

<span data-ttu-id="7e4bb-151">Aby skonfigurować chronologicznie grupy sekwencji numerów, przejdź do **Administrowanie organizacją** > **Numery kolejne** > **Chronologiczne grupy sekwencji liczb**.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-151">To configure number sequence groups chronology, go to **Organization administration** > **Number sequences** > **Chronological number sequence groups**.</span></span> <span data-ttu-id="7e4bb-152">Zdefiniuj warunki możliwości zastosowania dla grup sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-152">Define the applicability conditions for number sequence groups.</span></span>

![Ustawienia numerów chronologicznych](media/chrono-num-sequence-group-period.jpg)

| <span data-ttu-id="7e4bb-154">Pole</span><span class="sxs-lookup"><span data-stu-id="7e4bb-154">Field</span></span>            | <span data-ttu-id="7e4bb-155">opis</span><span class="sxs-lookup"><span data-stu-id="7e4bb-155">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7e4bb-156">Weszła w życie</span><span class="sxs-lookup"><span data-stu-id="7e4bb-156">Effective</span></span>  | <span data-ttu-id="7e4bb-157">Data rozpoczęcia obowiązywania grupy sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-157">The start date of number sequence group applicability.</span></span> |
| <span data-ttu-id="7e4bb-158">Data ważności</span><span class="sxs-lookup"><span data-stu-id="7e4bb-158">Expiration</span></span>      | <span data-ttu-id="7e4bb-159">Data zakończenia obowiązywania grupy sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-159">The end date of number sequence group applicability.</span></span> <span data-ttu-id="7e4bb-160">Jeśli data zakończenia nie zostanie zastosowana, wybierz opcję **Nigdy**.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-160">If no end date is applied, select **Never**.</span></span> |
| <span data-ttu-id="7e4bb-161">Grupa sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="7e4bb-161">Number sequence group</span></span> | <span data-ttu-id="7e4bb-162">Grupa sekwencji numerów, która będzie używana do generowania numerów dokumentów w okresie.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-162">Number sequence group that will be used to generate document numbers during the period.</span></span> |
| <span data-ttu-id="7e4bb-163">Oryginalna grupa sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="7e4bb-163">Original number sequence group</span></span> | <span data-ttu-id="7e4bb-164">Ten kod grupy sekwencji numerów jest używany do dodatkowego filtrowania w przypadkach, gdy dokumenty mają już przypisaną określoną *stałą* grupę numerów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-164">This number sequence group code is used for additional filtering for the cases when documents already have a specific *permanent* number sequence group assigned.</span></span> <span data-ttu-id="7e4bb-165">Wartość pusta jest uważana za określoną wartość.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-165">An empty value is considered a specific value.</span></span> <span data-ttu-id="7e4bb-166">Jeśli chcesz zignorować wstępnie przypisaną grupę, użyj opcji **Domyślna** dla tej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-166">If you need to ignore a preliminary assigned group, use the **Default** option for this setup.</span></span> |
| <span data-ttu-id="7e4bb-167">Domyślna</span><span class="sxs-lookup"><span data-stu-id="7e4bb-167">Default</span></span> | <span data-ttu-id="7e4bb-168">Jeśli ta opcja jest włączona, system ignoruje wstępnie przypisaną grupę numerów dokumentów i wykorzystuje tylko daty rozpoczęcia i zakończenia okresów do analizy stosowalności.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-168">If turned on, the system ignores the preliminary assigned document number sequence group and uses only the periods start and end dates for applicability analysis.</span></span> <span data-ttu-id="7e4bb-169">Jeśli ten tryb jest wyłączony, do wyboru jest używana pełna kombinacja **Data wprowadzenia** + **Data ważności** + **Oryginalna grupa sekwencji numerów**.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-169">If turned off, the system uses the full combination **Effective** + **Expiration** + **Original number sequence group** for selection.</span></span> |

## <a name="document-posting"></a><span data-ttu-id="7e4bb-170">Księgowanie dokumentów</span><span class="sxs-lookup"><span data-stu-id="7e4bb-170">Document posting</span></span>
<span data-ttu-id="7e4bb-171">Podczas księgowania dokumentu odpowiednia grupa numerów jest przypisywana do dokumentu na podstawie daty księgowania dokumentu, a następnie używana do generowania numeru dokumentu na podstawie wykrytej sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-171">When you post a document, the appropriate number sequence group is assigned to the document, based on document's posting date, and then used to generate a document number based on the detected number sequence.</span></span> <span data-ttu-id="7e4bb-172">System wyświetla komunikat dotyczący przypisania grup sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-172">The system provides a message regarding the number sequence group assignment.</span></span>

![Numer dokumentu](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> <span data-ttu-id="7e4bb-174">W niektórych krajach zaimplementowano już określoną logikę numeracji dokumentów.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-174">For some countries, there is a specific logic already implemented for document numbering.</span></span> <span data-ttu-id="7e4bb-175">W tym przypadku logika specyficzna dla kraju zastąpi funkcję **Numerowania chronologicznego**.</span><span class="sxs-lookup"><span data-stu-id="7e4bb-175">In this case, country-specific logic will override the **Chronological numbering** feature.</span></span>
