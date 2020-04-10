---
title: Włączanie ADLS w środowisku Dynamics 365 Commerce
description: W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage (ADLS) dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
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
ms.openlocfilehash: 3c037f5603af5af84917084eefa1edd508891c0d
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154443"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="9c10b-103">Włączanie ADLS w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9c10b-103">Enable ADLS in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9c10b-104">W tym temacie opisano sposób włączania i testowania Azure Data Lake Storage (ADLS) dla środowiska Dynamics 365 Commerce, który jest wstępnym warunkiem włączenia zaleceń dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="9c10b-104">This topic explains how to enable and test Azure Data Lake Storage (ADLS) for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="9c10b-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="9c10b-105">Overview</span></span>

<span data-ttu-id="9c10b-106">W rozwiązaniu Dynamics 365 Commerce wszystkie informacje o produktach i transakcjach są śledzone w magazynie jednostek środowiska.</span><span class="sxs-lookup"><span data-stu-id="9c10b-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="9c10b-107">Aby udostępnić te dane innym usługom Dynamics 365, takim jak analiza danych, analiza biznesowa i spersonalizowane rekomendacje, konieczne jest podłączenie środowiska do rozwiązania Customer Azure Data Lake Storage Gen 2 (ADLS).</span><span class="sxs-lookup"><span data-stu-id="9c10b-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 (ADLS) solution.</span></span>

<span data-ttu-id="9c10b-108">Ponieważ ADLS jest skonfigurowany w środowisku, wszystkie niezbędne dane są dublowane z magazynu jednostek, mimo że są nadal chronione i podlegają kontroli odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="9c10b-108">As ADLS is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="9c10b-109">Jeśli zaleceń produktu lub spersonalizowane rekomendacje są również włączone w środowisku, wówczas stos rekomendacji produktów będzie mieć dostęp do folderu dedykowanego w ADLS w celu pobrania danych odbiorcy i obliczania zaleceń na jego podstawie.</span><span class="sxs-lookup"><span data-stu-id="9c10b-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in ADLS to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9c10b-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="9c10b-110">Prerequisites</span></span>

<span data-ttu-id="9c10b-111">Klienci muszą mieć ADLS skonfigurowany w swojej subskrypcji systemu Azure.</span><span class="sxs-lookup"><span data-stu-id="9c10b-111">Customers need to have ADLS configured in an Azure subscription that they own.</span></span> <span data-ttu-id="9c10b-112">Ten temat nie obejmuje zakupu subskrypcji systemu Azure ani konfiguracji konta magazynu z włączonym ADLS.</span><span class="sxs-lookup"><span data-stu-id="9c10b-112">This topic does not cover the purchase of an Azure subscription or the setup of an ADLS-enabled storage account.</span></span>

