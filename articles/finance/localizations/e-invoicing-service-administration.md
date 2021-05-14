---
title: Składniki administracyjne fakturowania elektronicznego
description: Ten temat zawiera informacje o składnikach związanych z administrowaniem Fakturowaniem elektronicznym.
author: gionoder
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 3ac4a03d75898680b5655421f3024dc6f666464c
ms.sourcegitcommit: 54d3ec0c006bfa9d2b849590205be08551c4e0f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/30/2021
ms.locfileid: "5963198"
---
# <a name="electronic-invoicing-administration-components"></a><span data-ttu-id="5a5be-103">Składniki administracyjne fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="5a5be-103">Electronic invoicing administration components</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5a5be-104">Ten temat zawiera informacje o składnikach związanych z administrowaniem Fakturowaniem elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="5a5be-104">This topic provides information about the components that are related to administration of Electronic invoicing.</span></span> <span data-ttu-id="5a5be-105">Zawiera również informacje o konfigurowaniu usługi Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="5a5be-105">It also provides information about how to configure the Electronic invoicing service.</span></span>

## <a name="azure"></a><span data-ttu-id="5a5be-106">Azure</span><span class="sxs-lookup"><span data-stu-id="5a5be-106">Azure</span></span>

<span data-ttu-id="5a5be-107">Użyj Microsoft Azure, aby utworzyć wpisy tajne dla Key Vault i konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="5a5be-107">Use Microsoft Azure to create the secrets for the Key Vault and storage account.</span></span> <span data-ttu-id="5a5be-108">Następnie użyj tej funkcji w konfiguracji funkcji Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="5a5be-108">Then use the secrets in the configuration of Electronic invoicing.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="5a5be-109">Usługa Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="5a5be-109">Lifecycle Services</span></span>

<span data-ttu-id="5a5be-110">Użyj Microsoft Dynamics Lifecycle Services (LCS), aby włączyć funkcję dla mikrousług dla projektu wdrożenia LCS.</span><span class="sxs-lookup"><span data-stu-id="5a5be-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="5a5be-111">Instalacja mikrousługi w umacie LCS wymaga co najmniej maszyny wirtualnej warstwy 2.</span><span class="sxs-lookup"><span data-stu-id="5a5be-111">The installation of the microservice in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="5a5be-112">Aby uzyskać więcej informacji o planowaniu w środowiskach, należy zapoznać się z tematem [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="5a5be-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="5a5be-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="5a5be-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="5a5be-114">Dynamics 365 Regulatory Configuration Services (RCS) to interfejs używany do konfigurowania Fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="5a5be-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure Electronic invoicing.</span></span> <span data-ttu-id="5a5be-115">Zasoby takie jak środowiska i funkcje fakturowania elektronicznego są tworzone, utrzymywane i hostowane w RCS.</span><span class="sxs-lookup"><span data-stu-id="5a5be-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="5a5be-116">Gdy zasoby są gotowe, są publikowane w usłudze Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="5a5be-116">When the resources are ready, they are published to Electronic invoicing service.</span></span>

