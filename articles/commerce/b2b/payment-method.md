---
title: Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B
description: W tym temacie opisano sposób konfigurowania metody płatności na konto odbiorcy dla witryn handlu elektronicznego (B2B) firmy.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 754e2f83d6c8ff5d3698d98062e54bba7ccd9836
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035951"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a><span data-ttu-id="976ad-103">Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B</span><span class="sxs-lookup"><span data-stu-id="976ad-103">Configure the customer account payment method for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="976ad-104">W tym temacie opisano sposób konfigurowania metody płatności na konto odbiorcy dla witryn handlu elektronicznego (B2B) firmy.</span><span class="sxs-lookup"><span data-stu-id="976ad-104">This topic describes how to configure the customer account payment method for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="976ad-105">Sprzadawcy detaliczni mogą akceptować różne typy płatności w zamian za produkty i usługi, które sprzedają w kanale handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="976ad-105">Retailers can accept various types of payment in exchange for the products and services that they sell in an e-commerce channel.</span></span> <span data-ttu-id="976ad-106">Każdy typ płatności akceptowany przez sprzedawcę detalicznego musi zostać skonfigurowany w Microsoft Dynamics 365 Commerce na etapie konfiguracji systemu.</span><span class="sxs-lookup"><span data-stu-id="976ad-106">Each payment type that a retailer accepts must be configured in Microsoft Dynamics 365 Commerce when the system is set up.</span></span> <span data-ttu-id="976ad-107">W witrynach B2B handlu elektronicznego musi być obsługiwana metoda płatności konto odbiorcy (lub metoda płatności na konto).</span><span class="sxs-lookup"><span data-stu-id="976ad-107">The customer account (or "on account") payment method must be supported on B2B e-commerce sites.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="976ad-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="976ad-108">Prerequisites</span></span>

1. <span data-ttu-id="976ad-109">Dodaj metodę płatności konta odbiorcy w Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="976ad-109">Add the customer account payment method in Commerce headquarters.</span></span>
2. <span data-ttu-id="976ad-110">Skojarz metodę płatności konta odbiorcy z kanałem handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="976ad-110">Associate the customer account payment method with the e-commerce channel.</span></span>
3. <span data-ttu-id="976ad-111">Upewnij się, że opcja **Zezwalaj na akonto** jest włączona dla odbiorcy w **Retail i Commerce \> Odbiorcy \> Wszyscy odbiorcy \> Ustawienia domyślne płatności** w Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="976ad-111">Make sure that **Allow on account** is enabled for the customer at **Retail and Commerce \> Customers \> All customers \> Payment defaults** in Commerce headquarters.</span></span> <span data-ttu-id="976ad-112">Ponadto upewnij się, że parametry **Limitu kredytu** są odpowiednio ustawione dla odbiorcy w **Retail i Commerce \> Odbiorcy \> Wszysyc odbiorcy \> Kredyty i windykacja** w Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="976ad-112">Also make sure that **Credit limit** parameters are set appropriately for the customer at **Retail and Commerce \> Customers \> All customers \> Credit and Collections** in Commerce headquarters.</span></span> 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a><span data-ttu-id="976ad-113">Włącz metodę płatności na koncie klienta w narzędziu do tworzenia witryn Commerce</span><span class="sxs-lookup"><span data-stu-id="976ad-113">Enable the customer account payment method in Commerce site builder</span></span> 

<span data-ttu-id="976ad-114">Aby włączyć metodę płatności dla konta klienta w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="976ad-114">To enable the customer account payment method in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="976ad-115">Przejdź do **Ustawień witryny \> Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="976ad-115">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="976ad-116">Ustaw właściwość **Włącz płatności konta odbiorcy** na **Włącz dla odbiorców B2B**.</span><span class="sxs-lookup"><span data-stu-id="976ad-116">Set the **Enable customer account payments** property to **Enabled for B2B customers**.</span></span> 
1. <span data-ttu-id="976ad-117">Wybierz **Zapisz i opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="976ad-117">Select **Save and Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="976ad-118">Nowe ustawienia witryny zostaną wprowadzone dopiero po zaktualizowaniu pliku app.settings.json.</span><span class="sxs-lookup"><span data-stu-id="976ad-118">The new site settings take effect only after the app.settings.json file is updated.</span></span> <span data-ttu-id="976ad-119">Aby uzyskać więcej informacji, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](../e-commerce-extensibility/sdk-updates.md).</span><span class="sxs-lookup"><span data-stu-id="976ad-119">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md).</span></span>

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a><span data-ttu-id="976ad-120">Włącz metodę płatności na koncie klienta na stronie kasy w witrynie handlu elektronicznego B2B</span><span class="sxs-lookup"><span data-stu-id="976ad-120">Enable the customer account payment method on the checkout page for the B2B e-commerce site</span></span>

