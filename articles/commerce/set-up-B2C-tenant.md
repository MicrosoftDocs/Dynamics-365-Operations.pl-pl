---
title: Konfigurowanie dzierżawy B2C w usłudze Commerce
description: W tym artykule opisano sposób konfigurowania dzierżawcy Azure Active Directory (Azure AD) dzierżawców biznesowych (B2C) dla uwierzytelniania witryny użytkownika w programie Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 3421dd3d67198a99ac236a56cbb4f300cb591a03
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785150"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Konfigurowanie dzierżawy B2C w usłudze Commerce

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób konfigurowania dzierżawcy Azure Active Directory (Azure AD) dzierżawców biznesowych (B2C) dla uwierzytelniania witryny użytkownika w programie Dynamics 365 Commerce.

Dynamics 365 Commerce używa Azure AD B2C do obsługi przenoszonych poświadczeń i przepływów uwierzytelniania użytkowników. Użytkownik może zarejestrować się, zalogować się i zresetować swoje hasło za pośrednictwem tych przepływów. Azure AD B2C przechowuje poufne informacje o uwierzytelnianiu użytkownika, takie jak nazwa użytkownika i hasło. Rekord użytkownika w dzierżawie B2C będzie przechowywał zarówno rekord konta lokalnego B2C, jak i rekord dostawcy tożsamości socjalnej B2C. Te rekordy B2C zostaną połączone z rekordem odbiorcy w środowisku Commerce.

> [!WARNING] 
> Azure AD B2C wycofa stare (starsze) przepływy użytkowników do 1 sierpnia 2021. Dlatego należy zaplanować migrowanie przepływów użytkownika do nowej zalecanej wersji. Nowa wersja zapewnia parzystość funkcji i nowe funkcje. Biblioteka modułów dla wersji Commerce 10.0.15 lub wyższa powinna być używana z zalecanymi przepływami użytkowników B2C. Aby uzyskać więcej informacji, zobacz sekcję [Przepływy użytkowników w Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > Środowiska oceniania handlu są wstępnie załadowane do dzierżawy Azure AD B2C w celach demonstracyjnych. Ładowanie własnej dzierżawy Azure AD B2C przy użyciu poniższych kroków nie jest wymagane w środowiskach oceniania.

> [!TIP]
> Dodatkowo można chronić użytkowników witryny i zwiększyć bezpieczeństwo dzierżawy Azure AD B2C przy użyciu funkcji ochrony tożsamości i dostępu warunkowego Azure AD. Więcej informacji na temat możliwości dostępnych w przypadku dzierżawy Azure AD B2C Premium P1 i Premium P2 zawiera temat [Ochrona tożsamości i dostęp warunkowy Azure AD B2C](/azure/active-directory-b2c/conditional-access-identity-protection-overview).

## <a name="dynamics-environment-prerequisites"></a>Wymagania wstępne środowiska systemu Dynamics

Przed rozpoczęciem upewnij się, że środowisko Dynamics 365 Commerce i kanał handlu elektronicznego zostały odpowiednio skonfigurowane, aby spełniały następujące wymagania wstępne.

- Ustaw wartość **AllowAnonymousAccess** operacji punktu sprzedaży na „1” w centrali Commerce:
    1. Przejdź do okna **Operacje punktu sprzedaży**.
    1. Kliknij prawym przyciskiem myszy w siatce operacji, a następnie kliknij polecenie **Personalizuj**.
    1. Wybierz **Dodaj pole**.
    1. Z listy dostępnych kolumn wybierz kolumnę **AllowAnonymousAccess**, aby ją dodać.
    1. Wybierz **Aktualizuj**.
    1. Dla operacji **612** „Dodaj odbiorcę” zmień wartość **AllowAnonymousAccess** na „1”.
    1. Uruchom zadanie **1090 (Rejestry)**.
- Ustaw atrybut **Ręcznie** konta odbiorcy sekwencji numerów na wartość **Nie** w centrali Commerce:
    1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry modułu rozrachunków z odbiorcami**.
    1. Wybierz **Sekwencje numerów**.
    1. W wierszu **Konta odbiorcy** kliknij dwukrotnie wartość **Kod sekwencji numerów**.
    1. Na skróconej karcie **Ogólne** sekwencji numerów zmień wartość **Ręcznie** na **Nie**.

Po wdrożeniu środowiska Dynamics 365 Commerce zalecane jest również [zainicjowanie danych początkowych](enable-configure-retail-functionality.md) w środowisku.

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces konfigurowania dzierżawy B2C w portalu Commerce, [Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure](create-link-aad-b2c-tenant.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure](create-link-aad-b2c-tenant.md)

[Tworzenie aplikacji B2C](create-b2c-app.md)

[Tworzenie zasad przepływów użytkownika](create-user-flow-policies.md)

[Dodaj dostawców tożsamości społecznościowych (opcjonalnie)](add-social-identity-providers.md)

[Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD](update-hq-aad-b2c-info.md)

[Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce](config-b2c-tenant-site-builder.md)

[Informacje dodatkowe o B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
