---
title: "Sekwencje identyfikatorów"
description: "Sekwencje numerów są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które muszą mieć identyfikatory."
author: MargoC
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: NumberSequenceTableListPage, NumberSequenceConfiguration
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a290f6f453d8440d6e68a13915339d3da31d959a
ms.openlocfilehash: 353113d7c7341eab567224a0d3508f6fdb7bdcec
ms.contentlocale: pl-pl
ms.lasthandoff: 04/03/2018

---

# <a name="number-sequences"></a><span data-ttu-id="4606d-103">Sekwencje identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="4606d-103">Number sequences</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4606d-104">Sekwencje numerów są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które muszą mieć identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="4606d-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require identifiers.</span></span> <span data-ttu-id="4606d-105">Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do *odwołania*.</span><span class="sxs-lookup"><span data-stu-id="4606d-105">A master data record or transaction record that requires an identifier is referred to as a *reference*.</span></span>

<span data-ttu-id="4606d-106">Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem.</span><span class="sxs-lookup"><span data-stu-id="4606d-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="4606d-107">Zaleca się użycie stron w **Administrowaniu organizacją** do ustawiania sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="4606d-107">We recommend that you use the pages in **Organization administration** to set up number sequences.</span></span> <span data-ttu-id="4606d-108">Jeśli wymagane są ustawienia zależne od modułu, można użyć strony parametrów w module do określania sekwencji numerów dla odwołań w module.</span><span class="sxs-lookup"><span data-stu-id="4606d-108">If module-specific settings are required, you can use the parameters page in a module to specify number sequences for the references in that module.</span></span> <span data-ttu-id="4606d-109">Na przykład w **Rozrachunkach z odbiorcami** i **Rozrachunki z dostawcami**, aby przydzielić odpowiednie sekwencje numerów określonym odbiorcom lub dostawcom można skonfigurować grupy sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="4606d-109">For example, in **Accounts receivable** and **Accounts payable**, you can set up number sequence groups to allocate specific number sequences to specific customers or vendors.</span></span> 

<span data-ttu-id="4606d-110">Podczas konfigurowania sekwencji numerów, należy wyznaczyć zakres określający, która organizacja używa sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="4606d-110">When you set up a number sequence, you must specify a scope, which defines which organization uses the number sequence.</span></span> <span data-ttu-id="4606d-111">Zakres może mieć wartość **Współdzielony**, **Firma**, **Podmiot prawny** lub **Jednostka operacyjna**.</span><span class="sxs-lookup"><span data-stu-id="4606d-111">The scope can be **Shared**, **Company**, **Legal entity**, or **Operating unit**.</span></span> <span data-ttu-id="4606d-112">Zakresy **Podmiot prawny** i **Jednostka** można łączyć z **Okresem kalendarza obrachunkowego** w celu tworzenia bardziej odpowiednich sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="4606d-112">**Legal entity** and **Company** scopes can be combined with **Fiscal calendar period** to create even more specific number sequences.</span></span> 

<span data-ttu-id="4606d-113">Formaty sekwencji numerów składają się z segmentów.</span><span class="sxs-lookup"><span data-stu-id="4606d-113">Number sequence formats consist of segments.</span></span> <span data-ttu-id="4606d-114">Sekwencje numerów o zakresie innym niż **Współdzielony** mogą mieć segmenty odpowiadające ich zakresowi.</span><span class="sxs-lookup"><span data-stu-id="4606d-114">Number sequences with a scope other than **Shared** can contain segments that correspond to the scope.</span></span> <span data-ttu-id="4606d-115">Na przykład sekwencja numerów z zakresem **Firma** może zawierać segment firmy.</span><span class="sxs-lookup"><span data-stu-id="4606d-115">For example, a number sequence with a scope of **Legal entity** can contain a legal entity segment.</span></span> <span data-ttu-id="4606d-116">Dołączając segment zakresu do formatu sekwencji numerów, można określić zakres określonego rekordu, sprawdzając jego numer.</span><span class="sxs-lookup"><span data-stu-id="4606d-116">By including a scope segment in the number sequence format, you can identify the scope of a particular record by looking at its number.</span></span> 

