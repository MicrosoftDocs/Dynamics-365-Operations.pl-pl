---
title: Wskazówki dotyczące konfiguracji podwójnego zapisu
description: W tym temacie opisano scenariusze obsługiwane w konfiguracji podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 999b37970be1c10fd5e78c3d8ac6c1fb25cad367
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751393"
---
# <a name="guidance-for-dual-write-setup"></a><span data-ttu-id="a8470-103">Wskazówki dotyczące konfiguracji podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="a8470-103">Guidance for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a8470-104">Można skonfigurować połączenie podwójnego zapisywania między środowiskiem Finance and Operations a środowiskiem Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a8470-104">You can set up a dual-write connection between a Finance and Operations environment and a Dataverse environment.</span></span>

+ <span data-ttu-id="a8470-105">Środowisko **Finance and Operations** stanowi podstawową platformę dla aplikacji **Finance and Operations** (np. Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce i Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="a8470-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="a8470-106">**Środowisko Dataverse** stanowi podstawową platformę **aplikacji typu Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Column Service, Dynamics 365 Marketing i Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="a8470-106">A **Dataverse environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8470-107">Moduł Human Resources w Dynamics 365 Finance obsługuje połączenia dwukrotnego zapisu, ale aplikacja Dynamics 365 Human Resources nie.</span><span class="sxs-lookup"><span data-stu-id="a8470-107">The Human Resources module in Dynamics 365 Finance supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="a8470-108">Mechanizm konfiguracji zmienia się w zależności od subskrypcji i środowiska:</span><span class="sxs-lookup"><span data-stu-id="a8470-108">The setup mechanism varies, depending on your subscription and the environment:</span></span>

+ <span data-ttu-id="a8470-109">W przypadku nowych wystąpień aplikacji Finance and Operations konfiguracja podwójnego zapisywania rozpoczyna się w Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="a8470-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="a8470-110">Jeśli masz licencję na Microsoft Power Platform, otrzymasz nowe środowisko Dataverse, jeśli Twoja dzierżawa nie ma takiego nowego środowiska.</span><span class="sxs-lookup"><span data-stu-id="a8470-110">If you have a license for Microsoft Power Platform, you will get a new Dataverse environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="a8470-111">W przypadku istniejących aplikacji Finance and Operations wystąpień Konfiguracja dwukrotnego zapisu rozpoczyna się w środowisku Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a8470-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="a8470-112">Przed rozpoczęciem podwójnego zapisywania w jednostce można uruchomić synchronizację początkową umożliwiającą obsługę istniejących danych po obu stronach: aplikacji Finance and Operations i aplikacji do zakontraktowania klientów.</span><span class="sxs-lookup"><span data-stu-id="a8470-112">Before you start dual-write on an entity, you can run an initial synchronization to handle existing data on both sides: Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="a8470-113">Synchronizację początkową można pominąć, jeśli nie ma potrzeby synchronizowania danych między tymi środowiskami.</span><span class="sxs-lookup"><span data-stu-id="a8470-113">You can skip the initial synchronization if you don't have to sync data between the two environments.</span></span>

<span data-ttu-id="a8470-114">Synchronizacja początkowa umożliwia skopiowanie istniejących danych z jednej aplikacji na inną dwukierunkową.</span><span class="sxs-lookup"><span data-stu-id="a8470-114">An initial synchronization lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="a8470-115">Istnieje kilka różnych scenariuszy konfiguracji, w zależności od tego, które środowiska są już dostępne, oraz jakiego typu dane znajdują się w nich.</span><span class="sxs-lookup"><span data-stu-id="a8470-115">There are several setup scenarios, depending on the environments that you already have and the type of data in them.</span></span>

<span data-ttu-id="a8470-116">Obsługiwane są następujące scenariusze konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="a8470-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="a8470-117">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="a8470-118">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="a8470-119">Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="a8470-120">Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="a8470-121">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie nowej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="a8470-122">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="a8470-123">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="a8470-124">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i nowym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="a8470-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="a8470-125">Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="a8470-125">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="a8470-126">Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.</span><span class="sxs-lookup"><span data-stu-id="a8470-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="a8470-127">Zainicjowano obsługę administracyjną nowego, pustego wystąpienia aplikacji do zakontraktowania odbiorcy, w której zainstalowano rozwiązanie podstawowe programu CRM.</span><span class="sxs-lookup"><span data-stu-id="a8470-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="a8470-128">Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.</span><span class="sxs-lookup"><span data-stu-id="a8470-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="a8470-129">W mapowaniach tabeli włączono obsługę synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="a8470-129">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="a8470-130">Oba środowiska są następnie gotowe do synchronizacji danych na żywo.</span><span class="sxs-lookup"><span data-stu-id="a8470-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="a8470-131">Nowe wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="a8470-132">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i istniejącym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="a8470-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="a8470-133">Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="a8470-133">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="a8470-134">Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.</span><span class="sxs-lookup"><span data-stu-id="a8470-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="a8470-135">Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.</span><span class="sxs-lookup"><span data-stu-id="a8470-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="a8470-136">W mapowaniach tabeli włączono obsługę synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="a8470-136">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="a8470-137">Oba środowiska są następnie gotowe do synchronizacji danych na żywo.</span><span class="sxs-lookup"><span data-stu-id="a8470-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="a8470-138">Aby zsynchronizować istniejące dane Dataverse z aplikacją Finance and Operations, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a8470-138">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="a8470-139">Utwórz nową firmę w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a8470-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="a8470-140">Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.</span><span class="sxs-lookup"><span data-stu-id="a8470-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="a8470-141">[Uruchom](bootstrap-company-data.md) dane Dataverse przy użyciu trzech liter kodu firmy Międzynarodowej Organizacji Normalizacyjnej (ISO).</span><span class="sxs-lookup"><span data-stu-id="a8470-141">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="a8470-142">Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a8470-142">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="a8470-143">Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example) w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="a8470-143">For links to an example and an alternative approach, see the [Example](#example) section later in this topic.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="a8470-144">Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="a8470-145">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a nowym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji wystąpienia aplikacji do zakontraktowania odbiorcy](#new-new), która znajduje się we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="a8470-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="a8470-146">Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane z aplikacją do zakontraktowania odbiorcy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a8470-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="a8470-147">Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="a8470-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="a8470-148">Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a8470-148">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="a8470-149">Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).</span><span class="sxs-lookup"><span data-stu-id="a8470-149">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="a8470-150">Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="a8470-151">Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a istniejącym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji istniejącego wystąpienia aplikacji do zakontraktowania odbiorcy](#new-existing), która znajduje się we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="a8470-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="a8470-152">Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane z aplikacją do zakontraktowania odbiorcy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a8470-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="a8470-153">Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="a8470-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="a8470-154">Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a8470-154">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="a8470-155">Aby zsynchronizować istniejące dane Dataverse z aplikacją Finance and Operations, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a8470-155">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="a8470-156">Utwórz nową firmę w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a8470-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="a8470-157">Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.</span><span class="sxs-lookup"><span data-stu-id="a8470-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="a8470-158">[Uruchom](bootstrap-company-data.md) dane Dataverse przy użyciu trzech liter kodu firmy ISO.</span><span class="sxs-lookup"><span data-stu-id="a8470-158">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="a8470-159">Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a8470-159">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="a8470-160">Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).</span><span class="sxs-lookup"><span data-stu-id="a8470-160">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="a8470-161">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie nowej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="a8470-162">Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finance and Operations a nowym wystąpieniem aplikacji do zakontraktowania odbiorcy występuje w środowisku Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="a8470-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="a8470-163">[Skonfiguruj połączenie z aplikacji Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="a8470-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="a8470-164">Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a8470-164">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="a8470-165">Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).</span><span class="sxs-lookup"><span data-stu-id="a8470-165">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="a8470-166">Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a8470-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="a8470-167">Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finance and Operations a istniejącym wystąpieniem aplikacji do zakontraktowania odbiorcy występuje w środowisku Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="a8470-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="a8470-168">[Skonfiguruj połączenie z aplikacji Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="a8470-168">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="a8470-169">Aby zsynchronizować istniejące dane Dataverse z aplikacją Finance and Operations, należy [załadować](bootstrap-company-data.md) dane Dataverse przy użyciu trój-literowego kodu ISO firmy.</span><span class="sxs-lookup"><span data-stu-id="a8470-169">To sync the existing Dataverse data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="a8470-170">Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.</span><span class="sxs-lookup"><span data-stu-id="a8470-170">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="a8470-171">Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).</span><span class="sxs-lookup"><span data-stu-id="a8470-171">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="example"></a><span data-ttu-id="a8470-172">Przykład</span><span class="sxs-lookup"><span data-stu-id="a8470-172">Example</span></span>

<span data-ttu-id="a8470-173">Aby zapoznać się z przykładem, należy zapoznać się z formularzem [Włączanie odbiorcy v3 — Mapa tabeli kontaktów](enable-entity-map.md#enable-table-map)</span><span class="sxs-lookup"><span data-stu-id="a8470-173">For an example, see [Enabling the Customers V3—Contacts table map](enable-entity-map.md#enable-table-map)</span></span>

<span data-ttu-id="a8470-174">W celu rozwiązania alternatywnego opartego na woluminach danych w każdej jednostce, która musi uruchomić synchronizację początkową, należy zapoznać się z [Zagadnienia dotyczące synchronizacji początkowej](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="a8470-174">For an alternative approach that is based on data volumes in each entity that must run an initial synchronization, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]