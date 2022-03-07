---
title: Poziom obliczania kosztu
description: W tym temacie opisano poziom BOM o nazwie poziom obliczania kosztu. Ten poziom BOM wyklucza produkcję i zamówienia partii z obliczeń.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: e08d11c8e9d98e56c5ef076cbab7bb68bedea62a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7581039"
---
# <a name="cost-calculation-level"></a>Poziom obliczania kosztu

[!include [banner](../includes/banner.md)]

Poziom BOM o nazwie **Poziom obliczania kosztu** wyklucza zlecenia produkcyjne i zamówienia partii z jego obliczeń. Ten poziom jest używany w systemie podczas uruchamiania obliczeń kosztów w wersjach ceny. W procesach takich jak ponowne obliczanie i zamykanie zapasów system używa zamiast tego **Poziom wyceny** poziom BOM.

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