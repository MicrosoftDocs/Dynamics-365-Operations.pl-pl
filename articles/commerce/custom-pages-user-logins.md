---
title: Ustaw strony niestandardowe dla danych logowania użytkowników
description: W tym temacie opisano, jak budować niestandardowe strony w Microsoft Dynamics 365 Commerce, które obsługują niestandardowe logowanie dla użytkowników dzierżawców Azure Active Directory (Azure AD) dla klientów indywidualnych (B2C).
author: brianshook
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 644d937ddd3c219ae869f22d977d2846dffc20e1
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697573"
---
# <a name="set-up-custom-pages-for-user-logins"></a><span data-ttu-id="40ba4-103">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="40ba4-103">Set up custom pages for user logins</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="40ba4-104">W tym temacie opisano, jak budować niestandardowe strony w Microsoft Dynamics 365 Commerce, które obsługują niestandardowe logowanie dla użytkowników dzierżawców Azure Active Directory (Azure AD) dla klientów indywidualnych (B2C).</span><span class="sxs-lookup"><span data-stu-id="40ba4-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

## <a name="overview"></a><span data-ttu-id="40ba4-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="40ba4-105">Overview</span></span>

<span data-ttu-id="40ba4-106">Aby skorzystać ze stron niestandardowych, które są tworzone Dynamics 365 Commerce w celu obsługi przepływów logowania użytkowników, należy skonfigurować zasady Azure AD, które będą przywoływane w środowisku Commerce Environment.</span><span class="sxs-lookup"><span data-stu-id="40ba4-106">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="40ba4-107">Można skonfigurować zasady B2C Azure AD „Rejestracja i logowanie”, „Edytowanie profili” i „Resetowanie hasła” za pomocą aplikacji B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="40ba4-107">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="40ba4-108">Do nazw dzierżawy i zasad B2C Azure AD można następnie odwoływać się podczas procesu udostępniania, który jest wykonywany dla środowiska Commerce przy użyciu usług Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="40ba4-108">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="40ba4-109">Niestandardowe strony Commerce mogą być tworzone przy użyciu modułu logowanie, rejestracja, edycja profilu konta lub resetowanie hasła.</span><span class="sxs-lookup"><span data-stu-id="40ba4-109">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="40ba4-110">W konfiguracjach zasad B2C Azure AD w portalu Azure Portal należy odwoływać się do stron adresów URL opublikowanych dla stron niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="40ba4-110">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="40ba4-111">Ustawianie zasad B2C</span><span class="sxs-lookup"><span data-stu-id="40ba4-111">Set up B2C policies</span></span>

