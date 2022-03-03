---
title: Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS
description: W tym temacie opisano sposób synchronizowania zarządzania zadaniami między punktami sprzedaży Microsoft Teams i Dynamics 365 Commerce (POS).
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c07ca28b45335de5e327305b7426d1b6de8ce5c7
ms.sourcegitcommit: 68114cc54af88be9a3a1a368d5964876e68e8c60
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2022
ms.locfileid: "8323504"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a>Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób synchronizowania zarządzania zadaniami między punktami sprzedaży Microsoft Teams i Dynamics 365 Commerce (POS).

Jednym z głównych celów integracji zespołów jest włączenie synchronizacji zarządzania zadaniami między aplikacją POS a Teams. W ten sposób pracownicy sklepu mogą używać aplikacji pos lub Teams do zarządzania zadaniami i nie muszą przełączać aplikacji.

Ponieważ planowanie jest używane jako repozytorium zadań w Teams, między zespołami musi być połączenie Teams z Dynamics 365 Commerce. To łącze jest ustanowione przy użyciu określonego identyfikatora planu dla danego zespołu sklepu.

W poniższych procedurach popisano sposób skonfigurowania synchronizacji zarządzania zadaniami między aplikacją POS i Teams.

## <a name="publish-a-test-task-list-in-teams"></a>Publikowanie listy zadań testowych w Teams

W poniższej procedurze założono, że zespoły sklepów po raz pierwszy korzysta z integracji zarządzania zadaniami Microsoft Teams z usługami Commerce.

Aby opublikować listę zadań testowych w Teams, wykonaj następujące kroki.

1. Zaloguj się do Teams jako kierownik ds. komunikacji. Zazwyczaj kierownicy ds. komunikacji są użytkownikami, którzy mają rolę **Menedżer regionalny** w portalu Commerce.
1. W lewym okienku nawigacji wybierz pozycję **Zadania według programu Planner**.
1. Na karcie **Listy opublikowane** wybierz pozycję **Nowa lista** w lewym dolnym rogu i nadaj nazwę nowej liście **Lista zadań testowych**.
1. Wybierz opcję **Utwórz**. Nowa lista jest wyświetlana w obszarze **Wersje robocze**.
1. W obszarze **Tytuł zadania** nadaj pierwsze zadanie tytuł **Testowania integracji Teams**. Następnie wybierz opcję **Wprowadź**.
1. Z listy **Wersji roboczych** wybierz listę zadań. Następnie wybierz pozycję **Publikuj** w prawym górnym rogu.
1. W oknie dialogowym **Wybierz osoby, które mają zostać publikowane**, wybierz zespoły, które mają otrzymać listę zadań testowych.
1. Wybierz **przycisk Dalej**, aby przejrzeć plan publikacji. Jeśli musisz wprowadzić zmiany, wybierz pozycję  **Wstecz**. 
1. Wybierz **pozycję Potwierdź**, aby kontynuować, a następnie wybierz pozycję **Publikuj**.
1. Po zakończeniu publikowania u góry karty **Listy opublikowane** zostanie wyświetlony komunikat informujący, czy lista zadań została pomyślnie dostarczona.

Aby uzyskać więcej informacji, zobacz [Publikowanie list zadań w celu utworzenia i śledzenia pracy w organizacji](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).

## <a name="link-pos-and-teams-for-task-management"></a>Połącz POS z Teams w celu zarządzania zadaniami

Aby połączyć aplikacje POS z Microsoft Teams do zarządzania zadaniami w programie Commerce Headquarters, należy wykonać następujące kroki.

> [!NOTE]
> Przed rozpoczęciem integrowania zarządzania zadaniami z Microsoft Teams upewnij się, że włączono funkcję [Integrację Dynamics 365 Commerce i Microsoft Teams](enable-teams-integration.md). 

1. Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Itnegracja zadań z Microsoft Teams**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Zmień ustawienie opcji **Włącz integrację zarządzania zadaniami** na **Tak**.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz **Konfiguracja zarządzania zadaniami**. Należy otrzymać powiadomienie informujące o utworzeniu zadania wsadowego o nazwie **Tworzenie Teams**.
1. Przejdź do **Administracja systemu \> Zapytania \> Zadania wsadowe** i znajdź ostatnie zadanie z opisem Inicjowanie **Obsługa Teams**. Czekaj, aż to zadanie zakończy się.
1. Uruchom zadanie **1070 usługi CDX**, aby opublikować identyfikator planu i odwołania do sklepu w programie Retail Server.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie integracji Dynamics 365 Commerce i Microsoft Teams](commerce-teams-integration.md)

[Włączanie integracji Dynamics 365 Commerce i Microsoft Teams](enable-teams-integration.md)

[Obsługa Microsoft Teams z Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Zarządzanie rolami użytkowników w usłudze Microsoft Teams](manage-user-roles-teams.md)

[Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams](map-stores-existing-teams.md)

[Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ](teams-integration-faq.md)
