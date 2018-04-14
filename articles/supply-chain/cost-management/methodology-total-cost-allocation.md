---
title: "Metoda całkowitej alokacji kosztów"
description: "Ten temat zawiera wskazówki dotyczące korzystania z metody całkowitej alokacji kosztów (TCA). TCA jest metodą obliczania kosztu między głównym towarem formuły szarży produkcyjnej a produktami towarzyszącymi zdefiniowanymi w formule."
author: AndersGirke
manager: AnnBe
ms.date: 10/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, PmfFormulaCoBy
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 83852
ms.assetid: 7c14c3e5-9476-4a79-a210-e77fc91cc7fc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4f3d75411e8c99365f1aba8214c78e93b4741871
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="total-cost-allocation-method"></a>Metoda całkowitej alokacji kosztów

[!INCLUDE [banner](../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące korzystania z metody całkowitej alokacji kosztów (TCA). TCA jest metodą obliczania kosztu między głównym towarem formuły szarży produkcyjnej a produktami towarzyszącymi zdefiniowanymi w formule.

Całkowita alokacja kosztów (TCA) jest metodą obliczania kosztu między głównym towarem formuły szarży produkcyjnej a produktami towarzyszącymi zdefiniowanymi w formule. Ta metoda jest dynamiczna. Koszt jest obliczany jako średnia ważona między ilościami, które zostały zgłoszone jako gotowe dla produktu i produktów towarzyszących formuły. W przypadku używania metody TCA nie trzeba sprawdzać alokacji kosztów dla każdej szarży produkcyjnej. Jeśli metoda TCA nie jest używana, w obliczeniach formuły są używane istniejące funkcje.

## <a name="using-tca-for-coproducts"></a>Używanie metody TCA do produktów towarzyszących
Poniżej przedstawiono wybrane wskazówki dotyczące używania metody TCA dla produktów towarzyszących:

-   Jeśli w wersji formuły na suwaku **Całkowita alokacja kosztów** ustawisz wartość **Tak**, produkty towarzyszące muszą mieć koszt własny większy niż 0 (zero). Wartość może być pobierana z wersji aktywnego kosztu tego samego oddziału, a w przypadku formuły niepowiązanej z konkretnym oddziałem — z pierwszego dostępnego oddziału. Ten warunek jest weryfikowany podczas zatwierdzania formuły.

    -   Nie trzeba ręcznie wprowadzać wartości procentowych alokacji kosztów dla produktów towarzyszących. Zamiast tego system automatycznie tworzy wartości procentowe alokacji kosztów jako średnią aktywnych kosztów własnych produktów towarzyszących. 
    -   Nie trzeba wprowadzać kosztu standardowego towarów mających koszt niestandardowy, które są produktami towarzyszącymi. Istnieją dwa typy wersji wyceny w systemie: koszt standardowy i koszt planowany 
    -   Jeśli towar nie jest wyceniany metodą kosztu standardowego, zaleca się używanie aktywnego kosztu własnego w wersji kosztu planowanego. Ta cena jest używana do szacowania kosztów, na przykład w obliczaniu BOM, szacowaniu kosztów produkcji i ustalaniu ceny alternatywnej w procesu inwentaryzacji zapasów. 

-   Jeśli w wersji formuły na suwaku **Całkowita alokacja kosztów** ustawisz wartość **Tak** i są spełnione poniższe warunki, metodą alokacji kosztów jest **TCA**, a procent alokacji kosztów pozostaje bez zmian:
    -   Dodano produkty towarzyszące.
    -   Użyto innej metody alokacji kosztów dla produktów towarzyszących.
-   Jeśli w wersji formuły ustawisz na suwaku **Całkowita alokacja kosztów** wartość **Nie** i są spełnione poniższe warunki, metoda alokacji kosztów zmienia się na **Ręcznie**, a procent alokacji kosztów pozostaje bez zmian:
    -   Dodano produkty towarzyszące.
    -   Procent alokacji kosztów jest większy niż 0 (zero).
-   Aby można było pomyślnie wykonać obliczenie formuły, należy oszacować wartości procentowe alokacji kosztów. Ten krok można wykonać ręcznie lub przy użyciu opcji **Oszacuj koszt** umieszczonej na stronie **Produkty towarzyszące**. **Uwaga:** Opcja **Oszacuj koszt** jest dostępna tylko wtedy, gdy dla wersji formuły suwak **Całkowita alokacja kosztów** jest w pozycji **Tak**. Oczekiwaną alokację można wyświetlić, jeśli ilości szarży produkcyjnej zgłoszone jako gotowe są zgodne z ilościami podanymi w formule.
-   Podczas ręcznego tworzenia szarży produkcyjnej lub akceptowania planowanej szarży produkcyjnej wartość suwaka **Całkowita alokacja kosztów** w wersji formuły jest kopiowana do szarży produkcyjnej. Można jednak zmienić to ustawienie wewnątrz szarży produkcyjnej. Jeśli suwak **Całkowita alokacja kosztów** ma wartość **Nie** w wersji formuły, a następnie zostanie zmieniony na **Tak** w szarży produkcyjnej, metoda alokacji kosztów ustawiona dla każdego wiersza na **Ręcznie** zmieni się na **TCA**. Metoda alokacji kosztów **Brak** nie ulega zmianie. Jeśli suwak **Całkowita alokacja kosztów** ma wartość **Tak** w wersji formuły, a następnie zostanie zmieniony na **Nie** w szarży produkcyjnej, metoda alokacji kosztów dla każdego produktu towarzyszącego typu **Produkt** zmieni się na **Ręcznie**. Wszelkie szacowane wartości procentowe alokacji kosztów pozostają niezmienione.
-   Strona **Alokacja kosztów produktu towarzyszącego** pokazuje obliczony procent alokacji kosztów. Można otworzyć tę stronę ze strony **Szarża produkcyjna**. Informacje te są przydatne, gdy zgłaszane produkty i ilości różnią się od ilości zaplanowanych lub rozpoczętych w szarży produkcyjnej. Po zakończeniu obliczania kosztów nowe procentowe alokacje z TCA zostaną wyświetlone na strona **Alokacja kosztów produktu towarzyszącego**.

## <a name="calculating-the-burden-for-byproducts"></a>Obliczanie obciążenia dla produktów ubocznych
Pole **Alokacja kosztów produktu ubocznego** na stronie **Produkty towarzyszące** jest polem stałotekstowym używanym jedynie dla produktów ubocznych. W przypadku produktów towarzyszących wartością tego pola jest zawsze **Brak**. W przypadku wierszy produktów ubocznych to pole określa sposób dodawania kwot kosztów wierszy produktów ubocznych do całkowitego kosztu produkcji. Dostępne są następujące opcje:

-   **Brak** — Żadna kwota nie jest dodawana do całkowitego kosztu produkcji dla tego wiersza produktu ubocznego.
-   **Procent** — Kwota kosztu jest obliczana jako procent sumy kosztów surowców zużywanych w produkcji. Procent używany do obliczeń należy wpisać w polu.
-   **W serii** — Kwota kosztu jest obliczana jako kwota dla standardowego rozmiaru partii zlecenia produkcyjnego. Nie zależy od ilości zgłoszonej w produkcji. Kwotę używaną do obliczeń należy wpisać w polu.
-   **Na ilość** — Kwota kosztu jest obliczana jako kwota dla zgłoszonej ilości towaru formuły w produkcji. Kwotę używaną do obliczeń należy wpisać w polu.





