---
title: Włącz spersonalizowane rekomendacje produktów
description: W tym temacie opisano sposób udostępniania spersonalizowanych rekomendacji dotyczących klientów w programie Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
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
ms.openlocfilehash: 4103096f23e5568cc2bf64f21720c7c16d3e0cd1
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664865"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="922aa-103">Włącz spersonalizowane rekomendacje</span><span class="sxs-lookup"><span data-stu-id="922aa-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="922aa-104">W tym temacie opisano sposób udostępniania spersonalizowanych rekomendacji dotyczących klientów w programie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="922aa-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="922aa-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="922aa-105">Overview</span></span>

<span data-ttu-id="922aa-106">W systemie Dynamics 365 Commerce detaliści mogą udostępniać spersonalizowane rekomendacje dotyczące produktów (znane także jako Personalizacja).</span><span class="sxs-lookup"><span data-stu-id="922aa-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="922aa-107">Dzięki temu spersonalizowane rekomendacje mogą być włączane do obsługi klienta w trybie online i w punkcie sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="922aa-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="922aa-108">Gdy jest włączona funkcja personalizacji, system może skojarzyć informacje o zakupie i produkcie użytkownika w celu wygenerowania poszczególnych zaleceń dotyczących produktu.</span><span class="sxs-lookup"><span data-stu-id="922aa-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="922aa-109">Wymagania wstępne dotyczące personalizacji</span><span class="sxs-lookup"><span data-stu-id="922aa-109">Personalization prerequisites</span></span>

<span data-ttu-id="922aa-110">Przed udostępnieniem klientom spersonalizowanych rekomendacji dotyczących produktów należy zauważyć, że zalecenia dotyczące produktów są obsługiwane tylko dla użytkowników systemu Commerce, którzy dokonali migracji swoich magazynów do usługi Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="922aa-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="922aa-111">Zanim klienci będą mogli uzyskać spersonalizowane zalecenia dotyczące produktów, muszą [włączyć rekomendacje produktów](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="922aa-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="922aa-112">Włączając rekomendacje dotyczące produktów, Włącz również opcję Personalizacja.</span><span class="sxs-lookup"><span data-stu-id="922aa-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="922aa-113">Jeśli jednak wyłączysz personalizację, nie wyłączasz innych typów rekomendacji dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="922aa-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="922aa-114">Aby uzyskać więcej informacji na temat rekomendacji produktów, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="922aa-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="922aa-115">Włącz personalizację</span><span class="sxs-lookup"><span data-stu-id="922aa-115">Turn on personalization</span></span>

<span data-ttu-id="922aa-116">Aby włączyć personalizację, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="922aa-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="922aa-117">Przejdź do **Handel detaliczny i komercyjny \> Rekomendacje produktów \> Właściwości rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="922aa-117">Go to **Retail and commerce \> Product recommendations \> Recommendation parameters**.</span></span>
1. <span data-ttu-id="922aa-118">Na liście udostępnionych parametrów sieci sprzedaży wybierz **listy rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="922aa-118">In the list of Retail shared parameters, select **Recommendation lists**.</span></span>
1. <span data-ttu-id="922aa-119">Ustaw wartość **Tak** opcji **Włącz personalizację**.</span><span class="sxs-lookup"><span data-stu-id="922aa-119">Set the **Enable personalization** option to **Yes**.</span></span>

