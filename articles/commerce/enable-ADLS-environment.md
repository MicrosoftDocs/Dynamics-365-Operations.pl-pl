---
title: Włączanie ADLS w środowisku Dynamics 365 Commerce
description: W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage (ADLS) dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.
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
ms.openlocfilehash: ba428765babb9ca7566da7a457368959b1c29083
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259755"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="d0032-103">Włączanie ADLS w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="d0032-103">Enable ADLS in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d0032-104">W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage (ADLS) dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="d0032-104">This topic explains how to enable and test Azure Data Lake Storage (ADLS) for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="d0032-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="d0032-105">Overview</span></span>

<span data-ttu-id="d0032-106">W rozwiązaniu Dynamics 365 Commerce wszystkie informacje o produktach i transakcjach są śledzone w magazynie jednostek środowiska.</span><span class="sxs-lookup"><span data-stu-id="d0032-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="d0032-107">Aby udostępnić te dane innym usługom Dynamics 365, takim jak analiza danych, analiza biznesowa i spersonalizowane rekomendacje, konieczne jest podłączenie środowiska do rozwiązania Customer Azure Data Lake Storage Gen 2 (ADLS).</span><span class="sxs-lookup"><span data-stu-id="d0032-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 (ADLS) solution.</span></span>

<span data-ttu-id="d0032-108">Ponieważ ADLS jest skonfigurowany w środowisku, wszystkie niezbędne dane są dublowane z magazynu jednostek, mimo że są nadal chronione i podlegają kontroli odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d0032-108">As ADLS is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="d0032-109">Jeśli zaleceń produktu lub spersonalizowane rekomendacje są również włączone w środowisku, wówczas stos rekomendacji produktów będzie mieć dostęp do folderu dedykowanego w ADLS w celu pobrania danych odbiorcy i obliczania zaleceń na jego podstawie.</span><span class="sxs-lookup"><span data-stu-id="d0032-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in ADLS to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0032-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="d0032-110">Prerequisites</span></span>

<span data-ttu-id="d0032-111">Klienci muszą mieć ADLS skonfigurowany w swojej subskrypcji systemu Azure.</span><span class="sxs-lookup"><span data-stu-id="d0032-111">Customers need to have ADLS configured in an Azure subscription that they own.</span></span> <span data-ttu-id="d0032-112">Ten temat nie obejmuje zakupu subskrypcji systemu Azure ani konfiguracji konta magazynu z włączonym ADLS.</span><span class="sxs-lookup"><span data-stu-id="d0032-112">This topic does not cover the purchase of an Azure subscription or the setup of an ADLS-enabled storage account.</span></span>

