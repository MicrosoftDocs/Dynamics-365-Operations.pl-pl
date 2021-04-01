---
title: Zmienianie klasyfikacji krótkoterminowej części zobowiązania z tytułu wynajmu
description: W tym temacie opisano sposób tworzenia miesięcznego wpisu w arkuszu w celu przeklasyfikowania części zobowiązania z tytułu wynajmu na krótkoterminowe.
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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9189033987a3072c7122e1a198768d9de6aa2a52
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254090"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a><span data-ttu-id="4ec92-103">Zmienianie klasyfikacji krótkoterminowej części zobowiązania z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="4ec92-103">Reclassify the short-term portion of lease liability</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ec92-104">W tym temacie opisano sposób tworzenia miesięcznego wpisu w arkuszu w celu przeklasyfikowania części zobowiązania z tytułu wynajmu na krótkoterminowe.</span><span class="sxs-lookup"><span data-stu-id="4ec92-104">This topic explains how to create a monthly journal entry to reclassify a portion of the lease liability as short-term.</span></span> <span data-ttu-id="4ec92-105">Jeśli harmonogramem wybranym w procesie wsadowym jest **Przeklasyfikowanie krótkoterminowego zobowiązania z tytułu wynajmu**, jest tworzony wpis w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="4ec92-105">When the schedule that is selected in the batch process is **Short-term lease liability reclass**, a journal entry is created.</span></span> <span data-ttu-id="4ec92-106">Ten wpis służy do księgowania bieżącej części zobowiązania z tytułu wynajmu w ostatnim dniu miesiąca.</span><span class="sxs-lookup"><span data-stu-id="4ec92-106">This entry is used to post the current portion of the lease liability on the last day of the month.</span></span> <span data-ttu-id="4ec92-107">W tym samym czasie jest księgowany wpis stornujący na pierwszy dzień następnego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="4ec92-107">At the same time, a reversal entry is posted as of the first day of the next month.</span></span>

<span data-ttu-id="4ec92-108">Krótkoterminowa część zobowiązania z tytułu wynajmu jest wyświetlana w harmonogramie amortyzacji zobowiązań.</span><span class="sxs-lookup"><span data-stu-id="4ec92-108">The short-term portion of the lease liability is shown on the liability amortization schedule.</span></span> <span data-ttu-id="4ec92-109">Po zaksięgowaniu wpisu w arkuszu staje się dostępna kolumna **Utworzono arkusz przeklasyfikowania zobowiązania**, a w harmonogramie jest wpisywany identyfikator arkusza.</span><span class="sxs-lookup"><span data-stu-id="4ec92-109">When the journal entry is posted, the **Liability reclass journal created** column becomes available, and the journal ID is also filled in on the schedule.</span></span>

<span data-ttu-id="4ec92-110">Aby utworzyć i zaksięgować wpis w arkuszu dotyczący przeklasyfikowania zobowiązania krótkoterminowego, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="4ec92-110">To create and post the short-term liability reclassification journal entry, follow these steps.</span></span>

1. <span data-ttu-id="4ec92-111">Przejdź do **Wynajem składnika majątku \> Okresowe \> Tworzenie arkusza w partii**.</span><span class="sxs-lookup"><span data-stu-id="4ec92-111">Go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span>
2. <span data-ttu-id="4ec92-112">W oknie dialogowym **Tworzenie arkusza w partii** w polu **Wybierz harmonogram** wybierz pozycję **Przeklasyfikowanie krótkoterminowego zobowiązania z tytułu wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="4ec92-112">In the **Batch journal creation** dialog box, in the **Select schedule** field, select **Short-term lease liability reclass**.</span></span>
3. <span data-ttu-id="4ec92-113">W polu **Grupa wynajmu** wybierz grupę wynajmu.</span><span class="sxs-lookup"><span data-stu-id="4ec92-113">In the **Lease group** field, select a lease group.</span></span> <span data-ttu-id="4ec92-114">Alternatywnie w polu **Identyfikator księgi** wybierz identyfikator księgi.</span><span class="sxs-lookup"><span data-stu-id="4ec92-114">Alternatively, in the **Book ID** field, select the book ID.</span></span>
4. <span data-ttu-id="4ec92-115">Włącz parametr **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="4ec92-115">Turn on the **Post** parameter.</span></span> <span data-ttu-id="4ec92-116">Alternatywnie, jeśli wpis powinien zostać utworzony, ale nie zaksięgowany, pozostaw ten parametr wyłączony.</span><span class="sxs-lookup"><span data-stu-id="4ec92-116">Alternatively, if the entry should be created but not posted, leave this parameter turned off.</span></span>
5. <span data-ttu-id="4ec92-117">Włącz parametr **Wyświetl podgląd przed zaksięgowaniem**, aby obejrzeć wpis przed jego zaksięgowaniem.</span><span class="sxs-lookup"><span data-stu-id="4ec92-117">Turn on the **Preview before posting** parameter to view the entry before it's posted.</span></span>
6. <span data-ttu-id="4ec92-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ec92-118">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]