---
title: Dodatkowe komponenty administracyjne do elektronicznego fakturowania
description: Ten temat zawiera informacje o składnikach związanych z administrowaniem dodatkiem Fakturowanie elektroniczne.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6f630ebb694217c3bd52378a649933a670c090f2
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104425"
---
# <a name="electronic-invoicing-add-on-administration-components"></a><span data-ttu-id="b6bda-103">Dodatkowe komponenty administracyjne do elektronicznego fakturowania</span><span class="sxs-lookup"><span data-stu-id="b6bda-103">Electronic invoicing add-on administration components</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="b6bda-104">Ten temat zawiera informacje o składnikach związanych z administrowaniem dodatkiem Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-104">This topic provides information about the components that are related to administration of the Electronic invoicing add-on.</span></span> <span data-ttu-id="b6bda-105">Zawiera również informacje o konfigurowaniu dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-105">It also provides information about how to configure the Electronic invoicing add-on service.</span></span>

## <a name="azure"></a><span data-ttu-id="b6bda-106">Azure</span><span class="sxs-lookup"><span data-stu-id="b6bda-106">Azure</span></span>

<span data-ttu-id="b6bda-107">Użyj Microsoft Azure, aby utworzyć wpisy tajne dla magazynu kluczy i konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="b6bda-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="b6bda-108">Następnie użyj tej funkcji w konfiguracji dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-108">Then use the secrets in the configuration of the Electronic invoicing add-on.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="b6bda-109">Usługa Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="b6bda-109">Lifecycle Services</span></span>

<span data-ttu-id="b6bda-110">Użyj Microsoft Dynamics Lifecycle Services (LCS), aby włączyć dodatek dla mikrousług dla projektu wdrożenia LCS.</span><span class="sxs-lookup"><span data-stu-id="b6bda-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the add-on for the microservices for your LCS deployment project.</span></span>

<span data-ttu-id="b6bda-111">W LCS wybierz kafelek **Zarządzanie funkcjami wersji zapoznawczej**, a następnie włącz funkcję **Usługi e-fakturowania**.</span><span class="sxs-lookup"><span data-stu-id="b6bda-111">In LCS, select the **Preview feature management** tile, and then turn on the **e-Invoicing Service** feature.</span></span>

## <a name="regulatory-configuration-services"></a><span data-ttu-id="b6bda-112">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="b6bda-112">Regulatory Configuration Services</span></span>

<span data-ttu-id="b6bda-113">Dynamics 365 Regulatory Configuration Services (RCS) to interfejs używany do konfigurowania dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-113">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure the Electronic invoicing add-on.</span></span> <span data-ttu-id="b6bda-114">Zasoby takie jak środowiska i funkcje fakturowania elektronicznego są tworzone, utrzymywane i hostowane w RCS.</span><span class="sxs-lookup"><span data-stu-id="b6bda-114">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="b6bda-115">Gdy zasoby są gotowe, są publikowane w usłudze dodatkowej Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-115">When the resources are ready, they are published to the Electronic invoicing add-on service.</span></span>

<span data-ttu-id="b6bda-116">Aby uzyskać więcej informacji na temat RCS, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="b6bda-116">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="b6bda-117">Integracja z dodatkiem fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="b6bda-117">Integration with the Electronic invoicing add-on</span></span>

<span data-ttu-id="b6bda-118">Zanim będziesz mógł używać RCS do konfigurowania faktur elektronicznych, musisz skonfigurować RCS, aby umożliwić komunikację z dodatkiem Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-118">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with the Electronic invoicing add-on.</span></span> <span data-ttu-id="b6bda-119">Tę konfigurację można ukończyć na karcie **Dodatek Fakturowanie elektroniczne** na stronie **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="b6bda-119">You complete this configuration on the **Electronic invoicing add-on** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="b6bda-120">Punkt końcowy usługi</span><span class="sxs-lookup"><span data-stu-id="b6bda-120">Service endpoint</span></span>

