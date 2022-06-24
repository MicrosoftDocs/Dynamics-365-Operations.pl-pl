---
title: Obliczanie TDS na fakturach ze strony Faktura niezależna
description: W tym artykule wyjaśniono, jak obliczyć podatek odliczany u źródła (TDS) na fakturach przy użyciu strony Faktura niezależna.
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
ms.openlocfilehash: b1cf0f5366315884e75a6fee25b88a3aac7d62de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856619"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a>Obliczanie TDS na fakturach ze strony Faktura niezależna

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak obliczyć podatek odliczany u źródła (TDS) na fakturach przy użyciu strony **Faktura niezależna**.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Faktury \> Wszystkie faktury niezależne**.

    [![Strona faktury niezależnej.](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)

2. Wybierz **Nowy**, aby utworzyć fakturę niezależną i wprowadź wymagane szczegóły.
3. Na karcie **Faktura** w sekcji **Grupa potrąconej zaliczki na podatek** pole **Charakter grupy oszacowań** pokazuje charakter kategorii produktów ocenianych dostawcy lub odbiorcy.
4. W polu **Grupa TDS** przejrzyj lub zmień domyślną grupę TDS zdefiniowaną dla odbiorcy.

    > [!NOTE]
    > Po wybraniu wartości w polu **grupy TDS** pole **grupy TCS** staje się niedostępne. Identyfikator TDS jest obliczany tylko wtedy, gdy opcja **Oblicz potrącanie zaliczki** na podatek ma wartość **Tak** dla odbiorcy na stronie **Wszyscy odbiorcy**.

5. Na karcie **Informacje podatkowe**, w sekcji **Informacje o firmie**, w polu **Nazwa** wybierz nazwę firmy dla alternatywnego adresu, który został skonfigurowany dla firmy.

    W sekcji **Potrącona zaliczka na podatek** w polu **Numer konta podatkowego (TAN)** jest uwzględniany numer konta podatkowego (TAN) wybranej firmy.

6. Na karcie **Wiersze faktury** utwórz wiersze faktury i wprowadź wymagane szczegóły.

    W sekcji **Grupa potrąconej zaliczki** na podatek pole  **Numer konta podatkowego (TAN)** zawiera kod TAN, a pole **Grupa TDS** zawiera grupę TDS.

7. Wybierz przycisk **Potrącona zaliczka na podatek**, aby otworzyć stronę **Tymczasowe transakcje potrącenia zaliczki na podatek**. W górnej części tej strony są następujące pola:

    - **Łączna kwota potrąconej zaliczki na podatek** — łączna kwota TDS obliczona dla transakcji dla grupy TDS.
    - **Wartość** — łączna wartość procentowa użyta do obliczenia TDS dla transakcji. Łączny procent jest oparty na formule zdefiniowanej dla kodów podatków TDS i dołączonej do grupy TDS.
    - **Skorygowana łączna kwota potrąconej zaliczki na podatek** — łączna skorygowana kwota TDS dla wszystkich kodów podatków w grupie TDS.
    - **TDS** — zaznaczone pole wyboru wskazuje, że grupa TDS jest dołączona do transakcji.

    Pola na kartach **Przegląd**, **Ogólne** i **Korekta** pokazują obliczoną kwotę TDS oraz szczegóły skorygowanej kwoty TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.

8. Wybierz opcję **Próg**, aby otworzyć stronę **Progu**, na której możesz przejrzeć limit progowy zdefiniowany dla składnika podatku TDS dołączonego do określonego kodu podatku TDS.
9. Po wybraniu opcji **Projektant formuł** zostanie otwarta strona **Projektant formuł**, na której można przejrzeć formułę zdefiniowaną dla określonego kodu podatku TDS.
10. Księguj fakturę niezależną. Kwota TDS obliczona dla faktury niezależnej jest księgowana na koncie należności zdefiniowanym dla każdego kodu podatku potrącanego u źródła w grupie TDS. Konta należności dla kodów podatku TDS są definiowane na stronie **Kody potrąconych zaliczek na podatek**.
11. Wybierz przycisk **Zaksięgowana potrącona zaliczka na podatek**, aby otworzyć stronę **transakcje potrącenia zaliczki**. **Wartość** pokazuje łączną wartość procentowa użyta do obliczenia TDS dla transakcji.

    W polach na kartach **Przegląd**, **Ogólne** i **Kwota** są wyświetlane kwoty TDS, które zostały obliczone w wierszach faktury.

12. Przejrzyj informacje o obliczaniu TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.
