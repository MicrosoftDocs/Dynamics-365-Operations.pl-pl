---
title: Ustaw okresy rozliczenia podatku u źródła dla typu podatku TDS
description: W tym temacie wyjaśniono, jak skonfigurować okresy rozliczeniowe dla okresów rozliczenia podatku odliczonego u źródła (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 3fe6a21636b3d875ac1fd56370b8a5a848ac0256
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407362"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a>Ustaw okresy rozliczenia podatku u źródła dla typu podatku TDS

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować okresy rozliczeniowe dla okresów rozliczenia podatku odliczonego u źródła (TDS).

1. Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Potrącona zaliczka na podatek \> Okresy rozliczenia podatku u źródła**.

    [![Strona Okresy rozliczenia podatku u źródła.](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)

2. W polu **Typ podatku** wybierz **TDS**, aby ustawić okresy rozliczenia podatku u źródła dla typu podatku potrącanego u źródła.
3. Wybierz **Nowy**, aby utworzyć wiersz.
4. W polu **Okres rozliczeniowy** wprowadź nazwę okresu rozliczeniowego TDS.
5. W polu **Opis wprowadź** opis.
6. W polu **Potrącona zaliczka na podatek** wybierz urząd TDS, dla którym jest definiowany okres rozliczeniowy TDS.
7. Na skróconej karcie **Ogólne** w polu **Interwał okresu** wybierz typ interwału okresu dla okresu rozliczeniowego TDS.
8. W polu **Liczba jednostek** określ liczbę jednostek dla typu interwału okresu.
9. Na skróconej karcie **Okresy** w polu **Od dnia** wybierz datę rozpoczęcia okresu rozliczeniowego TDS. W polu **Do dnia** wybierz datę zakończenia.
10. Aby utworzyć kolejny okres rozliczeniowy TDS dla istniejącego okresu na podstawie interwału okresu i jednostek okresu, wybierz opcję **Nowy okres**.
11. Aby wyświetlić szczegóły okresowego rozliczania TDS uruchomionego dla określonego okresu rozliczeniowego, wybierz opcję **Płatności potrąconej zaliczki na podatek**, aby otworzyć stronę **Płatność potrąconej zaliczki na podatek**.

    > [!NOTE]
    > Aby uruchomić okresowy proces rozliczania TDS, przejdź do **Księga główna \> Okresowe \> Potrącona zaliczka na podatek \> Płatność zaliczki na podatek**.

    [![Strona płatności potrąconej zaliczki na podatek.](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)

12. Zamknij stronę.
