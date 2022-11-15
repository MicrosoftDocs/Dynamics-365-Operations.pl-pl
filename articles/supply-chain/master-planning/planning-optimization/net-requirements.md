---
title: Wymagania netto i informacje oznaczania transakcji
description: Ten artykuł zawiera informacje dotyczące obliczonego zapotrzebowania netto i informacji o oznaczaniu transakcji w ramach.
author: t-benebo
ms.date: 7/28/2021
ms.topic: article
ms.search.form: ReqTransOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a31ff5490b08d92f0d966388b65de02bca25b050
ms.sourcegitcommit: 613be2f35e600ae1a1fa7ea2ae30e78984ca398a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2022
ms.locfileid: "9748446"
---
# <a name="net-requirements-and-pegging-information"></a>Wymagania netto i informacje oznaczania transakcji

[!include [banner](../../includes/banner.md)]

Podczas uruchamiania planowania głównego ważne jest, aby zrozumieć, jaka jest wydajność, w jaki sposób istniejąca podaż pokrywa popyt i dlaczego została wygenerowana specyficzna podaż. Strona **Zapotrzebowanie netto** pozwala lepiej zrozumieć obliczone zapotrzebowanie, które generuje planowanie główne.

Na stronie **Zapotrzebowanie netto** pokazano zapotrzebowanie netto, które obliczono dla planowania głównego. Zawiera również ustawienia zapotrzebowania, które zostały zastosowane podczas planowania głównego, podział sum zapotrzebowania według typów transakcji i informacje o oznaczaniu transakcji.

## <a name="open-the-net-requirements-page"></a>Otwieranie strony Zapotrzebowanie netto

Stronę **Zapotrzebowanie netto** można otworzyć na jeden z następujących sposobów:

- Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**. Wybierz lub otwórz produkt. Następnie w okienku akcji na karcie **Plan** w grupie **Zapotrzebowanie** wybierz pozycję **Zapotrzebowanie netto**.
- Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**. Otwórz zamówienie sprzedaży. Następnie na skróconej karcie **Wiersze zamówienia sprzedaży** na pasku narzędzi wybierz pozycję **Produkt i dostawa \> Zapotrzebowanie netto**.
- Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Zamówienia planowane**. Wybierz lub otwórz zamówienie planowane. Następnie w okienku akcji na karcie **Widok** w grupie **Zapotrzebowanie** wybierz pozycję **Profil zapotrzebowania**.

## <a name="use-the-net-requirements-page"></a>Używawnie strony Zapotrzebowanie netto

Strona **Zapotrzebowanie netto** składa się z sekcji górnej i dolnej. Okienko akcji na tej stronie zawiera przycisk **Aktualizuj**. Po wybraniu tego przycisku zostanie wyświetlone menu poleceń.

### <a name="select-a-master-plan-to-view"></a>Wybierz plan główny do wyświetlenia

Przed przejrzeniem zapotrzebowania netto produktu należy wybrać odpowiedni plan główny w polu **Plan** u góry strony.

### <a name="upper-section"></a>Górna sekcja

W górnej sekcji strony znajdują się następujące karty:

- **Przegląd** — umożliwia wyświetlanie zapotrzebowania na pozycje dla wymiarów produktu.
- **Zapotrzebowanie na towar** — służy do wyświetlania ustawień zapotrzebowania, które zostały użyte podczas obliczania zapotrzebowania.
- **Podsumowanie** — umożliwia wyświetlanie podziału sum zapotrzebowania według typów transakcji.
- **Okres** — umożliwia wyświetlanie przyjęć, wydań i prognozowanych dostępnych zapasów dla wszystkich okresów zdefiniowanych w szablonie okresu. Można także uzyskać graficzny widok prognozowanych dostępnych zapasów.

### <a name="lower-section"></a>Dolna sekcja

W dolnej sekcji strony znajdują się następujące karty:

- **Przegląd** — umożliwia wyświetlenie listy zapotrzebowania na produkty, które obliczono podczas planowania głównego, wraz z transakcjami wydania i przyjęciom odpowiadającymi zamówieniom. Domyślnie lista jest sortowana według daty zapotrzebowania. Po wybraniu zapotrzebowania skrócona karta **Oznaczanie transakcji** w dolnej sekcji pokazuje albo źródło zapotrzebowania albo transakcje, które spełniają zapotrzebowanie.
- **Ogólne** — umożliwia wyświetlenie szczegółowych informacji o wybranym zapotrzebowaniu.
- **Akcja** — umożliwia wyświetlanie komunikatów akcji dotyczących zapotrzebowania.

### <a name="the-action-pane"></a>Okienko akcji

W okienku akcji są dostępne następujące polecenia:

- **Aktualizuj \> Planowanie główne** — uruchom planowanie główne bezpośrednio ze strony **Zapotrzebowanie netto**.
- **Aktualizuj \> Planowanie prognozy** — uruchom planowanie prognozy bezpośrednio ze strony **Zapotrzebowanie netto**. Optymalizacja planowania nie obsługuje jeszcze tej operacji.
- **Aktualizuj \> Planowanie sprzedaży ciągłej** — uruchom planowanie sprzedaży ciągłej bezpośrednio ze strony **Zapotrzebowanie netto**. Optymalizacja planowania nie obsługuje jeszcze tej operacji.

