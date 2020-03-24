---
title: Dodaj obsługę dla sieci dostarczania zawartości (CDN)
description: W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 23ac9d8844c2a8ae20bd316c40078319601a3a4d
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096732"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="3215b-103">Dodaj obsługę dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="3215b-103">Add support for a content delivery network (CDN)</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3215b-104">W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3215b-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="3215b-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="3215b-105">Overview</span></span>

<span data-ttu-id="3215b-106">Podczas konfigurowania środowiska e-Commerce w Dynamics 365 Commerce można skonfigurować je do pracy z usługą CDN.</span><span class="sxs-lookup"><span data-stu-id="3215b-106">When you set up an e-Commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="3215b-107">Domenę niestandardową można włączyć podczas procesu zastrzegania dla środowiska e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="3215b-107">Your custom domain can be enabled during the provisioning process for your e-Commerce environment.</span></span> <span data-ttu-id="3215b-108">Można również skorzystać z żądania usługi w celu skonfigurowania go po zakończeniu procesu zastrzegania.</span><span class="sxs-lookup"><span data-stu-id="3215b-108">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="3215b-109">Proces zastrzegania dla środowiska e-Commerce generuje nazwę hosta skojarzoną ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="3215b-109">The provisioning process for the e-Commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="3215b-110">Ta nazwa hosta ma następujący format: gdzie *e-commerce-tenant-name* jest nazwą Twojego środowiska:</span><span class="sxs-lookup"><span data-stu-id="3215b-110">This host name has the following format, where *e-commerce-tenant-name* is the name of your environment:</span></span>

