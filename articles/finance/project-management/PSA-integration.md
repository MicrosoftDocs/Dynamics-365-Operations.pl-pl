---
title: Omówienie rozwiązania Project Service Automation
description: Ten temat zawiera informacje dotyczące funkcji integracji rozwiązania Dynamics 365 Project Service Automation do Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
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
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250560"
---
# <a name="project-service-automation-overview"></a><span data-ttu-id="bfa15-103">Omówienie rozwiązania Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="bfa15-103">Project Service Automation overview</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="bfa15-104">Rozwiązanie integracji rozwiązania Project Service Automation oraz Finance korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami programu Dynamics 365 Finance oraz Dynamics 365 Project Service Automation poprzez usługę Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bfa15-104">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Dynamics 365 Finance and Dynamics 365 Project Service Automation via Common Data Service.</span></span> <span data-ttu-id="bfa15-105">Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych na temat projektów, umów dotyczących projektów, wierszy umowy dotyczącej projektu, punktów kontrolnych wiersza umowy projektu, zadań w ramach projektu, kategorii transakcji wydatkowych, szacunków godzinowych i szacowań wydatków z rozwiązania Project Service Automation do rozwiązania Finance.</span><span class="sxs-lookup"><span data-stu-id="bfa15-105">The integration templates that are available with the Data integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="bfa15-106">Jeśli używasz wersji 7.3.0, należy zainstalować poprawkę KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="bfa15-106">If you're using version 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="bfa15-107">Wtedy będzie można integrować projekty o stałej cenie.</span><span class="sxs-lookup"><span data-stu-id="bfa15-107">You will then be able to integrate fixed price projects.</span></span>
> - <span data-ttu-id="bfa15-108">Jeśli używasz wersji 7.3.0 i przenosisz transakcje opłat z programu Project Service Automation, należy zainstalować aktualizację KB 4345320, aby te opłaty były uwzględniane w fakturze projektu.</span><span class="sxs-lookup"><span data-stu-id="bfa15-108">If you're using version 7.3.0, and you are bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.</span></span>
> - <span data-ttu-id="bfa15-109">Jeśli używasz wersji 8.0, masz dostęp do mechanizmów integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji.</span><span class="sxs-lookup"><span data-stu-id="bfa15-109">If you're using version 8.0, you will be able to use project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
> - <span data-ttu-id="bfa15-110">Jeśli używasz wersji 8.0.1 lub nowszej, masz możliwość synchronizowania wartości rzeczywistych.</span><span class="sxs-lookup"><span data-stu-id="bfa15-110">If you're using version 8.0.1 or later, you will be able to synchronize actuals.</span></span>

