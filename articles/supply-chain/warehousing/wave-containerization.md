---
title: Konteneryzacja
description: W tym temacie opisano sposób zautomatyzowania kontenerów ładunków. Automatyczna konteneryzacja tworzy kontenery i pracę pobrania dla wysyłki podczas przetwarzania grupy czynności.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 3546547bd064835d195a2c6ac7e4eb1d5afc9b00
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838113"
---
# <a name="containerization"></a>Konteneryzacja

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób zautomatyzowania kontenerów ładunków. Automatyczna konteneryzacja tworzy kontenery i pracę pobrania dla wysyłki podczas przetwarzania grupy czynności.

Aby skonfigurować konteneryzację, należy utworzyć następujące elementy:

- **Typ kontenera** ─ Zdefiniuj fizyczne cechy pojemników. Użyj typów kontenera do pakowania towarów magazynowych do opakowań określonego typu i rozmiaru, takich jak pojemniki i palety.
- **Grupy kontenerów** ─ Utwórz grupy typów kontenerów, które są podobne. Na przykład grupa kontenerów może obejmować typy kontenerów mających podobne wymiary rozmiaru. Grupa kontenera określa kolejność pakowania kontenerów i procent wypełnienia każdego kontenera.
- **Szablon kompilacji kontenerów** - Utwórz szablony definiujące reguły tworzenia kontenerów. Na przykład reguły łączenia zapasów i inne strategie pakowania.
- **Szablony grup czynności** — Konfigurowanie jednego lub większej liczby szablonów grupy czynności do tworzenia pracy pobrania dla konteneryzacji.

## <a name="create-wave-templates-for-containerization"></a>Tworzenie szablonu grupy czynności dla konteneryzacji

Należy skonfigurować jeden lub większą liczbę szablonów grupy czynności wysyłki dla konteneryzacji. Szablony grupy czynności obejmują kryteria, które określają następujące elementy:

- Sposób przetwarzania grupy czynności. Może to być przetwarzanie ręczne lub automatyczne.
- Sposób tworzenia pobierania pracy. To zależy od metod grup czynności. Szablon grupy czynności musi zawierać metodę **konteneryzacji**.
- Sposób dopasowywania elementów lub wierszy alokacji do grupy czynności.

Aby uzyskać więcej informacji o szablonach, zobacz temat [Szablony grupy czynności](wave-templates.md).

## <a name="create-container-types"></a>Tworzenie typu kontenera

Użyj typów kontenerów do tworzenia opisów pojemników, uwzględniając maksymalne wartości wymiarów fizycznych rozmiarów i pojemność wagową. Podczas przetwarzania grup czynności kontenerowych kontenery są tworzone na podstawie informacji o typie kontenera.

Aby skonfigurować typ kontenera, należy wykonać następujące czynności:

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Kontenery** \> **Typy kontenerów**.
1. Wybierz pozycję **Nowy**, aby utworzyć nowy typ kontenera.
1. Wprowadź unikatowy identyfikator (ID) i opis typu kontenera.
1. W polu **Tara** wprowadź rzeczywistą lub szacunkową wagę kontenera.
1. W polu **Waga maksymalna** wprowadź maksymalną wagę, którą utrzyma kontener.
1. W polach **Maksymalna objętość konteneryzacji**, **Maksymalna długość konteneryzacji**, **Maksymalna szerokość konteneryzacji** oraz **Maksymalna wysokość konteneryzacji** określ fizyczne wymiary kontenera.

    > [!NOTE]
    > Wartości długości i szerokości są wymienne. Oznacza to, że w razie potrzeby możesz obracać elementy w bok lub na osi X. Na przykład, jeśli długość wynosi 2 stopy, a szerokość 1 stopę, można zmienić długość na 1 stopę, a szerokość na 2 stopy. Należy zauważyć, że to nie ma zastosowania do wysokości. Nie można zmienić wartości wysokości, aby obrócić towar w pionie.

1. Wybierz wartości atrybutów niestandardowych dla kontenera w odpowiednich polach dla atrybutów. Atrybuty są to niestandardowe wartości, które są używane do filtrowania lub sortowania elementów na podstawie wartości, które w innym przypadku nie są dostępne. Na przykład jeśli chcesz spakować towary dla określonego odbiorcy, możesz utworzyć atrybut dla nazwy odbiorcy. Utwórz atrybuty na stronie **Atrybuty kontenera**.

## <a name="create-container-groups"></a>Tworzenie grup kontenerów

Można skonfigurować logiczne grupy typów kontenerów. Dla każdej grupy można określić kolejność pakowania kontenerów oraz procent wypełnienia każdego kontenera. Wymiary rozmiaru towaru są używane do określenia, czy zmieści się on w kontenerze. Używany jest kontener, którym wymiarami jest najbardziej zbliżony do towaru. Jeśli masz wiele typów kontenerów w grupie, zaleca się rozmieszczenie kolejności według rozmiarów, tak, aby największy kontener był pierwszy, numer 1 w sekwencji, a najmniejszy kontener ostatni.

