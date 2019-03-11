---
title: Symulacja zmian kosztów przy użyciu wersji wyceny kosztów planowanych
description: W tym artykule wyjaśniono, jak symulować wpływ zmian kosztów na obliczone koszty wytwarzanego towaru poprzez użycie osobnej wersji wyceny dla kosztów planowanych.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 78183
ms.assetid: 1e41953f-cdb9-4598-b776-46e49383a773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3ef3cdb2ede2c30609db4addfc10b819629cdc64
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "318886"
---
# <a name="simulate-cost-changes-by-using-a-costing-version-for-planned-costs"></a>Symulacja zmian kosztów przy użyciu wersji wyceny kosztów planowanych

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak symulować wpływ zmian kosztów na obliczone koszty wytwarzanego towaru poprzez użycie osobnej wersji wyceny dla kosztów planowanych.

Można symulować wpływ zmian obliczonych kosztów wytwarzanych towarów, używając osobnej wersji wyceny dla kosztów planowanych. Należy używać tej osobnej wersji wyceny do wprowadzania rekordów kosztów oczekujących odzwierciedlających przyrostowe zmiany kosztów oraz do obliczania wpływu kosztów na produkowane towary. Ponieważ zasada alternatywnych źródeł danych aktywnych kosztów będzie używana przy obliczaniu listy składowej (BOM), należy wprowadzić tylko przyrostowe zmiany kosztów.

## <a name="guidelines-for-defining-the-simulation-costing-version"></a>Wytyczne dotyczące definiowania wersji wyceny w symulacji
Podczas definiowania wersji ceny dla symulacji należy postępować według następujących wskazówek:

-   Przypisz typ wyceny **Koszty planowane**.
-   Przypisz sugestywny identyfikator dla wersji ceny, na przykład **Symulacja**.
-   Upewnij się, że zawartość obejmuje rekordy kosztów.
-   Zezwól na wprowadzanie rekordów kosztów. Nie blokuj możliwości wprowadzania kosztów oczekujących.
-   Zezwól na wprowadzanie rekordów kosztów we wszystkich oddziałach. Podanie oddziału ograniczy możliwość wprowadzania rekordów kosztów tylko do tego oddziału.
-   Zapobiegaj aktywacji kosztów oczekujących. W wersji ceny dla symulacji w rekordach kosztów można wpisywać tylko koszty oczekujące.
-   Nie wprowadzaj daty początkowej. Data obliczenia zostanie wprowadzona dla każdego obliczenia BOM korzystającego z symulacji wersji ceny.
-   Jako zasadę alternatywnych źródeł danych określ **Aktywne**. Zasada alternatywnych źródeł danych umożliwia wprowadzanie przyrostowych zmian kosztów na potrzeby symulacji, ale wykorzystuje obecnie aktywne koszty jako źródło dla wszystkich pozostałych rekordów kosztów. Zakładamy, że dla wszystkich pozostałych rekordów kosztów istnieją wszystkie obecnie aktywne koszty.
-   Określ model kosztu własnego **Koszt własny wersji**, ale nie ograniczaj obliczeń. Na przykład symulacja może także wykorzystywać model kosztu własnego **Grupa obliczania BOM** w celu wskazania źródła danych o udziale kosztów w kupowanych towarach.
-   Określ tryb rozwinięcia **Wiele poziomów**, ale nie ograniczaj obliczeń. Symulacja może korzystać z innych trybów rozłożenia.

## <a name="costing-versions"></a>Wersje wyceny
W poniższych scenariuszach przedstawiono użycie wersji wyceny w symulacjach w celu określenia wpływu zmiany kosztów. Przed wprowadzeniem symulowanej zmiany kosztu usuń rekordy kosztów oczekujących z wersji wyceny w symulacji, aby uzyskać czysty punkt wyjściowy. Na stronie **Cena pozycji** wyświetl i usuń rekordy kosztów oczekujących związane z cenami towarów i cenami w kategoriach kosztów.

-   Przeprowadź symulację zmiany kosztu zakupionego towaru. Na przykład zmiana kosztu może odzwierciedlać oczekiwany wzrost lub spadek kosztu newralgicznych kupowanych materiałów. Aby zdefiniować różne koszty kupowanego towaru, na stronie **Cena pozycji** wprowadź rekord kosztu oczekującego w wersji wyceny w symulacji.
-   Przeprowadź symulację zmiany kategorii kosztów. Na przykład zmiana kosztu może odzwierciedlać oczekiwany wzrost lub spadek stawek robocizny lub stawek godzinowych dla zasobów produkcyjnych. Aby zdefiniować różne koszty dla kategorii kosztów, na stronie **Kategoria kosztu własnego** wprowadź rekord kosztów oczekujących w wersji wyceny w symulacji.
-   Przeprowadź symulację zmiany kosztu w formule obliczania kosztów pośrednich. Na przykład zmiana kosztu może odzwierciedlać oczekiwany wzrost lub spadek kosztów ogólnych produkcji. Aby zdefiniować zmianę w formule obliczania kosztów pośrednich, na stronie **Konfiguracja arkusza wyceny** wprowadź rekord kosztów oczekujących w wersji wyceny dla symulacji, sprawdź poprawność i zapisz zmianę.

Po wprowadzeniu symulowanych zmian kosztów oblicz koszty wytwarzanych towarów, na które wpłynęły zmiany. Na stronie **Obliczanie** dla wersji wyceny w symulacji zidentyfikuj wybrane produkowane towary, na które wpłynie zmiana kosztu. Jeśli nie wybierzesz konkretnych towarów, obliczenia BOM będą dotyczyć wszystkich wytwarzanych towarów. Alternatywnie za pomocą opcji obliczania BOM można zaktualizować dane miejsc użycia. Wyświetl rekordy kosztów towaru w wersji wyceny w symulacji w celu przeanalizowania wpływu symulowanych zmian kosztów na koszty wybranych wytwarzanych towarów. Do wyświetlania i analizowania kosztów służą strony **Cena pozycji** i **Oblicz koszt pozycji**.



