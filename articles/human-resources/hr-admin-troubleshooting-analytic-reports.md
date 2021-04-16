---
title: Rozwiązywanie problemów z raportami analitycznymi
description: W tym artykule wyjaśniono, co należy zrobić, gdy zmiany w danych klienta nie pojawiają się w żadnych jego obszarach roboczych.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b500d519d61edfd20456355376e3fc81f16517a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794980"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="281a8-103">Rozwiązywanie problemów z raportami analitycznymi</span><span class="sxs-lookup"><span data-stu-id="281a8-103">Troubleshoot analytic reports</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="281a8-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="281a8-104">**Issue**</span></span>

<span data-ttu-id="281a8-105">Zmiany danych odbiorcy nie pojawiają się w kartach **Analizy** tych obszarów roboczych odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="281a8-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="281a8-106">**Powód**</span><span class="sxs-lookup"><span data-stu-id="281a8-106">**Cause**</span></span>

<span data-ttu-id="281a8-107">Domyślnie raporty Microsoft Power BI są odświeżane co cztery godziny, zgodnie z harmonogramem zadania wsadowego Wdróż miarę.</span><span class="sxs-lookup"><span data-stu-id="281a8-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="281a8-108">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="281a8-108">**Resolution**</span></span>

<span data-ttu-id="281a8-109">Ten problem może być tylko kwestią czasu.</span><span class="sxs-lookup"><span data-stu-id="281a8-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="281a8-110">Wykonaj poniższe czynności, aby uruchomić zadanie wsadowe i zaktualizować obszary robocze analizy.</span><span class="sxs-lookup"><span data-stu-id="281a8-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="281a8-111">Otwórz **zadania wsadowe** w menu **administrowanie systemem \>łącza \>zadania wsadowe \>zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="281a8-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="281a8-112">Można także użyć funkcji Wyszukaj i wpisać **zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="281a8-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="281a8-113">Znajdź zadanie **Wdróż miarę** na liście.</span><span class="sxs-lookup"><span data-stu-id="281a8-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="281a8-114">Wybierz **Edytuj** u góry strony i ustaw planowaną datę/godzinę rozpoczęcia na wartość, która odświeży analizy bliżej czasu bieżącego.</span><span class="sxs-lookup"><span data-stu-id="281a8-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Zadania wsadowe](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]