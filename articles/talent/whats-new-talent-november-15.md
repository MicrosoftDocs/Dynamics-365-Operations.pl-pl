---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (15 listopada 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1a7598db1dc4c11864cf5f5a73d00672ceb66e8c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462227"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-november-15-2018"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (15 listopada 2018 r.)

**Kompilacja 8.1.2045**

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.

## <a name="other-changesfixes"></a>Inne zmiany/poprawki

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a>Nie można zmienić bieżącego stanowiska pracownika na stanowisko otwierane w przyszłości

Została wprowadzona zmiana, aby umożliwić przenoszenie stanowisk, jeśli stanowisko jest dostępne tylko w przyszłości. 

### <a name="position-does-not-display-when-creating-a-new-employee"></a>Stanowisko nie jest wyświetlane przy tworzeniu nowego pracownika

Została wprowadzona zmiana, która pozwala wyświetlać wszystkie otwarte stanowiska dostępne do obsadzenia, gdy są zatrudniani nowi pracownicy w systemie Talent. Obejmuje to stanowiska historyczne lub z datą przyszłą. Stanowiska będą pojawiały się prawidłowo na podstawie daty początkowej zatrudnienia. 

### <a name="termination-date-is-displaying-based-on-user-settings"></a>Data zakończenia zatrudnienia jest wyświetlana na podstawie ustawień użytkownika

Dokonano zmiany listy pracowników w przeszłości do rozliczenia dla dowolnego przesunięcia strefy czasowej dla preferowanej strefy czasowej pracowników przy wyświetlaniu daty zakończenia zatrudnienia.

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a>Łącza Elementy pracy przypisane do nie wyświetlają poprawnych informacji

Wraz z tą zmianą przejście do szczegółów elementów pracy danej osoby na liście spowoduje wyświetlenie prawidłowych informacji dla wybranego elementu. Ten problem występował tylko w przypadku zaawansowanych opcji zabezpieczeń.


## <a name="known-issue"></a>Znany problem

- **Problem**: Podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. 
- **Obejście:** Przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte. Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski złączników będą włączone. (Ten problem zostanie rozwiązany w następnej aktualizacji platformy).
