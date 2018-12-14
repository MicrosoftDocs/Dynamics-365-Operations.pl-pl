---
title: "Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (15 listopada 2018 r.)"
description: "W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 3cc19a8e5f726495e698a3a2f4ccce7460a61657
ms.openlocfilehash: 0e9de5e36e67941ab09c773a63b0e7045105a07e
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (15 listopada 2018 r.)

[!include [banner](includes/banner.md)]

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