Aby skonfigurować grupę kontenera, należy wykonać następujące czynności:

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Kontenery** \> **Grupy kontenerów**.
1. Wybierz pozycję **Nowy**, aby utworzyć grupę kontenerów.
1. Wprowadź unikatowy identyfikator i opis grupy kontenera.
1. Na skróconej karcie **Szczegóły** kliknij przycisk **Nowy**, aby dodać typ kontenera do grupy.
1. W polu **Kod typu kontenera** wpisz typ kontenera.
1. Wybierz opcję **Przenieś w górę** lub **Przenieś w dół**, aby określić kolejność pakowania typów kontenerów.

## <a name="create-container-build-templates"></a>Utwórz szablon kompilacji kontenera.

Można skonfigurować reguły w procesie tworzenia kontenerów, takie jak reguły łączenia zapasów i inne strategie pakowania zapasów. Na przykład można ustawić regułę, aby pracownicy nie mogli spakować wierszy alokacji, które reprezentują zamówienia sprzedaży od różnych odbiorców w tym samym kontenerze.

Aby skonfigurować szablon kompilacji kontenera, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Kontenery** \> **Szablony kompilacji kontenerów**.
1. Utwórz nowy szablon kompilacji kontenera.
1. W polach **Nazwa konteneryzacji** i **Sekwencja numerów** wprowadź nazwę szablonu konteneryzacji i kolejność, w jakiej zamówienie jest dopasowywane do wierszy alokacji.

    > [!NOTE]
    > System zastosuje pierwszy szablon, którego kryteria kwerendy spełnia wiersz alokacji. Zatem należy umieścić szablon zawierający najlepiej określone kryteria u góry listy. Im szersze kryteria, tym łatwiej wiersz alokacji je spełni. Może to prowadzić do błędnego przypisania wierszy do kontenera. W razie potrzeby można wybrać opcję **Przenieś w górę** lub **Przenieś w dół**, aby zmienić sekwencję szablonów.

1. W polu **Identyfikator grupy kontenerów** wybierz grupę kontenera, z której mają być utworzone kontenery.
1. W polu **Typy podstawowych zapytań** wybierz typ kwerendy, który określi, co należy zapakować i na czym należy oprzeć filtr kwerendy. Dostępne są następujące opcje:

      - **Wiersz alokacji sprzedaży** ─ Wiersze alokacji pakowania tworzone dla zamówień sprzedaży.
      - **Wiersz alokacji transferu** ─ Wiersze alokacji pakowania tworzone dla zamówień przeniesienia.
      - **Kontener** ─ Zapakuj kontener, który został już utworzony przez proces tworzenia kontenerów. Na przykład jest to stosowane do zagnieżdżania kontenerów.

        > [!NOTE]
        > Aby zastosować kontenery zagnieżdżane, należy ustawić powtarzalność metody tworzenia kontenerów. Aby uzyskać więcej informacji o szablonach, zobacz temat [Szablony grupy czynności](wave-templates.md).

1. Na skróconej karcie **Ogólne**, w polu **Kod kroku grupy czynności** wprowadź unikatowy identyfikator metody procesu grupy czynności łączącej szablon kompilacji kontenera z krokami w szablonie grupy czynności.
1. Wybierz pole wyboru **Pozwól na podzielony odbiór**, aby zezwolić pracownikom na pakowanie towarów z zamówienia pracy w oddzielnych kontenerach. W tym celu cała ilość musi mieścić się w kontenerze. Używana jest zawsze największa jednostka miary w wierszu alokacji.
1. W polu **Pakowanie według jednostki** wybierz jednostkę miary, która będzie reprezentować kontener. Na przykład można wskazać, że skrzynia jest kontenerem. Jeśli pakowanie odbywa się według jednostki miary, nie można także określić grupy kontenera, ponieważ jednostka miary jest kontenerem.
1. W polu **Strategia pakowania kontenerów** wybierz strategię pakowania do zastosowania. Dostępne są następujące opcje:

    > [!NOTE]
    > Strategia dotyczy tylko wiersze alokacji sprzedaży i przeniesienia.

      - **Zapakuj do wszystkich wolnych kontenerów** — System sprawdza, czy wiersz alokacji mieści się w dowolnym kontenerze, który został utworzony podczas cyklu tworzenia kontenerów.
      - **Zapakuj tylko do obecnego kontenera** — System sprawdza tylko, czy wiersza alokacji mieści się w kontenerze ostatnio utworzonym.

1. Aby skonfigurować reguły dla wierszy alokacji pakowania w kontenerach, wybierz **Przerwy logiki łączenia**. Na przykład można utworzyć regułę, która będzie pozwalać pracownikom na pakowanie wierszy alokacji dla dwóch różnych elementów w tym samym kontenerze. Aby zdefiniować regułę mieszania, wykonaj następujące kroki:

    1. Na stronie **Przerwy logiki łączenia** wybierz pozycję **Nowy**.
    1. W polu **Tabele** wybierz tabelę zawierającą pole, które ma być używane jako kryterium przerwy logiki łączenia.
    1. W polu **Wybór pola** wybierz pole, które ma być używane jako kryterium przerwy logiki łączenia.
    1. Powtórz te kroki, dopóki nie dodasz wszystkich kryteriów dla przerwy logiki łączenia.

    > [!NOTE]
    > Jeśli używasz logiki łączenia, zaleca się sortować te same pola w kwerendzie kryterium filtru. Zmniejsza to liczbę kontenerów, które zostały utworzone.