<span data-ttu-id="d0032-113">Aby uzyskać więcej informacji o ADLS, zobacz [Oficjalną dokumentację systemu ADLS](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="d0032-113">For more information about ADLS, see [ADLS official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="d0032-114">Kroki w konfiguracji</span><span class="sxs-lookup"><span data-stu-id="d0032-114">Configuration steps</span></span>

<span data-ttu-id="d0032-115">W tej sekcji omówiono kroki konfiguracji niezbędne do włączenia ADLS w środowisku w odniesieniu do zaleceń dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="d0032-115">This section covers the configuration steps necessary for enabling ADLS in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="d0032-116">Aby uzyskać bardziej szczegółowe omówienie kroków wymaganych do włączenia ADLS, zapoznaj się z [Udostępnianie magazynu jednostek w usłudze Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="d0032-116">For a more in-depth overview of the steps required to enable ADLS, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-adls-in-the-environment"></a><span data-ttu-id="d0032-117">Włączanie ADLS w środowisku</span><span class="sxs-lookup"><span data-stu-id="d0032-117">Enable ADLS in the environment</span></span>

1. <span data-ttu-id="d0032-118">Zaloguj się do portalu back office środowiska.</span><span class="sxs-lookup"><span data-stu-id="d0032-118">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="d0032-119">Wyszukaj **Parametry systemowe** i przejdź do karty **Połączenia danych**.</span><span class="sxs-lookup"><span data-stu-id="d0032-119">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="d0032-120">Określ opcję **Włącz integrację danych** w usłudze **Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="d0032-120">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="d0032-121">Ustaw opcję **Włącz stopniową aktualizację w Data Lake** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d0032-121">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="d0032-122">Nastepnie wprowadź wymagane informacje:</span><span class="sxs-lookup"><span data-stu-id="d0032-122">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="d0032-123">**Identyfikator aplikacji** // **Application Secret** // **Nazwa DNS** -wymagane do nawiązania połączenia z magazynem kluczy, w którym jest przechowywany klucz tajny ADLS.</span><span class="sxs-lookup"><span data-stu-id="d0032-123">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the ADLS secret is stored.</span></span>
    1. <span data-ttu-id="d0032-124">**Secret name** - nazwa tajna przechowywana w magazynie kluczy i używana do uwierzytelniania za pomocą ADLS.</span><span class="sxs-lookup"><span data-stu-id="d0032-124">**Secret name** - The secret name stored in KeyVault and used to authenticate with ADLS.</span></span>
1. <span data-ttu-id="d0032-125">Zapisz zmiany w lewym górnym rogu strony.</span><span class="sxs-lookup"><span data-stu-id="d0032-125">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="d0032-126">Poniższy obraz przedstawia przykład konfiguracji ADLS.</span><span class="sxs-lookup"><span data-stu-id="d0032-126">The following image shows an example ADLS configuration.</span></span>

![Przykładowa konfiguracja ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a><span data-ttu-id="d0032-128">Przetestuj połączenie ADLS</span><span class="sxs-lookup"><span data-stu-id="d0032-128">Test the ADLS connection</span></span>

1. <span data-ttu-id="d0032-129">Przetestuj połączenie z magazynem kluczy za pomocą łącza **Testuj magazyn kluczy usługi Azure**.</span><span class="sxs-lookup"><span data-stu-id="d0032-129">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="d0032-130">Przetestuj połączenie z ADLS za pomocą łącza **Testuj magazyn usługi Azure**.</span><span class="sxs-lookup"><span data-stu-id="d0032-130">Test the connection to ADLS using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="d0032-131">Jeśli testy zakończą się niepowodzeniem, dokładnie sprawdź, czy wszystkie dodane powyżej informacje o magazynie klucza są poprawne, a następnie spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="d0032-131">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="d0032-132">Po pomyślnym zakończeniu testów połączenia należy włączyć automatyczne odświeżanie magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="d0032-132">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="d0032-133">Aby włączyć automatyczne odświeżanie magazynu jednostek, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d0032-133">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="d0032-134">Wyszukaj **Magazynu jednostek**.</span><span class="sxs-lookup"><span data-stu-id="d0032-134">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="d0032-135">Na liście po lewej stronie przejdź do wpisu **RetailSales**, a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="d0032-135">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="d0032-136">Upewnij się, że opcja **Włączone automatyczne odświeżanie** jest **Włączona**, wybierz opcję **Odśwież**, a następnie wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d0032-136">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="d0032-137">Poniższy obraz przedstawia przykład magazynu jednostki z włączonym automatycznym odświeżaniem.</span><span class="sxs-lookup"><span data-stu-id="d0032-137">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Przykład magazynu jednostki z włączonym automatycznym odświeżaniem](./media/exampleADLSConfig2.png)

<span data-ttu-id="d0032-139">ADLS jest teraz skonfigurowany dla tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="d0032-139">ADLS is now configured for the environment.</span></span> 

<span data-ttu-id="d0032-140">Jeśli nie zostało to jeszcze zrobione, wykonaj kroki [w celu włączenia zaleceń i personalizacji produktu](enable-product-recommendations.md) w środowisku.</span><span class="sxs-lookup"><span data-stu-id="d0032-140">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d0032-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d0032-141">Additional resources</span></span>

[<span data-ttu-id="d0032-142">Udostępnianie magazynu jednostek w usłudze Data Lake</span><span class="sxs-lookup"><span data-stu-id="d0032-142">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="d0032-143">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="d0032-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="d0032-144">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="d0032-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="d0032-145">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="d0032-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="d0032-146">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="d0032-146">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="d0032-147">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d0032-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="d0032-148">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="d0032-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="d0032-149">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="d0032-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="d0032-150">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="d0032-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="d0032-151">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="d0032-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="d0032-152">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="d0032-152">Product recommendations FAQ</span></span>](faq-recommendations.md)
