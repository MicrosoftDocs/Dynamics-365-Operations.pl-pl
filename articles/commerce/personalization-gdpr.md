---
title: Wypisz się ze spersonalizowanych rekomendacji produktów
description: W tym temacie wyjaśniono, jak można pozwolić klientom zrezygnować z otrzymywania spersonalizowanych rekomendacji w firmie Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: e65fc54f87664caec95b2bc2c579d0820ae08c0f
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477691"
---
# <a name="opt-out-of-personalized-recommendations"></a><span data-ttu-id="636cd-103">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="636cd-103">Opt out of personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="636cd-104">W tym temacie wyjaśniono, jak można pozwolić klientom zrezygnować z otrzymywania spersonalizowanych rekomendacji w firmie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="636cd-104">This topic explains how you can let customers opt out of receiving personalized recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="636cd-105">Podczas tworzenia konta nowi odbiorcy są automatycznie konfigurowani w taki sposób, aby otrzymywać spersonalizowane rekomendacje.</span><span class="sxs-lookup"><span data-stu-id="636cd-105">During account creation, new customers are automatically set up to receive personalized recommendations.</span></span> <span data-ttu-id="636cd-106">Jednak Dynamics 365 Commerce oferuje różne sposoby, aby sprzedawcy mogli zrezygnować z otrzymywania tych zaleceń i ograniczyć przetwarzanie ich danych osobowych.</span><span class="sxs-lookup"><span data-stu-id="636cd-106">However, Dynamics 365 Commerce provides various ways for retailers to let users opt out of receiving these recommendations and restrict the processing of their personal data.</span></span> <span data-ttu-id="636cd-107">Użytkownicy uwierzytelnieni, którzy zrezygnują z otrzymywania spersonalizowanych rekomendacji, nie będą widzieć już tych spersonalizowanych list.</span><span class="sxs-lookup"><span data-stu-id="636cd-107">Authenticated users who opt out of receiving personalized recommendations will immediately stop seeing personalized lists.</span></span> <span data-ttu-id="636cd-108">Ponadto wszystkie dane osobowe zbierane w celu personalizacji zostaną usunięte z spersonalizowanych modeli rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="636cd-108">Additionally, all personal data that is collected for personalization will be removed from personalized recommendations models.</span></span>

