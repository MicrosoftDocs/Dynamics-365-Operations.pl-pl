---
title: Konfigurowanie modeli ewidencji
description: W tej procedurze pokazano, jak utworzyć nową księgę środków trwałych i skojarzyć ją z grupą środków trwałych.
author: moaamer
ms.date: 08/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46c26e5fad3c5c60d87c2fea2b29043c69b82b5d
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344665"
---
# <a name="set-up-value-models"></a>Konfigurowanie modeli ewidencji

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]


W tej procedurze pokazano, jak utworzyć nową księgę środków trwałych i skojarzyć ją z grupą środków trwałych. Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.

## <a name="create-a-book"></a>Tworzenie księgi
1. Wybierz kolejno opcje Środki trwałe > Ustawienia > Księgi.
2. Kliknij przycisk Nowy.
3. W polu Księga wpisz wartość.
4. Wypełnij pole Opis.
    * Jeśli zaznaczysz opcję Oblicz amortyzację, skojarzona księga środków trwałych będzie uwzględniana w propozycjach amortyzacji. Jeśli opcja nie jest zaznaczona, pozycje księgi środków trwałych nie będą automatycznie amortyzowane.  
5. W polu Oblicz amortyzację wybierz opcję Tak.
6. Wprowadź lub wybierz wartość w polu Profil amortyzacji.
    * Profil amortyzacji alternatywnej jest również nazywany alternatywną metodą amortyzacji. Propozycja amortyzacji zostanie przełączona na ten profil, gdy profil alternatywny wyliczy kwotę amortyzacji równą lub większą kwocie z domyślnego profilu amortyzacji.  
    * Profil Amortyzacja dodatkowa będzie używany na potrzeby dodatkowej amortyzacji składnika aktywów w nadzwyczajnych okolicznościach. Na przykład może to służy do zarejestrowania amortyzacji powstałej w wyniku klęski żywiołowej.  
    * Jeśli zaznaczysz opcję Tworzenie korekt amortyzacji przy korektach podstawy, korekty amortyzacji będą tworzone automatycznie po aktualizacji wartości środka trwałego. Jeśli opcja nie jest zaznaczona, zaktualizowana wartość składnika aktywów wpłynie tylko na przyszłe obliczenia amortyzacji.  
7. Zaznacz opcję Tak w polu Tworzenie korekt amortyzacji przy korektach podstawy.
    * Domyślnie transakcje księgi środków trwałych są księgowane w księdze głównej. Księgowania pozycji księgi w księdze głównej można wyłączyć, ustawiając w polu Księguj w księdze głównej wartość Nie. Księgi, które nie są księgowane w księdze głównej, są zazwyczaj używane na potrzeby sprawozdawczości podatkowej. Zapewnia to dodatkową elastyczność umożliwiającą usuwanie historycznych transakcji z księgi środków trwałych, ponieważ nie zostały one potwierdzone w księdze głównej.  
    * Ustawienie Warstwa księgowania domyślnie przyjmuje wartość Bieżąca warstwa, jeśli pozycje księgi są księgowane do księgi głównej, lub Brak, jeżeli pozycje nie są księgowane do księgi głównej. Zaktualizuj warstwę księgowania, jeśli chcesz, aby transakcje tej księgi były księgowanie na innej warstwie.  
8. W polu Kalendarz wprowadź lub wybierz wartość.
    * W przypadku ksiąg pochodnych transakcje są księgowane do różnych ksiąg w tym samym czasie. Transakcje tworzy się w księdze podstawowej, a podczas księgowania dokładne kopie transakcji są księgowane w księdze pochodnej. Transakcje w księdze pochodnej nie są ponownie obliczane, więc nie można ich stosować jako transakcji amortyzacji.  

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Kojarzenie księgi z grupą środków trwałych
1. Kliknij opcję Grupy środków trwałych.
2. W polu Grupa środków trwałych wprowadź lub wybierz wartość.
3. W polu Okres użytkowania wpisz liczbę.

  - Okresy amortyzacji są obliczane po wprowadzeniu okresu użytkowania środka trwałego.  
  - Konwencja amortyzacji może zostać ustawiona zgodnie z wymogami dla celów podatkowych.
  - W przypadku środków trwałych skojarzonych z wynajmami wartość w polu **Okres użytkowania** jest zastępowana przez okres wynajmu z księgi środków trwałych lub okres użyteczności środka trwałego, zależnie od tego, który okres jest krótszy. Jeśli w polu **Przeniesienie własności** jest ustawiona wartość **Tak** dla księgi wynajmu, wartość w polu **Okres użyteczności** zawsze będzie okresem użyteczności środka trwałego.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
