---
title: Omówienie zarządzania zmianami inżynieryjnymi (zawiera wideo)
description: Ten artykuł zawiera omówienie zarządzania zmianami inżynieryjnymi, które pomaga w planowaniu i zarządzaniu wersjami produktów oraz zarządzaniu cyklami życia produktu i zmianami inżynieryjnymi.
author: t-benebo
ms.date: 08/09/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a01dfd72428c75d1bb24f32c73c9c799a6c5017e
ms.sourcegitcommit: b3579ac62e1ea15664a114abcc2409cad76d4f19
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2022
ms.locfileid: "9682514"
---
# <a name="engineering-change-management-overview"></a>Omówienie zarządzania zmianami inżynieryjnymi

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Podsumowanie funkcji

Dzisiejsi producenci potrzebują zaawansowanych funkcji zarządzania danymi produktów, kontroli wersji i zarządzania zmianami inżynieryjnymi, aby odnieść sukces w świecie ciągle skracanych cykli życia produktów, zwiększonych wymagań dotyczących jakości i niezawodności oraz zwiększonego nacisku na bezpieczeństwo produktów.

Zarządzanie zmianami inżynieryjnymi umożliwia tworzenie struktury i dyscypliny w procesie zarządzania danymi produktów, a ponadto umożliwia definiowanie, zwalnianie i korygowanie produktów w sposób kontrolowany, który jest obsługiwany przez przepływy pracy. Dzięki wersjom produktów i zarządzaniu zmianami inżynieryjnymi możesz dokumentować i wprowadzać zmiany inżynieryjne oraz oceniać ich wpływ w całym cyklu życia produktu.

Zarządzanie zmianami inżynieryjnymi pomaga w planowaniu i zarządzaniu wersjami produktów oraz zarządzaniu cyklami życia produktu i zmianami inżynieryjnymi. Poniżej znajduje się lista funkcji głównych:

- Przechowywanie wersji produktów
- Ulepszona funkcjonalność wydania produktu, która umożliwia utrzymywanie danych podstawowych produktu w jednej firmie (firmie inżynierskiej) i publikowanie w pełni skonfigurowanego wydanego produktu innym firmom
- Zasady sprawdzania, czy wymagane informacje zostały wprowadzone przed aktywacją wersji produktu (kontrola gotowości)
- Udoskonalone zarządzanie cyklem życia produktu dzięki kontroli szczegółowej, gdy zwolniony produkt może być używany w konkretnych procesach biznesowych
- Żądania zmian inżynieryjnych obsługiwane przez przepływy pracy
- Zamówienia zmian inżynieryjnych obsługiwane przez przepływy pracy

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HE6B]

