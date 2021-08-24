---
title: Zapisywanie zaksięgowanych zapisów arkusza w arkuszu
description: W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu.
author: aprilolson
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 519431684cd26d566ae4c9dd75010d5c98881b602681211908c0c70215448fea
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738462"
---
# <a name="journalize-posted-journal-entries"></a>Zapisywanie zaksięgowanych zapisów arkusza w arkuszu

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu. Procedura wykorzystuje dane firmy demonstracyjnej USMF.

1. Przejdź do **Okienko nawigacji**, następnie **Moduły > Księga główna > Ustawienia księgi > Parametry księgi głównej**.
2. Pole **Rozszerzony arkusz księgi** można ustawić na wartość Tak lub Nie. Jeśli zaznaczysz wartość Tak, dane wyjściowe raportu będą inne.
3. Określ, czy okres może zostać zamknięty, jeśli nie został wykonany proces zapisywania w arkuszu. Jeśli ta opcja jest ustawiona na wartość Tak, nie można zamknąć okresu do czasu zakończenia procesu zapisywania w arkuszu dla tego okresu.  
4. Zamknij stronę.
5. W **Okienku nawigacji** otwórz **Moduły > Księga główna > Zadania okresowe > Generowanie arkuszy**.
6. Kliknij przycisk **Filtr**.
7. Zaznacz wiersz z kryteriami filtrowania, które chcesz zdefiniować.
8. W polu **Kryteria** wprowadź lub wybierz kryteria filtrowania.
9. Kliknij przycisk **OK**, aby zamknąć stronę filtru.
10. Kliknij przycisk **OK**, aby rozpocząć proces generowania arkuszy. Po zakończeniu procesu zostanie wygenerowany raport.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]