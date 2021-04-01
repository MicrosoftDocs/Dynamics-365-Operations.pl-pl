---
title: Zagadnienia optymalizacji wyszukiwarki dla witryny
description: Ten temat obejmuje zagadnienia optymalizacji aparatu wyszukiwania (SEO), które nie zostały rozbudowane do produkcji.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c4d1a4a1b14f7af1db1c53bd9ee1993cc9187609
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254800"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Zagadnienia optymalizacji wyszukiwarki dla witryny


[!include [banner](includes/banner.md)]

Ten temat obejmuje zagadnienia optymalizacji aparatu wyszukiwania (SEO), które nie zostały rozbudowane do produkcji.

## <a name="a-site-that-is-under-development"></a>Witryna w trakcie opracowywania

Podczas tworzenia witryny wszystkie strony witryny powinny mieć metatagi **NOINDEX** i **NOFOLLOW**, aby wyszukiwarki nie indeksowały stron i nie zapisywały wersji programistycznych witryny w pamięci podręcznej. Aby wykonać tę konfigurację, musisz dodać domyślny moduł metatagów do szablonu strony serwisu. Domyślne właściwości metatagów będą wówczas dostępne w sekcji właściwości SEO w edytorze stron. Te właściwości służą do zarządzania metatagami.

## <a name="soft-launch-of-a-site"></a>Wstępne uruchamianie witryny

Podczas „uruchamiania wstępnego” witryna sieci Web jest udostępniana do ograniczonej grupy odbiorców lub rynku przed wykonaniem pełnego uruchomienia. W przypadku miękkiego uruchomienia witryny należy rozważyć pozostawienie metatagów **NOINDEX**. W ten sposób pomagasz zagwarantować, że wstępne uruchomienie pozostanie ograniczone do ograniczonej grupy odbiorców, do której chcesz dotrzeć.

## <a name="a-site-that-is-in-production"></a>Witryna w produkcji

Jeśli witryna jest w produkcji, należy upewnić się, że wszystkie strony witryny są poprawnie oznakowane. Microsoft Dynamics 365 Commerce używa informacji wprowadzonych na stronie w celu renderowania wszystkich informacji dotyczących SEO na tej stronie Następujące moduły zapewniają tę funkcjonalność: podsumowanie strony kategorii, podsumowanie strony listy i podsumowanie strony produktu.

Aby zoptymalizować indeksowanie wyszukiwarek, struktura renderowania wykorzystuje obie informacje z właściwości SEO, które są skonfigurowane w Dynamics 365 Commerce i w informacjach dotyczących modułu. W przypadku witryny, która jest produkowana, należy upewnić się, że plik robots.txt pozwala na indeksowanie całej witryny oraz że zawiera linki do opublikowanego dokumentu mapy witryny. Należy włączyć funkcję generowania mapy witryny w **Ustawienia witryny \> Mapy witryny włączone**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Ustawienia SEO strony dla wewnętrznego podglądu, ograniczonej liczby odbiorców i wszystkich odbiorców

Ponieważ Dynamics 365 Commerce działa według zasady „to co widzisz, jest tym co dostajesz” (WYSIWYG) w wizualnym konstruktorze stron, autorzy mogą przygotować zawartość strony bez konieczności obaw, że informacje staną się widoczne dla osób odwiedzających witrynę. Jeśli strona musi zostać opublikowana, ale jej ekspozycja musi być ograniczona, powinna mieć metatag **NOINDEX**, aby nie był indeksowany przez wyszukiwarki. Następnie, gdy strona jest gotowa dla wszystkich odbiorców, wszystkie podstawowe metadane SEO powinny być obecne, aby zmaksymalizować skuteczność indeksowania wyszukiwarek. Ponadto należy usunąć metatag **NOLIMIT**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zarządzanie użytkownikami i rolami e-Commerce](manage-ecommerce-users-roles.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)

[Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]