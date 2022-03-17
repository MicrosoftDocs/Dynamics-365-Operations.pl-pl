---
title: Wykrywanie porzuconych koszyków i wysyłanie powiadomień do klientów
description: W tym temacie opisano, jak dostosować przykładową aplikację łącznika porzuconych koszyków Microsoft Dynamics 365 Commerce, aby wykrywać porzucone koszyki i wysyłać klientom powiadomienia e-mail z przypomnieniem.
author: bicyclingfool
ms.date: 02/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 82848f1ff068cea0adfc6ec1b33fc4bb035f78dc
ms.sourcegitcommit: 374bbdde90fc9a68c0799158a50409bfbe8ca64e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353365"
---
# <a name="detect-abandoned-carts-and-send-notifications-to-customers"></a>Wykrywanie porzuconych koszyków i wysyłanie powiadomień do klientów

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak dostosować przykładową aplikację łącznika porzuconych koszyków Microsoft Dynamics 365 Commerce, aby wykrywać porzucone koszyki i wysyłać klientom powiadomienia e-mail z przypomnieniem.

Możliwość odzyskania przychodu i zatrzymania odbiorców poprzez powiadomienia o porzuconych koszykach jest ważnymi możliwościami, które obsługują Dynamics 365 Commerce. Przez dostosowanie przykładowej aplikacji Commerce Porzucony łącznik koszyka sprzedawcy detaliczni mogą uzyskać dostęp do koszyków w programie Retail Server, które nie zostały zmodyfikowane w okresie czasu, który definiują sprzedawcy detaliczni. Koszyki te można następnie pobierać, rozszerzać przy użyciu danych produktów i klientów oraz przesyłać do zewnętrznego dostawcy marketingu poczty e-mail, który może generować powiadomienia pocztą e-mail i wysyłać do nich odbiorców.

Porzucony komunikat e-mail o koszyku, który otrzymuje odbiorcy, może zawierać następujące informacje:

- Imię odbiorcy.
- Nazwisko odbiorcy.
- Adres e-mail odbiorcy.
- Adres URL, który zwraca klienta do koszyka.
- Waluta transakcji.
- Lista produktów w koszyku odbiorcy. Do każdego produktu dołączone są następujące informacje:

    - Wyświetlana nazwa produktu
    - Identyfikator produktu (używany do kompletowania adresu URL strony opisu produktu)
    - Obraz produktu, którego rozmiar można automatycznie zmieniać, aby dostosować go do różnych rozmiarów okien ekranu
    - Tekst alternatywny dla obrazu produktu
    - Cena jednostkowa produktu

## <a name="abandoned-cart-connector-sample"></a>Przykład porzuconego łącznika koszyka

