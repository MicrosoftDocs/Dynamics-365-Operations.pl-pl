---
title: Synchronizowanie daty i godziny w zadaniach importu
description: Użyj stref czasowych UTC w zadaniach importu, aby uniknąć problemów z konwersjami stref czasowych.
author: Sunil-Garg
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c0ec805a20a525989e0133e5dffb29ce3fed39
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748676"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a><span data-ttu-id="2db5a-103">Synchronizowanie daty i godziny w zadaniach importu</span><span class="sxs-lookup"><span data-stu-id="2db5a-103">Synchronize date and time in import jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2db5a-104">Bardzo ważne jest ustawienie strefy czasowej dla zadania importu na uniwersalny czas koordynowany (UTC).</span><span class="sxs-lookup"><span data-stu-id="2db5a-104">It's important to set the time zone for your import job to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="2db5a-105">Użycie innego ustawienia może spowodować wyświetlanie w importowanych danych nieoczekiwanych dat i godzin.</span><span class="sxs-lookup"><span data-stu-id="2db5a-105">You might see unexpected dates and times in your imported data if you use a different setting.</span></span> <span data-ttu-id="2db5a-106">Bez poprawnego ustawienia proces importowania konwertuje datę UTC na format lokalny, a następnie ustawienia systemowe konwertują ją ponownie.</span><span class="sxs-lookup"><span data-stu-id="2db5a-106">Without the correct setting, the import process converts the UTC date to the local format, and then system settings converts it again.</span></span>

<span data-ttu-id="2db5a-107">Te dwie konwersje powodują zmianę dat między aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="2db5a-107">This dual conversion causes dates to change between applications.</span></span> <span data-ttu-id="2db5a-108">Na przykład podwójna konwersja może spowodować, że data rozpoczęcia dla pracownika może być różna w aplikacjach Dynamics 365 Human Resources i Dynamics 365 Finance z powodu różnic w strefach czasowych.</span><span class="sxs-lookup"><span data-stu-id="2db5a-108">For example, the dual conversion could cause an employee's start date to be different between Dynamics 365 Human Resources and Dynamics 365 Finance due to differences in local time zones.</span></span> <span data-ttu-id="2db5a-109">Ustawienie zadania importowania na czas UTC rozwiązało ten problem.</span><span class="sxs-lookup"><span data-stu-id="2db5a-109">Setting the import job to UTC resolves this problem.</span></span>

1. <span data-ttu-id="2db5a-110">W Dynamics 365 Finance and Operations wybierz pozycję **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="2db5a-110">In Dynamics 365 Finance and Operations, select **Data management**.</span></span>

2. <span data-ttu-id="2db5a-111">Wybierz opcję **Importuj projekty**, a następnie wybierz projekt.</span><span class="sxs-lookup"><span data-stu-id="2db5a-111">Select **Import projects**, and then select the project.</span></span>

3. <span data-ttu-id="2db5a-112">W obszarze **Format daty źródłowej** wybierz format **CSV-Unicode**.</span><span class="sxs-lookup"><span data-stu-id="2db5a-112">Under **Source date format**, select **CSV-Unicode**.</span></span>

   <span data-ttu-id="2db5a-113">[![Zmienianie formatu daty źródłowej na UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span><span class="sxs-lookup"><span data-stu-id="2db5a-113">[![Change source date format to UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span></span>

4. <span data-ttu-id="2db5a-114">Zmień **strefę czasową** na **Uniwersalny czas koordynowany** i zmień **język** na **En-US**.</span><span class="sxs-lookup"><span data-stu-id="2db5a-114">Change **Timezone** to **Coordinated Universal Timezone**, and change **Language** to **En-US**.</span></span>




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]