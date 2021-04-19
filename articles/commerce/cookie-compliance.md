---
title: Zgodność z plikami cookie
description: W tym temacie opisano zagadnienia dotyczące zgodności z plikami cookie i domyślnych zasad, które są zawarte w aplikacji Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2cc2089bc3052c0c59cb0414f8301123a9a30df2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796034"
---
# <a name="cookie-compliance"></a><span data-ttu-id="7bc49-103">Zgodność z plikami cookie</span><span class="sxs-lookup"><span data-stu-id="7bc49-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7bc49-104">W tym temacie opisano zagadnienia dotyczące zgodności z plikami cookie i domyślnych zasad, które są zawarte w aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7bc49-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7bc49-105">Prywatność jest ważnym czynnikiem, gdy używane są technologie śledzenia, które wpływają na klientów usługi e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="7bc49-105">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="7bc49-106">Ze względu na standardy zgodności z zasadami ochrony prywatności, takimi jak Ogólne rozporządzenie o ochronie danych (RODO) w Unii Europejskiej (UE), należy wziąć pod uwagę elektroniczne wytyczne dotyczące prywatności w odniesieniu do wszystkich witryn, które są obecnie aktywne.</span><span class="sxs-lookup"><span data-stu-id="7bc49-106">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="7bc49-107">Ponieważ wiele witryn e-Commerce jest domyślnie dostępnych globalnie, ważne jest, aby zapoznać się ze standardami zgodności dla witryny e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="7bc49-107">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="7bc49-108">Aby dowiedzieć się więcej na temat podstawowych zasad stosowanych przez Microsoft w przypadku zgodności z plikami cookie, odwiedź [Centrum zaufania Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="7bc49-108">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="7bc49-109">W tej witrynie można również znaleźć więcej informacji na temat obszarów zgodności i ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="7bc49-109">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="7bc49-110">W poniższej tabeli przedstawiono bieżące listy odwołań plików cookie umieszczanych przez witryny Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7bc49-110">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="7bc49-111">Nazwa pliku cookie</span><span class="sxs-lookup"><span data-stu-id="7bc49-111">Cookie name</span></span>                               | <span data-ttu-id="7bc49-112">Użycie</span><span class="sxs-lookup"><span data-stu-id="7bc49-112">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="7bc49-113">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="7bc49-113">.AspNet.Cookies</span></span>                             | <span data-ttu-id="7bc49-114">Przechowuj pliki cookie uwierzytelniania Azure Active Directory (Azure AD) od firmy Microsoft dla rejestracji jednokrotnej (SSO).</span><span class="sxs-lookup"><span data-stu-id="7bc49-114">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="7bc49-115">Przechowuje zaszyfrowane informacje główne użytkownika (imię, nazwisko, adres e-mail).</span><span class="sxs-lookup"><span data-stu-id="7bc49-115">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="7bc49-116">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="7bc49-116">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="7bc49-117">Identyfikator koszyka używany do uzyskania listy produktów dodanych do wystąpienia koszyka.</span><span class="sxs-lookup"><span data-stu-id="7bc49-117">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="7bc49-118">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="7bc49-118">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="7bc49-119">Śledzenie zgody na zgodność z plikami cookie.</span><span class="sxs-lookup"><span data-stu-id="7bc49-119">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="7bc49-120">ai_session</span><span class="sxs-lookup"><span data-stu-id="7bc49-120">ai_session</span></span>                                  | <span data-ttu-id="7bc49-121">Wykrywa, ile sesji użytkownika zostało dołączonych do niektórych stron i funkcji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7bc49-121">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="7bc49-122">ai_user</span><span class="sxs-lookup"><span data-stu-id="7bc49-122">ai_user</span></span>                                     | <span data-ttu-id="7bc49-123">Wykrywa liczbę osób korzystających z aplikacji i jej funkcji.</span><span class="sxs-lookup"><span data-stu-id="7bc49-123">Detects how many people used the app and its features.</span></span> <span data-ttu-id="7bc49-124">Użytkownicy są zliczani przy użyciu identyfikatorów anonimowych.</span><span class="sxs-lookup"><span data-stu-id="7bc49-124">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="7bc49-125">b2cru</span><span class="sxs-lookup"><span data-stu-id="7bc49-125">b2cru</span></span>                                       | <span data-ttu-id="7bc49-126">Umożliwia dynamiczne przechowywanie adresów URL przekierowań.</span><span class="sxs-lookup"><span data-stu-id="7bc49-126">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="7bc49-127">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="7bc49-127">JSESSIONID</span></span>                                  | <span data-ttu-id="7bc49-128">Używany przez łącznika płatności Adyen do przechowywania sesji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7bc49-128">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="7bc49-129">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="7bc49-129">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="7bc49-130">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="7bc49-130">Authentication</span></span>                                               |
| <span data-ttu-id="7bc49-131">x-MS-CPIM-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="7bc49-131">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="7bc49-132">Używane do obsługi stanu żądania.</span><span class="sxs-lookup"><span data-stu-id="7bc49-132">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="7bc49-133">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="7bc49-133">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="7bc49-134">Token Fałszerstwo żądania międzywitrynowego (CRSF) używany do ochrony przed CRSF.</span><span class="sxs-lookup"><span data-stu-id="7bc49-134">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="7bc49-135">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="7bc49-135">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="7bc49-136">Używany do routowania żądań do odpowiedniego wystąpienia serwera uwierzytelniania produkcji.</span><span class="sxs-lookup"><span data-stu-id="7bc49-136">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="7bc49-137">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="7bc49-137">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="7bc49-138">Używany do routowania żądań do odpowiedniego wystąpienia serwera uwierzytelniania produkcji.</span><span class="sxs-lookup"><span data-stu-id="7bc49-138">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="7bc49-139">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="7bc49-139">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="7bc49-140">Używany do routowania żądań do odpowiedniego wystąpienia serwera uwierzytelniania produkcji.</span><span class="sxs-lookup"><span data-stu-id="7bc49-140">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="7bc49-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="7bc49-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="7bc49-142">Używane do obsługi sesji SSO.</span><span class="sxs-lookup"><span data-stu-id="7bc49-142">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="7bc49-143">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="7bc49-143">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="7bc49-144">Służy do śledzenia transakcji (liczba otwartych kart uwierzytelniających się w odniesieniu do oddziału firmy (B2C)), w tym bieżącej transakcji.</span><span class="sxs-lookup"><span data-stu-id="7bc49-144">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a><span data-ttu-id="7bc49-145">Zgoda na korzystanie z pliku cookie użytkownika witryny Commerce</span><span class="sxs-lookup"><span data-stu-id="7bc49-145">Site user cookie consent on an e-Commerce site</span></span> 

