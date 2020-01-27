---
title: Zapisywanie przewodników zadań w usłudze LCS i odtwarzanie ich ponownie
description: W tym temacie opisano, jak zapisać przewodniki po zadaniach do programu Microsoft Dynamics Lifecycle Services (LCS), a następnie odtworzyć je ponownie.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6ee3556e033cf298bbd5102746d2b57884f5e6d0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898071"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Zapisywanie przewodników zadań w usłudze LCS i odtwarzanie ich ponownie

**Szczegóły środowiska** 

Microsoft Dynamics 365 Talent, który został wdrożony za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS)

**Wystawienie**

Odbiorca chce zapisać nowe nagrania zadań w projekcie LCS, a następnie odtworzyć wskazówki zapisanego zadania.

**Rozdzielczość**

Wykonaj te kroki, aby zapisać nagranie zadania w LCS.

1. Zaloguj się do LCS, a następnie wybierz projekt.
2. Wybierz kafelek **Narzędzie do modelowania procesów biznesowych**.
3. Wyświetl tę stronę w zaktualizowanym interfejsie narzędzia BPM.
4. Wybierz bibliotekę, a następnie wybierz przycisk **Kopiuj**.
5. Wprowadź nazwę dla modelu Narzędzie do modelowania procesów biznesowych (BPM).
6. Zaloguj się w aplikacji Talent z LCS.
7. W polu **Wyszukaj** wpisz **pomoc**. Zostanie otwarta pomoc usługi Lifecycle Services
8. Wybierz przycisk **odśwież** dla konfiguracji pomocy usługi Lifecycle Services.

    Nowe biblioteki BPM powinny być wyświetlane i aktywne.

9. Zamknij stronę.
10. Utwórz nagranie zadania.
11. Po zakończeniu zaznacz **zapisz w Lifecycle Services**.

    ![Zapisz w usłudze Lifecycle Services](media/task-guides.png)

12. Wybierz bibliotekę BPM i węzeł, aby zapisać nagranie zadania.

Wykonaj następujące kroki, aby powtórzyć odtworzyć przewodnik zadania z LCS.

1. Otwórz rejestratora zadań.
2. Wybierz **Otwórz z LCS**.
3. Wybierz bibliotekę i węzeł BPM, który ma zapisany przewodnik zadania.
4. Otwórz przewodnik zadania.
