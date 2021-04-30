---
title: Liczba ksiąg na arkusz
description: W tym temacie opisano relacje między arkuszami i księgami składników majątku występujące podczas tworzenia propozycji nabycia lub amortyzacji środka trwałego za pomocą zadania wsadowego. Można zdefiniować maksymalną liczbę ksiąg, które są uwzględniane w każdym nabyciu i amortyzacji.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-19
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fb2a25d9e2ffc26f0a37a09cdf3e28a7ca4b84bc
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892414"
---
# <a name="number-of-books-per-journal"></a>Liczba ksiąg na arkusz

[!include [banner](../includes/banner.md)]

W tym temacie opisano relacje między arkuszami i księgami składników majątku występujące podczas tworzenia propozycji nabycia lub amortyzacji środka trwałego za pomocą zadania wsadowego. Można zdefiniować maksymalną liczbę ksiąg, które są uwzględniane w każdym nabyciu i amortyzacji, używając pól znajdujących się w sekcji **Liczba ksiąg na arkusz** na karcie **Ogólne** na stronie **Parametry środków trwałych** (**Środki trwałe \> Ustawienia \> Parametry środków trwałych**). Te pola umożliwiają rozdzielenie wszystkich używanych ksiąg składników majątku z podziałem na arkusze nabycia i arkusze amortyzacji.

W przypadku propozycji nabycia wartość domyślna wynosi co najmniej 10 000 ksiąg. W przypadku propozycji amortyzacji wartość domyślna wynosi co najmniej 2000 ksiąg.

Jeśli na przykład istnieje 4000 środków trwałych, a z każdym środkiem trwałym są skojarzone dwie księgi, jedna księga zostanie zaksięgowana w bieżącej warstwie, a druga księga zostanie zaksięgowana w warstwie podatkowej. Jeśli w wyniku przetwarzania wsadowego zostanie nabytych 4000 środków trwałych, to zadanie wsadowe, które utworzyło jeden arkusz nabycia środków trwałych, będzie zawierało 4000 ksiąg składników majątku.

> [!NOTE]
> Utworzony arkusz będzie używany aż do zakończenia zadania wsadowego.
>
> Powstałe pochodne księgi nie są wliczane do maksymalnej dozwolonej liczby ksiąg na arkusz.

Przetwarzania wsadowego można użyć do wykonania amortyzacji dla tego samego zbioru nabytych środków trwałych. Na przykład zadanie wsadowe tworzy dwa arkusze amortyzacji, z których każdy zawiera 2000 ksiąg składników majątku. Pierwszy arkusz będzie zawierał księgi skojarzone ze środkami trwałymi o numerach od 1 do 2000. Drugi arkusz będzie następnie zawierał księgi skojarzone ze środkami trwałymi o numerach od 2001 do 4000.

Zadanie przetwarzania wsadowego wyklucza zamknięte księgi. Na przykład w zadaniu wsadowym amortyzacji 10 z pierwszych 2000 ksiąg jest zamkniętych. W tym przypadku pierwszy arkusz będzie zawierał księgi skojarzone ze środkami trwałymi o numerach od 1 do 2011. Drugi arkusz będzie następnie zawierał księgi skojarzone ze środkami trwałymi o numerach od 2,012 do 4,000.

> [!NOTE]
> Jeśli masz identyfikatory środków trwałych z różnymi separatorami (takimi jak - lub /) i tworzysz transakcje środków trwałych w zadaniach wsadowych, musisz uruchomić osobne zadanie wsadowe dla każdego typu separatora. System nie może przetwarzać różnych separatorów w ramach tego samego zadania wsadowego.

Limit liczby ksiąg jest stosowany, jeśli w tym samym arkuszu nie istnieją zduplikowane identyfikatory składników majątku. Jeśli jednak identyfikator składnika majątku jest taki sam, jak identyfikator księgi, liczba ksiąg na arkusz może zostać przekroczona w celu utrzymania identyfikatora składnika majątku w tym samym arkuszu.

Na przykład istnieje 5001 identyfikatory środków trwałych, z każdym identyfikatorem środka trwałego są powiązane trzy księgi, a każda księga składników majątku jest księgowana w tej samej warstwie księgowania. Wykonujesz amortyzacja przez trzy kolejne miesiące bez podsumowania.  Arkusz amortyzacji zostanie utworzony za pomocą zadania wsadowego, a system utworzy siedem arkuszy, które mają 667 identyfikatorów składników majątku, i trzy księgi dla każdego identyfikatora środka trwałego. Ogółem powstanie 2001 ksiąg. W związku z tym w ciągu trzech miesięcy na potrzeby zachowania tych samych identyfikatorów składników majątku w tym samym arkuszu powstaną 6003 wiersze arkuszy. System utworzy także jeden arkusz, który ma 332 identyfikatory środków trwałych, i trzy księgi dla każdego identyfikatora środka trwałego. W ciągu trzech miesięcy powstanie 2988 wierszy.

> [!NOTE] 
> Jeśli parametr **Podsumuj amortyzację** jest włączony podczas tworzenia propozycji amortyzacji, wartość w polu **Liczba ksiąg na arkusz** — propozycja amortyzacji nie ma żadnego wpływu. W tym przypadku liczba ksiąg na arkusz wynosi 6000, co jest limitem zdefiniowanym wewnętrznie.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