<span data-ttu-id="9c10b-113">Aby uzyskać więcej informacji o ADLS, zobacz [Oficjalną dokumentację systemu ADLS](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="9c10b-113">For more information about ADLS, see [ADLS official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="9c10b-114">Kroki w konfiguracji</span><span class="sxs-lookup"><span data-stu-id="9c10b-114">Configuration steps</span></span>

<span data-ttu-id="9c10b-115">W tej sekcji omówiono kroki konfiguracji niezbędne do włączenia ADLS w środowisku.</span><span class="sxs-lookup"><span data-stu-id="9c10b-115">This section covers the configuration steps necessary for enabling ADLS in an environment.</span></span>

### <a name="enable-adls-in-the-environment"></a><span data-ttu-id="9c10b-116">Włączanie ADLS w środowisku</span><span class="sxs-lookup"><span data-stu-id="9c10b-116">Enable ADLS in the environment</span></span>

1. <span data-ttu-id="9c10b-117">Zaloguj się do portalu back office środowiska.</span><span class="sxs-lookup"><span data-stu-id="9c10b-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="9c10b-118">Wyszukaj **Parametry systemowe** i przejdź do karty **Połączenia danych**.</span><span class="sxs-lookup"><span data-stu-id="9c10b-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="9c10b-119">Określ opcję **Włącz integrację danych** w usłudze **Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="9c10b-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="9c10b-120">Ustaw opcję **Włącz stopniową aktualizację w Data Lake** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9c10b-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="9c10b-121">Nastepnie wprowadź wymagane informacje:</span><span class="sxs-lookup"><span data-stu-id="9c10b-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="9c10b-122">**Identyfikator aplikacji** // **Application Secret** // **Nazwa DNS** -wymagane do nawiązania połączenia z magazynem kluczy, w którym jest przechowywany klucz tajny ADLS.</span><span class="sxs-lookup"><span data-stu-id="9c10b-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the ADLS secret is stored.</span></span>
    1. <span data-ttu-id="9c10b-123">**Secret name** - nazwa tajna przechowywana w magazynie kluczy i używana do uwierzytelniania za pomocą ADLS.</span><span class="sxs-lookup"><span data-stu-id="9c10b-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with ADLS.</span></span>
1. <span data-ttu-id="9c10b-124">Zapisz zmiany w lewym górnym rogu strony.</span><span class="sxs-lookup"><span data-stu-id="9c10b-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="9c10b-125">Poniższy obraz przedstawia przykład konfiguracji ADLS.</span><span class="sxs-lookup"><span data-stu-id="9c10b-125">The following image shows an example ADLS configuration.</span></span>

![Przykładowa konfiguracja ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a><span data-ttu-id="9c10b-127">Przetestuj połączenie ADLS</span><span class="sxs-lookup"><span data-stu-id="9c10b-127">Test the ADLS connection</span></span>

1. <span data-ttu-id="9c10b-128">Przetestuj połączenie z magazynem kluczy za pomocą łącza **Testuj magazyn kluczy usługi Azure**.</span><span class="sxs-lookup"><span data-stu-id="9c10b-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="9c10b-129">Przetestuj połączenie z ADLS za pomocą łącza **Testuj magazyn usługi Azure**.</span><span class="sxs-lookup"><span data-stu-id="9c10b-129">Test the connection to ADLS using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="9c10b-130">Jeśli testy zakończą się niepowodzeniem, dokładnie sprawdź, czy wszystkie dodane powyżej informacje o magazynie klucza są poprawne, a następnie spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="9c10b-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="9c10b-131">Po pomyślnym zakończeniu testów połączenia należy włączyć automatyczne odświeżanie magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="9c10b-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="9c10b-132">Aby włączyć automatyczne odświeżanie magazynu jednostek, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="9c10b-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="9c10b-133">Wyszukaj **Magazynu jednostek**.</span><span class="sxs-lookup"><span data-stu-id="9c10b-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="9c10b-134">Na liście po lewej stronie przejdź do wpisu **RetailSales**, a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="9c10b-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="9c10b-135">Upewnij się, że opcja **Włączone automatyczne odświeżanie** jest **Włączona**, wybierz opcję **Odśwież**, a następnie wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9c10b-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="9c10b-136">Poniższy obraz przedstawia przykład magazynu jednostki z włączonym automatycznym odświeżaniem.</span><span class="sxs-lookup"><span data-stu-id="9c10b-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Przykład magazynu jednostki z włączonym automatycznym odświeżaniem](./media/exampleADLSConfig2.png)

<span data-ttu-id="9c10b-138">ADLS jest teraz skonfigurowany dla tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="9c10b-138">ADLS is now configured for the environment.</span></span> 

<span data-ttu-id="9c10b-139">Jeśli nie zostało to jeszcze zrobione, wykonaj kroki [w celu włączenia zaleceń i personalizacji produktu](enable-product-recommendations.md) w środowisku.</span><span class="sxs-lookup"><span data-stu-id="9c10b-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c10b-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9c10b-140">Additional resources</span></span>

[<span data-ttu-id="9c10b-141">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="9c10b-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="9c10b-142">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="9c10b-142">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="9c10b-143">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="9c10b-143">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="9c10b-144">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="9c10b-144">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="9c10b-145">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9c10b-145">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="9c10b-146">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="9c10b-146">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="9c10b-147">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="9c10b-147">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="9c10b-148">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="9c10b-148">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="9c10b-149">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="9c10b-149">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="9c10b-150">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="9c10b-150">Product recommendations FAQ</span></span>](faq-recommendations.md)


