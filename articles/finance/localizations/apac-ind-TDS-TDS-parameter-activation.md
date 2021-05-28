---
title: Ustaw parametry TDS
description: W tym temacie wyjaśniono, jak skonfigurować parametry uaktywnienia funkcji potrącenia podatku w źródle (TDS) w określonych transakcjach. Jest to krok niezbędny, aby użyć funkcji Podatek potrącony w źródłowym TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: dda276b7d634317aae26728f7d9f51af9ccfb896
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023506"
---
# <a name="set-the-tds-parameters"></a>Ustaw parametry TDS

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować parametry uaktywnienia funkcji potrącenia podatku w źródle (TDS) w określonych transakcjach. Jest to krok niezbędny, aby użyć funkcji Podatek potrącony w źródłowym TDS.

1. Przejdź do pozycji **Księga główna \> Ustawienia księgi \> Parametry księgi głównej**.
2. Na karcie **Podatki bezpośrednie**, w sekcji **Podatek potrącony w źródle** ustaw opcję **Aktywuj TDS** na wartość **Tak**, aby uaktywnić funkcję TDS, oraz strony i pola, które są dla nich używane.
3. Ustaw dla opcji **Faktura** wartość **Tak**, aby uaktywnić pola używane do obliczania i odejmowania identyfikatorów TDS na poziomie faktury.
4. Ustaw dla opcji **Płatność** wartość **Tak**, aby uaktywnić pola używane do obliczania i odejmowania identyfikatorów TDS na poziomie płatności.

    [![Karta Podatki bezpośrednie](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. Na karcie **Sekwencje numerów** znajdź wiersz, w którym w polu **Odwołanie** ustawiono **płatność potrąconej zaliczki na podatek**. W wierszu **kod sekwencji numerów** wybierz kod każdej sekwencji numerów kodu. Kod sekwencji numerów służy do generowania numerów załączników dla okresowego procesu rozliczania TDS.

    > [!NOTE]
    > Aby uruchomić okresowy proces rozliczania TDS, przejdź do **Podatek \> Deklaracje \> Potrącona zaliczka na podatek \> Płatność zaliczki na podatek**.

    [![Karta Sekwencje numerów](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. Zamknij stronę.
