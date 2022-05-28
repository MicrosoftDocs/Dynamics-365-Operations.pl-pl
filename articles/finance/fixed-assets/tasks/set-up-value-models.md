---
title: Konfigurowanie modeli ewidencji
description: W tej procedurze pokazano, jak utworzyć nową księgę środków trwałych i skojarzyć ją z grupą środków trwałych.
author: moaamer
ms.date: 12/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71d256b600956a4e525cde626c958713f6258f5a
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727069"
---
# <a name="set-up-value-models"></a>Konfigurowanie modeli ewidencji

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

W tej procedurze pokazano, jak utworzyć nową księgę środków trwałych i skojarzyć ją z grupą środków trwałych.

## <a name="create-a-book"></a>Tworzenie księgi
1. Wybierz kolejno opcje **Środki trwałe \> Ustawienia \> Księgi**.
2. Wybierz pozycję **Nowy**.
3. Wprowadź wartość w polu **Księga**.
4. W polu **Opis** wprowadź lub wybierz wartość.
5. W opcji **Obliczanie amortyzacji** ustaw wartość **Tak**.

    Jeśli opcję **Obliczanie amortyzacji** ustawiono na **Tak**, skojarzona ewidencja składników majątku będzie uwzględniana w propozycjach amortyzacji. Jeśli opcja jest ustawiona na **Nie**, pozycje księgi środków trwałych nie będą automatycznie amortyzowane.

6. Wprowadź lub wybierz wartość w polu **Profil amortyzacji**.

    * Profil amortyzacji alternatywnej jest również nazywany alternatywną metodą amortyzacji. Propozycja amortyzacji zostanie przełączona na ten profil, gdy profil alternatywny wyliczy kwotę amortyzacji równą lub większą kwocie z domyślnego profilu amortyzacji.
    * Profil Amortyzacja dodatkowa będzie używany na potrzeby dodatkowej amortyzacji składnika aktywów w nadzwyczajnych okolicznościach. Na przykład może to służy do zarejestrowania amortyzacji powstałej w wyniku klęski żywiołowej.
    * Jeśli wybierzesz opcję **Tworzenie korekt amortyzacji przy korektach podstawy**, korekty amortyzacji będą tworzone automatycznie po aktualizacji wartości środka trwałego. W przeciwnym razie zaktualizowana wartość środka trwałego będzie mieć wpływ tylko na przyszłe obliczenia amortyzacji.

7. Ustaw opcję **Tworzenie korekt amortyzacji przy korektach podstawy** na **Tak**.

    * Domyślnie transakcje księgi środków trwałych są księgowane w księdze głównej. Można jednak wyłączyć księgowanie pozycji księgi w księdze głównej, ustawiając opcję **Księguj w księdze głównej** na **Nie**. Księgi, które nie są księgowane w księdze głównej, są zazwyczaj używane na potrzeby sprawozdawczości podatkowej. Ta opcja zapewnia większą elastyczność umożliwiającą usuwanie historycznych transakcji z księgi środków trwałych, ponieważ transakcje nie zostały potwierdzone w księdze głównej.
    * Domyślnie pole **Warstwa księgowania** jest ustawiane na wartość **Bieżąca warstwa**, jeśli pozycje księgi są księgowane do księgi głównej, lub **Brak**, jeżeli pozycje nie są księgowane do księgi głównej. Zaktualizuj wartość pola **Warstwa księgowania**, jeśli transakcje tej księgi powinny być księgowanie w innej warstwie.

8. Obliczanie amortyzacji dodatniej.

    * Domyślnie opcja **Obliczanie amortyzacji dodatniej** jest ustawiona na wartość **Nie**. To ustawienie wskazuje, że amortyzacja spowoduje uznanie wybranej księgi środków trwałych. Ponadto opcje **Zezwalaj na wartość księgową netto wyższą niż cena nabycia** i **Zezwalaj na ujemną wartość księgową netto** są jednocześnie ustawione na wartość **Nie**, a ustawienia można zmieniać niezależnie. 
    * Aby obliczać amortyzację dodatnią, ustaw opcję **Obliczanie amortyzacji dodatniej** na **Tak**. To ustawienie wskazuje, że amortyzacja spowoduje obciążenie wybranej księgi środków trwałych. Jeśli opcja **Obliczanie amortyzacji dodatniej** jest ustawiona na **Tak**, opcje **Zezwalaj na wartość księgową netto wyższą niż cena nabycia** i **Zezwalaj na ujemną wartość księgową netto** zostaną automatycznie ustawiona na **Tak** i zablokowane. Ta blokada pomaga zapewnić, że dodatnia amortyzacja będzie stosowana tylko do środków trwałych, które zostały nabyte z ujemną wartością księgową (uznanie). 

10. W polu **Kalendarz** wprowadź lub wybierz wartość.

    W przypadku ksiąg pochodnych transakcje są księgowane do różnych ksiąg w tym samym czasie. Transakcje tworzy się w księdze podstawowej, a podczas księgowania dokładne kopie transakcji są księgowane w księdze pochodnej. Transakcje w księdze pochodnej nie są ponownie obliczane, więc nie można ich stosować jako transakcji amortyzacji.

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Kojarzenie księgi z grupą środków trwałych

1. Wybierz pozycję **Grupy środków trwałych**.
2. W polu **Grupa środków trwałych** wprowadź lub wybierz wartość.
3. W polu **Okres użytkowania** wpisz liczbę.

    * Okresy amortyzacji są obliczane po wprowadzeniu okresu użytkowania środka trwałego.
    * Konwencja amortyzacji może zostać ustawiona zgodnie z wymogami dla celów podatkowych.
    * W przypadku środków trwałych skojarzonych z wynajmami wartość w polu **Okres użytkowania** jest zastępowana przez okres wynajmu z księgi środków trwałych lub okres użyteczności środka trwałego, zależnie od tego, który okres jest krótszy. Jeśli opcję **Przeniesienie własności** ustawiono na **Tak** dla księgi wynajmu, wartość w polu **Okres użyteczności** zawsze będzie okresem użyteczności środka trwałego.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