<span data-ttu-id="7bc49-146">Jeśli funkcja lub moduł witryny handlu elektronicznego używa nieistotnego pliku cookie, należy uzyskać zgodę użytkownika witryny przed jego wykorzystaniem.</span><span class="sxs-lookup"><span data-stu-id="7bc49-146">If an e-Commerce site feature or module uses a non-essential cookie, a site user's consent must be obtained before the cookie is tracked.</span></span> <span data-ttu-id="7bc49-147">Aby umożliwić użytkownikom witryny udostępnienie zgody na wykorzystanie pliku cookie w platformie handlu elektronicznego, autor witryny musi dodać i skonfigurować moduł udzielania zgody na pliki cookie w module nagłówka strony, aby umożliwić wysyłanie i odbieranie zgody na wykorzystanie pliku cookie.</span><span class="sxs-lookup"><span data-stu-id="7bc49-147">To allow site users to provide cookie consent on the e-Commerce site, a site author must add and configure a cookie consent module in the page's header module to ensure that the consent is prompted for and received.</span></span> <span data-ttu-id="7bc49-148">Przed wykorzystaniem na stronie nieistotnego pliku cookie musi być uzyskana zgoda użytkownika witryny.</span><span class="sxs-lookup"><span data-stu-id="7bc49-148">Site user consent must be given before a feature or module using a non-essential cookie can be rendered on a site page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7bc49-149">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7bc49-149">Additional resources</span></span>

[<span data-ttu-id="7bc49-150">Funkcje i możliwości dostępności</span><span class="sxs-lookup"><span data-stu-id="7bc49-150">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="7bc49-151">Omówienie zgodności</span><span class="sxs-lookup"><span data-stu-id="7bc49-151">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="7bc49-152">Dodawanie strony zasad ochrony prywatności</span><span class="sxs-lookup"><span data-stu-id="7bc49-152">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="7bc49-153">Zamień identyfikatory użytkowników skojarzone ze śledzonymi zmianami zawartości</span><span class="sxs-lookup"><span data-stu-id="7bc49-153">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)

[<span data-ttu-id="7bc49-154">Moduł zgody na pliki cookie</span><span class="sxs-lookup"><span data-stu-id="7bc49-154">Cookie consent module</span></span>](cookie-consent-module.md) 
 
[<span data-ttu-id="7bc49-155">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="7bc49-155">Header module</span></span>](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
