---
title: Zbiorowe zamykanie okresów obrachunkowych
description: W tym temacie pokazano sposób zawieszania okresu lub trwałego zamykania okresu albo więcej niż jednej firmy na raz.
author: aprilolson
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 398a62e575010501291af3016553fc72fbc891de
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186102"
---
# <a name="mass-financial-period-close"></a><span data-ttu-id="67170-103">Zbiorowe zamykanie okresów obrachunkowych</span><span class="sxs-lookup"><span data-stu-id="67170-103">Mass financial period close</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="67170-104">W tym temacie pokazano sposób zawieszania okresu lub trwałego zamykania okresu albo więcej niż jednej firmy na raz.</span><span class="sxs-lookup"><span data-stu-id="67170-104">This topic shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="67170-105">Ponadto w zadaniu zostanie pokazane, jak ograniczyć księgowanie przez grupę użytkowników do określonych modułów.</span><span class="sxs-lookup"><span data-stu-id="67170-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="67170-106">W okienku nawigacji przejdź do **Moduły > Księga główna > Zamykanie okresu > Kalendarze księgi**.</span><span class="sxs-lookup"><span data-stu-id="67170-106">In the navigation pane, go to **Modules > General ledger > Period close > Ledger calendars**.</span></span> <span data-ttu-id="67170-107">Należy zauważyć, że wyświetlana lista firm zależy od kalendarza obrachunkowego wybranego na stronie.</span><span class="sxs-lookup"><span data-stu-id="67170-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="67170-108">Zostaną wyświetlone tylko firmy używające wybranego kalendarza obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="67170-108">Only legal entities using the selected fiscal calendar will display.</span></span>
2. <span data-ttu-id="67170-109">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="67170-109">Select **Edit**.</span></span>
3. <span data-ttu-id="67170-110">Wybierz okres, dla którego chcesz zmodyfikować stan.</span><span class="sxs-lookup"><span data-stu-id="67170-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="67170-111">Wybierz firmy, dla których chcesz zaktualizować stan.</span><span class="sxs-lookup"><span data-stu-id="67170-111">Select the legal entities for which you want to update the status.</span></span> <span data-ttu-id="67170-112">Możesz szybko wybrać wszystkie firmy zaznaczając znacznik wyboru w lewej górnej części siatki.</span><span class="sxs-lookup"><span data-stu-id="67170-112">You can quickly select all legal entities by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="67170-113">Wybierz opcję **Aktualizuj dostęp do modułu**, aby zdefiniować uprawnienia księgowania do wybranego modułu.</span><span class="sxs-lookup"><span data-stu-id="67170-113">Select **Update module access** to define the posting access to a selected module.</span></span> <span data-ttu-id="67170-114">Stan modułu może być również aktualizowany jednostkowo poprzez edycję rekordów w siatce.</span><span class="sxs-lookup"><span data-stu-id="67170-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="67170-115">Przycisk jest przydatny, gdy chcesz szybko aktualizować wiele rekordów firm.</span><span class="sxs-lookup"><span data-stu-id="67170-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="67170-116">W module **Aplikacja** zaznacz moduł, któremu chcesz zaktualizować stan.</span><span class="sxs-lookup"><span data-stu-id="67170-116">In the **Application** module, select the module that you want to update the status.</span></span> <span data-ttu-id="67170-117">Kliknij opcję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="67170-117">Click **Select**.</span></span>
7. <span data-ttu-id="67170-118">W polu poziom **Dostępu** zaznacz wartość **Wszystko**, **Brak** lub konkretną grupę użytkowników.</span><span class="sxs-lookup"><span data-stu-id="67170-118">In the **Access** level, select **All**, **None**, or a specific user group.</span></span> <span data-ttu-id="67170-119">Kliknij opcję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="67170-119">Click **Select**.</span></span> <span data-ttu-id="67170-120">Opcja Wszystko wskazuje, że wszyscy użytkownicy z prawem edycji modułu mogą księgować, jeśli okres jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="67170-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="67170-121">Opcja Brak wskazuje, że użytkownicy nie mogą księgować w module, jeśli okres jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="67170-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="67170-122">Zaznaczenie określonej grupy użytkowników oznacza, że tylko użytkownicy należący do grupy mogą księgować w module, jeśli okres jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="67170-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="67170-123">Wybierz **Aktualizuj**.</span><span class="sxs-lookup"><span data-stu-id="67170-123">Select **Update**.</span></span>
9. <span data-ttu-id="67170-124">Wybierz inny okres, aby zaktualizować stan.</span><span class="sxs-lookup"><span data-stu-id="67170-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="67170-125">Wybierz firmy, dla których chcesz zaktualizować stan okresu.</span><span class="sxs-lookup"><span data-stu-id="67170-125">Select the legal entites for which you want to update the period status.</span></span>
11. <span data-ttu-id="67170-126">Wybierz opcję **Aktualizuj stan okresu** i ustaw stan **Wstrzymane**, **Otwarte** lub **Trwale zamknięty**.</span><span class="sxs-lookup"><span data-stu-id="67170-126">Select **Update period status** and set the status of **On hold**, **Open**, or **Permanently closed**.</span></span> <span data-ttu-id="67170-127">**Otwarte** wskazuje, że można księgować w okresie, pod warunkiem, że użytkownik ma dostęp.</span><span class="sxs-lookup"><span data-stu-id="67170-127">**Open** indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="67170-128">Wartość **Wstrzymane** oznacza, że nie może księgować w okresie, ale okres można otworzyć ponownie.</span><span class="sxs-lookup"><span data-stu-id="67170-128">**On hold** means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="67170-129">Wartość **Trwale zamknięty** oznacza, że okres jest zamknięty i już nigdy nie można go otworzyć.</span><span class="sxs-lookup"><span data-stu-id="67170-129">**Permanently closed** means the period is closed and can never be opened.</span></span> <span data-ttu-id="67170-130">Nie można księgować korekt.</span><span class="sxs-lookup"><span data-stu-id="67170-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="67170-131">Nie zaleca się ustawiania okresu na **Trwale zamknięty** do czasu zakończenia wszystkich korekt i inspekcji.</span><span class="sxs-lookup"><span data-stu-id="67170-131">We do not recommend setting a period to **Permanently closed** until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="67170-132">Wybierz **Aktualizuj**.</span><span class="sxs-lookup"><span data-stu-id="67170-132">Select **Update**.</span></span>