<span data-ttu-id="976ad-121">Aby włączyć metodę płatności na koncie klienta na stronie kasy w witrynie handlu elektronicznego B2B, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="976ad-121">To enable the customer account payment method on the checkout page for the B2B e-commerce site, follow these steps.</span></span>

1. <span data-ttu-id="976ad-122">W narzędziu do tworzenia witryn Commerce znajdź i edytuj stronę kasy lub fragment, który zawiera moduł kasy dla witryny handlu elektronicznego B2B.</span><span class="sxs-lookup"><span data-stu-id="976ad-122">In Commerce site builder, find and edit the checkout page or fragment that contains the checkout module for the B2B e-commerce site.</span></span>
1. <span data-ttu-id="976ad-123">W gnieździe **Kontener sekcji wyewidencjonowywania** wybierz opcję **Dodaj moduł**, a następnie dodaj moduł **Płatność na konto klienta**.</span><span class="sxs-lookup"><span data-stu-id="976ad-123">In the **Checkout section container** slot, select **Add Module**, and then add a **Customer account payment** module.</span></span>
1. <span data-ttu-id="976ad-124">Umieść moduł **Płatność na konto klienta**, zaznaczając wielokropek (**...**), a następnie w razie potrzeby **Przenieś w górę** lub **Przenieś w dół**.</span><span class="sxs-lookup"><span data-stu-id="976ad-124">Position the **Customer account payment** module by selecting the ellipsis (**...**), and then selecting **Move Up** or **Move Down** as required.</span></span>
1. <span data-ttu-id="976ad-125">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="976ad-125">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a><span data-ttu-id="976ad-126">Potwierdź, że metoda płatności na koncie odbiorcy została włączona i opublikowana</span><span class="sxs-lookup"><span data-stu-id="976ad-126">Confirm that the customer account payment method has been enabled and published</span></span>

<span data-ttu-id="976ad-127">Aby potwierdzić, że metoda płatności na koncie klienta została włączona, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="976ad-127">To confirm that the customer account payment method has been enabled, follow these steps.</span></span>

1. <span data-ttu-id="976ad-128">Zaloguj się w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="976ad-128">Sign in to the e-commerce site.</span></span>
1. <span data-ttu-id="976ad-129">Dodaj produkt do koszyka.</span><span class="sxs-lookup"><span data-stu-id="976ad-129">Add a product to the cart.</span></span>
1. <span data-ttu-id="976ad-130">Przechodzenie do strony realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="976ad-130">Go to the checkout page.</span></span> <span data-ttu-id="976ad-131">Powinna zostać wyświetlony nowa metoda płatności na **Koncie odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="976ad-131">You should see the new **Customer Account** payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="976ad-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="976ad-132">Additional resources</span></span>

[<span data-ttu-id="976ad-133">Konfigurowanie witryny handlu elektornicznego B2B</span><span class="sxs-lookup"><span data-stu-id="976ad-133">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="976ad-134">Tworzenie hierarchii modelowania organizacji dla organizacji B2B</span><span class="sxs-lookup"><span data-stu-id="976ad-134">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="976ad-135">Zarządzaj użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B</span><span class="sxs-lookup"><span data-stu-id="976ad-135">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="976ad-136">Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="976ad-136">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)

[<span data-ttu-id="976ad-137">Aktualizacje zestawu SDK i biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="976ad-137">SDK and Module library updates</span></span>](../e-commerce-extensibility/sdk-updates.md)
