---
title: Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce
description: W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.
author: bebeale
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 61f96dae0643e3383afd91864e4c145f3b5c04c8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792614"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="7382b-103">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7382b-103">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7382b-104">W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="7382b-104">This topic explains how to enable and test Azure Data Lake Storage for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

<span data-ttu-id="7382b-105">W rozwiązaniu Dynamics 365 Commerce wszystkie informacje o produktach i transakcjach są śledzone w magazynie jednostek środowiska.</span><span class="sxs-lookup"><span data-stu-id="7382b-105">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="7382b-106">Aby udostępnić te dane innym usługom Dynamics 365, takim jak analiza danych, analiza biznesowa i spersonalizowane rekomendacje, konieczne jest podłączenie środowiska do rozwiązania Customer Azure Data Lake Storage Gen 2.</span><span class="sxs-lookup"><span data-stu-id="7382b-106">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 solution.</span></span>

<span data-ttu-id="7382b-107">Ponieważ Azure Data Lake Storage jest skonfigurowany w środowisku, wszystkie niezbędne dane są dublowane z magazynu jednostek, mimo że są nadal chronione i podlegają kontroli odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="7382b-107">As Azure Data Lake Storage is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="7382b-108">Jeśli zaleceń produktu lub spersonalizowane rekomendacje są również włączone w środowisku, wówczas stos rekomendacji produktów będzie mieć dostęp do folderu dedykowanego w Azure Data Lake Storage w celu pobrania danych odbiorcy i obliczania zaleceń na jego podstawie.</span><span class="sxs-lookup"><span data-stu-id="7382b-108">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in Azure Data Lake Storage to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7382b-109">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="7382b-109">Prerequisites</span></span>

<span data-ttu-id="7382b-110">Klienci muszą mieć Azure Data Lake Storage skonfigurowany w swojej subskrypcji systemu Azure.</span><span class="sxs-lookup"><span data-stu-id="7382b-110">Customers need to have Azure Data Lake Storage configured in an Azure subscription that they own.</span></span> <span data-ttu-id="7382b-111">Ten temat nie obejmuje zakupu subskrypcji systemu Azure ani konfiguracji konta magazynu z włączonym Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="7382b-111">This topic does not cover the purchase of an Azure subscription or the setup of an Azure Data Lake Storage-enabled storage account.</span></span>

