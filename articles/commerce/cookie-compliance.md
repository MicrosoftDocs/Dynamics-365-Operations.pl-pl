---
title: Zgodność z plikami cookie
description: W tym temacie opisano zagadnienia dotyczące zgodności z plikami cookie i domyślnych zasad, które są zawarte w aplikacji Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 95c5801e69396b21a36c4ae12ce17801e6f7fd88
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993507"
---
# <a name="cookie-compliance"></a><span data-ttu-id="740c5-103">Zgodność z plikami cookie</span><span class="sxs-lookup"><span data-stu-id="740c5-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="740c5-104">W tym temacie opisano zagadnienia dotyczące zgodności z plikami cookie i domyślnych zasad, które są zawarte w aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="740c5-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="740c5-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="740c5-105">Overview</span></span>

<span data-ttu-id="740c5-106">Prywatność jest ważnym czynnikiem, gdy używane są technologie śledzenia, które wpływają na klientów usługi e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="740c5-106">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="740c5-107">Ze względu na standardy zgodności z zasadami ochrony prywatności, takimi jak Ogólne rozporządzenie o ochronie danych (RODO) w Unii Europejskiej (UE), należy wziąć pod uwagę elektroniczne wytyczne dotyczące prywatności w odniesieniu do wszystkich witryn, które są obecnie aktywne.</span><span class="sxs-lookup"><span data-stu-id="740c5-107">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="740c5-108">Ponieważ wiele witryn e-Commerce jest domyślnie dostępnych globalnie, ważne jest, aby zapoznać się ze standardami zgodności dla witryny e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="740c5-108">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="740c5-109">Aby dowiedzieć się więcej na temat podstawowych zasad stosowanych przez Microsoft w przypadku zgodności z plikami cookie, odwiedź [Centrum zaufania Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="740c5-109">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="740c5-110">W tej witrynie można również znaleźć więcej informacji na temat obszarów zgodności i ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="740c5-110">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="740c5-111">W poniższej tabeli przedstawiono bieżące listy odwołań plików cookie umieszczanych przez witryny Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="740c5-111">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="740c5-112">Nazwa pliku cookie</span><span class="sxs-lookup"><span data-stu-id="740c5-112">Cookie name</span></span>                               | <span data-ttu-id="740c5-113">Użycie</span><span class="sxs-lookup"><span data-stu-id="740c5-113">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="740c5-114">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="740c5-114">.AspNet.Cookies</span></span>                             | <span data-ttu-id="740c5-115">Przechowuj pliki cookie uwierzytelniania Azure Active Directory (Azure AD) od firmy Microsoft dla rejestracji jednokrotnej (SSO).</span><span class="sxs-lookup"><span data-stu-id="740c5-115">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="740c5-116">Przechowuje zaszyfrowane informacje główne użytkownika (imię, nazwisko, adres e-mail).</span><span class="sxs-lookup"><span data-stu-id="740c5-116">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="740c5-117">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="740c5-117">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="740c5-118">Identyfikator koszyka używany do uzyskania listy produktów dodanych do wystąpienia koszyka.</span><span class="sxs-lookup"><span data-stu-id="740c5-118">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="740c5-119">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="740c5-119">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="740c5-120">Śledzenie zgody na zgodność z plikami cookie.</span><span class="sxs-lookup"><span data-stu-id="740c5-120">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="740c5-121">ai_session</span><span class="sxs-lookup"><span data-stu-id="740c5-121">ai_session</span></span>                                  | <span data-ttu-id="740c5-122">Wykrywa, ile sesji użytkownika zostało dołączonych do niektórych stron i funkcji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="740c5-122">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="740c5-123">ai_user</span><span class="sxs-lookup"><span data-stu-id="740c5-123">ai_user</span></span>                                     | <span data-ttu-id="740c5-124">Wykrywa liczbę osób korzystających z aplikacji i jej funkcji.</span><span class="sxs-lookup"><span data-stu-id="740c5-124">Detects how many people used the app and its features.</span></span> <span data-ttu-id="740c5-125">Użytkownicy są zliczani przy użyciu identyfikatorów anonimowych.</span><span class="sxs-lookup"><span data-stu-id="740c5-125">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="740c5-126">b2cru</span><span class="sxs-lookup"><span data-stu-id="740c5-126">b2cru</span></span>                                       | <span data-ttu-id="740c5-127">Umożliwia dynamiczne przechowywanie adresów URL przekierowań.</span><span class="sxs-lookup"><span data-stu-id="740c5-127">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="740c5-128">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="740c5-128">JSESSIONID</span></span>                                  | <span data-ttu-id="740c5-129">Używany przez łącznika płatności Adyen do przechowywania sesji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="740c5-129">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="740c5-130">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="740c5-130">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="740c5-131">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="740c5-131">Authentication</span></span>                                               |
| <span data-ttu-id="740c5-132">x-MS-CPIM-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="740c5-132">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="740c5-133">Używane do obsługi stanu żądania.</span><span class="sxs-lookup"><span data-stu-id="740c5-133">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="740c5-134">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="740c5-134">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="740c5-135">Token Fałszerstwo żądania międzywitrynowego (CRSF) używany do ochrony przed CRSF.</span><span class="sxs-lookup"><span data-stu-id="740c5-135">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="740c5-136">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="740c5-136">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="740c5-137">Używany do routowania żądań do odpowiedniego wystąpienia serwera uwierzytelniania produkcji.</span><span class="sxs-lookup"><span data-stu-id="740c5-137">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="740c5-138">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="740c5-138">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="740c5-139">Używany do routowania żądań do odpowiedniego wystąpienia serwera uwierzytelniania produkcji.</span><span class="sxs-lookup"><span data-stu-id="740c5-139">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="740c5-140">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="740c5-140">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="740c5-141">Używany do routowania żądań do odpowiedniego wystąpienia serwera uwierzytelniania produkcji.</span><span class="sxs-lookup"><span data-stu-id="740c5-141">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="740c5-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="740c5-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="740c5-143">Używane do obsługi sesji SSO.</span><span class="sxs-lookup"><span data-stu-id="740c5-143">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="740c5-144">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="740c5-144">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="740c5-145">Służy do śledzenia transakcji (liczba otwartych kart uwierzytelniających się w odniesieniu do oddziału firmy (B2C)), w tym bieżącej transakcji.</span><span class="sxs-lookup"><span data-stu-id="740c5-145">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a><span data-ttu-id="740c5-146">Zgoda na korzystanie z pliku cookie użytkownika witryny Commerce</span><span class="sxs-lookup"><span data-stu-id="740c5-146">Site user cookie consent on an e-Commerce site</span></span> 

<span data-ttu-id="740c5-147">Jeśli funkcja lub moduł witryny handlu elektronicznego używa nieistotnego pliku cookie, należy uzyskać zgodę użytkownika witryny przed jego wykorzystaniem.</span><span class="sxs-lookup"><span data-stu-id="740c5-147">If an e-Commerce site feature or module uses a non-essential cookie, a site user's consent must be obtained before the cookie is tracked.</span></span> <span data-ttu-id="740c5-148">Aby umożliwić użytkownikom witryny udostępnienie zgody na wykorzystanie pliku cookie w platformie handlu elektronicznego, autor witryny musi dodać i skonfigurować moduł udzielania zgody na pliki cookie w module nagłówka strony, aby umożliwić wysyłanie i odbieranie zgody na wykorzystanie pliku cookie.</span><span class="sxs-lookup"><span data-stu-id="740c5-148">To allow site users to provide cookie consent on the e-Commerce site, a site author must add and configure a cookie consent module in the page's header module to ensure that the consent is prompted for and received.</span></span> <span data-ttu-id="740c5-149">Przed wykorzystaniem na stronie nieistotnego pliku cookie musi być uzyskana zgoda użytkownika witryny.</span><span class="sxs-lookup"><span data-stu-id="740c5-149">Site user consent must be given before a feature or module using a non-essential cookie can be rendered on a site page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="740c5-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="740c5-150">Additional resources</span></span>

[<span data-ttu-id="740c5-151">Funkcje i możliwości dostępności</span><span class="sxs-lookup"><span data-stu-id="740c5-151">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="740c5-152">Omówienie zgodności</span><span class="sxs-lookup"><span data-stu-id="740c5-152">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="740c5-153">Dodawanie strony zasad ochrony prywatności</span><span class="sxs-lookup"><span data-stu-id="740c5-153">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="740c5-154">Zamień identyfikatory użytkowników skojarzone ze śledzonymi zmianami zawartości</span><span class="sxs-lookup"><span data-stu-id="740c5-154">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)

[<span data-ttu-id="740c5-155">Moduł zgody na pliki cookie</span><span class="sxs-lookup"><span data-stu-id="740c5-155">Cookie consent module</span></span>](cookie-consent-module.md) 
 
[<span data-ttu-id="740c5-156">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="740c5-156">Header module</span></span>](author-header-module.md)
