---
title: Dodaj obsługę dla sieci dostarczania zawartości (CDN)
description: W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 59277323e0995f59d3a451395a038fa3708274eb
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936837"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="1512d-103">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="1512d-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1512d-104">W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1512d-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="1512d-105">Podczas konfigurowania środowiska e-Commerce w Dynamics 365 Commerce można skonfigurować je do pracy z usługą CDN.</span><span class="sxs-lookup"><span data-stu-id="1512d-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="1512d-106">Domenę niestandardową można włączyć podczas procesu zastrzegania dla środowiska e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="1512d-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="1512d-107">Można również skorzystać z żądania usługi w celu skonfigurowania go po zakończeniu procesu zastrzegania.</span><span class="sxs-lookup"><span data-stu-id="1512d-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="1512d-108">Proces zastrzegania dla środowiska e-Commerce generuje nazwę hosta skojarzoną ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="1512d-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="1512d-109">Ta nazwa hosta ma następujący format: gdzie \<*e-commerce-tenant-name*\> jest nazwą Twojego środowiska:</span><span class="sxs-lookup"><span data-stu-id="1512d-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="1512d-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="1512d-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="1512d-111">Nazwa hosta lub punkt końcowy, który jest generowany podczas procesu zastrzegania, obsługuje certyfikat SSL (Secure Sockets Layer) tylko dla \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="1512d-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="1512d-112">Nie obsługuje on protokołu SSL dla domen niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="1512d-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="1512d-113">Dlatego należy zamknąć protokół SSL dla domen niestandardowych w sieci CDN i przekazać ruch z sieci CDN do nazwy hosta lub punktu końcowego, który został wygenerowany przez moduł Commerce.</span><span class="sxs-lookup"><span data-stu-id="1512d-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="1512d-114">Ponadto *statystyki* (pliki JavaScript lub kaskadowe arkusze stylów \[CSS\]) z modułu Commerce są doręczane z poziomu punktu końcowego, który jest generowany przez moduł Commerce wygenerowany (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="1512d-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="1512d-115">Statyczne dane mogą być buforowane tylko wtedy, gdy nazwa hosta lub punkt końcowy, który został wygenerowany przez moduł commerce, jest umieszczony za CDN.</span><span class="sxs-lookup"><span data-stu-id="1512d-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="1512d-116">Ustaw format SSL</span><span class="sxs-lookup"><span data-stu-id="1512d-116">Set up SSL</span></span>

<span data-ttu-id="1512d-117">Po zainicjowaniu obsługi środowiska Commerce w dostarczonej niestandardowej domenie lub po dostarczeniu niestandardowej domeny środowiska za pomocą żądania obsługi, należy współpracować z zespołem wprowadzającym Commerce w celu zaplanowania zmian w systemie DNS.</span><span class="sxs-lookup"><span data-stu-id="1512d-117">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, you need to work with the Commerce onboarding team to plan the DNS changes.</span></span>

<span data-ttu-id="1512d-118">Jak wcześniej wspomniano, wygenerowana nazwa hosta lub punkt końcowy obsługuje certyfikat SSL tylko dla \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="1512d-118">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="1512d-119">Nie obsługuje on protokołu SSL dla domen niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="1512d-119">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="1512d-120">Usługi CDN</span><span class="sxs-lookup"><span data-stu-id="1512d-120">CDN services</span></span>

<span data-ttu-id="1512d-121">Ze środowiskiem Commerce można używać dowolnej usługi CDN.</span><span class="sxs-lookup"><span data-stu-id="1512d-121">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="1512d-122">Oto dwa przykłady:</span><span class="sxs-lookup"><span data-stu-id="1512d-122">Here are two examples:</span></span>

- <span data-ttu-id="1512d-123">**Microsoft Azure Front Door Service** — rozwiązanie usługi CDN sieci Azure.</span><span class="sxs-lookup"><span data-stu-id="1512d-123">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="1512d-124">Aby uzyskać więcej informacji o usługach Azure Front Door Service, zapoznaj sięz dokumentacją usługi [Azure Front Door Service](/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="1512d-124">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](/azure/frontdoor/).</span></span>
- <span data-ttu-id="1512d-125">**Akceleratordynamiczny witryny Akamai** — Aby uzyskać więcej informacji, należy zapoznać się z informacjami o [dynamicznym akceleratorze witryny](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="1512d-125">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="1512d-126">Ustawienia CDN</span><span class="sxs-lookup"><span data-stu-id="1512d-126">CDN setup</span></span>

<span data-ttu-id="1512d-127">Proces konfiguracji sieci CDN składa się z następujących ogólnych kroków:</span><span class="sxs-lookup"><span data-stu-id="1512d-127">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="1512d-128">Dodaj hosta frontonu</span><span class="sxs-lookup"><span data-stu-id="1512d-128">Add a front-end host.</span></span>
1. <span data-ttu-id="1512d-129">Skonfiguruj pulę zaplecza.</span><span class="sxs-lookup"><span data-stu-id="1512d-129">Configure a backend pool.</span></span>
1. <span data-ttu-id="1512d-130">Konfigurowanie reguł wyboru trasy.</span><span class="sxs-lookup"><span data-stu-id="1512d-130">Set up rules for routing.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="1512d-131">Dodaj hosta frontonu.</span><span class="sxs-lookup"><span data-stu-id="1512d-131">Add a front-end host</span></span>

<span data-ttu-id="1512d-132">Można użyć dowolnej usługi CDN, ale z przykładu w tym temacie jest używana usługa Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="1512d-132">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="1512d-133">Aby uzyskać informacje na temat konfigurowania usługi Azure Front Door Service, odwiedź witrynę [Szybki start: Tworzenie drzwi frontowych dla globalnej aplikacji sieci Web o dużej dostępności](/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="1512d-133">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="1512d-134">Skonfiguruj pulę zaplecza w usłudze Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="1512d-134">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="1512d-135">Aby skonfigurować pulę zaplecza w usłudze Azure Front Door Service, wykonaj nastepujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1512d-135">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="1512d-136">Dodaj **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** do puli wewnętrznej bazy danych jako niestandardowego hosta, który ma nagłówek hosta wewnętrznej bazy danych, który jest taki sam jak **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="1512d-136">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has a backend host header that is the same as **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span></span>
1. <span data-ttu-id="1512d-137">W obszarze **równoważenie obciążenia** pozostaw wartości domyślne.</span><span class="sxs-lookup"><span data-stu-id="1512d-137">Under **Load balancing**, leave the default values.</span></span>
1. <span data-ttu-id="1512d-138">Wyłącz testy kondycji dla puli wewnętrznej bazy danych.</span><span class="sxs-lookup"><span data-stu-id="1512d-138">Disable health checks for the backend pool.</span></span>

<span data-ttu-id="1512d-139">Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie zaplecza** w usłudze Azure Front Door Service z podaną nazwą hosta zaplecza.</span><span class="sxs-lookup"><span data-stu-id="1512d-139">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool.png)

<span data-ttu-id="1512d-141">Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie puli zaplecza** w usłudze Azure Front Door Service z domyślnymi wartościami równoważenia obciążenia.</span><span class="sxs-lookup"><span data-stu-id="1512d-141">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Kontynuacja Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool_2.png)