<span data-ttu-id="7382b-112">Aby uzyskać więcej informacji o Azure Data Lake Storage, zobacz [Oficjalną dokumentację Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="7382b-112">For more information about Azure Data Lake Storage, see [Azure Data Lake Storage Gen2 official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="7382b-113">Kroki w konfiguracji</span><span class="sxs-lookup"><span data-stu-id="7382b-113">Configuration steps</span></span>

<span data-ttu-id="7382b-114">W tej sekcji omówiono kroki konfiguracji niezbędne do włączenia Azure Data Lake Storage w środowisku w odniesieniu do zaleceń dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="7382b-114">This section covers the configuration steps necessary for enabling Azure Data Lake Storage in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="7382b-115">Aby uzyskać bardziej szczegółowe omówienie kroków wymaganych do włączenia Azure Data Lake Storage, zapoznaj się z [Udostępnianie magazynu jednostek w usłudze Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="7382b-115">For a more in-depth overview of the steps required to enable Azure Data Lake Storage, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-azure-data-lake-storage-in-the-environment"></a><span data-ttu-id="7382b-116">Włączanie Azure Data Lake Storage w środowisku</span><span class="sxs-lookup"><span data-stu-id="7382b-116">Enable Azure Data Lake Storage in the environment</span></span>

1. <span data-ttu-id="7382b-117">Zaloguj się do portalu back office środowiska.</span><span class="sxs-lookup"><span data-stu-id="7382b-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="7382b-118">Wyszukaj **Parametry systemowe** i przejdź do karty **Połączenia danych**.</span><span class="sxs-lookup"><span data-stu-id="7382b-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="7382b-119">Określ opcję **Włącz integrację danych** w usłudze **Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="7382b-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="7382b-120">Ustaw opcję **Włącz stopniową aktualizację w Data Lake** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="7382b-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="7382b-121">Nastepnie wprowadź wymagane informacje:</span><span class="sxs-lookup"><span data-stu-id="7382b-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="7382b-122">**Identyfikator aplikacji** // **Wpis tajny aplikacji** // **Nazwa DNS** - wymagane do nawiązania połączenia z magazynem kluczy, w którym jest przechowywany tajny wpis Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="7382b-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the Azure Data Lake Storage secret is stored.</span></span>
    1. <span data-ttu-id="7382b-123">**Tajna nazwa** - nazwa tajna przechowywana w magazynie kluczy i używana do uwierzytelniania za pomocą Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="7382b-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with Azure Data Lake Storage.</span></span>
1. <span data-ttu-id="7382b-124">Zapisz zmiany w lewym górnym rogu strony.</span><span class="sxs-lookup"><span data-stu-id="7382b-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="7382b-125">Poniższy obraz przedstawia przykład konfiguracji Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="7382b-125">The following image shows an example Azure Data Lake Storage configuration.</span></span>

![Przykładowa konfiguracja Azure Data Lake Storage](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a><span data-ttu-id="7382b-127">Przetestuj połączenie Azure Data Lake Storage</span><span class="sxs-lookup"><span data-stu-id="7382b-127">Test the Azure Data Lake Storage connection</span></span>

1. <span data-ttu-id="7382b-128">Przetestuj połączenie z magazynem kluczy za pomocą łącza **Testuj magazyn kluczy usługi Azure**.</span><span class="sxs-lookup"><span data-stu-id="7382b-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="7382b-129">Przetestuj połączenie z Azure Data Lake Storage za pomocą łącza **Testuj magazyn usługi Azure**.</span><span class="sxs-lookup"><span data-stu-id="7382b-129">Test the connection to Azure Data Lake Storage using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="7382b-130">Jeśli testy zakończą się niepowodzeniem, dokładnie sprawdź, czy wszystkie dodane powyżej informacje o magazynie klucza są poprawne, a następnie spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="7382b-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="7382b-131">Po pomyślnym zakończeniu testów połączenia należy włączyć automatyczne odświeżanie magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="7382b-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="7382b-132">Aby włączyć automatyczne odświeżanie magazynu jednostek, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7382b-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="7382b-133">Wyszukaj **Magazynu jednostek**.</span><span class="sxs-lookup"><span data-stu-id="7382b-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="7382b-134">Na liście po lewej stronie przejdź do wpisu **RetailSales**, a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="7382b-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="7382b-135">Upewnij się, że opcja **Włączone automatyczne odświeżanie** jest **Włączona**, wybierz opcję **Odśwież**, a następnie wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7382b-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="7382b-136">Poniższy obraz przedstawia przykład magazynu jednostki z włączonym automatycznym odświeżaniem.</span><span class="sxs-lookup"><span data-stu-id="7382b-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Przykład magazynu jednostki z włączonym automatycznym odświeżaniem](./media/exampleADLSConfig2.png)

<span data-ttu-id="7382b-138">Azure Data Lake Storage jest teraz skonfigurowany dla tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="7382b-138">Azure Data Lake Storage is now configured for the environment.</span></span> 

<span data-ttu-id="7382b-139">Jeśli nie zostało to jeszcze zrobione, wykonaj kroki [w celu włączenia zaleceń i personalizacji produktu](enable-product-recommendations.md) w środowisku.</span><span class="sxs-lookup"><span data-stu-id="7382b-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7382b-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7382b-140">Additional resources</span></span>

[<span data-ttu-id="7382b-141">Udostępnianie magazynu jednostek w usłudze Data Lake</span><span class="sxs-lookup"><span data-stu-id="7382b-141">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="7382b-142">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="7382b-142">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="7382b-143">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="7382b-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="7382b-144">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="7382b-144">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="7382b-145">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="7382b-145">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="7382b-146">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="7382b-146">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="7382b-147">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="7382b-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="7382b-148">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="7382b-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="7382b-149">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="7382b-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="7382b-150">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="7382b-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="7382b-151">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="7382b-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="7382b-152">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="7382b-152">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
