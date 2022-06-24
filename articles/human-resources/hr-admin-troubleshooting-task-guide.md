---
title: Zapisywanie przewodników zadań w usłudze LCS i odtwarzanie ich ponownie
description: W tym artykule opisano, jak zapisać przewodniki po zadaniach do programu Microsoft Dynamics Lifecycle Services (LCS), a następnie odtworzyć je ponownie.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2efe48a31db533c5f22d4174cc6897f4a590cf49
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875808"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Zapisywanie przewodników zadań w usłudze LCS i odtwarzanie ich ponownie


[!INCLUDE [PEAP](../includes/peap-2.md)]

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