<span data-ttu-id="3215b-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="3215b-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="3215b-112">Nazwa hosta lub punkt końcowy, który jest generowany podczas procesu zastrzegania, obsługuje certyfikat SSL (Secure Sockets Layer) tylko dla \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="3215b-112">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="3215b-113">Nie obsługuje on protokołu SSL dla domen niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="3215b-113">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="3215b-114">Dlatego należy zamknąć protokół SSL dla domen niestandardowych w sieci CDN i przekazać ruch z sieci CDN do nazwy hosta lub punktu końcowego, który został wygenerowany przez moduł Commerce.</span><span class="sxs-lookup"><span data-stu-id="3215b-114">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="3215b-115">Ponadto *statystyki* (pliki JavaScript lub kaskadowe arkusze stylów \[CSS\]) z modułu Commerce są doręczane z poziomu punktu końcowego, który jest generowany przez moduł Commerce wygenerowany (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="3215b-115">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="3215b-116">Statyczne dane mogą być buforowane tylko wtedy, gdy nazwa hosta lub punkt końcowy, który został wygenerowany przez moduł commerce, jest umieszczony za CDN.</span><span class="sxs-lookup"><span data-stu-id="3215b-116">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="3215b-117">Konfigurowanie systemu SSL</span><span class="sxs-lookup"><span data-stu-id="3215b-117">Set up SSL</span></span>

<span data-ttu-id="3215b-118">Aby zapewnić, że protokół SSL jest skonfigurowany, a statyczne są buforowane, należy skonfigurować sieć CDN w taki sposób, aby była skojarzona z nazwą hosta wygenerowaną przez moduł Commerce dla danego środowiska.</span><span class="sxs-lookup"><span data-stu-id="3215b-118">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="3215b-119">Ponadto należy buforować następujący wzorzec wyłącznie dla statycznych:</span><span class="sxs-lookup"><span data-stu-id="3215b-119">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="3215b-120">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="3215b-120">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="3215b-121">Po zainicjowaniu obsługi środowiska Commerce w dostarczonej niestandardowej domenie lub po dostarczeniu niestandardowej domeny środowiska za pomocą żądania obsługi, należy wskazać domenę niestandardową dla nazwy hosta lub punktu końcowego, który jest generowany przez moduł Commerce.</span><span class="sxs-lookup"><span data-stu-id="3215b-121">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="3215b-122">Jak wcześniej wspomniano, wygenerowana nazwa hosta lub punkt końcowy obsługuje certyfikat SSL tylko dla \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="3215b-122">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="3215b-123">Nie obsługuje on protokołu SSL dla domen niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="3215b-123">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="3215b-124">Usługi CDN</span><span class="sxs-lookup"><span data-stu-id="3215b-124">CDN services</span></span>

<span data-ttu-id="3215b-125">Ze środowiskiem Commerce można używać dowolnej usługi CDN.</span><span class="sxs-lookup"><span data-stu-id="3215b-125">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="3215b-126">Oto dwa przykłady:</span><span class="sxs-lookup"><span data-stu-id="3215b-126">Here are two examples:</span></span>

- <span data-ttu-id="3215b-127">**Microsoft Azure Front Door Service** — rozwiązanie usługi CDN sieci Azure.</span><span class="sxs-lookup"><span data-stu-id="3215b-127">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="3215b-128">Aby uzyskać więcej informacji o usługach Azure Front Door Service, zapoznaj sięz dokumentacją usługi [Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="3215b-128">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="3215b-129">**Akceleratordynamiczny witryny Akamai** — Aby uzyskać więcej informacji, należy zapoznać się z informacjami o [dynamicznym akceleratorze witryny](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="3215b-129">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="3215b-130">Ustawienia CDN</span><span class="sxs-lookup"><span data-stu-id="3215b-130">CDN setup</span></span>

<span data-ttu-id="3215b-131">Proces konfiguracji sieci CDN składa się z następujących ogólnych kroków:</span><span class="sxs-lookup"><span data-stu-id="3215b-131">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="3215b-132">Dodaj hosta frontonu</span><span class="sxs-lookup"><span data-stu-id="3215b-132">Add a front-end host.</span></span>
1. <span data-ttu-id="3215b-133">Skonfiguruj pulę zaplecza</span><span class="sxs-lookup"><span data-stu-id="3215b-133">Configure a back-end pool.</span></span>
1. <span data-ttu-id="3215b-134">Konfigurowanie reguł routingu i buforowania</span><span class="sxs-lookup"><span data-stu-id="3215b-134">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="3215b-135">Dodaj hosta frontonu.</span><span class="sxs-lookup"><span data-stu-id="3215b-135">Add a front-end host</span></span>

<span data-ttu-id="3215b-136">Można użyć dowolnej usługi CDN, ale z przykładu w tym temacie jest używana usługa Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="3215b-136">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="3215b-137">Aby uzyskać informacje na temat konfigurowania usługi Azure Front Door Service, odwiedź witrynę [Szybki start: Tworzenie drzwi frontowych dla globalnej aplikacji sieci Web o dużej dostępności](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="3215b-137">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a><span data-ttu-id="3215b-138">Skonfiguruj pulę zaplecza w usłudze Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="3215b-138">Configure a back-end pool in Azure Front Door Service</span></span>

<span data-ttu-id="3215b-139">Aby skonfigurować pulę zaplecza w usłudze Azure Front Door Service, wykonaj nastepujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3215b-139">To configure a back-end pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="3215b-140">Dodaj **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** do puli zaplecza jako hosta niestandardowego z pustym nagłówkiem hosta zaplecza końcowego.</span><span class="sxs-lookup"><span data-stu-id="3215b-140">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a back-end pool as a custom host that has an empty back-end host header.</span></span>
1. <span data-ttu-id="3215b-141">W obszarze **sondowanie kondycji** w polu **Ścieżka** wprowadź **/keepalive**.</span><span class="sxs-lookup"><span data-stu-id="3215b-141">Under **Health probes**, in the **Path** field, enter **/keepalive**.</span></span>
1. <span data-ttu-id="3215b-142">W polu **interwały (sekundy)** wprowadź wartość **255**.</span><span class="sxs-lookup"><span data-stu-id="3215b-142">In the **Intervals (seconds)** field, enter **255**.</span></span>
1. <span data-ttu-id="3215b-143">W obszarze **równoważenie obciążenia** pozostaw wartości domyślne.</span><span class="sxs-lookup"><span data-stu-id="3215b-143">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="3215b-144">Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie puli wewnętrznej bazy danych** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="3215b-144">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="3215b-146">Konfigurowanie reguł w usłudze Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="3215b-146">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="3215b-147">Aby skonfigurować regułę routingu w usłudze Azure Front Door Service, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3215b-147">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="3215b-148">Dodawanie reguły routingu.</span><span class="sxs-lookup"><span data-stu-id="3215b-148">Add a routing rule.</span></span>
1. <span data-ttu-id="3215b-149">W polu **Nazwa** wpisz **domyślna**.</span><span class="sxs-lookup"><span data-stu-id="3215b-149">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="3215b-150">W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="3215b-150">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="3215b-151">W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="3215b-151">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="3215b-152">W obszarze **wzory do dopasowania**, w górnym polu wprowadź wartość **/\***.</span><span class="sxs-lookup"><span data-stu-id="3215b-152">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="3215b-153">W obszarze **Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.</span><span class="sxs-lookup"><span data-stu-id="3215b-153">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="3215b-154">W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="3215b-154">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="3215b-155">W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**.</span><span class="sxs-lookup"><span data-stu-id="3215b-155">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="3215b-156">Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="3215b-156">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="3215b-157">Ustawienie opcji **Buforowanie** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="3215b-157">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="3215b-158">Aby skonfigurować regułę buforowania w usłudze Azure Front Door Service, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3215b-158">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="3215b-159">Dodawanie reguły buforowania.</span><span class="sxs-lookup"><span data-stu-id="3215b-159">Add a caching rule.</span></span>
1. <span data-ttu-id="3215b-160">W polu **Nazwa** wpisz **statystyki**.</span><span class="sxs-lookup"><span data-stu-id="3215b-160">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="3215b-161">W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="3215b-161">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="3215b-162">W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="3215b-162">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="3215b-163">W obszarze **wzory do dopasowania**, w górnym polu wprowadź wartość **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="3215b-163">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="3215b-164">W obszarze **Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.</span><span class="sxs-lookup"><span data-stu-id="3215b-164">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="3215b-165">W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="3215b-165">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="3215b-166">W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**.</span><span class="sxs-lookup"><span data-stu-id="3215b-166">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="3215b-167">Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="3215b-167">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="3215b-168">Ustawienie opcji **Buforowanie** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="3215b-168">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="3215b-169">W polu **Zachowanie buforowania ciągu zapytania** wybierz opcję **Buforuj każdy unikatowy adres URL**.</span><span class="sxs-lookup"><span data-stu-id="3215b-169">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="3215b-170">W grupie pól **kompresja dynamiczna** wybierz opcję **włączone**.</span><span class="sxs-lookup"><span data-stu-id="3215b-170">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="3215b-171">Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie reguły** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="3215b-171">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Onko dialogowe dodaj regułę](./media/CDN_CachingRule.png)

<span data-ttu-id="3215b-173">Po wdrożeniu początkowej konfiguracji należy dodać domenę niestandardową do konfiguracji usługi Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="3215b-173">After this initial configuration is deployed, you must add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="3215b-174">Aby dodać domenę niestandardową (na przykład `www.fabrikam.com`), należy skonfigurować nazwę kanoniczną (CNAME) dla domeny.</span><span class="sxs-lookup"><span data-stu-id="3215b-174">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="3215b-175">Na poniższej ilustracji przedstawiono okno dialogowe **Konfiguracja CNAME** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="3215b-175">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe konfiguracji CNAME](./media/CNAME_Configuration.png)

> [!NOTE]
> <span data-ttu-id="3215b-177">Jeśli domena, której będziesz używał, jest już aktywna i online, skontaktuj się z pomocą techniczną, aby włączyć tę domenę przy użyciu usługi Azure Front Door Service, aby skonfigurować test.</span><span class="sxs-lookup"><span data-stu-id="3215b-177">If the domain that you will use is already active and live, contact support to enable this domain with Azure Front Door Service to set up a test.</span></span>

<span data-ttu-id="3215b-178">Za pomocą usługi Azure Front Door Service można zarządzać certyfikatem lub można skorzystać z własnego certyfikatu dla domeny niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="3215b-178">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="3215b-179">Na poniższej ilustracji przedstawiono okno dialogowe **Niestandardowa domena HTTPS** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="3215b-179">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe domeny niestandardowej HTTPS](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="3215b-181">Sieć CDN powinna być teraz poprawnie skonfigurowana, aby można było jej używać z witryną Commerce.</span><span class="sxs-lookup"><span data-stu-id="3215b-181">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3215b-182">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3215b-182">Additional resources</span></span>

[<span data-ttu-id="3215b-183">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="3215b-183">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="3215b-184">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="3215b-184">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="3215b-185">Konfigurowanie kanału sklepu internetowego</span><span class="sxs-lookup"><span data-stu-id="3215b-185">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="3215b-186">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="3215b-186">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="3215b-187">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="3215b-187">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="3215b-188">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="3215b-188">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="3215b-189">Przekaż adresy URL przekierowań luzem</span><span class="sxs-lookup"><span data-stu-id="3215b-189">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="3215b-190">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="3215b-190">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="3215b-191">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="3215b-191">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="3215b-192">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="3215b-192">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="3215b-193">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="3215b-193">Enable location-based store detection</span></span>](enable-store-detection.md)
