---
title: Konfigurowanie harmonogramów płatności z alokacją podatku TDS
description: W tym temacie wyjaśniono, jak skonfigurować harmonogramy płatności z alokacją podatku odliczonego u źródła (TDS).
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
ms.openlocfilehash: 27f6750dd91a211ad12a1bd5d9c4ab9a2e1e4a79
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358417"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a>Konfigurowanie harmonogramów płatności z alokacją podatku TDS

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować harmonogramy płatności z alokacją podatku odliczonego u źródła (TDS).

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia płatności \> Harmonogramy płatności**.

    [![Strona Harmonogramy płatności.](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)

2. Wybierz **Nowy** na okienku akcji, aby utworzyć harmonogram opłat za płatność i wprowadź wymagane szczegóły.
3. W polu **Alokacja** wybierz metodę alokacji płatności dla harmonogramu płatności:

    - Razem
    - Stała kwota
    - Stała ilość
    - Określone

    Pole **Alokacja potrąconej zaliczki** na podatek zawiera metodę alokacji TDS dla harmonogramu płatności. Jeśli zostanie zaznaczyna wartość **Suma** w polu **Alokacja** zw polu **Alokacja potrąconej zaliczki na podatek** zostanie automatycznie ustawiona wartość **Suma**. W przypadku wybrania opcji **Stała kwota**, **Stała ilość** lub **Określona** w polu **Alokacja** pole **Alokacja potrąconej zaliczki na podatek** jest automatycznie ustawiane na wartość **Proporcjonalnie**.

    > [!NOTE]
    > Jeśli w polu **Alokacja potrąconej zaliczki na podatek** jest ustawiona wartość **Suma**, raty płatności są obliczane na podstawie kwoty brutto, która zawiera kwotę TDS. Jeśli w polu **Alokacja potrąconej zaliczki na podatek** jest ustawiona wartość **Proporcjonalnie**, raty płatności są naliczane na podstawie kwoty faktury netto po potrąceniu kwoty TDS.

4. Wprowadź inne wymagane szczegóły, a następnie zamknij stronę.
