--- 
title: "Masowe zamykanie okresów obrachunkowych"
description: "W tej procedurze pokazano sposób zawieszania okresu lub trwałego zamykania okresu albo więcej niż jednej firmy na raz."
author: aprilolson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: cafd837be054e96afc10d3b78402bdcc67c43c33
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="mass-financial-period-close"></a><span data-ttu-id="4a554-103">Masowe zamykanie okresów obrachunkowych</span><span class="sxs-lookup"><span data-stu-id="4a554-103">Mass financial period close</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4a554-104">W tej procedurze pokazano sposób zawieszania okresu lub trwałego zamykania okresu albo więcej niż jednej firmy na raz.</span><span class="sxs-lookup"><span data-stu-id="4a554-104">This procedure shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="4a554-105">Ponadto w zadaniu zostanie pokazane, jak ograniczyć księgowanie przez grupę użytkowników do określonych modułów.</span><span class="sxs-lookup"><span data-stu-id="4a554-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="4a554-106">Wybierz kolejno opcje Księga główna > Zamykanie okresu > Kalendarze księgi.</span><span class="sxs-lookup"><span data-stu-id="4a554-106">Go to General ledger > Period close > Ledger calendars.</span></span>
    * <span data-ttu-id="4a554-107">Należy zauważyć, że wyświetlana lista firm zależy od kalendarza obrachunkowego wybranego na stronie.</span><span class="sxs-lookup"><span data-stu-id="4a554-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="4a554-108">Zostaną wyświetlone tylko firmy używające wybranego kalendarza obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="4a554-108">Only legal entities using the selected fiscal calendar will display.</span></span>  
2. <span data-ttu-id="4a554-109">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="4a554-109">Click Edit.</span></span>
3. <span data-ttu-id="4a554-110">Wybierz okres, dla którego chcesz zmodyfikować stan.</span><span class="sxs-lookup"><span data-stu-id="4a554-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="4a554-111">Wybierz firmy, dla których chcesz zaktualizować stan.</span><span class="sxs-lookup"><span data-stu-id="4a554-111">Select the legal entities for which you want to update the status.</span></span>
    * <span data-ttu-id="4a554-112">Możesz szybko wybrać wszystkie firmy, zaznaczając znacznik wyboru w lewej górnej części siatki.</span><span class="sxs-lookup"><span data-stu-id="4a554-112">You can quickly select all legal entities  by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="4a554-113">Wybierz opcję Aktualizuj dostęp do modułu, aby zdefiniować uprawnienia księgowania do wybranego modułu.</span><span class="sxs-lookup"><span data-stu-id="4a554-113">Select Update module access to define the posting access to a selected module.</span></span>
    * <span data-ttu-id="4a554-114">Stan modułu może być również aktualizowany jednostkowo poprzez edycję rekordów w siatce.</span><span class="sxs-lookup"><span data-stu-id="4a554-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="4a554-115">Przycisk jest przydatny, gdy chcesz szybko aktualizować wiele rekordów firm.</span><span class="sxs-lookup"><span data-stu-id="4a554-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="4a554-116">W polu Moduł aplikacji zaznacz moduł, któremu chcesz zaktualizować stan.</span><span class="sxs-lookup"><span data-stu-id="4a554-116">In the Application module, select the module that you want to update the status.</span></span> <span data-ttu-id="4a554-117">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="4a554-117">Click Select.</span></span>
7. <span data-ttu-id="4a554-118">W polu Poziom dostępu zaznacz wartość Wszystko, Brak lub konkretną grupę użytkowników.</span><span class="sxs-lookup"><span data-stu-id="4a554-118">In the Access level, select All, None, or a specific user group.</span></span> <span data-ttu-id="4a554-119">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="4a554-119">Click Select.</span></span>
    * <span data-ttu-id="4a554-120">Opcja Wszystko wskazuje, że wszyscy użytkownicy z prawem edycji modułu mogą księgować, jeśli okres jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="4a554-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="4a554-121">Opcja Brak wskazuje, że użytkownicy nie mogą księgować w module, jeśli okres jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="4a554-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="4a554-122">Zaznaczenie określonej grupy użytkowników oznacza, że tylko użytkownicy należący do grupy mogą księgować w module, jeśli okres jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="4a554-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="4a554-123">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="4a554-123">Click Update.</span></span>
9. <span data-ttu-id="4a554-124">Wybierz inny okres, aby zaktualizować stan.</span><span class="sxs-lookup"><span data-stu-id="4a554-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="4a554-125">Wybierz firmy, dla których chcesz zaktualizować stan okresu.</span><span class="sxs-lookup"><span data-stu-id="4a554-125">Select the legal entities for which you want to update the period status.</span></span>
11. <span data-ttu-id="4a554-126">Wybierz opcję Aktualizuj stan okresu i ustaw stan Wstrzymane, Otwarte lub Trwale zamknięty.</span><span class="sxs-lookup"><span data-stu-id="4a554-126">Select Update period status and set the status of On hold, Open, or Permanently closed.</span></span>
    * <span data-ttu-id="4a554-127">Opcja Otwarta wskazuje, że można księgować w okresie, pod warunkiem, że użytkownik ma dostęp.</span><span class="sxs-lookup"><span data-stu-id="4a554-127">Open indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="4a554-128">Wartość Wstrzymane oznacza, że nie może księgować w okresie, ale okres można otworzyć ponownie.</span><span class="sxs-lookup"><span data-stu-id="4a554-128">On hold means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="4a554-129">Wartość Trwale zamknięty oznacza, że okres jest zamknięty i już nigdy nie można go otworzyć.</span><span class="sxs-lookup"><span data-stu-id="4a554-129">Permanently closed means the period is closed and can never be opened.</span></span> <span data-ttu-id="4a554-130">Nie można księgować korekt.</span><span class="sxs-lookup"><span data-stu-id="4a554-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="4a554-131">Nie zaleca się ustawiania okresu na Trwale zamknięty do czasu zakończenia wszystkich korekt i inspekcji.</span><span class="sxs-lookup"><span data-stu-id="4a554-131">We do not recommend setting a period to Permanently closed until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="4a554-132">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="4a554-132">Click Update.</span></span>


