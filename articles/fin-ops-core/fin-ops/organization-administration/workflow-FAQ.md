---
title: 'Przepływ pracy: często zadawane pytania'
description: W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy.
author: ChrisGarty
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14aa9b56da005e8e3ca121589d0e22c60f34343b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189782"
---
# <a name="workflow-faq"></a>Przepływ pracy — często zadawane pytania

[!include [banner](../includes/banner.md)]

W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Dlaczego otrzymuję wiele powiadomień, gdy element pracy został odrzucony?
Gdy element pracy został odrzucony, zostaje zakończony jako odrzucony. Inny element pracy zostanie utworzony i przypisany do inicjatora. Oznacza to, że inicjator otrzyma powiadomienie o odrzuconym elemencie pracy, a osobne powiadomienie zostanie wysłane do użytkownika przypisanego nowego elementu pracy „Zażądano zmiany”. 

Każde powiadomienie dotyczy innego elementu pracy, ale podobieństwa mogą powodować zamieszanie. Szukamy sposobów, aby to poprawić w przyszłej wersji.

## <a name="why-are-my-workflow-exports-failing"></a>Dlaczego moje próby eksportu przepływu pracy kończą się niepowodzeniem?
Obecnie istnieje ograniczenie funkcji eksportu przepływu pracy, które zapobiega przekraczaniu 48 znaków w nazwach przepływów pracy. Użycie nazwy, która jest dłuższa niż 48 znaków może spowodować wyświetlenie komunikatu o błędzie „Serwer nie może uwierzytelnić żądania” lub uniemożliwienie wyeksportowania pliku bez typu pliku. Poniższy wpis w blogu zawiera dodatkowe szczegóły [Rozwiązywanie problemów z eksportowaniem przepływów pracy](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>Czy osoba przesyłająca przepływ pracy może również zatwierdzić przepływ pracy?
Tak, osoba przesyłająca przepływ pracy może również zatwierdzić przepływ pracy, jeśli jest skonfigurowany w ten sposób. Aby temu zapobiec, należy skonfigurować **Parametry przepływu pracy >Ogólne > Osoba zatwierdzająca > Nie zezwalają na zatwierdzenie przez osobę przesyłającą** na wartości **Tak**.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>Czy mogę dodawać alerty do przepływów pracy w celu dostarczania powiadomień użytkownikom?
Poniżej znajduje się kilka kluczowych obszarów, w których należy pamiętać przy dodawaniu alertów do przepływów pracy w celu dostarczenia powiadomień:
- Alerty a mechanizmy powiadomień przepływu pracy
    - Alerty można konfigurować do wprowadzania zmian w rekordach. W przepływach pracy są zmieniane rekordy, dzięki czemu można skonfigurować alert związany ze zmianą rekordu spowodowany przez przepływ pracy. Ponieważ jednak przepływy pracy mają różne wbudowane opcje powiadamiania, korzystanie z alertów nie jest idealne.
- Standardowe powiadomienia z przepływów pracy 
    - Przepływy pracy zostały utworzone w powiadomieniach pocztą e-mail. Klient może tak skonfigurować powiadomienia, aby wiadomości e-mail były wysłane do użytkowników. Te powiadomienia nie skutkują komunikatami centrum akcji dla użytkowników.
    - W przyszłej aktualizacji zostanie dodany komunikat centrum akcji, dzięki czemu użytkownikowi zostanie przypisany element pracy przepływu pracy. 
- Dodawanie powiadomień do przepływów pracy
    - Komunikaty centrum akcji mogą być tworzone dla określonych użytkowników, takich jak wiadomość utworzona z przepływu pracy w X ++.
    - [Przepływy pracy mają zdarzenia biznesowe](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow), których odbiorca może wywoływać w celu wyzwolenia na wyszukiwane przez nich powiadomienia.   

Podsumowując, jeśli użytkownik nie otrzyma odpowiedniego powiadomienia z centrum akcji, gdy ma przypisany element pracy przepływu pracy, będzie korzystać [ze zdarzeń biznesowych przepływu pracy](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) w Microsoft Flow w celu wprowadzenia dodatkowych lub różnych powiadomień.
