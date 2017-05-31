---
title: "Zliczanie znaczników zapasów"
description: "Ten artykuł zawiera informacje o procesie zliczania znaczników, który służy do porównywania rzeczywistej zawartości magazynu z zapasami dostępnymi (na stanie)."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 61a48a61963f643c8969e9090c2e84b5499b716a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="inventory-tag-counting"></a>Zliczanie znaczników zapasów

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o procesie zliczania znaczników, który służy do porównywania rzeczywistej zawartości magazynu z zapasami dostępnymi (na stanie). 

Poprzez tworzenie wierszy na stronie **Zliczanie znaczników** na każdym towarze magazynowym umieszcza się numer znacznika, np. od 1 do 500. Podczas inwentaryzacji należy wprowadzić numer towaru i ilość związaną z odpowiednim znacznikiem. Znacznik może być później podstawą dla danych wejściowych arkusza zliczania znaczników. Po zaksięgowaniu arkusza zliczania znaczników na stronie **Zliczanie** tworzony jest nowy arkusz zliczania. Nowy arkusz bazuje na wierszach arkusza zliczania znaczników utworzonych przez użytkownika. Aby policzyć towary według znaczników w określonym wymiarze magazynu, należy wybrać wymiar na stronie **Wyświetl wymiary**, która jest wyświetlana podczas tworzenia arkusza zliczania znaczników. Na przykład aby policzyć towary w określonym magazynie, należy zaznaczyć pole wyboru **Magazyn**. Jeśli suwak **Zablokuj towary podczas liczenia** na stronie **Parametry zarządzania zapasami i magazynem** jest zaznaczony, towary nie mogą być fizycznie aktualizowane podczas zliczania. Jednak towary w arkuszach zliczania znaczników nie są zablokowane podczas zliczania. Transakcje magazynowe nie są tworzone, dopóki wiersze zliczania znaczników nie zostaną zaksięgowane ani przeniesione do arkusza zliczania. Jeśli znaczniki są wprowadzane losowo, aby zidentyfikować brakujące znaczniki, należy kliknąć nagłówek kolumny **Znacznik**, aby posortować wiersze według znacznika.

<a name="see-also"></a>Informacje dodatkowe
--------

[Inwentaryzacja ciągła](../warehousing/cycle-counting.md)




