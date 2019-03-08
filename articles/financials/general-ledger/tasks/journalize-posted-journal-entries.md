---
title: Zapisywanie zaksięgowanych zapisów arkusza w arkuszu
description: W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b50809cf9eb59475856f91d9f1ddfe28ecfd8de6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "318541"
---
# <a name="journalize-posted-journal-entries"></a>Zapisywanie zaksięgowanych zapisów arkusza w arkuszu

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu. Procedura wykorzystuje dane firmy demonstracyjnej USMF.

1. Sprawdź poprawność ustawień zapisywania w arkuszu w obszarze Księga główna > Ustawienia księgi > Parametry księgi głównej.
2. Pole Rozszerzony arkusz księgi można ustawić na wartość Tak lub Nie. Jeśli zaznaczysz wartość Tak, dane wyjściowe raportu będą inne.
3. Określ, czy okres może zostać zamknięty, jeśli nie został wykonany proces zapisywania w arkuszu.
    * Jeśli ta opcja jest ustawiona na wartość Tak, nie można zamknąć okresu do czasu zakończenia procesu zapisywania w arkuszu dla tego okresu.  
4. Zamknij stronę.
5. Wybierz kolejno opcje Księga główna > Zadania okresowe > Generowanie arkuszy.
6. Kliknij przycisk Filtr.
7. Zaznacz wiersz z kryteriami filtrowania, które chcesz zdefiniować.
8. W polu Kryteria wprowadź lub wybierz kryteria filtrowania.
9. Kliknij przycisk OK, aby zamknąć stronę filtru.
10. Kliknij przycisk OK, aby rozpocząć proces zapisywania w arkuszu.
    * Po zakończeniu procesu zostanie wygenerowany raport.  

