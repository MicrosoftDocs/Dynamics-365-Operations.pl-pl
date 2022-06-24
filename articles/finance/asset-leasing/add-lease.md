---
title: Dodaj lub kopiuj wynajmy (podgląd)
description: W tym artykule opisano sposób tworzenia nowego wynajmu przez wprowadzenie informacji jego dotyczących w Wynajem składnika majątku lub przez skopiowanie informacji z istniejącego wynajmu.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 798ab3ece45ee6f21694a364cfb7a4ff14a9c8aa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880940"
---
# <a name="add-or-copy-leases-preview"></a>Dodaj lub kopiuj wynajmy (podgląd)

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak utworzyć wynajem od podstaw w Wynajem składnika majątku, a także jak utworzyć wynajem, kopiując istniejący wynajem. Proces tworzenia wynajmu od podstaw obejmuje wprowadzenie informacji dotyczących nowego wynajmu, a następnie utworzenie harmonogramu wynajmu. Po skonfigurowaniu co najmniej jednego wynajmu może okazać się łatwiejsze skopiowanie informacji z istniejącego wynajmu, a następnie edytowanie tych informacji w razie konieczności utworzenia nowego wynajmu.

## <a name="create-a-lease"></a>Tworzenie wynajmu

Aby utworzyć wynajem w Wynajem składnika majątku, należy wykonać następujące czynności.

1. Na stronie **Podsumowanie wynajmu**, w okienku akcji, wybierz **Nowy**.
2. Wpisz informacje o wynajmie. Wymagane pola mają czerwone obramowanie.

Data początkowa opłaty z tytułu wynajmu nie może być wcześniejsza niż data rozpoczęcia wynajmu. W przypadku wprowadzenia daty rozpoczęcia opłaty z tytułu wynajmu, która jest wcześniejsza niż data początkowa wynajmu, zostanie wyświetlony komunikat o błędzie.

Domyślnie w opcji **Kwota płatności za podział** na skróconej karcie **Ogólne** strony **szczegółów dzierżawy** jest ustawiona wartość **Nie**, jeśli opcja **Zezwól na podział płatności** na stronie **Parametry dzierżawy środków trwałych** jest ustawiona wartość **Tak**. 

Jeśli opcja **Kwota płatności za podział** ma wartość **Tak**, pole **Kwota płatności** na skróconej karcie **Wiersze harmonogramu płatności** jest zablokowane. Zostanie ona ustawiona jako suma kwot płatności wprowadzonych później w katalogu **podziału kwot płatności**.

Wybierz **podział kwoty płatności**, aby otworzyć stronę, na której można dodać typy płatności dla pozycji. Przycisk **Dodaj sumy do kwoty płatności** spowoduje przeniesienie sum do pola **Kwota płatności**.

> [!NOTE]
> Jeśli dodasz kwotę płatności dla pozycji, a następnie wybierzesz klawisz **Esc**, wprowadzone kwoty nie zostaną dodane do pola **Kwota płatności** na skróconej karcie **Wiersze harmonogramu płatności**. Zostaną one natomiast zapisane w oknie dialogowym **Podział kwoty płatności**. Jeśli chcesz, aby w oknie dialogowym była pokazywana łączna kwota, wybierz kolumnę **Kwota**, wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy), a następnie wybierz pozycję **Suma dla tej kolumny**. 

Przycisk **Kopiuj wiersz** spowoduje skopiowanie podziału płatności dla pozycji.

## <a name="create-a-lease-schedule"></a>Tworzenie harmonogramu wynajmu

Po zakończeniu wprowadzania informacji dotyczących wynajmu należy wykonać poniższe kroki w celu utworzenia harmonogramu wynajmu.

> [!NOTE]
> Wymiary finansowe mogą się zmieniać w zależności od niestandardowych wymiarów finansowych.

1. Wybierz opcję **Utwórz harmonogramy**, aby wygenerować księgi wynajmu. Księgi wynajmu obejmują harmonogramy wydatków, amortyzacji i płatności.
2. Aby uzyskać dostęp do ksiąg wynajmu i wyświetlić nowo utworzone harmonogramy, wybierz kartę **Księgi**.

    Strona **Szczegóły księgi** pokazuje, w jaki sposób wynajem jest księgowany w przypisanych do niego księgach. W tym miejscu można przejrzeć harmonogramy wynajmu.

    Harmonogram płatności zawiera dane wejściowe z karty **Wiersze harmonogramu płatności** na stronie **Dodaj wynajem**. Nadal można zmienić każdą kwotę płatności i opłaty zmienne. Zobowiązanie z tytułu wynajmu jest obliczane na podstawie zmodyfikowanego harmonogramu płatności.

    > [!NOTE]
    > Data rozpoczęcia opłaty z tytułu wynajmu musi być taka sama jak data rozpoczęcia wynajmu lub od niej późniejsza. Zostanie wyświetlony komunikat o błędzie, jeśli data rozpoczęcia opłaty z tytułu wynajmu będzie wcześniejsza niż data rozpoczęcia wynajmu. 