Model łącznika dostarczany przez firmę Microsoft za pomocą zestawu Retail Software Development Kit (SDK) umożliwia pobieranie i wysyłanie informacji o porzucanych koszykach do dostawcy marketingu poczty e-mail innej firmy. Ten łącznik obsługuje komunikację z usługą Retail Server, korzysta z klucza Azure Dla zabezpieczeń, obsługuje planowanie pobierania koszyka dla określonego okna czasu oraz pobiera dane zamówień i produktów. Zawiera również przykładową implementację integracji z dostawcą marketingu poczty e-mail innej firmy. Złącze jest zbudowane do komunikacji z gotowymi [Emarsys](https://emarsys.com). Można go jednak łatwo dostosować, aby zintegrować go z innymi rozwiązaniami, takimi jak Stała osoba kontaktowa, Mailchimp i SendGrid.

Na poniższej ilustracji pokazano składniki porzuconej aplikacji przykładowej łącznika koszyka.

![Składniki porzuconej aplikacji przykładowej łącznika koszyka](media/AbandonedCartConnector.png)

> [!IMPORTANT]
> W niektórych regionach klienci muszą być w stanie zrezygnować z otrzymywania danych o koszyku do dostawcy marketingu poczty e-mail lub żądać usunięcia swoich danych. Firma Microsoft nie dostarcza jednak tych opcji dla klientów. Z tego względu, jeśli zamierzasz świadczyć usługi w regionach, w których ich udzielasz, musisz podać wymaganą infrastrukturę i dostosowania, aby śledzić preferencje klientów i na ich podstawie zapobiegać przekazy danych klientów do platformy poczty e-mail. Należy również zdefiniować proces przeczyszczania danych odbiorcy z dostawcy marketingu poczty e-mail na żądanie odbiorcy.

## <a name="obtain-the-code-sample"></a>Uzyskaj próbkę kodu

Porzucona przykładowa aplikacja łącznika koszyka jest dołączona do zestawu Retail SDK w wersji 10.0.16. Kod można znaleźć w obszarze **\\RetailSDK\\Code\\SampleExtensions\\RetailServer\\Extensions.AbandonedCartSample**. Aby uzyskać więcej informacji o pakiecie SDK dla sklepów detalicznych i o tym, gdzie go uzyskać, zobacz [Zestaw deweloperski oprogramowania dla sklepów detalicznych (SDK)](retail-sdk/retail-sdk-overview.md).

> [!NOTE]
> Chociaż przykładowy kod został po raz pierwszy dostępny w wersjach 10.0.16, jest zgodny z wersjami 10.0.13 i nowszą kompilacjami programu Retail Server.

## <a name="prerequisites-and-dependencies"></a>Wymagania wstępne i zależności

Aby można było wdrożyć i skonfigurować porzucony przykładowy kod łącznika koszyka, muszą być spełnione następujące wymagania wstępne.

### <a name="access-to-commerce-resources"></a>Dostęp do zasobów commerce

Aby skonfigurować i wdrożyć porzuconą aplikację Łącznik koszyka, musisz mieć dostęp do następujących zasobów handlowych:

- Dostęp administratora do programu Commerce Headquarters dla swojego środowiska
- Dostęp do projektu Microsoft Dynamics Lifecycle Services (LCS) dla swojego środowiska

### <a name="azure-cosmos-db"></a>Azure Cosmos DB

Porzucony łącznik koszyka używa platformy Azure Cosmos DB do śledzenia identyfikatorów i sygnatur czasowych koszyków, które zostały wcześniej pobrane. Możesz użyć systemu Azure Cosmos DB do utrwalania tych danych lub możesz dostosować przykład kodu do integracji z inną opcją magazynu danych. Aby uzyskać więcej informacji o systemie Azure Cosmos DB, zobacz [Witamy w systemie Azure Cosmos DB](/azure/cosmos-db/introduction).

Jeśli używasz Azure Cosmos DB, następujące wymagania wstępne muszą być spełnione przed uruchomieniem próbki:

- Musisz mieć subskrypcję systemu Azure Cosmos DB. Jeśli nie masz konta, zobacz temat [Tworzenie konta bazy danych](/azure/cosmos-db/create-sql-api-dotnet#create-a-database-account).
- Musisz pobrać wartości **URI** i **GŁÓWNY KLUCZ** (lub **KLUCZ WTÓRNY**) z bloku **Klucze** konta Azure Cosmos DB w Azure Portal. Aby uzyskać więcej informacji na temat pobierania informacji o punkcie końcowym i kluczu dla konta Azure Cosmos DB, zobacz [Wyświetlanie, kopiowanie i ponowne generowanie kluczy dostępu i haseł](/azure/cosmos-db/manage-account#keys).

### <a name="azure-key-vault"></a>Azure Key Vault

Porzucona aplikacja łącznika koszyka używa Key Vault do przechowywania nazw i wpisów tajnych różnych składników, które wymagają bezpiecznego dostępu.

Aby skonfigurować magazyn kluczy, wykonaj następujące kroki.

1. Postępuj zgodnie z instrukcjami w teście [Zarządzania kluczem w usłudze Azure Stack Hub, używając portalu](/azure-stack/user/azure-stack-key-vault-manage-portal?view=azs-2002&preserve-view=true).
2. Aby uzyskać następujące informacje:

    - Nazwa użytkownika i sekret API Emarsys
    - Identyfikator aplikacji porzuconego koszyka i tajny klucz

Porzucony przykładowy kod łącznika koszyka używa poświadczeń domyślnych systemu Azure, aby uzyskać dostęp do klucza. Należy podać uprawnienia **Lista** i **Odczyt** dla tożsamości, która ma być użyciu do uzyskiwania dostępu do klucza.

Aby uzyskać więcej informacji dotyczących poświadczeń domyślnych systemu Azure, zobacz klasę [DefaultAzureCredential](/dotnet/api/azure.identity.defaultazurecredential?view=azure-dotnet&preserve-view=true).

## <a name="create-an-abandoned-cart-connector-sample-app-application-id-for-the-azure-ad-tenant"></a>Utwórz porzucony identyfikator aplikacji przykładowej aplikacji łącznika koszyka dla dzierżawcy Azure AD

Należy utworzyć identyfikator przykładowej aplikacji łącznika porzuconego koszyka dla dzierżawy usługi Azure Active Directory (AD). Aby uzyskać informacje na temat tworzenia identyfikatora aplikacji, zobacz [Korzystanie z portalu do tworzenia aplikacji usługi i jednostki usługi Azure AD, która może uzyskiwać dostęp do zasobów](/azure/active-directory/develop/howto-create-service-principal-portal).

## <a name="add-the-abandoned-cart-connector-sample-app-application-id-to-the-allow-list-for-the-retail-server-api"></a>Dodaj identyfikator aplikacji przykładowej łącznika koszyka do listy zezwalań dla interfejsu API usługi Retail Server

Następnie należy dodać identyfikator przykładowej aplikacji łącznika porzuconego koszyka do listy dozwolonych dla interfejsu API serwera sprzedaży detalicznej. Aby uzyskać informacje dotyczące sposobu dodania identyfikatora aplikacji do listy zezwalania na korzystanie z systemu Azure, zobacz [pomoc techniczną uwierzytelniania usługą w programie Retail Server](https://community.dynamics.com/ax/b/axforretail/posts/support-for-service-to-service-authentication-in-retail-server).

## <a name="configure-the-abandoned-cart-connector-sample-app"></a>Skonfiguruj przykładową aplikację łącznika porzuconego koszyka

Aby skonfigurować porzuconą przykładową aplikację łącznika koszyka, zmodyfikuj plik konfiguracyjny **appSettings.json** znajdujący się w katalogu głównym **AbandonedCartDetectionSample**. W poniższych tabelach opisano właściwości pliku konfiguracji.

### <a name="keyvaultoptions"></a>KeyVaultOptions

| Właściwość    | Opis |
| ----------- | ----------- |
| KeyVaultURI | Nazwa systemu nazw domen (DNS) klucza, który jest używasz w portalu Azure. |

### <a name="retailserverclientoptions"></a>RetailServerClientOptions

| Właściwość                                      | Opis |
| --------------------------------------------- | ----------- |
| TenantId                                      | Identyfikator dzierżawy usługi Azure AD dzierżawy platformy Azure. |
| RetailServerAudienceId                        | Identyfikator odbiorcy usługi Retail Server. Możesz pozostawić wartość domyślną. |
| AppIdKeyVaultSecretName                       | Nazwa klucza tajnego utworzonego dla identyfikatora aplikacji przykładowej aplikacji łącznika porzuconego koszyka. |
| AppSecretKeyVaultSecretName                   | Nazwa klucza tajnego, który przechowuje klucz tajny aplikacji dla identyfikatora przykładowej aplikacji łącznika porzuconego koszyka. |
| RetailServerUrl                               | Adres URL wystąpienia usługi Retail Server. Możesz znaleźć tę wartość w LCS. |
| OperatingUnitNumber                           | Numer jednostki operacyjnej (OUN). Możesz znaleźć tę wartość w Commerce headquarters. |
| IncludeAbandonedCartsModifiedSinceLastMinutes | Początek okna czasu dla porzuconych koszyków, które mają zostać pobrane. Ta wartość jest wyrażona jako liczba minut przed bieżącym czasem. Na przykład ustaw tę właściwość na **120**, aby pobrać wszystkie koszyki, które zostały zmodyfikowane między 120 minutami a końcem okna czasowego zdefiniowanego przez właściwość **ExcludeAbandonedCartsModifiedSinceLastMinutes**. |
| ExcludeAbandonedCartsModifiedSinceLastMinutes | Koniec okna czasowego dla porzuconych wózków, które chcesz odzyskać. Ta wartość jest wyrażona jako liczba minut przed bieżącym czasem. Na przykład, jeśli właściwość **IncludeAbandonedCartsModifiedSinceLastMinutes** jest ustawiona na **120**, ustaw tę właściwość na **30**, aby pobrać wszystkie koszyki, które zostały zmodyfikowane między 120 a 30 minutami temu. W praktyce ta właściwość definiuje czas, po którym koszyk ma zostać zadeklarowany jako porzucony. |
| ReturnToCartUrl                               | Adres URL koszyka w witrynie e-commerce w formacie używanym w pliku **app.config**. |

### <a name="azurecosmosoptions"></a>AzureCosmosOptions

Stan porzuconego zadania pobierania koszyka, identyfikatory koszyków i zmodyfikowane sygnatury czasowe są przechowywane w systemie Azure Cosmos DB. Domyślnie ustawienia w pliku konfiguracji wskazują lokalne wystąpienie emulatora systemu Azure Cosmos DB. Podczas wdrażania łącznika w środowisku produkcyjnym należy zaktualizować te ustawienia, aby były one punktem wystąpienia systemu Azure Cosmos DB w subskrypcji systemu Azure. Do testowania lokalnego lub w piaskownicy możesz użyć [Emulatora Cosmos Azure](/azure/cosmos-db/local-emulator).

| Właściwość    | Opis |
| ----------- | ----------- |
| EndPointUri | Ten punkt końcowy jest dostarczany przez platformę Azure lub emulator. |
| PrimaryKey  | Klucz podstawowy dostarczany przez platformę Azure lub emulator. |
| DatabaseId  | Identyfikator bazy danych. Możesz pozostawić wartość domyślną lub podać swoją własną. |
| ContainerId | Identyfikator kontenera. Możesz pozostawić wartość domyślną lub podać swoją własną. |

### <a name="emarsysclientoptions"></a>EmarsysClientOptions

> [!NOTE]
> Jeśli integrujesz się z dostawcą marketingu e-mailowego innym niż Emarsys, musisz odpowiednio rozszerzyć interfejs **IEmailProvider**, aby komunikować się z tym dostawcą.

| Właściwość                      | Opis |
| ----------------------------- | ----------- |
| Interfejs ApiUrl                        | `https://api.emarsys.net/api/v2/event/{0}/trigger` |
| ExternalEventId               | Identyfikator zewnętrznego rekordu zdarzenia, który jest tworzony w Emarsys. Możesz znaleźć wartość w obszarze **Ustawienia wyzwalacza** w utworzonej kampanii, aby wysłać powiadomienia o porzuconych wiadomościach e-mail z koszyka. |
| ApiUserNameKeyVaultSecretName | Nazwa klucza, w którym przechowywana jest nazwa użytkownika interfejsu API Emarsys. |
| ApiSecretKeyVaultSecretName   | Nazwa klucza, w którym przechowywany jest klucz tajny interfejsu API Emarsys. |
| EmarsysContactKeyId           | Identyfikator kolumny e-mail w bazie danych kontaktów Emarsys. Wartość domyślna to **3** i nie należy jej zmieniać. |

### <a name="mediaoptions"></a>MediaOptions

Jeśli w handlu handlowym są dostępne funkcje handlu elektronicznego, do pobierania obrazów produktów można używać funkcji zarządzania cyfrowym zasobem handlowym. Aby uzyskać więcej informacji o możliwościach zmiany rozmiaru obrazu w cyfrowym zarządzaniu zasobami, zobacz temat [Konfiguracja widoku portu imageSettings](../e-commerce-extensibility/image-component.md#imagesettings-viewport-configuration).

| Właściwość                             | Opis |
| ------------------------------------ | ----------- |
| ImageServerUrl                       | Główny adres URL menedżera zasobów cyfrowych Twojej witryny. Wartość można znaleźć w kluczu właściwości **Podstawowy adres URL serwera multimedialnego** w **Handel detaliczny \> Konfiguracja kanału \> Profile kanałów** w centrali handlowej. |
| ImageViewPorts                       | Węzeł kontenera dla poszczególnych konfiguracji rzutni. |
| ImageViewPorts/viewport              | Definicja rzutni. Ta właściwość umożliwia określanie zakresów szerokości dlaportu wyświetlania w pikselach. Aby zapoznać się z przykładem, który pokazuje, jak ta właściwość jest używana, zobacz plik konfiguracyjny **appSettings.json**. |
| ImageViewPorts/imageWidth            | Szerokość obrazuportu w pikselach. |
| imageViewPorts/imageHeight           | Wysokość obrazu widocznego obszaru w pikselach. |
| imageViewPorts/useForDefaultImageTag | Wartość **prawda**/**fałsz** wskazująca, czy wymiary obrazu zdefiniowane przez widoczny obszar mają być używane, jeśli tag HTML `<picture>` nie jest obsługiwany przez przeglądarkę internetową lub klienta poczty e-mail. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
