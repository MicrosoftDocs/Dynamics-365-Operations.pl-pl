---
title: Dodaj obsługę dla sieci dostarczania zawartości (CDN)
description: W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d653b072eca134c765a5db5659b228648fc13c4a
ms.sourcegitcommit: 3fe4d9a33447aa8a62d704fbbf18aeb9cb667baa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2021
ms.locfileid: "5582726"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="739c0-103">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="739c0-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="739c0-104">W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="739c0-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="739c0-105">Podczas konfigurowania środowiska e-Commerce w Dynamics 365 Commerce można skonfigurować je do pracy z usługą CDN.</span><span class="sxs-lookup"><span data-stu-id="739c0-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="739c0-106">Domenę niestandardową można włączyć podczas procesu zastrzegania dla środowiska e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="739c0-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="739c0-107">Można również skorzystać z żądania usługi w celu skonfigurowania go po zakończeniu procesu zastrzegania.</span><span class="sxs-lookup"><span data-stu-id="739c0-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="739c0-108">Proces zastrzegania dla środowiska e-Commerce generuje nazwę hosta skojarzoną ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="739c0-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="739c0-109">Ta nazwa hosta ma następujący format: gdzie \<*e-commerce-tenant-name*\> jest nazwą Twojego środowiska:</span><span class="sxs-lookup"><span data-stu-id="739c0-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="739c0-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="739c0-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="739c0-111">Nazwa hosta lub punkt końcowy, który jest generowany podczas procesu zastrzegania, obsługuje certyfikat SSL (Secure Sockets Layer) tylko dla \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="739c0-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="739c0-112">Nie obsługuje on protokołu SSL dla domen niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="739c0-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="739c0-113">Dlatego należy zamknąć protokół SSL dla domen niestandardowych w sieci CDN i przekazać ruch z sieci CDN do nazwy hosta lub punktu końcowego, który został wygenerowany przez moduł Commerce.</span><span class="sxs-lookup"><span data-stu-id="739c0-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="739c0-114">Ponadto *statystyki* (pliki JavaScript lub kaskadowe arkusze stylów \[CSS\]) z modułu Commerce są doręczane z poziomu punktu końcowego, który jest generowany przez moduł Commerce wygenerowany (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="739c0-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="739c0-115">Statyczne dane mogą być buforowane tylko wtedy, gdy nazwa hosta lub punkt końcowy, który został wygenerowany przez moduł commerce, jest umieszczony za CDN.</span><span class="sxs-lookup"><span data-stu-id="739c0-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="739c0-116">Konfigurowanie systemu SSL</span><span class="sxs-lookup"><span data-stu-id="739c0-116">Set up SSL</span></span>

<span data-ttu-id="739c0-117">Aby zapewnić, że protokół SSL jest skonfigurowany, a statyczne są buforowane, należy skonfigurować sieć CDN w taki sposób, aby była skojarzona z nazwą hosta wygenerowaną przez moduł Commerce dla danego środowiska.</span><span class="sxs-lookup"><span data-stu-id="739c0-117">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="739c0-118">Ponadto należy buforować następujący wzorzec wyłącznie dla statycznych:</span><span class="sxs-lookup"><span data-stu-id="739c0-118">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="739c0-119">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="739c0-119">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="739c0-120">Po zainicjowaniu obsługi środowiska Commerce w dostarczonej niestandardowej domenie lub po dostarczeniu niestandardowej domeny środowiska za pomocą żądania obsługi, należy wskazać domenę niestandardową dla nazwy hosta lub punktu końcowego, który jest generowany przez moduł Commerce.</span><span class="sxs-lookup"><span data-stu-id="739c0-120">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="739c0-121">Jak wcześniej wspomniano, wygenerowana nazwa hosta lub punkt końcowy obsługuje certyfikat SSL tylko dla \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="739c0-121">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="739c0-122">Nie obsługuje on protokołu SSL dla domen niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="739c0-122">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="739c0-123">Usługi CDN</span><span class="sxs-lookup"><span data-stu-id="739c0-123">CDN services</span></span>

<span data-ttu-id="739c0-124">Ze środowiskiem Commerce można używać dowolnej usługi CDN.</span><span class="sxs-lookup"><span data-stu-id="739c0-124">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="739c0-125">Oto dwa przykłady:</span><span class="sxs-lookup"><span data-stu-id="739c0-125">Here are two examples:</span></span>

- <span data-ttu-id="739c0-126">**Microsoft Azure Front Door Service** — rozwiązanie usługi CDN sieci Azure.</span><span class="sxs-lookup"><span data-stu-id="739c0-126">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="739c0-127">Aby uzyskać więcej informacji o usługach Azure Front Door Service, zapoznaj sięz dokumentacją usługi [Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="739c0-127">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="739c0-128">**Akceleratordynamiczny witryny Akamai** — Aby uzyskać więcej informacji, należy zapoznać się z informacjami o [dynamicznym akceleratorze witryny](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="739c0-128">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="739c0-129">Ustawienia CDN</span><span class="sxs-lookup"><span data-stu-id="739c0-129">CDN setup</span></span>

<span data-ttu-id="739c0-130">Proces konfiguracji sieci CDN składa się z następujących ogólnych kroków:</span><span class="sxs-lookup"><span data-stu-id="739c0-130">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="739c0-131">Dodaj hosta frontonu</span><span class="sxs-lookup"><span data-stu-id="739c0-131">Add a front-end host.</span></span>
1. <span data-ttu-id="739c0-132">Skonfiguruj pulę zaplecza.</span><span class="sxs-lookup"><span data-stu-id="739c0-132">Configure a backend pool.</span></span>
1. <span data-ttu-id="739c0-133">Konfigurowanie reguł routingu i buforowania</span><span class="sxs-lookup"><span data-stu-id="739c0-133">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="739c0-134">Dodaj hosta frontonu.</span><span class="sxs-lookup"><span data-stu-id="739c0-134">Add a front-end host</span></span>

<span data-ttu-id="739c0-135">Można użyć dowolnej usługi CDN, ale z przykładu w tym temacie jest używana usługa Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="739c0-135">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="739c0-136">Aby uzyskać informacje na temat konfigurowania usługi Azure Front Door Service, odwiedź witrynę [Szybki start: Tworzenie drzwi frontowych dla globalnej aplikacji sieci Web o dużej dostępności](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="739c0-136">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="739c0-137">Skonfiguruj pulę zaplecza w usłudze Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="739c0-137">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="739c0-138">Aby skonfigurować pulę zaplecza w usłudze Azure Front Door Service, wykonaj nastepujące kroki.</span><span class="sxs-lookup"><span data-stu-id="739c0-138">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="739c0-139">Dodaj **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** do puli zaplecza jako hosta niestandardowego z pustym nagłówkiem hosta zaplecza końcowego.</span><span class="sxs-lookup"><span data-stu-id="739c0-139">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has an empty backend host header.</span></span>
1. <span data-ttu-id="739c0-140">W obszarze **równoważenie obciążenia** pozostaw wartości domyślne.</span><span class="sxs-lookup"><span data-stu-id="739c0-140">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="739c0-141">Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie zaplecza** w usłudze Azure Front Door Service z podaną nazwą hosta zaplecza.</span><span class="sxs-lookup"><span data-stu-id="739c0-141">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool.png)

<span data-ttu-id="739c0-143">Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie puli zaplecza** w usłudze Azure Front Door Service z domyślnymi wartościami równoważenia obciążenia.</span><span class="sxs-lookup"><span data-stu-id="739c0-143">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Kontynuacja Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="739c0-145">Konfigurowanie reguł w usłudze Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="739c0-145">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="739c0-146">Aby skonfigurować regułę routingu w usłudze Azure Front Door Service, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="739c0-146">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="739c0-147">Dodawanie reguły routingu.</span><span class="sxs-lookup"><span data-stu-id="739c0-147">Add a routing rule.</span></span>
1. <span data-ttu-id="739c0-148">W polu **Nazwa** wpisz **domyślna**.</span><span class="sxs-lookup"><span data-stu-id="739c0-148">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="739c0-149">W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="739c0-149">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="739c0-150">W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="739c0-150">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="739c0-151">W obszarze **wzory do dopasowania**, w górnym polu wprowadź wartość **/\***.</span><span class="sxs-lookup"><span data-stu-id="739c0-151">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="739c0-152">W obszarze **Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.</span><span class="sxs-lookup"><span data-stu-id="739c0-152">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="739c0-153">W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="739c0-153">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="739c0-154">W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**.</span><span class="sxs-lookup"><span data-stu-id="739c0-154">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="739c0-155">Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="739c0-155">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="739c0-156">Ustawienie opcji **Buforowanie** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="739c0-156">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="739c0-157">Aby skonfigurować regułę buforowania w usłudze Azure Front Door Service, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="739c0-157">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="739c0-158">Dodawanie reguły buforowania.</span><span class="sxs-lookup"><span data-stu-id="739c0-158">Add a caching rule.</span></span>
1. <span data-ttu-id="739c0-159">W polu **Nazwa** wpisz **statystyki**.</span><span class="sxs-lookup"><span data-stu-id="739c0-159">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="739c0-160">W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="739c0-160">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="739c0-161">W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="739c0-161">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="739c0-162">W obszarze **wzory do dopasowania**, w górnym polu wprowadź wartość **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="739c0-162">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="739c0-163">W obszarze **Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.</span><span class="sxs-lookup"><span data-stu-id="739c0-163">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="739c0-164">W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="739c0-164">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="739c0-165">W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**.</span><span class="sxs-lookup"><span data-stu-id="739c0-165">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="739c0-166">Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="739c0-166">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="739c0-167">Ustawienie opcji **Buforowanie** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="739c0-167">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="739c0-168">W polu **Zachowanie buforowania ciągu zapytania** wybierz opcję **Buforuj każdy unikatowy adres URL**.</span><span class="sxs-lookup"><span data-stu-id="739c0-168">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="739c0-169">W grupie pól **kompresja dynamiczna** wybierz opcję **włączone**.</span><span class="sxs-lookup"><span data-stu-id="739c0-169">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="739c0-170">Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie reguły** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="739c0-170">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Onko dialogowe dodaj regułę](./media/CDN_CachingRule.png)

> [!WARNING]
> <span data-ttu-id="739c0-172">Jeśli domena, której będziesz korzystać, jest już aktywna i na żywo, Utwórz bilet pomocy technicznej na kafelku **Pomocy technicznej** w usłudze [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/), aby uzyskać pomoc w następnych etapach.</span><span class="sxs-lookup"><span data-stu-id="739c0-172">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="739c0-173">Aby uzyskać więcej informacji, przejrzyj temat [Uzyskaj pomoc techniczną dla aplikacji Finance and Operations lub usług Lifecycle Services (usługi LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="739c0-173">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="739c0-174">Jeśli Twoja domena jest nowa i nie jest wcześniej istniejącą domeną aktywną, możesz dodać swoją domenę niestandardową do konfiguracji usługi Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="739c0-174">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="739c0-175">Umożliwi to kierowanie ruchu internetowego do Twojej witryny za pośrednictwem wystąpienia usługi Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="739c0-175">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="739c0-176">Aby dodać domenę niestandardową (na przykład `www.fabrikam.com`), należy skonfigurować nazwę kanoniczną (CNAME) dla domeny.</span><span class="sxs-lookup"><span data-stu-id="739c0-176">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="739c0-177">Na poniższej ilustracji przedstawiono okno dialogowe **Konfiguracja CNAME** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="739c0-177">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe konfiguracji CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="739c0-179">Za pomocą usługi Azure Front Door Service można zarządzać certyfikatem lub można skorzystać z własnego certyfikatu dla domeny niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="739c0-179">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="739c0-180">Na poniższej ilustracji przedstawiono okno dialogowe **Niestandardowa domena HTTPS** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="739c0-180">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe domeny niestandardowej HTTPS](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="739c0-182">Aby uzyskać szczegółowe instrukcje dotyczące dodawania domeny niestandardowej do Azure Front Door, zamieszczono w temacie [Dodawanie domeny niestandardowej do swoich Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="739c0-182">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="739c0-183">Sieć CDN powinna być teraz poprawnie skonfigurowana, aby można było jej używać z witryną Commerce.</span><span class="sxs-lookup"><span data-stu-id="739c0-183">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="739c0-184">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="739c0-184">Additional resources</span></span>

[<span data-ttu-id="739c0-185">Opcje implementacji sieci dostarczania zawartości</span><span class="sxs-lookup"><span data-stu-id="739c0-185">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
