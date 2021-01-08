---
title: Aktualizacja stanu w systemie Kanban
description: Gdy karta Kanban zostanie opróżniona przez pomyłkę lub otrzymana karta Kanban musi zostać opróżniona, należy zaktualizować stan karty Kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb8559c0843d7e6e538b5b29dc394a50d05462ee
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435390"
---
# <a name="update-kanban-status"></a><span data-ttu-id="a264b-103">Aktualizacja stanu w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="a264b-103">Update kanban status</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a264b-104">Gdy karta Kanban zostanie opróżniona przez pomyłkę lub otrzymana karta Kanban musi zostać opróżniona, należy zaktualizować stan karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="a264b-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="a264b-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="a264b-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a264b-106">Ta procedura jest przeznaczona dla kierownika produkcji.</span><span class="sxs-lookup"><span data-stu-id="a264b-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="a264b-107">Znajdź kartę Kanban.</span><span class="sxs-lookup"><span data-stu-id="a264b-107">Find the kanban.</span></span>
1. <span data-ttu-id="a264b-108">Wybierz kolejno opcje Kontrola produkcji > Kanban > Karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="a264b-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="a264b-109">Otwórz filtr kolumny Stan magazynowej jednostki obsługi.</span><span class="sxs-lookup"><span data-stu-id="a264b-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="a264b-110">Kliknij przycisk Wyczyść.</span><span class="sxs-lookup"><span data-stu-id="a264b-110">Click Clear.</span></span>
    * <span data-ttu-id="a264b-111">Spowoduje to zresetowanie filtrów.</span><span class="sxs-lookup"><span data-stu-id="a264b-111">This resets the filters.</span></span>  
4. <span data-ttu-id="a264b-112">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="a264b-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a264b-113">Na przykład wyfiltruj według pola Numer karty z wartością „000149”.</span><span class="sxs-lookup"><span data-stu-id="a264b-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="a264b-114">Zmiana stanu Opróżniono na Otrzymano</span><span class="sxs-lookup"><span data-stu-id="a264b-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="a264b-115">Kliknij opcję Wycofaj pustą magazynową jednostkę obsługi.</span><span class="sxs-lookup"><span data-stu-id="a264b-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="a264b-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a264b-116">Click OK.</span></span>
    * <span data-ttu-id="a264b-117">Zwróć uwagę, że pole Stan magazynowej jednostki obsługi ma wartość Otrzymano.</span><span class="sxs-lookup"><span data-stu-id="a264b-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="a264b-118">Zmiana stanu Otrzymano na Opróżniono</span><span class="sxs-lookup"><span data-stu-id="a264b-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="a264b-119">Kliknij opcję Pusta karta Kanban.</span><span class="sxs-lookup"><span data-stu-id="a264b-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="a264b-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="a264b-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a264b-121">Zwróć uwagę, że pole Stan magazynowej jednostki obsługi ma wartość Opróżniono.</span><span class="sxs-lookup"><span data-stu-id="a264b-121">Notice that the Handling unit status is Emptied.</span></span>  

