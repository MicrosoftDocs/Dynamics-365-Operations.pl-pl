---
title: Obsługiwane scenariusze dla konfiguracji podwójnego zapisu
description: W tym temacie opisano scenariusze obsługiwane w konfiguracji podwójnego zapisu.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
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
ms.openlocfilehash: b4f69e7933bc5a50cccad6911c99cf08d2768578
ms.sourcegitcommit: b3df62842e62234e8eaa16992375582518976131
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "3818603"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="47b29-103">Obsługiwane scenariusze dla konfiguracji podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="47b29-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="47b29-104">Można skonfigurować połączenie podwójnego zapisywania między środowiskiem Finance and Operations a środowiskiem Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="47b29-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="47b29-105">Środowisko **Finance and Operations** stanowi podstawową platformę dla aplikacji **Finance and Operations** (na przykład Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management oraz Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="47b29-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="47b29-106">Środowisko **Common Data Service**stanowi podstawową platformę aplikacji opartych na **modelach w systemie Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing i Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="47b29-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="47b29-107">Human Resources w Finance and Operations obsługuje połączenia dwukrotnego zapisu, ale aplikacja Dynamics 365 Human Resources nie.</span><span class="sxs-lookup"><span data-stu-id="47b29-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="47b29-108">Mechanizm konfiguracji zmienia się w zależności od subskrypcji i środowiska.</span><span class="sxs-lookup"><span data-stu-id="47b29-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="47b29-109">W przypadku nowych wystąpień aplikacji Finance and Operations konfiguracja podwójnego zapisywania rozpoczyna się w Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="47b29-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="47b29-110">Jeśli masz licencję na Power Platform, otrzymasz nowe środowisko Common Data Service, jeśli Twoja dzierżawa nie ma takiego nowego środowiska.</span><span class="sxs-lookup"><span data-stu-id="47b29-110">If you have a license for Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="47b29-111">W przypadku istniejących aplikacji Finance and Operations wystąpień Konfiguracja dwukrotnego zapisu rozpoczyna się w środowisku Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="47b29-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="47b29-112">Obsługiwane są następujące scenariusze konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="47b29-112">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="47b29-113">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-113">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="47b29-114">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-114">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="47b29-115">Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na nowym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-115">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="47b29-116">Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-116">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="47b29-117">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym lub istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-117">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="47b29-118">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-118">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="47b29-119">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i nowym wystąpieniem aplikacji opartej na modelu w systemie Dynamics 365, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="47b29-119">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="47b29-120">Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="47b29-120">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="47b29-121">Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.</span><span class="sxs-lookup"><span data-stu-id="47b29-121">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="47b29-122">Zainicjowano obsługę administracyjną nowego, pustego wystąpienia aplikacji opartej na modelu, w której zainstalowano rozwiązanie podstawowe programu CRM.</span><span class="sxs-lookup"><span data-stu-id="47b29-122">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="47b29-123">Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.</span><span class="sxs-lookup"><span data-stu-id="47b29-123">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="47b29-124">W mapowaniach jednostek włączono obsługę synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="47b29-124">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="47b29-125">Oba środowiska są następnie gotowe do synchronizacji danych na żywo.</span><span class="sxs-lookup"><span data-stu-id="47b29-125">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="47b29-126">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-126">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="47b29-127">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i istniejącym wystąpieniem aplikacji opartej na modelu w systemie Dynamics 365, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="47b29-127">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="47b29-128">Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="47b29-128">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="47b29-129">Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.</span><span class="sxs-lookup"><span data-stu-id="47b29-129">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="47b29-130">Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.</span><span class="sxs-lookup"><span data-stu-id="47b29-130">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="47b29-131">W mapowaniach jednostek włączono obsługę synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="47b29-131">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="47b29-132">Oba środowiska są następnie gotowe do synchronizacji danych na żywo.</span><span class="sxs-lookup"><span data-stu-id="47b29-132">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="47b29-133">Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="47b29-133">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="47b29-134">Utwórz nową firmę w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="47b29-134">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="47b29-135">Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.</span><span class="sxs-lookup"><span data-stu-id="47b29-135">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="47b29-136">[Uruchom](bootstrap-company-data.md) dane Common Data Service przy użyciu trzech liter kodu firmy Międzynarodowej Organizacji Normalizacyjnej (ISO).</span><span class="sxs-lookup"><span data-stu-id="47b29-136">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="47b29-137">Ponieważ podwójny zapis jest w trybie synchronizacji na żywo, dane z Common Data Service automatycznie zaczynają się przepływać do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="47b29-137">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="47b29-138">Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na nowym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-138">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="47b29-139">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a nowym wystąpieniem aplikacji obsługującej model w systemie Dynamics 365, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji wystąpienia aplikacji opartej na nowym modelu](#new-new), która znajduje się we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="47b29-139">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="47b29-140">Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane demonstracyjne z aplikacją obsługującą model, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="47b29-140">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="47b29-141">Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="47b29-141">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="47b29-142">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="47b29-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="47b29-143">Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-143">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="47b29-144">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a istniejącym wystąpieniem aplikacji obsługującej model w systemie Dynamics 365, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji wystąpienia aplikacji opartej na istniejącym modelu](#new-existing), która znajduje się we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="47b29-144">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="47b29-145">Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane demonstracyjne z aplikacją obsługującą model, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="47b29-145">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="47b29-146">Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="47b29-146">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="47b29-147">Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="47b29-147">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="47b29-148">Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="47b29-148">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="47b29-149">Utwórz nową firmę w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="47b29-149">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="47b29-150">Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.</span><span class="sxs-lookup"><span data-stu-id="47b29-150">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="47b29-151">[Uruchom](bootstrap-company-data.md) dane Common Data Service przy użyciu trzech liter kodu firmy ISO.</span><span class="sxs-lookup"><span data-stu-id="47b29-151">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="47b29-152">Ponieważ podwójny zapis jest w trybie synchronizacji na żywo, dane z Common Data Service automatycznie zaczynają się przepływać do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="47b29-152">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="47b29-153">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym lub istniejącym modelu</span><span class="sxs-lookup"><span data-stu-id="47b29-153">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="47b29-154">Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finance and Operations a nowym lub istniejącym wystąpieniem aplikacji opartej na modelu w systemie Dynamics 365 występuje w środowisku finansów i operacji.</span><span class="sxs-lookup"><span data-stu-id="47b29-154">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="47b29-155">Skonfiguruj połączenie z aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="47b29-155">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="47b29-156">Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, należy [załadować](bootstrap-company-data.md) dane Common Data Service przy użyciu trój-literowego kodu ISO firmy.</span><span class="sxs-lookup"><span data-stu-id="47b29-156">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="47b29-157">Ponieważ podwójny zapis jest w trybie synchronizacji na żywo, dane z Common Data Service automatycznie zaczynają się przepływać do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="47b29-157">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
