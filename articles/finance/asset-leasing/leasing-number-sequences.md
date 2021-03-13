---
title: Przypisywanie sekwencji identyfikatorów
description: W tym temacie opisano sposób tworzenia numeracji dla identyfikatorów wynajmu. Opisano tu także sposób tworzenia unikatowych identyfikatorów używanych w procesie przeszacowania indeksu.
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
ms.openlocfilehash: c21b7a55ff611a5d3ab745f3af5e2e855240531b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128962"
---
# <a name="assign-number-sequences"></a><span data-ttu-id="a12b6-104">Przypisywanie sekwencji identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="a12b6-104">Assign number sequences</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a12b6-105">W tym temacie opisano sposób tworzenia numeracji dla identyfikatorów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="a12b6-105">This topic explains how to create number sequences for lease IDs.</span></span> <span data-ttu-id="a12b6-106">Opisano tu także sposób tworzenia unikatowych identyfikatorów używanych w procesie przeszacowania indeksu.</span><span class="sxs-lookup"><span data-stu-id="a12b6-106">It also explains how to create unique IDs that are used in the index revaluation process.</span></span>

1. <span data-ttu-id="a12b6-107">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="a12b6-107">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="a12b6-108">Kliknij boczną kartę **Sekwencje numerów**.</span><span class="sxs-lookup"><span data-stu-id="a12b6-108">Select the **Number sequences** side tab.</span></span>
3. <span data-ttu-id="a12b6-109">Na pasku bocznym wybierz opcję **Sekwencje numerów**.</span><span class="sxs-lookup"><span data-stu-id="a12b6-109">Select **Number sequences** in the side bar.</span></span>
4. <span data-ttu-id="a12b6-110">Wybierz sekwencję numerów odwołania **Identyfikator wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="a12b6-110">Select the number sequence for the **Lease ID** reference.</span></span> <span data-ttu-id="a12b6-111">Ta numeracja zostanie użyta do wygenerowania unikatowego identyfikatora każdego wynajmu.</span><span class="sxs-lookup"><span data-stu-id="a12b6-111">This number sequence will be used to generate the unique identifier for each lease.</span></span>
5. <span data-ttu-id="a12b6-112">Wybierz sekwencję numerów odwołania **Identyfikator procesu**.</span><span class="sxs-lookup"><span data-stu-id="a12b6-112">Select the number sequence for the **Process ID** reference.</span></span> <span data-ttu-id="a12b6-113">Ta numeracja zostanie użyta do wygenerowania unikatowego identyfikatora każdego procesu przeszacowania indeksu.</span><span class="sxs-lookup"><span data-stu-id="a12b6-113">This number sequence will be used to generate the unique identifier for each index revaluation process.</span></span>
6. <span data-ttu-id="a12b6-114">Wybierz sekwencję numerów odwołania **Identyfikator propozycji rozwiązania umowy**.</span><span class="sxs-lookup"><span data-stu-id="a12b6-114">Select the number sequence for the **Termination Proposal ID** reference.</span></span> <span data-ttu-id="a12b6-115">Ta sekwencja numerów zostanie wykorzystana do wygenerowania unikalnego identyfikatora dla każdej propozycji zakończenia.</span><span class="sxs-lookup"><span data-stu-id="a12b6-115">This number sequence will be used to generate the unique identifier for each termination proposal.</span></span>