Poprzednie wideo ([Możliwości zarządzania zmianami w Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) znajduje się na liście odtwarzania [aplikacje finansowe i operacyjne - playlista](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na platformie YouTube.

## <a name="turn-on-the-engineering-change-management-features-for-your-system"></a>Włącz funkcje zarządzania zmianami inżynieryjnymi w systemie

Aby można było używać funkcji zarządzania zmianami inżynieryjnymi, należy włączyć zarówno funkcję *Zarządzania zmianami inżynieryjnymi*, jak i jej klucz konfiguracji. Jeśli chcesz również śledzić wymiar wersji produktów w transakcjach (opcjonalnie), musisz również włączyć zarówno funkcję *Wymiar wersji produktu*, jak i jej klucz konfiguracji. Po skonfigurowaniu tych wstępnych wymagań można włączyć dodatkowe opcjonalne funkcje zarządzania zmianami inżynieryjnych.

### <a name="turn-the-basic-engineering-change-management-features-on-or-off"></a>Włącz lub wyłącz podstawowe funkcje zarządzania zmianami inżynierskimi

Aby włączyć lub wyłączyć podstawowe funkcje zarządzania zmianami inżynierskimi, wykonaj następujące kroki. Od wersji 10.0.25 rozwiązania Supply Chain Management funkcja *Zarządzanie zmianami inżynierskimi* jest domyślnie włączona.

1. Przejdź do obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Sprawdź, czy są aktualizacje.
1. Włącz lub wyłącz funkcję o nazwie *Zarządzanie zmianami inżynieryjnymi*.
1. Jeśli chcesz śledzić wymiar wersji produktów w transakcjach (opcjonalnie), włącz funkcję o nazwie *Wersja wymiaru produktu*.

### <a name="turn-the-required-configuration-keys-on-or-off"></a>Włącz lub wyłącz wymagane klawisze konfiguracyjne

Następnie włącz klucze konfiguracji, wykonując następujące kroki. Nie są one domyślnie włączone.

1. Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.
1. Rozwiń węzeł **Handel**.
1. Włącz klucz konfiguracji funkcji głównej, zaznaczając pole wyboru **Zarządzanie zmianami inżynieryjnymi**.
1. Rozwiń węzeł **Zarządzanie zmianami inżynieryjnymi** i w razie potrzeby zaznacz lub wyczyść następujące pola wyboru (w zależności od potrzebnych funkcji):

    - **Wyszukiwanie atrybutów** – zaznaczenie tego pola wyboru umożliwia włączenie funkcji [wyszukiwania atrybutów](engineering-attributes-and-search.md). Zaleca się włączenie tej funkcji, ale jeśli nie będziesz jej używać, możesz wyczyścić to pole wyboru.
    - **Zarządzanie zmianami w produkcji procesowej** — to pole wyboru należy zaznaczyć, jeśli do zarządzania zmianami w formułach produkcji procesowej mają być dostępne funkcje zarządzania zmianami w formułach. Jeśli nie musisz zarządzać formułami, możesz wyczyścić to pole wyboru. Aby uzyskać więcej informacji, zobacz temat [Zarządzanie zmianami w formułach i ich składnikach](manage-formula-changes.md).

1. Jeśli chcesz także używać wymiaru wersji, zaznacz pole wyboru **Wymiar produktu — wersja**. (To pole wyboru znajduje się niżej w dół listy, nie jest zagnieżdżone w obszarze węzeł **Zarządzanie zmianami inżynieryjnymi**) To pole wyboru można wyczyścić, jeśli ta funkcja nie jest potrzebna.
1. Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Baza danych musi być zsynchronizowana, aby upewnić się, że klucze konfiguracji są prawidłowo aktualizowane w celu odzwierciedlenia wprowadzonych zmian. W zależności od typu środowiska, nad którym pracujesz, wykonaj jeden z następujących kroków:
    - **W przypadku środowisk warstwy 1 (programistycznych)**: otwórz projekt w firmie Microsoft Visual Studio, a następnie wybierz **Dynamics 365 \> Synchronizuj bazę danych \> Synchronizuj**.
    - **W przypadku środowisk warstwy 2 (i wyższych)**: baza danych synchronizuje się automatycznie po wsadowym trybie konserwacji, dzięki czemu można pominąć ten krok.

> [!NOTE]
> Aby można było korzystać z funkcji zarządzania zmianami projektowymi, sekwencję identyfikatorów BOM i sekwencję identyfikatorów formuł (jeśli używasz formuł) należy ustawić na *Automatyczne* na stronie **Sekwencje identyfikatorów**.

### <a name="turn-on-additional-engineering-change-management-features"></a>Włącz dodatkowe funkcje zarządzania zmianami inżynieryjnymi w systemie

Po włączeniu podstawowych funkcji zarządzania zmianami inżynieryjnych i włączeniu kluczy konfiguracji do zarządzania funkcjami zostanie dodanych kilka dodatkowych i opcjonalnych funkcji zarządzania zmianami inżynieryjnych. Każda z tych funkcji jest wymieniona w module **Zarządzanie zmianami inżynieryjnymi**. W poniższej tabeli opisano poszczególne funkcje opcjonalne i linki do dalszych informacji.

| Nazwa funkcji w zarządzaniu funkcjami | Opis | Stan funkcji |
|---|---|---|
| Włącz zarządzanie zmianami w istniejących produktach | <p>Ta funkcja umożliwia konwertowanie istniejących produktów na produkty inżynieryjne, dzięki czemu można rozpocząć zarządzanie nimi za pomocą funkcji zarządzania zmianami inżynieryjnymi.</p><p>Aby uzyskać więcej informacji, zobacz [Włącz zarządzanie zmianami w istniejących produktach](change-management-existing-products.md).</p> | Domyślnie w wersji 10.0.25. |
| Powiadomienia projektowe dla produkcji | <p>Po zmianie produktu w środowisku inżynieryjnym może być ważne powiadamianie o tych zmianach produkcji. Dzięki temu pracownicy produkcyjni mogą podjąć odpowiednie działania, takie jak podstawianie składników, zamiana list składowych (BOM) lub wymiana marszruty. Ta funkcja umożliwia powiadamianie produkcji o zmianach w tworzonych produktach.</p><p>Aby uzyskać więcej informacji, zobacz [Zarządzanie zmianami dotyczącymi produktów inżynieryjnych](engineering-change-management.md).</p> |  Domyślnie w wersji 10.0.25. |
| Poprawione dziedziczenie atrybutów dla zarządzania zmianami produkcyjnymi | <p>Upraszcza to zarządzanie atrybutami wyrobów gotowych lub pośrednich. Gdy ta funkcja jest włączona, łatwiej jest zidentyfikować wszystkie atrybuty należące do towaru i można wybrać atrybuty, które mają zostać przekazane z tego towaru do jego towaru nadrzędnego. Ta funkcja jest przydatna na przykład w przypadku, gdy jeden składnik gotowego produktu jest delikatny, toksyczny lub łatwopalny, ponieważ można łatwo zidentyfikować ten atrybut oznaczający składnik delikatny, toksyczny lub łatwopalny i propagować go do towaru gotowego.</p><p>Aby uzyskać więcej informacji, zobacz [Atrybuty inżynieryjne i wyszukiwanie atrybutów inżynieryjnych](engineering-attributes-and-search.md).</p> |  Domyślnie w wersji 10.0.25. |
| Kontrole gotowości produktu | <p>Ta funkcja pozwala również skonfigurować kontrole gotowości dla produktów standardowych (nie inżynierskich). Funkcji tej można użyć w celu sprawdzenia, czy każdy produkt jest w pełni zdefiniowany i czy wszystkie wymagane zasady zostały skonfigurowane przed jego użyciem w transakcjach. Wyłączenie tej funkcji po tym, jak przez jakiś czas była używana, spowoduje usunięcie wszystkich istniejących testów gotowości dla standardowych produktów.</p><p>Aby uzyskać więcej informacji, zobacz temat [Gotowość produktu](product-readiness.md).</p> |  Domyślnie w wersji 10.0.25. |
| Zarządzanie zmianami dotyczącymi formuł i ich substancji | <p>Funkcja ta umożliwia śledzenie zmian w składnikach formuły, produktach towarzyszących i produktach ubocznych.</p><p>Aby uzyskać więcej informacji, zobacz temat [Zarządzanie zmianami w formułach i ich składnikach](manage-formula-changes.md).</p> |  Domyślnie w wersji 10.0.25. |
| Generowanie wariantów produktów projektowych | <p>Ta funkcja umożliwia generowanie wariantów dla produktów inżynieryjnych na podstawie dostępnych wartości wymiarów.</p><p>Aby uzyskać więcej informacji, zobacz [Generowanie wariantów dla produktów inżynieryjnych](engineering-variants.md).</p> |  Domyślnie w wersji 10.0.25. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

