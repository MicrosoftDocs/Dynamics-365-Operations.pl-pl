---
title: Project Service Automation
description: "To rozwiązanie używa funkcji integracji danych do synchronizacji danych między wystąpieniami programu Microsoft Dynamics 365 for Finance and Operations ora rozwiązaniem Microsoft Dynamics 365 for Project Service Automation za pośrednictwem usługi Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a><span data-ttu-id="d04c1-103">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d04c1-103">Project Service Automation</span></span>

<span data-ttu-id="d04c1-104">Rozwiązanie integracji rozwiązania Project Service Automation oraz Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami systemu Microsoft Dynamics 365 for Finance and Operations oraz Microsoft Dynamics 365 for Project Service Automation poprzez wspólne usługi danych (CD).</span><span class="sxs-lookup"><span data-stu-id="d04c1-104">The Project Service Automation to Finance and Operations integration solution uses the Data Integration feature to synchronize data across instances of Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation via the Common Data Service (CDS).</span></span> <span data-ttu-id="d04c1-105">Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych na temat projektów, umów dotyczących projektów, wierszy umowy dotyczącej projektu, punktów kontrolnych wiersza umowy projektu, zadań w ramach projektu, kategorii transakcji wydatkowych, szacunków godzinowych i szacowań wydatków z rozwiązania Project Service Automation do rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d04c1-105">The integration templates that are available with the Data Integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance and Operations.</span></span>

> [!NOTE] 
> <span data-ttu-id="d04c1-106">Jeśli używasz programu Dynamics 365 for Finance and Operations Enterprise Edition 7.3.0, należy zainstalować poprawkę KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="d04c1-106">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="d04c1-107">Dzięki temu będzie można zintegrować projekty o stałej cenie.</span><span class="sxs-lookup"><span data-stu-id="d04c1-107">This will allow you to integrate fixed price projects.</span></span>
>
> <span data-ttu-id="d04c1-108">Jeśli używasz programu Dynamics 365 for Finance and Operations w wersji 8.0, masz dostęp do mechanizmów integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji.</span><span class="sxs-lookup"><span data-stu-id="d04c1-108">If you are using Dynamics 365 for Finance and Operations version 8.0, you will be able to use project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
>
> <span data-ttu-id="d04c1-109">Jeśli używasz programu Dynamics 365 for Finance and Operations w wersji 8.0.1, masz możliwość synchronizowania wartości rzeczywistych.</span><span class="sxs-lookup"><span data-stu-id="d04c1-109">If you are using Dynamics 365 for Finance and Operations version 8.0.1, you will be able to synchronize actuals.</span></span>
>
> <span data-ttu-id="d04c1-110">Jeśli używasz programu Dynamics 365 for Finance and Operations Enterprise Edition 7.3.0, po zainstalowaniu aktualizacji KB 4132657 i 4132660 możesz używać szablonów, aby integrować zadania projektu, kategorie transakcji wydatkowych, szacunki godzin, szacunki wydatków i wartości rzeczywiste oraz konfigurować blokowanie funkcji.</span><span class="sxs-lookup"><span data-stu-id="d04c1-110">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="d04c1-111">Jeśli należy zresetować zasady podziału księgowań, zalecamy dodatkowo zainstalować aktualizację KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="d04c1-111">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

<span data-ttu-id="d04c1-112">Zanim będzie można zintegrować program Project Service Automation z programem Finance and Operations, należy skonfigurować parametry integracji programu Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="d04c1-112">Before you can integrate Project Service Automation with Finance and Operations, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="d04c1-113">Aby uzyskać więcej informacji, zobacz Parametry integracji aplikacji Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="d04c1-113">For more information, see Project Service Automation integration parameters.</span></span>

<span data-ttu-id="d04c1-114">To rozwiązanie integracji umożliwia bezpośrednią synchronizację w następujących scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="d04c1-114">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="d04c1-115">Zarządzanie umowami na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d04c1-115">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d04c1-116">Tworzenie projektów w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d04c1-116">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d04c1-117">Zarządzanie wierszami umowy na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d04c1-117">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d04c1-118">Zarządzanie punktami kontrolnymi wierszy umowy na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d04c1-118">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d04c1-119">Zarządzanie zadaniami w projekcie w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d04c1-119">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d04c1-120">Zarządzanie kategoriami transakcji wydatkowych w programie Finance and Operations oraz synchronizowanie ich bezpośrednio z tego programu do modułu Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="d04c1-120">Maintain expense transaction categories in Finance and Operations, and synchronize them directly from Finance and Operations to Project Service Automation.</span></span>
- <span data-ttu-id="d04c1-121">Tworzenie szacunków godzin w projektach w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d04c1-121">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d04c1-122">Tworzenie szacunków wydatków w projektach w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d04c1-122">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="d04c1-123">Synchronizacja danych</span><span class="sxs-lookup"><span data-stu-id="d04c1-123">Data synchronization</span></span>
<span data-ttu-id="d04c1-124">Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane w ramach integracji pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d04c1-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="d04c1-125">Nie wszystkie szablony są obecnie dostępne.</span><span class="sxs-lookup"><span data-stu-id="d04c1-125">Not all templates are currently available.</span></span> <span data-ttu-id="d04c1-126">Szablony będą publikowane w miarę ich finalizowania.</span><span class="sxs-lookup"><span data-stu-id="d04c1-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="d04c1-127">[![Integracja programu Project Service Automation z programem Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="d04c1-127">[![Project Service Automation integration with Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="d04c1-128">Wymagania systemowe dla rozwiązania Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d04c1-128">System requirements for Finance and Operations</span></span>

<span data-ttu-id="d04c1-129">Aby użyć aplikacji Project Service Automation dla rozwiązań integracji finansów i operacji, należy zainstalować Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 z aktualizacją platformy 12 lub nowszą.</span><span class="sxs-lookup"><span data-stu-id="d04c1-129">To use the Project Service Automation to Finance and Operations integration solution, you must install Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 with platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="d04c1-130">Wymagania systemowe aplikacji Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d04c1-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="d04c1-131">Aby użyć aplikacji Project Service Automation dla rozwiązań integracji dla Finance and Operations, należy zainstalować następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="d04c1-131">To use the Project Service Automation to Finance and Operations integration solution, you must install the following components:</span></span>

- <span data-ttu-id="d04c1-132">Microsoft Dynamics 365 for Project Service Automation, wersja 9.0.0.0 lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="d04c1-132">Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 or later.</span></span>
- <span data-ttu-id="d04c1-133">Rozwiązanie Prospekt na gotówkę dla programu Dynamics 365 for Sales, wersja 1.14.0.0 (v14) lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="d04c1-133">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>
- <span data-ttu-id="d04c1-134">Rozwiązanie Project Service Automation na Operations dla programu Dynamics 365 for Project Service Automation w wersji 1.0.0.0 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="d04c1-134">Project Service Automation to Operations solution for Dynamics 365 for Project Service Automation version 1.0.0.0 or later.</span></span>

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="d04c1-135">Instalowanie rozwiązania do integrowania aplikacji Project Service Automation z Finance and Operations w wystąpieniu programu Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d04c1-135">Install the Project Service Automation to Finance and Operations integration solution in your Project Service Automation instance</span></span>



