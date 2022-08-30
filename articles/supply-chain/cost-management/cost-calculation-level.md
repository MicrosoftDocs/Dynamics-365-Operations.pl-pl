---
title: Poziom obliczania kosztu
description: W tym artykule opisano poziom BOM o nazwie poziom obliczania kosztu. Ten poziom BOM wyklucza produkcję i zamówienia partii z obliczeń.
author: JennySong-SH
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: e63a868696e36c1d4f5d19ea87bdf4d682c39f8c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334964"
---
# <a name="cost-calculation-level"></a>Poziom obliczania kosztu

[!include [banner](../includes/banner.md)]

Poziom BOM o nazwie **Poziom obliczania kosztu** wyklucza zlecenia produkcyjne i zamówienia partii z jego obliczeń. Ten poziom jest używany w systemie podczas uruchamiania obliczeń kosztów w wersjach ceny. W procesach takich jak ponowne obliczanie i zamykanie zapasów system używa zamiast tego **Poziom wyceny** poziom BOM.

## <a name="turn-the-cost-calculation-level-feature-on-or-off"></a>Włącz lub wyłącz funkcję Poziomu obliczania kosztu

Aby używać tej funkcji, należy ją włączyć dla systemu. Od wersji 10.0.29 Supply Chain Management funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Poziom obliczania kosztu* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="example-scenario"></a>Przykładowy scenariusz

Poniższy prosty scenariusz pokazuje różnice między poziomem BOM **Poziom obliczania kosztu** a poziomem BOM **Poziom wyceny**.

Istnieją trzy produkty: A, B i C. Produkt C jest składnikiem produktu B, a produkt B jest składnikiem produktu A.

- **Poziom wyceny** przypisuje następujące poziomy BOM:

    - **Produkt A:** 0
    - **Produkt B:** 1
    - **Produkt C:** 2

- **Poziom obliczania kosztu** przypisuje następujące poziomy BOM:

    - **Produkt A:** 0
    - **Produkt B:** 1
    - **Produkt C:** 2

Tworzone jest zlecenie produkcyjne dla produktu C, a produkt A jest dodawany do BOM zlecenia produkcyjnego. Po oszacowaniu zamówienia poziomy BOM są aktualizowane w następujący sposób:

- **Poziom wyceny** przypisuje następujące poziomy BOM:

    - **Produkt B:** 1
    - **Produkt C:** 2
    - **Produkt A:** 3

- **Poziom obliczania kosztu** przypisuje następujące poziomy BOM:

    - **Produkt A:** 0
    - **Produkt B:** 1
    - **Produkt C:** 2

To zachowanie gwarantuje, że zmiany BOM zlecenia produkcyjnego nie wpływają na kolejne obliczenia kosztów.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]