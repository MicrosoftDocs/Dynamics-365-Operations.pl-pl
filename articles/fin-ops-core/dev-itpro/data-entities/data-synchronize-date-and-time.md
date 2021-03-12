---
title: Synchronizowanie daty i godziny w zadaniach importu
description: Użyj stref czasowych UTC w zadaniach importu, aby uniknąć problemów z konwersjami stref czasowych.
author: Sunil-Garg
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae04b09a68e64d6d70c0329e689ab08c3903fca0
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798726"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Synchronizowanie daty i godziny w zadaniach importu

[!include [banner](../includes/banner.md)]

Bardzo ważne jest ustawienie strefy czasowej dla zadania importu na uniwersalny czas koordynowany (UTC). Użycie innego ustawienia może spowodować wyświetlanie w importowanych danych nieoczekiwanych dat i godzin. Bez poprawnego ustawienia proces importowania konwertuje datę UTC na format lokalny, a następnie ustawienia systemowe konwertują ją ponownie.

Te dwie konwersje powodują zmianę dat między aplikacjami. Na przykład podwójna konwersja może spowodować, że data rozpoczęcia dla pracownika może być różna w aplikacjach Dynamics 365 Human Resources i Dynamics 365 Finance z powodu różnic w strefach czasowych. Ustawienie zadania importowania na czas UTC rozwiązało ten problem.

1. W Dynamics 365 Finance and Operations wybierz pozycję **Zarządzanie danymi**.

2. Wybierz opcję **Importuj projekty**, a następnie wybierz projekt.

3. W obszarze **Format daty źródłowej** wybierz format **CSV-Unicode**.

   [![Zmienianie formatu daty źródłowej na UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Zmień **strefę czasową** na **Uniwersalny czas koordynowany** i zmień **język** na **En-US**.


