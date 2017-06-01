---
title: "Księgowanie wstępnego nabycia środka trwałego"
description: "W tym temacie wyjaśniono, jak skonfigurować i księgować wstępne nabycia środków trwałych."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 264704
ms.search.region: Czech Republic, Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 239611a90e077c1e55fe7832ff0cf7806287eccd
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="post-the-pre-acquisition-of-a-fixed-asset"></a>Księgowanie wstępnego nabycia środka trwałego

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono, jak skonfigurować i księgować wstępne nabycia środków trwałych.

**Uwaga:** Funkcjonalność księgowania operacji wstępnego nabycia środków trwałych jest dostępna tylko dla firm, których adres podstawowy mieści się na Węgrzech lub w Czechach. Wstępne nabycie środków trwałych nie podlega amortyzacji ani nie wpływa na koszty nabycia i wartość księgową netto środka trwałego. Po zaksięgowaniu wstępnego nabycia stan środka trwałego zmienia się na **Nabyto**. Środek trwały, którego stanem jest **Nabyto**, nie podlega amortyzacji. Z drugiej strony po zaksięgowaniu nabycia stan zmienia się na **Otwarte**, a środek trwały podlega amortyzacji.

## <a name="set-up-preacquisitions"></a>Konfigurowanie funkcji wstępnego nabycia
Zanim będzie można księgować wstępne nabycia, należy wykonać następujące czynności konfiguracyjne:

-   Na stronie **Parametry środków trwałych** ustaw opcję **Zezwalaj na wstępne nabycia** na **Tak**.
-   Na stronie **Profile księgowania środków trwałych** ustaw profil księgowania środków trwałych na typu księgowania wstępnego nabycia.

## <a name="post-a-preacquisition-of-a-fixed-asset"></a>Księgowanie wstępnego nabycia środka trwałego
1.  Na stronie **Środki trwałe** utwórz nowy arkusz i wprowadź w nim wszystkie niezbędne informacje.
2.  Dla nowo utworzonego arkusza kliknij opcję **Wiersze**, aby otworzyć stronę **Załącznik arkusza**.
3.  Kliknij przycisk **Nowy**, aby utworzyć wiersz.
4.  W polu **Typ transakcji** wybierz transakcję o typie transakcji **Wstępne nabycie**.
5.  Wprowadź wymagane wartości w pozostałych polach.
6.  Kliknij przycisk **Weryfikuj**, aby sprawdzić poprawność wierszy arkusza.
7.  Kliknij kolejno opcje **Propozycje** &gt; **Propozycja wstępnego nabycia**.
8.  Kliknij opcję **Wybierz**, aby skonfigurować kryteria wyboru, a następnie kliknij przycisk **OK**.
9.  Kliknij przycisk **OK**, aby zamknąć stronę **Propozycja wstępnego nabycia**.
10. Kliknij kolejno opcje **Księguj** &gt; **Księguj**, aby zaksięgować transakcję wstępnego nabycia. Na stronie **Księgi** stan środka trwałego powinien mieć teraz wartość **Nabyto**.





