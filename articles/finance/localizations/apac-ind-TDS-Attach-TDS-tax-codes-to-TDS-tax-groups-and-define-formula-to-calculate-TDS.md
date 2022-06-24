---
title: Umożliwia dołączanie kodów podatków TDS do grup podatków TDS i definiowanie formuły obliczania TDS
description: W tym artykule wyjaśniono, jak skonfigurować grupy podatków Potrącone w źródle (TDS) i dołączyć kody podatków TDS do grup podatków TDS. Aby obliczyć TDS dla grupy podatków TDS, należy zdefiniować formułę dla dołączonych do niej kodów podatków TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3607e44bdcf7a32b156e6b4639ef907aa923cadc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853322"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a>Umożliwia dołączanie kodów podatków TDS do grup podatków TDS i definiowanie formuły obliczania TDS

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak skonfigurować grupy podatków Potrącone w źródle (TDS) i dołączyć kody podatków TDS do grup podatków TDS. Aby obliczyć TDS dla grupy podatków TDS, należy zdefiniować formułę dla dołączonych do niej kodów podatków TDS.

Aby skonfigurować grupę podatków TDS, dołączyć kody podatków TDS i zdefiniować formułę obliczania tych identyfikatorów.

1. Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Potrącona zaliczka na podatek \> Grupy potrąconych zaliczek na podatek**.

    [![Strona Grupy potrąconych zaliczek na podatek.](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)

2. Wybierz **Nowy** na okienku akcji, aby utworzyć grupę podatku u źródła dla podatku u źródła i wprowadź wymagane szczegóły.
3. W polu **Typ podatku** zaznacz opcję **TDS**.
4. Na skróconej karcie **Ustawienia** wybierz **Dodaj**, aby utworzyć nowy wiersz.
5. W polu **Kod potrąconej zaliczki na podatek** wybierz kod podatku TDS dla grupy podatkowej TDS. Pole **Nazwa potrąconej zaliczki na podatek** zawiera nazwę kodu podatku TDS, a pole **Wartość** zawiera wartość.
6. Aby zignorować limit progowy i limit progu wyjątku, który jest zdefiniowany dla składnika podatku TDS dołączonego do kodu podatku TDS w transakcjach TDS, zaznacz pole wyboru **Przeoczenie progu**.
7. Aby zapobiec obliczaniu grupy podatkowej w transakcjach, zaznacz pole wyboru **Zwolnienie**.
8. W okienku akcji wybierz opcję **Projektant**, aby otworzyć projektanta formuł, aby można było zdefiniować formułę obliczania TDS dla grupy podatków TDS. Na stronie **Konstruktor** na karcie **Podatki** są widać kody podatków TDS wybrane dla grupy podatków TDS.

    [![Strona Projektant.](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)

9. Na karcie **Obliczanie** wybierz klawisze **Alt+N**, aby utworzyć wiersz. Pole **identyfikator** zawiera automatycznie wygenerowany identyfikator priorytetu dla obliczania TDS.
10. W polu **Kod podatku** wybierz kod podatku TDS, dla którego ma zostać zdefiniowana formuła. W tym polu są dostępne wszystkie kody podatków TDS wybrane dla grupy podatków TDS.
11. W polu **Podstawa opodatkowania** wybierz podstawę do obliczania TDS:

    - **Kwota brutto** — obliczanie TDS na podstawie kwoty transakcji brutto (to jest kwoty faktury) przy użyciu wyrażenia obliczeń zdefiniowanego dla kodu podatku.
    - **Bez kwoty brutto** — obliczanie TDS na podstawie wyrażenia obliczeń zdefiniowanego dla kodu podatku.

    > [!NOTE]
    > W polu **Podstawa opodatkowania** nie można ustawić wartości **Bez kwoty brutto** dla kodu podatku TDS o identyfikatorze priorytetu **1**.

12. Obliczenie TDS jest oparte na formule zdefiniowanej w polu **Obliczanie wyrażenia** dla każdego kodu podatku dołączonego do grupy podatków TDS. Umożliwia wybranie znaku plus (+), znaku minus (-), znaku mnożenia (\*) lub znaku dzielenia (/) w celu wprowadzenia wyrażenia obliczeń dla wybranego kodu podatku TDS w polu **Obliczanie wyrażenia**.

    > [!NOTE]
    > Nie można zdefiniować wyrażenia obliczeń dla kodu podatku TDS o identyfikatorze priorytetu **1**.

13. Aby zdefiniować wyrażenie obliczeń dla kodu podatku TDS w polu **Obliczanie wyrażenia**, dodaj kody podatków TDS, które są dostępne na karcie **Podatki**. Aby dodać kody podatków TDS w polu **Obliczanie wyrażenia**, można użyć dowolnej z następujących metod:

    - Przeciągnij wymagany kod podatku z karty **Podatki** do pola **Obliczanie wyrażenia**.
    - Kliknij dwukrotnie (lub kliknij dwukrotnie) wymagany kod podatku na karcie **Podatki**.
    - Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) wymagany kod podatku na karcie **Podatki**, a następnie wybierz polecenie **Dodaj kod podatku**.

    > [!NOTE]
    > Wstaw wyrażenie obliczeń przed każdym kodem podatku TDS. Kody podatków TDS dodane do obliczenia wyrażenia są wyświetlane w nawiasach (\[...\]).

14. Aby wyczyścić wyrażenie obliczeń, które jest zdefiniowane dla kodu podatku w polu **Obliczanie wyrażenia**, wybierz przycisk **C**.
15. Aby usunąć rekord na karcie **Obliczanie**, wybierz polecenie **Usuń**.
16. Zamknij stronę.
