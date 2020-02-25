---
title: Włącz spersonalizowane rekomendacje produktów
description: W tym temacie opisano sposób udostępniania spersonalizowanych rekomendacji dotyczących klientów w programie Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 01/28/2020
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
ms.openlocfilehash: 6b3c6140b8bd3ea15458223c0f61810421d0b2bc
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025274"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="6e94e-103">Włącz spersonalizowane rekomendacje</span><span class="sxs-lookup"><span data-stu-id="6e94e-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6e94e-104">W tym temacie opisano sposób udostępniania spersonalizowanych rekomendacji dotyczących klientów w programie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6e94e-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6e94e-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6e94e-105">Overview</span></span>

<span data-ttu-id="6e94e-106">W systemie Dynamics 365 Commerce detaliści mogą udostępniać spersonalizowane rekomendacje dotyczące produktów (znane także jako Personalizacja).</span><span class="sxs-lookup"><span data-stu-id="6e94e-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="6e94e-107">Dzięki temu spersonalizowane rekomendacje mogą być włączane do obsługi klienta w trybie online i w punkcie sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="6e94e-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="6e94e-108">Gdy jest włączona funkcja personalizacji, system może skojarzyć informacje o zakupie i produkcie użytkownika w celu wygenerowania poszczególnych zaleceń dotyczących produktu.</span><span class="sxs-lookup"><span data-stu-id="6e94e-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="6e94e-109">Wymagania wstępne dotyczące personalizacji</span><span class="sxs-lookup"><span data-stu-id="6e94e-109">Personalization prerequisites</span></span>

<span data-ttu-id="6e94e-110">Przed udostępnieniem klientom spersonalizowanych rekomendacji dotyczących produktów należy zauważyć, że zalecenia dotyczące produktów są obsługiwane tylko dla użytkowników systemu Commerce, którzy dokonali migracji swoich magazynów do usługi Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="6e94e-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="6e94e-111">Zanim klienci będą mogli uzyskać spersonalizowane zalecenia dotyczące produktów, muszą [włączyć rekomendacje produktów](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6e94e-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6e94e-112">Włączając rekomendacje dotyczące produktów, Włącz również opcję Personalizacja.</span><span class="sxs-lookup"><span data-stu-id="6e94e-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="6e94e-113">Jeśli jednak wyłączysz personalizację, nie wyłączasz innych typów rekomendacji dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="6e94e-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="6e94e-114">Aby uzyskać więcej informacji na temat rekomendacji produktów, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6e94e-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="6e94e-115">Włącz personalizację</span><span class="sxs-lookup"><span data-stu-id="6e94e-115">Turn on personalization</span></span>

<span data-ttu-id="6e94e-116">Aby włączyć personalizację, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6e94e-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="6e94e-117">Przejdź do **Handel detaliczny i komercyjny \> Rekomendacje produktów \> Właściwości rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="6e94e-117">Go to **Retail and commerce \> Product recommendations \> Recommendation parameters**.</span></span>
1. <span data-ttu-id="6e94e-118">Na liście udostępnionych parametrów sieci sprzedaży wybierz **listy rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="6e94e-118">In the list of Retail shared parameters, select **Recommendation lists**.</span></span>
1. <span data-ttu-id="6e94e-119">Ustaw wartość **Tak** opcji **Włącz personalizację**.</span><span class="sxs-lookup"><span data-stu-id="6e94e-119">Set the **Enable personalization** option to **Yes**.</span></span>

