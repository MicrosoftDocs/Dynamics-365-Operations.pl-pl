---
title: Skonfiguruj kody podatku u źródła dla typu podatku TDS
description: W tym temacie wyjaśniono, jak skonfigurować kody podatków dla podatku odliczanego u źródła (TDS).
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
ms.openlocfilehash: ced5902b5a2e822f84a40da8149bc319c94973ba
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724735"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>Skonfiguruj kody podatku u źródła dla typu podatku TDS

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować kody podatków dla podatku odliczanego u źródła (TDS).

1. Wybierz kolejno opcje **Podatek \> I Podatki pośrednie \> Potrącona zaliczka na podatek \> Kody potrąconych zaliczek na podatek**.

    [![Strona Kody potrąconych zaliczek na podatek.](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)

2. Wybierz **Nowy** na okienku akcji, aby utworzyć kod podatku u źródła dla podatku u źródła i wprowadź wymagane szczegóły.
3. Na skróconej karcie **Ogólne** w polu **Typ podatku** wybierz kod **TDS**, aby sklasyfikować kod podatku jako kod podatku TDS.
4. W polu **Okres rozliczeniowy** wybierz okres rozliczeniowy podatku potrącanego u źródła dla kodu podatku potrącanego u źródła.
5. W polu **Konto główne** wybierz konto księgowe, na które ma zostać zaksięgowana kwota TDS.
6. W polu **Konto należności** wybierz konto należności, na które ma być księgowana kwota TDS potrącona z transakcji sprzedaży.

    W polu **Źródło** jest automatycznie ustawiana wartość **Procent od kwoty brutto** i nie można zmienić tej wartości.

    > [!NOTE]
    > Nie można ustawić **wartości procentowej kwoty netto** dla kodów podatków typu TDS.

7. W polu **Składnik zaliczki na podatek** wybierz składnik podatku potrącanego u źródła dla kodu podatku potrącanego u źródła.
8. W okienku akcji wybierz opcję **Wartości**, aby otworzyć stronę **Wartości podatku u źródła**.
9. Wybierz datę początkową wartości TDS w polu **Od dnia**. W polu **Do dnia** wprowadź datę zakończenia.

    > [!NOTE]
    > Pola **Minimalny limit**, **Górny limit** i **Wyklucz procent** nie są dostępne dla kodów podatków typu TDS.

10. W polu **Wartość** wprowadź wartość procentową podatku potrącanego u źródła dla kodu podatku potrącanego u źródła.
11. Zamknij stronę **Wartości podatku u źródła**, aby powrócić do strony **Kody potrąconej zaliczki na podatek**.

    > [!NOTE]
    > Przycisk **Limity** na stronie **Kody potrąconych zaliczek** na podatek jest niedostępny dla kodów podatków typu TDS.

12. Zamknij stronę.
