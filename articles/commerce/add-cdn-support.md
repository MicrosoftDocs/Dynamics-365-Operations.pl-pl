---
title: Dodaj obsługę dla sieci dostarczania zawartości (CDN)
description: W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: fb757672fffb56892837c066d552773908dd1ec1
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696975"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="47deb-103">Dodaj obsługę dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="47deb-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="47deb-104">W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="47deb-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="47deb-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="47deb-105">Overview</span></span>

<span data-ttu-id="47deb-106">Podczas konfigurowania środowiska e-Commerce w Dynamics 365 Commerce można skonfigurować je do pracy z usługą CDN.</span><span class="sxs-lookup"><span data-stu-id="47deb-106">When you set up an e-Commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="47deb-107">Domenę niestandardową można włączyć podczas procesu zastrzegania dla środowiska e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="47deb-107">Your custom domain can be enabled during the provisioning process for your e-Commerce environment.</span></span> <span data-ttu-id="47deb-108">Można również skorzystać z żądania usługi w celu skonfigurowania go po zakończeniu procesu zastrzegania.</span><span class="sxs-lookup"><span data-stu-id="47deb-108">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="47deb-109">Proces zastrzegania dla środowiska e-Commerce generuje nazwę hosta skojarzoną ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="47deb-109">The provisioning process for the e-Commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="47deb-110">Ta nazwa hosta ma następujący format: gdzie *e-commerce-tenant-name* jest nazwą Twojego środowiska:</span><span class="sxs-lookup"><span data-stu-id="47deb-110">This host name has the following format, where *e-commerce-tenant-name* is the name of your environment:</span></span>

