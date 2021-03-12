---
title: Zapisywanie zaksięgowanych zapisów arkusza w arkuszu
description: W tej procedurze pokazano sposób zapisywania zaksięgowanych zapisów arkusza w arkuszu.
author: aprilolson
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad18063e0a66a4aac0ebef7f0ce45c73137abcc7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968536"
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

