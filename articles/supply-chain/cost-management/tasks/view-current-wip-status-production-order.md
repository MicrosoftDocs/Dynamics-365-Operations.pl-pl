---
title: Wyświetlanie aktualnego stanu PWT na zleceniu produkcyjnym
description: W tej procedurze pokazano sposób tworzenia zestawienia PWT w zleceniu produkcyjnym.
author: AndersGirke
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, CostAdminWorkspace, CostLastInventoryCloseCard, CostLastBackflushCostingCard, CostStatementCacheCard, CostReleasedProductsMissingCostingDataFormPart, CostCalculationPeriodTopVariancesChartFormPart, ProdTable, CostStatement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f76a7589de13237ba822296d357df3e0300f11ad
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5002030"
---
# <a name="view-current-wip-status-on-a-production-order"></a><span data-ttu-id="bed89-103">Wyświetlanie aktualnego stanu PWT na zleceniu produkcyjnym</span><span class="sxs-lookup"><span data-stu-id="bed89-103">View current WIP status on a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bed89-104">W tej procedurze pokazano sposób tworzenia zestawienia PWT w zleceniu produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="bed89-104">This procedure shows how to view WIP statement on a production order.</span></span> <span data-ttu-id="bed89-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="bed89-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bed89-106">Ta procedura jest przeznaczona dla kontrolera kosztów.</span><span class="sxs-lookup"><span data-stu-id="bed89-106">This procedure is intended for the cost controller.</span></span>

1. <span data-ttu-id="bed89-107">Kliknij przycisk Administrowanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="bed89-107">Click Cost administration.</span></span>
2. <span data-ttu-id="bed89-108">Kliknij opcję Zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="bed89-108">Click Production orders.</span></span>
3. <span data-ttu-id="bed89-109">Użyj szybkiego filtru, aby wyfiltrować pole Produkcja według wartości „p000153”.</span><span class="sxs-lookup"><span data-stu-id="bed89-109">Use the Quick Filter to filter on the Production field with a value of 'p000153'.</span></span>
4. <span data-ttu-id="bed89-110">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="bed89-110">On the Action Pane, click Manage costs.</span></span>
5. <span data-ttu-id="bed89-111">Kliknij opcję Zestawienie PWT produkcji.</span><span class="sxs-lookup"><span data-stu-id="bed89-111">Click Production WIP statement.</span></span>
6. <span data-ttu-id="bed89-112">W polu Od dnia ustaw wartość daty równą „2012-12-01”.</span><span class="sxs-lookup"><span data-stu-id="bed89-112">In the From date field, set the date to '2012-12-01'.</span></span>
7. <span data-ttu-id="bed89-113">W polu Do dnia ustaw wartość daty równą „2012-12-31”.</span><span class="sxs-lookup"><span data-stu-id="bed89-113">In the To date field, set the date to '2012-12-31'.</span></span>

