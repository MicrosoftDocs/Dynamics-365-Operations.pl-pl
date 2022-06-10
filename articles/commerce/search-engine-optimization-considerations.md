---
title: Zagadnienia optymalizacji wyszukiwarki dla witryny
description: Ten temat obejmuje zagadnienia optymalizacji aparatu wyszukiwania (SEO), które nie zostały rozbudowane do produkcji.
author: psimolin
ms.date: 05/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: 2f90581766dba3d3a671df52ec08339a1a0fd7dc
ms.sourcegitcommit: 9dd2d32fc303023a509d58ec7b5935f89d1e9c6d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/26/2022
ms.locfileid: "8806412"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Zagadnienia optymalizacji aparatu wyszukiwania (SEO) dla witryny


[!include [banner](includes/banner.md)]

Ten temat obejmuje zagadnienia optymalizacji aparatu wyszukiwania (SEO), które nie zostały rozbudowane do produkcji.

## <a name="a-site-that-is-under-development"></a>Witryna w trakcie opracowywania

Aby zapewnić, że wyszukiwarki nie będą indeksować witryny w trakcie tworzenia, wszystkie strony witryny powinny mieć znaczniki meta **noindex** i **nofollow**. Dobrą praktyką jest stworzenie fragmentu opartego na module [moduł MetaTags](metatags-module.md), który zawiera następujący wpis meta tagów, i upewnienie się, że fragment ten jest dodany do sekcji HTML \<head\> wszystkich szablonów używanych na twojej stronie.

```html
<meta name="robots" content="noindex,nofollow" /> 
```

## <a name="soft-launch-of-a-site"></a>Wstępne uruchamianie witryny

Podczas „uruchamiania wstępnego” witryna sieci Web jest udostępniana do ograniczonej grupy odbiorców lub rynku przed wykonaniem pełnego uruchomienia. W przypadku miękkiego uruchomienia witryny należy rozważyć pozostawienie metatagów **noindex**. W ten sposób pomagasz zagwarantować, że wstępne uruchomienie pozostanie ograniczone do ograniczonej grupy odbiorców, do której chcesz dotrzeć.

## <a name="a-site-that-is-in-production"></a>Witryna w produkcji

Jeśli witryna jest w produkcji, należy upewnić się, że wszystkie strony witryny są poprawnie oznakowane. Microsoft Dynamics 365 Commerce używa informacji wprowadzonych na stronie w celu renderowania wszystkich informacji dotyczących SEO na tej stronie Następujące moduły zapewniają tę funkcjonalność: podsumowanie strony kategorii, podsumowanie strony listy i podsumowanie strony produktu.

Aby zoptymalizować indeksowanie wyszukiwarek, struktura renderowania wykorzystuje obie informacje z właściwości SEO, które są skonfigurowane w Dynamics 365 Commerce i w informacjach dotyczących modułu. W przypadku witryny, która jest produkowana, należy upewnić się, że plik robots.txt pozwala na indeksowanie całej witryny oraz że zawiera linki do opublikowanego dokumentu mapy witryny. Należy włączyć funkcję generowania mapy witryny w **Ustawienia witryny \> Mapy witryny włączone**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Ustawienia SEO strony dla wewnętrznego podglądu, ograniczonej liczby odbiorców i wszystkich odbiorców

Ponieważ Dynamics 365 Commerce działa według zasady „to co widzisz, jest tym co dostajesz” (WYSIWYG) w wizualnym konstruktorze stron, autorzy mogą przygotować zawartość strony bez konieczności obaw, że informacje staną się widoczne dla osób odwiedzających witrynę. Jeśli strona musi zostać opublikowana, ale jej ekspozycja musi być ograniczona, powinna mieć metatag **noindex**, aby nie był indeksowany przez wyszukiwarki. Następnie, gdy strona jest gotowa dla wszystkich odbiorców, wszystkie podstawowe metadane SEO powinny być obecne, aby zmaksymalizować skuteczność indeksowania wyszukiwarek. Ponadto należy usunąć metatag **nolimit**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zarządzanie użytkownikami i rolami e-Commerce](manage-ecommerce-users-roles.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)

[Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
