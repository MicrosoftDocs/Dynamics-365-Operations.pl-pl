---
title: Ustawianie środowiska wyszukiwania danych głównych
description: W tym temacie wyjaśniono, jak skonfigurować środowisko do korzystania z funkcji wyszukiwania danych podstawowych obliczania podatku.
author: kai-cloud
ms.date: 03/31/2021
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
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869091"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="25fee-103">Ustawianie środowiska wyszukiwania danych głównych</span><span class="sxs-lookup"><span data-stu-id="25fee-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="25fee-104">W tym temacie wyjaśniono, jak skonfigurować środowisko do korzystania z funkcji wyszukiwania danych podstawowych obliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="25fee-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="25fee-105">Konfigurowanie integracji platformy zasilania w Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="25fee-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="25fee-106">Aby uzyskać więcej informacji, zobacz [Integracja Microsoft Power Platform - Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="25fee-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="25fee-107">Konfiguracja Dynamics 365 Finance i Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="25fee-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="25fee-108">Aby uzyskać więcej informacji, zobacz [Uzyskiwanie rozwiązania](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) oraz [Uwierzytelnianie i autoryzacja](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="25fee-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="25fee-109">Zaimportuj *rozwiązanie jednostki wirtualnej usługi podatkowej* z [jednostki wirtualnej Usługi podatkowej](https://go.microsoft.com/fwlink/?linkid=2158160).</span><span class="sxs-lookup"><span data-stu-id="25fee-109">Import the *Prerequisite tax service virtual entity solution* from the [Tax service virtual entity](https://go.microsoft.com/fwlink/?linkid=2158160).</span></span>
4. <span data-ttu-id="25fee-110">Skonfiguruj usługę Dynamics 365 Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="25fee-110">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="25fee-111">Utwórz zgłoszenie serwisowe dla firmy Microsoft, aby umożliwić wyświetlanie następujących funkcji:</span><span class="sxs-lookup"><span data-stu-id="25fee-111">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="25fee-112">ERCdsFeatura</span><span class="sxs-lookup"><span data-stu-id="25fee-112">ERCdsFeature</span></span>
      - <span data-ttu-id="25fee-113">TaxServiceCDSFeatura</span><span class="sxs-lookup"><span data-stu-id="25fee-113">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="25fee-114">W Finance przejdź do obszaru roboczego **Zarządzanie funkcjami** i włącz następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="25fee-114">In Finance, go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="25fee-115">(Wersja zapoznawcza) Obsługa elektronicznych źródeł danych raportowania Dataverse</span><span class="sxs-lookup"><span data-stu-id="25fee-115">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="25fee-116">(Wersja zapoznawcza) Obsługa źródeł danych usługi podatkowej Dataverse</span><span class="sxs-lookup"><span data-stu-id="25fee-116">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="25fee-117">(Wersja zapoznawcza) Funkcje globalizacji</span><span class="sxs-lookup"><span data-stu-id="25fee-117">(Preview) Globalization features</span></span>

5. <span data-ttu-id="25fee-118">Zaloguj się do RCS przy użyciu konta administratora dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="25fee-118">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="25fee-119">Przejdź do **Raportowanie elektroniczne** > **Połączone aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="25fee-119">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="25fee-120">Wybierz pozycję **Nowy**, aby dodać rekord, i wprowadź następujące informacje o polu.</span><span class="sxs-lookup"><span data-stu-id="25fee-120">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="25fee-121">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="25fee-121">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="25fee-122">W polu **Typ** zaznacz opcję **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="25fee-122">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="25fee-123">W polu **Aplikacja** wprowadź adres URL Dataverse.</span><span class="sxs-lookup"><span data-stu-id="25fee-123">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="25fee-124">W polu **Dzierżawa** wprowadź dzierżawę.</span><span class="sxs-lookup"><span data-stu-id="25fee-124">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="25fee-125">W polu **Niestandardowy adres URL** wprowadź adres URL Dataverse i dołącz do niego „/api/data/v9.1”.</span><span class="sxs-lookup"><span data-stu-id="25fee-125">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="25fee-126">Wybierz pozycję **Sprawdź połączenie** i zakończ proces połączania.</span><span class="sxs-lookup"><span data-stu-id="25fee-126">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="25fee-127">[![Przycisk Sprawdź połączenie](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="25fee-127">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="25fee-128">Przejdź do **Raportowanie elektroniczne** > **Konfiguracje podatku** i importuj konfiguracje podatku z [Konfiguracje podatku](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="25fee-128">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="25fee-129">[![Strona Konfiguracje podatku, Drzewo modelu danych podatkowych](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="25fee-129">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="25fee-130">Przejdź do **Mapowanie modelu dokumentu podlegającego opodatkowaniu** lub **Mapowania modelu Dataverse**, jeśli używasz konfiguracji firmy Microsoft, a w polu **Połączona aplikacja** wybierz rekord utworzony w kroku 7.</span><span class="sxs-lookup"><span data-stu-id="25fee-130">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="25fee-131">Ustaw opcję **Domyślnego mapowania modelu** jako **Tak**.</span><span class="sxs-lookup"><span data-stu-id="25fee-131">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="25fee-132">[![Strona mapowania modelu](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="25fee-132">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
