---
title: Synchronizowanie daty i godziny w zadaniach importu
description: Użyj stref czasowych UTC w zadaniach importu, aby uniknąć problemów z konwersjami stref czasowych.
author: peakerbl
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8faa7b73349c48d3a02b685546b47c4969c6027
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109441"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Synchronizowanie daty i godziny w zadaniach importu

[!include [banner](../includes/banner.md)]

Bardzo ważne jest ustawienie strefy czasowej dla zadania importu na uniwersalny czas koordynowany (UTC). Użycie innego ustawienia może spowodować wyświetlanie w importowanych danych nieoczekiwanych dat i godzin. Bez poprawnego ustawienia proces importowania konwertuje datę UTC na format lokalny, a następnie ustawienia systemowe konwertują ją ponownie.

Te dwie konwersje powodują zmianę dat między aplikacjami. Na przykład podwójna konwersja może spowodować, że data rozpoczęcia dla pracownika może być różna w aplikacjach Dynamics 365 Human Resources i Dynamics 365 Finance z powodu różnic w strefach czasowych. Ustawienie zadania importowania na czas UTC rozwiązało ten problem.

1. W aplikacjach finansowych i operacyjnych usługi Dynamics 365 wybierz pozycję **Zarządzanie danymi**.

2. Wybierz opcję **Importuj projekty**, a następnie wybierz projekt.

3. W obszarze **Format daty źródłowej** wybierz format **CSV-Unicode**.

   [![Zmienianie formatu daty źródłowej na UTC.](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Zmień **strefę czasową** na **Uniwersalny czas koordynowany** i zmień **język** na **En-US**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

