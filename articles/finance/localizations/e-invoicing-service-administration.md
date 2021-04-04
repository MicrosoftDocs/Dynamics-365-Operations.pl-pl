---
title: Dodatkowe komponenty administracyjne do elektronicznego fakturowania
description: Ten temat zawiera informacje o składnikach związanych z administrowaniem dodatkiem Fakturowanie elektroniczne.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: 70ef47dd45200a14c9d780f3c280c554d0e52ac3
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592581"
---
# <a name="electronic-invoicing-add-on-administration-components"></a><span data-ttu-id="39611-103">Dodatkowe komponenty administracyjne do elektronicznego fakturowania</span><span class="sxs-lookup"><span data-stu-id="39611-103">Electronic invoicing add-on administration components</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="39611-104">Ten temat zawiera informacje o składnikach związanych z administrowaniem dodatkiem Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-104">This topic provides information about the components that are related to administration of the Electronic invoicing add-on.</span></span> <span data-ttu-id="39611-105">Zawiera również informacje o konfigurowaniu dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-105">It also provides information about how to configure the Electronic invoicing add-on service.</span></span>

## <a name="azure"></a><span data-ttu-id="39611-106">Azure</span><span class="sxs-lookup"><span data-stu-id="39611-106">Azure</span></span>

<span data-ttu-id="39611-107">Użyj Microsoft Azure, aby utworzyć wpisy tajne dla magazynu kluczy i konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="39611-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="39611-108">Następnie użyj tej funkcji w konfiguracji dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-108">Then use the secrets in the configuration of the Electronic invoicing add-on.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="39611-109">Usługa Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="39611-109">Lifecycle Services</span></span>

<span data-ttu-id="39611-110">Użyj Microsoft Dynamics Lifecycle Services (LCS), aby włączyć dodatek dla mikrousług dla projektu wdrożenia LCS.</span><span class="sxs-lookup"><span data-stu-id="39611-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the add-on for the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="39611-111">Instalacja dodatku mikrousługi w umacie LCS wymaga co najmniej maszyny wirtualnej warstwy 2.</span><span class="sxs-lookup"><span data-stu-id="39611-111">The installation of the microservice add-on in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="39611-112">Aby uzyskać więcej informacji o planowaniu w środowiskach, należy zapoznać się z tematem [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="39611-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="39611-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="39611-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="39611-114">Dynamics 365 Regulatory Configuration Services (RCS) to interfejs używany do konfigurowania dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure the Electronic invoicing add-on.</span></span> <span data-ttu-id="39611-115">Zasoby takie jak środowiska i funkcje fakturowania elektronicznego są tworzone, utrzymywane i hostowane w RCS.</span><span class="sxs-lookup"><span data-stu-id="39611-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="39611-116">Gdy zasoby są gotowe, są publikowane w usłudze dodatkowej Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-116">When the resources are ready, they are published to the Electronic invoicing add-on service.</span></span>

