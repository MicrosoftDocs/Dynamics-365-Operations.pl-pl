---
title: Przeliczanie jednostki miary dla wariantów produktów
description: W tym temacie wyjaśniono, jak skonfigurować konwersje jednostek miary dla wariantów produktu. Zawiera przykładową konfigurację.
author: johanhoffmann
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: b9ad41395055d9f63aae8ffa869e0613be330051390955599a95a30869a145dc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713645"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Przeliczanie jednostki miary dla wariantów produktów

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować konwersje jednostek miary dla różnych wariantów produktu.

Zamiast tworzyć wiele pojedynczych produktów, które wymagają obsługi, można użyć wariantów produktu w celu utworzenia różnych wariantów jednego produktu. Na przykład wariantem produktu może być koszulka w danym rozmiarze i kolorze.

Wcześniej konwersje jednostek można było konfigurować tylko na poziomie produktu głównego. Dlatego wszystkie warianty produktu miały takie same reguły konwersji jednostek. Jeśli jednak funkcja *Konwersje jednostki miary dla wariantów produktów* jest włączona, a koszulki są sprzedawane w pudełkach i liczba koszulek, które można zapakować do pudełka, zależy od rozmiaru koszulki, można teraz skonfigurować konwersję jednostek między różnymi rozmiarami koszulek a pudełkami używanymi do pakowania.

## <a name="turn-on-the-feature-in-your-system"></a>Włączanie funkcji w systemie

Jeśli ta funkcja nie jest jeszcze widoczna w systemie, przejdź do tematu [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Konwersje jednostki miary dla wariantów produktów*.

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Konfigurowanie produktu pod katem konwersji jednostek dla wariantu produktu

Warianty produktów można tworzyć tylko dla produktów głównych. Aby uzyskać więcej informacji, zobacz temat [Tworzenie produktu głównego](tasks/create-product-master.md). Funkcja *Konwersje jednostki miary dla wariantów produktów* jest niedostępna dla produktów skonfigurowanych dla procesów obsługi ilości efektywnej.

Aby skonfigurować produkt główny w celu obsługi konwersji jednostek na wariant, wykonaj następujące kroki.

1. Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Produkty \> Produkty główne**.
1. Utwórz lub otwórz produkt główny, aby przejść do jego strony **Szczegóły produktu**.
1. Ustaw opcję **Włącz konwersje jednostek miary** na wartość *Tak*.
1. W okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz pozycję **Konwersje jednostek**.
1. Zostanie otwarta strona **Konwersje jednostek**. Wybierz jedną z następujących kart:

    - **Przeliczenia wewnątrz klasy** — tę kartę należy wybrać, aby dokonać konwersji między jednostkami należącymi do tej samej klasy jednostek.
    - **Przeliczenia między klasami** — tę kartę należy wybrać, aby dokonać konwersji między jednostkami należącymi do różnych klas jednostek.

1. Wybierz pozycję **Nowa**.
1. Ustaw pole **Utwórz konwersję dla** na jedną z następujących wartości:

    - **Produkt** — wybranie tej wartości umożliwi skonfigurowanie konwersji jednostek dla produktu głównego. Ta konwersja jednostek będzie używana jako rezerwowa dla wszystkich wariantów produktu, dla których nie zdefiniowano żadnej konwersji jednostek.
    - **Wariant produktu** — wybranie tej wartości umożliwi skonfigurowanie konwersji jednostek dla określonego wariantu produktu. Użyj pola **Wariant produktu**, aby wybrać wariant.

    ![Dodawanie nowej konwersji jednostek.](media/uom-new-conversion.png "Dodawanie nowej konwersji jednostek")

1. Aby skonfigurować konwersję jednostek, skorzystaj z dostępnych pól.
1. Wybierz przycisk **OK**, aby zapisać nową konwersję jednostek.

> [!TIP]
> Stronę **Konwersja jednostek** dla produktu lub wariantu produktu można otworzyć z dowolnej z następujących stron:
> 
> - Szczegóły produktu
> - Szczegóły zwolnionych produktów
> - Zwolnione warianty produktu

## <a name="example-scenario"></a>Przykładowy scenariusz

W tym scenariuszu firma sprzedaje T-shirty w rozmiarach Mały, Średni, Duży i Bardzo duży. T-shirt jest definiowany jako produkt, a różne rozmiary są definiowane jako warianty tego produktu. Koszulki są pakowane w pudełka. W przypadku rozmiarów Mały, Średni i Duży w każdym pudełku może znajdować się pięć koszulek. Jednak w przypadku rozmiaru Bardzo duży w każdym pudełku mieszczą się tylko cztery koszulki.

Firma chce śledzić różne warianty w jednostce *Sztuki*, ale sprzedaje T-shirty w jednostkach *Pudełka*. W przypadku rozmiarów Mały, Średni i Duży konwersja między jednostką zapasów i jednostką sprzedaży to 1 pudełko = 5 sztuk. W przypadku rozmiaru Bardzo duży konwersja to 1 pudełko = 4 sztuki.

1. Na stronie **Szczegóły zwolnionego produktu** produktu **T-Shirt** otwórz stronę **Konwersje jednostek**.
1. Na stronie **Konwersje jednostek** ustaw następującą konwersję jednostek dla wariantu zwolnionego produktu **Bardzo duży**.

    | Pole                 | Ustawienie                 |
    |-----------------------|-------------------------|
    | Utwórz konwersję dla | Wariant produktu         |
    | Wariant produktu       | T-Shirt : : X-Large : : |
    | Od jednostki             | Pola                   |
    | Współczynnik                | 4                       |
    | Do jednostki               | Sztuki                  |

1. Ponieważ warianty produktu **Mały**, **Średni** i **Duży** mają tę samą konwersję jednostki między jednostkami *Pudełko* i *Sztuki*, możesz zdefiniować następującą konwersję jednostek dla tych wariantów w produkcie głównym.

    | Pole                 | Ustawienie |
    |-----------------------|---------|
    | Utwórz konwersję dla | Produkt |
    | Produkt               | T-Shirt |
    | Od jednostki             | Pola   |
    | Współczynnik                | 5       |
    | Do jednostki               | Sztuki  |

## <a name="using-excel-to-update-the-unit-conversions"></a>Aktualizowanie konwersji jednostek przy użyciu programu Excel

Jeśli produkt ma wiele wariantów z różnymi konwersjami jednostek, dobrym pomysłem jest wyeksportowanie konwersji jednostek do skoroszytu programu Microsoft Excel, zaktualizowanie ich i ponowne opublikowanie w aplikacji Dynamics 365 Supply Chain Management.

Aby wyeksportować konwersje jednostek do programu Excel, na stronie **Konwersje jednostek** w okienku akcji wybierz pozycję **Otwórz w pakiecie Microsoft Office**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zarządzanie jednostkami miary](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]