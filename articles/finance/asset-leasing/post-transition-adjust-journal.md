---
title: Księgowanie wpisów w arkuszu dotyczących korekt przejścia w module Wynajem składnika majątku
description: W tym temacie opisano funkcję, która umożliwia przeniesienie portfela umów wynajmu do nowych standardów księgowania takich umów — Accounting Standards Codification Topic 842 (ASC 842) i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16).
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4af7b9dc7a03a6d17ff34ffc726eb87e848dd785
ms.sourcegitcommit: f0f5545a8ff99583e0131f435d91c64bb68a1c38
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "4447014"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a><span data-ttu-id="69dfb-103">Księgowanie wpisów w arkuszu dotyczących korekt przejścia w module Wynajem składnika majątku</span><span class="sxs-lookup"><span data-stu-id="69dfb-103">Post transition adjustment journal entries in Asset leasing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="69dfb-104">W tym temacie opisano funkcję, która umożliwia przeniesienie portfela umów wynajmu do nowych standardów księgowania takich umów — Accounting Standards Codification Topic 842 (ASC 842), który jest standardem przyjętym w ogólnie przyjętych zasadach rachunkowości w Stanach Zjednoczonych (US GAAP), i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16).</span><span class="sxs-lookup"><span data-stu-id="69dfb-104">This topic describes the functionality that lets you transition a lease portfolio to the new lease accounting standards: Accounting Standards Codification Topic 842 (ASC 842), which is the standard in Generally Accepted Accounting Principles in the US (US GAAP), and International Financial Reporting Standard 16 (IFRS 16).</span></span>

<span data-ttu-id="69dfb-105">Aby uzyskać informacje dotyczące konfigurowania księgi dla przejścia do nowych standardów, zapoznaj się z tematem [Konfigurowanie ksiąg wynajmu](set-up-lease-books.md).</span><span class="sxs-lookup"><span data-stu-id="69dfb-105">For information about how to set up a book for the transition to the new standards, see [Set up lease books](set-up-lease-books.md).</span></span>

<span data-ttu-id="69dfb-106">Podczas tworzenia wpisu w arkuszu dotyczącego korekty przejścia jest tworzony wpis w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="69dfb-106">When you create a transition adjustment journal entry, a journal entry is generated.</span></span> <span data-ttu-id="69dfb-107">Ten wpis odzwierciedla wpływ zarejestrowania wynajmu na bilans według nowych standardów na dany dzień.</span><span class="sxs-lookup"><span data-stu-id="69dfb-107">This entry reflects the balance sheet impact of recording the lease under the new standards on that date.</span></span> <span data-ttu-id="69dfb-108">W tym dniu odpowiednie konto aktywów jest obciążane wartością bilansową, a konto pasywów jest uznawane.</span><span class="sxs-lookup"><span data-stu-id="69dfb-108">The appropriate asset account is debited for the carrying amount on that date, and the liability account is credited.</span></span> <span data-ttu-id="69dfb-109">Różnica jest księgowana po stronie debetowej lub kredytowej na koncie zysków zatrzymanych.</span><span class="sxs-lookup"><span data-stu-id="69dfb-109">The difference is either debited or credited to retained earnings.</span></span>

<span data-ttu-id="69dfb-110">Aby zaksięgować korektę przejścia zgodnie z nowymi standardami rachunkowości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="69dfb-110">To post a transition adjustment in compliance with the new accounting standards, follow these steps.</span></span>

1. <span data-ttu-id="69dfb-111">Na stronie **Podsumowanie wynajmu** wybierz wynajem, a następnie wybierz opcję **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="69dfb-111">On the **Lease summary** page, select the lease, and then select **Books**.</span></span>
2. <span data-ttu-id="69dfb-112">W księdze wybierz opcję **Harmonogram płatności**.</span><span class="sxs-lookup"><span data-stu-id="69dfb-112">In the book, select **Payment schedule**.</span></span>
3. <span data-ttu-id="69dfb-113">W oknie dialogowym **Harmonogram płatności** wybierz opcję **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="69dfb-113">In the **Payment schedule** dialog box, select **Confirm**.</span></span> <span data-ttu-id="69dfb-114">Następnie zamknij okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="69dfb-114">Then close the dialog box.</span></span>
4. <span data-ttu-id="69dfb-115">Wybierz opcję **Korekta przejścia**.</span><span class="sxs-lookup"><span data-stu-id="69dfb-115">Select **Transition adjustment**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="69dfb-116">Korektę przejścia można utworzyć tylko dla ksiąg wynajmu przypisanych do księgi mającej dostępne pole **Księga przejścia**.</span><span class="sxs-lookup"><span data-stu-id="69dfb-116">A transition adjustment can be created only for lease books that are assigned to a book where the **Transition book** field is available.</span></span> <span data-ttu-id="69dfb-117">Jeśli data w polu **Rozpoczęcie wynajmu** jest późniejsza niż data przejścia, wartość w polu **Korekta przejścia** nie zostanie zaktualizowana.</span><span class="sxs-lookup"><span data-stu-id="69dfb-117">If the value in the **Lease commencement** field is later than the transition date, the value in the **Transition adjustment** field won't be updated.</span></span>

5. <span data-ttu-id="69dfb-118">Aby wyświetlić wpis w arkuszu, wybierz opcję **Arkusze wynajmu składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="69dfb-118">To view the journal entry, select **Asset leasing journals**.</span></span>
6. <span data-ttu-id="69dfb-119">Zaznacz nowy arkusz, a następnie wybierz opcję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="69dfb-119">Select the new journal, and then select **Post**.</span></span>
