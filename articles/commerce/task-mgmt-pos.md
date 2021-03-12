---
title: Zarządzanie zadaniami w punkcie sprzedaży
description: W tym temacie opisano zarządzanie zadaniami w aplikacji punktu sprzedaży (POS) w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 889cc90b534de33ccd0e2bea367b2da42b5d72e0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006192"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="28e47-103">Zarządzanie zadaniami w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="28e47-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="28e47-104">W tym temacie opisano zarządzanie zadaniami w aplikacji punktu sprzedaży (POS) w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="28e47-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

## <a name="overview"></a><span data-ttu-id="28e47-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="28e47-105">Overview</span></span>

<span data-ttu-id="28e47-106">Aplikacja punktu sprzedaży Dynamics 365 Commerce zawiera funkcje zarządzania zadaniami, które umożliwiają menedżerom i pracownikom sklepów zarządzanie zadaniami i aktualizowanie stanu zadań.</span><span class="sxs-lookup"><span data-stu-id="28e47-106">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="28e47-107">Pracownicy sklepów mogą uzyskać dostęp do zadań, zaznaczając kafelek **Zadania** na stronie głównej punktu sprzedaży lub wybierając powiadomienia o zadaniach.</span><span class="sxs-lookup"><span data-stu-id="28e47-107">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="28e47-108">Domyślnie pracownicy sklepów są przeniesieni na kartę **Moje zadania**, gdzie mogą przeglądać przypisane do nich zadania.</span><span class="sxs-lookup"><span data-stu-id="28e47-108">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="28e47-109">Mogą jednak łatwo przełączać się do kart **Zaległe zadania**, **Zadania otwarte** i **Listy zadań**.</span><span class="sxs-lookup"><span data-stu-id="28e47-109">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="28e47-110">Operacje zadania dla menedżerów sklepów</span><span class="sxs-lookup"><span data-stu-id="28e47-110">Task operations for store managers</span></span>

<span data-ttu-id="28e47-111">Menedżerowie sklepów mogą wykonywać następujące operacje dotyczące zadań w aplikacji punktu sprzedaży za pomocą przycisków na pasku poleceń:</span><span class="sxs-lookup"><span data-stu-id="28e47-111">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="28e47-112">**Przypisanie** — przydzielenie wybranych zadań do pracownika sklepu.</span><span class="sxs-lookup"><span data-stu-id="28e47-112">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="28e47-113">**Stan zadania** — umożliwia zmianę stanu zaznaczonych zadań.</span><span class="sxs-lookup"><span data-stu-id="28e47-113">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="28e47-114">**Filtr** — domyślnie są wyświetlane tylko aktywne zadania.</span><span class="sxs-lookup"><span data-stu-id="28e47-114">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="28e47-115">Jednak dzięki zastosowaniu filtrów menedżerowie mogą wyświetlać wszystkie zadania, nawet zadania, które zostały wykonane lub anulowane.</span><span class="sxs-lookup"><span data-stu-id="28e47-115">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="28e47-116">**Nowe zadanie** — umożliwia utworzenie zadania na istniejącej liście zadań lub utworzenie zadania jednokierunkowego.</span><span class="sxs-lookup"><span data-stu-id="28e47-116">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="28e47-117">Pracownicy sklepów mogą wykonywać następujące operacje dotyczące zadań w aplikacji punktu sprzedaży za pomocą przycisków na pasku poleceń:</span><span class="sxs-lookup"><span data-stu-id="28e47-117">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="28e47-118">**Stan zadania** — umożliwia zmianę stanu zaznaczonych zadań.</span><span class="sxs-lookup"><span data-stu-id="28e47-118">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="28e47-119">**Filtr** — domyślnie są wyświetlane tylko aktywne zadania.</span><span class="sxs-lookup"><span data-stu-id="28e47-119">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="28e47-120">Jednak dzięki zastosowaniu filtrów pracownicy mogą wyświetlać wszystkie zadania, nawet zadania, które zostały wykonane lub anulowane.</span><span class="sxs-lookup"><span data-stu-id="28e47-120">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="28e47-121">Na poniższej ilustracji przedstawiono kartę **Moje zadania** w aplikacji Commerce punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="28e47-121">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Karta Moje zadania w aplikacji punktu sprzedaży Commerce](media/POS-task-management.png)

<span data-ttu-id="28e47-123">Na ilustracji przedstawiono kartę **Listy zadań**.</span><span class="sxs-lookup"><span data-stu-id="28e47-123">The following illustration shows the **Task lists** tab.</span></span>

![Karta Listy zadań w aplikacji punktu sprzedaży Commerce](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="28e47-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="28e47-125">Additional resources</span></span>

[<span data-ttu-id="28e47-126">Omówienie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="28e47-126">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="28e47-127">Konfigurowanie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="28e47-127">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="28e47-128">Tworzenie list zadań i dodawanie zadań</span><span class="sxs-lookup"><span data-stu-id="28e47-128">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="28e47-129">Przypisywanie list zadań do sklepów lub pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="28e47-129">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)
