---
title: Zliczanie znaczników zapasów
description: Ten artykuł zawiera informacje o procesie zliczania znaczników, który służy do porównywania rzeczywistej zawartości magazynu z zapasami dostępnymi (na stanie).
author: yufeihuang
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ceccfce98a71f7396358de9369af61c9eb96dce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856172"
---
# <a name="inventory-tag-counting"></a>Zliczanie znaczników zapasów

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o procesie zliczania znaczników, który służy do porównywania rzeczywistej zawartości magazynu z zapasami dostępnymi (na stanie).

Poprzez tworzenie wierszy na stronie **Zliczanie znaczników** na każdym towarze magazynowym umieszcza się numer znacznika, np. od 1 do 500. Podczas inwentaryzacji należy wprowadzić numer towaru i ilość związaną z odpowiednim znacznikiem. Znacznik może być później podstawą dla danych wejściowych arkusza zliczania znaczników. Po zaksięgowaniu arkusza zliczania znaczników na stronie **Zliczanie** tworzony jest nowy arkusz zliczania. Nowy arkusz bazuje na wierszach arkusza zliczania znaczników utworzonych przez użytkownika. Aby policzyć towary według znaczników w określonym wymiarze magazynu, należy wybrać wymiar na stronie **Wyświetl wymiary**, która jest wyświetlana podczas tworzenia arkusza zliczania znaczników. Na przykład aby policzyć towary w określonym magazynie, należy zaznaczyć pole wyboru **Magazyn**. Jeśli suwak **Zablokuj towary podczas liczenia** na stronie **Parametry zarządzania zapasami i magazynem** jest zaznaczony, towary nie mogą być fizycznie aktualizowane podczas zliczania. Jednak towary w arkuszach zliczania znaczników nie są zablokowane podczas zliczania. Transakcje magazynowe nie są tworzone, dopóki wiersze zliczania znaczników nie zostaną zaksięgowane ani przeniesione do arkusza zliczania. Jeśli znaczniki są wprowadzane losowo, aby zidentyfikować brakujące znaczniki, należy kliknąć nagłówek kolumny **Znacznik**, aby posortować wiersze według znacznika.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inwentaryzacja ciągła](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]