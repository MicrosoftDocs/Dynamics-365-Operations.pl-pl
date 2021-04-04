---
title: Rozwiązywanie problemów z raportami analitycznymi
description: W tym artykule wyjaśniono, co należy zrobić, gdy zmiany w danych klienta nie pojawiają się w żadnych jego obszarach roboczych.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
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
ms.openlocfilehash: e0befe1a35aa46b2eabb4516559fe07ce27e9f18
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466671"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="fcd6c-103">Rozwiązywanie problemów z raportami analitycznymi</span><span class="sxs-lookup"><span data-stu-id="fcd6c-103">Troubleshoot analytic reports</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="fcd6c-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="fcd6c-104">**Issue**</span></span>

<span data-ttu-id="fcd6c-105">Zmiany danych odbiorcy nie pojawiają się w kartach **Analizy** tych obszarów roboczych odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="fcd6c-106">**Powód**</span><span class="sxs-lookup"><span data-stu-id="fcd6c-106">**Cause**</span></span>

<span data-ttu-id="fcd6c-107">Domyślnie raporty Microsoft Power BI są odświeżane co cztery godziny, zgodnie z harmonogramem zadania wsadowego Wdróż miarę.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="fcd6c-108">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="fcd6c-108">**Resolution**</span></span>

<span data-ttu-id="fcd6c-109">Ten problem może być tylko kwestią czasu.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="fcd6c-110">Wykonaj poniższe czynności, aby uruchomić zadanie wsadowe i zaktualizować obszary robocze analizy.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="fcd6c-111">Otwórz **zadania wsadowe** w menu **administrowanie systemem \>łącza \>zadania wsadowe \>zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="fcd6c-112">Można także użyć funkcji Wyszukaj i wpisać **zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="fcd6c-113">Znajdź zadanie **Wdróż miarę** na liście.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="fcd6c-114">Wybierz **Edytuj** u góry strony i ustaw planowaną datę/godzinę rozpoczęcia na wartość, która odświeży analizy bliżej czasu bieżącego.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Zadania wsadowe](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]