<span data-ttu-id="636cd-109">Aby uzyskać informacje o spersonalizowanych rekomendacjach produktów, zobacz [Włączanie spersonalizowanych rekomendacji](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="636cd-109">For more information about personalized product recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a><span data-ttu-id="636cd-110">Sposoby zaimplementowania rezygnacji z usługi</span><span class="sxs-lookup"><span data-stu-id="636cd-110">Ways for retailers to implement an opt-out experience</span></span>

<span data-ttu-id="636cd-111">Sprzedawcom udostępniono trzy sposoby zaimplementowania rezygnacji z usługi.</span><span class="sxs-lookup"><span data-stu-id="636cd-111">Retailers have three ways to implement an opt-out experience.</span></span>

### <a name="opting-out-on-behalf-of-users"></a><span data-ttu-id="636cd-112">Rezygnacja w imieniu użytkowników</span><span class="sxs-lookup"><span data-stu-id="636cd-112">Opting out on behalf of users</span></span>

<span data-ttu-id="636cd-113">W przypadku zarządzania kontami w module zaplecza Commerce, sprzedawcy mogą zrezygnować w imieniu użytkowników.</span><span class="sxs-lookup"><span data-stu-id="636cd-113">In Account management in Commerce back office, retailers can opt out on behalf of users.</span></span>

1. <span data-ttu-id="636cd-114">Na stronie głównej zaplecza wyszukaj **wszystkich odbiorców**.</span><span class="sxs-lookup"><span data-stu-id="636cd-114">From the back-office home page, search for **all customers**.</span></span>
1. <span data-ttu-id="636cd-115">Wyszukaj i wybierz odbiorcę, a następnie wybierz skróconą kartę **Sieć sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="636cd-115">Search for and select a customer, and then select the **Retail** FastTab.</span></span>

    ![Skrócona karta sieci sprzedaży](./media/Disablepersonalizationpart1.png)

1. <span data-ttu-id="636cd-117">W obszarze **prywatność** ustaw opcję **Wyłącz personalizację** na **tak**.</span><span class="sxs-lookup"><span data-stu-id="636cd-117">Under **Privacy**, set the **Disable personalization** option to **Yes**.</span></span>

    ![Ustawienia prywatności](./media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="636cd-119">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="636cd-119">Select **Save**, and close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="636cd-120">Oparta na module usługa rezygnacji</span><span class="sxs-lookup"><span data-stu-id="636cd-120">Module-based opt-out experience</span></span>

<span data-ttu-id="636cd-121">Detaliści mogą zezwolić uwierzytelnionym użytkownikom na rezygnację z spersonalizowanych rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="636cd-121">Retailers can let authenticated users opt out of personalized recommendations by themselves.</span></span> <span data-ttu-id="636cd-122">Aby określić to działanie, należy dodać moduł rezygnacji przez użytkownika do stron profilu konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="636cd-122">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="636cd-123">Rozszerzenia niestandardowe</span><span class="sxs-lookup"><span data-stu-id="636cd-123">Custom extensions</span></span>

<span data-ttu-id="636cd-124">Detaliści mogą tworzyć własne rozszerzenia służące do zarządzania niektórymi usługami rezygnacji użytkowników.</span><span class="sxs-lookup"><span data-stu-id="636cd-124">Retailers can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="636cd-125">Aby uzyskać więcej informacji, zobacz [Wywoływanie interfejsów API w usłudze Retail Server](e-commerce-extensibility/call-retail-server-apis.md) i [rozszerzalność kanału online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="636cd-125">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a><span data-ttu-id="636cd-126">Uzyskaj cyfrową kopię spersonalizowanych danych rekomendacji w imieniu uwierzytelnionego użytkownika</span><span class="sxs-lookup"><span data-stu-id="636cd-126">Obtain a digital copy of personalized recommendations data on behalf of an authenticated user</span></span>

<span data-ttu-id="636cd-127">Klienci mogą chcieć uzyskać cyfrową kopię swoich danych osobowych, a także wyeksportowanego widoku wyników ich rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="636cd-127">Customers might want to obtain a digital copy of their personal data and also see an exported view of their recommendations results.</span></span> <span data-ttu-id="636cd-128">Jeśli odbiorca zażąda tych informacji, sprzedawca musi utworzyć niestandardowe rozszerzenie, które wywołuje interfejs programowania aplikacji serwera Retail Server (API) i kwerendę dotyczącą pełnych wyników z listy **Wybrane dla Ciebie** na podstawie identyfikatora odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="636cd-128">If a customer requests this information, the retailer must create a customized extension that calls the Retail Server application programming interface (API) and queries for the full results from the **Picks for you** list, based on the customer's customer ID.</span></span> <span data-ttu-id="636cd-129">Wyniki mogą zostać wyeksportowane w formacie CSV (wartości rozdzielane przecinkami) i udostępniane klientowi.</span><span class="sxs-lookup"><span data-stu-id="636cd-129">The results can then be exported in comma-separated values (CSV) format and shared with the customer.</span></span>

<span data-ttu-id="636cd-130">Poniższy przykład przedstawia sposób, w jaki sprzedawca może wykonać to zadanie.</span><span class="sxs-lookup"><span data-stu-id="636cd-130">The following example shows how a retailer can accomplish this task.</span></span>

1. <span data-ttu-id="636cd-131">Detalista tworzy niestandardowe rozszerzenie w celu pobrania danych osobistych rekomendacji w imieniu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="636cd-131">The retailer creates a custom extension to pull personal recommendations data on behalf of the user.</span></span> <span data-ttu-id="636cd-132">Aby uzyskać informacje na temat tworzenia modułów, klonować istniejące moduły, wywoływać interfejsy API serwera sieci sprzedaży i akcje danych wywołań, należy zapoznać się z tematem [Rozszerzania kanału online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="636cd-132">For information about how to create modules, clone existing modules, call Retail Server APIs, and call data actions, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
2. <span data-ttu-id="636cd-133">Rozszerzenie niestandardowe powoduje wywołanie głównej akcji dotyczącej **danych polecanych** do pobrania i przekazuje do niej wymagane informacje na podstawie wymagań listy.</span><span class="sxs-lookup"><span data-stu-id="636cd-133">The custom extension makes a call to the **get-recommendations** core data action and passes the required information to it, based on the requirements of the list.</span></span> <span data-ttu-id="636cd-134">W przypadku listy **Wybrane dla Ciebie** rozszerzenie musi przekazać poprawną nazwę listy i identyfikator klienta do akcji danych.</span><span class="sxs-lookup"><span data-stu-id="636cd-134">In the case of the **Picks for you** list, the extension must pass the correct list name and customer ID to the data action.</span></span>

    <span data-ttu-id="636cd-135">Jednym ze sposobów utworzenia niestandardowego rozszerzenia jest sklonowanie istniejącego modułu zbierania produktów używanego do zwracania wyników rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="636cd-135">One way to create the custom extension is to clone the existing product collection module that is used to return recommendations results.</span></span> <span data-ttu-id="636cd-136">Przez Klonowanie istniejącego modułu sprzedawca może zmodyfikować istniejący kod i dodać nowy przycisk, który eksportuje wyniki do pliku CSV.</span><span class="sxs-lookup"><span data-stu-id="636cd-136">By cloning this existing module, a retailer can modify the existing code and add a new button that exports the recommendations results to a CSV file.</span></span> <span data-ttu-id="636cd-137">Aby uzyskać więcej informacji, zobacz [Sklonuj moduł biblioteki modułów](e-commerce-extensibility/clone-starter-module.md) i [modułu zbierania produktów](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="636cd-137">For more information, see [Clone a module library module](e-commerce-extensibility/clone-starter-module.md) and [Product collection modules](product-collection-module-overview.md).</span></span>

    <span data-ttu-id="636cd-138">Aby zapoznać się z pełnym widokiem biblioteki API serwera Retail Server, zobacz [Interfejsy API klienta serwera sieci sprzedaży i odbiorców](dev-itpro/retail-server-customer-consumer-api.md).</span><span class="sxs-lookup"><span data-stu-id="636cd-138">For a full view of the Retail Server API library, see [Retail Server Customer and Consumer APIs](dev-itpro/retail-server-customer-consumer-api.md).</span></span>

3. <span data-ttu-id="636cd-139">Po utworzeniu niestandardowego rozszerzenia sprzedawca może eksportować plik CSV wszystkich wyników rekomendacji na podstawie unikatowego identyfikatora klienta uwierzytelnionego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="636cd-139">After the custom extension is created, the retailer can export a CSV file of all recommendations results, based on the unique customer ID of the authenticated user.</span></span>
4. <span data-ttu-id="636cd-140">Sprzedawca może udostępnić wyeksportowany plik CSV zawierający pełną spersonalizowaną listę zalecanych produktów uwierzytelnionemu użytkownikowi.</span><span class="sxs-lookup"><span data-stu-id="636cd-140">The retailer can share the exported CSV file that contains the full personalized list of recommended products with the authenticated user.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="636cd-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="636cd-141">Additional resources</span></span>

[<span data-ttu-id="636cd-142">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="636cd-142">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="636cd-143">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="636cd-143">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="636cd-144">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="636cd-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="636cd-145">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="636cd-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="636cd-146">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="636cd-146">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="636cd-147">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="636cd-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="636cd-148">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="636cd-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="636cd-149">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="636cd-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="636cd-150">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="636cd-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="636cd-151">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="636cd-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="636cd-152">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="636cd-152">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
