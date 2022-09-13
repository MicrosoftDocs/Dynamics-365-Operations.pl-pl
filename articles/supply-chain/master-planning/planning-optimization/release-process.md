---
title: Proces wydania i historia wydań optymalizacji planowania
description: Ten artykuł zawiera informacje o procesie wydania i historii wydań dla optymalizacji planowania.
author: t-benebo
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 5e8b4ab74bf973a131499799efa66e9c7fe9d5be
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403725"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Proces wydania i historia wydań optymalizacji planowania

[!include [banner](../../includes/banner.md)]

Microsoft aktualizuje optymalizację planowania co miesiąc. Jednak na podstawie wymagań biznesowych od czasu do czasu wydajemy dodatkowe aktualizacje między zaplanowanymi wydaniami.

Każda wersja jest publikowana w poszczególnych regionach, w których dostępna jest optymalizacja planowania. Proces trwa zazwyczaj trzy dni.

Podczas gdy optymalizacja planowania jest aktualizowana, planowanie główne może działać nieco wolniej niż zwykle.

Środowiska korzystające z optymalizacji planowania automatycznie otrzymują najnowsze wydanie. Nie jest wymagana żadna akcja użytkownika: usługa jest automatycznie aktualizowana. Jednak żadna funkcja ze zmianami powodującymi niezgodność nie jest automatycznie wypychana do środowisk. Domyślnie wszelkie zmiany, które są uważane za powodujące niezgodność, są wyłączone i muszą być jawnie włączone za pomocą [zarządzania funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). W związku z tym te zmiany nie będą wyświetlane w środowiskach, dopóki nie wybierzesz opcji ich włączenia.

Ponieważ powiadomienia nie są wyświetlane, gdy optymalizacja planowania jest aktualizowana w środowisku, można przejrzeć informacje o wersji w poniższej tabeli, aby określić, kiedy zmiany zostały wydane i jakie funkcje wprowadziły. W tej tabeli przedstawiono zmiany, które zostały wydane dla optymalizacji planowania, podano, czy te zmiany są skojarzone z funkcją z zarządzania funkcjami oraz podano datę wydania.

| Zmiany | Szczegóły zarządzania funkcjami | Daty zwolnienia |
|---|---|---|
| <p>Ogólne usprawnienia wydajności, jakości i stabilności. | Nie jest wymagane zarządzanie funkcjami. | 29 sierpnia — 3 września 2022 |
| <p>Ogólne usprawnienia wydajności, jakości i stabilności.<p>[Obsługa kalendarza scentralizowanego optymalizacji planowania](../supply-chain-calendars-master-planning.md)<p>[Optymalizacja planowania – propozycje optymalizacji istniejących dostaw](../action-messages.md)<p>[Wsparcie optymalizacji planowania dla podwykonawstwa](../../production-control/manage-subcontract-work-production.md) | Nie jest wymagane zarządzanie funkcjami. | 7-11 marca 2022 r. |
| <p>Dodano obsługę priorytetów planowania dla zleceń produkcyjnych. | Dostępne od wersji 10.0.25 jako część funkcji o nazwie *Wsparcie MRP oparte na priorytetach dla optymalizacji planowania*. | 12–18 listopada 2021 r. |
| <p>Ogólne usprawnienia wydajności, jakości i stabilności. | Nie jest wymagane zarządzanie funkcjami. | 12–18 listopada 2021 r. |
| <p>Dodano obsługę formuł obliczania czasu procesu, marszrutę produkcji z nakładaniem i numer operacji produkcyjnej w transakcjach zapotrzebowania.</p><p>Rozszerzone komunikaty o błędach w planowaniu produkcji związane z limitem czasu, nie można odnaleźć zdolności produkcyjnych i marszrutą cykliczną.</p><p>Poprawiona spójność podczas obliczania dat przyjęcia i wydania zarówno dla zamówień planowanych, jak i zamówień potwierdzonych.</p><p>Ogólne usprawnienia wydajności, jakości i stabilności. | Nazwa funkcji: *Planowanie nieskończonej pojemności dla optymalizacji planowania* | 22-27 października 2021 |
| <p>Dodano obsługę uwzględnienia procentu odpadków w obliczeniach czasu przetwarzania.</p><p>Dodano obsługę numeru operacji i użycia materiałów podczas planowania. | Nazwa funkcji: *Planowanie nieskończonej pojemności dla optymalizacji planowania* | 5-7 października 2021 |
| <p>Dodano obsługę typów zadań marszruty produkcji: **Kolejka przed**, **Kolejka po** i **Czas transportu**.</p><p>Ogólne usprawnienia wydajności, jakości i stabilności. | Nazwa funkcji: *Planowanie nieskończonej pojemności dla optymalizacji planowania* | 25-30 września 2021 |
| <p>Dodano obsługę planów główne z **metodą planowania** ustawioną na *planowanie operacji*.</p><p>Na stronie **Grupy marszrut** wartości pól wyboru **Aktywacja**, **Czas pracy** i **Zdolności produkcyjne** są zwracane w przypadku wierszy o typie **Marszruta/zadanie** o typie *Konfiguracja* lub *Proces*. </p><p>Ogólne usprawnienia wydajności, jakości i stabilności. | <p>Planowanie operacji jest dostępne w zarządzaniu funkcjami od wersji 10.0.20.</p><p>Nazwa funkcji: *Planowanie nieskończonej pojemności dla optymalizacji planowania*</p>  | 9–17 września 2021 r. |
| Ogólne usprawnienia wydajności, jakości i stabilności. | Nie jest wymagane zarządzanie funkcjami. | 25–30 sierpnia 2021 r. |
| <p>Dodano pole **Czas realizacji** do zamówień planowanych.</p><p>Ogólne usprawnienia wydajności, jakości i stabilności.</p> | Nie jest wymagane zarządzanie funkcjami. | 12–17 sierpnia 2021 r. |
| <p>Dodano wymagania dotyczące typu zasobu dla planowania nieskończonej pojemności.</p><p>Zwiększono wydajność zasobów i wydajność kalendarza w celu planowania nieskończonej pojemności.</p><p>Aby uzyskać więcej informacji, zobacz [Planowanie z nieskończoną pojemnością](infinite-capacity-planning.md). | <p>Dostępne w zarządzaniu funkcjami w wersji 10.0.20.</p><p>Nazwa funkcji: *Planowanie nieskończonej pojemności dla optymalizacji planowania*</p> | 6–12 lipca 2021 r. |
| Ogólna poprawa jakości. | Nie jest wymagane zarządzanie funkcjami. | 6–12 lipca 2021 r. |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
