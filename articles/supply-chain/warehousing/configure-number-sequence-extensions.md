---
title: Konfigurowanie sekwencji identyfikatorów dla przepływów magazynowych
description: W tym temacie opisano funkcje, które umożliwiają obsługę rozszerzeń sekwencji identyfikatorów dla numerów identyfikacyjnych, identyfikatorów etykiet grupy czynności, identyfikatorów kontenerów i identyfikatorów list przewozowych.
author: GarmMSFT
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSNumberSequenceExt
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: fa4074c23baa74983f4922d2d09d7da81c943bfe
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973842"
---
# <a name="configure-number-sequences-for-warehouse-flows"></a>Konfigurowanie sekwencji identyfikatorów dla przepływów magazynowych

[!include [banner](../includes/banner.md)]

Funkcja *Rozszerzeń sekwencji identyfikatorów* umożliwia dodanie nowej strony konfiguracji w celu skonfigurowania sekwencji identyfikatorów. Umożliwia ona elastyczne konfigurowanie identyfikatorów GS1, w tym prefiksów GS1 i cyfr kontrolnych (modulo 10), a także wymusza limit długości istniejących sekwencji iedntyfikatorów.

Standardowe segmenty sekwencji identyfikatorów nie są odpowiednie do implementacji GS1, ponieważ nie jest obliczana żadna cyfra kontrolna, a prefiks GS1 firmy musi zostać zaktualizowany ręcznie.

Ta funkcja dodaje następującą funkcjonalność:

- Identyfikatory listów przewozowych mogą być generowane z góry.
- Unikatową sekwencję identyfikatorów można wygenerować dla numerów numeru kodu kontenera wysyłkowego (SSCC)
- Sekwencje identyfikatorów zgodne z GS1 można tworzyć dla numerów listów przewozowych i SSCC. Funkcja ta dodaje gotowe wsparcie dla numerów identyfikacyjnych, identyfikatorów kontenerów, identyfikatorów etykiet grup czynności i identyfikatorów listów przewozowych.
- Konfiguracja numerów identyfikacyjnych jest elastyczna. Można na przykład uwzględnić lub wykluczyć identyfikatory aplikacji (AI), np. zera wiodące (00).

Ta funkcja zwiększa efektywność etykietowania kartonów oraz dostosowuje nowe numery generowane przez system.

## <a name="turn-on-the-number-sequence-extensions-feature"></a>Włącz funkcję rozszerzeń sekwencji identyfikatorów

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Rozszerzenia sekwencji identyfikatorów*

## <a name="set-up-the-feature"></a>Konfiguracja funkcji

Aby skonfigurować rozszerzenia sekwencji identyfikatorów w systemie, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na karcie **Ogólne**, w polu **Prefiks firmy GS1** i wprowadź prefiks GS1 firmy. Ta wartość będzie mieć wpływ na wszystkie sekwencje identyfikatorów, w których prefiks GS1 jest uwzględniony jako segment.
1. Jeśli chcesz wygenerować numery list przewozowy dla etykiet grupy czynności, na karcie **Raporty** zaznacz pole wyboru **Generuj numer listu przewozowego podczas drukowania etykiet grup czynności**.

    > [!NOTE]
    > To pole wyboru jest dostępne tylko wtedy, gdy jest włączona funkcja drukowania [etykiet grupy czynności](configure-wave-label-printing.md).

1. Przejdź do **Zarządzanie magazynem** \> **Konfiguracja** \> **Rozszerzenia sekwencji identyfikatorów**
1. W okienku akcji wybierz **Utwórz konfigurację domyślną**. Zostanie utworzona sekwencja identyfikatorów listów przewozowych zgodna z GS1 i trzy typy sekwencji identyfikatorów SSCC. Wszystkie te sekwencje identyfikatorów zajmują długość prefiksu firmy GS1.

    Aby uzyskać więcej informacji o dostosowywaniu domyślnych sekwencji identyfikatorów i/lub dodawaniu nowych sekwencji, zapoznaj się z następną sekcją. Można również usunąć dowolną z tych sekwencji, jeśli nie są one potrzebne.

1. Wróć do **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na karcie **Sekwencje identyfikatorów** wybierz odpowiednie rozszerzenie sekwencji identyfikatorów, które ma być używane do generowania numerów identyfikacyjnych, identyfikatorów etykiet grup czynności, identyfikatorów kontenerów (w tym przypadku należy wybrać odpowiednią sekwencję **identyfikatorów SSCC-18**) i/lub identyfikatory listów przewozowych (w tym przypadku należy wybrać sekwencję **List przewozowy**). Domyślnie rozszerzenia sekwencji identyfikatorów są obsługiwane tylko dla tych czterech typów identyfikatorów.

