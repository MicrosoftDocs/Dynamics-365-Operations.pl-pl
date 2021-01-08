---
title: Uwierzytelnianie
description: W tym artykule zamieszczono przegląd informacji na temat sposobów uwierzytelniania w interfejsie programowania aplikacji (API) modułu Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a0509ce99205d49d516e180203ffb65a1dc09a7c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420000"
---
# <a name="authentication"></a><span data-ttu-id="f8762-103">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="f8762-103">Authentication</span></span>

<span data-ttu-id="f8762-104">W tym artykule zamieszczono przegląd informacji na temat sposobów uwierzytelniania w interfejsie programowania aplikacji (API) modułu Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f8762-104">This article provides overview information about how to authenticate with the Microsoft Dynamics 365 Human Resources data application programming interface (API).</span></span>

## <a name="overview"></a><span data-ttu-id="f8762-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="f8762-105">Overview</span></span>

<span data-ttu-id="f8762-106">Interfejs API danych dla modułu Human Resources jest implementacją protokołu OData.</span><span class="sxs-lookup"><span data-stu-id="f8762-106">The data API for Human Resources is an OData implementation.</span></span> <span data-ttu-id="f8762-107">Aby uzyskać więcej informacji, zobacz temat [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span><span class="sxs-lookup"><span data-stu-id="f8762-107">For more information, see [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span></span>

<span data-ttu-id="f8762-108">Aby interfejs API obsługiwał żądania z aplikacji, aplikacja musi się najpierw uwierzytelnić jako autoryzowany obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="f8762-108">Your application must authenticate as an authorized caller before the API will service requests from your application.</span></span>

## <a name="fundamentals"></a><span data-ttu-id="f8762-109">Informacje podstawowe</span><span class="sxs-lookup"><span data-stu-id="f8762-109">Fundamentals</span></span>

<span data-ttu-id="f8762-110">Aby wywołać interfejs API danych, aplikacja musi uzyskać token dostępu z platformy tożsamości Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8762-110">To call the data API, your application must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="f8762-111">Token dostępu zawiera informacje o aplikacji oraz o uprawnieniach, które aplikacja musi mieć, aby wywoływać zasoby w programie Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f8762-111">The access token contains information about your application and the permission that it has to call resources in Human Resources.</span></span>

### <a name="access-token"></a><span data-ttu-id="f8762-112">Token dostępu</span><span class="sxs-lookup"><span data-stu-id="f8762-112">Access token</span></span>

<span data-ttu-id="f8762-113">Tokeny dostępu wydawane przez platformę tożsamości Microsoft to tokeny sieci Web w notacji JSON (JavaScript Object Notation) (tokeny JWT) z kodowaniem Base64.</span><span class="sxs-lookup"><span data-stu-id="f8762-113">Access tokens issued by the Microsoft identity platform are base64–encoded JavaScript Object Notation (JSON) Web Tokens (JWTs).</span></span> <span data-ttu-id="f8762-114">Zawierają informacje (oświadczenia), których interfejs API danych (i innych interfejsy API sieci Web zabezpieczone przez platformę tożsamości Microsoft) używają do weryfikacji obiektu wywołującego i upewnienia się, że obiekt wywołujący ma odpowiednie uprawnienia do wykonywania operacji, której żąda.</span><span class="sxs-lookup"><span data-stu-id="f8762-114">They contain information (claims) that the data API (and other web APIs that are secured by the Microsoft identity platform) use to validate the caller and make sure that the caller has the correct permissions to perform the operation they're requesting.</span></span> <span data-ttu-id="f8762-115">Podczas wywołań tokeny dostępu można traktować jako nieprzezroczyste.</span><span class="sxs-lookup"><span data-stu-id="f8762-115">During calls, you can treat access tokens as opaque.</span></span> <span data-ttu-id="f8762-116">Tokeny dostępu należy zawsze wysyłać przez bezpieczny kanał, taki jak Transport Layer Security (TLS) lub Hypertext Transfer Protocol Secure (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="f8762-116">You should always transmit access tokens over a secure channel, such as Transport Layer Security (TLS) and Hypertext Transfer Protocol Secure (HTTPS).</span></span>

<span data-ttu-id="f8762-117">Poniżej przedstawiono przykładowy token dostępu wystawiany przez platformę tożsamości Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8762-117">Here is an example of an access token that is issued by the Microsoft identity platform.</span></span>

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

<span data-ttu-id="f8762-118">Aby wywołać interfejs API danych, należy dołączyć token dostępu jako token okaziciela do nagłówka autoryzacji w żądaniu HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8762-118">To call the data API, you attach the access token as a bearer token to the authorization header in your HTTP request.</span></span> <span data-ttu-id="f8762-119">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="f8762-119">Here is an example.</span></span>

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a><span data-ttu-id="f8762-120">Rejestrowanie nowej aplikacji w portalu Azure</span><span class="sxs-lookup"><span data-stu-id="f8762-120">Register a new application by using the Azure portal</span></span>

1. <span data-ttu-id="f8762-121">Zaloguj się w [portalu Microsoft Azure](https://portal.azure.com) przy użyciu konta uczelnianego lub służbowego albo osobistego konta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8762-121">Sign in to the [Microsoft Azure portal](https://portal.azure.com) with a work or school account, or a personal Microsoft account.</span></span>

2. <span data-ttu-id="f8762-122">Jeśli konto oferuje dostęp do więcej niż jednej dzierżawy, wybierz swoje konto w prawym górnym rogu, a następnie ustaw sesję portalu na żądaną dzierżawę usługi Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f8762-122">If your account gives you access to more than one tenant, select your account in the upper-right corner, and set your portal session to the Azure Active Directory (Azure AD) tenant that you want.</span></span>

3. <span data-ttu-id="f8762-123">W lewym okienku wybierz usługę **Azure Active Directory**, a następnie wybierz kolejno opcje **Rejestracje aplikacji \> Nowa rejestracja**.</span><span class="sxs-lookup"><span data-stu-id="f8762-123">In the left pane, select the **Azure Active Directory** service, and then select **App registrations \> New registration**.</span></span>

4. <span data-ttu-id="f8762-124">Gdy pojawi się strona **Rejestrowanie aplikacji**, wprowadź informacje rejestracyjne aplikacji:</span><span class="sxs-lookup"><span data-stu-id="f8762-124">When the **Register an application** page appears, enter your application's registration information:</span></span>

    - <span data-ttu-id="f8762-125">**Nazwa**: wprowadź opisową nazwę aplikacji, która będzie wyświetlana użytkownikom aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f8762-125">**Name**: Enter a meaningful application name that will be shown to users of the app.</span></span>
    - <span data-ttu-id="f8762-126">**Obsługiwane typy kont**: wybierz typy kont, które aplikacja ma obsługiwać.</span><span class="sxs-lookup"><span data-stu-id="f8762-126">**Supported account types**: Select the types of accounts that your app should support.</span></span>

        | <span data-ttu-id="f8762-127">Obsługiwane typy kont</span><span class="sxs-lookup"><span data-stu-id="f8762-127">Supported account types</span></span> | <span data-ttu-id="f8762-128">Opis</span><span class="sxs-lookup"><span data-stu-id="f8762-128">Description</span></span> |
        |-------------------------|-------------|
        | <span data-ttu-id="f8762-129">Tylko konta w tym katalogu organizacyjnym</span><span class="sxs-lookup"><span data-stu-id="f8762-129">Accounts in this organizational directory only</span></span> | <span data-ttu-id="f8762-130">Wybierz tę opcję, jeśli tworzysz aplikację biznesową.</span><span class="sxs-lookup"><span data-stu-id="f8762-130">Select this option if you're building a line-of-business app.</span></span> <span data-ttu-id="f8762-131">Ta opcja jest dostępna tylko wtedy, gdy rejestrujesz aplikację w katalogu.</span><span class="sxs-lookup"><span data-stu-id="f8762-131">This option isn't available unless you're registering the app in a directory.</span></span><p><span data-ttu-id="f8762-132">Ta opcja jest mapowana na ustawienie **Jedna dzierżawa tylko w usłudze Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="f8762-132">This option is mapped to **Azure AD only single-tenant**.</span></span></p><p><span data-ttu-id="f8762-133">Ta opcja jest domyślna, chyba że rejestrujesz aplikację poza katalogiem.</span><span class="sxs-lookup"><span data-stu-id="f8762-133">This option is the default option unless you're registering the app outside a directory.</span></span> <span data-ttu-id="f8762-134">W takim przypadku opcją domyślną jest **Wiele dzierżaw w usłudze Azure AD i osobiste konta Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f8762-134">In that case, the default option is **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p> |
        | <span data-ttu-id="f8762-135">Konta w dowolnym katalogu organizacyjnym</span><span class="sxs-lookup"><span data-stu-id="f8762-135">Accounts in any organizational directory</span></span> | <span data-ttu-id="f8762-136">Tę opcję należy zaznaczyć, jeśli aplikacja jest kierowana do wszystkich odbiorców biznesowych i edukacyjnych.</span><span class="sxs-lookup"><span data-stu-id="f8762-136">Select this option to target all business and educational customers.</span></span><p><span data-ttu-id="f8762-137">Ta opcja jest mapowana na jednostkę **Wiele dzierżaw tylko w usłudze Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="f8762-137">This option is mapped to **Azure AD only multi-tenant**.</span></span></p><p><span data-ttu-id="f8762-138">Jeśli aplikacja została zarejestrowana ustawieniem **Jedna dzierżawa tylko w usłudze Azure AD**, można w bloku **Uwierzytelnianie** zaktualizować ją do poziomu **Wiele dzierżaw tylko w usłudze Azure AD**, a następnie z powrotem do poziomu **Jedna dzierżawa tylko w usłudze Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="f8762-138">If you registered the app as **Azure AD only single-tenant**, you can use the **Authentication** blade to update it to **Azure AD only multi-tenant** and then back to **Azure AD only single-tenant**.</span></span></p> |
        | <span data-ttu-id="f8762-139">Konta w dowolnym katalogu organizacyjnym i osobiste konta Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8762-139">Accounts in any organizational directory and personal Microsoft accounts</span></span> | <span data-ttu-id="f8762-140">Wybierz tę opcję, aby kierować aplikację do najszerszego grona odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f8762-140">Select this option to target the widest set of customers.</span></span><p><span data-ttu-id="f8762-141">Ta opcja jest mapowana na ustawienie **Wiele dzierżaw w usłudze Azure AD i osobiste konta Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f8762-141">This option is mapped to **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p><p><span data-ttu-id="f8762-142">Jeśli aplikacja została zarejestrowana z ustawieniem **Wiele dzierżaw w usłudze Azure AD i osobiste konta Microsoft**, nie można zmienić tego ustawienia w interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f8762-142">If you registered the app as **Azure AD multi-tenant and personal Microsoft accounts**, you can't change this setting in the user interface (UI).</span></span> <span data-ttu-id="f8762-143">Zamiast tego do zmiany obsługiwanych typów kont należy użyć edytora manifestów aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f8762-143">Instead, you must use the application manifest editor to change the supported account types.</span></span></p> |

    - <span data-ttu-id="f8762-144">**Identyfikator URI przekierowania (opcjonalny)** — umożliwia wybór typu tworzonej aplikacji: **Sieć Web** lub **Klient publiczny (przenośny i klasyczny)**.</span><span class="sxs-lookup"><span data-stu-id="f8762-144">**Redirect URI (optional)** – Select the type of app that you're building: **Web** or **Public client (mobile & desktop)**.</span></span> <span data-ttu-id="f8762-145">Następnie wprowadź identyfikator URI przekierowania (lub adres URL odpowiedzi) dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f8762-145">Then enter the redirect URI (or reply URL) for the app.</span></span>

        - <span data-ttu-id="f8762-146">Dla aplikacji sieci Web podaj podstawowy adres URL aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f8762-146">For web apps, provide the base URL of the app.</span></span> <span data-ttu-id="f8762-147">Na przykład `http://localhost:31544` może być adresem URL aplikacji internetowej działającej na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="f8762-147">For example, `http://localhost:31544` might be the URL for a web app that runs on your local machine.</span></span> <span data-ttu-id="f8762-148">Następnie użytkownicy za pomocą tego adresu URL będą się logować do aplikacji klienckiej sieci Web.</span><span class="sxs-lookup"><span data-stu-id="f8762-148">Users then use this URL to sign in to a web client app.</span></span>
        - <span data-ttu-id="f8762-149">W przypadku aplikacji klienta publicznego podaj identyfikator URI używany przez usługę Azure AD do zwracania odpowiedzi na tokeny.</span><span class="sxs-lookup"><span data-stu-id="f8762-149">For public client apps, provide the URI that Azure AD uses to return token responses.</span></span> <span data-ttu-id="f8762-150">Wprowadź wartość charakterystyczną dla Twojej aplikacji, np. `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="f8762-150">Enter a value that is specific to your app, such as `myapp://auth`.</span></span>

        <span data-ttu-id="f8762-151">Aby zapoznać się z konkretnymi przykładami aplikacji sieci Web lub aplikacji natywnych, zobacz przewodniki szybkiego startu na [platformie tożsamości Microsoft (dawniej Azure Active Directory dla deweloperów)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="f8762-151">To see specific examples for web apps or native apps, see the quickstarts in [Microsoft identity platform (formerly Azure Active Directory for developers)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span></span>

5. <span data-ttu-id="f8762-152">W obszarze **Uprawnienia do interfejsu API** wybierz opcję **Dodaj uprawnienie**.</span><span class="sxs-lookup"><span data-stu-id="f8762-152">Under **API permissions**, select **Add a permission**.</span></span> <span data-ttu-id="f8762-153">Następnie na karcie **Interfejsy API używane w mojej organizacji** poszukaj pozycji **Dynamics 365 Human Resources** i dodaj do aplikacji uprawnienie **user\_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="f8762-153">Then, on the **APIs my organization uses** tab, search for **Dynamics 365 Human Resources**, and add the **user\_impersonation** permission to your app.</span></span> <span data-ttu-id="f8762-154">Identyfikator aplikacji dla modułu Human Resources to f9be0c49-aa22-4ec6-911a-c5da515226ff.</span><span class="sxs-lookup"><span data-stu-id="f8762-154">The Application ID for Human Resources is f9be0c49-aa22-4ec6-911a-c5da515226ff.</span></span> <span data-ttu-id="f8762-155">Użyj tego identyfikatora, aby upewnić się, że wybrano prawidłową aplikację.</span><span class="sxs-lookup"><span data-stu-id="f8762-155">Use this ID to ensure you have chosen the correct application.</span></span>

6. <span data-ttu-id="f8762-156">Wybierz opcję **Zarejestruj**.</span><span class="sxs-lookup"><span data-stu-id="f8762-156">Select **Register**.</span></span>

   <span data-ttu-id="f8762-157">[![Rejestrowanie nowej aplikacji w portalu Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f8762-157">[![Registering a new app in the Azure portal](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span></span>

<span data-ttu-id="f8762-158">Usługa Azure AD przypisze aplikacji unikatowy identyfikator aplikacji (identyfikator klienta) i przełączy do strony **Omówienie** dla tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f8762-158">Azure AD assigns a unique application ID (client ID) to your app, and takes you to the **Overview** page for your app.</span></span> <span data-ttu-id="f8762-159">Aby dodać więcej funkcji do aplikacji, można wybrać inne opcje konfiguracji, takie jak opcje znakowania marką oraz certyfikaty i klucze tajne.</span><span class="sxs-lookup"><span data-stu-id="f8762-159">To add more capabilities to your app, you can select other configuration options, such as options for branding and for certificates and secrets.</span></span>

## <a name="retrieving-an-access-token"></a><span data-ttu-id="f8762-160">Pobieranie tokenu dostępu</span><span class="sxs-lookup"><span data-stu-id="f8762-160">Retrieving an access token</span></span>

<span data-ttu-id="f8762-161">Szczegóły sposobu pobierania tokenu dostępu służącego do wywoływania interfejsu API danych modułu Human Resources zależy od technologii używanej do utworzenia aplikacji klienckiej.</span><span class="sxs-lookup"><span data-stu-id="f8762-161">The specifics of how you retrieve an access token for calling the Human Resources data API will depend on what technologies you're using to develop your client application.</span></span> <span data-ttu-id="f8762-162">Może to być na przykład [testowanie za pomocą narzędzia innej firmy](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (na przykład Postman), pisanie aplikacji konsoli lub usługi sieci Web w języku C# albo tworzenie aplikacji klienckiej w języku JavaScript/TypeScript.</span><span class="sxs-lookup"><span data-stu-id="f8762-162">For example, you might be [testing with a third party utility](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (such as Postman), developing a C# console application or web service, or building a javascript/TypeScript client.</span></span>

<span data-ttu-id="f8762-163">Przykład aplikacji klienckiej napisanej w języku C#:</span><span class="sxs-lookup"><span data-stu-id="f8762-163">Example C# client application:</span></span>
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

<span data-ttu-id="f8762-164">Po pobraniu tokenu dostępu przekażesz go w nagłówku autoryzacji jako token okaziciela w każdym żądaniu wysyłanym do interfejsu API danych, jak opisano powyżej.</span><span class="sxs-lookup"><span data-stu-id="f8762-164">Once you've retrieved an access token, you'll pass the token in the Authorization header as a bearer token with each request you send to the data API, as described above.</span></span>
