---
title: '`Dodatek Widoczność magazynu'
description: W tym temacie opisano sposób instalowania i konfigurowania dodatku Widoczność magazynu dla systemu Dynamics 365 Supply Chain Management.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625072"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="8b9fa-103">Dodatek Widoczność magazynu</span><span class="sxs-lookup"><span data-stu-id="8b9fa-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="8b9fa-104">Dodatek Widoczność magazynu jest niezależną i wysoko skalowalną mikrodostępną usługą, która umożliwia śledzenie dostępnych zapasów w czasie rzeczywistym, udostępniając w ten sposób globalny widok widoczności zapasów.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="8b9fa-105">Wszystkie informacje dotyczące dostępnych zapasów są eksportowane do usługi w czasie rzeczywistym przez integrację SQL niskiego poziomu.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="8b9fa-106">System zewnętrzny uzyskuje dostęp do usługi za pośrednictwem interfejsów API RESTful w celu uzyskania informacji o dostępnych zapasach w danym zbiorze wymiarów, pobierając w ten sposób listę dostępnych stanowisk.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="8b9fa-107">Widoczność zapasów to mikrousługa wbudowana w systemie Common Data Service, co oznacza, że można ją rozszerzyć przez budowanie Power Apps i stosowanie dostosowanych funkcji Power BI w celu spełnienia wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-107">Inventory Visibility is a microservice built on the Common Data Service, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="8b9fa-108">Możliwe jest również uaktualnienie indeksu do kwerend magazynowych.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="8b9fa-109">Widoczność zapasów zapewnia opcje konfiguracji, które umożliwiają integrację z wieloma systemami innych firm.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="8b9fa-110">Obsługuje on standardowy rozmiar magazynu, możliwe do dostosowania rozszerzenia i standardowe, konfigurowalne obliczone ilości.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="8b9fa-111">W tym temacie opisano sposób instalowania i konfigurowania dodatku widoczność magazynu dla systemu Dynamics 365 Supply Chain Management oraz używania jego interfejsu programowania aplikacji (API).</span><span class="sxs-lookup"><span data-stu-id="8b9fa-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="8b9fa-112">Instalowanie dodatku Widoczność magazynu</span><span class="sxs-lookup"><span data-stu-id="8b9fa-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="8b9fa-113">Musisz zainstalować dodatek Widoczność magazynu, korzystając z Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8b9fa-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="8b9fa-114">LCS to portal współpracy, który zapewnia środowisko i zbiór regularnie zaktualizowanych usług ułatwiających zarządzanie cyklem życia aplikacji w aplikacjach Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="8b9fa-115">Aby uzyskać więcej informacji, zobacz [Zasoby w Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="8b9fa-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="8b9fa-116">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="8b9fa-116">Prerequisites</span></span>

<span data-ttu-id="8b9fa-117">Aby można było zainstalować dodatek Widoczność magazynu, trzeba:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="8b9fa-118">Uzyskać projekt implementacji usługi LCS z co najmniej jednym wdrożonym środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="8b9fa-119">Wygeneruj klucze beta dla oferty w LCS.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="8b9fa-120">Włącz klucze beta dla usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="8b9fa-121">Skontaktuj się z zespołem ds. produktu Widoczność magazynu Microsoft i podaj identyfikator środowiska, w którym chcesz wdrożyć dodatek Widoczność magazynu.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="8b9fa-122">Jeśli masz pytania dotyczące tych wymagań wstępnych, skontaktuj się z zespołem ds. produktu Widoczność magazynu.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="8b9fa-123">Instalacja aplikacji dodatkowych</span><span class="sxs-lookup"><span data-stu-id="8b9fa-123">Install the add-in</span></span>

