---
title: Skonfiguruj składniki podatku dla typu podatku TDS
description: W tym artykule wyjaśniono, jak skonfigurować składniki podatku u źródła dla typu podatku odliczanego u źródła (TDS). Opisano w nim także sposób definiowania limitu progowego używanego do obliczania identyfikatorów TDS dla każdego składnika TDS.
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
ms.openlocfilehash: df2eb10ce9e372bb1e984f6ae1a2e889bbd90ad0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871165"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a>Skonfiguruj składniki podatku dla typu podatku TDS

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak skonfigurować składniki podatku u źródła dla typu podatku odliczanego u źródła (TDS). Składniki TDS to TDS, dopłaty, PE-Cess i SHE Cess. Opisano w artykule także sposób definiowania limitu progowego używanego do obliczania identyfikatorów TDS dla każdego składnika TDS. Ponadto można zdefiniować próg wyjątku, który służy do obliczania identyfikatorów TDS dla każdego składnika TDS.

Wykonaj poniższe czynności, aby skonfigurować składniki TDS.

1. Wybierz kolejno opcje **Podatek \> Konfiguracja \> Potrącona zaliczka na podatek \> Składniki potrąconej zaliczki**.

    [![Strona składników podatku u źródła.](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)

2. W polu **Typ podatku** wybierz **TDS**, aby skonfigurować składniki potrąconej zaliczki na podatek dla tego typu podatku TDS.
3. W okienku akcji wybierz opcję **Nowy**, aby utworzyć wiersz.
4. W polu **Składniki potrąconej zaliczki na podatek** wprowadź nazwę składników TDS.
5. W polu **Grupa składników potrąconej zaliczki na podatek** wybierz grupę składników potrąconej zaliczki na podatek TDS, do której ma być dołączany składnik TDS.
6. Na skróconej karcie **Ogólne** w polu **Opis** wpisz opis składnika TDS.
7. W okienku akcji wybierz pozycję **Próg**, aby otworzyć stronę **Progu**, aby można było zdefiniować próg używany do obliczania TDS dla składnika TDS.
8. Za pomocą pól **Od dnia** i **Do dnia** zdefiniuj okres, do których ma zastosowanie próg.
9. Na skróconej karcie **Ogólne** w polu **Próg** wprowadź kwotę progu używaną do obliczania TDS dla składnika TDS. Podatek zostanie potrącony w źródle tylko wtedy, gdy skumulowana kwota faktury przekroczy próg.

    Na przykład, jeśli kwota progowa wynosi 10 000, identyfikator TDS jest obliczany po tym, jak kwota skumulowanej faktury przekroczy 10 000 (czyli jeśli wynosi 10 001 lub więcej).

10. W polu **Próg wyjątku** wprowadź kwotę progu wyjątku, która jest używana do obliczenia TDS dla składnika TDS. Podatek w wierszu faktury zostanie potrącony u źródła tylko wtedy, gdy kwota przekroczy próg wyjątku.

    Na przykład, jeśli kwota progu wyjątku wynosi 5000, identyfikator TDS jest obliczany dla określonego wiersza faktury, jeśli kwota wiersza faktury przekracza 5000 (innymi słowy, jeśli wynosi 5001 lub więcej).

    [![Strona progu.](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)

    > [!NOTE]
    > Kwota progu wyjątku musi być mniejsza od kwoty progu lub jej równa.
    >
    > Podatek jest potrącana dla transakcji, jeśli kwota transakcji przekracza próg wyjątku, nawet jeśli skumulowana kwota faktury nie przekracza progu określonego w polu **Próg**.

11. Zamknij stronę **Próg**, aby powrócić do strony **Składniki potrąconej zaliczki na podatek**.
12. W okienku akcji wybierz opcję **Kopiuj**, aby otworzyć okno dialogowe **Kopiowanie składników potrąconych zaliczek na podatek**, aby można było skopiować składniki TDS, które zostały ustawione dla jednej grupy składników TDS do innej grupy składników TDS.
13. W polu **Od** wybierz grupę składników TDS, z których mają być skopiowane składniki TDS. W polu **Do** wybierz grupę składników zaliczki, do których mają być skopiowane składniki TDS.

    > [!NOTE]
    > Typowe składniki TDS dołączone do obu grup składników TDS nie są kopiowane.

14. Wybierz **przycisk OK**, aby skopiować i utworzyć składniki TDS dla innej grupy składników TDS na stronie **Składniki potrąconej zaliczki na podatek**.

    [![Okno dialogowe kopiowania składników potrąconych zaliczek na podatek.](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)

15. Zamknij stronę.
