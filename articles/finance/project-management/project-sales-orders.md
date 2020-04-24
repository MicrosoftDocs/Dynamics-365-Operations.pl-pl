---
title: Zamówienia sprzedaży dla projektu dla projektów typu czas i materiały
description: W tym temacie opisano, jak tworzyć zamówienia sprzedaży na podstawie projektu dla projektów typu Czas i materiały.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: d19ee9de70cd14c78a997b7a87c10b53ab3917b0
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249100"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a><span data-ttu-id="48122-103">Zamówienia sprzedaży dla projektu dla projektów typu czas i materiały</span><span class="sxs-lookup"><span data-stu-id="48122-103">Project sales orders for time and material projects</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="48122-104">W tym temacie opisano sposób tworzenia zamówień sprzedaży dla projektu.</span><span class="sxs-lookup"><span data-stu-id="48122-104">This topic describes how to create a sales order for a project.</span></span> <span data-ttu-id="48122-105">Zamówienia sprzedaży można tworzyć tylko dla projektów typu **Czas i materiały**.</span><span class="sxs-lookup"><span data-stu-id="48122-105">Sales orders can only be created for projects of type **time and material**.</span></span>

<span data-ttu-id="48122-106">Jeśli projekt typu czas i materiały ma wiele źródeł finansowania w umowie dot. projektu, należy włączyć parametr **Zezwalaj na zamówienia sprzedaży w projektach z wieloma źródłami finansowania** na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="48122-106">If a time and material project has multiple funding sources on the project contract, you must enable the **Allow sales orders for projects with multiple funding sources** parameter on the **Project management and accounting parameters** page.</span></span> 

> [!NOTE]
> - <span data-ttu-id="48122-107">Obsługa zamówień sprzedaży dla projektu z wieloma źródłami finansowania jest dostępna w wersji 10.0.2 aplikacji i nowszych.</span><span class="sxs-lookup"><span data-stu-id="48122-107">Support for project sales orders with multiple funding sources is available starting with application release 10.0.2 and higher.</span></span>
> - <span data-ttu-id="48122-108">Parametr umożliwiający obsługę zamówień sprzedaży dla projektu z wieloma źródłami finansowania zostanie usunięty w wersji planowanej na kwiecień 2020 r., a po tym czasie funkcja będzie zawsze włączona.</span><span class="sxs-lookup"><span data-stu-id="48122-108">The parameter to enable the support for project sales orders with multiple funding sources will be removed in the April 2020 release wave, after which the functionality will always be enabled.</span></span>

<span data-ttu-id="48122-109">Zamówienia sprzedaży na podstawie projektu można utworzyć na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="48122-109">You can create project-based sales orders in two ways:</span></span>

- <span data-ttu-id="48122-110">Z samego projektu.</span><span class="sxs-lookup"><span data-stu-id="48122-110">Go to the project itself.</span></span> <span data-ttu-id="48122-111">W okienku akcji wybierz **Zarządzaj > Zadania dotyczące pozycji > Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="48122-111">On the Action Pane, select **Manage > Item tasks > Sales order**.</span></span> <span data-ttu-id="48122-112">Informacje o projekcie zostaną domyślnie przypisane do zamówienia sprzedaży z projektu.</span><span class="sxs-lookup"><span data-stu-id="48122-112">The project information will default to the sales order from the project.</span></span> <span data-ttu-id="48122-113">Jeśli umowa dotycząca projektu ma więcej niż jedno źródło finansowania, należy wybrać źródło finansowania w celu ustawiania odbiorcy dla zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="48122-113">If the project contract has more than one funding source, you will need to select the funding source to set the customer for the sales order.</span></span> <span data-ttu-id="48122-114">Jeśli występuje tylko jedno źródło finansowania projektu, odbiorca zostanie automatycznie ustawiony.</span><span class="sxs-lookup"><span data-stu-id="48122-114">If there is only one funding source for the project, the customer will be automatically set.</span></span>
- <span data-ttu-id="48122-115">Przejdź do strony listy **Wszystkie zamówienia sprzedaży** i utwórz nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="48122-115">Go to the **All sales order** list page and create a new sales order.</span></span> <span data-ttu-id="48122-116">Należy wybrać projekt dla zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="48122-116">You will need to select the project for the sales order.</span></span> <span data-ttu-id="48122-117">Po wybraniu projektu, odbiorca zostanie ustawiony na podstawie źródła finansowania lub trzeba będzie wybrać źródło finansowania, jeśli umowa dotycząca projektu ma wiele źródeł finansowania.</span><span class="sxs-lookup"><span data-stu-id="48122-117">After the project is selected, the customer will be set from the funding source or you will need to select the funding source if the project contract has multiple funding sources.</span></span>

