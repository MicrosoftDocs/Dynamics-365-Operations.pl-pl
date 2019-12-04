---
title: Automatyczne akceptowanie z optymalizacją planowania
description: W tym temacie opisano sposób korzystania z funkcji automatycznego ustalania z optymalizacją planowania.
author: ChristianRytt
manager: AnnBe
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 90319222e7357d7c54243faa8c64575377348467
ms.sourcegitcommit: 0138b6c108a10f2bcb90c91205da8092917160d8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2783160"
---
# <a name="auto-firming-with-planning-optimization"></a><span data-ttu-id="c8e34-103">Automatyczne akceptowanie z optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="c8e34-103">Auto-firming with Planning Optimization</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c8e34-104">Funkcja automatycznego ustalania umożliwia nadawanie zamówień planowanych (zwolnienie) jako części procesu planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="c8e34-104">Automatic firming lets you firm (that is, release) planned orders as part of the master planning process.</span></span> <span data-ttu-id="c8e34-105">Podczas ustalania zamówień planowanych są one przekształcane w rzeczywiste zamówienia zakupu, zamówienia przeniesienia lub zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="c8e34-105">When planned orders are firmed, they are transformed into actual purchase orders, transfer orders, or production orders.</span></span> <span data-ttu-id="c8e34-106">Jeśli jest używana optymalizacja planowania, zamówienia planowane są ustalane podczas planowania głównego, gdy data zamówienia (czyli data rozpoczęcia) przypada w ramach horyzontu czasowego do ustalenia.</span><span class="sxs-lookup"><span data-stu-id="c8e34-106">When Planning Optimization is used, planned orders are firmed during a master planning run when the order date (that is, the start date) is within the time fence for firming.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e34-107">Aby możliwe było automatyczne ustalanie planowanego zamówienia zakupu, towar musi być skojarzony z dostawcą.</span><span class="sxs-lookup"><span data-stu-id="c8e34-107">Auto-firming of a planned purchase order can occur only if the item is associated with a vendor.</span></span>

## <a name="turn-on-auto-firming"></a><span data-ttu-id="c8e34-108">Włącz automatyczne akceptowanie</span><span class="sxs-lookup"><span data-stu-id="c8e34-108">Turn on auto-firming</span></span>

<span data-ttu-id="c8e34-109">Aby włączyć automatyczne akceptowanie, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c8e34-109">To turn on auto-firming, follow these steps.</span></span>

1. <span data-ttu-id="c8e34-110">W obszarze roboczym **Zarządzanie funkcjami** na liście na **nowej** karcie Wybierz opcję **Automatyczne ustalanie na potrzeby optymalizacji** planowania z listy.</span><span class="sxs-lookup"><span data-stu-id="c8e34-110">In the **Feature management** workspace, on the **New** tab, select **Auto-firming for Planning Optimization** in the list.</span></span> <span data-ttu-id="c8e34-111">Jeśli funkcja nie jest wyświetlana na **nowej** karcie, sprawdź, czy **nie jest włączona** i **wszystkie** karty.</span><span class="sxs-lookup"><span data-stu-id="c8e34-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="c8e34-112">Wybierz **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="c8e34-112">Select **Enable now**.</span></span> <span data-ttu-id="c8e34-113">Możesz też wybrać **harmonogram**, a następnie wybrać czas, w którym funkcja ma być włączona</span><span class="sxs-lookup"><span data-stu-id="c8e34-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

## <a name="set-up-the-firming-time-fence"></a><span data-ttu-id="c8e34-114">Ustal horyzont czasowy akceptacji</span><span class="sxs-lookup"><span data-stu-id="c8e34-114">Set up the firming time fence</span></span>

<span data-ttu-id="c8e34-115">Ten horyzont czasowy akceptowania jest obliczany od daty planowanego uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="c8e34-115">The firming time fence is calculated forward from the master planning run date.</span></span> <span data-ttu-id="c8e34-116">Jest definiowane liczbą dni, która została wpisana.</span><span class="sxs-lookup"><span data-stu-id="c8e34-116">It's defined by the number of days that you enter.</span></span> <span data-ttu-id="c8e34-117">Horyzont czasowy ustalania można kontrolować w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c8e34-117">You can control the firming time fence in the following ways:</span></span>