<span data-ttu-id="5a5be-117">Aby uzyskać informacje o rejestracji w RCS, zobacz temat [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="5a5be-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="5a5be-118">Aby uzyskać więcej informacji na temat RCS, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="5a5be-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="5a5be-119">Integracja z funkcją fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="5a5be-119">Integration with Electronic invoicing</span></span> 

<span data-ttu-id="5a5be-120">Zanim będziesz mógł używać RCS do konfigurowania faktur elektronicznych, musisz skonfigurować RCS, aby umożliwić komunikację z funkcją Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="5a5be-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with Electronic invoicing.</span></span> <span data-ttu-id="5a5be-121">Tę konfigurację można ukończyć na karcie **Fakturowanie elektroniczne** na stronie **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="5a5be-121">You complete this configuration on the **Electronic invoicing** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="5a5be-122">Punkt końcowy usługi</span><span class="sxs-lookup"><span data-stu-id="5a5be-122">Service endpoint</span></span>

<span data-ttu-id="5a5be-123">Fakturowanie elektroniczne jest dostępne w kilku lokalizacjach geograficznych centrów danych platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="5a5be-123">Electronic invoicing is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="5a5be-124">W poniższej tabeli przedstawiono dostępność według regionów.</span><span class="sxs-lookup"><span data-stu-id="5a5be-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="5a5be-125">Geografia centrum danych platformy Azure</span><span class="sxs-lookup"><span data-stu-id="5a5be-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="5a5be-126">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="5a5be-126">East US</span></span>                    |
| <span data-ttu-id="5a5be-127">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="5a5be-127">West US</span></span>                    |
| <span data-ttu-id="5a5be-128">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="5a5be-128">North EU</span></span>                   |
| <span data-ttu-id="5a5be-129">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="5a5be-129">West EU</span></span>                    |

### <a name="service-environments"></a><span data-ttu-id="5a5be-130">Środowiska usługi</span><span class="sxs-lookup"><span data-stu-id="5a5be-130">Service environments</span></span>

<span data-ttu-id="5a5be-131">Środowiska usług to partycje logiczne utworzone w celu obsługi funkcji fakturowania elektronicznego w Fakturowaniu elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="5a5be-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in Electronic invoicing.</span></span> <span data-ttu-id="5a5be-132">Klucze tajne zabezpieczeń i certyfikaty cyfrowe oraz ład (czyli uprawnienia dostępu) należy skonfigurować na poziomie środowiska usługi.</span><span class="sxs-lookup"><span data-stu-id="5a5be-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="5a5be-133">Klienci mogą tworzyć dowolną liczbę środowisk usługowych.</span><span class="sxs-lookup"><span data-stu-id="5a5be-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="5a5be-134">Wszystkie środowiska usług, które tworzy klient, są od siebie niezależne.</span><span class="sxs-lookup"><span data-stu-id="5a5be-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="5a5be-135">Środowiska usługowe muszą być tworzone i utrzymywane w RCS.</span><span class="sxs-lookup"><span data-stu-id="5a5be-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="5a5be-136">Gdy środowiska usług są gotowe, należy je opublikować w funkcji Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="5a5be-136">When the service environments are ready, they must be published to Electronic invoicing.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="5a5be-137">Stan środowiska usługi</span><span class="sxs-lookup"><span data-stu-id="5a5be-137">Service environment status</span></span>

<span data-ttu-id="5a5be-138">Środowiskami usług można zarządzać za pomocą stanu.</span><span class="sxs-lookup"><span data-stu-id="5a5be-138">Service environments can be managed through status.</span></span> <span data-ttu-id="5a5be-139">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="5a5be-139">The possible options are:</span></span>

- <span data-ttu-id="5a5be-140">**Nie opublikowano** — środowisko zostało utworzone, ale nie zostało jeszcze opublikowane.</span><span class="sxs-lookup"><span data-stu-id="5a5be-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="5a5be-141">**Opublikowano** — środowisko zostało opublikowane w funkcji Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="5a5be-141">**Published** – The environment has been published to Electronic invoicing .</span></span>
- <span data-ttu-id="5a5be-142">**Zmienione** — Atrybuty opublikowanego środowiska zostały zmienione, ale zmiany nie zostały jeszcze opublikowane.</span><span class="sxs-lookup"><span data-stu-id="5a5be-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="5a5be-143">Tajemnice odbiorców</span><span class="sxs-lookup"><span data-stu-id="5a5be-143">Customer secrets</span></span>

<span data-ttu-id="5a5be-144">Usługa Fakturowanie elektroniczne jest odpowiedzialna za przechowywanie wszystkich danych biznesowych w zasobach platformy Azure należących do Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="5a5be-144">The Electronic invoicing service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="5a5be-145">Aby upewnić się, że usługa działa poprawnie i że wszystkie dane biznesowe, które są potrzebne i generowane przez Faktury elektroniczne, są dostępne tylko dla tego dodatku, musisz utworzyć dwa główne zasoby platformy Azure:</span><span class="sxs-lookup"><span data-stu-id="5a5be-145">To ensure that the service works correctly, and that all the business data that is required for and generated by Electronic invoicing is accessed appropriately, you must create two main Azure resources:</span></span>

- <span data-ttu-id="5a5be-146">Konto magazynu systemu Azure (magazyn obiektów BLOB) do przechowywania faktur elektronicznych</span><span class="sxs-lookup"><span data-stu-id="5a5be-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="5a5be-147">Magazyn Azure Key Vault, w którym będą przechowywane certyfikaty i jednolity identyfikator zasobów (URI) konta magazynu</span><span class="sxs-lookup"><span data-stu-id="5a5be-147">An Azure Key Vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>


<span data-ttu-id="5a5be-148">Dedykowany magazyn Key Vault i konto magazynu klienta muszą być przydzielone specjalnie do użytku z Fakturowaniem elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="5a5be-148">A dedicated Key Vault and customer storage account must be allocated specifically for use with Electronic Invoicing.</span></span> <span data-ttu-id="5a5be-149">Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="5a5be-149">For more information, see [Create an Azure storage account and a Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

<span data-ttu-id="5a5be-150">Aby monitorować kondycję magazynu Key Vault i odbierać alerty, skonfiguruj monitor Azure dla magazynu Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5a5be-150">To monitor the health of your Key Vault and receive alerts, configure the Azure Monitor for key Vault.</span></span> <span data-ttu-id="5a5be-151">Włączenie rejestrowania magazynu Key Vault umożliwia monitorowanie, jak, kiedy i kto uzyskuje dostęp do magazynów Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5a5be-151">By enabling Key Vault logging, you can monitor how, when, and by whom your Key Vaults are accessed.</span></span> <span data-ttu-id="5a5be-152">Aby uzyskać więcej informacji, zobacz temat [Monitorowanie i alerty Azure Key Vault](/azure/key-vault/general/alert) i [Włączanie rejestrowania magazynu Key Vault](/azure/key-vault/general/howto-logging?tabs=azure-cli).</span><span class="sxs-lookup"><span data-stu-id="5a5be-152">For more information, see [Monitoring and alerting for Azure Key Vault](/azure/key-vault/general/alert) and [How to enable Key Vault logging](/azure/key-vault/general/howto-logging?tabs=azure-cli).</span></span>

<span data-ttu-id="5a5be-153">Dobrą praktyką jest rotacja wpisów tajnych.</span><span class="sxs-lookup"><span data-stu-id="5a5be-153">As a best practice, periodically rotate the secrets.</span></span> <span data-ttu-id="5a5be-154">Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją wpisów tajnych](/azure/key-vault/secrets/).</span><span class="sxs-lookup"><span data-stu-id="5a5be-154">For more information, see [Secrets documentation](/azure/key-vault/secrets/).</span></span>

#### <a name="users"></a><span data-ttu-id="5a5be-155">Użytkownicy</span><span class="sxs-lookup"><span data-stu-id="5a5be-155">Users</span></span>

<span data-ttu-id="5a5be-156">Każde środowisko usługowe musi zawierać listę użytkowników, którzy mogą łączyć się z Dynamics 365 Finance i Dynamics 365 Supply Chain Management w funkcji Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="5a5be-156">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in Electronic invoicing.</span></span>

#### <a name="publication"></a><span data-ttu-id="5a5be-157">Publikacja</span><span class="sxs-lookup"><span data-stu-id="5a5be-157">Publication</span></span>

<span data-ttu-id="5a5be-158">Środowiska usług muszą zostać opublikowane w funkcji Fakturowanie elektroniczne, zanim będą mogły być używane.</span><span class="sxs-lookup"><span data-stu-id="5a5be-158">Service environments must be published to Electronic invoicing before they can be used.</span></span> <span data-ttu-id="5a5be-159">Finance i Supply Chain Management mają dostęp tylko do opublikowanych środowisk.</span><span class="sxs-lookup"><span data-stu-id="5a5be-159">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="5a5be-160">Ponadto środowisko usługi musi zostać opublikowane, zanim jakiekolwiek aktualizacje jego atrybutów zaczną obowiązywać w usłudze fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="5a5be-160">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="5a5be-161">Połączone aplikacje</span><span class="sxs-lookup"><span data-stu-id="5a5be-161">Connected applications</span></span>

<span data-ttu-id="5a5be-162">Połączone aplikacje to instancje Finance i Supply Chain Management, do których możesz chcieć dotrzeć za pośrednictwem RCS.</span><span class="sxs-lookup"><span data-stu-id="5a5be-162">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="5a5be-163">Oprócz adresu URL aplikacji i jej dzierżawy, połączona aplikacja zawiera poświadczenia, które umożliwiają RCS łączenie się ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="5a5be-163">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="5a5be-164">Za pomocą połączonych aplikacji można skonfigurować część funkcji fakturowania elektronicznego w rozwiązaniu Finance i Supply Chain Management, aby cała funkcja fakturowania elektronicznego działała.</span><span class="sxs-lookup"><span data-stu-id="5a5be-164">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="5a5be-165">Finance i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="5a5be-165">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="5a5be-166">Integracja z funkcją fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="5a5be-166">Integration with Electronic invoicing</span></span>

<span data-ttu-id="5a5be-167">Zanim będzie można używać programu Finance i Supply Chain Management do wystawiania faktur elektronicznych za pośrednictwem Fakturowania elektronicznego, dodatek musi być skonfigurowany tak, aby umożliwić komunikację z usługą.</span><span class="sxs-lookup"><span data-stu-id="5a5be-167">Before you can use Finance and Supply Chain Management to issue electronic invoices through Electronic invoicing, it must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-integration-feature"></a><span data-ttu-id="5a5be-168">Funkcja integracji fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="5a5be-168">Electronic invoicing integration feature</span></span>

<span data-ttu-id="5a5be-169">Aby umożliwić komunikację między rozwiązaniami Finance i Supply Chain Management a dodatkiem Fakturowanie elektroniczne, należy włączyć funkcję integracji **Fakturowanie elektroniczne** w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="5a5be-169">To enable communication between Finance and Supply Chain Management and Electronic invoicing, you must turn on the **Electronic Invoicing integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="5a5be-170">Punkt końcowy usługi</span><span class="sxs-lookup"><span data-stu-id="5a5be-170">Service endpoint</span></span>

<span data-ttu-id="5a5be-171">Punkt końcowy usługi to adres URL, w którym znajduje się Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="5a5be-171">The service endpoint is the URL where Electronic invoicing is located.</span></span> <span data-ttu-id="5a5be-172">Przed wystawieniem faktur elektronicznych należy skonfigurować punkt końcowy usługi w programie Finance i Supply Chain Management, aby umożliwić komunikację z usługą.</span><span class="sxs-lookup"><span data-stu-id="5a5be-172">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="5a5be-173">Aby skonfigurować punkt końcowy usługi, przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametr dokumentu elektronicznego**, a następnie na zakładce **Usługi przesyłania** w polu **Adres URL do fakturowania elektronicznego** wprowadź adres URL zgodnie z opisem w tabeli opisanej w sekcji **Punkt końcowy usługi**.</span><span class="sxs-lookup"><span data-stu-id="5a5be-173">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="5a5be-174">Środowiska</span><span class="sxs-lookup"><span data-stu-id="5a5be-174">Environments</span></span>

<span data-ttu-id="5a5be-175">Nazwa środowiska wprowadzona w Finance i Supply Chain Management odnosi się do nazwy środowiska utworzonego w RCS i opublikowanego w Fakturowaniu elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="5a5be-175">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to Electronic invoicing.</span></span>

<span data-ttu-id="5a5be-176">Środowisko należy skonfigurować na karcie **Usługi przesyłania** na stronie **Parametrów dokumentu elektronicznego**, tak aby każde żądanie wystawienia faktury elektronicznej zawierało środowisko, w którym Fakturowanie elektroniczne może określić, która funkcja fakturowania elektronicznego musi przetworzyć żądanie.</span><span class="sxs-lookup"><span data-stu-id="5a5be-176">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where Electronic invoicing can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5a5be-177">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5a5be-177">Additional resources</span></span>

- [<span data-ttu-id="5a5be-178">Skonfiguruj faktury elektroniczne w RCS</span><span class="sxs-lookup"><span data-stu-id="5a5be-178">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="5a5be-179">Wystawiaj faktury elektroniczne w Finance i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="5a5be-179">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
