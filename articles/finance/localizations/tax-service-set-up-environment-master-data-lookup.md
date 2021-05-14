---
title: Ustawianie środowiska wyszukiwania danych głównych
description: W tym temacie wyjaśniono, jak skonfigurować środowisko do korzystania z funkcji wyszukiwania danych podstawowych obliczania podatku.
author: kai-cloud
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9f9b385df1db60b27698d90281c43fabb574af49
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924161"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="70e4b-103">Ustawianie środowiska wyszukiwania danych głównych</span><span class="sxs-lookup"><span data-stu-id="70e4b-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70e4b-104">W tym temacie wyjaśniono, jak skonfigurować środowisko do korzystania z funkcji wyszukiwania danych podstawowych obliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="70e4b-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="70e4b-105">Konfigurowanie integracji platformy zasilania w Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="70e4b-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="70e4b-106">Aby uzyskać więcej informacji, zobacz [Integracja Microsoft Power Platform - Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="70e4b-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="70e4b-107">Konfiguracja Dynamics 365 Finance i Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="70e4b-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="70e4b-108">Aby uzyskać więcej informacji, zobacz [Uzyskiwanie rozwiązania](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) oraz [Uwierzytelnianie i autoryzacja](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="70e4b-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="70e4b-109">Należy skonfigurować następujące encje:</span><span class="sxs-lookup"><span data-stu-id="70e4b-109">Set up the following entities.</span></span> <span data-ttu-id="70e4b-110">Aby uzyskać więcej informacji, zobacz [Włączanie wirtualnych encji](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="70e4b-110">For more information, see [Enabling virtual entities](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span></span>
      - <span data-ttu-id="70e4b-111">CompanyInfoEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-111">CompanyInfoEntity</span></span>
      - <span data-ttu-id="70e4b-112">CurrencyEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-112">CurrencyEntity</span></span>
      - <span data-ttu-id="70e4b-113">CustCustomerV3Entity</span><span class="sxs-lookup"><span data-stu-id="70e4b-113">CustCustomerV3Entity</span></span>
      - <span data-ttu-id="70e4b-114">DeliveryTermsEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-114">DeliveryTermsEntity</span></span>
      - <span data-ttu-id="70e4b-115">EcoResProductCategoryEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-115">EcoResProductCategoryEntity</span></span>
      - <span data-ttu-id="70e4b-116">EcoResReleasedProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="70e4b-116">EcoResReleasedProductV2Entity</span></span>
      - <span data-ttu-id="70e4b-117">LogisticsAddressCityEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-117">LogisticsAddressCityEntity</span></span>
      - <span data-ttu-id="70e4b-118">LogisticsAddressCountryRegionTranslationEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-118">LogisticsAddressCountryRegionTranslationEntity</span></span>
      - <span data-ttu-id="70e4b-119">LogisticsAddressStateEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-119">LogisticsAddressStateEntity</span></span>
      - <span data-ttu-id="70e4b-120">PurchProcurementChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-120">PurchProcurementChargeCDSEntity</span></span>
      - <span data-ttu-id="70e4b-121">SalesChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-121">SalesChargeCDSEntity</span></span>
      - <span data-ttu-id="70e4b-122">TaxGroupEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-122">TaxGroupEntity</span></span>
      - <span data-ttu-id="70e4b-123">TaxItemGroupHeadingEntity</span><span class="sxs-lookup"><span data-stu-id="70e4b-123">TaxItemGroupHeadingEntity</span></span>
      - <span data-ttu-id="70e4b-124">VendVendorV2Entity</span><span class="sxs-lookup"><span data-stu-id="70e4b-124">VendVendorV2Entity</span></span>
4. <span data-ttu-id="70e4b-125">Skonfiguruj usługę Dynamics 365 Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="70e4b-125">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="70e4b-126">Utwórz zgłoszenie serwisowe dla firmy Microsoft, aby umożliwić wyświetlanie następujących funkcji:</span><span class="sxs-lookup"><span data-stu-id="70e4b-126">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="70e4b-127">ERCdsFeatura</span><span class="sxs-lookup"><span data-stu-id="70e4b-127">ERCdsFeature</span></span>
      - <span data-ttu-id="70e4b-128">TaxServiceCDSFeatura</span><span class="sxs-lookup"><span data-stu-id="70e4b-128">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="70e4b-129">Przejdź do obszaru roboczego **Zarządzanie funkcjami** i włącz następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="70e4b-129">Go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="70e4b-130">(Wersja zapoznawcza) Obsługa elektronicznych źródeł danych raportowania Dataverse</span><span class="sxs-lookup"><span data-stu-id="70e4b-130">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="70e4b-131">(Wersja zapoznawcza) Obsługa źródeł danych usługi podatkowej Dataverse</span><span class="sxs-lookup"><span data-stu-id="70e4b-131">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="70e4b-132">(Wersja zapoznawcza) Funkcje globalizacji</span><span class="sxs-lookup"><span data-stu-id="70e4b-132">(Preview) Globalization features</span></span>

5. <span data-ttu-id="70e4b-133">Zaloguj się do RCS przy użyciu konta administratora dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="70e4b-133">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="70e4b-134">Przejdź do **Raportowanie elektroniczne** > **Połączone aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="70e4b-134">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="70e4b-135">Wybierz pozycję **Nowy**, aby dodać rekord, i wprowadź następujące informacje o polu.</span><span class="sxs-lookup"><span data-stu-id="70e4b-135">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="70e4b-136">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="70e4b-136">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="70e4b-137">W polu **Typ** zaznacz opcję **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="70e4b-137">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="70e4b-138">W polu **Aplikacja** wprowadź adres URL Dataverse.</span><span class="sxs-lookup"><span data-stu-id="70e4b-138">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="70e4b-139">W polu **Dzierżawa** wprowadź dzierżawę.</span><span class="sxs-lookup"><span data-stu-id="70e4b-139">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="70e4b-140">W polu **Niestandardowy adres URL** wprowadź adres URL Dataverse i dołącz do niego „/api/data/v9.1”.</span><span class="sxs-lookup"><span data-stu-id="70e4b-140">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="70e4b-141">Wybierz pozycję **Sprawdź połączenie** i zakończ proces połączania.</span><span class="sxs-lookup"><span data-stu-id="70e4b-141">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="70e4b-142">[![Przycisk Sprawdź połączenie](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="70e4b-142">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="70e4b-143">Przejdź do **Raportowanie elektroniczne** > **Konfiguracje podatku** i importuj konfiguracje podatku z [Konfiguracje podatku](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="70e4b-143">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="70e4b-144">[![Strona Konfiguracje podatku, Drzewo modelu danych podatkowych](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="70e4b-144">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="70e4b-145">Przejdź do **Mapowanie modelu dokumentu podlegającego opodatkowaniu** lub **Mapowania modelu Dataverse**, jeśli używasz konfiguracji firmy Microsoft, a w polu **Połączona aplikacja** wybierz rekord utworzony w kroku 7.</span><span class="sxs-lookup"><span data-stu-id="70e4b-145">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="70e4b-146">Ustaw opcję **Domyślnego mapowania modelu** jako **Tak**.</span><span class="sxs-lookup"><span data-stu-id="70e4b-146">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="70e4b-147">[![Strona mapowania modelu](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="70e4b-147">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