> [!NOTE]
> <span data-ttu-id="1512d-143">Pamiętaj, aby wyłączyć **Sondy kondycji** podczas konfigurowania własnej usługi Azure Front Door dla handlu.</span><span class="sxs-lookup"><span data-stu-id="1512d-143">Be sure to disable **Health Probes** when setting up your own Azure Front Door service for Commerce.</span></span>


### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="1512d-144">Konfigurowanie reguł w usłudze Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="1512d-144">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="1512d-145">Aby skonfigurować regułę routingu w usłudze Azure Front Door Service, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1512d-145">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="1512d-146">Dodawanie reguły routingu.</span><span class="sxs-lookup"><span data-stu-id="1512d-146">Add a routing rule.</span></span>
1. <span data-ttu-id="1512d-147">W polu **Nazwa** wpisz **domyślna**.</span><span class="sxs-lookup"><span data-stu-id="1512d-147">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="1512d-148">W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="1512d-148">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="1512d-149">W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="1512d-149">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="1512d-150">W obszarze **wzory do dopasowania**, w górnym polu wprowadź wartość **/\***.</span><span class="sxs-lookup"><span data-stu-id="1512d-150">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="1512d-151">W obszarze **Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.</span><span class="sxs-lookup"><span data-stu-id="1512d-151">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="1512d-152">W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="1512d-152">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="1512d-153">W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**.</span><span class="sxs-lookup"><span data-stu-id="1512d-153">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="1512d-154">Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="1512d-154">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="1512d-155">Ustawienie opcji **Buforowanie** na **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="1512d-155">Set the **Caching** option to **Disabled**.</span></span>


> [!WARNING]
> <span data-ttu-id="1512d-156">Jeśli domena, której będziesz korzystać, jest już aktywna i na żywo, Utwórz bilet pomocy technicznej na kafelku **Pomocy technicznej** w usłudze [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/), aby uzyskać pomoc w następnych etapach.</span><span class="sxs-lookup"><span data-stu-id="1512d-156">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="1512d-157">Aby uzyskać więcej informacji, przejrzyj temat [Uzyskaj pomoc techniczną dla aplikacji Finance and Operations lub usług Lifecycle Services (usługi LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="1512d-157">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="1512d-158">Jeśli Twoja domena jest nowa i nie jest wcześniej istniejącą domeną aktywną, możesz dodać swoją domenę niestandardową do konfiguracji usługi Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="1512d-158">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="1512d-159">Umożliwi to kierowanie ruchu internetowego do Twojej witryny za pośrednictwem wystąpienia usługi Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="1512d-159">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="1512d-160">Aby dodać domenę niestandardową (na przykład `www.fabrikam.com`), należy skonfigurować nazwę kanoniczną (CNAME) dla domeny.</span><span class="sxs-lookup"><span data-stu-id="1512d-160">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="1512d-161">Na poniższej ilustracji przedstawiono okno dialogowe **Konfiguracja CNAME** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="1512d-161">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe konfiguracji CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="1512d-163">Za pomocą usługi Azure Front Door Service można zarządzać certyfikatem lub można skorzystać z własnego certyfikatu dla domeny niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="1512d-163">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="1512d-164">Na poniższej ilustracji przedstawiono okno dialogowe **Niestandardowa domena HTTPS** w usłudze Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="1512d-164">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Okno dialogowe domeny niestandardowej HTTPS](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="1512d-166">Aby uzyskać szczegółowe instrukcje dotyczące dodawania domeny niestandardowej do Azure Front Door, zamieszczono w temacie [Dodawanie domeny niestandardowej do swoich Front Door](/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="1512d-166">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="1512d-167">Sieć CDN powinna być teraz poprawnie skonfigurowana, aby można było jej używać z witryną Commerce.</span><span class="sxs-lookup"><span data-stu-id="1512d-167">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1512d-168">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1512d-168">Additional resources</span></span>

[<span data-ttu-id="1512d-169">Opcje implementacji sieci dostarczania zawartości</span><span class="sxs-lookup"><span data-stu-id="1512d-169">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]