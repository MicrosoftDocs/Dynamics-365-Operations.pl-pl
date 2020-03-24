---
title: Konfigurowanie dzierżawy B2C w usłudze Commerce
description: W tym temacie opisano sposób konfigurowania dzierżawcy Azure Active Directory (Azure AD) dzierżawców biznesowych (B2C) dla uwierzytelniania witryny użytkownika w programie Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: BriShoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: a5fca37fb89c723273ef753b102092e2cfb26563
ms.sourcegitcommit: 236672932ffd0a758012ebb7b2df9bc51249c126
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096521"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a><span data-ttu-id="fe06c-103">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="fe06c-103">Set up a B2C tenant in Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe06c-104">W tym temacie opisano sposób konfigurowania dzierżawcy Azure Active Directory (Azure AD) dzierżawców biznesowych (B2C) dla uwierzytelniania witryny użytkownika w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe06c-104">This topic describes how to set up your Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants for user site authentication in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fe06c-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="fe06c-105">Overview</span></span>

<span data-ttu-id="fe06c-106">Dynamics 365 Commerce używa Azure AD B2C do obsługi przenoszonych poświadczeń i przepływów uwierzytelniania użytkowników.</span><span class="sxs-lookup"><span data-stu-id="fe06c-106">Dynamics 365 Commerce uses Azure AD B2C to support user credential and authentication flows.</span></span> <span data-ttu-id="fe06c-107">Użytkownik może zarejestrować się, zalogować się i zresetować swoje hasło za pośrednictwem tych przepływów.</span><span class="sxs-lookup"><span data-stu-id="fe06c-107">A user can sign up, sign in, and reset their password through these flows.</span></span> <span data-ttu-id="fe06c-108">Azure AD B2C przechowuje poufne informacje o uwierzytelnianiu użytkownika, takie jak nazwa użytkownika i hasło.</span><span class="sxs-lookup"><span data-stu-id="fe06c-108">Azure AD B2C stores sensitive user authentication information, such as username and password.</span></span> <span data-ttu-id="fe06c-109">Rekord użytkownika w dzierżawie B2C będzie przechowywał zarówno rekord konta lokalnego B2C, jak i rekord dostawcy tożsamości socjalnej B2C.</span><span class="sxs-lookup"><span data-stu-id="fe06c-109">The user record in the B2C tenant will store either a B2C local account record or a B2C social identity provider record.</span></span> <span data-ttu-id="fe06c-110">Te rekordy B2C zostaną połączone z rekordem odbiorcy w środowisku Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe06c-110">These B2C records will link back to the customer record in the Commerce environment.</span></span>

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a><span data-ttu-id="fe06c-111">Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze AAD w portalu Azure</span><span class="sxs-lookup"><span data-stu-id="fe06c-111">Create or link to an existing AAD B2C tenant in the Azure portal</span></span>

