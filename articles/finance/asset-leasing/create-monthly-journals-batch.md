---
title: Tworzenie miesięcznych wpisów w arkuszu w partii
description: W tym temacie opisano sposób tworzenia zapisów arkusza w partii w celu zwiększenia efektywności, gdy są rejestrowane miesięczne koszty dzierżawy.
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
ms.openlocfilehash: a2293f6bd3ce66832996652c3bfca0fc4bc73782
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4446996"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a><span data-ttu-id="e3269-103">Tworzenie miesięcznych wpisów w arkuszu w partii</span><span class="sxs-lookup"><span data-stu-id="e3269-103">Create monthly journal entries in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3269-104">W tym temacie opisano sposób tworzenia zapisów arkusza w partii w celu zwiększenia efektywności, gdy są rejestrowane miesięczne koszty dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="e3269-104">This topic explains how to create journal entries in a batch to help increase efficiency when monthly lease expenses are recorded.</span></span> <span data-ttu-id="e3269-105">Przetwarzanie wsadowe może być używane do tworzenia zapisów w arkuszu na podstawie wielu harmonogramów.</span><span class="sxs-lookup"><span data-stu-id="e3269-105">Batch processing can be used to create journal entries from multiple schedules.</span></span> <span data-ttu-id="e3269-106">Do tych wpisów w arkuszu mogą należeć płatności leasingowe, amortyzacja zobowiązań, prawa do użycia (ROU) amortyzacja środków trwałych i koszty kosztowe.</span><span class="sxs-lookup"><span data-stu-id="e3269-106">These journal entries can include lease payments, liability amortization, right-of-use (ROU) asset amortization, and executory cost expenses.</span></span> <span data-ttu-id="e3269-107">Przetwarzanie wsadowe można również wykonać w celu jednorazowego rozpoznania wielu dzierżaw lub w celu jednoczesnego utworzenia korekty przejścia dla wielu dzierżaw.</span><span class="sxs-lookup"><span data-stu-id="e3269-107">You can also use batch processing to do the initial recognition of multiple leases at the same time, or to create transition adjustments for multiple leases at the same time.</span></span>

<span data-ttu-id="e3269-108">Aby skonfigurować zadanie wsadowe lub przetwarzać faktury płatności, amortyzację lub odsetki dla wielu dzierżaw, należy przejść do **Wynajem składnika majątku \> Okresowe \> Tworzenie arkusza w partii**.</span><span class="sxs-lookup"><span data-stu-id="e3269-108">To set up a batch job, or to process payment invoices, depreciation, or interest for multiple leases, go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span> <span data-ttu-id="e3269-109">W wyświetlonym oknie dialogowym można wybrać harmonogram, na podstawie którego mają zostać utworzone zapisy arkusza.</span><span class="sxs-lookup"><span data-stu-id="e3269-109">In the dialog box that appears, you can select the schedule that the journal entries should be created from.</span></span> <span data-ttu-id="e3269-110">Można również określić, czy proces przetwarzania wsadowego powinien być uruchamiany dla określonych jednostek, grup dzierżaw czy książek dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="e3269-110">You can also specify whether the batch process should be run for specific entities, lease groups, or lease books.</span></span>

> [!NOTE]
> <span data-ttu-id="e3269-111">Kolejne transakcje, takie jak harmonogramy amortyzacji zobowiązań, płatności, amortyzacja i wydatki, będą księgowane dopiero po zaksięgowaniu początkowego oddzielenia dla odpowiednich dzierżaw.</span><span class="sxs-lookup"><span data-stu-id="e3269-111">Subsequent transactions, such as liability amortization schedules, payments, depreciation, and expenses, will be posted only after the initial recognition for corresponding leases is posted.</span></span>
>
> <span data-ttu-id="e3269-112">Wpisy w arkuszu są tworzone, ale nie są księgowane, dopóki nie zostanie wybrane polecenie **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="e3269-112">The journal entries are created, but they won't be posted until you select the **Run** command.</span></span>
