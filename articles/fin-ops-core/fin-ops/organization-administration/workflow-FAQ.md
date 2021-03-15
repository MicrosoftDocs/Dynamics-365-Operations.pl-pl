---
title: 'Przepływ pracy: często zadawane pytania'
description: W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy.
author: ChrisGarty
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58aa4a6d313a78e88c2858637d6de167895ec534
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797398"
---
# <a name="workflow-faq"></a>Przepływ pracy — często zadawane pytania

[!include [banner](../includes/banner.md)]

W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Dlaczego otrzymuję wiele powiadomień, gdy element pracy został odrzucony?
Gdy element pracy został odrzucony, zostaje zakończony jako odrzucony. Inny element pracy zostanie utworzony i przypisany do inicjatora. Oznacza to, że inicjator otrzyma powiadomienie o odrzuconym elemencie pracy, a osobne powiadomienie zostanie wysłane do użytkownika przypisanego nowego elementu pracy „Zażądano zmiany”. 

Każde powiadomienie dotyczy innego elementu pracy, ale podobieństwa mogą powodować zamieszanie. Szukamy sposobów, aby to poprawić w przyszłej wersji.

## <a name="why-are-my-workflow-exports-failing"></a>Dlaczego moje próby eksportu przepływu pracy kończą się niepowodzeniem?
Obecnie istnieje ograniczenie funkcji eksportu przepływu pracy, które zapobiega przekraczaniu 48 znaków w nazwach przepływów pracy. Użycie nazwy, która jest dłuższa niż 48 znaków może spowodować wyświetlenie komunikatu o błędzie „Serwer nie może uwierzytelnić żądania” lub uniemożliwienie wyeksportowania pliku bez typu pliku. Poniższy wpis w blogu zawiera dodatkowe szczegóły; [Rozwiązywanie problemów z eksportowaniem przepływów pracy](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>Czy osoba przesyłająca przepływ pracy może również zatwierdzić przepływ pracy?
Tak, osoba przesyłająca przepływ pracy może również zatwierdzić przepływ pracy, jeśli jest skonfigurowany w ten sposób. Aby temu zapobiec, należy ustawić pozycję **Administracja systemem > Przepływ pracy > Parametry przepływu pracy >Ogólne > Osoba zatwierdzająca > Nie zezwalają na zatwierdzenie przez osobę przesyłającą** na wartość **Tak**.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>Czy mogę dodawać alerty do przepływów pracy w celu dostarczania powiadomień użytkownikom?
Poniżej znajduje się kilka kluczowych obszarów, w których należy pamiętać przy dodawaniu alertów do przepływów pracy w celu dostarczenia powiadomień:
- Alerty a mechanizmy powiadomień przepływu pracy
    - Alerty można konfigurować do wprowadzania zmian w rekordach. W przepływach pracy są zmieniane rekordy, dzięki czemu można skonfigurować alert związany ze zmianą rekordu spowodowany przez przepływ pracy. Ponieważ jednak przepływy pracy mają różne wbudowane opcje powiadamiania, korzystanie z alertów nie jest idealne.
- Standardowe powiadomienia z przepływów pracy 
    - Przepływy pracy zostały utworzone w powiadomieniach pocztą e-mail. Klient może tak skonfigurować powiadomienia, aby wiadomości e-mail były wysłane do użytkowników. Te powiadomienia nie skutkują komunikatami centrum akcji dla użytkowników.
    - W przyszłej aktualizacji zostanie dodany komunikat centrum akcji, dzięki czemu użytkownikowi zostanie przypisany element pracy przepływu pracy. 
- Dodawanie powiadomień do przepływów pracy
    - Komunikaty centrum akcji mogą być tworzone dla określonych użytkowników, takich jak wiadomość utworzona z przepływu pracy w X ++.
    - [Przepływy pracy mają zdarzenia biznesowe](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow), których odbiorca może wywoływać w celu wyzwolenia Przepływów, które mają wyszukiwane przez nich powiadomienia.   

Podsumowując, jeśli użytkownik nie otrzyma odpowiedniego powiadomienia z centrum akcji, gdy ma przypisany element pracy przepływu pracy, będzie korzystać ze [zdarzeń biznesowych przepływu pracy](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) w Microsoft Power Automate w celu wprowadzenia dodatkowych lub innych powiadomień.

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>Dlaczego Edytor przepływu pracy nie może być uruchomiony w programie AD FS?
Podczas uruchamiania w usługach Active Directory Federation Services (AD FS) w uaktualnionym środowisku, edytor przepływu pracy może mieć problemy z uruchomieniem. Jeśli tak, upewnij się, że adres URL „https://dynamicsaxworkfloweditor/” jest dodawany do właściwości **Microsoft Dynamics 365 for Operations (Lokalne — Przepływ pracy — Aplikacja natywna)** w ustawieniach usługi ADFS.

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>Dlaczego otrzymuję zakleszczenia kodu SQL w przetwarzaniu przepływu pracy? 
Domyślna wartość pola **Liczba elementów przepływu pracy przypadająca na partię** na stronie **Parametry przepływu pracy** wynosi 0. Wartość 0 powoduje zmianę wartości domyślnej na 20 sztuk na partię. Podczas dostosowywania tej wartości należy zachować ostrożność, ponieważ duża liczba towarów na partię (> 40) może spowodować zakleszczenie kodu SQL.

## <a name="what-is-the-workflow-enhanced-error-feature"></a>Co to jest funkcja błędów rozszerzonych przepływu pracy?
Funkcja błędów rozszerzonych przepływu pracy w wersji 10.0.13 dodaje kody błędów w celu odróżnienia różnych klas błędów przepływu pracy. Komunikaty o błędach raportowane są głównie pod kątem mniejszych różnic w celu ich wyraźniejszego wyróżnienia.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]