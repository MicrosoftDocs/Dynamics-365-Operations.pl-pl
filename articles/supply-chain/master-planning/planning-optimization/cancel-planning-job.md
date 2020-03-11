---
title: Anuluj planowanie pracy
description: W tym temacie wyjaśniono, jak usunąć aktywne planowanie pracy, gdy używana jest funkcja optymalizacji planowania.
author: ChristianRytt
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 18c5c7b8030fc6adbc548dab750e4f454aebc867
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076356"
---
# <a name="cancel-a-planning-job"></a>Anulowanie zadania planowania

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

W Microsoft Dynamics 365 Supply Chain Management, można usunąć aktywne planowanie pracy, gdy używana jest funkcja optymalizacji planowania. Po wybraniu opcji **Anuluj** w oknie dialogowym, gdy zadanie optymalizacji planowania zostanie wyzwolone bezpośrednio z interfejsu użytkownika (a nie w tle), zadanie optymalizacji planowania nie zostanie anulowane. Nawet w przypadku otrzymania ostrzeżenia, na przykład „Operacja anulowana”, trzeba wykonać następujące kroki, aby anulować zadanie planowania z optymalizacją planowania.


Aby anulować aktywne zadanie planowania, należy wykonać następujące kroki. 

> [!NOTE]
> Tylko aktywna praca może być usunięta.

1. Przejdź do **Planowanie główne \> Ustawień \> Plany**.
2. Umożliwia wybór odpowiedniego planu dla przebiegu planowania.
3. Wybierz **Historia**.
4. Wybierz planowaną pracę do anulowania.
5. Wybierz **Anuluj**.

Stan zadania będzie **anulowany** do momentu potwierdzenia przez usługę optymalizacji planowania, że zadanie zostało anulowane. Status zostanie wówczas zaktualizowany do stanu **Anulowane**.

> [!NOTE]
> Aby wyświetlić zmiany stanu, należy odświeżyć stronę, wybierając przycisk **Odśwież**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie optymalizacji planowania](planning-optimization-overview.md)

[Rozpoczęcie optymalizacji planowania](get-started.md)

[Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md)

[Wyświetlanie dzienników historii i planowania planów](plan-history-logs.md)

[Stosowanie filtrów do planu](plan-filters.md)