1. <span data-ttu-id="fe06c-112">Zaloguj się do witryny [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="fe06c-112">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="fe06c-113">W menu portalu Azure wybierz polecenie **Utwórz zasób**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-113">From the Azure portal menu, select **Create a resource**.</span></span> <span data-ttu-id="fe06c-114">Należy pamiętać o użyciu subskrypcji i katalogu, który będzie połączony ze środowiskiem Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe06c-114">Be sure to use the subscription and directory that will be connected with your Commerce environment.</span></span>

    ![Utwórz zasób w portalu Azure](./media/B2CImage_1.png)

1. <span data-ttu-id="fe06c-116">Przejdź do **Tożsamość \> Azure Active Directory B2C**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-116">Go to **Identity \> Azure Active Directory B2C**.</span></span>
1. <span data-ttu-id="fe06c-117">Na stronie **Utwórz nowego B2C dzierżawę lub Połącz z istniejącą stroną dzierżawy**, Skorzystaj z jednej z poniższych opcji, która najlepiej pasuje do potrzeb firmy:</span><span class="sxs-lookup"><span data-stu-id="fe06c-117">Once on the **Create New B2C Tenant or Link to existing Tenant** page, use one of the options below that best suits your company's needs:</span></span>

    - <span data-ttu-id="fe06c-118">**Utwórz nową dzierżawę B2C Azure AD**: Ta opcja służy do utworzenia nowej dzierżawy B2C w usłudze AAD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-118">**Create a new Azure AD B2C Tenant**: Use this option to create a new AAD B2C tenant.</span></span>
        1. <span data-ttu-id="fe06c-119">Wybierz **Stwórz nową dzierżawę B2C Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-119">Select **Create a new Azure AD B2C Tenant**.</span></span>
        1. <span data-ttu-id="fe06c-120">W obszarze **Nazwa organizacji** wprowadź nazwę organizacji.</span><span class="sxs-lookup"><span data-stu-id="fe06c-120">Under **Organization name**, enter the organization name.</span></span>
        1. <span data-ttu-id="fe06c-121">W obszarze **początkowa nazwa domeny** wprowadź początkową nazwę domeny.</span><span class="sxs-lookup"><span data-stu-id="fe06c-121">Under **Initial domain name**, enter the initial domain name.</span></span>
        1. <span data-ttu-id="fe06c-122">W przypadku **kraju lub regionu** wybierz kraj lub region.</span><span class="sxs-lookup"><span data-stu-id="fe06c-122">For **Country or region**, select the country or region.</span></span>
        1. <span data-ttu-id="fe06c-123">Wybierz przycisk **Utwórz**, aby utworzyć dzierżawę.</span><span class="sxs-lookup"><span data-stu-id="fe06c-123">Select **Create** to create the tenant.</span></span>

     ![Tworzenie nowej dzierżawy Azure AD](./media/B2CImage_2.png)

     - <span data-ttu-id="fe06c-125">**Połącz istniejącą dzierżawę B2C Azure AD z moją subskrypcją systemu Azure**: Tę opcję należy użyć, jeśli istnieje już dzierżawa B2C Azure AD, do której ma zostać utworzone łącze.</span><span class="sxs-lookup"><span data-stu-id="fe06c-125">**Link an existing Azure AD B2C Tenant to my Azure subscription**: Use this option if you already have an Azure AD B2C tenant you want to link to.</span></span>
        1. <span data-ttu-id="fe06c-126">Wybierz **łącze do istniejącej dzierżawy B2C Azure AD do mojej subskrypcji systemu Azure**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-126">Select **Link an existing Azure AD B2C Tenant to my Azure subscription**.</span></span>
        1. <span data-ttu-id="fe06c-127">W **Dzierżawa B2C Azure AD** wybierz odpowiednią dzierżawę B2C.</span><span class="sxs-lookup"><span data-stu-id="fe06c-127">For **Azure AD B2C Tenant**, select the appropriate B2C tenant.</span></span> <span data-ttu-id="fe06c-128">Jeśli w polu wyboru zostanie wyświetlona wiadomość „nie znaleziono dzierżawców B2C”, nie masz istniejącej uprawnionej dzierżawy B2C i będzie konieczne utworzenie nowej.</span><span class="sxs-lookup"><span data-stu-id="fe06c-128">If the message "No eligible B2C Tenants found" appears in the selection box, you do not have an existing eligible B2C tenant and will need to create a new one.</span></span>
        1. <span data-ttu-id="fe06c-129">W **Grupie zasobów** wybierz opcję **Utwórz nową**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-129">For **Resource group**, select **Create new**.</span></span> <span data-ttu-id="fe06c-130">Wprowadź **nazwę** grupy zasobów, która będzie zawierać dzierżawcę, wybierz **lokalizację grupy zasobów**, a następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-130">Enter a **Name** for the resource group that will contain the tenant, select the **Resource group location**, and then select **Create**.</span></span>

    ![Wybierz łącze do istniejącej dzierżawy B2C Azure AD do subskrypcji systemu Azure](./media/B2CImage_3.png)

1. <span data-ttu-id="fe06c-132">Po utworzeniu nowego katalogu B2C Azure AD (może to chwilę potrwać) na pulpicie nawigacyjnym pojawi się łącze do nowego katalogu.</span><span class="sxs-lookup"><span data-stu-id="fe06c-132">Once the new Azure AD B2C directory is created (this may take a few moments), a link to the new directory will appear on the dashboard.</span></span> <span data-ttu-id="fe06c-133">To łącze spowoduje przekierowanie do strony „Witamy w B2C usługi Azure Active Directory”.</span><span class="sxs-lookup"><span data-stu-id="fe06c-133">This link will direct you to the "Welcome to Azure Active Directory B2C" page.</span></span>

    ![Połącz z nowym katalogiem usługi AAD](./media/B2CImage_4.png)

> [!NOTE]
> <span data-ttu-id="fe06c-135">Jeśli masz wiele subskrypcji na koncie systemu Azure lub skonfigurowano dzierżawcę B2C bez łączenia z aktywną subskrypcją, transparent do **rozwiązywania problemów** poinformuje dzierżawcę o połączeniu z subskrypcją.</span><span class="sxs-lookup"><span data-stu-id="fe06c-135">If you have multiple subscriptions within your Azure account or have set up the B2C tenant without linking to an active subscription, a **Troubleshoot** banner will direct you to link the tenant to a subscription.</span></span> <span data-ttu-id="fe06c-136">Wybierz komunikat rozwiązywania problemów i postępuj zgodnie z instrukcjami, aby rozwiązać problem z subskrypcją.</span><span class="sxs-lookup"><span data-stu-id="fe06c-136">Select the troubleshooting message and follow the instructions to resolve the subscription issue.</span></span>

<span data-ttu-id="fe06c-137">Poniższy obraz przedstawia przykład transparentu B2C Azure AD **Rozwiązywanie problemów**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-137">The following image shows an example of an Azure AD B2C **Troubleshoot** banner.</span></span>

![Ostrzeżenie pokazujące katalog, który nie ma aktywnej subskrypcji](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a><span data-ttu-id="fe06c-139">Tworzenie aplikacji B2C</span><span class="sxs-lookup"><span data-stu-id="fe06c-139">Create the B2C application</span></span>

<span data-ttu-id="fe06c-140">Po utworzeniu dzierżawy B2C użytkownik utworzy aplikację B2C w dzierżawie w celu interakcji z akcjami Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe06c-140">Once the B2C tenant has been created, you will create a B2C application within the tenant to interact with the Commerce actions.</span></span>

<span data-ttu-id="fe06c-141">Aby utworzyć aplikację B2C, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="fe06c-141">To create the B2C application, follow these steps.</span></span>

1. <span data-ttu-id="fe06c-142">W portalu Azure wybierz opcję **aplikacje**, a następnie wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-142">In the Azure portal, select **Applications** and then select **Add**.</span></span>
1. <span data-ttu-id="fe06c-143">W polu **Nazwa** wprowadź nazwę żądanej aplikacji B2C w usłudze AAD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-143">Under **Name**, enter the name of the desired AAD B2C application.</span></span>
1. <span data-ttu-id="fe06c-144">W obszarze **Aplikacji sieci Web/API sieci Web** dla **Dołącz aplikację sieci Web/API sieci Web** wybierz **Tak**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-144">Under **Web App/Web API**, for **Include web app / web API**, select **Yes**.</span></span>
1. <span data-ttu-id="fe06c-145">W przypadku **Zezwól na dorozumiany przepływ** wybierz opcję **Tak** (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="fe06c-145">For **Allow implicit flow**, select **Yes** (the default value).</span></span>
1. <span data-ttu-id="fe06c-146">W obszarze **Adres URL odpowiedzi** wprowadź dedykowane adresy URL odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="fe06c-146">Under **Reply URL**, enter your dedicated reply URLs.</span></span> <span data-ttu-id="fe06c-147">Patrz [Adresu URL odpowiedzi](#reply-urls) poniżej w celu znalezienia informacji na temat adresów URL oraz jak je formatować.</span><span class="sxs-lookup"><span data-stu-id="fe06c-147">See [Reply URLs](#reply-urls) below for information on reply URLs and how to format them here.</span></span>
1. <span data-ttu-id="fe06c-148">Aby **włączyć macierzystego klienta**, wybierz **nie** (wartość domyślną).</span><span class="sxs-lookup"><span data-stu-id="fe06c-148">For **Include native client**, select **No** (the default value).</span></span>
1. <span data-ttu-id="fe06c-149">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-149">Select **Create**.</span></span>

### <a name="reply-urls"></a><span data-ttu-id="fe06c-150">Adresy URL odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="fe06c-150">Reply URLs</span></span>

<span data-ttu-id="fe06c-151">Adresy URL odpowiedzi są ważne, ponieważ zezwalają one na białą listę domen zwracanych, gdy odwołuje się on B2C usługi Azure AD do uwierzytelnienia użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe06c-151">Reply URLs are important as they allow a whitelist of the return domains when your site calls Azure AD B2C to authenticate a user.</span></span> <span data-ttu-id="fe06c-152">Pozwala to na powrót uwierzytelnionego użytkownika z powrotem do domeny, z której są zalogowani (domena witryny).</span><span class="sxs-lookup"><span data-stu-id="fe06c-152">This allows the return of the authenticated user back to the domain from which they are signing into (your site domain).</span></span> 

<span data-ttu-id="fe06c-153">W polu **adres URL odpowiedzi** na ekranie **B2C Azure AD — Aplikacje \> Nowa aplikacja** należy dodać osobne wiersze dla domeny witryny i (po zainicjowaniu środowiska) wygenerowany w systemie handlowym adres URL.</span><span class="sxs-lookup"><span data-stu-id="fe06c-153">In the **Reply URL** box on the **Azure AD B2c - Applications \> New application** screen, you need to add separate lines for both your site domain and (once your environment is provisioned) the Commerce-generated URL.</span></span> <span data-ttu-id="fe06c-154">Te adresy URL muszą zawsze mieć prawidłowy format adresu URL i muszą być tylko podstawowymi adresami URL (nie można kończyć ukośnikami ani ścieżkami).</span><span class="sxs-lookup"><span data-stu-id="fe06c-154">These URLs must always use a valid URL format and must be base URLs only (no trailing forward slashes or paths).</span></span> <span data-ttu-id="fe06c-155">Następnie należy dołączyć ciąg ``/_msdyn365/authresp`` do podstawowych adresów URL, tak jak w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="fe06c-155">The string ``/_msdyn365/authresp`` then needs to be appended to the base URLs, as in the following examples.</span></span>

- ``https://fabrikam.com/_msdyn365/authresp``
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a><span data-ttu-id="fe06c-156">Tworzenie zasad przepływów użytkownika</span><span class="sxs-lookup"><span data-stu-id="fe06c-156">Create user flow policies</span></span>

<span data-ttu-id="fe06c-157">Przepływy użytkowników to zasady, które B2C Azure AD stosuje w celu zapewnienia bezpiecznego logowania, zapisywania się, edytowania profilu i zapomnienia hasła użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe06c-157">User flows are the policies Azure AD B2C uses to provide secure sign in, sign up, edit profile, and forget password user experiences.</span></span> <span data-ttu-id="fe06c-158">Dynamics 365 Commerce używa tych przepływów do wykonywania akcji związanych z zasadami dotyczącymi interakcji z dzierżawcą B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-158">Dynamics 365 Commerce uses these flows to perform the policy actions to interact with the Azure AD B2C tenant.</span></span> <span data-ttu-id="fe06c-159">Gdy użytkownik współpracuje z tymi zasadami, są one przekierowywane do dzierżawy B2C Azure AD w celu wykonania akcji.</span><span class="sxs-lookup"><span data-stu-id="fe06c-159">When a user interacts with these policies, they are redirected to the Azure AD B2C tenant to perform the actions.</span></span>

<span data-ttu-id="fe06c-160">W B2C Azure AD dostępne są trzy podstawowe typy przepływu użytkownika:</span><span class="sxs-lookup"><span data-stu-id="fe06c-160">Azure AD B2C provides three basic user flow types:</span></span>
- <span data-ttu-id="fe06c-161">Rejestracja i logowanie</span><span class="sxs-lookup"><span data-stu-id="fe06c-161">Sign up and sign in</span></span>
- <span data-ttu-id="fe06c-162">Edytowanie profilu</span><span class="sxs-lookup"><span data-stu-id="fe06c-162">Profile editing</span></span>
- <span data-ttu-id="fe06c-163">Resetowanie hasła</span><span class="sxs-lookup"><span data-stu-id="fe06c-163">Password reset</span></span>

<span data-ttu-id="fe06c-164">Można wybrać Używanie domyślnego przepływu użytkownika dostarczonego przez Azure AD, który będzie wyświetlał stronę hostowaną przez B2C AAD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-164">You can choose to use the default user flows provided by Azure AD, which will display a page hosted by AAD B2C.</span></span> <span data-ttu-id="fe06c-165">Alternatywnie można utworzyć stronę HTML umożliwiającą sterowanie wyglądem i działaniem tych funkcji przepływu pracy użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe06c-165">Alternately, you can create an HTML page to control the look and feel of these user flow experiences.</span></span> 

<span data-ttu-id="fe06c-166">Aby dostosować strony zasad użytkowników dla systemu Dynamics 365 Commerce, należy zapoznać się z tematami [Konfigurowanie niestandardowych stron logowania użytkowników](custom-pages-user-logins.md).</span><span class="sxs-lookup"><span data-stu-id="fe06c-166">To customize the user policy pages for Dynamics 365 Commerce, see [Set up custom pages for user logins](custom-pages-user-logins.md).</span></span> <span data-ttu-id="fe06c-167">Aby uzyskać dodatkowe informacje, należy zapoznać się z tematem [Dostosowywanie interfejsu środowiska użytkownika w B2C Azure Active Directory](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).</span><span class="sxs-lookup"><span data-stu-id="fe06c-167">For additional information, see [Customize the interface of user experiences in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).</span></span>

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a><span data-ttu-id="fe06c-168">Utwórz zasadę przepływu użytkownika rejestracji i logowania</span><span class="sxs-lookup"><span data-stu-id="fe06c-168">Create a sign up and sign in user flow policy</span></span>

<span data-ttu-id="fe06c-169">Aby utworzyć zasady przepływu użytkownika dla rejestracji i logowania, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-169">To create a sign up and sign in user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="fe06c-170">W portalu Azure wybierz pozycję **przepływy użytkowników (zasady)** w lewym okienku nawigacji.</span><span class="sxs-lookup"><span data-stu-id="fe06c-170">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="fe06c-171">Na stronie **B2C Azure AD — przepływy użytkownika (zasady)** wybierz opcję **nowy przepływ użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-171">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="fe06c-172">Na karcie **zalecane** wybierz opcję **Rejestracja i logowanie**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-172">On the **Recommended** tab, select **Sign up and sign in**.</span></span>
1. <span data-ttu-id="fe06c-173">W polu **Nazwa** wprowadź nazwę zasady.</span><span class="sxs-lookup"><span data-stu-id="fe06c-173">Under **Name**, enter a policy name.</span></span> <span data-ttu-id="fe06c-174">Ta nazwa będzie wyświetlana następnie z prefiksem przypisanym przez portal (na przykład „B2C_1_”).</span><span class="sxs-lookup"><span data-stu-id="fe06c-174">This name will display afterwards with a prefix the portal assigns (for example, "B2C_1_").</span></span>
1. <span data-ttu-id="fe06c-175">W obszarze **dostawcy tożsamości** zaznacz odpowiednie pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="fe06c-175">Under **Identity providers**, select the appropriate check box.</span></span>
1. <span data-ttu-id="fe06c-176">W obszarze **uwierzytelnianie wieloczynnikowe** wybierz odpowiedni wybór dla firmy.</span><span class="sxs-lookup"><span data-stu-id="fe06c-176">Under **Multifactor Authentication**, select the appropriate choice for your company.</span></span> 
1. <span data-ttu-id="fe06c-177">W obszarze **atrybuty użytkownika i oświadczenia** wybierz opcje, aby w razie potrzeby zebrać atrybuty lub roszczenia zwrotów.</span><span class="sxs-lookup"><span data-stu-id="fe06c-177">Under **User attributes and claims**, select options to collect attributes or return claims as appropriate.</span></span> <span data-ttu-id="fe06c-178">W rozwiązaniu Commerce są wymagane następujące opcje domyślne:</span><span class="sxs-lookup"><span data-stu-id="fe06c-178">Commerce requires the following default options:</span></span>

    | <span data-ttu-id="fe06c-179">**Zbierz atrybuty**</span><span class="sxs-lookup"><span data-stu-id="fe06c-179">**Collect  attribute**</span></span> | <span data-ttu-id="fe06c-180">**Roszczenie zwrotu**</span><span class="sxs-lookup"><span data-stu-id="fe06c-180">**Return  claim**</span></span> |
    | ---------------------- | ----------------- |
    |                        | <span data-ttu-id="fe06c-181">Adresy e-mail</span><span class="sxs-lookup"><span data-stu-id="fe06c-181">Email Addresses</span></span>   |
    | <span data-ttu-id="fe06c-182">Imię</span><span class="sxs-lookup"><span data-stu-id="fe06c-182">Given Name</span></span>             | <span data-ttu-id="fe06c-183">Imię</span><span class="sxs-lookup"><span data-stu-id="fe06c-183">Given Name</span></span>        |
    |                        | <span data-ttu-id="fe06c-184">Dostawca tożsamości</span><span class="sxs-lookup"><span data-stu-id="fe06c-184">Identity Provider</span></span> |
    | <span data-ttu-id="fe06c-185">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="fe06c-185">Surname</span></span>                | <span data-ttu-id="fe06c-186">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="fe06c-186">Surname</span></span>           |
    |                        | <span data-ttu-id="fe06c-187">Identyfikator obiektu użytkownika</span><span class="sxs-lookup"><span data-stu-id="fe06c-187">User’s Object ID</span></span>  |

1. <span data-ttu-id="fe06c-188">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-188">Select **Create**.</span></span>

<span data-ttu-id="fe06c-189">Poniższy obraz przedstawia przykład B2C Azure AD rejestracji i logowania w przepływie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe06c-189">The following image is an example of the Azure AD B2C sign up and sign in user flow.</span></span>

![Ustawienia zasad rejestracji i logowania](./media/B2CImage_11.png)

<span data-ttu-id="fe06c-191">Poniższy rysunek przedstawia opcję **Uruchom przepływ** użytkownika w B2C Azure AD rejestracja i logowanie w przepływie pracy użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe06c-191">The following image shows the **Run user flow** option in the Azure AD B2C sign up and sign in user flow.</span></span>

![Uruchom opcję przepływu użytkownika w przepływie zasad](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a><span data-ttu-id="fe06c-193">Tworzenie zasady przepływu użytkowników dla edycji profilu</span><span class="sxs-lookup"><span data-stu-id="fe06c-193">Create a profile editing user flow policy</span></span>

<span data-ttu-id="fe06c-194">Aby utworzyć zasady przepływu użytkownika dla edycji profilu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-194">To create a profile editing user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="fe06c-195">W portalu Azure wybierz pozycję **przepływy użytkowników (zasady)** w lewym okienku nawigacji.</span><span class="sxs-lookup"><span data-stu-id="fe06c-195">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="fe06c-196">Na stronie **B2C Azure AD — przepływy użytkownika (zasady)** wybierz opcję **nowy przepływ użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-196">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="fe06c-197">Na karcie **zalecane** wybierz opcję **Edycja profilu**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-197">On the **Recommended** tab, select **Profile editing**.</span></span>
1. <span data-ttu-id="fe06c-198">W polu **Nazwa** wprowadź przepływ użytkownika edycji profilu.</span><span class="sxs-lookup"><span data-stu-id="fe06c-198">Under **Name**, enter the profile editing user flow.</span></span> <span data-ttu-id="fe06c-199">Ta nazwa będzie wyświetlana następnie z prefiksem przypisanym przez portal (na przykład „B2C_1_”).</span><span class="sxs-lookup"><span data-stu-id="fe06c-199">This name will display afterwards with a prefix the portal assigns (for example, "B2C_1_").</span></span>
1. <span data-ttu-id="fe06c-200">W obszarze **dostawcy tożsamości** wybierz opcję **Zaloguj się do konta lokalnego**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-200">Under **Identity providers**, select **Local Account SignIn**.</span></span>
1. <span data-ttu-id="fe06c-201">W obszarze **Atrybuty użytkownika** zaznacz jedno z następujących pól wyboru:</span><span class="sxs-lookup"><span data-stu-id="fe06c-201">Under **User attributes**, select the following check boxes:</span></span>
    - <span data-ttu-id="fe06c-202">**Adresy e-mail** (tylko **Roszczenie zwrotu**)</span><span class="sxs-lookup"><span data-stu-id="fe06c-202">**Email Addresses** (**Return claim** only)</span></span>
    - <span data-ttu-id="fe06c-203">**Imię** (**Zbierz atrybuty** i **roszczenie zwrotne**)</span><span class="sxs-lookup"><span data-stu-id="fe06c-203">**Given Name** (**Collect attribute** and **Return claim**)</span></span>
    - <span data-ttu-id="fe06c-204">**Dostawca tożsamości** (tylko **roszczenie zwrotne**)</span><span class="sxs-lookup"><span data-stu-id="fe06c-204">**Identity Provider** (**Return claim** only)</span></span>
    - <span data-ttu-id="fe06c-205">**Nazwisko** (**Zbierz atrybuty** i **roszczenie zwrotne**)</span><span class="sxs-lookup"><span data-stu-id="fe06c-205">**Surname** (**Collect attribute** and **Return claim**)</span></span>
    - <span data-ttu-id="fe06c-206">**Identyfikator obiektu użytkownika** (tylko **roszczenie zwrotne**)</span><span class="sxs-lookup"><span data-stu-id="fe06c-206">**User's Object ID** (**Return claim** only)</span></span>
1. <span data-ttu-id="fe06c-207">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-207">Select **Create**.</span></span>

<span data-ttu-id="fe06c-208">Poniższy obraz przedstawia przykład przepływu użytkownika edytującego profil w B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-208">The following image shows an example of the Azure AD B2C profile editing user flow.</span></span>

![Tworzenie przepływu użytkowników dla edycji profilu](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a><span data-ttu-id="fe06c-210">Tworzenie zasady przepływu użytkowników dla resetowania hasła</span><span class="sxs-lookup"><span data-stu-id="fe06c-210">Create a password reset user flow policy</span></span>

<span data-ttu-id="fe06c-211">Aby utworzyć zasady przepływu użytkownika dla resetowania hasła, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-211">To create a password reset user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="fe06c-212">W portalu Azure wybierz pozycję **przepływy użytkowników (zasady)** w lewym okienku nawigacji.</span><span class="sxs-lookup"><span data-stu-id="fe06c-212">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="fe06c-213">Na stronie **B2C Azure AD — przepływy użytkownika (zasady)** wybierz opcję **nowy przepływ użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-213">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="fe06c-214">Na karcie **zalecane** wybierz opcję **Reset hasła**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-214">On the **Recommended** tab, select **Password Reset**.</span></span>
1. <span data-ttu-id="fe06c-215">W polu **Nazwa** wprowadź nazwę przepływu użytkownika resetowania hasła.</span><span class="sxs-lookup"><span data-stu-id="fe06c-215">Under **Name**, enter a name for the password reset user flow.</span></span>
1. <span data-ttu-id="fe06c-216">W sekcji **dostawcy tożsamości** wybierz opcję **Resetuj hasło, używając adresu e-mail**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-216">Under **Identity providers**, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="fe06c-217">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-217">Select **Create**.</span></span>
1. <span data-ttu-id="fe06c-218">W obszarze **Przetwarzanie aplikacji** zaznacz jedno z następujących pól wyboru:</span><span class="sxs-lookup"><span data-stu-id="fe06c-218">Under **Application claims**, select the following check boxes:</span></span>
    - <span data-ttu-id="fe06c-219">**E-mail**</span><span class="sxs-lookup"><span data-stu-id="fe06c-219">**Email**</span></span>
    - <span data-ttu-id="fe06c-220">**Adresy**</span><span class="sxs-lookup"><span data-stu-id="fe06c-220">**Addresses**</span></span>
    - <span data-ttu-id="fe06c-221">**Imię**</span><span class="sxs-lookup"><span data-stu-id="fe06c-221">**Given Name**</span></span>
    - <span data-ttu-id="fe06c-222">**Nazwisko**</span><span class="sxs-lookup"><span data-stu-id="fe06c-222">**Surname**</span></span>
    - <span data-ttu-id="fe06c-223">**Identyfikator obiektu użytkownika**</span><span class="sxs-lookup"><span data-stu-id="fe06c-223">**User's Object ID**</span></span>
1. <span data-ttu-id="fe06c-224">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-224">Select **Create**.</span></span>

<span data-ttu-id="fe06c-225">Poniższy obraz pokazuje, gdzie ustawić **hasło resetowania przy użyciu adresu pocztowego** w przepływie użytkownika resetowania hasła B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-225">The following image shows where to set **Reset Password using mail address** in the Azure AD B2C password reset user flow.</span></span>

![Ustawienie „Resetuj hasło przy użyciu adresu pocztowego” w zasadach resetowania hasła](./media/B2CImage_13.png)

## <a name="add-social-identity-providers-optional"></a><span data-ttu-id="fe06c-227">Dodaj dostawców tożsamości społecznościowych (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="fe06c-227">Add social identity providers (Optional)</span></span>

<span data-ttu-id="fe06c-228">Dostawcy tożsamości społecznościowych umożliwiają użytkownikom uwierzytelnianie przy użyciu ich kont społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="fe06c-228">Social identity providers allow users to use their social accounts for authentication.</span></span> <span data-ttu-id="fe06c-229">Dodawanie uwierzytelniania dostawcy tożsamości społecznościowej jest opcjonalne w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe06c-229">Adding social identity provider authentication is optional in Dynamics 365 Commerce.</span></span> 

<span data-ttu-id="fe06c-230">Jeśli uwierzytelnianie dostawcy tożsamości społecznościowej nie zostanie dodane, domyślne profile B2C Azure AD będą głównymi profilami bazy danych użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe06c-230">If social identity provider authentication is not added, the default Azure AD B2C profiles will be the main profiles for your user base.</span></span> <span data-ttu-id="fe06c-231">Użytkownicy będą mogli wybrać własną nazwę użytkownika (preferowany adres e-mail) i określić hasło.</span><span class="sxs-lookup"><span data-stu-id="fe06c-231">Users will select their own username (their preferred email address) and set a password.</span></span> <span data-ttu-id="fe06c-232">B2C Azure AD będą uwierzytelniać użytkowników bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="fe06c-232">Azure AD B2C will authenticate users directly.</span></span> 

<span data-ttu-id="fe06c-233">Jeśli zostanie dodane uwierzytelnianie dostawcy tożsamości społecznej, a użytkownik wybierze jednego z oferowanych dostawców tożsamości społecznych, jednostka nadal zostanie utworzona w dzierżawie B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-233">If social identity provider authentication is added and a user chooses one of the social identity providers offered, an entity is still created in the Azure AD B2C tenant.</span></span> <span data-ttu-id="fe06c-234">B2C Azure AD będzie wówczas uwierzytelniać poświadczenia użytkownika za pomocą dostawcy tożsamości społecznościowej.</span><span class="sxs-lookup"><span data-stu-id="fe06c-234">Azure AD B2C will then authenticate the user's credentials with the social identity provider.</span></span>

> [!NOTE]
> <span data-ttu-id="fe06c-235">W trakcie logowania dostawca tożsamości tworzy rekord w dzierżawie B2C, ale w innym formacie niż konta lokalne, ponieważ będzie wywoływać odwołanie do zewnętrznego dostawcy tożsamości społecznościowej w celu uwierzytelnienia.</span><span class="sxs-lookup"><span data-stu-id="fe06c-235">The identity provider sign in creates a record in the B2C tenant, but in a different format than local accounts since it will call the external social identity provider reference for authentication.</span></span> <span data-ttu-id="fe06c-236">Użytkownik może używać tego samego adresu e-mail dla dostawców tożsamości społecznych, co oznacza, że nazwa użytkownika poczty e-mail używana do uwierzytelniania może nie być unikatowa dla dzierżawcy.</span><span class="sxs-lookup"><span data-stu-id="fe06c-236">The user can use the same email address across social identity providers, meaning that the email username used for authentication may not be unique to the tenant.</span></span> <span data-ttu-id="fe06c-237">B2C Azure AD wymusza, aby użytkownicy mieli unikatowy adres e-mail tylko na lokalnych kontach B2C.</span><span class="sxs-lookup"><span data-stu-id="fe06c-237">Azure AD B2C will only enforce that users have a unique email address on local B2C accounts.</span></span>

<span data-ttu-id="fe06c-238">Zanim będzie można dodać dostawcę tożsamości społecznościowej do uwierzytelniania, należy przejść do portalu dostawcy tożsamości i skonfigurować aplikację dostawcy tożsamości zgodnie z instrukcją w dokumentacji B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-238">Before you can add a social identity provider for authentication, you must go to the identity provider's portal and set up an identity provider application as instructed in the Azure AD B2C documentation.</span></span> <span data-ttu-id="fe06c-239">Poniżej znajduje się lista łączy do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="fe06c-239">A list of links to the documentation is provided below.</span></span>

- [<span data-ttu-id="fe06c-240">Amazon</span><span class="sxs-lookup"><span data-stu-id="fe06c-240">Amazon</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [<span data-ttu-id="fe06c-241">Azure AD (Jeden dzierżawca)</span><span class="sxs-lookup"><span data-stu-id="fe06c-241">Azure AD (Single Tenant)</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [<span data-ttu-id="fe06c-242">Konto Microsoft</span><span class="sxs-lookup"><span data-stu-id="fe06c-242">Microsoft Account</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [<span data-ttu-id="fe06c-243">Facebook</span><span class="sxs-lookup"><span data-stu-id="fe06c-243">Facebook</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [<span data-ttu-id="fe06c-244">GitHub</span><span class="sxs-lookup"><span data-stu-id="fe06c-244">GitHub</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [<span data-ttu-id="fe06c-245">Google</span><span class="sxs-lookup"><span data-stu-id="fe06c-245">Google</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [<span data-ttu-id="fe06c-246">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="fe06c-246">LinkedIn</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [<span data-ttu-id="fe06c-247">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="fe06c-247">OpenID Connect</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [<span data-ttu-id="fe06c-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="fe06c-248">Twitter</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a><span data-ttu-id="fe06c-249">Dodaj i skonfiguruj dostawcę tożsamości społecznościowej</span><span class="sxs-lookup"><span data-stu-id="fe06c-249">Add and set up a social identity provider</span></span>

<span data-ttu-id="fe06c-250">Aby dodać i skonfigurować dostawcę tożsamości społecznościowej, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-250">To add and set up a social identity provider, follow these steps.</span></span>  

1. <span data-ttu-id="fe06c-251">W portalu Azure przejdź do **dostawców tożsamości**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-251">In the Azure portal, navigate to **Identity Providers**.</span></span>
1. <span data-ttu-id="fe06c-252">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-252">Select **Add**.</span></span> <span data-ttu-id="fe06c-253">Pojawi się ekran **Dodaj dostawcę tożsamości**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-253">The **Add identity provider** screen appears.</span></span>
1. <span data-ttu-id="fe06c-254">W polu **Nazwa** wprowadź nazwę, która ma być wyświetlana użytkownikom na ekranie logowania.</span><span class="sxs-lookup"><span data-stu-id="fe06c-254">Under **Name**, enter the name to be displayed to users on your sign in screen.</span></span>
1. <span data-ttu-id="fe06c-255">W obszarze **Typ dostawcy tożsamości** wybierz dostawcę tożsamości z listy.</span><span class="sxs-lookup"><span data-stu-id="fe06c-255">Under **Identity provider type**, select an identity provider from the list.</span></span>
1. <span data-ttu-id="fe06c-256">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-256">Select **OK**.</span></span>
1. <span data-ttu-id="fe06c-257">Wybierz opcję **Skonfiguruj tego dostawcę tożsamości**, aby uzyskać dostęp do ekranu **Konfigurowanie dostawcy tożsamości społecznych**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-257">Select **Set up this identity provider** to access the **Set up the social identity provider** screen.</span></span>
1. <span data-ttu-id="fe06c-258">W obszarze **Identyfikator klienta** wprowadź identyfikator klienta, który został otrzymany z konfiguracji aplikacji dostawcy tożsamości.</span><span class="sxs-lookup"><span data-stu-id="fe06c-258">Under **Client ID**, enter the client ID as obtained from the identity provider application setup.</span></span>
1. <span data-ttu-id="fe06c-259">W obszarze **Nazwa tajna klienta** wprowadź nazwę tajną klienta, która została otrzymana z konfiguracji aplikacji dostawcy tożsamości.</span><span class="sxs-lookup"><span data-stu-id="fe06c-259">Under **Client secret**, enter the client secret as obtained from the identity provider application setup.</span></span>
1. <span data-ttu-id="fe06c-260">Dołącz przepływ użytkownika dla logowania w zasadach rejestracji:</span><span class="sxs-lookup"><span data-stu-id="fe06c-260">Attach user flow for sign in sign up policies:</span></span>
1. <span data-ttu-id="fe06c-261">Przejdź do **B2C Azure AD — przepływy tożsamości \> {zasady logowania rejestracji użytkowników} \> Dostawcy tożsamości**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-261">Go to **Azure AD B2C – User flows (policies) \> {your sign-in sign-up policy} \> Identity providers**.</span></span>
1. <span data-ttu-id="fe06c-262">Aby dołączyć zasadę przepływu użytkowników logowania/rejestracji, wybierz każdego dostawcę tożsamości skonfigurowanego dla swojego konta.</span><span class="sxs-lookup"><span data-stu-id="fe06c-262">To attach the sign in/sign up user flow policy, select each identity provider you have set up for your account.</span></span> <span data-ttu-id="fe06c-263">Aby je przetestować, wybierz opcję **Uruchom przepływ użytkownika** dla każdego dostawcy tożsamości.</span><span class="sxs-lookup"><span data-stu-id="fe06c-263">To test these, select **Run user flow** for each identity provider.</span></span> <span data-ttu-id="fe06c-264">Na nowej karcie zostanie wyświetlona strona logowania z wyświetlonym polem wyboru nowego dostawcy tożsamości.</span><span class="sxs-lookup"><span data-stu-id="fe06c-264">A new tab will display the sign-in page displaying the new identity provider selection box.</span></span>

<span data-ttu-id="fe06c-265">Na poniższym obrazie pokazano przykłady **dodawania dostawcy tożsamości** i **konfigurowania ekranów dostawcy tożsamości społecznościowych** w B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-265">The following image shows examples of the **Add identity provider** and **Set up the social identity provider** screens in Azure AD B2C.</span></span>

![Dodawanie dostawcy tożsamości społecznościowej do aplikacji](./media/B2CImage_14.png)

<span data-ttu-id="fe06c-267">Poniższy rysunek przedstawia przykład wyboru dostawców tożsamości na stronie **dostawców tożsamości** B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-267">The following image shows an example of how to select identity providers on the Azure AD B2C **Identity Providers** page.</span></span>

![Wybierz każdego dostawcę tożsamości społecznościowych, który ma być włączony dla zasady](./media/B2CImage_16.png)

<span data-ttu-id="fe06c-269">Poniższy obraz przedstawia przykład domyślnego ekranu logowania z wyświetlonym przyciskiem logowania dostawcy tożsamości społecznościowej.</span><span class="sxs-lookup"><span data-stu-id="fe06c-269">The following image shows an example of a default sign-in screen with a social identity provider sign-in button displayed.</span></span>

![Przykładowy domyślny ekran logowania z wyświetlonym przyciskiem logowania dostawcy tożsamości społecznościowej](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a><span data-ttu-id="fe06c-271">Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD</span><span class="sxs-lookup"><span data-stu-id="fe06c-271">Update Commerce headquarters with the new Azure AD B2C information</span></span>

<span data-ttu-id="fe06c-272">Po wykonaniu powyższej procedury B2C Azure AD, aplikacja B2C Azure AD musi być zarejestrowana w środowisku Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe06c-272">Once the Azure AD B2C provisioning steps above are completed, the Azure AD B2C application must be registered in your Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="fe06c-273">Aby zaktualizować centralę za pomocą nowych informacji B2C Azure AD, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-273">To update headquarters with the new Azure AD B2C information, follow these steps.</span></span>

1. <span data-ttu-id="fe06c-274">W module Commerce przejdź do **udostępnionych parametrów modułu Commerce** i wybierz pozycję **dostawcy tożsamości** w lewym menu.</span><span class="sxs-lookup"><span data-stu-id="fe06c-274">In Commerce, go to **Commerce Shared Parameters** and select **Identity Providers** in the left menu.</span></span>
1. <span data-ttu-id="fe06c-275">W obszarze **dostawcy tożsamości** wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="fe06c-275">Under **Identity Providers**, do the following:</span></span>
    1. <span data-ttu-id="fe06c-276">W polu **wystawca** wprowadź adres URL wystawcy dostawcy tożsamości.</span><span class="sxs-lookup"><span data-stu-id="fe06c-276">In the **Issuer** box, enter the identity provider issuer URL.</span></span> <span data-ttu-id="fe06c-277">Aby znaleźć adres URL wystawcy, przeczytaj [Uzyskaj adres URL wystawcy](#obtain-issuer-url) poniżej.</span><span class="sxs-lookup"><span data-stu-id="fe06c-277">To find your issuer URL, see [Obtain issuer URL](#obtain-issuer-url) below.</span></span>
    1. <span data-ttu-id="fe06c-278">W polu **nazwa** wprowadź nazwę rekordu wystawcy.</span><span class="sxs-lookup"><span data-stu-id="fe06c-278">In the **Name** box, enter a name for your issuer record.</span></span>
    1. <span data-ttu-id="fe06c-279">W polu **typ** wprowadź **B2C Azure AD (id_token)**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-279">In the **Type** box, enter **Azure AD B2C (id_token)**.</span></span>
1. <span data-ttu-id="fe06c-280">W obszarze **jednostki uzależnione**, z zaznaczonym powyższym elementem dostawcy tożsamości B2C, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="fe06c-280">Under **Relying Parties**, with the above B2C identity provider item selected, do the following:</span></span>
    1. <span data-ttu-id="fe06c-281">W polu **ClientID** wprowadź swój identyfikator aplikacji B2C.</span><span class="sxs-lookup"><span data-stu-id="fe06c-281">In the **ClientID** box, enter your B2C application ID.</span></span> <span data-ttu-id="fe06c-282">Tę nazwę można znaleźć w polu **identyfikator aplikacji** na stronie właściwości aplikacji B2C.</span><span class="sxs-lookup"><span data-stu-id="fe06c-282">You can find this in the **Application ID** box of your B2C application's properties page.</span></span>
    1. <span data-ttu-id="fe06c-283">W polu **typ** wprowadź wartość **publiczne**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-283">In the **Type** box, enter **Public**.</span></span>
    1. <span data-ttu-id="fe06c-284">W polu **typ użytkownika** wprowadź wartość **Odbiorca**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-284">In the **User Type** box, enter **Customer**.</span></span>
1. <span data-ttu-id="fe06c-285">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-285">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="fe06c-286">W polu Wyszukiwanie w module Commerce można wyszukiwać **sekwencje numerów** (Administrowanie organizacją > sekwencje numerów).</span><span class="sxs-lookup"><span data-stu-id="fe06c-286">In the Commerce search box, search for **Number sequences** (Organization administration > Number sequences).</span></span>
1. <span data-ttu-id="fe06c-287">W okienku akcji wybierz opcję **Edytuj** w obszarze **obsługa**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-287">Under the action pane, select **Edit** under **Maintain**.</span></span>
1. <span data-ttu-id="fe06c-288">Na skróconej karcie **Ogólne** wybierz opcję **nie** dla **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-288">On the **General** fast tab, select **No** for **Manual**.</span></span>
1. <span data-ttu-id="fe06c-289">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-289">On the action pane, select **Save**.</span></span> 
1. <span data-ttu-id="fe06c-290">W polu Wyszukiwanie w module Commerce należy wyszukać **harmonogram dystrybucji**</span><span class="sxs-lookup"><span data-stu-id="fe06c-290">In the Commerce search box, search for **Distribution schedule**</span></span>
1. <span data-ttu-id="fe06c-291">W menu nawigacji w lewym panelu na stronie **harmonogramy dystrybucji** wybierz zadanie **Konfiguracja globalna 1110**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-291">In the left navigation menu of the **Distribution schedules** page, select job **1110 Global configuration**.</span></span>
1. <span data-ttu-id="fe06c-292">W okienku akcji wybierz opcję **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-292">On the action pane, select **Run Now**.</span></span>

### <a name="obtain-issuer-url"></a><span data-ttu-id="fe06c-293">Uzyskaj adres URL wystawcy</span><span class="sxs-lookup"><span data-stu-id="fe06c-293">Obtain issuer URL</span></span>

<span data-ttu-id="fe06c-294">Aby uzyskać adres URL wystawcy dostawcy tożsamości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-294">To obtain your identity provider issuer URL, follow these steps.</span></span>

1. <span data-ttu-id="fe06c-295">Utwórz adres URL metadanych w poniższym formacie przy użyciu dzierżawy i zasad B2C: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``</span><span class="sxs-lookup"><span data-stu-id="fe06c-295">Create a metadata address URL in the following format using your B2C tenant and policy: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``</span></span>
    - <span data-ttu-id="fe06c-296">Przykład: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``</span><span class="sxs-lookup"><span data-stu-id="fe06c-296">Example: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.</span></span>
1. <span data-ttu-id="fe06c-297">Wprowadź adres URL metadanych na pasku adresu przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-297">Enter the metadata address URL into a browser address bar.</span></span>
1. <span data-ttu-id="fe06c-298">W metadanych Skopiuj adres URL wystawcy dostawcy tożsamości (wartość dla **„wystawca”**).</span><span class="sxs-lookup"><span data-stu-id="fe06c-298">In the metadata, copy the identity provider issuer URL (the value for **"issuer"**).</span></span>
    - <span data-ttu-id="fe06c-299">Przykład: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``</span><span class="sxs-lookup"><span data-stu-id="fe06c-299">Example: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.</span></span>

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a><span data-ttu-id="fe06c-300">Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce</span><span class="sxs-lookup"><span data-stu-id="fe06c-300">Configure your B2C tenant in Commerce site builder</span></span>

<span data-ttu-id="fe06c-301">Po zakończeniu konfigurowania dzierżawy B2C Azure AD należy skonfigurować dzierżawę B2C w module kreatora witryny Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe06c-301">Once setup of your Azure AD B2C tenant is completed, you must configure the B2C tenant in Commerce site builder.</span></span> <span data-ttu-id="fe06c-302">Kroki konfiguracyjne obejmują zbieranie informacji o aplikacji B2C z portalu Azure, wprowadzenie do konstruktora witryn informacji o aplikacji B2C, a następnie skojarzenie aplikacji B2C z witryną i kanałem.</span><span class="sxs-lookup"><span data-stu-id="fe06c-302">Configuration steps include collecting B2C application information from the Azure portal, entering that B2C application information into site builder, and then associating the B2C application with your site and channel.</span></span>

### <a name="collect-the-required-application-information"></a><span data-ttu-id="fe06c-303">Zbierz wymagane informacje o aplikacji</span><span class="sxs-lookup"><span data-stu-id="fe06c-303">Collect the required application information</span></span>

<span data-ttu-id="fe06c-304">Aby zebrać wymagane informacje o aplikacji, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-304">To collect the required application information, follow these steps.</span></span>

1. <span data-ttu-id="fe06c-305">W portalu Azure przejdź do **Strony głównej \> B2C Azure AD — aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-305">In the Azure portal, go to **Home \> Azure AD B2C - Applications**.</span></span>
1. <span data-ttu-id="fe06c-306">Wybierz aplikację, a następnie w lewym okienku nawigacji wybierz **właściwości**, aby uzyskać szczegółowe informacje o aplikacji.</span><span class="sxs-lookup"><span data-stu-id="fe06c-306">Select your application, and then in the left navigation pane select **Properties** to obtain the application details.</span></span>
1. <span data-ttu-id="fe06c-307">W polu **identyfikator aplikacji** Zbierz identyfikator aplikacji B2C utworzonej w dzierżawie B2C.</span><span class="sxs-lookup"><span data-stu-id="fe06c-307">From the **Application ID** box, collect the application ID of the B2C application created in your B2C tenant.</span></span> <span data-ttu-id="fe06c-308">Zostanie to później wprowadzone jako **identyfikator GUID klienta** w module Konstruktor witryn.</span><span class="sxs-lookup"><span data-stu-id="fe06c-308">This will later be entered as the **Client GUID** in site builder.</span></span>
1. <span data-ttu-id="fe06c-309">W obszarze **adres URL odpowiedzi** Zbierz adres URL odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="fe06c-309">Under **Reply URL**, collect the reply URL.</span></span>
1. <span data-ttu-id="fe06c-310">Przejdź do **Strona główna \> B2C Azure AD — przepływy użytkownika (zasady)**, a następnie Zbierz nazwy poszczególnych zasad przepływu użytkowników.</span><span class="sxs-lookup"><span data-stu-id="fe06c-310">Go to **Home \> Azure AD B2C – User flows (policies)**, and then collect the names of each user flow policy.</span></span>

<span data-ttu-id="fe06c-311">Poniższy rysunek przedstawia przykład strony **B2C Azure AD — aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-311">The following image shows an example of the **Azure AD B2C - Applications** page.</span></span>

![Przejdź do aplikacji B2C w dzierżawie](./media/B2CImage_19.png)

<span data-ttu-id="fe06c-313">Poniższy rysunek przedstawia przykład strony aplikacji **Właściwości** w B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fe06c-313">The following image shows an example of an application **Properties** page in Azure AD B2C.</span></span> 

![Kopiuj identyfikator aplikacji z właściwości aplikacji B2C](./media/B2CImage_21.png)

<span data-ttu-id="fe06c-315">Poniższy obraz przedstawia przykład zasad przepływu użytkowników na stronie **B2C Azure AD — przepływy użytkownika (zasady)**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-315">The following image shows an example of user flow policies on the **Azure AD B2C – User flows (policies)** page.</span></span>

![Zbierz nazwy poszczególnych przepływów zasad B2C](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a><span data-ttu-id="fe06c-317">Umożliwia wprowadzenie informacji dotyczących aplikacji dzierżawczej usługi AAD B2C do modułu Commerce</span><span class="sxs-lookup"><span data-stu-id="fe06c-317">Enter your AAD B2C tenant application information into Commerce</span></span>

<span data-ttu-id="fe06c-318">Przed skojarzeniem dzierżawy B2C Azure AD z witrynami należy wprowadzić szczegóły dzierżawy B2C w module konstruktora witryn Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe06c-318">You must enter details of the Azure AD B2C tenant into Commerce site builder before associating the B2C tenant with your site(s).</span></span>

<span data-ttu-id="fe06c-319">Aby dodać informacje dotyczące aplikacji dzierżawczej usługi B2C AAD do systemu Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-319">To add your AAD B2C tenant application information to Commerce, follow these steps.</span></span>

1. <span data-ttu-id="fe06c-320">Zaloguj się jako administrator do modułu konstruktora witryn Commerce dla swojego środowiska.</span><span class="sxs-lookup"><span data-stu-id="fe06c-320">Sign in as an administrator to Commerce site builder for your environment.</span></span>
1. <span data-ttu-id="fe06c-321">W lewym okienku nawigacji wybierz pozycję **Ustawienia dzierżawcy**, aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="fe06c-321">In the left navigation pane, select **Tenant Settings**  to expand it.</span></span>
1. <span data-ttu-id="fe06c-322">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Ustawienia B2C**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-322">Under **Tenant Settings**, select **B2C Settings**.</span></span> 
1. <span data-ttu-id="fe06c-323">W oknie głównym obok **Aplikacje B2C**wybierz opcję **Zarządzaj**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-323">In the main window next **B2C Applications**, select **Manage**.</span></span> <span data-ttu-id="fe06c-324">(Jeśli Twoja dzierżawa jest wyświetlana na liście aplikacji B2C, została ona już dodana przez administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="fe06c-324">(If your tenant appears in the B2C Applications list, then it was already added by an administrator.</span></span> <span data-ttu-id="fe06c-325">Sprawdź, czy elementy w kroku 6 są zgodne z aplikacją B2C.)</span><span class="sxs-lookup"><span data-stu-id="fe06c-325">Verify that the items in step 6 below match your B2C Application.)</span></span>
1. <span data-ttu-id="fe06c-326">Wybierz **Dodaj aplikację B2C**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-326">Select **Add B2C Application**.</span></span>
1. <span data-ttu-id="fe06c-327">Wprowadź w wyświetlonym formularzu następujące wymagane elementy, używając wartości ze swojej dzierżawy B2C i aplikacji.</span><span class="sxs-lookup"><span data-stu-id="fe06c-327">Enter the following required items in the form displayed, using values from your B2C tenant and application.</span></span> <span data-ttu-id="fe06c-328">Pola, które nie są wymagane (bez gwiazdki), mogą pozostać puste.</span><span class="sxs-lookup"><span data-stu-id="fe06c-328">Fields that are not required (those without an asterisk) may be left blank.</span></span>

    - <span data-ttu-id="fe06c-329">**Nazwa aplikacji**: Nazwa aplikacji B2C, na przykład „Fabrikam B2C”.</span><span class="sxs-lookup"><span data-stu-id="fe06c-329">**Application Name**: The name for your B2C Application, for example "Fabrikam B2C".</span></span>
    - <span data-ttu-id="fe06c-330">**Nazwa dzierżawcy**: nazwa dzierżawy B2C, na przykład „Fabrikam”.</span><span class="sxs-lookup"><span data-stu-id="fe06c-330">**Tenant Name**: The name of your B2C Tenant, for example "Fabrikam".</span></span>
    - <span data-ttu-id="fe06c-331">**Identyfikator zasady zapominania hasła**: identyfikator zasady przepływu użytkownika zapominania hasła, na przykład „B2C_1_PasswordReset”.</span><span class="sxs-lookup"><span data-stu-id="fe06c-331">**Forget Password Policy ID**: The forget password user flow policy ID, for example "B2C_1_PasswordReset".</span></span>
    - <span data-ttu-id="fe06c-332">**Identyfikator zasad logowania rejestracji**: Identyfikator zasad tworzenia konta i logowania użytkownika, na przykład „B2C_1_signup_signin”.</span><span class="sxs-lookup"><span data-stu-id="fe06c-332">**Signup Signin Policy ID**: The sign up and sign in user flow policy ID, for example "B2C_1_signup_signin".</span></span>
    - <span data-ttu-id="fe06c-333">**Identyfikator GUID klienta**: Identyfikator aplikacji B2C, na przykład „22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6”.</span><span class="sxs-lookup"><span data-stu-id="fe06c-333">**Client GUID**: The B2C application ID, for example "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".</span></span>
    - <span data-ttu-id="fe06c-334">**Identyfikator zasad edycji profilu**: Identyfikator zasad przepływu użytkownika edycji profilu, na przykład „B2C_1A_ProfileEdit”.</span><span class="sxs-lookup"><span data-stu-id="fe06c-334">**Edit Profile Policy ID**: The profile editing user flow policy ID, for example "B2C_1A_ProfileEdit".</span></span>

1. <span data-ttu-id="fe06c-335">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-335">Select **OK**.</span></span> <span data-ttu-id="fe06c-336">Na liście powinna być widoczna nazwa aplikacji B2C.</span><span class="sxs-lookup"><span data-stu-id="fe06c-336">You should now see the name of your B2C application appear in the list.</span></span>

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a><span data-ttu-id="fe06c-337">Skojarz aplikację B2C z witryną i kanałem</span><span class="sxs-lookup"><span data-stu-id="fe06c-337">Associate the B2C application to your site and channel</span></span>

> [!WARNING]
> <span data-ttu-id="fe06c-338">Jeśli witryna jest już skojarzona z aplikacją B2C, zmiana w innej aplikacji B2C spowoduje usunięcie bieżących odwołań ustanowionych dla użytkowników już zarejestrowanych w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="fe06c-338">If your site is already associated with a B2C application, changing to a different B2C application will remove the current references established for users already signed up in this environment.</span></span> <span data-ttu-id="fe06c-339">W przypadku zmiany wszelkie poświadczenia skojarzone z aktualnie przypisaną aplikacją B2C nie będą dostępne dla użytkowników.</span><span class="sxs-lookup"><span data-stu-id="fe06c-339">If changed, any credentials associated with the currently-assigned B2C application will not be available to users.</span></span> 
> 
> <span data-ttu-id="fe06c-340">Aplikację B2C należy aktualizować tylko wtedy, gdy jest ustawiany kanał aplikacji B2C po raz pierwszy lub jeśli użytkownik chce, aby użytkownicy mogli ponownie rejestrować się z nowymi poświadczeniami w tym kanale z nową aplikacją B2C.</span><span class="sxs-lookup"><span data-stu-id="fe06c-340">Only update the B2C application if you are setting up the channel's B2C application for the first time or if you intend to have users re-sign up with new credentials to this channel with the new B2C application.</span></span> <span data-ttu-id="fe06c-341">Należy zachować ostrożność podczas kojarzenia kanałów z aplikacjami B2C i jasno określać nazwy aplikacji.</span><span class="sxs-lookup"><span data-stu-id="fe06c-341">Take caution when associating channels to B2C applications, and name applications clearly.</span></span> <span data-ttu-id="fe06c-342">Jeśli kanał nie jest skojarzony z aplikacją B2C w poniższych krokach, użytkownicy logujący się do tego kanału witryny będą wprowadzani do aplikacji B2C, która jest wyświetlana **domyślnie** na liście aplikacji B2C **Ustawienia dzierżawcy \> Ustawienia B2C**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-342">If a channel is not associated to a B2C application in the steps below, users signing into that channel for your site will be entered into the B2C application showing as **default** in the **Tenant Settings \> B2C Settings** list of B2C applications.</span></span>

<span data-ttu-id="fe06c-343">Aby skojarzyć aplikację B2C z witryną i kanałem, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="fe06c-343">To associate the B2C application to your site and channel, follow these steps.</span></span>

1. <span data-ttu-id="fe06c-344">Przejdź do swojej witryny w module konstruktora witryn Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe06c-344">Navigate to your site in Commerce site builder.</span></span>
1. <span data-ttu-id="fe06c-345">W lewym okienku nawigacji wybierz pozycję **Ustawienia witryny**, aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="fe06c-345">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="fe06c-346">W obszarze **Ustawienia witryny** wybierz opcję **kanały**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-346">Below **Site Settings**, select **Channels**.</span></span>
1. <span data-ttu-id="fe06c-347">W oknie głównym w obszarze **kanały**wybierz kanał.</span><span class="sxs-lookup"><span data-stu-id="fe06c-347">In the main window under **Channels**, select your channel.</span></span>
1. <span data-ttu-id="fe06c-348">W okienku właściwości kanału z prawej strony wybierz nazwę aplikacji B2C z menu rozwijanego **wybierz aplikację B2C**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-348">In the channel properties pane on the right, select your B2C application name from the **Select B2C Application** drop down menu.</span></span>
1. <span data-ttu-id="fe06c-349">Wybierz opcję **Zamknij**, a następnie wybierz opcję **Zapisz i opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="fe06c-349">Select **Close**, and then select **Save and Publish**.</span></span>

## <a name="additional-b2c-information"></a><span data-ttu-id="fe06c-350">Informacje dodatkowe o B2C</span><span class="sxs-lookup"><span data-stu-id="fe06c-350">Additional B2C information</span></span>

### <a name="customer-migration"></a><span data-ttu-id="fe06c-351">Migracja odbiorcy</span><span class="sxs-lookup"><span data-stu-id="fe06c-351">Customer migration</span></span>

<span data-ttu-id="fe06c-352">Jeśli rozważasz Migrowanie rekordów klientów z poprzedniej platformy dostawców tożsamości, skontaktuj się z zespołem Dynamics 365 Commerce, aby przejrzeć potrzeby dotyczące migracji odbiorców.</span><span class="sxs-lookup"><span data-stu-id="fe06c-352">If you are considering migrating customer records from a previous identity provider platform, please work with the Dynamics 365 Commerce team to review your customer migration needs.</span></span>

<span data-ttu-id="fe06c-353">Aby uzyskać dodatkową dokumentację B2C Azure AD dotyczącą migracji klientów, należy zapoznać się z tematem [Migrowanie użytkowników do B2C Azure Active Directory](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).</span><span class="sxs-lookup"><span data-stu-id="fe06c-353">For additional Azure AD B2C documentation on customer migration, see [Migrate users to Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).</span></span>

### <a name="custom-policies"></a><span data-ttu-id="fe06c-354">Zasady niestandardowe</span><span class="sxs-lookup"><span data-stu-id="fe06c-354">Custom policies</span></span>

<span data-ttu-id="fe06c-355">Aby uzyskać dodatkowe informacje dotyczące dostosowywania interakcji B2C Azure AD i przepływów zasad ponad to, co jest oferowane przez zasady standardowe B2C, zapoznać się z [zasadami niestandardowymi w B2C Azure Active Directory](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom).</span><span class="sxs-lookup"><span data-stu-id="fe06c-355">For additional information regarding customizing Azure AD B2C interactions and policy flows beyond what is offered by B2C standard policies, see [Custom policies in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom).</span></span> 

### <a name="secondary-admin"></a><span data-ttu-id="fe06c-356">Administrator pomocniczy</span><span class="sxs-lookup"><span data-stu-id="fe06c-356">Secondary admin</span></span>

<span data-ttu-id="fe06c-357">W sekcji **użytkownicy** dzierżawy B2C można dodać opcjonalne pomocnicze konto administratora.</span><span class="sxs-lookup"><span data-stu-id="fe06c-357">An optional, secondary administrator account can be added in the **Users** section of your B2C tenant.</span></span> <span data-ttu-id="fe06c-358">Może to być konto bezpośrednie lub konto ogólne.</span><span class="sxs-lookup"><span data-stu-id="fe06c-358">This can be a direct account or a general account.</span></span> <span data-ttu-id="fe06c-359">Jeśli trzeba udostępnić konto w zasobach zespołu, można również utworzyć wspólne konto.</span><span class="sxs-lookup"><span data-stu-id="fe06c-359">If you need to share an account across team resources, a common account can also be created.</span></span> <span data-ttu-id="fe06c-360">Ze względu na wagę danych przechowywanych w B2C Azure AD, wspólne konto powinno być ściśle monitorowane zgodnie z zasadami zabezpieczeń firmy.</span><span class="sxs-lookup"><span data-stu-id="fe06c-360">Due to the sensitivity of the data stored in Azure AD B2C, a common account should be monitored closely per your company's security practices.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fe06c-361">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fe06c-361">Additional resources</span></span>

[<span data-ttu-id="fe06c-362">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="fe06c-362">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="fe06c-363">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="fe06c-363">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="fe06c-364">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="fe06c-364">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="fe06c-365">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="fe06c-365">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="fe06c-366">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="fe06c-366">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="fe06c-367">Przekaż adresy URL przekierowań luzem</span><span class="sxs-lookup"><span data-stu-id="fe06c-367">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="fe06c-368">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="fe06c-368">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="fe06c-369">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="fe06c-369">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="fe06c-370">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="fe06c-370">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="fe06c-371">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="fe06c-371">Enable location-based store detection</span></span>](enable-store-detection.md)
