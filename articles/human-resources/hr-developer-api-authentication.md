---
title: Uwierzytelnianie
description: W tym artykule zamieszczono przegląd informacji na temat sposobów uwierzytelniania w interfejsie programowania aplikacji (API) modułu Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4e73438170294863b7aa092cf1fc027787f57c70
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054387"
---
# <a name="authentication"></a>Uwierzytelnianie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule zamieszczono przegląd informacji na temat sposobów uwierzytelniania w interfejsie programowania aplikacji (API) modułu Microsoft Dynamics 365 Human Resources.

## <a name="overview"></a>Omówienie

Interfejs API danych dla modułu Human Resources jest implementacją protokołu OData. Aby uzyskać więcej informacji, zobacz temat [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).

Aby interfejs API obsługiwał żądania z aplikacji, aplikacja musi się najpierw uwierzytelnić jako autoryzowany obiekt wywołujący.

## <a name="fundamentals"></a>Informacje podstawowe

Aby wywołać interfejs API danych, aplikacja musi uzyskać token dostępu z platformy tożsamości Microsoft. Token dostępu zawiera informacje o aplikacji oraz o uprawnieniach, które aplikacja musi mieć, aby wywoływać zasoby w programie Human Resources.

### <a name="access-token"></a>Token dostępu

Tokeny dostępu wydawane przez platformę tożsamości Microsoft to tokeny sieci Web w notacji JSON (JavaScript Object Notation) (tokeny JWT) z kodowaniem Base64. Zawierają informacje (oświadczenia), których interfejs API danych (i innych interfejsy API sieci Web zabezpieczone przez platformę tożsamości Microsoft) używają do weryfikacji obiektu wywołującego i upewnienia się, że obiekt wywołujący ma odpowiednie uprawnienia do wykonywania operacji, której żąda. Podczas wywołań tokeny dostępu można traktować jako nieprzezroczyste. Tokeny dostępu należy zawsze wysyłać przez bezpieczny kanał, taki jak Transport Layer Security (TLS) lub Hypertext Transfer Protocol Secure (HTTPS).

Poniżej przedstawiono przykładowy token dostępu wystawiany przez platformę tożsamości Microsoft.

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

Aby wywołać interfejs API danych, należy dołączyć token dostępu jako token okaziciela do nagłówka autoryzacji w żądaniu HTTP. Oto przykład.

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a>Rejestrowanie nowej aplikacji w portalu Azure

