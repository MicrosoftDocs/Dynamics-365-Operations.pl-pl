---
title: Księgowanie wpisów w arkuszu dotyczących korekt przejścia w module Wynajem składnika majątku
description: W tym temacie opisano funkcję, która umożliwia przeniesienie portfela umów wynajmu do nowych standardów księgowania takich umów — Accounting Standards Codification Topic 842 (ASC 842) i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16).
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ea61a0d6e30695a2ef6b93529fcf3d21882c9cd2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819777"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a><span data-ttu-id="51dcb-103">Księgowanie wpisów w arkuszu dotyczących korekt przejścia w module Wynajem składnika majątku</span><span class="sxs-lookup"><span data-stu-id="51dcb-103">Post transition adjustment journal entries in Asset leasing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51dcb-104">W tym temacie opisano funkcję, która umożliwia przeniesienie portfela umów wynajmu do nowych standardów księgowania takich umów — Accounting Standards Codification Topic 842 (ASC 842), który jest standardem przyjętym w ogólnie przyjętych zasadach rachunkowości w Stanach Zjednoczonych (US GAAP), i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16).</span><span class="sxs-lookup"><span data-stu-id="51dcb-104">This topic describes the functionality that lets you transition a lease portfolio to the new lease accounting standards: Accounting Standards Codification Topic 842 (ASC 842), which is the standard in Generally Accepted Accounting Principles in the US (US GAAP), and International Financial Reporting Standard 16 (IFRS 16).</span></span>

<span data-ttu-id="51dcb-105">Aby uzyskać informacje dotyczące konfigurowania księgi dla przejścia do nowych standardów, zapoznaj się z tematem [Konfigurowanie ksiąg wynajmu](set-up-lease-books.md).</span><span class="sxs-lookup"><span data-stu-id="51dcb-105">For information about how to set up a book for the transition to the new standards, see [Set up lease books](set-up-lease-books.md).</span></span>

<span data-ttu-id="51dcb-106">Podczas tworzenia wpisu w arkuszu dotyczącego korekty przejścia jest tworzony wpis w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="51dcb-106">When you create a transition adjustment journal entry, a journal entry is generated.</span></span> <span data-ttu-id="51dcb-107">Ten wpis odzwierciedla wpływ zarejestrowania wynajmu na bilans według nowych standardów na dany dzień.</span><span class="sxs-lookup"><span data-stu-id="51dcb-107">This entry reflects the balance sheet impact of recording the lease under the new standards on that date.</span></span> <span data-ttu-id="51dcb-108">W tym dniu odpowiednie konto aktywów jest obciążane wartością bilansową, a konto pasywów jest uznawane.</span><span class="sxs-lookup"><span data-stu-id="51dcb-108">The appropriate asset account is debited for the carrying amount on that date, and the liability account is credited.</span></span> <span data-ttu-id="51dcb-109">Różnica jest księgowana po stronie debetowej lub kredytowej na koncie zysków zatrzymanych.</span><span class="sxs-lookup"><span data-stu-id="51dcb-109">The difference is either debited or credited to retained earnings.</span></span>

<span data-ttu-id="51dcb-110">Aby zaksięgować korektę przejścia zgodnie z nowymi standardami rachunkowości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="51dcb-110">To post a transition adjustment in compliance with the new accounting standards, follow these steps.</span></span>

1. <span data-ttu-id="51dcb-111">Na stronie **Podsumowanie wynajmu** wybierz wynajem, a następnie wybierz opcję **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="51dcb-111">On the **Lease summary** page, select the lease, and then select **Books**.</span></span>
2. <span data-ttu-id="51dcb-112">W księdze wybierz opcję **Harmonogram płatności**.</span><span class="sxs-lookup"><span data-stu-id="51dcb-112">In the book, select **Payment schedule**.</span></span>
3. <span data-ttu-id="51dcb-113">W oknie dialogowym **Harmonogram płatności** wybierz opcję **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="51dcb-113">In the **Payment schedule** dialog box, select **Confirm**.</span></span> <span data-ttu-id="51dcb-114">Następnie zamknij okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="51dcb-114">Then close the dialog box.</span></span>
4. <span data-ttu-id="51dcb-115">Wybierz opcję **Korekta przejścia**.</span><span class="sxs-lookup"><span data-stu-id="51dcb-115">Select **Transition adjustment**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="51dcb-116">Korektę przejścia można utworzyć tylko dla ksiąg wynajmu przypisanych do księgi mającej dostępne pole **Księga przejścia**.</span><span class="sxs-lookup"><span data-stu-id="51dcb-116">A transition adjustment can be created only for lease books that are assigned to a book where the **Transition book** field is available.</span></span> <span data-ttu-id="51dcb-117">Jeśli data w polu **Rozpoczęcie wynajmu** jest późniejsza niż data przejścia, wartość w polu **Korekta przejścia** nie zostanie zaktualizowana.</span><span class="sxs-lookup"><span data-stu-id="51dcb-117">If the value in the **Lease commencement** field is later than the transition date, the value in the **Transition adjustment** field won't be updated.</span></span>

5. <span data-ttu-id="51dcb-118">Aby wyświetlić wpis w arkuszu, wybierz opcję **Arkusze wynajmu składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="51dcb-118">To view the journal entry, select **Asset leasing journals**.</span></span>
6. <span data-ttu-id="51dcb-119">Zaznacz nowy arkusz, a następnie wybierz opcję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="51dcb-119">Select the new journal, and then select **Post**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]