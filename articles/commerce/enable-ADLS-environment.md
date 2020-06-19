---
title: Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce
description: W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 83b829306c2da2d10924e547fd3cac6ae6781db3
ms.sourcegitcommit: fdc5dd9eb784c7d8e75692c8cdba083fe0dd87ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/26/2020
ms.locfileid: "3404193"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="2e5a9-103">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2e5a9-103">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2e5a9-104">W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-104">This topic explains how to enable and test Azure Data Lake Storage for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="2e5a9-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="2e5a9-105">Overview</span></span>

<span data-ttu-id="2e5a9-106">W rozwiązaniu Dynamics 365 Commerce wszystkie informacje o produktach i transakcjach są śledzone w magazynie jednostek środowiska.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="2e5a9-107">Aby udostępnić te dane innym usługom Dynamics 365, takim jak analiza danych, analiza biznesowa i spersonalizowane rekomendacje, konieczne jest podłączenie środowiska do rozwiązania Customer Azure Data Lake Storage Gen 2.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 solution.</span></span>

<span data-ttu-id="2e5a9-108">Ponieważ Azure Data Lake Storage jest skonfigurowany w środowisku, wszystkie niezbędne dane są dublowane z magazynu jednostek, mimo że są nadal chronione i podlegają kontroli odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-108">As Azure Data Lake Storage is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="2e5a9-109">Jeśli zaleceń produktu lub spersonalizowane rekomendacje są również włączone w środowisku, wówczas stos rekomendacji produktów będzie mieć dostęp do folderu dedykowanego w Azure Data Lake Storage w celu pobrania danych odbiorcy i obliczania zaleceń na jego podstawie.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in Azure Data Lake Storage to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2e5a9-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2e5a9-110">Prerequisites</span></span>

<span data-ttu-id="2e5a9-111">Klienci muszą mieć Azure Data Lake Storage skonfigurowany w swojej subskrypcji systemu Azure.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-111">Customers need to have Azure Data Lake Storage configured in an Azure subscription that they own.</span></span> <span data-ttu-id="2e5a9-112">Ten temat nie obejmuje zakupu subskrypcji systemu Azure ani konfiguracji konta magazynu z włączonym Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-112">This topic does not cover the purchase of an Azure subscription or the setup of an Azure Data Lake Storage-enabled storage account.</span></span>