<span data-ttu-id="40ba4-112">Po skonfigurowaniu dzierżawy B2C Azure AD i kojarzeniu jej ze środowiskiem Commerce, przejdź na stronę **Azure AD B2C** w portalu Azure, a następnie w menu w obszarze **Zasady** wybierz pozycję **Przepływy użytkowników (zasady)**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-112">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Polecenie przepływy użytkowników (zasady) w menu](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="40ba4-114">Teraz można skonfigurować przepływy logowania użytkownika „Rejestracja i logowanie”, „Edytowanie profili” i „Resetowanie hasła”.</span><span class="sxs-lookup"><span data-stu-id="40ba4-114">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="40ba4-115">Skonfiguruj zasadę „Rejestracja i logowanie”</span><span class="sxs-lookup"><span data-stu-id="40ba4-115">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="40ba4-116">Aby skonfigurować zasadę „Rejestracja i logowanie”, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="40ba4-116">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="40ba4-117">Wybierz opcję **Nowy przepływ użytkownika**, a następnie na karcie **Rekomendowany** wybierz zasadę **Rejestracja i logowanie**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-117">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="40ba4-118">Wprowadź nazwę zasady (na przykład **B2C\_1\_RejestracjaiLogowanie**).</span><span class="sxs-lookup"><span data-stu-id="40ba4-118">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="40ba4-119">W sekcji **Dostawcy tożsamości** wybierz dostawców tożsamości, którzy mają być używani dla zasady.</span><span class="sxs-lookup"><span data-stu-id="40ba4-119">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="40ba4-120">Należy wybrać co najmniej opcję **Rejestracja e-mail**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-120">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="40ba4-121">W kolumnie **Zbieranie atrybutów** zaznacz pola wyboru **Adres e-mail**, **Imię** i **Nazwisko**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-121">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="40ba4-122">W kolumnie **Oświadczenie zwrotu** zaznacz pola wyboru dla **Adresy e-mail**, **Imię**, **Dostawca tożsamości**, **Nazwisko** i **Identyfikator obiektu użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-122">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Wybrane atrybuty i roszczenia](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="40ba4-124">Wybierz przycisk **OK**, aby utworzyć zasadę.</span><span class="sxs-lookup"><span data-stu-id="40ba4-124">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="40ba4-125">Kliknij dwukrotnie nazwę nowej zasady, a następnie w okienku nawigacji wybierz opcję **Właściwości.**</span><span class="sxs-lookup"><span data-stu-id="40ba4-125">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="40ba4-126">Ustaw opcję **Włącz układ wymuszający JavaScript w układzie strony (podgląd)** jako **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-126">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![Strona właściwości nowej zasady](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="40ba4-128">Nazwa zasad będzie w pełni wywoływana w środowisku Commerce.</span><span class="sxs-lookup"><span data-stu-id="40ba4-128">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="40ba4-129">(Prefiks **B2C\_1\_** zostanie uwzględniony w odwołaniu.) Nie można zmieniać nazw zasad po ich utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="40ba4-129">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="40ba4-130">W przypadku wymiany istniejących zasad środowiska Commerce można usunąć zasady oryginalne i utworzyć nowe zasady o takiej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="40ba4-130">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="40ba4-131">Ewentualnie, jeśli zainicjowano już obsługę środowiska, można przesłać nową nazwę zasady za pośrednictwem żądania usługi.</span><span class="sxs-lookup"><span data-stu-id="40ba4-131">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="40ba4-132">Ta zasada zostanie przywrócona, aby dokończyć konfigurowanie po stworzeniu stron niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="40ba4-132">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="40ba4-133">Na razie Zamknij zasady, aby powrócić do strony **przepływy użytkownika (zasady)** w portalu Azure.</span><span class="sxs-lookup"><span data-stu-id="40ba4-133">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="40ba4-134">Skonfiguruj zasadę „edycji profilu”</span><span class="sxs-lookup"><span data-stu-id="40ba4-134">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="40ba4-135">Aby skonfigurować zasadę „edycji profilu”, wykonaj poniższe czynności.</span><span class="sxs-lookup"><span data-stu-id="40ba4-135">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="40ba4-136">Wybierz opcję **Nowy przepływ użytkownika**, a następnie na karcie **Rekomendowany** wybierz zasadę **Edycja profilu**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-136">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="40ba4-137">Wprowadź nazwę zasady (na przykład **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="40ba4-137">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="40ba4-138">W sekcji **Dostawcy tożsamości** wybierz dostawców tożsamości, którzy mają być używani dla zasady.</span><span class="sxs-lookup"><span data-stu-id="40ba4-138">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="40ba4-139">Należy wybrać co najmniej opcję **logowania lokalnego konta**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-139">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="40ba4-140">W kolumnie **Zbieranie atrybutów** zaznacz pola wyboru **Adres e-mail** i **Nazwisko**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-140">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="40ba4-141">W kolumnie **Oświadczenie zwrotu** zaznacz pola wyboru dla **Adresy e-mail**, **Imię**, **Dostawca tożsamości**, **Nazwisko** i **Identyfikator obiektu użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-141">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="40ba4-142">Wybierz przycisk **OK**, aby utworzyć zasadę.</span><span class="sxs-lookup"><span data-stu-id="40ba4-142">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="40ba4-143">Kliknij dwukrotnie nazwę nowej zasady, a następnie w okienku nawigacji wybierz opcję **Właściwości.**</span><span class="sxs-lookup"><span data-stu-id="40ba4-143">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="40ba4-144">Ustaw opcję **Włącz układ wymuszający JavaScript w układzie strony (podgląd)** jako **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-144">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="40ba4-145">Ta zasada zostanie przywrócona, aby dokończyć konfigurowanie po stworzeniu stron niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="40ba4-145">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="40ba4-146">Na razie Zamknij zasady, aby powrócić do strony **przepływy użytkownika (zasady)** w portalu Azure.</span><span class="sxs-lookup"><span data-stu-id="40ba4-146">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="40ba4-147">Skonfiguruj zasadę „resetowania hasła”</span><span class="sxs-lookup"><span data-stu-id="40ba4-147">Configure the "Password reset" policy</span></span>

<span data-ttu-id="40ba4-148">Aby skonfigurować zasadę „resetowania hasła”, wykonaj poniższe czynności.</span><span class="sxs-lookup"><span data-stu-id="40ba4-148">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="40ba4-149">Wybierz opcję **Nowy przepływ użytkownika**, a następnie na karcie **Podgląd** wybierz zasadę **Resetowanie hasła v1:1**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-149">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Zasada resetowania hasła v1.1 wybrana na karcie Podgląd](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="40ba4-151">Wprowadź nazwę zasady (na przykład **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="40ba4-151">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="40ba4-152">W sekcji **dostawcy tożsamości** wybierz opcję **Resetuj hasło, używając adresu e-mail**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-152">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="40ba4-153">W kolumnie **Oświadczenie zwrotu** zaznacz pola wyboru dla **Adresy e-mail**, **Imię**, **Nazwisko** i **Identyfikator obiektu użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-153">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Wybrane roszczenia](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="40ba4-155">Wybierz przycisk **OK**, aby utworzyć zasadę.</span><span class="sxs-lookup"><span data-stu-id="40ba4-155">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="40ba4-156">Kliknij dwukrotnie nazwę nowej zasady, a następnie w okienku nawigacji wybierz opcję **Właściwości.**</span><span class="sxs-lookup"><span data-stu-id="40ba4-156">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="40ba4-157">Ustaw opcję **Włącz układ wymuszający JavaScript w układzie strony (podgląd)** jako **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-157">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="40ba4-158">Ta zasada zostanie przywrócona, aby dokończyć konfigurowanie po stworzeniu stron niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="40ba4-158">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="40ba4-159">Na razie Zamknij zasady, aby powrócić do strony **przepływy użytkownika (zasady)** w portalu Azure.</span><span class="sxs-lookup"><span data-stu-id="40ba4-159">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="40ba4-160">Tworzenie niestandardowych stron</span><span class="sxs-lookup"><span data-stu-id="40ba4-160">Build the custom pages</span></span>

<span data-ttu-id="40ba4-161">Aby utworzyć niestandardowe strony do obsługi podpisów użytkowników, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="40ba4-161">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="40ba4-162">W narzedziu autorskim Commerce przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="40ba4-162">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="40ba4-163">Utwórz następujące pięć szablonów i pięć stron:</span><span class="sxs-lookup"><span data-stu-id="40ba4-163">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="40ba4-164">Szablon **Zaloguj się** i strona korzystająca z modułu logowania.</span><span class="sxs-lookup"><span data-stu-id="40ba4-164">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="40ba4-165">Szablon **Zarejestruj się** i strona korzystająca z modułu rejestracji.</span><span class="sxs-lookup"><span data-stu-id="40ba4-165">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="40ba4-166">Szablon **resetowania hasła** i strona, która korzysta z modułu resetowania hasła.</span><span class="sxs-lookup"><span data-stu-id="40ba4-166">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="40ba4-167">Szablon **Potwierdzenie resetowania hasła** i strona, która korzysta z modułu potwierdzenia resetowania hasła.</span><span class="sxs-lookup"><span data-stu-id="40ba4-167">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="40ba4-168">Szablon **Edytuj profil** i stronę, która używa modułu Edytuj profil konta</span><span class="sxs-lookup"><span data-stu-id="40ba4-168">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="40ba4-169">Podczas tworzenia stron postępuj zgodnie z następującymi wskazówkami:</span><span class="sxs-lookup"><span data-stu-id="40ba4-169">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="40ba4-170">Dla każdej strony lub modułu należy zastosować układ i styl najlepiej odpowiadające wymaganiom biznesowym.</span><span class="sxs-lookup"><span data-stu-id="40ba4-170">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="40ba4-171">Publikuj wszystkie strony i adresy URL, które muszą być używane w ustawieniach Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="40ba4-171">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="40ba4-172">Po opublikowaniu stron i adresów URL należy zebrać adresy URL, które muszą być używane w konfiguracjach zasad Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="40ba4-172">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="40ba4-173">A **?preloadscripts=true** sufiks zostanie dodany do każdego z adresów URL, gdy jest używany.</span><span class="sxs-lookup"><span data-stu-id="40ba4-173">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40ba4-174">Nie należy ponownie używać uniwersalnych nagłówków i stopek mających łącza względne.</span><span class="sxs-lookup"><span data-stu-id="40ba4-174">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="40ba4-175">Ponieważ te strony będą przechowywane w domenie Azure AD B2C, gdy są używane, dla wszystkich łączy będą używane tylko bezwzględne adresy URL</span><span class="sxs-lookup"><span data-stu-id="40ba4-175">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="40ba4-176">Skonfiguruj zasady Azure AD B2C za pomocą niestandardowych informacji o stronie</span><span class="sxs-lookup"><span data-stu-id="40ba4-176">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="40ba4-177">W portalu Azure Wróć do strony **Azure AD B2C**, a następnie w menu w obszarze **zasady** wybierz pozycję **przepływy użytkowników (zasady)**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-177">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="40ba4-178">Aktualizuj zasadę „Rejestracja i logowanie w” przy użyciu niestandardowych informacji o stronie</span><span class="sxs-lookup"><span data-stu-id="40ba4-178">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="40ba4-179">Aktualizuj zasadę „Rejestracja i logowanie w” przy użyciu niestandardowych informacji o stronie za pomocą następujących czynności.</span><span class="sxs-lookup"><span data-stu-id="40ba4-179">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="40ba4-180">W obszarze zasady **Zaloguj się i zarejestruj**, którą skonfigurowano wcześniej, w okienku nawigacji wybierz opcję **układy stron**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-180">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="40ba4-181">Wybierz układ **Unifikuj rejestrację i logowanie na stronie**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-181">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="40ba4-182">Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-182">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="40ba4-183">W polu **identyfikator URL strony niestandardowej** wprowadź pełny adres URL logowania.</span><span class="sxs-lookup"><span data-stu-id="40ba4-183">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="40ba4-184">Dołącz sufiks **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-184">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="40ba4-185">Na przykład wprowadź **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-185">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="40ba4-186">W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-186">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="40ba4-187">Wybierz układ **Strona rejestracji lokalnego konta**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-187">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="40ba4-188">Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-188">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="40ba4-189">W polu **identyfikator URL strony niestandardowej** wprowadź pełny adres URL logowania.</span><span class="sxs-lookup"><span data-stu-id="40ba4-189">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="40ba4-190">Dołącz sufiks **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-190">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="40ba4-191">Na przykład wprowadź **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-191">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="40ba4-192">W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-192">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="40ba4-193">W sekcji **atrybuty użytkownika** wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="40ba4-193">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="40ba4-194">W przypadku **adresu e-mail**, **imienia** i **nazwiska** należy wybrać opcję **nie** w polu **wymagane weryfikacje**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-194">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="40ba4-195">W przypadku adresu **imienia** i **nazwiska** należy wybrać opcję **nie** w polu **opcjonalne**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-195">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![Konfiguracja zasad rejestracji na koncie lokalnym](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="40ba4-197">Aktualizuj zasadę „Edycja profilu” przy użyciu niestandardowych informacji o stronie</span><span class="sxs-lookup"><span data-stu-id="40ba4-197">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="40ba4-198">Aktualizuj zasadę „Edycja profilu” przy użyciu niestandardowych informacji o stronie za pomocą następujących czynności.</span><span class="sxs-lookup"><span data-stu-id="40ba4-198">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="40ba4-199">W obszarze zasady **Edycja profilu**, którą skonfigurowano wcześniej, w okienku nawigacji wybierz opcję **układy stron**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-199">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="40ba4-200">Wybierz układ **strony edytowania profilu**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-200">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="40ba4-201">Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-201">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="40ba4-202">W polu **identyfikator URL strony niestandardowej** wprowadź pełny adres URL logowania.</span><span class="sxs-lookup"><span data-stu-id="40ba4-202">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="40ba4-203">Dołącz sufiks **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-203">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="40ba4-204">Na przykład wprowadź **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-204">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="40ba4-205">W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-205">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="40ba4-206">W sekcji **atrybuty użytkownika** wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="40ba4-206">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="40ba4-207">W przypadku **adresu e-mail** i **imienia**  należy wybrać opcję **nie** w polu **wymagane weryfikacje**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-207">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="40ba4-208">W przypadku adresu **imienia** i **nazwiska** należy wybrać opcję **nie** w polu **opcjonalne**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-208">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="40ba4-209">Aktualizuj zasadę „Resetowanie hasła” przy użyciu niestandardowych informacji o stronie</span><span class="sxs-lookup"><span data-stu-id="40ba4-209">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="40ba4-210">Aktualizuj zasadę „Resetowanie hasła” przy użyciu niestandardowych informacji o stronie za pomocą następujących czynności.</span><span class="sxs-lookup"><span data-stu-id="40ba4-210">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="40ba4-211">W obszarze zasady **resetowanie hasła**, którą skonfigurowano wcześniej, w okienku nawigacji wybierz opcję **układy stron**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-211">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="40ba4-212">Wybierz układ **strona nowego hasła**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-212">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="40ba4-213">Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-213">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="40ba4-214">W polu **identyfikator URL strony niestandardowej** wprowadź pełny adres URL logowania.</span><span class="sxs-lookup"><span data-stu-id="40ba4-214">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="40ba4-215">Dołącz sufiks **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-215">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="40ba4-216">Na przykład wprowadź **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-216">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="40ba4-217">W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-217">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="40ba4-218">Wybierz układ **strony weryfikacji konta**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-218">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="40ba4-219">Ustawienie opcji **używaj niestandardowej zawartości** strony na wartość **tak**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-219">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="40ba4-220">W polu **identyfikator URL strony niestandardowej** wprowadź pełny adres URL logowania.</span><span class="sxs-lookup"><span data-stu-id="40ba4-220">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="40ba4-221">Dołącz sufiks **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-221">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="40ba4-222">Na przykład wprowadź **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-222">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="40ba4-223">W polu **wersja układu strony (wersja podglądu)** wybierz opcję **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-223">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="40ba4-224">Dostosowywanie domyślnych ciągów tekstowych dla etykiet i opisów</span><span class="sxs-lookup"><span data-stu-id="40ba4-224">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="40ba4-225">W przypadku zestawu początkowy zestaw moduły logowania są wstępnie wypełniane domyślnymi ciągami tekstowymi dla etykiet i opisów.</span><span class="sxs-lookup"><span data-stu-id="40ba4-225">In the starter kit, sign in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="40ba4-226">Można dostosować te ciągi w zestawie SDK (Software Development Kit), aktualizując wartości w pliku Global. JSON systemu logowania w module.</span><span class="sxs-lookup"><span data-stu-id="40ba4-226">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="40ba4-227">Na przykład domyślny tekst dla łącza zapomnianego hasła jest **Zapomniałeś hasła?**.</span><span class="sxs-lookup"><span data-stu-id="40ba4-227">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="40ba4-228">Poniżej przedstawiono domyślny tekst na stronie rejestracji.</span><span class="sxs-lookup"><span data-stu-id="40ba4-228">The following shows this default text on the sign-in page.</span></span>

![Domyślny tekst łącza zapomnianego hasła na stronie rejestracji](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="40ba4-230">Jednak w pliku global.json dla początkowego zestawu dzienników w module można edytować tekst, aby **Zapomniałeś hasła?**, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="40ba4-230">However, in the global.json file for the starter kit sign in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Zaktualizowany tekst łącza w pliku global.json modułu rejestrowania](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="40ba4-232">Po zaktualizowaniu pliku global.json i opublikowaniu zmian tekst nowego łącza jest wyświetlany w module logowanie zarówno w Commerce, jak i na stronie rejestracji online.</span><span class="sxs-lookup"><span data-stu-id="40ba4-232">After you update the global.json file and publish your changes, the new link text appears in the sign in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40ba4-233">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="40ba4-233">Additional resources</span></span>

[<span data-ttu-id="40ba4-234">Omówienie sklepu internetowego</span><span class="sxs-lookup"><span data-stu-id="40ba4-234">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="40ba4-235">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="40ba4-235">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="40ba4-236">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="40ba4-236">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="40ba4-237">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="40ba4-237">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="40ba4-238">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="40ba4-238">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="40ba4-239">Dodaj obsługę dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="40ba4-239">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="40ba4-240">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="40ba4-240">Enable location-based store detection</span></span>](enable-store-detection.md)
