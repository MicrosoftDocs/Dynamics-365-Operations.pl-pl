---
title: Szacowanie kosztu zlecenia produkcyjnego
description: Ten artykuł zawiera informacje o szacowaniu kosztów produkcji. Szacowanie kosztów produkcji pokazuje prognozowane koszty zużycia materiałów i zdolności produkcyjnych w celu wytworzenia towaru w ilości określonej w planowanym zleceniu produkcyjnym.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a101f82e60113941d389421b19cddc1ad123ce9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435308"
---
# <a name="production-order-cost-estimation"></a>Szacowanie kosztu zlecenia produkcyjnego

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o szacowaniu kosztów produkcji. Szacowanie kosztów produkcji pokazuje prognozowane koszty zużycia materiałów i zdolności produkcyjnych w celu wytworzenia towaru w ilości określonej w planowanym zleceniu produkcyjnym. 

Po utworzeniu zlecenia produkcyjnego należy oszacować koszty produkcji. Celem jest oszacowanie zużycia towaru i marszruty w procesie produkcji, ponieważ te szacunki są używane jako podstawa dla kolejnych procesów planowania i produkcji.

## <a name="production-cost-estimation"></a>Szacowanie kosztu produkcji
Szacunki kosztów produkcji bazują na następujących informacjach:

-   Ilość w zleceniu produkcyjnym
-   Składniki w listach składowych (BOM)
-   Operacje marszruty w marszrucie produkcji
-   Koszty pośrednie dotyczące składników i operacji
-   Dane aktywnych kosztów na dzień obliczania

Jeśli listy BOM produkcji zawierają wiersze fantomowe, obliczenia odzwierciedlają składniki i operacje marszruty istniejące w tych fantomach. Zadanie szacowania umożliwia ponowne obliczanie szacowanych kosztów, tak aby odzwierciedlały zaktualizowane informacje. Na przykład zaktualizowanymi informacjami mogą być zmiany ilości w zleceniu produkcyjnym, składników w BOM produkcji, operacji marszruty w marszrucie produkcji, kosztów pośrednich dotyczących tych składników i operacji albo aktywnych kosztów na dzień ponownego obliczania. Obliczanie szacowanych kosztów umożliwia również zaproponowanie ceny sprzedaży wytwarzanego towaru na podstawie metody „koszt plus narzut”. Obliczenia szacowanych kosztów mogą opcjonalnie dotyczyć zamówień odniesienia odzwierciedlających inne zlecenia produkcyjne powiązane ze zleceniem produkcyjnym.

## <a name="view-the-estimated-costs"></a>Wyświetlanie szacowanych kosztów
Po wykonaniu szacowania wyniki można obejrzeć na stronie **Obliczanie ceny**. Szacowanie powoduje obliczenie następujących wartości:

-   **Koszt produkcji** — Koszt produkcji to górny wiersz szacowania. Pokazuje on całkowity koszt realizacji zlecenia produkcyjnego oraz łączną cenę sprzedaży produkcji. Jest to suma wszystkich wierszy kosztów w szacowaniu.
-   **Koszty marszrut lub zasobów** — Koszty marszrut lub zasobów to koszty operacji produkcyjnych. Obejmują koszty elementów takich jak czas przezbrajania i czas procesu oraz koszty ogólne.
-   **Koszty materiałów** — Koszty materiałów to koszty i ceny składników BOM potrzebnych do wyprodukowania towaru. Koszty te zostały uprzednio określone i wprowadzone w systemie.

## <a name="other-uses-of-cost-estimation"></a>Inne zastosowania szacowania kosztów
Szacowanie kosztów może także dostarczać następujących informacji:

-   Sensowne oferty cenowe.
-   Oszacowania zyskowności zamówienia.
-   Oszacowania wykorzystania surowców.
-   Porównania z informacjami o kosztach wcześniejszych produkcji.
-   Informacje o budżecie i prognozach.
-   Oszacowania rozmiaru produkcji wymaganego do utrzymania określonego kosztu.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]