<span data-ttu-id="39611-117">Aby uzyskać informacje o rejestracji w RCS, zobacz temat [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="39611-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="39611-118">Aby uzyskać więcej informacji na temat RCS, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="39611-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="39611-119">Integracja z dodatkiem fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="39611-119">Integration with the Electronic invoicing add-on</span></span>

<span data-ttu-id="39611-120">Zanim będziesz mógł używać RCS do konfigurowania faktur elektronicznych, musisz skonfigurować RCS, aby umożliwić komunikację z dodatkiem Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with the Electronic invoicing add-on.</span></span> <span data-ttu-id="39611-121">Tę konfigurację można ukończyć na karcie **Dodatek Fakturowanie elektroniczne** na stronie **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="39611-121">You complete this configuration on the **Electronic invoicing add-on** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="39611-122">Punkt końcowy usługi</span><span class="sxs-lookup"><span data-stu-id="39611-122">Service endpoint</span></span>

<span data-ttu-id="39611-123">Dodatek Fakturowanie elektroniczne jest dostępny w kilku lokalizacjach geograficznych centrów danych platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="39611-123">The Electronic invoicing add-on is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="39611-124">W poniższej tabeli przedstawiono dostępność według regionów.</span><span class="sxs-lookup"><span data-stu-id="39611-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="39611-125">Geografia centrum danych platformy Azure</span><span class="sxs-lookup"><span data-stu-id="39611-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="39611-126">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="39611-126">East US</span></span>                    |
| <span data-ttu-id="39611-127">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="39611-127">West US</span></span>                    |
| <span data-ttu-id="39611-128">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="39611-128">North EU</span></span>                   |
| <span data-ttu-id="39611-129">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="39611-129">West EU</span></span>                    |

### <a name="service-environments"></a><span data-ttu-id="39611-130">Środowiska usługi</span><span class="sxs-lookup"><span data-stu-id="39611-130">Service environments</span></span>

<span data-ttu-id="39611-131">Środowiska usług to partycje logiczne utworzone w celu obsługi funkcji fakturowania elektronicznego w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in the Electronic invoicing add-on.</span></span> <span data-ttu-id="39611-132">Klucze tajne zabezpieczeń i certyfikaty cyfrowe oraz ład (czyli uprawnienia dostępu) należy skonfigurować na poziomie środowiska usługi.</span><span class="sxs-lookup"><span data-stu-id="39611-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="39611-133">Klienci mogą tworzyć dowolną liczbę środowisk usługowych.</span><span class="sxs-lookup"><span data-stu-id="39611-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="39611-134">Wszystkie środowiska usług, które tworzy klient, są od siebie niezależne.</span><span class="sxs-lookup"><span data-stu-id="39611-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="39611-135">Środowiska usługowe muszą być tworzone i utrzymywane w RCS.</span><span class="sxs-lookup"><span data-stu-id="39611-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="39611-136">Gdy środowiska usług są gotowe, należy je opublikować w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-136">When the service environments are ready, they must be published to the Electronic invoicing add-on.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="39611-137">Stan środowiska usługi</span><span class="sxs-lookup"><span data-stu-id="39611-137">Service environment status</span></span>

<span data-ttu-id="39611-138">Środowiskami usług można zarządzać za pomocą stanu.</span><span class="sxs-lookup"><span data-stu-id="39611-138">Service environments can be managed through status.</span></span> <span data-ttu-id="39611-139">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="39611-139">The possible options are:</span></span>

- <span data-ttu-id="39611-140">**Nie opublikowano** — środowisko zostało utworzone, ale nie zostało jeszcze opublikowane.</span><span class="sxs-lookup"><span data-stu-id="39611-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="39611-141">**Opublikowano** — środowisko zostało opublikowane w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-141">**Published** – The environment has been published to the Electronic invoicing add-on.</span></span>
- <span data-ttu-id="39611-142">**Zmienione** — Atrybuty opublikowanego środowiska zostały zmienione, ale zmiany nie zostały jeszcze opublikowane.</span><span class="sxs-lookup"><span data-stu-id="39611-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="39611-143">Tajemnice odbiorców</span><span class="sxs-lookup"><span data-stu-id="39611-143">Customer secrets</span></span>

<span data-ttu-id="39611-144">Usługa dodatkowa Fakturowanie elektroniczne jest odpowiedzialna za przechowywanie wszystkich danych biznesowych w zasobach platformy Azure należących do Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="39611-144">The Electronic invoicing add-on service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="39611-145">Aby upewnić się, że usługa działa poprawnie i że wszystkie dane biznesowe, które są potrzebne i generowane przez dodatek Faktury elektroniczne, są dostępne tylko dla tego dodatku, musisz utworzyć dwa główne zasoby platformy Azure:</span><span class="sxs-lookup"><span data-stu-id="39611-145">To ensure that the service works correctly, and that all the business data that is required for and generated by the Electronic invoicing add-on is accessed only by the add-on, you must create two main Azure resources:</span></span>

- <span data-ttu-id="39611-146">Konto magazynu systemu Azure (magazyn obiektów BLOB) do przechowywania faktur elektronicznych</span><span class="sxs-lookup"><span data-stu-id="39611-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="39611-147">Magazyn kluczy platformy Azure, w którym będą przechowywane certyfikaty i jednolity identyfikator zasobów (URI) konta magazynu</span><span class="sxs-lookup"><span data-stu-id="39611-147">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="39611-148">Dedykowany magazyn kluczy i konto magazynu klienta muszą być przydzielone specjalnie do użytku z dodatkiem Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-148">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing add-on.</span></span>

<span data-ttu-id="39611-149">Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="39611-149">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="39611-150">Użytkownicy</span><span class="sxs-lookup"><span data-stu-id="39611-150">Users</span></span>

<span data-ttu-id="39611-151">Każde środowisko usługowe musi zawierać listę użytkowników, którzy mogą łączyć się z Dynamics 365 Finance i Dynamics 365 Supply Chain Management w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-151">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in the Electronic invoicing add-on.</span></span>

#### <a name="publication"></a><span data-ttu-id="39611-152">Publikacja</span><span class="sxs-lookup"><span data-stu-id="39611-152">Publication</span></span>

<span data-ttu-id="39611-153">Środowiska usług muszą zostać opublikowane w dodatku Fakturowanie elektroniczne, zanim będą mogły być używane.</span><span class="sxs-lookup"><span data-stu-id="39611-153">Service environments must be published to the Electronic invoicing add-on before they can be used.</span></span> <span data-ttu-id="39611-154">Finance i Supply Chain Management mają dostęp tylko do opublikowanych środowisk.</span><span class="sxs-lookup"><span data-stu-id="39611-154">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="39611-155">Ponadto środowisko usługi musi zostać opublikowane, zanim jakiekolwiek aktualizacje jego atrybutów zaczną obowiązywać w usłudze fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="39611-155">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="39611-156">Połączone aplikacje</span><span class="sxs-lookup"><span data-stu-id="39611-156">Connected applications</span></span>

<span data-ttu-id="39611-157">Połączone aplikacje to instancje Finance i Supply Chain Management, do których możesz chcieć dotrzeć za pośrednictwem RCS.</span><span class="sxs-lookup"><span data-stu-id="39611-157">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="39611-158">Oprócz adresu URL aplikacji i jej dzierżawy, połączona aplikacja zawiera poświadczenia, które umożliwiają RCS łączenie się ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="39611-158">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="39611-159">Za pomocą połączonych aplikacji można skonfigurować część funkcji fakturowania elektronicznego w rozwiązaniu Finance i Supply Chain Management, aby cała funkcja fakturowania elektronicznego działała.</span><span class="sxs-lookup"><span data-stu-id="39611-159">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="39611-160">Finance i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="39611-160">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing-add-on"></a><span data-ttu-id="39611-161">Integracja z dodatkiem fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="39611-161">Integration with Electronic invoicing add-on</span></span>

<span data-ttu-id="39611-162">Zanim będzie można używać programu Finance i Supply Chain Management do wystawiania faktur elektronicznych za pośrednictwem dodatku Fakturowanie elektroniczne, dodatek musi być skonfigurowany tak, aby umożliwić komunikację z usługą.</span><span class="sxs-lookup"><span data-stu-id="39611-162">Before you can use Finance and Supply Chain Management to issue electronic invoices through the Electronic invoicing add-on, the add-on must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="39611-163">Funkcja integracji dodatku elektronicznego fakturowania</span><span class="sxs-lookup"><span data-stu-id="39611-163">Electronic invoicing add-on integration feature</span></span>

<span data-ttu-id="39611-164">Aby umożliwić komunikację między rozwiązaniami Finance i Supply Chain Management a dodatkiem Fakturowanie elektroniczne, należy włączyć funkcję integracji dodatku **Fakturowanie elektroniczne** w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="39611-164">To enable communication between Finance and Supply Chain Management and the Electronic invoicing add-on, you must turn on the **Electronic Invoicing add-on integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="39611-165">Punkt końcowy usługi</span><span class="sxs-lookup"><span data-stu-id="39611-165">Service endpoint</span></span>

<span data-ttu-id="39611-166">Punkt końcowy usługi to adres URL, w którym znajduje się dodatek Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-166">The service endpoint is the URL where the Electronic invoicing add-on is located.</span></span> <span data-ttu-id="39611-167">Przed wystawieniem faktur elektronicznych należy skonfigurować punkt końcowy usługi w programie Finance i Supply Chain Management, aby umożliwić komunikację z usługą.</span><span class="sxs-lookup"><span data-stu-id="39611-167">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="39611-168">Aby skonfigurować punkt końcowy usługi, przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametr dokumentu elektronicznego**, a następnie na zakładce **Usługi przesyłania** w polu **Adres URL dodatku do fakturowania elektronicznego** wprowadź adres URL zgodnie z opisem w tabeli opisanej w sekcji **Punkt końcowy usługi**.</span><span class="sxs-lookup"><span data-stu-id="39611-168">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing add-on URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="39611-169">Środowiska</span><span class="sxs-lookup"><span data-stu-id="39611-169">Environments</span></span>

<span data-ttu-id="39611-170">Nazwa środowiska wprowadzona w Finance i Supply Chain Management odnosi się do nazwy środowiska utworzonego w RCS i opublikowanego w dodatku Fakturowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39611-170">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to the Electronic invoicing add-on.</span></span>

<span data-ttu-id="39611-171">Środowisko należy skonfigurować na karcie **Usługi przesyłania** na stronie **Parametrów dokumentu elektronicznego**, tak aby każde żądanie wystawienia faktury elektronicznej zawierało środowisko, w którym dodatek Fakturowanie elektroniczne może określić, która funkcja fakturowania elektronicznego musi przetworzyć żądanie.</span><span class="sxs-lookup"><span data-stu-id="39611-171">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where the Electronic invoicing add-on can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39611-172">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="39611-172">Additional resources</span></span>

- [<span data-ttu-id="39611-173">Skonfiguruj faktury elektroniczne w RCS</span><span class="sxs-lookup"><span data-stu-id="39611-173">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="39611-174">Wystawiaj faktury elektroniczne w Finance i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="39611-174">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