<span data-ttu-id="b6bda-121">Adres URL punktu końcowego dodatku do fakturowania elektronicznego może się różnić w zależności od lokalizacji geograficznej centrum danych platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="b6bda-121">The URL of the Electronic invoicing add-on endpoint can vary according to the Azure datacenter geography.</span></span> <span data-ttu-id="b6bda-122">W poniższej tabeli przedstawiono dostępność według regionów:</span><span class="sxs-lookup"><span data-stu-id="b6bda-122">The following table lists the availability per region:</span></span>

| <span data-ttu-id="b6bda-123">Geografia centrum danych platformy Azure</span><span class="sxs-lookup"><span data-stu-id="b6bda-123">Azure datacenter geography</span></span> | <span data-ttu-id="b6bda-124">Adres URL punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="b6bda-124">Service endpoint URL</span></span>                                                       |
|----------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="b6bda-125">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="b6bda-125">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="b6bda-126">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="b6bda-126">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="b6bda-127">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="b6bda-127">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="b6bda-128">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="b6bda-128">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

#### <a name="application-id"></a><span data-ttu-id="b6bda-129">Identyfikator aplikacji</span><span class="sxs-lookup"><span data-stu-id="b6bda-129">Application ID</span></span>

<span data-ttu-id="b6bda-130">Identyfikator aplikacji jest identyfikatorem dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-130">The application ID is the ID of the Electronic invoicing add-on application.</span></span> <span data-ttu-id="b6bda-131">W tym przypadku wartość jest stała: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="b6bda-131">In this case, the value is fixed: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

#### <a name="lcs-environment-id"></a><span data-ttu-id="b6bda-132">Identyfikator środowiska LCS</span><span class="sxs-lookup"><span data-stu-id="b6bda-132">LCS environment ID</span></span>

<span data-ttu-id="b6bda-133">Identyfikator środowiska LCS to identyfikator subskrypcji LCS Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="b6bda-133">The LCS environment ID is the ID of your organization's LCS subscription.</span></span>

### <a name="service-environments"></a><span data-ttu-id="b6bda-134">Środowiska usługi</span><span class="sxs-lookup"><span data-stu-id="b6bda-134">Service environments</span></span>

<span data-ttu-id="b6bda-135">Środowiska usług to partycje logiczne utworzone w celu obsługi funkcji fakturowania elektronicznego w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-135">Service environments are logical partitions that are created to support execution of the electronic invoicing features in the Electronic invoicing add-on.</span></span> <span data-ttu-id="b6bda-136">Klucze tajne zabezpieczeń i certyfikaty cyfrowe oraz ład (czyli uprawnienia dostępu) należy skonfigurować na poziomie środowiska usługi.</span><span class="sxs-lookup"><span data-stu-id="b6bda-136">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="b6bda-137">Klienci mogą tworzyć dowolną liczbę środowisk usługowych.</span><span class="sxs-lookup"><span data-stu-id="b6bda-137">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="b6bda-138">Wszystkie środowiska usług, które tworzy klient, są od siebie niezależne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-138">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="b6bda-139">Środowiska usługowe muszą być tworzone i utrzymywane w RCS.</span><span class="sxs-lookup"><span data-stu-id="b6bda-139">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="b6bda-140">Gdy środowiska usług są gotowe, należy je opublikować w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-140">When the service environments are ready, they must be published to the Electronic invoicing add-on.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="b6bda-141">Stan środowiska usługi</span><span class="sxs-lookup"><span data-stu-id="b6bda-141">Service environment status</span></span>

<span data-ttu-id="b6bda-142">Środowiskami usług można zarządzać za pomocą stanu.</span><span class="sxs-lookup"><span data-stu-id="b6bda-142">Service environments can be managed through status.</span></span> <span data-ttu-id="b6bda-143">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="b6bda-143">The possible options are:</span></span>

