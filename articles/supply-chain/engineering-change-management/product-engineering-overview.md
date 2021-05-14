---
title: Omówienie zarządzania zmianami inżynieryjnymi
description: Ten temat zawiera omówienie zarządzania zmianami inżynieryjnymi, które pomaga w planowaniu i zarządzaniu wersjami produktów oraz zarządzaniu cyklami życia produktu i zmianami inżynieryjnymi.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d7c0839ffbea80904ca12d1cba7ba9880f721cdd
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947527"
---
# <a name="engineering-change-management-overview"></a>Omówienie zarządzania zmianami inżynieryjnymi

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Podsumowanie funkcji

Dzisiejsi producenci wymagają silnego zarządzania danymi produktu, kontroli wersji i zarządzania zmianami inżynieryjnymi, aby odnieść sukces w świecie stale kurczących się cykli życia produktów, zwiększonych wymagań dotyczących jakości i niezawodności oraz zwiększonego nacisku na bezpieczeństwo produktu.

Zarządzanie zmianami inżynieryjnymi umożliwia tworzenie struktury i dyscypliny w procesie zarządzania danymi produktów, a ponadto umożliwia definiowanie, zwalnianie i korygowanie produktów w sposób kontrolowany, który jest obsługiwany przez przepływy pracy. Dzięki wersjom produktów i zarządzaniu zmianami inżynieryjnymi możesz dokumentować, oceniać wpływ i wprowadzać zmiany w całym cyklu życia produktu.

Zarządzanie zmianami inżynieryjnymi pomaga w planowaniu i zarządzaniu wersjami produktów oraz zarządzaniu cyklami życia produktu i zmianami inżynieryjnymi. Poniżej znajduje się lista funkcji głównych:

- Przechowywanie wersji produktów
- Ulepszona funkcjonalność wydania produktu, która umożliwia utrzymywanie danych podstawowych produktu w jednej firmie (firmie inżynierskiej) i publikowanie w pełni skonfigurowanego wydanego produktu innym firmom
- Zasady sprawdzania, czy wymagane informacje zostały wprowadzone przed aktywacją wersji produktu (kontrola gotowości)
- Udoskonalone zarządzanie cyklem życia produktu dzięki kontroli szczegółowej, gdy zwolniony produkt może być używany w konkretnych procesach biznesowych
- Żądania zmian inżynieryjnych obsługiwane przez przepływy pracy
- Zamówienia zmian inżynieryjnych obsługiwane przez przepływy pracy

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

Poprzednie wideo ([Możliwości zarządzania zmianami w Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) znajduje się na [liście odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na platformie YouTube.

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a>Włącz w systemie funkcje zarządzania zmianami technicznymi i wymiarowania wersji

Aby można było używać funkcji zarządzania zmianami inżynieryjnymi, należy włączyć zarówno funkcję *Zarządzania zmianami inżynieryjnymi*, jak i jej klucz konfiguracji. Jeśli chcesz również śledzić wymiar wersji produktów w transakcjach (opcjonalnie), musisz również włączyć funkcję *Wymiar wersji produktu* i jej klucz konfiguracji.

Najpierw włącz funkcje, wykonując następujące kroki.

1. Przejdź do obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Sprawdź, czy są aktualizacje.
1. Włącz funkcję o nazwie **Zarządzanie zmianami inżynieryjnymi**.
1. Jeśli chcesz go użyć, włącz również funkcję o nazwie **Wersja wymiaru produktu**.

Następnie włącz klucze konfiguracji, wykonując następujące kroki.

1. Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.
1. Rozwiń węzeł **Handel**.
1. Włącz klucz konfiguracji funkcji głównej, zaznaczając pole wyboru **Zarządzanie zmianami inżynieryjnymi**. (Rozwinięcie węzła nie jest konieczne, chyba że trzeba również wyłączyć jedną lub obie jego funkcje podrzędne).
1. Jeśli chcesz także używać wymiaru wersji, zaznacz pole wyboru **Wymiar produktu — wersja**. (To pole wyboru jest dalej niż lista, ale nie jest zagnieżdżone w węźle **Zarządzanie zmianami inżynieryjnymi**).
1. Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

> [!IMPORTANT]
> Począwszy od kwietnia 2022 roku klucze licencji do węzłów **Zarządzanie zmianami inżynieryjnych** i **Wymiar produktu — wersja** będą domyślnie włączone dla wszystkich nowych instalacji, ale w razie potrzeby będzie można je wyłączyć.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
