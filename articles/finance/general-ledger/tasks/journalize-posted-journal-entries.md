---
title: Zapisywanie zaksięgowanych zapisów arkusza w arkuszu
description: W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu.
author: aprilolson
ms.date: 03/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8fca167563b14c825ebe29874c6488ddfb4d9a
ms.sourcegitcommit: 06acdfbccd7bd213a2397ea7b85d104f01914437
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2022
ms.locfileid: "8400882"
---
# <a name="journalize-posted-journal-entries"></a>Zapisywanie zaksięgowanych zapisów arkusza w arkuszu

[!include [banner](../../includes/banner.md)]

Proces zapis do arkusza w księdze głównej umożliwia grupowanie zaksięgowanych zapisów załącznika i zgłaszanie ich w księdze głównej. Na podstawie podanych kryteriów przetwarzanie generuje listę załączników, które używają unikalnej sekwencji numerów i mają wartość **Numer arkusza** wartości księgi głównej jako odniesienie.

Wykonaj poniższe czynności, aby księgować opublikowane wpisy księgowe. Procedura wykorzystuje dane firmy demonstracyjnej **USMF**.

1. Przejdź do pozycji **Księga główna** \> **Ustawienia księgi** \> **Parametry księgi głównej**.
2. W polu **Rozszerzony arkusz księgi** wybierz wartość. Jeśli zaznaczysz wartość **Tak**, dane wyjściowe raportu będą inne.
3. Określ, czy okres może zostać zamknięty, jeśli nie został wykonany proces zapisywania w arkuszu. Jeśli ta opcja jest ustawiona na wartość **Tak**, nie można zamknąć okresu do czasu zakończenia procesu zapisywania w arkuszu dla tego okresu.
4. Zamknij stronę.
5. Przejdź do **Księga główna** \> **Zadania okresowe** \> **Generowanie arkuszy** i wybierz **Filtr**.
6. Wybierz wiersz kryteriów filtrowania, które chcesz zdefiniować.
7. W polu **Kryteria** wprowadź lub wybierz kryteria filtrowania.
8. Kliknij przycisk **OK**, aby zamknąć stronę.
9. Wybierz **OK**, aby rozpocząć proces generowania arkuszy. Po zakończeniu procesu zostanie wygenerowany raport.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
