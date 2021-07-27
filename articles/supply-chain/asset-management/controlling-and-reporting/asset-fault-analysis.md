---
title: Analiza usterek składników majątku
description: W tym temacie wyjaśniono analizę usterek składników majątku w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 913e5cf8d39dfe36efea0526d84808e7d736b030
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6361167"
---
# <a name="asset-fault-analysis"></a>Analiza usterek składników majątku

[!include [banner](../../includes/banner.md)]

 

W module Zarządzanie składnikami majątku można analizować rejestracje usterek składników majątku, aby uzyskać przegląd łącznej liczby usterek zarejestrowanych w danym okresie. Rejestracje usterek mogą być analizowane z różnych perspektyw, na przykład z nastawieniem na składniki majątku, typy składników majątku, lokalizacje czynności konserwacyjnych, objawy usterek lub typy usterek.

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Analiza usterek składników majątku**.

2. W oknie **Obliczanie analizy usterek składników majątku** można użyć pola **Poziom**, aby określić, jak bardzo szczegółowe mają być wiersze błędów składniku majątku dotyczące lokalizacji czynności konserwacyjnych. 

    Jeśli na przykład w polu wstawiono liczbę „1” i istnieje struktura lokalizacji czynności konserwacyjnych wielopoziomowej, wszystkie wiersze usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji funkcjonalnych znajdujących się na niższym poziomie. 
        
    W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze usterek składnika majątku na każdym poziomie lokalizacji czynności konserwacyjnych, z którym jest powiązany.

3. Aby ograniczyć wyszukiwanie, można wybrać określone składniki majątku, daty usterek, przyczyny usterek i środki zaradcze w skróconej karcie **Rekordy do uwzględnienia**.

4. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

5. Na karcie **Analiza usterek składników majątku** kliknij jeden lub więcej przycisków **Grupuj wg**, aby wyświetlić poziom szczegółowości, który ma być widoczny. Przyciski aktywne są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy kliknąć na niego.

6. Kliknij **Zaktualizuj obliczenia** obliczenia, aby wyświetlić wybrane opcje na ekranie. 

>[!NOTE]
>Przy każdym aktywowaniu lub dezaktywowaniu przycisku **Grupuj wg** pamiętaj o kliknięciu przycisku **Zaktualizuj obliczenia**. Jest to wymagane, ponieważ podczas ponownego obliczania prawdopodobieństwa wystąpienia błędów jest przetwarzana duża ilość danych.

## <a name="examples"></a>Przykłady

Istnieje wiele sposobów analizowania rejestracji usterek. Ta sekcja zawiera pięć przykładów pokazujących, jak różne wybory danych udostępniają więcej szczegółów i lepszy wgląd w informacje podczas analizowania rejestracji usterek.

### <a name="group-by-symptoms"></a>Grupowanie według objawów

Na poniższym zrzucie jest zaznaczony tylko przycisk **Objaw**.

- Przeprowadzono rejestracje błędów na trzech objawach usterek: „przeciek powietrza”, „przepalony bezpiecznik” i „wystąpiło zacięcie sprzętu”.  
- W kolumnie **Prawdopodobieństwo (%)** wszystkie wartości procentowe sumują się do 100%. W tej analizie błędów prawdopodobieństwo jest oparte na wszystkich wpisach **Objawów**.