![Włączanie personalizacji](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="922aa-121">Po włączeniu personalizacji zostanie rozpoczęty proces generowania spersonalizowanych list rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="922aa-121">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="922aa-122">Zanim te listy będą dostępne i widoczne w trybie online i w punkcie sprzedaży, może być wymagany maksymalnie jeden dzień.</span><span class="sxs-lookup"><span data-stu-id="922aa-122">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="922aa-123">Spersonalizowane listy</span><span class="sxs-lookup"><span data-stu-id="922aa-123">Personalized lists</span></span>

<span data-ttu-id="922aa-124">Oprócz zezwalania na personalizację istniejących wygenerowanych przez komputer list, usługa rekomendacji umożliwia personalizację środowiska wykrywania produktów zarówno w trybie online, jak i w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="922aa-124">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="922aa-125">Po włączeniu personalizacji w terminalach punktu sprzedaży mogą być wyświetlane listy spersonalizowane „Wybrane dla Ciebie” lub „polecane klientom”.</span><span class="sxs-lookup"><span data-stu-id="922aa-125">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="922aa-126">Ponadto Detaliści mogą zastosować personalizację do istniejących list rekomendacji produktów i dostarczać użytkownikom uwierzytelnionym użytkownikom ogólne rozporządzenie o ochronie danych (GDPR).</span><span class="sxs-lookup"><span data-stu-id="922aa-126">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="922aa-127">Wyłączenie personalizacji powoduje również wyłączenie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="922aa-127">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="922aa-128">Listy „Wybrane dla Ciebie” w trybie online</span><span class="sxs-lookup"><span data-stu-id="922aa-128">Online "Picks for you" lists</span></span>

<span data-ttu-id="922aa-129">Lista „Wybrane dla Ciebie” to sztuczna Lista materiałów do analizy (AI-ML), która pokazuje uwierzytelnionemu użytkownikowi spersonalizowaną listę sugerowanych produktów.</span><span class="sxs-lookup"><span data-stu-id="922aa-129">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="922aa-130">Ta lista jest oparta na wielokanałowej historii zakupów użytkownika.</span><span class="sxs-lookup"><span data-stu-id="922aa-130">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="922aa-131">Spersonalizowane rekomendacje są aktualizowane dynamicznie, gdy użytkownik dokonuje ponownych zakupów.</span><span class="sxs-lookup"><span data-stu-id="922aa-131">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="922aa-132">Ten typ listy obsługuje również filtrowanie kategorii, dzięki czemu Detaliści mogą wyświetlać propozycje na podstawie hierarchii nawigacyjnych.</span><span class="sxs-lookup"><span data-stu-id="922aa-132">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="922aa-133">Zanim będzie można wyświetlić listę „Wybrane dla Ciebie” na stronie handlu elektronicznego, muszą zostać spełnione następujące wymagania użytkownika:</span><span class="sxs-lookup"><span data-stu-id="922aa-133">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="922aa-134">Użytkownicy muszą być zalogowani.</span><span class="sxs-lookup"><span data-stu-id="922aa-134">Users must be signed in.</span></span> <span data-ttu-id="922aa-135">Użytkownicy anonimowi nie będą widzieli spersonalizowanych rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="922aa-135">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="922aa-136">Użytkownicy muszą mieć co najmniej jeden zakup na swoim koncie.</span><span class="sxs-lookup"><span data-stu-id="922aa-136">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="922aa-137">Użytkownicy musieli wyrazić zgodę na otrzymywanie spersonalizowanych rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="922aa-137">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="922aa-138">Na poniższej ilustracji przedstawiono przykład listy „Wybrane dla Ciebie” na stronie sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="922aa-138">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Lista Wybrane dla Ciebie w trybie online](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="922aa-140">Listy „Wybrane dla Ciebie” w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="922aa-140">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="922aa-141">Aby usprawnić usługi świadczone klientom, detaliści mogą personalizować istniejące strony szczegółów klientów, dodając listę kontekstową „Polecane klientom”.</span><span class="sxs-lookup"><span data-stu-id="922aa-141">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="922aa-142">Na poniższej ilustracji przedstawiono przykład listy „Polecane klientom” w terminalu punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="922aa-142">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![Lista Wybrane dla Ciebie w punkcie sprzedaży](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="922aa-144">Zastosuj personalizację do istniejących list rekomendacji</span><span class="sxs-lookup"><span data-stu-id="922aa-144">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="922aa-145">Detaliści mogą zastosować personalizację do istniejących list rekomendacji, takich jak „nowe”, „popularne”, „Bestsellery”, „Klienci także lubią” i „Często kupowane razem”.</span><span class="sxs-lookup"><span data-stu-id="922aa-145">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="922aa-146">Po zastosowaniu personalizacji do istniejących list z tych list są usuwane elementy, które zostały wcześniej zakupione przez zalogowanego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="922aa-146">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="922aa-147">Zarówno dla użytkowników anonimowych, jak i użytkowników, którzy zrezygnowali ze spersonalizowanych rekomendacji, zostaną wyświetlone domyślne wersje istniejących list.</span><span class="sxs-lookup"><span data-stu-id="922aa-147">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="922aa-148">W związku z tym detaliści nie muszą ręcznie obsługiwać oddzielnych stron.</span><span class="sxs-lookup"><span data-stu-id="922aa-148">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="922aa-149">Na przykład użytkownik zalogowany już kupił czarny zegarem i brązowe buty robocze, które pojawią się na liście „popularne — domyślnie” na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="922aa-149">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="922aa-150">Dlatego użytkownik zobaczy nowe produkty zamiast tych produktów, tak jak to pokazano na liście „Popularne — spersonalizowane”.</span><span class="sxs-lookup"><span data-stu-id="922aa-150">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Trwa stosowanie personalizacji](./media/applypersonalization.png)

<span data-ttu-id="922aa-152">Aby zastosować personalizację do istniejącej listy rekomendacji w module strony kreatora Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="922aa-152">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="922aa-153">Otwórz istniejącą stronę konstruktora witryn zawierającą moduł zbierania produktów.</span><span class="sxs-lookup"><span data-stu-id="922aa-153">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="922aa-154">W okienku nawigacji po lewej stronie zaznacz moduł zbierania produktów.</span><span class="sxs-lookup"><span data-stu-id="922aa-154">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="922aa-155">W okienku nawigacji po prawej stronie, w obszarze **Produkty**, zaznacz listę.</span><span class="sxs-lookup"><span data-stu-id="922aa-155">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="922aa-156">W oknie dialogowym **Wybór konfiguracji listy produktów** w obszarze **typ** wybierz typ listy.</span><span class="sxs-lookup"><span data-stu-id="922aa-156">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="922aa-157">Zaznacz pole wyboru **Zastosuj personalizację**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="922aa-157">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Stosowanie personalizacji do listy popularnych produktów](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="922aa-159">Zapisz stronę, zakończ jej edycję, a następnie ją opublikuj.</span><span class="sxs-lookup"><span data-stu-id="922aa-159">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="922aa-160">Po opublikowaniu strony zalogowani użytkownicy będą widzieli spersonalizowane listy popularnych produktów.</span><span class="sxs-lookup"><span data-stu-id="922aa-160">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="922aa-161">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="922aa-161">Additional resources</span></span>

[<span data-ttu-id="922aa-162">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="922aa-162">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="922aa-163">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="922aa-163">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="922aa-164">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="922aa-164">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="922aa-165">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="922aa-165">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="922aa-166">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="922aa-166">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="922aa-167">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="922aa-167">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="922aa-168">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="922aa-168">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="922aa-169">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="922aa-169">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="922aa-170">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="922aa-170">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="922aa-171">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="922aa-171">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="922aa-172">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="922aa-172">Product recommendations FAQ</span></span>](faq-recommendations.md)