![Włączanie personalizacji](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="6e94e-121">Po włączeniu personalizacji zostanie rozpoczęty proces generowania spersonalizowanych list rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="6e94e-121">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="6e94e-122">Zanim te listy będą dostępne i widoczne w trybie online i w punkcie sprzedaży, może być wymagany maksymalnie jeden dzień.</span><span class="sxs-lookup"><span data-stu-id="6e94e-122">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="6e94e-123">Spersonalizowane listy</span><span class="sxs-lookup"><span data-stu-id="6e94e-123">Personalized lists</span></span>

<span data-ttu-id="6e94e-124">Oprócz zezwalania na personalizację istniejących wygenerowanych przez komputer list, usługa rekomendacji umożliwia personalizację środowiska wykrywania produktów zarówno w trybie online, jak i w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6e94e-124">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="6e94e-125">Po włączeniu personalizacji w terminalach punktu sprzedaży mogą być wyświetlane listy spersonalizowane „Wybrane dla Ciebie” lub „polecane klientom”.</span><span class="sxs-lookup"><span data-stu-id="6e94e-125">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="6e94e-126">Ponadto Detaliści mogą zastosować personalizację do istniejących list rekomendacji produktów i dostarczać użytkownikom uwierzytelnionym użytkownikom ogólne rozporządzenie o ochronie danych (GDPR).</span><span class="sxs-lookup"><span data-stu-id="6e94e-126">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="6e94e-127">Wyłączenie personalizacji powoduje również wyłączenie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="6e94e-127">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="6e94e-128">Listy „Wybrane dla Ciebie” w trybie online</span><span class="sxs-lookup"><span data-stu-id="6e94e-128">Online "Picks for you" lists</span></span>

<span data-ttu-id="6e94e-129">Lista „Wybrane dla Ciebie” to sztuczna Lista materiałów do analizy (AI-ML), która pokazuje uwierzytelnionemu użytkownikowi spersonalizowaną listę sugerowanych produktów.</span><span class="sxs-lookup"><span data-stu-id="6e94e-129">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="6e94e-130">Ta lista jest oparta na wielokanałowej historii zakupów użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6e94e-130">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="6e94e-131">Spersonalizowane rekomendacje są aktualizowane dynamicznie, gdy użytkownik dokonuje ponownych zakupów.</span><span class="sxs-lookup"><span data-stu-id="6e94e-131">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="6e94e-132">Ten typ listy obsługuje również filtrowanie kategorii, dzięki czemu Detaliści mogą wyświetlać propozycje na podstawie hierarchii nawigacyjnych.</span><span class="sxs-lookup"><span data-stu-id="6e94e-132">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="6e94e-133">Zanim będzie można wyświetlić listę „Wybrane dla Ciebie” na stronie handlu elektronicznego, muszą zostać spełnione następujące wymagania użytkownika:</span><span class="sxs-lookup"><span data-stu-id="6e94e-133">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="6e94e-134">Użytkownicy muszą być zalogowani.</span><span class="sxs-lookup"><span data-stu-id="6e94e-134">Users must be signed in.</span></span> <span data-ttu-id="6e94e-135">Użytkownicy anonimowi nie będą widzieli spersonalizowanych rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="6e94e-135">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="6e94e-136">Użytkownicy muszą mieć co najmniej jeden zakup na swoim koncie.</span><span class="sxs-lookup"><span data-stu-id="6e94e-136">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="6e94e-137">Użytkownicy musieli wyrazić zgodę na otrzymywanie spersonalizowanych rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="6e94e-137">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="6e94e-138">Na poniższej ilustracji przedstawiono przykład listy „Wybrane dla Ciebie” na stronie sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="6e94e-138">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Lista Wybrane dla Ciebie w trybie online](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="6e94e-140">Listy „Wybrane dla Ciebie” w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6e94e-140">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="6e94e-141">Aby usprawnić usługi świadczone klientom, detaliści mogą personalizować istniejące strony szczegółów klientów, dodając listę kontekstową „Polecane klientom”.</span><span class="sxs-lookup"><span data-stu-id="6e94e-141">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="6e94e-142">Na poniższej ilustracji przedstawiono przykład listy „Polecane klientom” w terminalu punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6e94e-142">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![Lista Wybrane dla Ciebie w punkcie sprzedaży](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="6e94e-144">Zastosuj personalizację do istniejących list rekomendacji</span><span class="sxs-lookup"><span data-stu-id="6e94e-144">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="6e94e-145">Detaliści mogą zastosować personalizację do istniejących list rekomendacji, takich jak „nowe”, „popularne”, „Bestsellery”, „Klienci także lubią” i „Często kupowane razem”.</span><span class="sxs-lookup"><span data-stu-id="6e94e-145">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="6e94e-146">Po zastosowaniu personalizacji do istniejących list z tych list są usuwane elementy, które zostały wcześniej zakupione przez zalogowanego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6e94e-146">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="6e94e-147">Zarówno dla użytkowników anonimowych, jak i użytkowników, którzy zrezygnowali ze spersonalizowanych rekomendacji, zostaną wyświetlone domyślne wersje istniejących list.</span><span class="sxs-lookup"><span data-stu-id="6e94e-147">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="6e94e-148">W związku z tym detaliści nie muszą ręcznie obsługiwać oddzielnych stron.</span><span class="sxs-lookup"><span data-stu-id="6e94e-148">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="6e94e-149">Na przykład użytkownik zalogowany już kupił czarny zegarem i brązowe buty robocze, które pojawią się na liście „popularne — domyślnie” na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="6e94e-149">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="6e94e-150">Dlatego użytkownik zobaczy nowe produkty zamiast tych produktów, tak jak to pokazano na liście „Popularne — spersonalizowane”.</span><span class="sxs-lookup"><span data-stu-id="6e94e-150">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Trwa stosowanie personalizacji](./media/applypersonalization.png)

<span data-ttu-id="6e94e-152">Aby zastosować personalizację do istniejącej listy rekomendacji w module strony kreatora Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6e94e-152">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="6e94e-153">Otwórz istniejącą stronę konstruktora witryn zawierającą moduł zbierania produktów.</span><span class="sxs-lookup"><span data-stu-id="6e94e-153">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="6e94e-154">W okienku nawigacji po lewej stronie zaznacz moduł zbierania produktów.</span><span class="sxs-lookup"><span data-stu-id="6e94e-154">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="6e94e-155">W okienku nawigacji po prawej stronie, w obszarze **Produkty**, zaznacz listę.</span><span class="sxs-lookup"><span data-stu-id="6e94e-155">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="6e94e-156">W oknie dialogowym **Wybór konfiguracji listy produktów** w obszarze **typ** wybierz typ listy.</span><span class="sxs-lookup"><span data-stu-id="6e94e-156">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="6e94e-157">Zaznacz pole wyboru **Zastosuj personalizację**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e94e-157">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Stosowanie personalizacji do listy popularnych produktów](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="6e94e-159">Zapisz stronę, zakończ jej edycję, a następnie ją opublikuj.</span><span class="sxs-lookup"><span data-stu-id="6e94e-159">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="6e94e-160">Po opublikowaniu strony zalogowani użytkownicy będą widzieli spersonalizowane listy popularnych produktów.</span><span class="sxs-lookup"><span data-stu-id="6e94e-160">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6e94e-161">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6e94e-161">Additional resources</span></span>

[<span data-ttu-id="6e94e-162">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="6e94e-162">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="6e94e-163">Włączanie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="6e94e-163">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="6e94e-164">Rozporządzenie RODO i rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="6e94e-164">GDPR and product recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="6e94e-165">Dodawanie list rekomendacji produktów do stron</span><span class="sxs-lookup"><span data-stu-id="6e94e-165">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="6e94e-166">Dodaj panel rekomendacji do urządzeń punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="6e94e-166">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="6e94e-167">Omówienie modułu kolekcji produktów</span><span class="sxs-lookup"><span data-stu-id="6e94e-167">Product collection module overview</span></span>](product-collection-module-overview.md)
