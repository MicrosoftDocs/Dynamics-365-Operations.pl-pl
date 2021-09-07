---
title: Proces wydania i historia wydań optymalizacji planowania
description: Ten temat zawiera informacje o procesie wydania i historii wydań dla optymalizacji planowania.
author: crytt
ms.date: 8/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fcd18341629afcf3092a457ae711e27b0bbfeb2a
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394424"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Proces wydania i historia wydań optymalizacji planowania

[!include [banner](../../includes/banner.md)]

Microsoft aktualizuje optymalizację planowania co miesiąc. Jednak na podstawie wymagań biznesowych od czasu do czasu wydajemy dodatkowe aktualizacje między zaplanowanymi wydaniami.

Każda wersja jest publikowana w poszczególnych regionach, w których dostępna jest optymalizacja planowania. Proces trwa zazwyczaj trzy dni.

Podczas gdy optymalizacja planowania jest aktualizowana, planowanie główne może działać nieco wolniej niż zwykle.

Środowiska korzystające z optymalizacji planowania automatycznie otrzymują najnowsze wydanie. Nie jest wymagana żadna akcja użytkownika: usługa jest automatycznie aktualizowana. Jednak żadna funkcja ze zmianami powodującymi niezgodność nie jest automatycznie wypychana do środowisk. Domyślnie wszelkie zmiany, które są uważane za powodujące niezgodność, są wyłączone i muszą być jawnie włączone za pomocą [zarządzania funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). W związku z tym te zmiany nie będą wyświetlane w środowiskach, dopóki nie wybierzesz opcji ich włączenia.

Ponieważ powiadomienia nie są wyświetlane, gdy optymalizacja planowania jest aktualizowana w środowisku, można przejrzeć informacje o wersji w poniższej tabeli, aby określić, kiedy zmiany zostały wydane i jakie funkcje wprowadziły. W tej tabeli przedstawiono zmiany, które zostały wydane dla optymalizacji planowania, podano, czy te zmiany są skojarzone z funkcją z zarządzania funkcjami oraz podano datę wydania.

| Zmiany | Szczegóły zarządzania funkcjami | Data zwolnienia |
|---|---|---|
| <p>Dodano pole **Czas realizacji** do zamówień planowanych.</p><p>Ogólne usprawnienia wydajności, jakości i stabilności.</p> | Nie jest wymagane zarządzanie funkcjami. | 16 sierpnia 2021 r. |
| <p>Dodano wymagania dotyczące typu zasobu dla planowania nieskończonej pojemności.</p><p>Zwiększono wydajność zasobów i wydajność kalendarza w celu planowania nieskończonej pojemności.</p><p>Aby uzyskać więcej informacji, zobacz [Planowanie z nieskończoną pojemnością](infinite-capacity-planning.md). | <p>Dostępne w zarządzaniu funkcjami w wersji 10.0.20.</p><p>Nazwa funkcji: *Planowanie nieskończonej pojemności dla optymalizacji planowania*</p> | 6 lipca 2021 r. |
| Ogólna poprawa jakości. | Nie jest wymagane zarządzanie funkcjami. | 6 lipca 2021 r. |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
