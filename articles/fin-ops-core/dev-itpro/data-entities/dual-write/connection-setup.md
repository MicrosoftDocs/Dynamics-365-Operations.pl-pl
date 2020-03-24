---
title: Obsługiwane scenariusze dla konfiguracji podwójnego zapisu
description: W tym temacie opisano scenariusze obsługiwane w konfiguracji podwójnego zapisu.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 1319f1228b635e207754f7c2516cb2b5353a9edd
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112500"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="679d8-103">Obsługiwane scenariusze dla konfiguracji podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="679d8-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="679d8-104">Można skonfigurować połączenie podwójnego zapisywania między środowiskiem Finance and Operations a środowiskiem Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="679d8-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="679d8-105">Środowisko **Finance and Operations** stanowi podstawową platformę dla aplikacji **Finance and Operations** (np. Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail i Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="679d8-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="679d8-106">Środowisko **Common Data Service**stanowi podstawową platformę aplikacji opartych na **modelach w systemie Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing i Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="679d8-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

<span data-ttu-id="679d8-107">Mechanizm konfiguracji zmienia się w zależności od subskrypcji i środowiska.</span><span class="sxs-lookup"><span data-stu-id="679d8-107">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="679d8-108">W przypadku nowych wystąpień aplikacji Finance and Operations konfiguracja podwójnego zapisywania rozpoczyna się w Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="679d8-108">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="679d8-109">Jeśli masz licencję na Microsoft Power Platform, otrzymasz nowe środowisko Common Data Service, jeśli Twoja dzierżawa nie ma takiego nowego środowiska.</span><span class="sxs-lookup"><span data-stu-id="679d8-109">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="679d8-110">W przypadku istniejących aplikacji Finance and Operations wystąpień Konfiguracja dwukrotnego zapisu rozpoczyna się w środowisku Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="679d8-110">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="679d8-111">Obsługiwane są następujące scenariusze konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="679d8-111">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="679d8-112">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-112">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="679d8-113">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-113">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="679d8-114">Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na nowym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-114">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="679d8-115">Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-115">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="679d8-116">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym lub istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-116">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="679d8-117">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-117">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="679d8-118">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i nowym wystąpieniem aplikacji opartej na modelu w systemie Dynamics 365, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="679d8-118">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="679d8-119">Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="679d8-119">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="679d8-120">Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.</span><span class="sxs-lookup"><span data-stu-id="679d8-120">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="679d8-121">Zainicjowano obsługę administracyjną nowego, pustego wystąpienia aplikacji opartej na modelu, w której zainstalowano rozwiązanie podstawowe programu CRM.</span><span class="sxs-lookup"><span data-stu-id="679d8-121">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="679d8-122">Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.</span><span class="sxs-lookup"><span data-stu-id="679d8-122">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="679d8-123">W mapowaniach jednostek włączono obsługę synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="679d8-123">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="679d8-124">Oba środowiska są następnie gotowe do synchronizacji danych na żywo.</span><span class="sxs-lookup"><span data-stu-id="679d8-124">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="679d8-125">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-125">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="679d8-126">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i istniejącym wystąpieniem aplikacji opartej na modelu w systemie Dynamics 365, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="679d8-126">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="679d8-127">Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="679d8-127">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="679d8-128">Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.</span><span class="sxs-lookup"><span data-stu-id="679d8-128">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="679d8-129">Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.</span><span class="sxs-lookup"><span data-stu-id="679d8-129">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="679d8-130">W mapowaniach jednostek włączono obsługę synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="679d8-130">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="679d8-131">Oba środowiska są następnie gotowe do synchronizacji danych na żywo.</span><span class="sxs-lookup"><span data-stu-id="679d8-131">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="679d8-132">Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="679d8-132">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="679d8-133">Utwórz nową firmę w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="679d8-133">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="679d8-134">Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.</span><span class="sxs-lookup"><span data-stu-id="679d8-134">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="679d8-135">[Uruchom](bootstrap-company-data.md) dane Common Data Service przy użyciu trzech liter kodu firmy Międzynarodowej Organizacji Normalizacyjnej (ISO).</span><span class="sxs-lookup"><span data-stu-id="679d8-135">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="679d8-136">Ponieważ podwójny zapis jest w trybie synchronizacji na żywo, dane z Common Data Service automatycznie zaczynają się przepływać do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="679d8-136">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="679d8-137">Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na nowym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-137">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="679d8-138">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a nowym wystąpieniem aplikacji obsługującej model w systemie Dynamics 365, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji wystąpienia aplikacji opartej na nowym modelu](#new-new), która znajduje się we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="679d8-138">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="679d8-139">Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane demonstracyjne z aplikacją obsługującą model, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="679d8-139">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="679d8-140">Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="679d8-140">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="679d8-141">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="679d8-141">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="679d8-142">Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-142">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="679d8-143">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a istniejącym wystąpieniem aplikacji obsługującej model w systemie Dynamics 365, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji wystąpienia aplikacji opartej na istniejącym modelu](#new-existing), która znajduje się we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="679d8-143">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="679d8-144">Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane demonstracyjne z aplikacją obsługującą model, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="679d8-144">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="679d8-145">Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="679d8-145">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="679d8-146">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="679d8-146">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="679d8-147">Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="679d8-147">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="679d8-148">Utwórz nową firmę w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="679d8-148">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="679d8-149">Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.</span><span class="sxs-lookup"><span data-stu-id="679d8-149">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="679d8-150">[Uruchom](bootstrap-company-data.md) dane Common Data Service przy użyciu trzech liter kodu firmy ISO.</span><span class="sxs-lookup"><span data-stu-id="679d8-150">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="679d8-151">Ponieważ podwójny zapis jest w trybie synchronizacji na żywo, dane z Common Data Service automatycznie zaczynają się przepływać do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="679d8-151">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="679d8-152">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym lub istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="679d8-152">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="679d8-153">Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finance and Operations a nowym lub istniejącym wystąpieniem aplikacji opartej na modelu w systemie Dynamics 365 występuje w środowisku finansów i operacji.</span><span class="sxs-lookup"><span data-stu-id="679d8-153">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="679d8-154">Skonfiguruj połączenie z aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="679d8-154">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="679d8-155">Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, należy [załadować](bootstrap-company-data.md) dane Common Data Service przy użyciu trój-literowego kodu ISO firmy.</span><span class="sxs-lookup"><span data-stu-id="679d8-155">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="679d8-156">Ponieważ podwójny zapis jest w trybie synchronizacji na żywo, dane z Common Data Service automatycznie zaczynają się przepływać do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="679d8-156">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
