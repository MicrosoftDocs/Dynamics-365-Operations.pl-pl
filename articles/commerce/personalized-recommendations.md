---
title: Włącz spersonalizowane rekomendacje produktów
description: W tym temacie opisano sposób udostępniania spersonalizowanych rekomendacji dotyczących klientów w programie Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/18/2020
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
ms.openlocfilehash: dc0fbff437bfa948d70a03479561542106805bdb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804436"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="16b7e-103">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="16b7e-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="16b7e-104">W tym temacie opisano sposób udostępniania spersonalizowanych rekomendacji dotyczących klientów w programie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="16b7e-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="16b7e-105">W systemie Dynamics 365 Commerce detaliści mogą udostępniać spersonalizowane rekomendacje dotyczące produktów (znane także jako Personalizacja).</span><span class="sxs-lookup"><span data-stu-id="16b7e-105">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="16b7e-106">Dzięki temu spersonalizowane rekomendacje mogą być włączane do obsługi klienta w trybie online i w punkcie sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="16b7e-106">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="16b7e-107">Gdy jest włączona funkcja personalizacji, system może skojarzyć informacje o zakupie i produkcie użytkownika w celu wygenerowania poszczególnych zaleceń dotyczących produktu.</span><span class="sxs-lookup"><span data-stu-id="16b7e-107">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="16b7e-108">Wymagania wstępne dotyczące personalizacji</span><span class="sxs-lookup"><span data-stu-id="16b7e-108">Personalization prerequisites</span></span>

