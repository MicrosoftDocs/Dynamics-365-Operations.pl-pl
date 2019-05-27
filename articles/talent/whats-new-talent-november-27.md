---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (27 listopada 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/27/2018
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
ms.search.validFrom: 2018-11-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 81ea0e4f4878d1967234c597504071ce464a22c5
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518854"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-27-2018"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (27 listopada 2018 r.)

[!include [banner](includes/banner.md)]

**Kompilacja 8.1.2064**

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.


## <a name="changes"></a>Zmiany

### <a name="unable-to-create-a-note-in-case-management"></a>Nie można utworzyć notatki w Zarządzaniu sprawami

Wprowadzono zmiany, aby rozwiązać problem występujący podczas próby edytowania lub tworzenia notatki w dzienniku spraw w Zarządzaniu sprawami.

### <a name="misspelled-word-on-the-analytics-tab-in-the-compensation-workspace"></a>Nieprawidłowo napisane słowo na karcie analityki w obszarze roboczym wynagrodzeń 

Poprawiono pisownię pochodzenia etnicznego na wykresie analiz wynagrodzeń w obszarze roboczym wynagrodzeń.

### <a name="employee-self-service-workspace-not-displaying-when-a-user-isnt-assigned-to-a-worker"></a>Obszar roboczy samoobsługi pracownika nie wyświetla się, jeśli użytkownik nie jest przypisany do pracownika 

Wprowadzono zmiany, gdy obszar roboczy **samoobsługa pracownika** jest wybrany jako strona początkowa przy rozruchu dla użytkownika, który nie jest przypisany do pracownika. W takiej sytuacji jest wyświetlany domyślny pulpit nawigacyjny.

### <a name="leave-and-absence-error-object-reference-not-set-to-an-instance-of-an-object"></a>Błąd urlopów i nieobecności: obiekt odwołania nie jest ustawiony na wystąpienie obiektu

Wprowadzono zmiany do urlopów i nieobecności, aby rozwiązać ten problem po zatwierdzeniu rekordów urlopów i nieobecności na liście **elementy pracy przypisane do mnie**.

### <a name="unable-to-recall-an-image-workflow"></a>Nie można wznowić przepływu pracy obrazu

Po wznowieniu przepływ pracy obrazu, przepływ pracy zostanie ustawiony jako „anulowany” i istniejące żądanie można usunąć w obszarze roboczym samoobsługi pracowników.

### <a name="rehired-employees-or-contractors-show-up-multiple-times-after-termination"></a>Ponownie zatrudnieni pracownicy lub zleceniobiorcy pokazują się wiele razy po zakończeniu umowy 

Ta aktualizacja sprawia, że zwolnieni i ponownie zatrudnieni pracownicy będą wyświetlani tylko raz na liście „odeszli”. 

## <a name="known-issue"></a>Znany problem

- **Problem**: Podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. 
- **Obejście:** Przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte. Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski złączników będą włączone. (Ten problem zostanie rozwiązany w następnej aktualizacji platformy).
