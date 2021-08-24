---
title: Omówienie integracji Dynamics 365 Commerce i Microsoft Teams
description: Ten temat zawiera omówienie integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 38235c237f4311a9616f88b56f1503935b25b251d1c2d35d4392418e8c1a357b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714023"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a>Omówienie integracji Dynamics 365 Commerce i Microsoft Teams

[!include [banner](includes/banner.md)]

Ten temat zawiera omówienie integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.

Dynamics 365 Commerce integruje się z Teams, aby pomagać klientom i ich pracownikom w zwiększaniu produktywności dzięki zsynchronizowaniu zarządzania zadaniami między tymi dwiema aplikacjami. Bezproblemowa zarządzanie zadaniami, dzięki integracji z usługami Commerce and Teams, menedżerowie sklepu i pracownicy mogą tworzyć listy zadań, przypisywać zadania do wielu sklepów i śledzić stan zadań w różnych sklepach z każdej aplikacji.

Integracja z usługami Commerce and Teams jest dostępna od wersji 10.0.18 Commerce.

## <a name="key-features"></a>Najważniejsze funkcje

Poniżej przedstawiono niektóre najważniejsze funkcje dostępne dzięki integracji Commerce i Microsoft Teams:

- Obsługuj Teams, korzystając z dobrze zdefiniowanych informacji z aplikacji Commerce, takich jak struktura organizacyjna i informacje o sklepach, pracownikach, uprawnieniach i kontekście biznesowym.
- Z łatwością synchronizuj bieżące zmiany (na przykład dodawanie nowych sklepów lub zatrudnianie nowych pracowników) między aplikacjami Commerce i Teams, ale zachowaj Commerce jako główne źródło danych o strukturze organizacyjnej.
- Zintegruj zarządzanie zadaniami między aplikacjami Commerce i Teams, aby ułatwić pracownikom sklepów, kierownikom sklepów, kierownikom regionalnym i kierownikom ds. Komunikacji zarządzanie zadaniami z dowolnej aplikacji.

## <a name="prerequisites-for-using-integration-features"></a>Wymagania wstępne dotyczące używania funkcji integracji

Przed rozpoczęciem korzystania z funkcji integracji Microsoft Teams muszą zostać spełnione następujące wymagania wstępne:

- Licencja na oprogramowanie Microsoft 365 Business Standard (ta licencja zawiera Teams.)
- Azure Active Directory (Azure AD) konta wszystkich menedżerów sklepów i pracowników
- Systemy punktu sprzedaży, które są skonfigurowane z uwierzytelnianiem Azure AD

## <a name="conceptual-architecture"></a>Architektura pojęć

Na poniższej ilustracji przedstawiono architekturę pojęć i integrację Dynamics 365 Commerce i Microsoft Teams, w których przykładem jest sklep San Francisco. Zarówno Teams, jak i aplikacja Commerce POS używają Microsoft Planner jako repozytorium, dzięki czemu zadania publikowane z Teams pojawiają się w aplikacji POS, a zadania ad hoc utworzone przez kierowników sklepów w aplikacji POS pojawiają się w aplikacji Teams, co skutkuje bezproblemowym zarządzaniem zadaniami między aplikacjami .    

![Architektura integracji z usługami Commerce i Teams.](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Włączanie integracji Dynamics 365 Commerce i Microsoft Teams](enable-teams-integration.md)

[Obsługa Microsoft Teams z Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Zarządzanie rolami użytkowników w usłudze Microsoft Teams](manage-user-roles-teams.md)

[Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams](map-stores-existing-teams.md)

[Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ](teams-integration-faq.md)
