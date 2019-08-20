---
title: Aktualizacja stanu w systemie Kanban
description: Gdy karta Kanban zostanie opróżniona przez pomyłkę lub otrzymana karta Kanban musi zostać opróżniona, należy zaktualizować stan karty Kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 97b6eea4e93967dbe1eea5eac9fe3fbf6b336a49
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838470"
---
# <a name="update-kanban-status"></a><span data-ttu-id="a3e32-103">Aktualizacja stanu w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="a3e32-103">Update kanban status</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a3e32-104">Gdy karta Kanban zostanie opróżniona przez pomyłkę lub otrzymana karta Kanban musi zostać opróżniona, należy zaktualizować stan karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="a3e32-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="a3e32-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="a3e32-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a3e32-106">Ta procedura jest przeznaczona dla kierownika produkcji.</span><span class="sxs-lookup"><span data-stu-id="a3e32-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="a3e32-107">Znajdź kartę Kanban.</span><span class="sxs-lookup"><span data-stu-id="a3e32-107">Find the kanban.</span></span>
1. <span data-ttu-id="a3e32-108">Wybierz kolejno opcje Kontrola produkcji > Kanban > Karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="a3e32-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="a3e32-109">Otwórz filtr kolumny Stan magazynowej jednostki obsługi.</span><span class="sxs-lookup"><span data-stu-id="a3e32-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="a3e32-110">Kliknij przycisk Wyczyść.</span><span class="sxs-lookup"><span data-stu-id="a3e32-110">Click Clear.</span></span>
    * <span data-ttu-id="a3e32-111">Spowoduje to zresetowanie filtrów.</span><span class="sxs-lookup"><span data-stu-id="a3e32-111">This resets the filters.</span></span>  
4. <span data-ttu-id="a3e32-112">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="a3e32-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a3e32-113">Na przykład wyfiltruj według pola Numer karty z wartością „000149”.</span><span class="sxs-lookup"><span data-stu-id="a3e32-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="a3e32-114">Zmiana stanu Opróżniono na Otrzymano</span><span class="sxs-lookup"><span data-stu-id="a3e32-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="a3e32-115">Kliknij opcję Wycofaj pustą magazynową jednostkę obsługi.</span><span class="sxs-lookup"><span data-stu-id="a3e32-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="a3e32-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a3e32-116">Click OK.</span></span>
    * <span data-ttu-id="a3e32-117">Zwróć uwagę, że pole Stan magazynowej jednostki obsługi ma wartość Otrzymano.</span><span class="sxs-lookup"><span data-stu-id="a3e32-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="a3e32-118">Zmiana stanu Otrzymano na Opróżniono</span><span class="sxs-lookup"><span data-stu-id="a3e32-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="a3e32-119">Kliknij opcję Pusta karta Kanban.</span><span class="sxs-lookup"><span data-stu-id="a3e32-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="a3e32-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="a3e32-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a3e32-121">Zwróć uwagę, że pole Stan magazynowej jednostki obsługi ma wartość Opróżniono.</span><span class="sxs-lookup"><span data-stu-id="a3e32-121">Notice that the Handling unit status is Emptied.</span></span>  

