---
title: Generowanie wariantów dla produktów projektowych
description: W tym temacie opisano sposób generowania wariantów dla produktów projektowych
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e24bceac9457212ecaafda876d19ba62df049371
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2021
ms.locfileid: "7471843"
---
# <a name="generate-variants-for-engineering-products"></a>Generowanie wariantów dla produktów projektowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób generowania wariantów dla produktów projektowych.

## <a name="turn-on-variant-generation-for-engineering-products"></a>Włączanie generowania wariantów dla produktów projektowych

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł**: *Zarządzanie zmianami projektowymi*
- **Nazwa funkcji:** *Generowanie wariantów dla produktów projektowych*

> [!IMPORTANT]
> Funkcja *generowania wariantów produktów projektowych* będzie widoczna w systemie tylko po włączeniu klucza konfiguracji *Zarządzanie zmianami projektowymi*. Aby uzyskać instrukcje, zobacz [Omówienie zarządzania zmianą inżynieryjną](product-engineering-overview.md).

## <a name="generate-one-or-more-new-variants-of-an-engineering-product"></a>Generowanie jednego lub więcej nowych wariantów produktu projektowego

Można utworzyć jeden lub więcej nowych wariantów produktu bez kopiowania informacji z istniejącego produktu. Jest to przydatne, gdy trzeba utworzyć kilka wariantów produktu w tym samym czasie.

Poniższa procedura zawiera przykład tworzenia kilku wariantów, które zawierają wymiar koloru.

1. Otwórz stronę **Zwolnione produkty** (na przykład przejdź do pozycji **Zarządzanie zmianami projektowymi \> Wspólne \> Zwolnione produkty**).
1. W okienku akcji na karcie otwórz kartę **Produkt** i w grupie **Nowy** wybierz opcję **Produkt projektowy**.
1. Zostanie otwarte okno dialogowe **Nowy produkt**. Wybierz odpowiednią **kategorię projektową**.
1. Jeśli wybrana kategoria projektowa zawiera wymiary wariantów, można teraz ustawić dla nich wartości. W tym przykładzie, jeśli kategoria ma wymiar **Kolor**, można ustawić ją na *Niebieski*.
1. W razie potrzeby należy wprowadzić inne ustawienia. Wybierz przycisk **OK**, aby utworzyć produkt.
1. Produkt i wariant V-1 w kolorze niebieskim są tworzone, a nowy produkt zostanie otwarty.
1. W razie potrzeby dodaj listę składową (BOM) i trasę do wariantu.
1. W okienku akcji otwórz kartę **Produkt** i w grupie **Produkt główny** wybierz opcję **Wymiary produktu**.
1. Zostanie otwarta strona **Wymiary produktu**. Ta strona zawiera kartę dla każdego dostępnego wymiaru. Na każdej karcie dodaj wiersz dla każdej wartości, którą będzie obsługiwana dla każdego odpowiedniego wymiaru. (W tym przykładzie można dodać wiersze na karcie **Kolor** dla koloru *białego*, *żółtego* i *zielonego*).
1. Zamknij stronę i wybierz opcję **Zwolnione warianty produktu**. Zwróć uwagę, że jest wyświetlany pierwszy utworzony wariant (niebieski V-1).
1. W okienku akcji na karcie **Wariant produktu** wybierz opcję **Propozycje wariantów**.
1. W oknie dialogowym **Propozycje wariantów** wykonaj jedną z poniższych czynności:

    - W górnej części okna dialogowego znajduje się sekcja dla każdego dostępnego wymiaru. Dla każdego wymiaru zaznacz pole wyboru przy każdej wartości, dla której chcesz wygenerować propozycję wariantu, a następnie wybierz pozycję **Sugeruj** na pasku narzędzi. Odpowiednie sugestie są dodawane do sekcji **Sugerowane warianty**.
    - Zaznacz pole **Sugeruj wszystkie** na pasku narzędzi, aby wygenerować propozycje wariantów dla wszystkich dostępnych kombinacji wartości wymiarów. Sugestie są dodawane do sekcji **Sugerowane warianty**.

1. W sekcji **Sugerowane warianty** zaznacz pole wyboru obok każdego wariantu, który chcesz utworzyć. Następnie wybierz pozycję **Utwórz**, aby wygenerować i zwolnić warianty dla firmy inżynieryjnej. Należy uwzględnić następujące warunki:

    - Żaden z utworzonych wariantów nie będzie miał listy składowej (BOM) ani trasy.
    - Atrybuty dla tych wariantów będą domyślnie pochodzić z kategorii inżynieryjnej i nie zostaną skopiowane z poprzedniego wariantu.

## <a name="generate-a-variant-as-a-copy-of-another-product-variant"></a>Generowanie wariantu jako kopii innego wariantu produktu

Można utworzyć wariant produktu na podstawie innego wariantu produktu. Lista składowa (BOM) i trasa z wariantu produktu źródłowego są kopiowane do nowego wariantu. Może to być przydatne w przypadku produktów z produkcji dyskretnej, w przypadku których może być pomocne utworzenie listy składowej (BOM) na podstawie początkowej listy BOM-u i śledzenie zmian z poprzedniego wariantu. Aby zachować możliwość identyfikowania, system rejestruje, który wariant został skopiowany w celu utworzenia nowej kopii.

Poniższa procedura zawiera przykład tworzenia nowego wariantu, który zawiera wymiar kolorów, przez utworzenie kopii istniejącego wariantu

1. Otwórz stronę **Zwolnione produkty** (na przykład przejdź do pozycji **Zarządzanie zmianami projektowymi \> Wspólne \> Zwolnione produkty**).
1. W okienku akcji na karcie otwórz kartę **Produkt** i w grupie **Nowy** wybierz opcję **Produkt projektowy**.
1. Zostanie otwarte okno dialogowe **Nowy produkt**. Wybierz odpowiednią **kategorię projektową**.
1. Jeśli wybrana kategoria projektowa zawiera wymiary wariantów, można teraz ustawić dla nich wartości. W tym przykładzie, jeśli kategoria ma wymiar **Kolor**, można ustawić ją na *Niebieski*).
1. W razie potrzeby należy wprowadzić inne ustawienia. Wybierz przycisk **OK**, aby utworzyć produkt.
1. Produkt i wariant V-1 w kolorze niebieskim są tworzone, a nowy produkt zostanie otwarty.
1. W razie potrzeby dodaj listę składową (BOM) i trasę do wariantu.
1. W razie potrzeby dodaj atrybuty do wariantu produktu.
1. Dodaj wariant produktu „niebieski V-1” do zlecenia zmiany projektowej.
1. Ustaw opcję **Wpływ** na *Nowy wariant*.
1. Wybierz nową wartość koloru (na przykład *Biały*). Zauważ, że mają zastosowanie następujące warunki: 
    - Nowy wariant ma BOM i trasę, które zostały skopiowane z poprzedniego wariantu.
    - Nowy wariant ma atrybuty skopiowane z poprzedniego wariantu.
1. Zatwierdź zlecenie zmiany.
1. Przetwórz zlecenie zmiany. Po przetworzeniu zamówienia nowy wariant V-1 zostanie utworzony i wydany zwolniony do firmy inżynieryjnej.
