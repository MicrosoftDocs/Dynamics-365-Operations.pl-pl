---
title: Synchronizowanie daty i godziny w zadaniach importu
description: Użyj stref czasowych UTC w zadaniach importu, aby uniknąć problemów z konwersjami stref czasowych.
author: Sunil-Garg
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ce3bf39e8342d3fe19a253f6d17684b2bd0aec0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570488"
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




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]