- <span data-ttu-id="b6bda-144">**Nie opublikowano** — środowisko zostało utworzone, ale nie zostało jeszcze opublikowane.</span><span class="sxs-lookup"><span data-stu-id="b6bda-144">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="b6bda-145">**Opublikowano** — środowisko zostało opublikowane w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-145">**Published** – The environment has been published to the Electronic invoicing add-on.</span></span>
- <span data-ttu-id="b6bda-146">**Zmienione** — Atrybuty opublikowanego środowiska zostały zmienione, ale zmiany nie zostały jeszcze opublikowane.</span><span class="sxs-lookup"><span data-stu-id="b6bda-146">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="b6bda-147">Tajemnice odbiorców</span><span class="sxs-lookup"><span data-stu-id="b6bda-147">Customer secrets</span></span>

<span data-ttu-id="b6bda-148">Usługa dodatkowa Fakturowanie elektroniczne jest odpowiedzialna za przechowywanie wszystkich danych biznesowych w zasobach platformy Azure należących do Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="b6bda-148">The Electronic invoicing add-on service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="b6bda-149">Aby upewnić się, że usługa działa poprawnie i że wszystkie dane biznesowe, które są potrzebne i generowane przez dodatek Faktury elektroniczne, są dostępne tylko dla tego dodatku, musisz utworzyć dwa główne zasoby platformy Azure:</span><span class="sxs-lookup"><span data-stu-id="b6bda-149">To ensure that the service works correctly, and that all the business data that is required for and generated by the Electronic invoicing add-on is accessed only by the add-on, you must create two main Azure resources:</span></span>

- <span data-ttu-id="b6bda-150">Konto magazynu systemu Azure (magazyn obiektów BLOB) do przechowywania faktur elektronicznych</span><span class="sxs-lookup"><span data-stu-id="b6bda-150">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="b6bda-151">Magazyn kluczy platformy Azure, w którym będą przechowywane certyfikaty i jednolity identyfikator zasobów (URI) konta magazynu</span><span class="sxs-lookup"><span data-stu-id="b6bda-151">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="b6bda-152">Dedykowany magazyn kluczy i konto magazynu klienta muszą być przydzielone specjalnie do użytku z dodatkiem Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-152">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing add-on.</span></span>

<span data-ttu-id="b6bda-153">Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="b6bda-153">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="b6bda-154">Użytkownicy</span><span class="sxs-lookup"><span data-stu-id="b6bda-154">Users</span></span>

<span data-ttu-id="b6bda-155">Każde środowisko usługowe musi zawierać listę użytkowników, którzy mogą łączyć się z Dynamics 365 Finance i Dynamics 365 Supply Chain Management w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-155">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in the Electronic invoicing add-on.</span></span>

#### <a name="publication"></a><span data-ttu-id="b6bda-156">Publikacja</span><span class="sxs-lookup"><span data-stu-id="b6bda-156">Publication</span></span>

<span data-ttu-id="b6bda-157">Środowiska usług muszą zostać opublikowane w dodatku Fakturowanie elektroniczne, zanim będą mogły być używane.</span><span class="sxs-lookup"><span data-stu-id="b6bda-157">Service environments must be published to the Electronic invoicing add-on before they can be used.</span></span> <span data-ttu-id="b6bda-158">Finance i Supply Chain Management mają dostęp tylko do opublikowanych środowisk.</span><span class="sxs-lookup"><span data-stu-id="b6bda-158">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="b6bda-159">Ponadto środowisko usługi musi zostać opublikowane, zanim jakiekolwiek aktualizacje jego atrybutów zaczną obowiązywać w usłudze fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="b6bda-159">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="b6bda-160">Połączone aplikacje</span><span class="sxs-lookup"><span data-stu-id="b6bda-160">Connected applications</span></span>

