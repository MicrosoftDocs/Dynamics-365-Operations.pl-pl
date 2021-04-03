---
title: Ustawianie różnych wymiarów pakowania i przechowywania
description: W tym temacie pokazano, jak określić, do którego procesu (pakowanie, przechowywanie lub zagnieżdżone pakowanie) będzie używany każdy określony wymiar.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: aa5cbf807e809238489c539d3ad8c0bc34421774
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501301"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a>Ustawianie różnych wymiarów pakowania i przechowywania

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Niektóre towary są pakowane lub przechowywane w taki sposób, że konieczne może być śledzenie wymiarów fizycznych w inny sposób dla każdego z kilku różnych procesów. Funkcja *wymiarów produktu do pakowania* umożliwia skonfigurowanie jednego lub kilku typów wymiarów dla każdego produktu. Każdy typ wymiaru ma zestaw miar fizycznych (waga, szerokość, głębokość i wysokość) i ustala proces, w którym te wartości miar fizycznych mają zastosowanie. Gdy ta funkcja jest włączona, system obsługuje następujące typy wymiarów:

- *Przechowywanie* — wymiary magazynowania są używane razem z danymi wolumetrycznymi lokalizacji w celu określenia, ile każdego towaru można przechowywać w różnych lokalizacjach magazynowych.
- *Pakowanie* — wymiary pakowania są używane podczas konteneryzacji i ręcznego procesu pakowania w celu określenia, ile każdego towaru dopasuje się do różnych typów kontenerów.
- *Zagnieżdżone pakowanie* — zagnieżdżone wymiary pakowania są używane, gdy proces pakowania zawiera wiele poziomów.

Wymiany *magazynowania* są obsługiwane, nawet jeśli funkcja *Wymiary produktu do pakowania* nie jest włączona. Te ustawienia są ustawiane za pomocą strony **Wymiar fizyczny** w aplikacji Supply Chain Management. Te wymiary są używane przez wszystkie procesy, w których nie określono wymiarów pakowania i zagnieżdżonych wymiarów pakowania.

Wymiary *pakowania* i *zagnieżdżonego pakowania* są ustawiane za pomocą strony **Fizyczne wymiary produktu**, która jest dodawana po włączeniu funkcji *wymiarów produktu do pakowania*.
Ten temat zawiera scenariusz, który ilustruje sposób używania tej funkcji.

## <a name="turn-on-the-packaging-product-dimensions-feature"></a>Włączanie funkcji wymiarów produktu opakowania

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Wymiary produktu do pakowania*

## <a name="example-scenario"></a>Przykładowy scenariusz

### <a name="set-up-the-scenario"></a>Konfiguracja scenariusza

Przed uruchomieniem przykładowego scenariusza należy przygotować system w sposób opisany w tej sekcji.

#### <a name="enable-demo-data"></a>Włączanie danych pokazowych

Aby pracować z tym scenariuszem przy użyciu określonych pokazowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane pokazowe](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę *USMF* przed rozpoczęciem.

#### <a name="add-a-new-physical-dimension-to-a-product"></a>Dodawanie nowego wymiaru fizycznego do produktu

Dodaj nowy wymiar fizyczny dla produktu, wykonując następujące czynności:

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz produkt z **numerem pozycji** *A0001*.
1. W okienku akcji otwórz kartę **Zarządzaj zapasami** i w grupie **Magazyn** wybierz **Wymiary fizyczne produktu**.
1. Zostanie otwarta strona **Wymiary fizyczne produktu**. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wymiar do siatki, używając następujących ustawień:
    - **Typ wymiaru fizycznego** - *Pakowanie*
    - **Jednostka fizyczna** - *sztuki*
    - **Waga** - *4*
    - **Jednostka wagi** - *kg*
    - **Długość** - *3*
    - **Wysokość** - *4*
    - **Szerokość** - *3*
    - **Długość** - *cm*
    - **Jednostka objętości** - *cm3*

Pole **Objętość** jest obliczane automatycznie na podstawie ustawień **głębokości**, **wysokości** i **szerokości**.

#### <a name="create-a-new-container-type"></a>Tworzenie nowego typu kontenera

Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Typy kontenerów** i utwórz nowy rekord z następującymi ustawieniami:

- **Kod typu kontenera** - *Pudełko krótkie*
- **Opis** - *Pudełko krótkie*
- **Maksymalna waga netto** - *50*
- **Objętość** - *144*
- **Długość** - *6*
- **Szerokość** - *6*
- **Wysokość** - *4*

#### <a name="create-a-container-group"></a>Tworzenie grupy kontenerów

Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Grupy kontenerów** i utwórz nowy rekord z następującymi ustawieniami:

- **Identyfikator grupy kontenerów** - *Pudełko krótkie*
- **Opis** - *Pudełko krótkie*

Dodaj nowy wiersz do sekcji **Szczegóły**. Ustaw **typ kontenera** na *Pudełko krótkie*.

#### <a name="set-up-a-container-build-template"></a>Ustawianie szablonu kompilacji kontenera

Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Szablony kompilacji kontenerów** i wybierz pozycję **Pudełka**. Zmień **identyfikator grupy kontenerów** na *Pudełko krótkie*.

### <a name="run-the-scenario"></a>Uruchamianie scenariusza

Po przygotowaniu systemu zgodnie z opisem w poprzedniej sekcji można rozpocząć scenariusz opisany w następnej sekcji.

#### <a name="create-a-sales-order-and-create-a-shipment"></a>Tworzenie zamówienia sprzedaży i tworzenie wysyłki

W tym procesie można utworzyć wysyłkę na podstawie wymiarów *pakowania* towarów, dla których wysokość jest mniejsza niż 3.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *63*

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Powinno zawierać pusty wiersz w siatce na skróconej karcie **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *5*

1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.
1. Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.
1. Zamknij stronę.
1. W okienku akcji otwórz kartę **Magazyn** i wybierz pozycję **Zwolnij do magazynu**, aby utworzyć pracę dla magazynu.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Magazyn \> Szczegóły wysyłki**.
1. W okienku akcji otwórz kartę **Transport** i wybierz opcję **Wyświetl kontenery**. Potwierdź, że towar został przeniesiony do dwóch kontenerów *Pudełko krótkie*.

#### <a name="place-an-item-into-storage"></a>Umieszczanie pozycji w magazynie

1. Otwórz urządzenie przenośne, zaloguj się do magazynu 63 i przejdź do pozycji **Zapasy \> Dostosuj w**.
1. Wprowadź **lokalizację** = *SHORT-01*. Utwórz nowy numer identyfikacyjny z **pozycją** = *A0001* i **ilością** = *1 szt.*
1. Kliknij przycisk **OK**. Pojawi się błąd „Niepowodzenie lokalizacji SHORT-01, pozycja A0001 nie pasuje do wymiarów określonych dla lokalizacji”. Wynika to z tego, że wymiary typu *Magazyn* są większe niż wymiary określone w profilu lokalizacji.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]