## <a name="example-scenario"></a>Przykładowy scenariusz

W tym przykładzie pokazano, jak informacje o oznaczaniu transakcji są prezentowane na stronie **Zapotrzebowanie netto**.

### <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem pracy z tym scenariuszem użycia przygotuj następujące wymagania wstępne:

1. Musisz pracować w systemie, w którym są dostępne standardowe przykładowe dane, a firma musi mieć ustawioną wartość *USMF*.
2. W tym przykładzie użyto produktu *1000*, który jest częścią przykładowych danych USMF. Upewnij się, że ten produkt jest dostępny i że jest ustawiony w następujący sposób:

    - **Domyślny typ zamówienia:** *Zamówienie zakupu*
    - **Dostępne zapasy:** *10,00*

3. Utwórz zamówienie sprzedaży dla ilości *25,00* produktu *1000*. Użyj wymiarów magazynowania, w których są zlokalizowane dostępne zapasy.
4. Uruchom planowanie główne dla planu głównego *DynPlan*.

### <a name="review-the-calculated-requirements"></a>Przeglądanie obliczonego zapotrzebowania

Następnie zostanie otwarta strona **Zapotrzebowanie netto** dla produktu *1000* w celu sprawdzenia, w jaki sposób obliczone wartości zapotrzebowania odpowiadają sobie.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz produkt z polem **Numer pozycji** równym *1000*.
1. W okienku akcji na karcie **Plan** w grupie **Zapotrzebowanie** wybierz pozycję **Zapotrzebowanie netto**.
1. Na stronie **Zapotrzebowanie netto** w polu **Plan** ustaw wartość *DynPlan*.
1. Na karcie **Przegląd** w dolnej części strony sprawdź, czy poniższe zapotrzebowania są wymienione jako wiersze w siatce.

    | Odwołanie | Ilość zapotrzebowania | Narastająco |
    |---|---|---|
    | Dostępne zapasy | 10,00 | 10,00 |
    | Planowane zamówienia zakupu | 15.00 | 25.00 |
    | Zamówienie sprzedaży | -25,00 | (Puste) |

    > [!NOTE]
    > Pole **Ilość zapotrzebowania** reprezentuje całkowitą ilość wymaganą przez zapotrzebowanie (jeśli wartość jest ujemna) lub dostawy (jeśli ta wartość jest dodatnia). Pole **Skumulowane** zawiera sumę ilości przyjęć i wydań, które narastają w wybranym okresie.

1. Zaznacz wiersz zapotrzebowania *Dostępne zapasy*, a następnie na skróconej karcie **Oznaczanie transakcji** przejrzyj wymagania, które są objęte tą dostawą. Powinien tam zostać wyświetlony następujący wiersz.

    | Odwołanie | Ilość zapotrzebowania | Pokryta ilość |
    |---|---|---|
    | Zamówienie sprzedaży | -25,00 | -10,00 |

    Istniejące dostępne zapasy częściowo pokrywają zapotrzebowanie z zamówienia sprzedaży.

    ![Informacje o oznaczaniu transakcji dla dostępnych zapasów](media/pegging-on-hand.png "Informacje o oznaczaniu transakcji dla dostępnych zapasów")

1. Zaznacz wiersz zapotrzebowania *Planowane zamówienie zakupu*, a następnie na skróconej karcie **Oznaczanie transakcji** przejrzyj wymagania, które są objęte tą dostawą. Powinien tam zostać wyświetlony następujący wiersz.

    | Odwołanie | Ilość zapotrzebowania | Pokryta ilość |
    |---|---|---|
    | Zamówienie sprzedaży | -25,00 | -15,00 |

    Ponieważ zamówienie sprzedaży zostało już częściowo pokryte, system tworzy planowane zamówienie zakupu dla pozostałej ilości bez pokrycia.

    ![Informacje o oznaczaniu transakcji dla planowanego zamówienia zakupu](media/pegging-planned-purchase-order.png "Informacje o oznaczaniu transakcji dla planowanego zamówienia zakupu")

1. Zaznacz wiersz zapotrzebowania *Zamówienie sprzedaży*, a następnie na skróconej karcie **Oznaczanie transakcji** przejrzyj zapotrzebowanie pokrywające ten popyt. Powinny tam zostać wyświetlone następujące wiersze.

    | Odwołanie | Ilość zapotrzebowania | Pokryta ilość |
    |---|---|---|
    | Dostępne zapasy | 10,00 | 10,00 |
    | Planowane zamówienia zakupu | 15.00 | 15.00 |

    ![Informacje o oznaczaniu transakcji dla zamówienia sprzedaży](media/pegging-planned-purchase-order.png "Informacje o oznaczaniu transakcji dla zamówienia sprzedaży")

> [!NOTE]
> Typ *zapotrzebowania na zapas bezpieczeństwa* nie jest uwzględniony na stronie **Zapotrzebowanie netto**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