<span data-ttu-id="16b7e-109">Przed udostępnieniem klientom spersonalizowanych rekomendacji dotyczących produktów należy zauważyć, że zalecenia dotyczące produktów są obsługiwane tylko dla użytkowników systemu Commerce, którzy dokonali migracji swoich magazynów do usługi Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="16b7e-109">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="16b7e-110">Zanim klienci będą mogli uzyskać spersonalizowane zalecenia dotyczące produktów, muszą [włączyć rekomendacje produktów](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="16b7e-110">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="16b7e-111">Włączając rekomendacje dotyczące produktów, Włącz również opcję Personalizacja.</span><span class="sxs-lookup"><span data-stu-id="16b7e-111">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="16b7e-112">Jeśli jednak wyłączysz personalizację, nie wyłączasz innych typów rekomendacji dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="16b7e-112">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="16b7e-113">Aby uzyskać więcej informacji na temat rekomendacji produktów, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="16b7e-113">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="16b7e-114">Włącz personalizację</span><span class="sxs-lookup"><span data-stu-id="16b7e-114">Turn on personalization</span></span>

<span data-ttu-id="16b7e-115">Aby włączyć personalizację, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="16b7e-115">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="16b7e-116">W module Commerce Headquarters znajdź **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="16b7e-116">In Commerce headquarters, search for **Feature Management**.</span></span>
1. <span data-ttu-id="16b7e-117">Opcja **Wszystkie** umożliwia wyświetlenie listy dostępnych funkcji.</span><span class="sxs-lookup"><span data-stu-id="16b7e-117">Select **All** to see a list of available features.</span></span> 
1. <span data-ttu-id="16b7e-118">W polu wyszukiwania wprowadź **Rekomendacje**.</span><span class="sxs-lookup"><span data-stu-id="16b7e-118">In the search box, enter **Recommendations**.</span></span>
1. <span data-ttu-id="16b7e-119">Wybierz funkcję **Spersonalizowane rekomendacje produktów**.</span><span class="sxs-lookup"><span data-stu-id="16b7e-119">Select the **Personalized product recommendations** feature.</span></span>
1. <span data-ttu-id="16b7e-120">W okienku właściwości **Spersonalizowane rekomendacje produktów** wybierz opcję **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="16b7e-120">In the **Personalized product recommendations** properties pane, select **Enable now**.</span></span>

![Włączanie personalizacji](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> <span data-ttu-id="16b7e-122">Po włączeniu personalizacji zostanie rozpoczęty proces generowania spersonalizowanych list rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="16b7e-122">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="16b7e-123">Zanim te listy będą dostępne i widoczne w trybie online i w punkcie sprzedaży, może być wymagany maksymalnie jeden dzień.</span><span class="sxs-lookup"><span data-stu-id="16b7e-123">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="16b7e-124">Spersonalizowane listy</span><span class="sxs-lookup"><span data-stu-id="16b7e-124">Personalized lists</span></span>

<span data-ttu-id="16b7e-125">Oprócz zezwalania na personalizację istniejących wygenerowanych przez komputer list, usługa rekomendacji umożliwia personalizację środowiska wykrywania produktów zarówno w trybie online, jak i w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="16b7e-125">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="16b7e-126">Po włączeniu personalizacji w terminalach punktu sprzedaży mogą być wyświetlane listy spersonalizowane „Wybrane dla Ciebie” lub „polecane klientom”.</span><span class="sxs-lookup"><span data-stu-id="16b7e-126">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="16b7e-127">Ponadto Detaliści mogą zastosować personalizację do istniejących list rekomendacji produktów i dostarczać użytkownikom uwierzytelnionym użytkownikom ogólne rozporządzenie o ochronie danych (GDPR).</span><span class="sxs-lookup"><span data-stu-id="16b7e-127">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="16b7e-128">Wyłączenie personalizacji powoduje również wyłączenie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="16b7e-128">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="16b7e-129">Listy „Wybrane dla Ciebie” w trybie online</span><span class="sxs-lookup"><span data-stu-id="16b7e-129">Online "Picks for you" lists</span></span>

<span data-ttu-id="16b7e-130">Lista „Wybrane dla Ciebie” to sztuczna Lista materiałów do analizy (AI-ML), która pokazuje uwierzytelnionemu użytkownikowi spersonalizowaną listę sugerowanych produktów.</span><span class="sxs-lookup"><span data-stu-id="16b7e-130">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="16b7e-131">Ta lista jest oparta na wielokanałowej historii zakupów użytkownika.</span><span class="sxs-lookup"><span data-stu-id="16b7e-131">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="16b7e-132">Spersonalizowane rekomendacje są aktualizowane dynamicznie, gdy użytkownik dokonuje ponownych zakupów.</span><span class="sxs-lookup"><span data-stu-id="16b7e-132">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="16b7e-133">Ten typ listy obsługuje również filtrowanie kategorii, dzięki czemu Detaliści mogą wyświetlać propozycje na podstawie hierarchii nawigacyjnych.</span><span class="sxs-lookup"><span data-stu-id="16b7e-133">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="16b7e-134">Zanim będzie można wyświetlić listę „Wybrane dla Ciebie” na stronie handlu elektronicznego, muszą zostać spełnione następujące wymagania użytkownika:</span><span class="sxs-lookup"><span data-stu-id="16b7e-134">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="16b7e-135">Użytkownicy muszą być zalogowani.</span><span class="sxs-lookup"><span data-stu-id="16b7e-135">Users must be signed in.</span></span> <span data-ttu-id="16b7e-136">Użytkownicy anonimowi nie będą widzieli spersonalizowanych rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="16b7e-136">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="16b7e-137">Użytkownicy muszą mieć co najmniej jeden zakup na swoim koncie.</span><span class="sxs-lookup"><span data-stu-id="16b7e-137">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="16b7e-138">Użytkownicy musieli wyrazić zgodę na otrzymywanie spersonalizowanych rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="16b7e-138">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="16b7e-139">Na poniższej ilustracji przedstawiono przykład listy „Wybrane dla Ciebie” na stronie sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="16b7e-139">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Lista Wybrane dla Ciebie w trybie online](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="16b7e-141">Listy „Wybrane dla Ciebie” w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="16b7e-141">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="16b7e-142">Aby usprawnić usługi świadczone klientom, detaliści mogą personalizować istniejące strony szczegółów klientów, dodając listę kontekstową „Polecane klientom”.</span><span class="sxs-lookup"><span data-stu-id="16b7e-142">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="16b7e-143">Na poniższej ilustracji przedstawiono przykład listy „Polecane klientom” w terminalu punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="16b7e-143">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![Lista Wybrane dla Ciebie w punkcie sprzedaży](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="16b7e-145">Zastosuj personalizację do istniejących list rekomendacji</span><span class="sxs-lookup"><span data-stu-id="16b7e-145">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="16b7e-146">Detaliści mogą zastosować personalizację do istniejących list rekomendacji, takich jak „nowe”, „popularne”, „Bestsellery”, „Klienci także lubią” i „Często kupowane razem”.</span><span class="sxs-lookup"><span data-stu-id="16b7e-146">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="16b7e-147">Po zastosowaniu personalizacji do istniejących list z tych list są usuwane elementy, które zostały wcześniej zakupione przez zalogowanego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="16b7e-147">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="16b7e-148">Zarówno dla użytkowników anonimowych, jak i użytkowników, którzy zrezygnowali ze spersonalizowanych rekomendacji, zostaną wyświetlone domyślne wersje istniejących list.</span><span class="sxs-lookup"><span data-stu-id="16b7e-148">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="16b7e-149">W związku z tym detaliści nie muszą ręcznie obsługiwać oddzielnych stron.</span><span class="sxs-lookup"><span data-stu-id="16b7e-149">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="16b7e-150">Na przykład użytkownik zalogowany już kupił czarny zegarem i brązowe buty robocze, które pojawią się na liście „popularne — domyślnie” na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="16b7e-150">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="16b7e-151">Dlatego użytkownik zobaczy nowe produkty zamiast tych produktów, tak jak to pokazano na liście „Popularne — spersonalizowane”.</span><span class="sxs-lookup"><span data-stu-id="16b7e-151">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Trwa stosowanie personalizacji](./media/applypersonalization.png)

<span data-ttu-id="16b7e-153">Aby zastosować personalizację do istniejącej listy rekomendacji w module strony kreatora Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="16b7e-153">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="16b7e-154">Otwórz istniejącą stronę konstruktora witryn zawierającą moduł zbierania produktów.</span><span class="sxs-lookup"><span data-stu-id="16b7e-154">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="16b7e-155">W okienku nawigacji po lewej stronie zaznacz moduł zbierania produktów.</span><span class="sxs-lookup"><span data-stu-id="16b7e-155">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="16b7e-156">W okienku nawigacji po prawej stronie, w obszarze **Produkty**, zaznacz listę.</span><span class="sxs-lookup"><span data-stu-id="16b7e-156">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="16b7e-157">W oknie dialogowym **Wybór konfiguracji listy produktów** w obszarze **typ** wybierz typ listy.</span><span class="sxs-lookup"><span data-stu-id="16b7e-157">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="16b7e-158">Zaznacz pole wyboru **Zastosuj personalizację**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="16b7e-158">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Stosowanie personalizacji do listy popularnych produktów](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="16b7e-160">Zapisz stronę, zakończ jej edycję, a następnie ją opublikuj.</span><span class="sxs-lookup"><span data-stu-id="16b7e-160">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="16b7e-161">Po opublikowaniu strony zalogowani użytkownicy będą widzieli spersonalizowane listy popularnych produktów.</span><span class="sxs-lookup"><span data-stu-id="16b7e-161">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="16b7e-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="16b7e-162">Additional resources</span></span>

[<span data-ttu-id="16b7e-163">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="16b7e-163">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="16b7e-164">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="16b7e-164">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="16b7e-165">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="16b7e-165">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="16b7e-166">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="16b7e-166">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="16b7e-167">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="16b7e-167">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="16b7e-168">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="16b7e-168">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="16b7e-169">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="16b7e-169">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="16b7e-170">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="16b7e-170">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="16b7e-171">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="16b7e-171">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="16b7e-172">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="16b7e-172">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="16b7e-173">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="16b7e-173">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
