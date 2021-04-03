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
ms.openlocfilehash: 18ba781795058de6228c712c6a22e59038e96368
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478369"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="87faf-103">Zarządzanie zadaniami w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="87faf-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="87faf-104">W tym temacie opisano zarządzanie zadaniami w aplikacji punktu sprzedaży (POS) w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="87faf-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="87faf-105">Aplikacja punktu sprzedaży Dynamics 365 Commerce zawiera funkcje zarządzania zadaniami, które umożliwiają menedżerom i pracownikom sklepów zarządzanie zadaniami i aktualizowanie stanu zadań.</span><span class="sxs-lookup"><span data-stu-id="87faf-105">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="87faf-106">Pracownicy sklepów mogą uzyskać dostęp do zadań, zaznaczając kafelek **Zadania** na stronie głównej punktu sprzedaży lub wybierając powiadomienia o zadaniach.</span><span class="sxs-lookup"><span data-stu-id="87faf-106">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="87faf-107">Domyślnie pracownicy sklepów są przeniesieni na kartę **Moje zadania**, gdzie mogą przeglądać przypisane do nich zadania.</span><span class="sxs-lookup"><span data-stu-id="87faf-107">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="87faf-108">Mogą jednak łatwo przełączać się do kart **Zaległe zadania**, **Zadania otwarte** i **Listy zadań**.</span><span class="sxs-lookup"><span data-stu-id="87faf-108">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="87faf-109">Operacje zadania dla menedżerów sklepów</span><span class="sxs-lookup"><span data-stu-id="87faf-109">Task operations for store managers</span></span>

<span data-ttu-id="87faf-110">Menedżerowie sklepów mogą wykonywać następujące operacje dotyczące zadań w aplikacji punktu sprzedaży za pomocą przycisków na pasku poleceń:</span><span class="sxs-lookup"><span data-stu-id="87faf-110">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="87faf-111">**Przypisanie** — przydzielenie wybranych zadań do pracownika sklepu.</span><span class="sxs-lookup"><span data-stu-id="87faf-111">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="87faf-112">**Stan zadania** — umożliwia zmianę stanu zaznaczonych zadań.</span><span class="sxs-lookup"><span data-stu-id="87faf-112">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="87faf-113">**Filtr** — domyślnie są wyświetlane tylko aktywne zadania.</span><span class="sxs-lookup"><span data-stu-id="87faf-113">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="87faf-114">Jednak dzięki zastosowaniu filtrów menedżerowie mogą wyświetlać wszystkie zadania, nawet zadania, które zostały wykonane lub anulowane.</span><span class="sxs-lookup"><span data-stu-id="87faf-114">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="87faf-115">**Nowe zadanie** — umożliwia utworzenie zadania na istniejącej liście zadań lub utworzenie zadania jednokierunkowego.</span><span class="sxs-lookup"><span data-stu-id="87faf-115">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="87faf-116">Pracownicy sklepów mogą wykonywać następujące operacje dotyczące zadań w aplikacji punktu sprzedaży za pomocą przycisków na pasku poleceń:</span><span class="sxs-lookup"><span data-stu-id="87faf-116">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="87faf-117">**Stan zadania** — umożliwia zmianę stanu zaznaczonych zadań.</span><span class="sxs-lookup"><span data-stu-id="87faf-117">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="87faf-118">**Filtr** — domyślnie są wyświetlane tylko aktywne zadania.</span><span class="sxs-lookup"><span data-stu-id="87faf-118">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="87faf-119">Jednak dzięki zastosowaniu filtrów pracownicy mogą wyświetlać wszystkie zadania, nawet zadania, które zostały wykonane lub anulowane.</span><span class="sxs-lookup"><span data-stu-id="87faf-119">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="87faf-120">Na poniższej ilustracji przedstawiono kartę **Moje zadania** w aplikacji Commerce punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="87faf-120">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Karta Moje zadania w aplikacji punktu sprzedaży Commerce](media/POS-task-management.png)

<span data-ttu-id="87faf-122">Na ilustracji przedstawiono kartę **Listy zadań**.</span><span class="sxs-lookup"><span data-stu-id="87faf-122">The following illustration shows the **Task lists** tab.</span></span>

![Karta Listy zadań w aplikacji punktu sprzedaży Commerce](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="87faf-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="87faf-124">Additional resources</span></span>

[<span data-ttu-id="87faf-125">Omówienie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="87faf-125">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="87faf-126">Konfigurowanie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="87faf-126">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="87faf-127">Tworzenie list zadań i dodawanie zadań</span><span class="sxs-lookup"><span data-stu-id="87faf-127">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="87faf-128">Przypisywanie list zadań do sklepów lub pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="87faf-128">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