<span data-ttu-id="bfa15-111">Zanim będzie można zintegrować program Project Service Automation z programem Finance, należy skonfigurować parametry integracji programu Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="bfa15-111">Before you can integrate Project Service Automation Finance, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="bfa15-112">Aby uzyskać więcej informacji, zobacz [Parametry integracji aplikacji Project Service Automation](PSA-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="bfa15-112">For more information, see [Project Service Automation integration parameters](PSA-parameters.md).</span></span>

<span data-ttu-id="bfa15-113">To rozwiązanie integracji umożliwia bezpośrednią synchronizację w następujących scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="bfa15-113">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="bfa15-114">Zarządzanie umowami na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance</span><span class="sxs-lookup"><span data-stu-id="bfa15-114">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="bfa15-115">Tworzenie projektów w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.</span><span class="sxs-lookup"><span data-stu-id="bfa15-115">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="bfa15-116">Zarządzanie wierszami umów na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.</span><span class="sxs-lookup"><span data-stu-id="bfa15-116">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="bfa15-117">Zarządzanie kroków miliowych wierszy umów na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.</span><span class="sxs-lookup"><span data-stu-id="bfa15-117">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="bfa15-118">Zarządzanie zadaniami na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.</span><span class="sxs-lookup"><span data-stu-id="bfa15-118">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="bfa15-119">Zarządzanie kategoriami transakcji wydatkowych w programie Finance oraz synchronizowanie ich bezpośrednio z tego programu do modułu Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="bfa15-119">Maintain expense transaction categories in Finance, and synchronize them directly from Finance to Project Service Automation.</span></span>
- <span data-ttu-id="bfa15-120">Tworzenie szacunków godzin w projektach w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.</span><span class="sxs-lookup"><span data-stu-id="bfa15-120">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="bfa15-121">Tworzenie wydatków w projektach w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.</span><span class="sxs-lookup"><span data-stu-id="bfa15-121">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="bfa15-122">Tworzenie wartości rzeczywistych czasu, wydatków i opłat w projekcie w aplikacji Project Service Automation oraz tworzenie transakcji projektu w arkuszu integracji programu Project Service Automation, tak aby można je było księgować w programie Finance.</span><span class="sxs-lookup"><span data-stu-id="bfa15-122">Create project time, expense, and fee actuals in Project Service Automation, and create project transactions in the Project Service Automation integration journal so that they can be posted in Finance.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="bfa15-123">Synchronizacja danych</span><span class="sxs-lookup"><span data-stu-id="bfa15-123">Data synchronization</span></span>

<span data-ttu-id="bfa15-124">Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane w ramach integracji pomiędzy rozwiązaniami Project Service Automation oraz Finance.</span><span class="sxs-lookup"><span data-stu-id="bfa15-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance.</span></span>

> [!NOTE]
> <span data-ttu-id="bfa15-125">Nie wszystkie szablony są obecnie dostępne.</span><span class="sxs-lookup"><span data-stu-id="bfa15-125">Not all templates are currently available.</span></span> <span data-ttu-id="bfa15-126">Szablony będą publikowane w miarę ich finalizowania.</span><span class="sxs-lookup"><span data-stu-id="bfa15-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="bfa15-127">[![Parametry integracji Project Service Automation z Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="bfa15-127">[![Project Service Automation integration with Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance"></a><span data-ttu-id="bfa15-128">Wymagania systemowe dla rozwiązania Finance</span><span class="sxs-lookup"><span data-stu-id="bfa15-128">System requirements for Finance</span></span>

<span data-ttu-id="bfa15-129">Aby użyć aplikacji Project Service Automation dla rozwiązań integracji Finance, należy zainstalować Enterprise edition 7.3 z aktualizacją platformy 12 lub nowszą.</span><span class="sxs-lookup"><span data-stu-id="bfa15-129">To use the Project Service Automation to Finance integration solution, you must install Enterprise edition 7.3 with Platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="bfa15-130">Wymagania systemowe aplikacji Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="bfa15-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="bfa15-131">Aby użyć aplikacji Project Service Automation dla rozwiązań integracji dla Finance, należy zainstalować następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="bfa15-131">To use the Project Service Automation to Finance integration solution, you must install the following components:</span></span>

- <span data-ttu-id="bfa15-132">Dynamics 365 Project Service Automation, wersja 9.0.0.0 lub nowsza</span><span class="sxs-lookup"><span data-stu-id="bfa15-132">Dynamics 365 Project Service Automation version 9.0.0.0 or later</span></span>
- <span data-ttu-id="bfa15-133">Rozwiązanie Prospekt na gotówkę dla programu Dynamics 365 Sales, wersja 1.14.0.0 (v14) lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="bfa15-133">Prospect to cash solution for Dynamics 365 Sales, version 1.14.0.0 (v14) or later</span></span>
- <span data-ttu-id="bfa15-134">Rozwiązanie do integrowania aplikacji Project Service Automation z Finance dla programu Dynamics 365 Project Service Automation w wersji 1.0.0.0 lub nowszej</span><span class="sxs-lookup"><span data-stu-id="bfa15-134">Project Service Automation to Finance solution for Dynamics 365 Project Service Automation version 1.0.0.0 or later</span></span>

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="bfa15-135">Instalowanie rozwiązania do integrowania aplikacji Project Service Automation z Finance w wystąpieniu programu Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="bfa15-135">Install the Project Service Automation to Finance integration solution in your Project Service Automation instance</span></span>

<span data-ttu-id="bfa15-136">Pobierz rozwiązanie do integrowania aplikacji Project Service Automation z Finance z [Centrum pobierania Microsoft](https://www.microsoft.com/download/details.aspx?id=57016) i postępuj zgodnie z instrukcjami dołączonymi do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="bfa15-136">Download the Project Service Automation to Finance integration solution from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016), and follow the instructions that are included with the solution.</span></span>
