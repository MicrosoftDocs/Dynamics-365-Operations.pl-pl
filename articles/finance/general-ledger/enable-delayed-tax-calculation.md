---
title: Włączanie opóźnionego obliczania podatku w arkuszach
description: W tym temacie objaśniono sposób włączania funkcji opóźnionego obliczania podatku w celu zwiększenia wydajności obliczeń podatku, gdy liczba wierszy arkusza jest duża.
author: ericwang
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: acf5ead6ed90d4dbb41de08520cde8085a7f3935
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823723"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a>Włączanie opóźnionego obliczania podatku w arkuszach
[!include [banner](../includes/banner.md)]


W tym temacie wyjaśniono, w jaki sposób można opóźnić obliczanie podatku w arkuszach. Dzięki tej funkcji można poprawić wydajność obliczeń podatku, gdy istnieje wiele wierszy arkusza.

Domyślnie kwoty podatku w wierszach arkusza są obliczane po każdej aktualizacji pól związanych z podatkiem. Pola te obejmują pola dotyczące grup podatków i grup podatków dla pozycji. Każda aktualizacja wiersza arkusza powoduje ponowne obliczenie kwot podatku dla wszystkich wierszy arkusza. Chociaż to zachowanie pomaga użytkownikowi widzieć kwoty podatku obliczone w czasie rzeczywistym, może również wpływać na wydajność, jeśli liczba wierszy arkusza jest bardzo duża.

Funkcja opóźnionego obliczania podatku pozwala opóźnić obliczanie podatku w arkuszach, co ułatwia rozwiązywanie problemów z wydajnością. Gdy ta funkcja jest włączona, kwoty podatku będą obliczane tylko wtedy, gdy użytkownik wybierze pozycję **Podatek** lub zaksięguje arkusz.

Obliczanie podatku można opóźnić na trzech poziomach:

- Firma
- Nazwa arkusza
- Nagłówek arkusza

System nadaje priorytet ustawieniu dla nagłówka arkusza. Domyślnie to ustawienie jest pobierane z nazwy arkusza. Domyślnie ustawienie dla nazwy arkusza jest pobierane z ustawienia na stronie **Parametry księgi głównej** podczas tworzenia nazwy arkusza. W poniższych sekcjach przedstawiono sposób włączania opóźnionego obliczania podatku dla firm, nazw arkuszy i nagłówków arkuszy.

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a>Włączanie opóźnionego obliczania podatku na poziomie firmy

1. Przejdź do pozycji **Księga główna \> Ustawienia księgi \> Parametry księgi głównej**.
2. Na karcie **Podatek**, na skróconej karcie **Ogólne** ustaw opcję **Obliczanie podatku opóźnionego** na **Tak**.

![Obraz parametrów księgi głównej](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a>Włączanie opóźnionego obliczania podatku na poziomie nazwy arkusza

1. Przejdź do pozycji **Księga główna \> Konfiguracja arkusza \> Nazwy arkuszy**.
2. Na skróconej karcie **Ogólne**, w sekcji **Podatek** ustaw opcję **Obliczanie podatku opóźnionego** na **Tak**.

![Obraz nazw arkusza](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a>Włączanie opóźnionego obliczania podatku na poziomie nagłówka arkusza

1. Przejdź do pozycji **Księga główna \> Wpisy w arkuszu \> Arkusze finansowe**.
2. Wybierz pozycję **Nowy**.
3. Wybierz nazwę arkusza.
4. Na karcie **Ustawienia** ustaw opcję **Obliczanie podatku opóźnionego** na **Tak**.

![Obraz strony arkusza finansowego](media/delayed-tax-calculation-journal-header.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]