<span data-ttu-id="8b9fa-124">Aby zainstalować dodatek Widoczność magazynu, trzeba:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="8b9fa-125">Zalogować się do portalu [Microsoft LifeCycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="8b9fa-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="8b9fa-126">Na stronie głównej wybierz projekt, w którym jest wdrożone środowisko.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="8b9fa-127">Na stronie projektu wybierz środowisko, w którym chcesz zainstalować dodatek.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="8b9fa-128">Na stronie środowiska przewiń w dół, aż zostanie wyświetlona sekcja **Dodatki środowiska**.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="8b9fa-129">Jeśli sekcja nie jest widoczna, należy upewnić się, że wstępnie wymagane klucze beta zostały w pełni przetworzone.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="8b9fa-130">W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="8b9fa-131">![Strona środowiska w LCS](media/inventory-visibility-environment.png "Strona środowiska w LCS")</span><span class="sxs-lookup"><span data-stu-id="8b9fa-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="8b9fa-132">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="8b9fa-133">Zostanie otwarta lista dostępnych dodatków.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="8b9fa-134">Wybierz **Usługę zapasy** z listy.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="8b9fa-135">(Uwaga: może to być teraz widoczne jako **Dodatek Widoczność magazynu dla Dynamics 365 Supply Chain Management** .)</span><span class="sxs-lookup"><span data-stu-id="8b9fa-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="8b9fa-136">Wprowadź wartości dla następujących pól środowiska:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="8b9fa-137">**AAD identyfikatora aplikacji**</span><span class="sxs-lookup"><span data-stu-id="8b9fa-137">**AAD application ID**</span></span>
    - <span data-ttu-id="8b9fa-138">**Identyfikator AAD dzierżawy**</span><span class="sxs-lookup"><span data-stu-id="8b9fa-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="8b9fa-139">![Strona konfiguracji dodatku](media/inventory-visibility-setup.png "Strona konfiguracji dodatku")</span><span class="sxs-lookup"><span data-stu-id="8b9fa-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="8b9fa-140">Zaakceptuj regulamin, zaznaczając pole wyboru **Regulamin**.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="8b9fa-141">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-141">Select **Install**.</span></span> <span data-ttu-id="8b9fa-142">Stan dodatku będzie widoczny jako **Instalowany**.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="8b9fa-143">Po zakończeniu operacji odśwież stronę, aby zobaczyć zmianę stanu na **Zainstalowane**.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="8b9fa-144">Pobierz token usługi zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="8b9fa-144">Get a security service token</span></span>

<span data-ttu-id="8b9fa-145">Aby uzyskać token usługi zabezpieczeń, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-145">To get a security service token, do the following:</span></span>

1. <span data-ttu-id="8b9fa-146">Pobierz `aadToken` i wywołaj punkt końcowy: https://securityservice.operations365.dynamics.com/token.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-146">Get your `aadToken` and call the endpoint: https://securityservice.operations365.dynamics.com/token.</span></span>
1. <span data-ttu-id="8b9fa-147">Zastąp `client_assertion` w treści swoim `aadToken`.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-147">Replace the `client_assertion` in the body with your `aadToken`.</span></span>
1. <span data-ttu-id="8b9fa-148">Zastąp kontekst w treści środowiskiem, w którym chcesz wdrożyć dodatek.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-148">Replace the context in the body with the environment where you want to deploy the add-in.</span></span>
1. <span data-ttu-id="8b9fa-149">Zamień zakres w treści na następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-149">Replace the scope in the body with the following:</span></span>

    - <span data-ttu-id="8b9fa-150">Zakres dla MCK — „https://inventoryservice.operations365.dynamics.cn/.default”</span><span class="sxs-lookup"><span data-stu-id="8b9fa-150">Scope for MCK - "https://inventoryservice.operations365.dynamics.cn/.default"</span></span>  
    <span data-ttu-id="8b9fa-151">(Identyfikator aplikacji Azure Active Directory i identyfikator dzierżawy MCK można znaleźć w `appsettings.mck.json` .)</span><span class="sxs-lookup"><span data-stu-id="8b9fa-151">(You can find the Azure Active Directory application ID and tenant ID for MCK in `appsettings.mck.json`.)</span></span>
    - <span data-ttu-id="8b9fa-152">Zakres dla PROD — „https://inventoryservice.operations365.dynamics.com/.default”</span><span class="sxs-lookup"><span data-stu-id="8b9fa-152">Scope for PROD - "https://inventoryservice.operations365.dynamics.com/.default"</span></span>  
    <span data-ttu-id="8b9fa-153">(Identyfikator aplikacji Azure Active Directory i identyfikator dzierżawy PROD można znaleźć w `appsettings.prod.json` .)</span><span class="sxs-lookup"><span data-stu-id="8b9fa-153">(You can find the Azure Active Directory application ID and tenant ID for PROD in `appsettings.prod.json`.)</span></span>

    <span data-ttu-id="8b9fa-154">Nowy raport powinien przypominać następujący przykład.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-154">The result should resemble the following example.</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. <span data-ttu-id="8b9fa-155">Otrzymasz `access_token` w odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-155">You will get an `access_token` in response.</span></span> <span data-ttu-id="8b9fa-156">Do wywołania interfejsu API Widoczność magazynu potrzebny jest token elementu nośnego.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-156">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="8b9fa-157">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-157">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="8b9fa-158">Odinstalowywanie dodatku</span><span class="sxs-lookup"><span data-stu-id="8b9fa-158">Uninstall the add-in</span></span>

<span data-ttu-id="8b9fa-159">Aby odinstalować dodatek, wybierz opcję **Odinstaluj**.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-159">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="8b9fa-160">Odśwież usługi LCS i dodatek Widoczność magazynu zostanie usunięty.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-160">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="8b9fa-161">Proces odinstalowywania usunie rejestrację dodatku, a także uruchomi zadanie w celu oczyszczenia wszystkich danych biznesowych przechowywanych w usłudze.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-161">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="8b9fa-162">Dodatek Widoczność magazynu w API publicznym</span><span class="sxs-lookup"><span data-stu-id="8b9fa-162">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="8b9fa-163">Publiczny interfejs API REST w dodatku Widoczność magazynu przedstawia kilka konkretnych punktów końcowych integracji.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-163">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="8b9fa-164">Obsługuje on trzy główne typy interakcji:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-164">It supports three main interaction types:</span></span>

- <span data-ttu-id="8b9fa-165">Księgowanie dostępnych zmian zapasów w dodatku z systemu zewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-165">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="8b9fa-166">Badanie bieżących ilości dostępnych zapasów z systemu zewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-166">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="8b9fa-167">Automatyczna synchronizacja z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-167">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="8b9fa-168">Synchronizacja automatyczna nie jest częścią publicznego interfejsu API, ale jest traktowana w tle dla środowisk, w których włączono dodatek widoczności magazynu.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-168">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="8b9fa-169">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-169">Authentication</span></span>

<span data-ttu-id="8b9fa-170">Token zabezpieczający platformy jest używany do wywoływania dodatku widoczności magazynu, więc musisz wygenerować token Azure Active Directory przy użyciu Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-170">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="8b9fa-171">Aby uzyskać więcej informacji na temat uzyskiwania tokenu zabezpieczającego, przejrzyj temat [Instalowanie dodatku Widoczność zapasów](#install-add-in).</span><span class="sxs-lookup"><span data-stu-id="8b9fa-171">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="8b9fa-172">Skonfiguruj interfejs API funkcji Widoczność magazynu</span><span class="sxs-lookup"><span data-stu-id="8b9fa-172">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="8b9fa-173">Przed rozpoczęciem korzystania z usługi należy wykonać konfiguracje opisane w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-173">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="8b9fa-174">Konfiguracja może się różnić w zależności od szczegółów środowiska.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-174">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="8b9fa-175">Obejmuje ono głównie cztery części:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-175">It primarily includes four parts:</span></span>

- [<span data-ttu-id="8b9fa-176">Partycjonowanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-176">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="8b9fa-177">Konfiguracje wymiarów</span><span class="sxs-lookup"><span data-stu-id="8b9fa-177">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="8b9fa-178">Indeksowanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-178">Indexing</span></span>](#indexing)
- [<span data-ttu-id="8b9fa-179">Miara niestandardowa</span><span class="sxs-lookup"><span data-stu-id="8b9fa-179">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="8b9fa-180">Partycjonowanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-180">Partitioning</span></span>

<span data-ttu-id="8b9fa-181">Partycjonowanie może znacząco wpłynąć na wydajność interfejsu API funkcji Widoczność magazynu.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-181">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="8b9fa-182">Dobrym pomysłem jest zdefiniowanie schematu, który umożliwi obsługę małych grup danych, a jednocześnie pozwala na uzyskanie istotnych kwerend dotyczących danych.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-182">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="8b9fa-183">`organizationId` (`dataAreaId` w Supply Chain Management) zawsze jest częścią partycjonowania, a domyślnie Widoczność magazynu jest ustawiana jako partycja według wymiarów jako *Oddział + Lokalizacja*.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-183">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="8b9fa-184">Oznacza to, że usługa musi być zawsze kwerendą o wymiarach zdefiniowane w filtrach.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-184">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="8b9fa-185">*Oddział* i *Lokalizacja* to dwa ogólne wymiary domyślne w obszarze Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-185">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="8b9fa-186">W Supply Chain Management te wymiary są nazywane *Oddziałem* (`InventSiteId`) i *Magazynem* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="8b9fa-186">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="8b9fa-187">Konfiguracje wymiarów</span><span class="sxs-lookup"><span data-stu-id="8b9fa-187">Dimension configurations</span></span>

<span data-ttu-id="8b9fa-188">Widoczność magazynu będzie zawierać listę ogólnych wymiarów, które umożliwiają integrację z systemem z wieloma źródłami.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-188">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="8b9fa-189">W poniższej tabeli wymieniono wymiary magazynowe, które będą domyślnymi nazwami wymiarów widocznymi w obszarze Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-189">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="8b9fa-190">Typ wymiaru</span><span class="sxs-lookup"><span data-stu-id="8b9fa-190">Dimension type</span></span> | <span data-ttu-id="8b9fa-191">Nazwa wymiaru</span><span class="sxs-lookup"><span data-stu-id="8b9fa-191">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="8b9fa-192">Produkt</span><span class="sxs-lookup"><span data-stu-id="8b9fa-192">Product</span></span> | `ColorId` |
| <span data-ttu-id="8b9fa-193">Produkt</span><span class="sxs-lookup"><span data-stu-id="8b9fa-193">Product</span></span> | `SizeId` |
| <span data-ttu-id="8b9fa-194">Produkt</span><span class="sxs-lookup"><span data-stu-id="8b9fa-194">Product</span></span> | `StyleId` |
| <span data-ttu-id="8b9fa-195">Produkt</span><span class="sxs-lookup"><span data-stu-id="8b9fa-195">Product</span></span> | `ConfigId` |
| <span data-ttu-id="8b9fa-196">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-196">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="8b9fa-197">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-197">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="8b9fa-198">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="8b9fa-198">Location</span></span> | `LocationId` |
| <span data-ttu-id="8b9fa-199">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="8b9fa-199">Location</span></span> | `SiteId` |
| <span data-ttu-id="8b9fa-200">Stan zapasów</span><span class="sxs-lookup"><span data-stu-id="8b9fa-200">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="8b9fa-201">Właściwe dla magazynu</span><span class="sxs-lookup"><span data-stu-id="8b9fa-201">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="8b9fa-202">Właściwe dla magazynu</span><span class="sxs-lookup"><span data-stu-id="8b9fa-202">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="8b9fa-203">Właściwe dla magazynu</span><span class="sxs-lookup"><span data-stu-id="8b9fa-203">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="8b9fa-204">Typ wymiaru wymieniony w poprzedniej tabeli służy tylko do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-204">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="8b9fa-205">Nie trzeba definiować typu wymiaru w funkcji Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-205">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="8b9fa-206">Jeśli wymiar niestandardowy istnieje i musi przepływać do wartości domyślnej w przypadku zużycia przez Widoczność zapasów, można skonfigurować **niestandardową** nazwę wymiaru w funkcji Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-206">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="8b9fa-207">Widoczność zapasów w systemie zewnętrznym za pośrednictwem interfejsów API RESTful, które umożliwiają uzyskiwanie dostępnych informacji na temat danego zestawu wymiarów do zbadania.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-207">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="8b9fa-208">W przypadku integracji funkcja Widoczność zapasów umożliwia skonfigurowanie *źródła danych kanału zewnętrznego* i wymiaru źródłowego do *Wymiarów docelowych* w ramach funkcji Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-208">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="8b9fa-209">Wymiar docelowy powinien mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-209">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="8b9fa-210">Wymiary domyślne w funkcji Widoczność zapasów</span><span class="sxs-lookup"><span data-stu-id="8b9fa-210">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="8b9fa-211">Wymiary niestandardowe</span><span class="sxs-lookup"><span data-stu-id="8b9fa-211">Custom dimensions</span></span>

<span data-ttu-id="8b9fa-212">Celem konfiguracji wymiarów jest ujednolicenie integracji wielosystemowej dla kwerendy dotyczącej wymiarów i zdarzenia księgowania z wymiarami.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-212">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="8b9fa-213">Indeksowanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-213">Indexing</span></span>

<span data-ttu-id="8b9fa-214">W większości momentów zapytanie o dostępne zapasy nie będzie zwracane tylko na najwyższym poziomie „suma”, ale wyniki zagregowane mogą być wyświetlane na podstawie wymiarów magazynowych.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-214">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="8b9fa-215">Widoczność zapasów zapewnia elastyczność, umożliwiając konfigurowanie indeksów opartych na wymiarze lub kombinacji wymiarów.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-215">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="8b9fa-216">Obecnie można konfigurować indeksy tylko do maks. pięć.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-216">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="8b9fa-217">Należy dokładnie rozważyć, którą kombinację wymiarów należy zastosować przed implementacją, aby zagwarantować, że będzie ona zgodna z potrzebami biznesowymi.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-217">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="8b9fa-218">Na przykład, jeśli chcesz zbadać produkty w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-218">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="8b9fa-219">Umożliwia wykonanie kwerendy dotyczącej zagregowanych dostępnych zapasów towaru, korzystając z wymiarów *Kolor* i *Rozmiar*.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-219">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="8b9fa-220">W niektórych przypadkach użytkownik chce jedynie wykonać kwerendę dotyczącą produktu łącznie.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-220">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="8b9fa-221">Dwa indeksy powinny mieć zdefiniowane następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-221">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="8b9fa-222">Pusty nawias będzie agregował na podstawie identyfikatora produktu w partycji.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-222">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="8b9fa-223">Indeksowanie określa sposób grupowania wyników na podstawie ustawienia kwerendy `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-223">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="8b9fa-224">W takim przypadku, jeśli nie zostaną zdefiniowane żadne wartości `groupBy`, sumy będą pobierane według `productid`.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-224">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="8b9fa-225">W przeciwnym razie, jeśli zostanie zdefiniowana `groupBy` jako `groupBy=ColorId&groupBy=SizeId`, zostanie otrzymanych wiele wierszy na podstawie różnych kombinacji koloru i rozmiaru w systemie.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-225">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="8b9fa-226">Kryteria kwerendy można umieścić w treści żądania.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-226">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="8b9fa-227">Oto przykładowe zapytanie dotyczące produktu z kombinacją koloru i rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-227">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a><span data-ttu-id="8b9fa-228">Miara niestandardowa</span><span class="sxs-lookup"><span data-stu-id="8b9fa-228">Custom measurement</span></span>

<span data-ttu-id="8b9fa-229">Domyślne ilości miar są połączone z Supply Chain Management, jednak może zaistnieć potrzeba utworzenia ilości składającej się z kombinacji domyślnych miar.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-229">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="8b9fa-230">W tym celu można skonfigurować niestandardowe ilości, które zostaną dodane do danych wyjściowych zapytań dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-230">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="8b9fa-231">Funkcja umożliwia po prostu zdefiniowanie zestawu miar, które będą dodawane, i/lub zestawu miar, które zostaną odjęte od miary niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-231">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="8b9fa-232">Na przykład przy użyciu poniższego warunku kwerendy można skonfigurować niestandardową ilość miary jako `MyCustomAvailableforReservation`, która będzie zużywana przez system zużycia.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-232">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="8b9fa-233">System zużycia</span><span class="sxs-lookup"><span data-stu-id="8b9fa-233">Consumption system</span></span> | <span data-ttu-id="8b9fa-234">Obliczone miary</span><span class="sxs-lookup"><span data-stu-id="8b9fa-234">Calculated measurers</span></span> | <span data-ttu-id="8b9fa-235">Źródło danych</span><span class="sxs-lookup"><span data-stu-id="8b9fa-235">Data source</span></span> | <span data-ttu-id="8b9fa-236">Modyfikator</span><span class="sxs-lookup"><span data-stu-id="8b9fa-236">Modifier</span></span> | <span data-ttu-id="8b9fa-237">Typ obliczania modyfikatora</span><span class="sxs-lookup"><span data-stu-id="8b9fa-237">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="8b9fa-238">Dodanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-238">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="8b9fa-239">Dodanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-239">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="8b9fa-240">Odejmowanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-240">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="8b9fa-241">Dodanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-241">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="8b9fa-242">Odejmowanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-242">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="8b9fa-243">Dodanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-243">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="8b9fa-244">Dodanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-244">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="8b9fa-245">Odejmowanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-245">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="8b9fa-246">Odejmowanie</span><span class="sxs-lookup"><span data-stu-id="8b9fa-246">Subtraction</span></span> |

<span data-ttu-id="8b9fa-247">Dzięki temu kwerenda dotycząca niestandardowej ilości miary zwróci następujące dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-247">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="8b9fa-248">Dane wyjściowe `MyCustomAvailableforReservation` są oparte na ustawieniu obliczania w niestandardowych pomiarach jako:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-248">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="8b9fa-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="8b9fa-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="8b9fa-250">Księgowanie zmian dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="8b9fa-250">Posting on-hand changes</span></span>

<span data-ttu-id="8b9fa-251">Dokładny adres URL, na który zostanie ogłoszone zdarzenie, zależy od regionu geograficznego.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-251">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="8b9fa-252">Przyjmie on postać:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-252">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="8b9fa-253">Po uwierzytelnieniu ten adres URL może być używany wraz z HTTP `POST` w celu wysyłania do usługi zdarzeń zmiany dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-253">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="8b9fa-254">Specjalny nagłówek jest używany do komunikowania się z usługami Dynamics 365 Services za pośrednictwem żądań HTTP, oznaczający identyfikator środowiska Supply Chain Management, z którym są połączone dane.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-254">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="8b9fa-255">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-255">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="8b9fa-256">Wysyłanie zapytania o zmiany dostępnych zapasów — przykład 1</span><span class="sxs-lookup"><span data-stu-id="8b9fa-256">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="8b9fa-257">W tym przykładzie przedstawiono scenariusz, w którym zostanie ustawiona konfiguracja wymiaru w programie Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-257">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="8b9fa-258">Aby skonfigurować mapowanie wymiaru w programie, należy skorzystać z następującej kwerendy Power Apps:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-258">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="8b9fa-259">Teraz można określić `dimensionDataSource` i zastosować w kwerendach niestandardowe wymiary.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-259">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="8b9fa-260">System automatycznie przekonwertuje niestandardowe wymiary na wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-260">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="8b9fa-261">Wysyłanie zapytania o zmiany dostępnych zapasów — przykład 2</span><span class="sxs-lookup"><span data-stu-id="8b9fa-261">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="8b9fa-262">W tym przykładzie przedstawiono scenariusz, w którym nie skonfigurowano żadnych mapowań konfiguracji wymiarów w systemie Power Apps, więc Księgowanie powinno również mieć wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-262">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="8b9fa-263">Wszystkie wymiary muszą być wymiarami podstawowymi, jeśli pole `dimensionDataSource` ma wartość null, jest puste lub zawiera białe znaki.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-263">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="8b9fa-264">Edytowanie pól właściwości dokumentów JSON</span><span class="sxs-lookup"><span data-stu-id="8b9fa-264">JSON document field properties</span></span>

<span data-ttu-id="8b9fa-265">Pola z dostarczonych wcześniej przykładów zapytania JSON mają właściwości wymienione w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-265">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="8b9fa-266">Identyfikator pola</span><span class="sxs-lookup"><span data-stu-id="8b9fa-266">Field ID</span></span> | <span data-ttu-id="8b9fa-267">opis</span><span class="sxs-lookup"><span data-stu-id="8b9fa-267">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="8b9fa-268">Unikatowy identyfikator określonego zdarzenia zmiany.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-268">A unique ID for the specific change event.</span></span> <span data-ttu-id="8b9fa-269">Ten identyfikator służy do zapewnienia, że jeśli komunikacja z usługą nie powiedzie się w trakcie księgowania, ponowne przesłanie zdarzenia nie spowoduje, że zdarzenie to jest zliczane dwukrotnie w systemie.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-269">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="8b9fa-270">Identyfikator organizacji połączonej ze zdarzeniem.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-270">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="8b9fa-271">Ta opcja jest mapowana na dane organizacji Supply Chain Management lub identyfikatory obszaru danych.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-271">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="8b9fa-272">Identyfikator zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-272">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="8b9fa-273">Ilość, o którą należy zmienić dostępne zapasy.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-273">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="8b9fa-274">Jeśli na przykład do półki dodano 10 nowych bajgli, ta wartość byłaby równa 10.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-274">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="8b9fa-275">Jeśli 3 bajgle zostały usunięte z półki lub sprzedane, ta wartość wynosi-3.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-275">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="8b9fa-276">Źródło danych wymiarów używanych w zdarzeniu zmiany księgowania i kwerendzie.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-276">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="8b9fa-277">W przypadku określenia źródła danych można wykorzystać niestandardowe wymiary z określonego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-277">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="8b9fa-278">W przypadku konfiguracji wymiarów widoczność zapasów może mapować niestandardowe wymiary do ogólnych wymiarów domyślnych.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-278">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="8b9fa-279">Jeśli `dimensionDataSource` nie określiło wartości, w kwerendach można stosować tylko ogólne wymiary domyślne.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-279">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="8b9fa-280">Dynamiczny zbiór par klucz-wartość.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-280">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="8b9fa-281">Zostaną one zmapowane na niektóre wymiary w module Supply Chain Management, ale można również dodać niestandardowe wymiary (np *źródło*), które mogą oznaczać, że zdarzenie pochodzi z Supply Chain Management lub z systemu zewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-281">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="8b9fa-282">Badanie bieżących dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="8b9fa-282">Querying current on-hand</span></span>

<span data-ttu-id="8b9fa-283">Punkt końcowy badania bieżących dostępnych zapasów będzie miał podobny adres URL:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-283">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="8b9fa-284">Zostanie zbadany za pomocą metody HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-284">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="8b9fa-285">Bieżąca kwerenda dostępnych zapasów — przykład 1</span><span class="sxs-lookup"><span data-stu-id="8b9fa-285">Current on-hand query example 1</span></span>

<span data-ttu-id="8b9fa-286">W tym przykładzie przedstawiono scenariusz, w którym została zakończona konfiguracja wymiaru w programie Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-286">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="8b9fa-287">Aby skonfigurować mapowanie wymiaru w programie, należy skorzystać z następującej kwerendy Power Apps:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-287">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="8b9fa-288">Teraz można określić `dimensionDataSource` i zastosować w kwerendach niestandardowe wymiary.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-288">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="8b9fa-289">System automatycznie przekonwertuje niestandardowe wymiary na wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-289">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="8b9fa-290">Istnieje możliwość określenia wartości `DimensionDataSource` w polu `filters` i określenia wymiarów niestandardowych w polach `filters` i `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-290">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="8b9fa-291">System automatycznie przekonwertuje niestandardowe wymiary na wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-291">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="8b9fa-292">Bieżąca kwerenda dostępnych zapasów — przykład 2</span><span class="sxs-lookup"><span data-stu-id="8b9fa-292">Current on-hand query example 2</span></span>

<span data-ttu-id="8b9fa-293">W tym przykładzie przedstawiono scenariusz, w którym nie skonfigurowano żadnych mapowań konfiguracji wymiarów w systemie Power Apps, więc Księgowanie powinno również mieć wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-293">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="8b9fa-294">Wszystkie wymiary muszą być wymiarami podstawowymi, jeśli pole `dimensionDataSource` ma wartość null w `filters`, jest puste lub zawiera białe znaki.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-294">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="8b9fa-295">Przykładowy wynik zwrotu</span><span class="sxs-lookup"><span data-stu-id="8b9fa-295">Example return result</span></span>

<span data-ttu-id="8b9fa-296">Kwerendy przedstawione w poprzednich przykładach mogą zwracać wynik podobny do tego.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-296">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="8b9fa-297">Należy zwrócić uwagę, że pola ilości są ustrukturyzowane i w postaci słownika miar i skojarzonych z nimi wartości.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-297">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