![Rysunek 1.](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a>Grupowanie według objawów i okresu

W poniższym zrzucie ekranu **Rok** i **Miesiąc** zostały dodane, aby pokazać jak można wyświetlić rejestracje usterek w wybranym okresie.

- Objawy usterki są teraz widoczne jako rejestracje na rok/miesiąc.  
- Jeśli w kolumnie **Prawdopodobieństwo (%)** zostaną dodane wszystkie wartości procentowe dla każdego miesiąca, sumują się do 100%. W tej analizie błędów prawdopodobieństwo jest oparte na wszystkich wpisach **Objawów**. Jeśli składnik majątku zawiera dużą liczbę wierszy, ale w wierszu znajduje się duża wartość procentowa, to znaczy, że jest to wskaźnik usterki służący do dokładnego zbadania, aby znaleźć sposób ograniczenia liczby rejestracji dla tego objawu usterki.

![Rysunek 2.](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a>Grupowanie według wielu objawów i składników majątku

Połączenie składników majątku i typu składnika majątku jest używana jako podstawa dla obliczeń przedstawionych w trzech poniższych zrzutach, które spowodują zwiększenie poziomu szczegółowości.  

Na ogół przyciski w grupach okienka akcji **Grupuj według dat**, **Grupuj według składników majątku**, **Grupuj według lokalizacji czynności konserwacyjnych**, a także przycisk **Usterka** (identyfikator usterki) zawierają okresy lub relacje składników majątku. Przyciski **Objaw**, **Obszar**, **Typ**, **Przyczyna** i **Środek zaradczy** są używane w module zarządzanie błędami do analizowania rejestracji usterek i okreaślania problematycznych obszarów.  

**Grupowanie według objawu, składnika majątku i typu składnika majątku**

W poniższym zrzucie ekranu dodano **Składnik majątku** i **Typ składnika majątku**, co daje więcej szczegółowych informacji dotyczących rejestracji błędów.

- Objawy błędów są teraz podzielone w kombinacjach **Składnik majątku** / **Typ składnika majątku** / **Objaw**.  
- Jeśli w kolumnie **Prawdopodobieństwo (%)** zostaną dodane wszystkie wartości procentowe dla odpowiednich kombinacji **Składnik majątku** / **Typ składnika majątku** / **Objaw**, które sumują się do 100%. W tej analizie błędów prawdopodobieństwo jest oparte na wszystkich rejestracjach **Objawów**. Jeśli składnik majątku zawiera dużą liczbę wierszy, ale w wierszu znajduje się duża wartość procentowa, to znaczy, że jest to wskaźnik usterki służący do dokładnego zbadania, aby znaleźć sposób ograniczenia liczby rejestracji dla tego objawu usterki.

![Rysunek 3.](media/08-controlling-and-reporting.png)

**Grupowanie według dwóch objawów, składnika majątku i typu składnika majątku**

W poniższym zrzucie ekranu dodano **Obszar** do **Objaw**, **Składnik majątku** i **Typ składnika majątku**, co daje więcej szczegółowych informacji dotyczących rejestracji błędów.

- Jeśli w kolumnie **Prawdopodobieństwo (%)** zostaną dodane wszystkie wartości procentowe dla odpowiednich kombinacji **Składnik majątku** / **Typ składnika majątku** / **Objaw** dla danego składnika majątku, to wartości sumują się do 100%. W tej analizie błędów prawdopodobieństwo jest oparte na kombinacji **Objaw** i **Obszar**. Jeśli składnik majątku zawiera dużą liczbę wierszy, ale w wierszu wyróżnia się duża wartość procentowa, to znaczy, że jest to wskaźnik obszaru usterki służący do dokładnego zbadania, aby znaleźć sposób ograniczenia liczby rejestracji dla tego obszaru usterki.  

![Rysunek 4.](media/09-controlling-and-reporting.png)

**Grupowanie według trzech objawów, składnika majątku i typu składnika majątku**

W poniższym zrzutie ekranu dodano **Typ**, a w tym przykładzie jest pokazane najbardziej szczegółowe obliczenie.
 
- Jeśli w kolumnie **Prawdopodobieństwo (%)** zostaną dodane wszystkie wartości procentowe dla odpowiednich kombinacji **Składnik majątku** / **Typ składnika majątku** / **Objaw** dla danego składnika majątku, to wartości sumują się do 100%. W tej analizie błędów prawdopodobieństwo jest oparte na kombinacji **Objaw**, **Obszar** i **Typ** Jeśli składnik majątku zawiera dużą liczbę wierszy, ale w wierszu wyróżnia się duża wartość procentowa, to znaczy, że jest to wskaźnik typu usterki służący do dokładnego zbadania, aby znaleźć sposób ograniczenia liczby rejestracji dla tego typu usterki.

![Rysunek 5.](media/10-controlling-and-reporting.png)


>[!NOTE]
>Aby zapoznać się z omówieniem wszystkich rejestracji błędów utworzonych na zleceniach pracy i żądaniach konserwacji kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Usterki składnika majątku**. Na stronie **Usterki składnika majątku** wybierz rejestrację usterek składnika majątku i rozwiń okienko **Informacje pokrewne**, aby wyświetlić informacje dotyczące powiązanego zlecenia pracy lub żądania konserwacji.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]