Jeśli dla jednej z tych sekwencji identyfikatorów zostanie wygenerowany nowy identyfikator, zostanie użyta nowa logika.

> [!NOTE]
> Jeśli nie zostanie wybrane rozszerzenie sekwencji numerów dla identyfikatorów numeru identyfikacyjnego, zostaną użyte bieżące reguły generowania numerów identyfikacyjnych. W przeciwnym razie zostanie użyta wybrana sekwencja identyfikatorów. Inne identyfikatory będą używały zwykłej sekwencji identyfikatorów do momentu zastosowania rozszerzenia sekwencji identyfikatorów.

## <a name="create-and-edit-number-sequences"></a>Tworzenie i edytowanie sekwencji identyfikatorów

W poprzedniej sekcji wygenerowano domyślny zbiór sekwencji identyfikatorów. W tej sekcji wyjaśniono sposób definiowania poszczególnych sekwencji identyfikatorów. Omówiono również sposób tworzenia sekwencji niestandardowych i edytowania sekwencji domyślnej lub niestandardowej.

Aby utworzyć i edytować sekwencje identyfikatorów, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie magazynem** \> **Konfiguracja** \> **Rozszerzenia sekwencji identyfikatorów**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Rozszerzenie sekwencji identyfikatorów** wprowadź nazwę nowej sekwencji. W polu **Opis wprowadź** opis.
1. Na skróconej karcie **Segmenty** przyciski na pasku narzędzi służą do tworzenia formatu numerowania przez dodawanie, usuwanie i rozmieszczanie segmentów. W polu **Segment** dla każdego wiersza przypisz typ segmentu, aby zdefiniować cel i zawartość segmentu. W poniższej tabeli opisano typy segmentów, które są dostępne.

    | Typ segmentu | opis |
    |---|---|
    | Stała | Ten typ segmentu dodaje ten sam stały tekst dla każdego wygenerowanego identyfikatora w sekwencji. W polu **Wartość** wprowadź wymagany tekst. Pole **Długość** jest automatycznie aktualizowane do długości tekstu wprowadzonego w polu **Wartość**. |
    | Sekwencja numerów | W polu **Wartość** wprowadź znak numeru (*\#*) dla każdego znaku, który ma być pokazywany w wygenerowanej kolejności. Sama sekwencja identyfikatorów może generować dłuższe liczby, ale tylko znaki z prawej strony będą wyświetlane. Pole **Długość** jest automatycznie aktualizowane do liczby znaków identyfikatora wprowadzonego w polu **Wartość**.<p>Aby zachować zgodność z wymaganiami GS1 dotyczącymi numerów SSCC-18, upewnij się, że długość tego segmentu wynosi 16 minus długość prefiksu GS1.</p> |
    | Prefiks kodu GS1 | Ten typ segmentu umożliwia dodanie wartości ustawionej w polu **Prefiks firmy GS1** na stronie **Parametry zarządzania magazynem**. W polu **Wartość** wyświetlana jest wartość ustawiona na stronie **Parametry zarządzania magazynem**, a w polu **Długość** wyświetlana jest liczba znaków w wartości. Pola **Wartość** i **Długość** są tylko do odczytu. |
    | Identyfikator aplikacji | W polu **Wartość** wprowadź identyfikator aplikacji określony w odpowiednich zasadach GS1 dla tego typu sekwencji identyfikatorów. Na przykład wprowadź wartość *00* dla SSCC lub *420* dla listu przewozowego. Pole **Długość** jest automatycznie aktualizowane do długości identyfikatora wprowadzonego w polu **Wartość**. |
    | Typ opakowania | W przypadku towarów, które można jasno zidentyfikować, ten typ segmentu powoduje dodanie wartości pola z odpowiedniej grupy sekwencji jednostek (ze strony **Grupy sekwencji jednostek**). (To zachowanie jest zgodne z istniejącą logiką dla numerów identyfikacyjnych.) W przypadku numerów identyfikacyjnych zawierających wiele jednostek magazynowych (SKU) ten typ segmentu domyślnie dodaje wartość *0* (zero). W przypadku tego typu segmentu pole **Wartość** jest zawsze ustawione na wartość *P*, a pole **Długość** zawsze ma wartość *1*.|
    | Cyfra kontrolna | W tym typie segmentu jest dodawana cyfra kontrolna, czyli obliczenie modulo 10. (To zachowanie jest zgodne z istniejącą logiką dla identyfikatorów numerów identyfikacyjnych.) W przypadku tego typu segmentu pole **Wartość** jest zawsze ustawione na znak daszka (*^*), a pole **Długość** zawsze ma wartość *1*. |

1. Aby wyświetlić przykład końcowego formatu numerów, należy sprawdzić pole **Format** w dolnej części skróconej karty **Segmenty**.