1. Zaloguj się w [portalu Microsoft Azure](https://portal.azure.com) przy użyciu konta uczelnianego lub służbowego albo osobistego konta Microsoft.

2. Jeśli konto oferuje dostęp do więcej niż jednej dzierżawy, wybierz swoje konto w prawym górnym rogu, a następnie ustaw sesję portalu na żądaną dzierżawę usługi Azure Active Directory (Azure AD).

3. W lewym okienku wybierz usługę **Azure Active Directory**, a następnie wybierz kolejno opcje **Rejestracje aplikacji \> Nowa rejestracja**.

4. Gdy pojawi się strona **Rejestrowanie aplikacji**, wprowadź informacje rejestracyjne aplikacji:

    - **Nazwa**: wprowadź opisową nazwę aplikacji, która będzie wyświetlana użytkownikom aplikacji.
    - **Obsługiwane typy kont**: wybierz typy kont, które aplikacja ma obsługiwać.

        | Obsługiwane typy kont | Opis |
        |-------------------------|-------------|
        | Tylko konta w tym katalogu organizacyjnym | Wybierz tę opcję, jeśli tworzysz aplikację biznesową. Ta opcja jest dostępna tylko wtedy, gdy rejestrujesz aplikację w katalogu.<p>Ta opcja jest mapowana na ustawienie **Jedna dzierżawa tylko w usłudze Azure AD**.</p><p>Ta opcja jest domyślna, chyba że rejestrujesz aplikację poza katalogiem. W takim przypadku opcją domyślną jest **Wiele dzierżaw w usłudze Azure AD i osobiste konta Microsoft**.</p> |
        | Konta w dowolnym katalogu organizacyjnym | Tę opcję należy zaznaczyć, jeśli aplikacja jest kierowana do wszystkich odbiorców biznesowych i edukacyjnych.<p>Ta opcja jest mapowana na jednostkę **Wiele dzierżaw tylko w usłudze Azure AD**.</p><p>Jeśli aplikacja została zarejestrowana ustawieniem **Jedna dzierżawa tylko w usłudze Azure AD**, można w bloku **Uwierzytelnianie** zaktualizować ją do poziomu **Wiele dzierżaw tylko w usłudze Azure AD**, a następnie z powrotem do poziomu **Jedna dzierżawa tylko w usłudze Azure AD**.</p> |
        | Konta w dowolnym katalogu organizacyjnym i osobiste konta Microsoft | Wybierz tę opcję, aby kierować aplikację do najszerszego grona odbiorców.<p>Ta opcja jest mapowana na ustawienie **Wiele dzierżaw w usłudze Azure AD i osobiste konta Microsoft**.</p><p>Jeśli aplikacja została zarejestrowana z ustawieniem **Wiele dzierżaw w usłudze Azure AD i osobiste konta Microsoft**, nie można zmienić tego ustawienia w interfejsie użytkownika. Zamiast tego do zmiany obsługiwanych typów kont należy użyć edytora manifestów aplikacji.</p> |

    - **Identyfikator URI przekierowania (opcjonalny)** — umożliwia wybór typu tworzonej aplikacji: **Sieć Web** lub **Klient publiczny (przenośny i klasyczny)**. Następnie wprowadź identyfikator URI przekierowania (lub adres URL odpowiedzi) dla aplikacji.

        - Dla aplikacji sieci Web podaj podstawowy adres URL aplikacji. Na przykład `http://localhost:31544` może być adresem URL aplikacji internetowej działającej na komputerze lokalnym. Następnie użytkownicy za pomocą tego adresu URL będą się logować do aplikacji klienckiej sieci Web.
        - W przypadku aplikacji klienta publicznego podaj identyfikator URI używany przez usługę Azure AD do zwracania odpowiedzi na tokeny. Wprowadź wartość charakterystyczną dla Twojej aplikacji, np. `myapp://auth`.

        Aby zapoznać się z konkretnymi przykładami aplikacji sieci Web lub aplikacji natywnych, zobacz przewodniki szybkiego startu na [platformie tożsamości Microsoft (dawniej Azure Active Directory dla deweloperów)](/azure/active-directory/develop/#quickstarts).

5. W obszarze **Uprawnienia do interfejsu API** wybierz opcję **Dodaj uprawnienie**. Następnie na karcie **Interfejsy API używane w mojej organizacji** poszukaj pozycji **Dynamics 365 Human Resources** i dodaj do aplikacji uprawnienie **user\_impersonation**. Identyfikator aplikacji dla modułu Human Resources to f9be0c49-aa22-4ec6-911a-c5da515226ff. Użyj tego identyfikatora, aby upewnić się, że wybrano prawidłową aplikację.

6. Wybierz opcję **Zarejestruj**.

   [![Rejestrowanie nowej aplikacji w portalu Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)

Usługa Azure AD przypisze aplikacji unikatowy identyfikator aplikacji (identyfikator klienta) i przełączy do strony **Omówienie** dla tej aplikacji. Aby dodać więcej funkcji do aplikacji, można wybrać inne opcje konfiguracji, takie jak opcje znakowania marką oraz certyfikaty i klucze tajne.

## <a name="retrieving-an-access-token"></a>Pobieranie tokenu dostępu

Szczegóły sposobu pobierania tokenu dostępu służącego do wywoływania interfejsu API danych modułu Human Resources zależy od technologii używanej do utworzenia aplikacji klienckiej. Może to być na przykład [testowanie za pomocą narzędzia innej firmy](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (na przykład Postman), pisanie aplikacji konsoli lub usługi sieci Web w języku C# albo tworzenie aplikacji klienckiej w języku JavaScript/TypeScript.

Przykład aplikacji klienckiej napisanej w języku C#:
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

Po pobraniu tokenu dostępu przekażesz go w nagłówku autoryzacji jako token okaziciela w każdym żądaniu wysyłanym do interfejsu API danych, jak opisano powyżej.


[!INCLUDE[footer-include](../includes/footer-banner.md)]