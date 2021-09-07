---
title: Zapisywanie przewodników zadań w usłudze LCS i odtwarzanie ich ponownie
description: W tym temacie opisano, jak zapisać przewodniki po zadaniach do programu Microsoft Dynamics Lifecycle Services (LCS), a następnie odtworzyć je ponownie.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 42fad014590abebf159b71227a44eb8df60bf05e
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416888"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Zapisywanie przewodników zadań w usłudze LCS i odtwarzanie ich ponownie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Szczegóły środowiska** 

Microsoft Dynamics 365 Human Resources, który został wdrożony za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS)

**Wystawienie**

Odbiorca chce zapisać nowe nagrania zadań w projekcie LCS, a następnie odtworzyć wskazówki zapisanego zadania.

**Rozdzielczość**

Wykonaj te kroki, aby zapisać nagranie zadania w LCS.

1. Zaloguj się do LCS, a następnie wybierz projekt.
2. Wybierz kafelek **Narzędzie do modelowania procesów biznesowych**.
3. Wyświetl tę stronę w zaktualizowanym interfejsie narzędzia BPM.
4. Wybierz bibliotekę, a następnie wybierz przycisk **Kopiuj**.
5. Wprowadź nazwę dla modelu Narzędzie do modelowania procesów biznesowych (BPM).
6. Zaloguj się do modułu Human Resources z usługi LCS.
7. W polu **Wyszukaj** wpisz **pomoc**. Zostanie otwarta pomoc usługi Lifecycle Services
8. Wybierz przycisk **odśwież** dla konfiguracji pomocy usługi Lifecycle Services.

    Nowe biblioteki BPM powinny być wyświetlane i aktywne.

9. Zamknij stronę.
10. Utwórz nagranie zadania.
11. Po zakończeniu zaznacz **zapisz w Lifecycle Services**.

    ![Zapisz w usłudze Lifecycle Services.](media/task-guides.png)

12. Wybierz bibliotekę BPM i węzeł, aby zapisać nagranie zadania.

Wykonaj następujące kroki, aby powtórzyć odtworzyć przewodnik zadania z LCS.

1. Otwórz rejestratora zadań.
2. Wybierz **Otwórz z LCS**.
3. Wybierz bibliotekę i węzeł BPM, który ma zapisany przewodnik zadania.
4. Otwórz przewodnik zadania.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