- <span data-ttu-id="c8e34-118">Aby zdefiniować domyślny horyzont czasowy ustalania dla grupy zapotrzebowania, należy przejść do grup **Planowanie główne** \> **Ustawienia** \> **Zapotrzebowanie** \> **Grupy zapotrzebowania** i wybrać grupę zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="c8e34-118">To define the default firming time fence for a coverage group, go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**, and select a coverage group.</span></span> <span data-ttu-id="c8e34-119">Następnie, na skróconej karcie w **Inne**, w polu **automatyczny horyzont czasowy akceptacji (dni)** wprowadź liczbę dni.</span><span class="sxs-lookup"><span data-stu-id="c8e34-119">Then, on the **Other** FastTab, in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="c8e34-120">Aby zastąpić horyzont czasowy ustalania, który jest zdefiniowany dla grupy zapotrzebowania dla określonego towaru, przejdź do zwolnionych produktów w module **Zarządzanie informacjami o produktach** \> **Zwolnione produkty**, następnie w okienku akcji wybierz pozycję **plan**, a następnie wybierz pozycję **zapotrzebowanie na towar**.</span><span class="sxs-lookup"><span data-stu-id="c8e34-120">To overwrite the firming time fence that is defined for the coverage group for a specific item, go to **Product information management** \> **Released products**, then from the action pane select **Plan** and then select **Item coverage**.</span></span> <span data-ttu-id="c8e34-121">Następnie na karcie **Ogólne** wybierz opcję **Zastąp horyzont czasowy**, a następnie w polu **automatyczny horyzont czasowy akceptacji (dni)** wprowadź liczbę dni.</span><span class="sxs-lookup"><span data-stu-id="c8e34-121">Then, on the **General** tab, select **Override time fence** and in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="c8e34-122">Aby zastąpić horyzont czasowy ustalania, który jest zdefiniowany dla grupy zapotrzebowania i zapotrzebowania na towary dla określonego planu głównego, należy przejść do **Planowanie główne** \> **Ustawienia** \> **Plany główne** i wybrać plan główny.</span><span class="sxs-lookup"><span data-stu-id="c8e34-122">To overwrite the firming time fence that is defined for the coverage group and item coverage for a specific master plan, go to **Master planning** \> **Setup** \> **Master plans**, and select a Master plan.</span></span> <span data-ttu-id="c8e34-123">Następnie, na skróconej karcie w **Time fence in days**, ustaw **Zamrożenie** na wartość **Tak** wprowadź liczbę dni.</span><span class="sxs-lookup"><span data-stu-id="c8e34-123">Then, on the **Time fence in days** FastTab, set **Freeze** to **Yes**, and enter the number of days.</span></span>

<span data-ttu-id="c8e34-124">Jeśli funkcja automatycznego ustalania jest włączona dla przebiegu planowania głównego, w którym jest używana Optymalizacja planowania, proces automatycznego ustalania jest wykonywany zgodnie z konfiguracją automatycznego ustalania.</span><span class="sxs-lookup"><span data-stu-id="c8e34-124">If auto-firming is turned on for a master planning run that uses Planning Optimization, the auto-firming process is done according to the auto-firming setup.</span></span> <span data-ttu-id="c8e34-125">Jeśli funkcja automatycznego ustalania nie jest włączona lub jeśli planowanie jest uruchamiane na stronie **zapotrzebowanie netto**, proces automatycznego ustalania zostanie pominięty.</span><span class="sxs-lookup"><span data-stu-id="c8e34-125">If auto-firming isn't turned on, or if planning is started from the **Net requirements** page, the auto-firming process is skipped.</span></span>

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a><span data-ttu-id="c8e34-126">Planowanie optymalizacji w porównaniu z wbudowanym aparatem planowania Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c8e34-126">Planning Optimization vs. the built-in Supply Chain Management planning engine</span></span>

