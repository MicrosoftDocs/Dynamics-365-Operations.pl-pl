---
title: Łącze logowania jest przekierowywany z powrotem do witryny handlu elektronicznego
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc przy przekierowywanym łączu logowania z powrotem do witryny handlu elektronicznego, a nie na stronę logowania.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: a1d0ae4e487c391020947c607d5d7cb5d1ba6af4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020610"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a><span data-ttu-id="5f7d9-103">Łącze logowania jest przekierowywany z powrotem do witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="5f7d9-103">Sign-in link redirects back to an e-commerce site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5f7d9-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc przy przekierowywanym łączu logowania z powrotem do witryny handlu elektronicznego, a nie na stronę logowania.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-104">This topic provides troubleshooting guidance that can help when a sign-in link redirects back to the e-commerce site instead of going to the sign-in page.</span></span>

## <a name="description"></a><span data-ttu-id="5f7d9-105">opis</span><span class="sxs-lookup"><span data-stu-id="5f7d9-105">Description</span></span>

<span data-ttu-id="5f7d9-106">Po skonfigurowaniu nowej dzierżawy usługi Microsoft Azure Active Directory B2C (Azure AD B2C) w Konstruktorze witryn Commerce użytkownicy, którzy wybiorą łącze **Logowania**, są przekierowywani z powrotem do głównej strony docelowej witryny usługi handlu elektronicznego, bez konieczności logowania się do tej strony.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-106">After you configure a new Microsoft Azure Active Directory B2C (Azure AD B2C) tenant in Commerce site builder, users who select the **Sign in** link are redirected back to the main e-commerce landing page without going to the sign-in page.</span></span>

## <a name="resolution"></a><span data-ttu-id="5f7d9-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="5f7d9-107">Resolution</span></span>

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a><span data-ttu-id="5f7d9-108">Potwierdź, że adres URL odpowiedzi jest poprawnie skonfigurowany w aplikacji Azure AD B2C</span><span class="sxs-lookup"><span data-stu-id="5f7d9-108">Confirm that the reply URL is correctly configured in the Azure AD B2C application</span></span>

<span data-ttu-id="5f7d9-109">Aby potwierdzić, że adres URL odpowiedzi jest poprawnie skonfigurowany w aplikacji Azure AD B2C, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-109">To confirm that the reply URL is correctly configured in the Azure AD B2C application, follow these steps.</span></span>

1. <span data-ttu-id="5f7d9-110">Przejdź do [portalu Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="5f7d9-110">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="5f7d9-111">Wybierz aplikację Azure AD B2C utworzoną dla swojego dostępu do witryny.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-111">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="5f7d9-112">Wybierz aplikację utworzoną podczas konfigurowania Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-112">Select the application that you created during the Azure AD B2C setup.</span></span>
1. <span data-ttu-id="5f7d9-113">W obszarze **Adres URL odpowiedzi** upewnij się, że lista zawiera wpisy zarówno dla adresu URL domeny witryny, jak i adresu URL wygenerowanego w portalu e-commerce, jak pokazano na przykładzie na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-113">Under **Reply URL**, make sure that the list includes entries for both the site domain URL and the e-commerce-generated URL, as shown in the example in the following illustration.</span></span>

    ![Wpisy adresu URL odpowiedzi Azure AD B2C](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> <span data-ttu-id="5f7d9-115">Zarówno adres URL domeny witryny, jak i adres URL generowany przez e-commerce muszą mieć prawidłowy format adresu URL, który nie zawiera początkowych ani końcowych ukośników.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-115">Both the site domain URL and the e-commerce-generated URL must be in a valid URL format that doesn't include leading or trailing slashes.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5f7d9-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5f7d9-116">Additional resources</span></span>

[<span data-ttu-id="5f7d9-117">Zarejestruj połączoną aplikację sieci Web w Azure Active Directory B2C</span><span class="sxs-lookup"><span data-stu-id="5f7d9-117">Register a web application in Azure Active Directory B2C</span></span>](/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[<span data-ttu-id="5f7d9-118">Konfigurowanie dzierżawy B2C w module Commerce</span><span class="sxs-lookup"><span data-stu-id="5f7d9-118">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)