<span data-ttu-id="2e5a9-113">Aby uzyskać więcej informacji o Azure Data Lake Storage, zobacz [Oficjalną dokumentację Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="2e5a9-113">For more information about Azure Data Lake Storage, see [Azure Data Lake Storage Gen2 official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="2e5a9-114">Kroki w konfiguracji</span><span class="sxs-lookup"><span data-stu-id="2e5a9-114">Configuration steps</span></span>

<span data-ttu-id="2e5a9-115">W tej sekcji omówiono kroki konfiguracji niezbędne do włączenia Azure Data Lake Storage w środowisku w odniesieniu do zaleceń dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-115">This section covers the configuration steps necessary for enabling Azure Data Lake Storage in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="2e5a9-116">Aby uzyskać bardziej szczegółowe omówienie kroków wymaganych do włączenia Azure Data Lake Storage, zapoznaj się z [Udostępnianie magazynu jednostek w usłudze Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="2e5a9-116">For a more in-depth overview of the steps required to enable Azure Data Lake Storage, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-azure-data-lake-storage-in-the-environment"></a><span data-ttu-id="2e5a9-117">Włączanie Azure Data Lake Storage w środowisku</span><span class="sxs-lookup"><span data-stu-id="2e5a9-117">Enable Azure Data Lake Storage in the environment</span></span>

1. <span data-ttu-id="2e5a9-118">Zaloguj się do portalu back office środowiska.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-118">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="2e5a9-119">Wyszukaj **Parametry systemowe** i przejdź do karty **Połączenia danych**.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-119">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="2e5a9-120">Określ opcję **Włącz integrację danych** w usłudze **Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-120">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="2e5a9-121">Ustaw opcję **Włącz stopniową aktualizację w Data Lake** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-121">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="2e5a9-122">Nastepnie wprowadź wymagane informacje:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-122">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="2e5a9-123">**Identyfikator aplikacji** // **Wpis tajny aplikacji** // **Nazwa DNS** - wymagane do nawiązania połączenia z magazynem kluczy, w którym jest przechowywany tajny wpis Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-123">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the Azure Data Lake Storage secret is stored.</span></span>
    1. <span data-ttu-id="2e5a9-124">**Tajna nazwa** - nazwa tajna przechowywana w magazynie kluczy i używana do uwierzytelniania za pomocą Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-124">**Secret name** - The secret name stored in KeyVault and used to authenticate with Azure Data Lake Storage.</span></span>
1. <span data-ttu-id="2e5a9-125">Zapisz zmiany w lewym górnym rogu strony.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-125">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="2e5a9-126">Poniższy obraz przedstawia przykład konfiguracji Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-126">The following image shows an example Azure Data Lake Storage configuration.</span></span>

![Przykładowa konfiguracja Azure Data Lake Storage](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a><span data-ttu-id="2e5a9-128">Przetestuj połączenie Azure Data Lake Storage</span><span class="sxs-lookup"><span data-stu-id="2e5a9-128">Test the Azure Data Lake Storage connection</span></span>

1. <span data-ttu-id="2e5a9-129">Przetestuj połączenie z magazynem kluczy za pomocą łącza **Testuj magazyn kluczy usługi Azure**.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-129">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="2e5a9-130">Przetestuj połączenie z Azure Data Lake Storage za pomocą łącza **Testuj magazyn usługi Azure**.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-130">Test the connection to Azure Data Lake Storage using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="2e5a9-131">Jeśli testy zakończą się niepowodzeniem, dokładnie sprawdź, czy wszystkie dodane powyżej informacje o magazynie klucza są poprawne, a następnie spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-131">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="2e5a9-132">Po pomyślnym zakończeniu testów połączenia należy włączyć automatyczne odświeżanie magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-132">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="2e5a9-133">Aby włączyć automatyczne odświeżanie magazynu jednostek, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-133">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="2e5a9-134">Wyszukaj **Magazynu jednostek**.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-134">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="2e5a9-135">Na liście po lewej stronie przejdź do wpisu **RetailSales**, a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-135">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="2e5a9-136">Upewnij się, że opcja **Włączone automatyczne odświeżanie** jest **Włączona**, wybierz opcję **Odśwież**, a następnie wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-136">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="2e5a9-137">Poniższy obraz przedstawia przykład magazynu jednostki z włączonym automatycznym odświeżaniem.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-137">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Przykład magazynu jednostki z włączonym automatycznym odświeżaniem](./media/exampleADLSConfig2.png)

<span data-ttu-id="2e5a9-139">Azure Data Lake Storage jest teraz skonfigurowany dla tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-139">Azure Data Lake Storage is now configured for the environment.</span></span> 

<span data-ttu-id="2e5a9-140">Jeśli nie zostało to jeszcze zrobione, wykonaj kroki [w celu włączenia zaleceń i personalizacji produktu](enable-product-recommendations.md) w środowisku.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-140">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2e5a9-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2e5a9-141">Additional resources</span></span>

[<span data-ttu-id="2e5a9-142">Udostępnianie magazynu jednostek w usłudze Data Lake</span><span class="sxs-lookup"><span data-stu-id="2e5a9-142">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="2e5a9-143">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="2e5a9-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="2e5a9-144">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="2e5a9-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="2e5a9-145">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="2e5a9-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="2e5a9-146">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="2e5a9-146">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="2e5a9-147">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e5a9-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="2e5a9-148">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="2e5a9-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="2e5a9-149">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="2e5a9-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="2e5a9-150">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="2e5a9-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="2e5a9-151">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="2e5a9-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="2e5a9-152">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="2e5a9-152">Product recommendations FAQ</span></span>](faq-recommendations.md)
