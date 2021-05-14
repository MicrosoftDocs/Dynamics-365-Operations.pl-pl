---
title: Automatyzacja procesu
description: Ten temat zawiera szczegółowe informacje dotyczące sposobu, w jaki funkcja Automatyzacji procesów umożliwia proste planowanie procesów, które będą wykonywane przez serwer przetwarzania wsadowego.
author: RyanCCarlson2
ms.date: 04/20/2021
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
ms.openlocfilehash: a8722adfe410f15bc379f9b550f0618c881f067d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920836"
---
# <a name="process-automation"></a><span data-ttu-id="ac6d7-103">Automatyzacja procesu</span><span class="sxs-lookup"><span data-stu-id="ac6d7-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ac6d7-104">Funkcja Automatyzacji procesów umożliwia proste planowanie procesów, które będą wykonywane przez serwer przetwarzania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="ac6d7-105">Zaktualizowany widok kalendarza pracy zaplanowanej umożliwia użytkownikom końcowym przeglądanie i podejmowanie działań dot. planowanej i zakończonej pracy.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="ac6d7-106">Administracja</span><span class="sxs-lookup"><span data-stu-id="ac6d7-106">Administration</span></span>

<span data-ttu-id="ac6d7-107">Strona Administracji centralnej dla wszystkich automatyzacji procesów znajduje się w module administrowania systemem w menu **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="ac6d7-108">Na tej stronie będzie wyświetlona lista wszystkich zautomatyzowanych procesów (seria) skonfigurowanych w systemie.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="ac6d7-109">Umożliwi to również dodawanie nowych automatyzacji procesów bezpośrednio z poziomu tej strony.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="ac6d7-110">Po skonfigurowaniu serii można zarządzać każdą z serii z tej listy.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="ac6d7-111">Można wybrać opcję edycji całej serii, usunąć ją, wyświetlić wszystkie wystąpienia w widoku listy lub wyłączyć serię, jeśli chcesz wstrzymać pracę według harmonogramu przez pewien czas.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-111">You can choose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a while.</span></span> 

<span data-ttu-id="ac6d7-112">Żadne procesy wyłączone w module Zarządzanie funkcjami nie będą widoczne, gdy funkcja jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-112">Any processes that are disabled in feature management won't show when the feature is disabled.</span></span> <span data-ttu-id="ac6d7-113">Ponadto aparat planowania automatyzacji procesów nie będzie planować wystąpień ani procesów wykonywanych w tle dla wyłączonej funkcji.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-113">Additionally, the process automation scheduling engine won't schedule any occurrences or background processes for a disabled feature.</span></span> <span data-ttu-id="ac6d7-114">Ponowne włączenie tej funkcji spowoduje natychmiastowe uruchomienie wszystkich zaplanowanych w przeszłości wystąpień lub procesów w tle.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-114">Re-enabling the feature will cause any scheduled occurrences or background processes in the past to run immediately.</span></span> <span data-ttu-id="ac6d7-115">Działanie aparatu planowania automatyzacji procesów zależy od systemowego zadania wsadowego **Sondowanie automatyzacji procesów**.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-115">The process automation scheduling engine relies on the system batch job, **Process automation polling system job** to run.</span></span> <span data-ttu-id="ac6d7-116">Zadania nie należy w żadnym momencie zmieniać ani modyfikować.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-116">The job shouldn't be altered or tampered with at any time.</span></span> 

## <a name="calendar-view"></a><span data-ttu-id="ac6d7-117">Widok kalendarza</span><span class="sxs-lookup"><span data-stu-id="ac6d7-117">Calendar view</span></span>

<span data-ttu-id="ac6d7-118">Jedną z głównych zalet automatyzacji procesu jest możliwość wyświetlania pracy według harmonogramu w prostym widoku kalendarzowym.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-118">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="ac6d7-119">Ten widok umożliwia oglądanie pracy w danym tygodniu.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-119">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="ac6d7-120">Ten widok będzie dostępny po prawej stronie strony **Automatyzacji procesów**.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-120">You'll see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="ac6d7-121">Zostanie ona wypełniona pracą według harmonogramu dla wybranej serii.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-121">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="ac6d7-122">[![Kalendarz automatyzacji procesu](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="ac6d7-122">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="ac6d7-123">Zmiany wystąpienia</span><span class="sxs-lookup"><span data-stu-id="ac6d7-123">Occurrence changes</span></span>

<span data-ttu-id="ac6d7-124">Każde wystąpienie może zostać zmodyfikowane bez wpływu na inne wystąpienia zdefiniowane przez serie, w których powstały.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-124">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="ac6d7-125">Wystąpienia zaplanowanej pracy można edytować w widoku kalendarza, wybierając przycisk **Widok/Edycja** i wybierając polecenie **Wystąpienie**.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-125">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="ac6d7-126">Ta strona umożliwia to dostęp do wszystkich ustawień początkowo wyświetlanych w Kreatorze ustawień serii i umożliwia dokonywanie jednorazowej zmiany w wybranym wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-126">This page allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="ac6d7-127">Wystąpienie pracy zaplanowanej można również wyłączyć, zaznaczając przycisk **Wyłącz** w widoku Kalendarz.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-127">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span>

## <a name="developer-documentation"></a><span data-ttu-id="ac6d7-128">Dokumentacja dewelopera</span><span class="sxs-lookup"><span data-stu-id="ac6d7-128">Developer documentation</span></span>

<span data-ttu-id="ac6d7-129">Struktura automatyzacji procesów umożliwia programistom rozszerzenie struktury automatyzacji procesów.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-129">The process automation framework allows developers to extend the process automation framework.</span></span> <span data-ttu-id="ac6d7-130">W dokumentacji [Struktura automatyzacji procesów](../process-automation/process-automation-framework.md) znajdują się informacje dotyczące sposobu tworzenia niestandardowych procesów, które trzeba uruchomić przez serwer przetwarzania wsadowego zaplanowanego za pomocą Kreatora automatyzacji procesów i automatycznie wyświetlanych w widoku Kalendarz.</span><span class="sxs-lookup"><span data-stu-id="ac6d7-130">The [Process automation framework](../process-automation/process-automation-framework.md) documentation provides information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
