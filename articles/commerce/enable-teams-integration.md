---
title: Włączanie integracji Dynamics 365 Commerce i Microsoft Teams
description: W tym temacie opisano sposób włączania integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c0dbf7a3c7fa3532e35cac240c1abb8adbdbe489
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842724"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Włączanie integracji Dynamics 365 Commerce i Microsoft Teams

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano sposób włączania integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.

Aby wyposażyć Teams w informacje z Dynamics 365 Commerce i zsynchronizować funkcje zarządzania zadaniami między Teams i aplikacją punktu sprzedaży (POS), musisz włączyć funkcje integracji w centrali Commerce.

> [!NOTE]
> Włączając integrację Teams, wyrażasz zgodę na udostępnianie swoich danych Teams. Dane, które są udostępniane Teams, mogą znajdować się w innym kraju niż Twoje dane Commerce i mogą podlegać innym standardom zgodności. Aby uzyskać więcej informacji, zobacz temat [Microsoft Trust Center](https://www.microsoft.com/trust-center). Aby uzyskać więcej informacji o zasadach zachowania poufności informacji firmy Microsoft, zobacz [Zasady zachowania poufności informacji firmy Microsoft](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Włączanie integracji Teams

Zanim będzie można włączyć integrację Microsoft Teams z Commerce, musisz zarejestrować aplikację Teams u dzierżawcy w Azure Portal.

Aby zarejestrować aplikację Teams u dzierżawcy w witrynie Azure Portal, wykonaj następujące kroki.

1. Wykonaj kroki w narzędziu [Quickstart: Zarejestruj aplikację na platformie tożsamości firmy Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app), aby zarejestrować aplikację Teams w Twojej dzierżawie w portalu Azure.
1. Skopiuj wartość **Identyfikator aplikacji (klienta)** ze strony **Przegląd** zarejestrowanej aplikacji. Użyjesz tej wartości, aby włączyć integrację Teams w centrali Commerce.
1. Umożliwia skopiowanie wartości certyfikatu wprowadzonej podczas [dodawana do certyfikatu](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) w kroku 1. Certyfikat jest również znany jako klucz publiczny lub klucz aplikacji. Użyjesz tej wartości, aby włączyć integrację Teams w centrali Commerce.

Aby włączyć integrację Teams w centrali Commerce, wykonaj następujące kroki.

1. Przejdź do opcji **Retail i Commerce \> Konfiguracja kanału \> Grupy realizacji Microsoft Teams**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Ustaw opcję **Włącz integracje Microsoft Teams** na **Tak**.
1. W polach **Identyfikator aplikacji** i **Klucz aplikacji** wprowadź wartości uzyskane podczas rejestrowania aplikacji Teams w portalu Azure.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższa ilustracja przedstawia przykład konfiguracji integracji Teams w centrali Commerce.

![Konfiguracja integracji zespołów w Commerce Headquarters](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

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