<span data-ttu-id="4606d-117">Oprócz segmentów, które odpowiadają zakresom, formaty sekwencji numerów mogą zawierać segmenty **Stałe** i **Alfanumeryczne**.</span><span class="sxs-lookup"><span data-stu-id="4606d-117">In addition to segments that correspond to scopes, number sequence formats can contain **Constant** and **Alphanumeric segments**.</span></span> <span data-ttu-id="4606d-118">Segment **Stałe** zawiera zbiór litery, cyfry i symboli, który nie jest zmieniany.</span><span class="sxs-lookup"><span data-stu-id="4606d-118">A **Constant** segment contains a set of letters, numbers, or symbols that does not change.</span></span> <span data-ttu-id="4606d-119">Segment **Alfanumeryczne** zawiera zestaw liter lub cyfr, które przyrastają przy każdym użyciu numeru.</span><span class="sxs-lookup"><span data-stu-id="4606d-119">An **Alphanumeric** segment contains a set of letters or numbers that increment every time that a number is used.</span></span> <span data-ttu-id="4606d-120">Użyj znaku cyfry (\#), aby przedstawić numery rosnąco, i znaku handlowego „i” (&), aby przedstawić litery rosnąco.</span><span class="sxs-lookup"><span data-stu-id="4606d-120">Use a number sign (\#) to represent incrementing numbers and an ampersand (&) to represent incrementing letters.</span></span> <span data-ttu-id="4606d-121">Na przykład format \#\#\#\#\#\_2017 tworzy sekwencję 00001\_2017, 00002\_2017 i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="4606d-121">For example, the format \#\#\#\#\#\_2017 creates the sequence 00001\_2017, 00002\_2017, and so on.</span></span>

<a name="number-sequence-examples"></a><span data-ttu-id="4606d-122">Przykłady sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="4606d-122">Number sequence examples</span></span>
------------------------

<span data-ttu-id="4606d-123">Poniższe przykłady przedstawiają metody korzystania z segmentów do tworzenia formatów sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="4606d-123">The following examples show how to use segments to create number sequence formats.</span></span> <span data-ttu-id="4606d-124">W szczególności w przykładach tych przedstawiono efekty użycia segmentów zakresu.</span><span class="sxs-lookup"><span data-stu-id="4606d-124">In particular, the examples demonstrate the effects of using scope segments.</span></span>

### <a name="expense-report-numbers"></a><span data-ttu-id="4606d-125">Numery raportu wydatków.</span><span class="sxs-lookup"><span data-stu-id="4606d-125">Expense report numbers</span></span>

<span data-ttu-id="4606d-126">W poniższym przykładzie numery raportu wydatków są ustawiane dla firmy oznaczonej jako **CS**.</span><span class="sxs-lookup"><span data-stu-id="4606d-126">In the following example, expense report numbers are set up for the legal entity that is titled **CS**.</span></span> 

- <span data-ttu-id="4606d-127">**Obszar:** Wyjazdy i wydatki</span><span class="sxs-lookup"><span data-stu-id="4606d-127">**Area:** Travel and expense</span></span> 
- <span data-ttu-id="4606d-128">**Odwołanie:** Numer raportu wydatków</span><span class="sxs-lookup"><span data-stu-id="4606d-128">**Reference:** Expense report number</span></span> 
- <span data-ttu-id="4606d-129">**Zakres:** Firma</span><span class="sxs-lookup"><span data-stu-id="4606d-129">**Scope:** Legal entity</span></span> 
- <span data-ttu-id="4606d-130">**Firma:** CS</span><span class="sxs-lookup"><span data-stu-id="4606d-130">**Legal entity:** CS</span></span>

| <span data-ttu-id="4606d-131">Segmenty</span><span class="sxs-lookup"><span data-stu-id="4606d-131">Segments</span></span>  | <span data-ttu-id="4606d-132">Typ segmentów</span><span class="sxs-lookup"><span data-stu-id="4606d-132">Segment type</span></span> | <span data-ttu-id="4606d-133">Wartość</span><span class="sxs-lookup"><span data-stu-id="4606d-133">Value</span></span>     |
|-----------|--------------|-----------|
| <span data-ttu-id="4606d-134">Segment 1</span><span class="sxs-lookup"><span data-stu-id="4606d-134">Segment 1</span></span> | <span data-ttu-id="4606d-135">Firma</span><span class="sxs-lookup"><span data-stu-id="4606d-135">Legal entity</span></span> | <span data-ttu-id="4606d-136">CS</span><span class="sxs-lookup"><span data-stu-id="4606d-136">CS</span></span>        |
| <span data-ttu-id="4606d-137">Segment 2</span><span class="sxs-lookup"><span data-stu-id="4606d-137">Segment 2</span></span> | <span data-ttu-id="4606d-138">Stała</span><span class="sxs-lookup"><span data-stu-id="4606d-138">Constant</span></span>     | <span data-ttu-id="4606d-139">-WYDATEK-</span><span class="sxs-lookup"><span data-stu-id="4606d-139">-EXPENSE-</span></span> |
| <span data-ttu-id="4606d-140">Segment 3</span><span class="sxs-lookup"><span data-stu-id="4606d-140">Segment 3</span></span> | <span data-ttu-id="4606d-141">Alfanumeryczne</span><span class="sxs-lookup"><span data-stu-id="4606d-141">Alphanumeric</span></span> | \#\#\#\#  |

<span data-ttu-id="4606d-142">**Przykład sformatowanego numeru**: CS-WYDATKI-0039</span><span class="sxs-lookup"><span data-stu-id="4606d-142">**Example of formatted number**: CS-EXPENSE-0039</span></span> 

<span data-ttu-id="4606d-143">Można skonfigurować podobny format sekwencji numerów dla innych firm.</span><span class="sxs-lookup"><span data-stu-id="4606d-143">You can set up a similar number sequence format for other legal entities.</span></span> <span data-ttu-id="4606d-144">Na przykład dla firmy zwanej **RW**, jeśli zmienisz tylko wartość segmentu firmy, sformatowanym numerem będzie RW-wydatki-0039.</span><span class="sxs-lookup"><span data-stu-id="4606d-144">For example, for a legal entity that is named **RW**, if you change only the value of the legal entity segment, the formatted number is RW-EXPENSE-0039.</span></span> <span data-ttu-id="4606d-145">Można też zmienić cały format sekwencji numerów dla innych firm.</span><span class="sxs-lookup"><span data-stu-id="4606d-145">You can also change the whole number sequence format for other legal entities.</span></span> <span data-ttu-id="4606d-146">Na przykład można pominąć segment zakresu firmy przy tworzeniu sformatowanej liczby, na przykład Wyd-0001.</span><span class="sxs-lookup"><span data-stu-id="4606d-146">For example, you can omit the legal entity scope segment to create a formatted number such as Exp-0001.</span></span>

### <a name="sales-order-numbers"></a><span data-ttu-id="4606d-147">Numery zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="4606d-147">Sales order numbers</span></span>

<span data-ttu-id="4606d-148">W poniższym przykładzie numery zamówienia sprzedaży są konfigurowane dla Identyfikatora firmy **CEU**.</span><span class="sxs-lookup"><span data-stu-id="4606d-148">In the following example, sales order numbers are set up for the company ID **CEU**.</span></span> 

- <span data-ttu-id="4606d-149">**Obszar:** Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="4606d-149">**Area:** Sales</span></span> 
- <span data-ttu-id="4606d-150">**Odwołanie:** Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="4606d-150">**Reference:** Sales order</span></span> 
- <span data-ttu-id="4606d-151">**Zakres:** Firma</span><span class="sxs-lookup"><span data-stu-id="4606d-151">**Scope:** Company</span></span> 
- <span data-ttu-id="4606d-152">**Firma:** CEU</span><span class="sxs-lookup"><span data-stu-id="4606d-152">**Company:** CEU</span></span>

| <span data-ttu-id="4606d-153">Segmenty</span><span class="sxs-lookup"><span data-stu-id="4606d-153">Segments</span></span>  | <span data-ttu-id="4606d-154">Typ segmentu</span><span class="sxs-lookup"><span data-stu-id="4606d-154">Segment type</span></span> | <span data-ttu-id="4606d-155">Wartość</span><span class="sxs-lookup"><span data-stu-id="4606d-155">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="4606d-156">Segment 1</span><span class="sxs-lookup"><span data-stu-id="4606d-156">Segment 1</span></span> | <span data-ttu-id="4606d-157">Stała</span><span class="sxs-lookup"><span data-stu-id="4606d-157">Constant</span></span>     | <span data-ttu-id="4606d-158">SO-</span><span class="sxs-lookup"><span data-stu-id="4606d-158">SO-</span></span>      |
| <span data-ttu-id="4606d-159">Segment 2</span><span class="sxs-lookup"><span data-stu-id="4606d-159">Segment 2</span></span> | <span data-ttu-id="4606d-160">Alfanumeryczne</span><span class="sxs-lookup"><span data-stu-id="4606d-160">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="4606d-161">**Przykład sformatowanego numeru**: SO-0029</span><span class="sxs-lookup"><span data-stu-id="4606d-161">**Example of formatted number**: SO-0029</span></span> 

<span data-ttu-id="4606d-162">Mimo że segment zakresu nie jest uwzględniony w formacie, numerowanie zostaje ponownie uruchamiane dla każdego identyfikatora firmy.</span><span class="sxs-lookup"><span data-stu-id="4606d-162">Even though a scope segment is not included in the format, numbering restarts for each company ID.</span></span> <span data-ttu-id="4606d-163">Jeśli korzysta się z tego samego formatu dla wszystkich identyfikatorów firm, w każdej firmie są używane te same numery.</span><span class="sxs-lookup"><span data-stu-id="4606d-163">If you use the same format for all company IDs, the same numbers are used in each company.</span></span> <span data-ttu-id="4606d-164">Na przykład numer zamówienia sprzedaży SO-0029 jest używany w każdej firmie.</span><span class="sxs-lookup"><span data-stu-id="4606d-164">For example, sales order number SO-0029 is used in each company.</span></span> <span data-ttu-id="4606d-165">Można też zmienić cały format sekwencji numerów dla innych identyfikatorów firm.</span><span class="sxs-lookup"><span data-stu-id="4606d-165">You can also change the whole number sequence format for other company IDs.</span></span>

### <a name="purchase-requisition-numbers"></a><span data-ttu-id="4606d-166">Numery zapotrzebowania na zakup</span><span class="sxs-lookup"><span data-stu-id="4606d-166">Purchase requisition numbers</span></span>

<span data-ttu-id="4606d-167">W poniższym przykładzie numery zapotrzebowań na zakup są stosowane na poziomie organizacji.</span><span class="sxs-lookup"><span data-stu-id="4606d-167">In the following example, purchase requisition numbers are organization-wide.</span></span> 

- <span data-ttu-id="4606d-168">**Obszar:** Zakup</span><span class="sxs-lookup"><span data-stu-id="4606d-168">**Area:** Purchase</span></span> 
- <span data-ttu-id="4606d-169">**Odwołanie:** Zapotrzebowanie na zakup</span><span class="sxs-lookup"><span data-stu-id="4606d-169">**Reference:** Purchase requisition</span></span> 
- <span data-ttu-id="4606d-170">**Zakres:** Współdzielony</span><span class="sxs-lookup"><span data-stu-id="4606d-170">**Scope:** Shared</span></span>

| <span data-ttu-id="4606d-171">Segmenty</span><span class="sxs-lookup"><span data-stu-id="4606d-171">Segments</span></span>  | <span data-ttu-id="4606d-172">Typ segmentu</span><span class="sxs-lookup"><span data-stu-id="4606d-172">Segment type</span></span> | <span data-ttu-id="4606d-173">Wartość</span><span class="sxs-lookup"><span data-stu-id="4606d-173">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="4606d-174">Segment 1</span><span class="sxs-lookup"><span data-stu-id="4606d-174">Segment 1</span></span> | <span data-ttu-id="4606d-175">Stała</span><span class="sxs-lookup"><span data-stu-id="4606d-175">Constant</span></span>     | <span data-ttu-id="4606d-176">Ilość</span><span class="sxs-lookup"><span data-stu-id="4606d-176">Req</span></span>      |
| <span data-ttu-id="4606d-177">Segment 2</span><span class="sxs-lookup"><span data-stu-id="4606d-177">Segment 2</span></span> | <span data-ttu-id="4606d-178">Alfanumeryczne</span><span class="sxs-lookup"><span data-stu-id="4606d-178">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="4606d-179">**Przykład sformatowanego numeru**: Req0052</span><span class="sxs-lookup"><span data-stu-id="4606d-179">**Example of formatted number**: Req0052</span></span> 

<span data-ttu-id="4606d-180">Ponieważ zakres ma wartość **Współdzielony**, format numeracji jest używany w całej organizacji.</span><span class="sxs-lookup"><span data-stu-id="4606d-180">Because the scope is **Shared**, the number sequence format is used across the organization.</span></span> <span data-ttu-id="4606d-181">Nie można ustawić różnych formatów sekwencji numerów dla różnych części organizacji.</span><span class="sxs-lookup"><span data-stu-id="4606d-181">You cannot set up different number sequence formats for different parts of the organization.</span></span> 

<a name="performance-considerations-for-number-sequences"></a><span data-ttu-id="4606d-182">Zagadnienia dotyczące wydajności dla sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="4606d-182">Performance considerations for number sequences</span></span>
-----------------------------------------------

<span data-ttu-id="4606d-183">Należy wziąć pod uwagę następujące informacje na temat sposobu, w jaki konfiguracja sekwencji numerów może wpłynąć na wydajność systemu przed ustawieniem sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="4606d-183">Consider the following information about how the configuration of number sequences can affect system performance before you set up number sequences.</span></span>

### <a name="continuous-and-non-continuous-number-sequences"></a><span data-ttu-id="4606d-184">Ciągle i nieciągłe sekwencje numerów</span><span class="sxs-lookup"><span data-stu-id="4606d-184">Continuous and non-continuous number sequences</span></span>

<span data-ttu-id="4606d-185">Sekwencje numerów mogą być ciągle lub nieciągłe.</span><span class="sxs-lookup"><span data-stu-id="4606d-185">Number sequences can be continuous or non-continuous.</span></span> <span data-ttu-id="4606d-186">Ciągła sekwencja numerów nie powoduje pominięcia żadnych liczby, ale numery nie mogą być używane po kolei.</span><span class="sxs-lookup"><span data-stu-id="4606d-186">A continuous number sequence does not skip any numbers, but numbers may not be used sequentially.</span></span> <span data-ttu-id="4606d-187">Numery z nieciągłej sekwencji numerów używane są sekwencyjne, ale może następować pomijanie numerów sekwencji.</span><span class="sxs-lookup"><span data-stu-id="4606d-187">Numbers from a non-continuous number sequence are used sequentially, but the number sequence may skip numbers.</span></span> <span data-ttu-id="4606d-188">Na przykład jeśli użytkownik anuluje transakcję, numer jest generowany, ale nie jest używany.</span><span class="sxs-lookup"><span data-stu-id="4606d-188">For example, if a user cancels a transaction, a number is generated, but not used.</span></span> <span data-ttu-id="4606d-189">W ciągłej sekwencji numerów numer ten zostanie ponownie wykorzystany później.</span><span class="sxs-lookup"><span data-stu-id="4606d-189">In a continuous number sequence, that number is recycled later.</span></span> <span data-ttu-id="4606d-190">W nieciągłej sekwencji numerów numer ten nie zostanie ponownie wykorzystany.</span><span class="sxs-lookup"><span data-stu-id="4606d-190">In a non-continuous number sequence, the number is not used.</span></span> 

<span data-ttu-id="4606d-191">Zazwyczaj ciągłe sekwencje numerów są wymagane dla zewnętrznych dokumentów, takich jak zamówienia zakupu, zamówienia sprzedaży i faktury.</span><span class="sxs-lookup"><span data-stu-id="4606d-191">Continuous number sequences are typically required for external documents, such as purchase orders, sales orders, and invoices.</span></span> <span data-ttu-id="4606d-192">Jednak ciągłe sekwencje numerów mogą negatywnie wpływać na czas reakcji systemu, ponieważ system musi żądać numeru z bazy danych przy każdym tworzeniu nowego dokumentu lub rekordu.</span><span class="sxs-lookup"><span data-stu-id="4606d-192">However, continuous number sequences can adversely affect system response times because the system must request a number from the database every time that a new document or record is created.</span></span> 

<span data-ttu-id="4606d-193">Jeśli używasz nieciągłej sekwencji numerów, możesz włączyć **Wstępne przydzielanie** na skróconej karcie **Wydajność** na stronie **Sekwencja numerów**.</span><span class="sxs-lookup"><span data-stu-id="4606d-193">If you use a non-continuous number sequence, you can enable **Preallocation** on the **Performance** FastTab of the **Number sequences** page.</span></span> <span data-ttu-id="4606d-194">Kiedy określasz liczbę numerów do wstępnego przydzielenia, system wybiera te numery i przechowuje je w pamięci.</span><span class="sxs-lookup"><span data-stu-id="4606d-194">When you specify a quantity of numbers to preallocate, the system selects those numbers and stores them in memory.</span></span> <span data-ttu-id="4606d-195">Nowe numery są pobierane z bazy danych tylko wtedy, gdy zostały użyte ilości przydzielone wstępnie.</span><span class="sxs-lookup"><span data-stu-id="4606d-195">New numbers are requested from the database only after the preallocated quantity has been used.</span></span> 

<span data-ttu-id="4606d-196">Jeśli przepisy nie nakazują używania ciągłej sekwencji numerów, zaleca się używanie nieciągłej sekwencji numerów w celu uzyskania lepszej wydajności.</span><span class="sxs-lookup"><span data-stu-id="4606d-196">Unless there is a regulatory requirement that you use continuous number sequences, we recommend that you use non-continuous number sequences for better performance.</span></span>

### <a name="automatic-cleanup-of-number-sequences"></a><span data-ttu-id="4606d-197">Automatyczne oczyszczanie sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="4606d-197">Automatic cleanup of number sequences</span></span>

<span data-ttu-id="4606d-198">W przypadku awarii zasilania, błędu aplikacji lub innego nieoczekiwanego problemu system nie może automatycznie odtworzyć numerów dla ciągłych sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="4606d-198">In case of a power failure, an application error, or other unexpected failure, the system cannot recycle numbers automatically for continuous number sequences.</span></span> <span data-ttu-id="4606d-199">Proces oczyszczania można uruchomić ręcznie lub automatycznie w celu odzyskania zagubionych numerów.</span><span class="sxs-lookup"><span data-stu-id="4606d-199">You can run the cleanup process manually or automatically to recover the lost numbers.</span></span> 

<span data-ttu-id="4606d-200">Należy dokładnie rozważyć zużycie serwera podczas planowania procesu oczyszczania.</span><span class="sxs-lookup"><span data-stu-id="4606d-200">Carefully consider server usage when you plan the cleanup process.</span></span> <span data-ttu-id="4606d-201">Zalecane jest przeprowadzanie oczyszczania jako zadania wsadowego w godzinach poza szczytem.</span><span class="sxs-lookup"><span data-stu-id="4606d-201">We recommend that you perform the cleanup as a batch job during non-peak hours.</span></span>






