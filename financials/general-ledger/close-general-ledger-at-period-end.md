---
title: "Zamknięcie księgi głównej na koniec okresu"
description: "W tym temacie opisano zadania, które zazwyczaj są wykonywane podczas wykonywania operacji zamknięcia okresu w księdze głównej."
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 81d687cc16ef43442c8c1c166cc6f0d8b171e28f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="close-the-general-ledger-at-period-end"></a>Zamknięcie księgi głównej na koniec okresu

[!include[banner](../includes/banner.md)]


W tym temacie opisano zadania, które zazwyczaj są wykonywane podczas wykonywania operacji zamknięcia okresu w księdze głównej. 

W księdze głównej można wykonać procedury zamykania dla okresu lub roku. Procesy zamknięcia przygotowują system do nowego okresu. Aby przygotować system do nowego roku, należy uruchomić proces zamknięcia roku. Każda organizacja ma różne procesy i czynności wykonywane na koniec okresu. Oto kilka kroków opcjonalnych na koniec okresu:

-   Ukończenie wszystkie zadań dla wszystkich innych modułów, takich jak Rozrachunki z odbiorcami, Rozrachunki z dostawcami i Zapasy.
-   Sprawdzenie, czy wszystkie arkusze są zaksięgowane.
-   Wykonanie przeszacowania w walucie obcej w celu wygenerowania wszelkiej niezrealizowanej dodatniej lub ujemnej różnicy kursowej.
-   Rozliczenie transakcji dla każdego konta księgowego.
-   Przetworzenie wszelkich wymaganych alokacji.
-   Ręczne zaksięgowanie korekt na koniec roku.
-   Zapis transakcji do arkusza i sprawdzenie raportu **Arkusz księgi**.
-   Wykonywanie konsolidacji przy użyciu konsolidowanej firmy lub raportów finansowych.
-   Generowanie sprawozdań finansowych na koniec okresu przy użyciu raportów finansowych.
-   Ustawianie stanu **Zablokowany** dla okresów księgowych, by dalsze księgowania nie występowały. Można również ograniczyć okres do określonej grupy użytkowników, gdy występują czynności związane z końcem okresu. Pozwala to zachować większą kontrolę. Dobrze jest ustawić dla okresów stan **Trwale zamknięty**, ponieważ nie można ponownie otworzyć okresu, który został zamknięty.

W obszarze roboczym Zamknięcie okresu obrachunkowego można porządkować i śledzić zadania wymagane do różnych procesów zamknięcia okresu. Aby uzyskać więcej informacji, patrz [Obszar roboczy zamknięcia okresu obrachunkowego](financial-period-close-workspace.md) i [Zamknięcie na koniec roku](Year-end-close.md). 






