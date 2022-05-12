---
title: Omówienie rozliczeń subskrypcji
description: W tym temacie opisano rozliczanie subskrypcji w Microsoft Dynamics 365 Finance..
author: JodiChristiansen
ms.date: 04/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-02-09
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 9d46492cca3cc435048fa497f6b1f3a28b77140a
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644535"
---
# <a name="subscription-billing-overview"></a>Omówienie rozliczeń subskrypcji

[!include [banner](../includes/banner.md)]

Fakturowanie subskrypcji umożliwia organizacjom zarządzanie szansami sprzedaży subskrypcji i fakturowaniem cyklicznym za pomocą harmonogramów fakturowania. Złożone modele wyceny i fakturowania oraz alokacja przychodu są łatwe do zarządzania oraz są fakturowane i rozpoznawane na poziomie wiersza. Wieloelementowa alokacja przychodów umożliwia alokację przychodów zgodnie z Międzynarodowymi Standardami Rachunkowości (Międzynarodowy Standard Sprawozdawczości Finansowej 15 \[IFRS 15\]) i ogólnie przyjętymi zasadami rachunkowości (US GAAP) (Zagadnienie Kodyfikacji Standardów Rachunkowości 606 \[ASC 606\]).

Rozwiązanie ma trzy moduły, których można używać niezależnie. Można również używać razem wszystkich trzech modułów.

- **Cykliczne fakturowanie umowy** — ten moduł umożliwia cykliczne zarządzanie fakturowaniem i ceną zapewnia kontrolę parametrów cen i fakturowania, odnowienia umowy oraz fakturowania skonsolidowanego.
- **Przychody i odroczenia wydatków** — Ten moduł eliminuje ręczne procesy i zależność systemów zewnętrznych, zarządzając przychodami i umożliwiając w czasie rzeczywistym wgląd w miesięczny cykliczny przychód.
- **Wielo elementowa alokacja przychodów** — ten moduł pomaga zapewnić zgodność przychodów, obsługuj alokację cen i przychodów dla wielu towarów.

Więcej informacji o rozliczaniu subskrypcji znajdziesz w [Rozliczanie subskrypcji zawartości Power BI](sub-bill-power-bi.md).

Fakturowanie subskrypcji jest włączane za pośrednictwem **funkcji zarządzania**. Nie można go jednak używać z funkcją **Rozpoznawania przychodów**. Dlatego tę funkcję należy wyłączyć przed włączeniem fakturowania subskrypcji.

1. W obszarze **roboczym Zarządzanie funkcjami** na karcie **Wszystkie** wprowadź w **filtrze przychód**, a następnie wybierz nazwę funkcji jako filtr.
2. Wybierz funkcję **Rozpoznawanie przychodów**, a następnie **Wyłącz**.
3. W **filtrze nazwy** funkcji wprowadź opcję **Fakturowanie subskrypcji**, a następnie wybierz filtr modułu.
4. Wybierz funkcję **fakturowania subskrypcji**, a następnie **włącz**.
5. Wybierz jeden z trzech modułów z poprzedniej listy, a następnie wybierz opcję **Włącz**. Powtórz ten krok dla każdego z pozostałych dwóch modułów.

    > [!IMPORTANT]
    > Funkcja **Rozliczenia za subskrypcję** musi być włączona, zanim będzie można włączyć którykolwiek z trzech modułów.
