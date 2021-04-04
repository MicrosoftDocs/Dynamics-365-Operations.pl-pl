---
title: Ograniczenie dostępu do sklepu podczas testowania lub rozwoju
description: W tym temacie wyjaśniono, jak ograniczyć dostęp do sklepu Microsoft Dynamics 365 Commerce podczas wewnętrznego testowania lub testowania.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2cdf131048e0fac940475322294ed99e76c0a53b
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585487"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a><span data-ttu-id="2d336-103">Ograniczenie dostępu do sklepu podczas testowania lub rozwoju</span><span class="sxs-lookup"><span data-stu-id="2d336-103">Restrict access to a storefront during testing or development</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d336-104">W tym temacie wyjaśniono, jak ograniczyć dostęp do sklepu Microsoft Dynamics 365 Commerce podczas wewnętrznego testowania lub testowania.</span><span class="sxs-lookup"><span data-stu-id="2d336-104">This topic explains how to restrict access to a Microsoft Dynamics 365 Commerce storefront while internal testing or development is occurring.</span></span>

## <a name="description"></a><span data-ttu-id="2d336-105">opis</span><span class="sxs-lookup"><span data-stu-id="2d336-105">Description</span></span>

<span data-ttu-id="2d336-106">Podczas testowania wewnętrznego lub aktywnego testowania można ograniczyć dostęp do witryny, aby uniemożliwić użytkownikom zewnętrznym dostęp do opublikowanych stron sklepu.</span><span class="sxs-lookup"><span data-stu-id="2d336-106">During internal testing or active development, you might want to restrict access to your site to prevent external users from accessing the published storefront pages.</span></span>

## <a name="resolution"></a><span data-ttu-id="2d336-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="2d336-107">Resolution</span></span>

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a><span data-ttu-id="2d336-108">Konfigurowanie Azure AD B2C przy użyciu standardowych przepływów użytkownika</span><span class="sxs-lookup"><span data-stu-id="2d336-108">Set up Azure AD B2C by using standard user flows</span></span>

<span data-ttu-id="2d336-109">Aby uzyskać informacje dotyczące konfigurowania Azure Active Directory B2C (Azure AD B2C) dla witryny e-commerce, zobacz temat [Konfigurowanie dzierżawy usług B2C w Commerce](../set-up-b2c-tenant.md).</span><span class="sxs-lookup"><span data-stu-id="2d336-109">For information about how to configure Azure Active Directory B2C (Azure AD B2C) for your e-commerce site, see [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md).</span></span>

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a><span data-ttu-id="2d336-110">Ogranicz dostęp użytkowników do stron sklepu i zablokuj tworzenie nowych użytkowników</span><span class="sxs-lookup"><span data-stu-id="2d336-110">Restrict user access to storefront pages and block the creation of new users</span></span>

<span data-ttu-id="2d336-111">Aby ograniczyć użytkownikom dostęp do stron sklepu w Konstruktorze witryn portalu Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2d336-111">To restrict user access to storefront pages in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="2d336-112">Przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="2d336-112">Go to your site.</span></span>
1. <span data-ttu-id="2d336-113">Wybierz **Strony**, a następnie wybierz stronę, dla których chcesz ograniczyć dostęp użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2d336-113">Select **Pages**, and then select the page to restrict user access for.</span></span>
1. <span data-ttu-id="2d336-114">Wybierz moduł lub gniazdo fragmentu, a następnie **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2d336-114">Select the module or fragment slot, and then select **Edit**.</span></span>
1. <span data-ttu-id="2d336-115">W okienku właściwości wybierz opcję **Wymaga zalogowania**, a następnie wybierz opcję **Zakończ edytowanie**.</span><span class="sxs-lookup"><span data-stu-id="2d336-115">In the properties pane, select **Requires sign-in?**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="2d336-116">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="2d336-116">Select **Publish**.</span></span>

<span data-ttu-id="2d336-117">Aby zablokować tworzenie nowych użytkowników Azure AD w tej części, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2d336-117">To block the creation of new users in Azure AD, follow these steps.</span></span>

1. <span data-ttu-id="2d336-118">Przejdź do [portalu Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="2d336-118">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="2d336-119">Wybierz aplikację Azure AD B2C utworzoną dla swojego dostępu do witryny.</span><span class="sxs-lookup"><span data-stu-id="2d336-119">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="2d336-120">W okienku nawigacji po lewej stronie wybierz pozycję **Przepływy użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="2d336-120">In the left navigation, select **User flows**.</span></span>
1. <span data-ttu-id="2d336-121">U góry strony **Przepływy użytkowników** wybierz **Nowy przepływ użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="2d336-121">At the top of the **User Flows** page, select **New user flow**.</span></span>
1. <span data-ttu-id="2d336-122">Na stronie **Wybierz typ przepływu użytkownika** wybierz pozycję **Podgląd**.</span><span class="sxs-lookup"><span data-stu-id="2d336-122">On the **Select a user flow type** page, select **Preview**.</span></span>
1. <span data-ttu-id="2d336-123">W środku strony wybierz pozycję **Zaloguj się w wersji 2**.</span><span class="sxs-lookup"><span data-stu-id="2d336-123">In the middle of the page, select **Sign in v2**.</span></span> <span data-ttu-id="2d336-124">Następnie wykonaj kroki w witrynie [Konfigurowanie dzierżawy usług B2C w Commerce](../set-up-b2c-tenant.md), aby skonfigurować przepływ jako standardowy przepływ użytkownika dla usługi Azure AD B2C w witrynie podczas testowania lub rozwoju.</span><span class="sxs-lookup"><span data-stu-id="2d336-124">Then follow the steps in [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md) to configure the flow as your site's standard user flow for Azure AD B2C during testing or development.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2d336-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2d336-125">Additional resources</span></span>

[<span data-ttu-id="2d336-126">Konfigurowanie dzierżawy B2C w module Commerce</span><span class="sxs-lookup"><span data-stu-id="2d336-126">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)

[<span data-ttu-id="2d336-127">Konfiguracja stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="2d336-127">Set up custom pages for user sign-ins</span></span>](../custom-pages-user-logins.md)
