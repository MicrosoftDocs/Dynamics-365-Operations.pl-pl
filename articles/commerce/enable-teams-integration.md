---
title: Włączanie integracji Dynamics 365 Commerce i Microsoft Teams
description: W tym temacie opisano sposób włączania integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dfada577ab97fdb9912c22d2399529f934b25d54
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695741"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Włączanie integracji Dynamics 365 Commerce i Microsoft Teams

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób włączania integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.

Aby wyposażyć Teams w informacje z Dynamics 365 Commerce i zsynchronizować funkcje zarządzania zadaniami między Teams i aplikacją punktu sprzedaży (POS), musisz włączyć funkcje integracji w centrali Commerce.

> [!NOTE]
> Włączając integrację Teams, wyrażasz zgodę na udostępnianie swoich danych Teams. Dane, które są udostępniane Teams, mogą znajdować się w innym kraju niż Twoje dane Commerce i mogą podlegać innym standardom zgodności. Aby uzyskać więcej informacji, zobacz temat [Microsoft Trust Center](https://www.microsoft.com/trust-center). Aby uzyskać więcej informacji o zasadach zachowania poufności informacji firmy Microsoft, zobacz [Zasady zachowania poufności informacji firmy Microsoft](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Włączanie integracji Teams

Zanim będzie można włączyć integrację Microsoft Teams z Commerce, musisz zarejestrować aplikację Teams u dzierżawcy w Azure Portal.

Aby zarejestrować aplikację Teams u dzierżawcy w witrynie Azure Portal, wykonaj następujące kroki.

1. Wykonaj kroki w narzędziu [Quickstart: Zarejestruj aplikację na platformie tożsamości firmy Microsoft](/azure/active-directory/develop/quickstart-register-app), aby zarejestrować aplikację Teams w Twojej dzierżawie w portalu Azure.
1. Na karcie **Rejestracja aplikacji** wybierz aplikację utworzoną w poprzednim kroku. Następnie na karcie **Uwierzytelnianie** wybierz pozycję **Dodaj platformę**.
1. W oknie dialogowym kliknij **sieć Web**. Następnie w polu **Przekieruj adresy URL** wprowadź adres URL w formacie **\<HQUrl\>/oauth**. Zamień **\<HQUrl\>** na adres URL w centrali commerce (na przykład `https://hxennugbjtweufmdeo385f47fadb6aa9a0aos.cloudax.int.dynamics.com/oauth`).
1. Na stronie **Przegląd** zarejestrowanej aplikacji skopiuj wartość **Identyfikator aplikacji (klient)**. Będziesz musiał podać tę wartość, aby umożliwić integrację Teams w centrali Commerce w następnej sekcji.
1. Postępuj zgodnie z instrukcjami w dodaj [klucz tajny klienta](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret), aby dodać klucz tajny klienta. Następnie skopiuj wartość **Tajny klucz** dla klienta. Będziesz musiał podać tę wartość, aby umożliwić integrację Teams w centrali Commerce w następnej sekcji.
1. Wybierz **Uprawnienia do interfejsu API** i wybierz opcję **Dodaj uprawnienie**.
1. W oknie dialogowym **Poproś o uprawnienia API** wybierz **Microsoft Graph**, wybierz **Uprawnienia delegowane**, rozwiń **Grupa**, wybierz **Group.ReadWrite.All**, a następnie wybierz **Dodaj uprawnienia**.
1. W oknie **Poproś o uprawnienia API** wybierz **Dodaj uprawnienie**, wybierz **Microsoft Graph**, wybierz **Uprawnienia aplikacji**, rozwiń **Grupa**, wybierz **Group.ReadWrite.All**, a następnie wybierz **Dodaj uprawnienia**.
1. W oknie dialogowym **Żądanie uprawnień interfejsu API** wybierz pozycję **Dodaj uprawnienie**. Na karcie **Interfejsy API mojej organizacji** wyszukaj usługę **Microsoft Teams sieci sprzedaży** i wybierz ją.
1. Wybierz **uprawnienia delegowane**, rozwiń pozycję **TaskPublishing**, wybierz **pozycję TaskPubpubing.ReadWrite.All**, a następnie wybierz pozycję **Dodaj uprawnienia**. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie aplikacji klienckiej w celu uzyskiwania dostępu do interfejsu API sieci Web](/azure/active-directory/develop/quickstart-configure-app-access-web-apis).

Aby włączyć integrację Teams w centrali Commerce, wykonaj następujące kroki.

1. Przejdź do opcji **Retail i Commerce \> Konfiguracja kanału \> Grupy realizacji Microsoft Teams**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Ustaw opcję **Włącz integracje Microsoft Teams** na **Tak**.
1. W polach **Identyfikator aplikacji** wprowadź wartość **Identyfikator aplikacji (klient)** uzyskaną podczas rejestracji aplikacji Teams w Azure Portal.
1. W polach **Klucz aplikacji** wprowadź wartość **Tajna wartość** uzyskaną podczas dodawania klucza tajnego klienta w portalu Azure.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższa ilustracja przedstawia przykład konfiguracji integracji Teams w centrali Commerce.

![Konfiguracja integracji zespołów w Commerce Headquarters.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a>Wyłączanie integracji Teams

Aby wyłączyć integrację Microsoft Teams w centrali Commerce, wykonaj następujące kroki.

1. Przejdź do opcji **Retail i Commerce \> Konfiguracja kanału \> Grupy realizacji Microsoft Teams**.
1. W okienku akcji wybierz pozycję **Edytuj**.
3. Ustaw opcję **Włącz integracje Microsoft Teams** na **Nie**.
4. Wyczyść wartości pól **Identyfikator aplikacji** i **Klucz aplikacji**.
1. Na okienku akcji wybierz opcję **Zapisz**.

> [!NOTE]
> Po wyłączeniu integracji Teams z aplikacją Commerce terminale POS nie będą już wyświetlać zadań opublikowanych z aplikacji Teams.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie integracji Dynamics 365 Commerce i Microsoft Teams](commerce-teams-integration.md)

[Obsługa Microsoft Teams z Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Zarządzanie rolami użytkowników w usłudze Microsoft Teams](manage-user-roles-teams.md)

[Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams](map-stores-existing-teams.md)

[Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ](teams-integration-faq.md)