<span data-ttu-id="b6bda-161">Połączone aplikacje to instancje Finance i Supply Chain Management, do których możesz chcieć dotrzeć za pośrednictwem RCS.</span><span class="sxs-lookup"><span data-stu-id="b6bda-161">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="b6bda-162">Oprócz adresu URL aplikacji i jej dzierżawy, połączona aplikacja zawiera poświadczenia, które umożliwiają RCS łączenie się ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="b6bda-162">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="b6bda-163">Za pomocą połączonych aplikacji można skonfigurować część funkcji fakturowania elektronicznego w rozwiązaniu Finance i Supply Chain Management, aby cała funkcja fakturowania elektronicznego działała.</span><span class="sxs-lookup"><span data-stu-id="b6bda-163">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="b6bda-164">Finance i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="b6bda-164">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing-add-on"></a><span data-ttu-id="b6bda-165">Integracja z dodatkiem fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="b6bda-165">Integration with Electronic invoicing add-on</span></span>

<span data-ttu-id="b6bda-166">Zanim będzie można używać programu Finance i Supply Chain Management do wystawiania faktur elektronicznych za pośrednictwem dodatku Fakturowanie elektroniczne, dodatek musi być skonfigurowany tak, aby umożliwić komunikację z usługą.</span><span class="sxs-lookup"><span data-stu-id="b6bda-166">Before you can use Finance and Supply Chain Management to issue electronic invoices through the Electronic invoicing add-on, the add-on must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="b6bda-167">Funkcja integracji dodatku elektronicznego fakturowania</span><span class="sxs-lookup"><span data-stu-id="b6bda-167">Electronic invoicing add-on integration feature</span></span>

<span data-ttu-id="b6bda-168">Aby umożliwić komunikację między rozwiązaniami Finance i Supply Chain Management a dodatkiem Fakturowanie elektroniczne, należy włączyć funkcję integracji dodatku **Fakturowanie elektroniczne** w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="b6bda-168">To enable communication between Finance and Supply Chain Management and the Electronic invoicing add-on, you must turn on the **Electronic Invoicing add-on integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="b6bda-169">Punkt końcowy usługi</span><span class="sxs-lookup"><span data-stu-id="b6bda-169">Service endpoint</span></span>

<span data-ttu-id="b6bda-170">Punkt końcowy usługi to adres URL, w którym znajduje się dodatek Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-170">The service endpoint is the URL where the Electronic invoicing add-on is located.</span></span> <span data-ttu-id="b6bda-171">Przed wystawieniem faktur elektronicznych należy skonfigurować punkt końcowy usługi w programie Finance i Supply Chain Management, aby umożliwić komunikację z usługą.</span><span class="sxs-lookup"><span data-stu-id="b6bda-171">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="b6bda-172">Aby skonfigurować punkt końcowy usługi, przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametr dokumentu elektronicznego**, a następnie na zakładce **Usługi przesyłania** w polu **Adres URL dodatku do fakturowania elektronicznego** wprowadź adres URL zgodnie z opisem w tabeli opisanej w sekcji **Punkt końcowy usługi**.</span><span class="sxs-lookup"><span data-stu-id="b6bda-172">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing add-on URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="b6bda-173">Środowiska</span><span class="sxs-lookup"><span data-stu-id="b6bda-173">Environments</span></span>

<span data-ttu-id="b6bda-174">Nazwa środowiska wprowadzona w Finance i Supply Chain Management odnosi się do nazwy środowiska utworzonego w RCS i opublikowanego w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="b6bda-174">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to the Electronic invoicing add-on.</span></span>

<span data-ttu-id="b6bda-175">Środowisko należy skonfigurować na karcie **Usługi przesyłania** na stronie **Parametrów dokumentu elektronicznego**, tak aby każde żądanie wystawienia faktury elektronicznej zawierało środowisko, w którym dodatek Fakturowanie elektroniczne może określić, która funkcja fakturowania elektronicznego musi przetworzyć żądanie.</span><span class="sxs-lookup"><span data-stu-id="b6bda-175">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where the Electronic invoicing add-on can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6bda-176">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b6bda-176">Additional resources</span></span>

- [<span data-ttu-id="b6bda-177">Skonfiguruj faktury elektroniczne w RCS</span><span class="sxs-lookup"><span data-stu-id="b6bda-177">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="b6bda-178">Wystawiaj faktury elektroniczne w Finance i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="b6bda-178">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)
