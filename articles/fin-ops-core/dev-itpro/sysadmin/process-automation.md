---
title: Automatyzacja procesu
description: Ten temat zawiera szczegółowe informacje dotyczące sposobu, w jaki funkcja Automatyzacji procesów umożliwia proste planowanie procesów, które będą wykonywane przez serwer przetwarzania wsadowego.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 08/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: e3babed18caefff16105f70a0b15b8b8cf0f08eb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568217"
---
# <a name="process-automation"></a><span data-ttu-id="c0310-103">Automatyzacja procesu</span><span class="sxs-lookup"><span data-stu-id="c0310-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c0310-104">Funkcja Automatyzacji procesów umożliwia proste planowanie procesów, które będą wykonywane przez serwer przetwarzania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="c0310-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="c0310-105">Zaktualizowany widok kalendarza pracy zaplanowanej umożliwia użytkownikom końcowym przeglądanie i podejmowanie działań dot. planowanej i zakończonej pracy.</span><span class="sxs-lookup"><span data-stu-id="c0310-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="c0310-106">Administracja</span><span class="sxs-lookup"><span data-stu-id="c0310-106">Administration</span></span>

<span data-ttu-id="c0310-107">Strona Administracji centralnej dla wszystkich automatyzacji procesów znajduje się w module administrowania systemem w menu **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="c0310-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="c0310-108">Na tej stronie będzie wyświetlona lista wszystkich zautomatyzowanych procesów (seria) skonfigurowanych w systemie.</span><span class="sxs-lookup"><span data-stu-id="c0310-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="c0310-109">Umożliwi to również dodawanie nowych automatyzacji procesów bezpośrednio z poziomu tej strony.</span><span class="sxs-lookup"><span data-stu-id="c0310-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="c0310-110">Po skonfigurowaniu serii można zarządzać każdą z serii z tej listy.</span><span class="sxs-lookup"><span data-stu-id="c0310-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="c0310-111">Można wybrać opcję edycji całej serii, usunąć ją, wyświetlić wszystkie wystąpienia w widoku listy lub wyłączyć serię, jeśli chcesz wstrzymać pracę według harmonogramu przez pewien czas.</span><span class="sxs-lookup"><span data-stu-id="c0310-111">You can choose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a while.</span></span> 

<span data-ttu-id="c0310-112">Żadne procesy wyłączone w module Zarządzanie funkcjami nie będą widoczne, gdy funkcja jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="c0310-112">Any processes that are disabled in feature management won't show when the feature is disabled.</span></span> <span data-ttu-id="c0310-113">Ponadto aparat planowania automatyzacji procesów nie będzie planować wystąpień ani procesów wykonywanych w tle dla wyłączonej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c0310-113">Additionally, the process automation scheduling engine won't schedule any occurrences or background processes for a disabled feature.</span></span> <span data-ttu-id="c0310-114">Ponowne włączenie tej funkcji spowoduje natychmiastowe uruchomienie wszystkich zaplanowanych w przeszłości wystąpień lub procesów w tle.</span><span class="sxs-lookup"><span data-stu-id="c0310-114">Re-enabling the feature will cause any scheduled occurrences or background processes in the past to run immediately.</span></span>

## <a name="calendar-view"></a><span data-ttu-id="c0310-115">Widok kalendarza</span><span class="sxs-lookup"><span data-stu-id="c0310-115">Calendar view</span></span>

<span data-ttu-id="c0310-116">Jedną z głównych zalet automatyzacji procesu jest możliwość wyświetlania pracy według harmonogramu w prostym widoku kalendarzowym.</span><span class="sxs-lookup"><span data-stu-id="c0310-116">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="c0310-117">Ten widok umożliwia oglądanie pracy w danym tygodniu.</span><span class="sxs-lookup"><span data-stu-id="c0310-117">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="c0310-118">Ten widok będzie dostępny po prawej stronie strony **Automatyzacji procesów**.</span><span class="sxs-lookup"><span data-stu-id="c0310-118">You'll see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="c0310-119">Zostanie ona wypełniona pracą według harmonogramu dla wybranej serii.</span><span class="sxs-lookup"><span data-stu-id="c0310-119">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="c0310-120">[![Kalendarz automatyzacji procesu](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="c0310-120">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="c0310-121">Zmiany wystąpienia</span><span class="sxs-lookup"><span data-stu-id="c0310-121">Occurrence changes</span></span>

<span data-ttu-id="c0310-122">Każde wystąpienie może zostać zmodyfikowane bez wpływu na inne wystąpienia zdefiniowane przez serie, w których powstały.</span><span class="sxs-lookup"><span data-stu-id="c0310-122">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="c0310-123">Wystąpienia zaplanowanej pracy można edytować w widoku kalendarza, wybierając przycisk **Widok/Edycja** i wybierając polecenie **Wystąpienie**.</span><span class="sxs-lookup"><span data-stu-id="c0310-123">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="c0310-124">Ta strona umożliwia to dostęp do wszystkich ustawień początkowo wyświetlanych w Kreatorze ustawień serii i umożliwia dokonywanie jednorazowej zmiany w wybranym wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="c0310-124">This page allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="c0310-125">Wystąpienie pracy zaplanowanej można również wyłączyć, zaznaczając przycisk **Wyłącz** w widoku Kalendarz.</span><span class="sxs-lookup"><span data-stu-id="c0310-125">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span>

## <a name="developer-documentation"></a><span data-ttu-id="c0310-126">Dokumentacja dewelopera</span><span class="sxs-lookup"><span data-stu-id="c0310-126">Developer documentation</span></span>

<span data-ttu-id="c0310-127">Struktura automatyzacji procesów umożliwia programistom rozszerzenie struktury automatyzacji procesów.</span><span class="sxs-lookup"><span data-stu-id="c0310-127">The process automation framework allows developers to extend the process automation framework.</span></span> <span data-ttu-id="c0310-128">W dokumentacji [Struktura automatyzacji procesów](../process-automation/process-automation-framework.md) znajdują się informacje dotyczące sposobu tworzenia niestandardowych procesów, które trzeba uruchomić przez serwer przetwarzania wsadowego zaplanowanego za pomocą Kreatora automatyzacji procesów i automatycznie wyświetlanych w widoku Kalendarz.</span><span class="sxs-lookup"><span data-stu-id="c0310-128">The [Process automation framework](../process-automation/process-automation-framework.md) documentation provides information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]