<span data-ttu-id="c8e34-127">Zarówno Optymalizacja planowania, jak i aparat planowania wbudowany w firmę Microsoft Dynamics 365 Supply Chain Management mogą być używane do automatycznego ustalania zamówień planowanych.</span><span class="sxs-lookup"><span data-stu-id="c8e34-127">Both Planning Optimization and the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management can be used to auto-firm planned orders.</span></span> <span data-ttu-id="c8e34-128">Istnieją jednak pewne ważne różnice.</span><span class="sxs-lookup"><span data-stu-id="c8e34-128">However, there are some important differences.</span></span> <span data-ttu-id="c8e34-129">Na przykład w optymalizacji planowania jest używana Data zamówienia (to znaczy Data rozpoczęcia) w celu ustalenia, które zamówienia planowane mają zostać ustalone, wbudowany aparat planowania Supply Chain Management używa daty zapotrzebowania (Data zakończenia).</span><span class="sxs-lookup"><span data-stu-id="c8e34-129">For example, whereas Planning Optimization uses the order date (that is, the start date) to determine which planned orders to firm, the built-in Supply Chain Management planning engine uses the requirement date (that is, the end date).</span></span> <span data-ttu-id="c8e34-130">Poniżej znajduje się podsumowanie różnic.</span><span class="sxs-lookup"><span data-stu-id="c8e34-130">Here is a summary of the differences.</span></span>

<span data-ttu-id="c8e34-131">**Optymalizacja planowania**</span><span class="sxs-lookup"><span data-stu-id="c8e34-131">**Planning Optimization**</span></span>

- <span data-ttu-id="c8e34-132">Automatyczne ustalanie jest oparte na dacie zamówienia (Data początkowa).</span><span class="sxs-lookup"><span data-stu-id="c8e34-132">Auto-firming is based on the order date (start date).</span></span>
- <span data-ttu-id="c8e34-133">Ponieważ Data zamówienia (Data początkowa) wyzwala akceptację, nie trzeba brać pod uwagę czasu realizacji w ramach horyzontu czasowego ustalania.</span><span class="sxs-lookup"><span data-stu-id="c8e34-133">Because the order date (start date) triggers the firming, you don't have to consider the lead time as part of the firming time fence.</span></span>
- <span data-ttu-id="c8e34-134">Jeśli chcesz ustalić wszystkie zamówienia, które muszą się rozpoczynać w bieżącym tygodniu, horyzont czasowy ustalania musi wynosić jeden tydzień.</span><span class="sxs-lookup"><span data-stu-id="c8e34-134">If you want to firm all orders that must start during the current week, the firming time fence must be one week.</span></span>

<span data-ttu-id="c8e34-135">**Wbudowany silnik planowania Supply Chain Management**</span><span class="sxs-lookup"><span data-stu-id="c8e34-135">**Built-in Supply Chain Management planning engine**</span></span>

- <span data-ttu-id="c8e34-136">Automatyczne ustalanie jest oparte na dacie zapotrzebowania (Data końcowa).</span><span class="sxs-lookup"><span data-stu-id="c8e34-136">Auto-firming is based on the requirement date (end date).</span></span>
- <span data-ttu-id="c8e34-137">W celu zagwarantowania akceptacji zamówień w odpowiednim czasie horyzont czasowy ustalania musi być dłuższy niż czas realizacji.</span><span class="sxs-lookup"><span data-stu-id="c8e34-137">To help guarantee that orders are firmed in due time, the firming time fence must be longer than the lead time.</span></span>
- <span data-ttu-id="c8e34-138">Jeśli chcesz ustalić wszystkie zamówienia, które muszą się rozpoczynać w bieżącym tygodniu, horyzont czasowy ustalania musi wynosić czas realizacji plus jeden tydzień.</span><span class="sxs-lookup"><span data-stu-id="c8e34-138">If you want to firm all orders that must start during the current week, the firming time fence must be the lead time plus one week.</span></span>
