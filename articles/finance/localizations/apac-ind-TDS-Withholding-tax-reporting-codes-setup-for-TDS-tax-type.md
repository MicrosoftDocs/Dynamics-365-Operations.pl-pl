---
title: Skonfiguruj kody raportowania podatku u źródła dla typu podatku TDS
description: Kody raportowania potrąconych zaliczek na podatek są używane do generowania sprawozdań z formularzy 26Q i 27Q dla podatku potrąconego w źródle (TDS). W tym temacie opisano sposób skonfigurowania kroków kodów raportowania potrąconych zaliczek na podatek, aby można było skonfigurować kody raportowania TDS.
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
ms.openlocfilehash: 6775d9d6d917e617e0d371914f0b8b4958c69c54
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407997"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a>Skonfiguruj kody raportowania podatku u źródła dla typu podatku TDS

[!include [banner](../includes/banner.md)]

Kody raportowania potrąconych zaliczek na podatek są używane do generowania sprawozdań z formularzy 26Q i 27Q dla podatku potrąconego w źródle (TDS). W tym temacie opisano sposób skonfigurowania kroków kodów raportowania potrąconych zaliczek na podatek, aby można było skonfigurować kody raportowania TDS.

1. Wybierz kolejno opcje **Podatek \> Konfiguracja \> Potrącona zaliczka na podatek \> Kody raportowania potrąconych zaliczek na podatek**.

    [![Strona kodów raportowania potrąconych zaliczek na podatek.](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)

2. W polu **Typ podatku** wybierz **TDS**, aby zdefiniować kody raportowania podatku u źródła dla typu podatku potrącanego u źródła.
3. W polu **Składnik potrąconej zaliczki na podatek** wybierz składnik TDS, dla których ma być definiowany kod raportowania potrąconej zaliczki na podatek. Pole **Grupa składników potrąconej zaliczki na podatek** zawiera grupę składników TDS zdefiniowaną dla definiowanego składnika TDS.

    Pole **Kod sekcji** na skróconej karcie **Ogólne** zawiera kod sekcji dołączony do grupy składników TDS.

4. Na skróconej karcie **Ogólne** w polu **Kod raportowania** wybierz kod raportowania TDS:

    - TDS
    - TCS
    - Dopłata
    - PE\_Cess
    - SHE\_Cess

5. Zamknij stronę.