4. Po przejrzeniu harmonogramu płatności wybierz pozycję **Potwierdź harmonogram**. Po potwierdzeniu harmonogramu wynajem nie będzie już dostępny do edycji.

    > [!NOTE]
    > System automatycznie obliczy okres wynajmu na podstawie wierszy harmonogramu płatności na stronie **Dodaj wynajem**.
    >
    > Aby obliczyć okres wynajmu w miesiącach, system wyszukuje różnicę między datą początkową a datą końcową określonego wiersza harmonogramu płatności. Następnie następuje przejście do następnego wiersza harmonogramu płatności i ponowne obliczenie różnicy. Na koniec system sumuje wszystkie kwoty, aby określić okres wynajmu w miesiącach.

5. Aby wyświetlić obliczone okresowe koszty odsetek, otwórz stronę **Harmonogram amortyzacji zobowiązań**. Aby wyświetlić obliczoną amortyzację liniową, otwórz stronę **Harmonogram amortyzacji składników majątku**.
6. Po przejrzeniu obliczonej kwoty można utworzyć wpis w arkuszu początkowego rozpoznania na stronie **Początkowe rozpoznawanie**. Zostanie wyświetlony komunikat informujący o utworzeniu arkusza.

    > [!NOTE]
    > Wpis w arkuszu nie jest publikowany w księdze głównej, dopóki nie zostanie zaksięgowany ręcznie.

7. Aby przejrzeć proponowany wpis początkowego rozpoznania przed zaksięgowaniem go, wybierz **Arkusze wynajmu składnika majątku**.

    > [!NOTE]
    > Nie można ręcznie utworzyć Arkusza wynajmu składnika majątku. Jest on tworzony automatycznie podczas tworzenia harmonogramów wynajmu.

8. Aby zaksięgować wpis w arkuszu początkowego rozpoznania po jego przejrzeniu, należy wybrać opcję **Zaksięguj** w celu opublikowania składnika majątku z PDU i zobowiązania z tytułu wynajmu w księdze głównej.

## <a name="copy-a-lease"></a>Kopiowanie wynajmu

Wynajem składników majątku umożliwia kopiowanie szczegółów wynajmu w celu utworzenia nowego wynajmu mającego takie same informacje. Następnie można zmienić pola wynajmu przed utworzeniem harmonogramów dla kopiowanego wynajmu.

1. Na stronie **Podsumowanie wynajmu** wybierz wynajem do skopiowania, a następnie w okienku akcji wybierz opcję **Kopiuj wynajem**.

    > [!NOTE]
    > Jeśli parametr **Ręczny** jest wyłączony dla sekwencji numerów dla identyfikatorów wynajmów, kolejny numer w sekwencji jest automatycznie generowany jako identyfikator wynajmu dla kopiowanego wynajmu. Jeśli parametr **Ręczny** jest włączony, zostanie wyświetlony komunikat z monitem o wprowadzenie identyfikatora wynajmu, zanim będzie można kontynuować kopiowanie wynajmu.

2. Wybierz opcję **Kopiuj**. Szczegóły wynajmu z wybranego wynajmu są kopiowane do nowego wynajmu. Szczegóły nowego wynajmu można zmodyfikować przed jego zapisaniem i utworzeniem harmonogramów wynajmu.

## <a name="asset-leasing-journal"></a>Arkusz wynajmu składnika majątku

Wszystkie wpisy w arkuszu, które są tworzone w module Wynajem składnika majątku, są zawarte w arkuszu wynajmu składnika majątku. Na stronie **Arkusz wynajmu składnika majątku** (**Wynajem składnika majątku \> Wpisy w arkuszu \> Arkusz wynajmu składnika majątku**) można filtrować według stanu zaksięgowania, wyświetlać określone wpisy w arkuszu i załączniki oraz księgować niezaksięgowane wpisy w arkuszu.

> [!NOTE]
> Nie można ręcznie utworzyć Arkusza wynajmu składnika majątku. Jest on tworzony automatycznie podczas tworzenia harmonogramów wynajmu.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
