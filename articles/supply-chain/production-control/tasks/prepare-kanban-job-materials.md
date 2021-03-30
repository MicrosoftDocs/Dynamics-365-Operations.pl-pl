---
title: Przygotowanie zadania procesu w systemie Kanban, gdy materiały są dostępne dla komórki roboczej
description: To zadanie koncentruje się na przygotowaniu zadania przetwarzania w systemie Kanban, gdy wszystkie materiały są dostępne dla komórki roboczej.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bde7a52e092723f9c6a686cb79080656c8de964c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204599"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a><span data-ttu-id="3f9ac-103">Przygotowanie zadania procesu w systemie Kanban, gdy materiały są dostępne dla komórki roboczej</span><span class="sxs-lookup"><span data-stu-id="3f9ac-103">Prepare a process kanban job when materials are available for the work cell</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f9ac-104">To zadanie koncentruje się na przygotowaniu zadania przetwarzania w systemie Kanban, gdy wszystkie materiały są dostępne dla komórki roboczej.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-104">This task focuses on preparing a process kanban job when all materials are available for the work cell.</span></span> <span data-ttu-id="3f9ac-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="3f9ac-106">Zadanie jest przeznaczone dla operatora maszyny.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-106">This task is intended for the machine operator.</span></span>

1. <span data-ttu-id="3f9ac-107">Przejdź do tablicy Kanban pokazującej zadania przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-107">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="3f9ac-108">W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-108">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="3f9ac-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3f9ac-110">Wybierz komórkę roboczą 1250 i kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-110">Select work cell 1250 and click OK.</span></span>  
4. <span data-ttu-id="3f9ac-111">Na liście zaznacz wiersz 4.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-111">In the list, select row 4.</span></span>
    * <span data-ttu-id="3f9ac-112">W firmie demonstracyjnej bez danych Kanban 000329 w wierszu numer 4 jest pierwszym zadaniem, które nie zostało jeszcze wykonane.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-112">In the clean demo company, Kanban 000329 in row 4 is the first job that is not completed yet.</span></span>  
5. <span data-ttu-id="3f9ac-113">Przełącz rozwinięcie sekcji Lista pobrania.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-113">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="3f9ac-114">Upewnij się, że stan dostaw wskazuje dostępność dla wszystkich towarów na liście pobrania.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-114">Verify that the supply status is available for all items in the picking list.</span></span>  
    * <span data-ttu-id="3f9ac-115">W przypadku wybrania wielu zadań na liście pobrania będzie widoczna suma wszystkich towarów potrzebnych dla wybranych zadań.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-115">If multiple jobs are selected, the picking list will show the sum of all items needed for the selected jobs.</span></span>  
6. <span data-ttu-id="3f9ac-116">Kliknij przycisk Przygotuj.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-116">Click Prepare.</span></span>
    * <span data-ttu-id="3f9ac-117">Proces przygotowywania jest teraz zakończony.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-117">The preparation process is now completed.</span></span> <span data-ttu-id="3f9ac-118">Zaznaczone pole wyboru dla wszystkich wierszy na liście pobrania wskazuje, że dostawa jest pobrana.</span><span class="sxs-lookup"><span data-stu-id="3f9ac-118">The selected check box for all rows in the picking list indicates that the supply status is picked.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]