---
title: Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams
description: W tym artykule opisano, jak mapować sklepy i odpowiadające im zespoły w centrali Dynamics 365 Commerce headquarters, jeśli Twoja organizacja już utworzyła zespoły w Microsoft Teams przed integracją Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 67a1a79dd74d411aa7e21000c8baaa8a069cede7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279127"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a>Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak mapować sklepy i odpowiadające im zespoły w centrali Dynamics 365 Commerce headquarters, jeśli Twoja organizacja już utworzyła zespoły w Microsoft Teams przed integracją Commerce.

Twoja organizacja może mieć zespoły utworzone dla niektórych lub wszystkich sklepów przed integracją Dynamics 365 Commerce i Microsoft Teams. W takim przypadku, aby ustanowić synchronizację zadań między Commerce POS i Microsoft Teams, musisz zapewnić mapowanie sklepów i odpowiedniego zespołu w siedzibie Commerce.

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a>Mapowanie sklepów i odpowiadających im zespołów w centrali usługi Commerce Headquarters 

Aby zmapować sklepy i odpowiadające im zespoły w centrali Commerce, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Administrowanie systemem \> Obszar roboczy \> Zarządzanie danymi**.
1. Wybierz opcję **Eksportuj**. 
1. W okienku akcji wybierz opcję **Nowy**.
1. W obszarze **Nazwa grupy** wprowadź nazwę „Mapowanie zespołów eksportu”.
1. Na skróconej karcie **Wybrane jednostki** wybierz pozycję **Dodaj jednostkę**. Zostanie wyświetlone okno dialogowe **Dodaj jednostkę**.  
1. Na liście rozwijanej **Nazwa jednostki** wybierz opcję **Mapowanie zespołów między źródłem i zespołem**.
1. Z listy rozwijanej **Format danych docelowych** wybierz format **CSV**.
1. Wybierz opcję **Dodaj**, a następnie opcję **Zamknij**.
1. W lewym górnym rogu okienka akcji wybierz pozycję **Eksportuj teraz**.
1. W obszarze **Stan przetwarzania jednostki** wybierz pozycję **Pobierz plik**.
1. W eksportowanych plikach CSV wprowadź wartości parametrów **SOURCETYPE**, **SOURCEID** i **TEAMID** następująco:
    - W przypadku typu **SOURCETYPE** wprowadź nazwę „RetailStore”. 
    - W przypadku kodu **SOURCEID** wprowadź numer sklepu (na przykład „000135” dla sklepu San Francisco). Numery sklepów można znaleźć w **Retail i Commerce \> Kanały \> Sklepy**.
    - Dla identyfikatora **TEAMID** wprowadź odpowiedni identyfikator zespołu Microsoft Teams (na przykład „5f8bc92b-6aa8-451e-85d1-3949c01ddc6c”). Informacje o identyfikatorze zespołu można znaleźć [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
1. Zapisz plik CSV na komputerze lokalnym.
1. Wybierz kolejno opcje **Administrowanie systemem \> Obszar roboczy \> Zarządzanie danymi**, a następnie wybrać **Importuj**.
1. Na skróconej karcie **Wybrane jednostki** wybierz pozycję **Dodaj plik**. Zostanie wyświetlone okno dialogowe **Dodaj plik**.
1. Na liście rozwijanej **Nazwa jednostki** wybierz opcję **Mapowanie zespołów między źródłem i zespołem**.
1. Z listy rozwijanej **Format danych źródłowych** wybierz format **CSV**.
1. Wybierz opcję **Przekaż i dodaj**, wybierz uprzednio zapisany plik CSV, a następnie wybierz opcję **Otwórz**.
1. W oknie dialogowym **Dodaj plik** wybierz **Zamknij**.
1. W okienku akcji wybierz opcję **Zapisz**, a następnie wybierz opcję **Importuj**.

Poniższy przykładowy obraz przedstawia grupę **Mapowanie zespołów eksportu** w aplikacji Commerce z wyróżnionymi elementami **Dodaj jednostkę** i nagłówkami wyeksportowanych plików CSV.

![Eksportuj zespoły mapujące grupę w Commerce z dodanymi elementami encji i wyróżnionymi nagłówkami wyeksportowanych plików CSV.](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> Aby zsynchronizować zarządzanie zadaniami, po ukończeniu tych działań wykonaj kroki opisane w teksie [Synchronizuj zarządzanie zadaniami między Microsoft Teams i POS](synchronize-tasks-teams-pos.md). 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie integracji Dynamics 365 Commerce i Microsoft Teams](commerce-teams-integration.md)

[Włączanie integracji Dynamics 365 Commerce i Microsoft Teams](enable-teams-integration.md)

[Obsługa Microsoft Teams z Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Zarządzanie rolami użytkowników w usłudze Microsoft Teams](manage-user-roles-teams.md)

[Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ](teams-integration-faq.md)