<span data-ttu-id="47deb-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="47deb-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="47deb-112">Nazwa hosta lub punkt końcowy, który jest generowany podczas procesu zastrzegania, obsługuje certyfikat SSL (Secure Sockets Layer) tylko dla \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="47deb-112">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="47deb-113">Nie obsługuje on protokołu SSL dla domen niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="47deb-113">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="47deb-114">Dlatego należy zamknąć protokół SSL dla domen niestandardowych w sieci CDN i przekazać ruch z sieci CDN do nazwy hosta lub punktu końcowego, który został wygenerowany przez moduł Commerce.</span><span class="sxs-lookup"><span data-stu-id="47deb-114">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="47deb-115">Ponadto *statystyki* (pliki JavaScript lub kaskadowe arkusze stylów \[CSS\]) z modułu Commerce są doręczane z poziomu punktu końcowego, który jest generowany przez moduł Commerce wygenerowany (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="47deb-115">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="47deb-116">Statyczne dane mogą być buforowane tylko wtedy, gdy nazwa hosta lub punkt końcowy, który został wygenerowany przez moduł commerce, jest umieszczony za CDN.</span><span class="sxs-lookup"><span data-stu-id="47deb-116">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="47deb-117">Konfigurowanie systemu SSL</span><span class="sxs-lookup"><span data-stu-id="47deb-117">Set up SSL</span></span>

<span data-ttu-id="47deb-118">Aby zapewnić, że protokół SSL jest skonfigurowany, a statyczne są buforowane, należy skonfigurować sieć CDN w taki sposób, aby była skojarzona z nazwą hosta wygenerowaną przez moduł Commerce dla danego środowiska.</span><span class="sxs-lookup"><span data-stu-id="47deb-118">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="47deb-119">Ponadto należy buforować następujący wzorzec wyłącznie dla statycznych:</span><span class="sxs-lookup"><span data-stu-id="47deb-119">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="47deb-120">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="47deb-120">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="47deb-121">Po zainicjowaniu obsługi środowiska Commerce w dostarczonej niestandardowej domenie lub po dostarczeniu niestandardowej domeny środowiska za pomocą żądania obsługi, należy wskazać domenę niestandardową dla nazwy hosta lub punktu końcowego, który jest generowany przez moduł Commerce.</span><span class="sxs-lookup"><span data-stu-id="47deb-121">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="47deb-122">Jak wcześniej wspomniano, wygenerowana nazwa hosta lub punkt końcowy obsługuje certyfikat SSL tylko dla \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="47deb-122">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="47deb-123">Nie obsługuje on protokołu SSL dla domen niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="47deb-123">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="47deb-124">Usługi CDN</span><span class="sxs-lookup"><span data-stu-id="47deb-124">CDN services</span></span>

<span data-ttu-id="47deb-125">Ze środowiskiem Commerce można używać dowolnej usługi CDN.</span><span class="sxs-lookup"><span data-stu-id="47deb-125">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="47deb-126">Oto dwa przykłady:</span><span class="sxs-lookup"><span data-stu-id="47deb-126">Here are two examples:</span></span>

- <span data-ttu-id="47deb-127">**Microsoft Azure Front Door Service** — rozwiązanie usługi CDN sieci Azure.</span><span class="sxs-lookup"><span data-stu-id="47deb-127">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="47deb-128">Aby uzyskać więcej informacji o usługach Azure Front Door Service, zapoznaj sięz dokumentacją usługi [Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="47deb-128">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="47deb-129">**Akceleratordynamiczny witryny Akamai** — Aby uzyskać więcej informacji, należy zapoznać się z informacjami o [dynamicznym akceleratorze witryny](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="47deb-129">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="47deb-130">Ustawienia CDN</span><span class="sxs-lookup"><span data-stu-id="47deb-130">CDN setup</span></span>

<span data-ttu-id="47deb-131">Proces konfiguracji sieci CDN składa się z następujących ogólnych kroków:</span><span class="sxs-lookup"><span data-stu-id="47deb-131">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="47deb-132">Dodaj hosta frontonu</span><span class="sxs-lookup"><span data-stu-id="47deb-132">Add a front-end host.</span></span>
1. <span data-ttu-id="47deb-133">Skonfiguruj pulę zaplecza</span><span class="sxs-lookup"><span data-stu-id="47deb-133">Configure a back-end pool.</span></span>
1. <span data-ttu-id="47deb-134">Konfigurowanie reguł routingu i buforowania</span><span class="sxs-lookup"><span data-stu-id="47deb-134">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="47deb-135">Dodaj hosta frontonu.</span><span class="sxs-lookup"><span data-stu-id="47deb-135">Add a front-end host</span></span>

<span data-ttu-id="47deb-136">Można użyć dowolnej usługi CDN, ale z przykładu w tym temacie jest używana usługa Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="47deb-136">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="47deb-137">Aby uzyskać informacje na temat konfigurowania usługi Azure Front Door Service, odwiedź witrynę [Szybki start: Tworzenie drzwi frontowych dla globalnej aplikacji sieci Web o dużej dostępności](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="47deb-137">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a><span data-ttu-id="47deb-138">Skonfiguruj pulę zaplecza w usłudze Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="47deb-138">Configure a back-end pool in Azure Front Door Service</span></span>

<span data-ttu-id="47deb-139">Aby skonfigurować pulę zaplecza w usłudze Azure Front Door Service, wykonaj nastepujące kroki.</span><span class="sxs-lookup"><span data-stu-id="47deb-139">To configure a back-end pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="47deb-140">Dodaj **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** do puli zaplecza jako hosta niestandardowego z pustym nagłówkiem hosta zaplecza końcowego.</span><span class="sxs-lookup"><span data-stu-id="47deb-140">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a back-end pool as a custom host that has an empty back-end host header.</span></span>
1. <span data-ttu-id="47deb-141">W obszarze **sondowanie kondycji** w polu **Ścieżka** wprowadź **/keepalive**.</span><span class="sxs-lookup"><span data-stu-id="47deb-141">Under **Health probes**, in the **Path** field, enter **/keepalive**.</span></span>
1. <span data-ttu-id="47deb-142">W polu **interwały (sekundy)** wprowadź wartość **255**.</span><span class="sxs-lookup"><span data-stu-id="47deb-142">In the **Intervals (seconds)** field, enter **255**.</span></span>
1. <span data-ttu-id="47deb-143">W obszarze **równoważenie obciążenia** pozostaw wartości domyślne.</span><span class="sxs-lookup"><span data-stu-id="47deb-143">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="47deb-144">Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie puli wewnętrznej bazy danych** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="47deb-144">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="47deb-146">Konfigurowanie reguł w usłudze Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="47deb-146">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="47deb-147">Aby skonfigurować regułę routingu w usłudze Azure Front Door Service, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="47deb-147">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="47deb-148">Dodawanie reguły routingu.</span><span class="sxs-lookup"><span data-stu-id="47deb-148">Add a routing rule.</span></span>
1. <span data-ttu-id="47deb-149">W polu **Nazwa** wpisz **domyślna**.</span><span class="sxs-lookup"><span data-stu-id="47deb-149">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="47deb-150">W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="47deb-150">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="47deb-151">W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="47deb-151">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="47deb-152">W obszarze **wzory do dopasowania**, w górnym polu wprowadź wartość **/\***.</span><span class="sxs-lookup"><span data-stu-id="47deb-152">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="47deb-153">W obszarze **Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.</span><span class="sxs-lookup"><span data-stu-id="47deb-153">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="47deb-154">W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="47deb-154">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="47deb-155">W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**.</span><span class="sxs-lookup"><span data-stu-id="47deb-155">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="47deb-156">Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="47deb-156">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="47deb-157">Ustawienie opcji **Buforowanie** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="47deb-157">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="47deb-158">Aby skonfigurować regułę buforowania w usłudze Azure Front Door Service, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="47deb-158">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="47deb-159">Dodawanie reguły buforowania.</span><span class="sxs-lookup"><span data-stu-id="47deb-159">Add a caching rule.</span></span>
1. <span data-ttu-id="47deb-160">W polu **Nazwa** wpisz **statystyki**.</span><span class="sxs-lookup"><span data-stu-id="47deb-160">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="47deb-161">W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="47deb-161">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="47deb-162">W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="47deb-162">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="47deb-163">W obszarze **wzory do dopasowania**, w górnym polu wprowadź wartość **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="47deb-163">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="47deb-164">W obszarze **Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.</span><span class="sxs-lookup"><span data-stu-id="47deb-164">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="47deb-165">W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="47deb-165">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="47deb-166">W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**.</span><span class="sxs-lookup"><span data-stu-id="47deb-166">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="47deb-167">Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="47deb-167">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="47deb-168">Ustawienie opcji **Buforowanie** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="47deb-168">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="47deb-169">W polu **Zachowanie buforowania ciągu zapytania** wybierz opcję **Buforuj każdy unikatowy adres URL**.</span><span class="sxs-lookup"><span data-stu-id="47deb-169">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="47deb-170">W grupie pól **kompresja dynamiczna** wybierz opcję **włączone**.</span><span class="sxs-lookup"><span data-stu-id="47deb-170">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="47deb-171">Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie reguły** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="47deb-171">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Onko dialogowe dodaj regułę](./media/CDN_CachingRule.png)

<span data-ttu-id="47deb-173">Po wdrożeniu początkowej konfiguracji należy dodać domenę niestandardową do konfiguracji usługi Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="47deb-173">After this initial configuration is deployed, you must add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="47deb-174">Aby dodać domenę niestandardową (na przykład `www.fabrikam.com`), należy skonfigurować nazwę kanoniczną (CNAME) dla domeny.</span><span class="sxs-lookup"><span data-stu-id="47deb-174">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="47deb-175">Na poniższej ilustracji przedstawiono okno dialogowe **Konfiguracja CNAME** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="47deb-175">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe konfiguracji CNAME](./media/CNAME_Configuration.png)

> [!NOTE]
> <span data-ttu-id="47deb-177">Jeśli domena, której będziesz używał, jest już aktywna i online, skontaktuj się z pomocą techniczną, aby włączyć tę domenę przy użyciu usługi Azure Front Door Service, aby skonfigurować test.</span><span class="sxs-lookup"><span data-stu-id="47deb-177">If the domain that you will use is already active and live, contact support to enable this domain with Azure Front Door Service to set up a test.</span></span>

<span data-ttu-id="47deb-178">Za pomocą usługi Azure Front Door Service można zarządzać certyfikatem lub można skorzystać z własnego certyfikatu dla domeny niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="47deb-178">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="47deb-179">Na poniższej ilustracji przedstawiono okno dialogowe **Niestandardowa domena HTTPS** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="47deb-179">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe domeny niestandardowej HTTPS](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="47deb-181">Sieć CDN powinna być teraz poprawnie skonfigurowana, aby można było jej używać z witryną Commerce.</span><span class="sxs-lookup"><span data-stu-id="47deb-181">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="47deb-182">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="47deb-182">Additional resources</span></span>

[<span data-ttu-id="47deb-183">Omówienie sklepu internetowego</span><span class="sxs-lookup"><span data-stu-id="47deb-183">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="47deb-184">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="47deb-184">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="47deb-185">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="47deb-185">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="47deb-186">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="47deb-186">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="47deb-187">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="47deb-187">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="47deb-188">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="47deb-188">Enable location-based store detection</span></span>](enable-store-detection.md)

[<span data-ttu-id="47deb-189">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="47deb-189">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
