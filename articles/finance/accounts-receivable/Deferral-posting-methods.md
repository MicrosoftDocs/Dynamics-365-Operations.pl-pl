---
title: Sposoby księgowania odroczenia
description: W tym artykule opisano różnice między metodami księgowania odroczeń dla przychodów i wydatków w rozliczaniu subskrypcji.
author: JodiChristiansen
ms.date: 6/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: c66ed1c38251140dd798c39797873ceb5f7121a4
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9019101"
---
# <a name="deferral-posting-methods"></a>Sposoby księgowania odroczenia

W tym artykule opisano różnice między metodami księgowania odroczeń dla przychodów i wydatków w rozliczaniu subskrypcji.

Na stronie **Parametry odrodzenia przychodów i wydatków** opcje dla sposobów księgowania odroczeń to **Bilans** i **Zyski i straty**. Przykład w tym artykule pomaga wyjaśniać różnice między tymi dwiema metodami i powodami do wybrania jednego sposobu bądź drugiego.

W metodzie **Bilans** używane są tylko dwa konta. W związku z tym konfiguracja jest prostsza. Sposób **Zyski i straty** posiada dwa dodatkowe konta: **Wstępne rozpoznanie** i **Konto przeciwstawne rozpoznania** dla przychodu, rabatów i kosztów w zależności od typu transakcji. Te konta są ustawiane na stronie **Ustawienia domyślne odroczeń** (**Rozliczanie subskrypcji \> Odroczenia przychodów i wydatków \> Ustawienia**). Chociaż przykład dotyczy przychodu odroczonego, to jednak to samo pojęcie można zastosować do odroczonych rabatów i kosztów.

## <a name="example"></a>Przykład

Faktura sprzedaży 1 jest na kwotę 3000 USD i ma odroczony przychód. W poniższych tabelach przedstawiono dystrybucje po zaksięgowaniu tej faktury sprzedaży.

**Sposób bilansu**

| Typ | Konto | Uznanie | Środki|
|---|---|---|---|
| Uznanie | Rozrachunki z odbiorcami | 3,000.00 | |
| Środki | Odroczony przychód | | 3,000.00 |

**Sposób przychodów i wydatków**

| Typ | Konto | Uznanie | Środki |
|---|---|---|---|
| Uznanie | Rozrachunki z odbiorcami | 3,000.00 | |
| Uznanie | Przesunięcie rozpoznawania przychodów | 3,000.00 | |
| Środki | Odroczony przychód | | 3,000.00 |
| Środki | Początkowe rozpoznawanie przychodu | | 3,000.00 |

Faktura sprzedaży 2 jest na kwotę 2000 USD i nie ma odroczonego przychodu.

| Typ | Konto | Ilość |
|---|---|---|
| Uznanie | Rozrachunki z odbiorcami | 3,000.00 |
| Środki | Przychód | 3,000.00 |

**Sumy metod bilansowych dla połączonych faktur sprzedaży 1 i 2**

| Konto | Uznanie | Środki |
|---|---|---|
| Rozrachunki z odbiorcami | 5,000.00 | |
| Przychód | | 2,000.00 |
| Odroczony przychód | | 3,000.00 |

W przypadku korzystania z metody **Bilans** nie jest łatwo zobaczyć przychód brutto za okres. Część przychodu zostanie zaksięgowana na koncie **Odroczony przychód**. Należy pamiętać, że ponieważ przychód jest rozpoznawany w każdym okresie, na koncie **Odroczonego przychodu** istnieje wiele uznań i obciążeń. Przychód brutto w danym okresie będzie zmieszany z wpłatami/wypłatami rozpoznawania przychodu.

**Sumy metod zysków i strat dla połączonych faktur sprzedaży 1 i 2**

| Konto | Uznanie | Środki |
|---|---|---|
| Rozrachunki z odbiorcami | 5,000.00 | |
| Przychód | | 5,000.00 |
| Konto przeciwstawne przychodu | 3,000.00 | |
| Odroczony przychód | | 3,000.00 |

Wszystkie przychody idą na konto **Przychów** zysków i strat. Następnie odroczony przychód jest przenoszony z zestawienia zysków i strat do bilansu. Można łatwo zobaczyć przychód brutto, ponieważ wszystkie wartości są księgowane na koncie **Przychodów**. Część tego przychodu brutto jest jednak odroczona. W związku z tym jest przenoszony na konto **Przychodu odroczonego** i rozpoznawany później.

W sposobie **Zyski i straty** można sprawdzić konto **przychodów** i konto **przeciwstawne przychodów**,aby zobaczyć przychód brutto w wysokości 5000 USD oraz przychód netto (netto odroczonych) 2000 USD. Chociaż metoda **Zyski i straty** ułatwia raportowanie, ma ona więcej kont do skonfigurowania.
