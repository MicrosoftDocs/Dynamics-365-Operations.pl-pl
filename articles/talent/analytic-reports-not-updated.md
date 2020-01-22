---
title: Raporty analityczne nie są aktualizowane
description: W tym temacie wyjaśniono, co należy zrobić, gdy zmiany w danych klienta nie pojawiają się w żadnych jego obszarach roboczych.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: fc2e6259a8f9d17dc0f7652f207acfa53da76a8d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898580"
---
# <a name="analytic-reports-are-not-updated"></a><span data-ttu-id="b2f3c-103">Raporty analityczne nie są aktualizowane</span><span class="sxs-lookup"><span data-stu-id="b2f3c-103">Analytic reports are not updated</span></span>

<span data-ttu-id="b2f3c-104">**Wydaj**</span><span class="sxs-lookup"><span data-stu-id="b2f3c-104">**Issue**</span></span>

<span data-ttu-id="b2f3c-105">Zmiany danych odbiorcy nie pojawiają się w kartach **Analizy** tych obszarów roboczych odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b2f3c-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="b2f3c-106">**Przyczyna**</span><span class="sxs-lookup"><span data-stu-id="b2f3c-106">**Cause**</span></span>

<span data-ttu-id="b2f3c-107">Domyślnie raporty Microsoft Power BI są odświeżane co cztery godziny, zgodnie z harmonogramem zadania wsadowego Wdróż miarę.</span><span class="sxs-lookup"><span data-stu-id="b2f3c-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="b2f3c-108">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="b2f3c-108">**Resolution**</span></span>

<span data-ttu-id="b2f3c-109">Ten problem może być tylko kwestią czasu.</span><span class="sxs-lookup"><span data-stu-id="b2f3c-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="b2f3c-110">Wykonaj poniższe czynności, aby uruchomić zadanie wsadowe i zaktualizować obszary robocze analizy.</span><span class="sxs-lookup"><span data-stu-id="b2f3c-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="b2f3c-111">Otwórz **zadania wsadowe** w menu **administrowanie systemem \>łącza \>zadania wsadowe \>zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="b2f3c-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="b2f3c-112">Można także użyć funkcji Wyszukaj i wpisać **zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="b2f3c-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="b2f3c-113">Znajdź zadanie **Wdróż miarę** na liście.</span><span class="sxs-lookup"><span data-stu-id="b2f3c-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="b2f3c-114">Wybierz **Edytuj** u góry strony i ustaw planowaną datę/godzinę rozpoczęcia na wartość, która odświeży analizy bliżej czasu bieżącego.</span><span class="sxs-lookup"><span data-stu-id="b2f3c-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Zadania wsadowe](media/batch-jobs.png)
