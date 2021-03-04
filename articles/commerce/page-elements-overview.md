---
title: Słownik terminów dotyczących modelu strony
description: W tym temacie opisano różne elementy, które są używane na stronach witryny Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5c772a19958ebf0687d09af4c3055c733d99d750
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415036"
---
# <a name="page-model-glossary"></a>Słownik terminów dotyczących modelu strony


[!include [banner](includes/banner.md)]

W tym temacie opisano różne elementy, które są używane na stronach witryny Microsoft Dynamics 365 Commerce.

## <a name="page-element-definitions"></a>Definicje elementów strony

Poniższa tabela przedstawia podsumowanie pojęć, które powinny być znane, gdy zmieniasz wygląd, działanie i zawartość witryny. Aby uzyskać dokładniejsze wyjaśnienia i procedury, należy skorzystać z łączy.

| Okres | Opis i uwagi |
|------|-----------------------|
| [Moduł](work-with-modules.md) | <p>**Definicja:** moduły są blokami konstrukcyjnymi, które mogą być tworzone i tworzą szkielet strony sieci Web. Przykładem mogą być moduły nagłóweka, bohatera i karuzela.</p><p>**Gdzie jest wybrana opcja:** wdrożone moduły można wybierać i konfigurować na różnych etapach przepływu pracy tworzenia witryn, takich jak szablon, układ, strona i etapy tworzenia fragmentów.</p><p>**Gdzie jest edytowany:** moduły niestandardowe są tworzone w kodzie przy użyciu zestawu Software Development Kit (SDK). Następnie są one przekazywane do witryny, gdzie będą dostępne do wybrania.</p> |
| Właściwość modułu | <p>**Definicja:** właściwości modułu są określonymi ustawieniami zdefiniowanymi przez moduł. Można je edytować w narzędziach autorskich e-Commerce. Na przykład właściwości modułu służą do ustawiania nagłówka i obrazu tła w module banera.</p><p>**Gdzie jest skonfigurowany:** wybrano i skonfigurowano właściwości modułu w okienku właściwości, które pojawia się w środowiskach autorskich (edytorach) dla szablonów, układów, stron, fragmentów i ustawień aplikacji.</p> |
| [Szablon](templates-layouts-overview.md) | <p>**Definicja:** szablony definiują kombinacje i opcje modułu, które powinny być używane dla kategorii stron (np. stron marketingowych, stron kategorii i stron produktów).</p><p>**Gdzie jest wybrany:** szablony można wybierać podczas tworzenia strony lub układu przepływów pracy.</p><p>**Gdzie jest edytowany:** szablony są tworzone w edytorze szablonów. Do utworzenia lub zmodyfikowania nie jest wymagany żaden kod.</p> |
| [Układ](templates-layouts-overview.md) | <p>**Definicja:** układy definiują ostateczne wybór i układ modułów na podstawie zbioru opcji szablonu nadrzędnego. Układ może być konfigurowany dla pojedynczej strony (*układ niestandardowy*) lub może być współużytkowany przez wiele stron (*układ predefiniowany*).</p><p>**Gdzie jest zaznaczone:** układy można wybierać podczas tworzenia nowej strony lub gdy dla istniejącej strony wymagany jest inny układ.</p><p>**Gdzie jest edytowany:** układy są tworzone w edytorze układu. Do utworzenia lub zmodyfikowania nie jest wymagany żaden kod.</p> |
| [Wystąpienie strony](modify-existing-page.md) | <p>**Definicja:** wystąpienia strony definiują ostateczną zawartość poddaną stronie dla pojedynczej strony. Ta zawartość pochodzi od wartości właściwości modułu.</p><p>**Gdzie jest on wybrany:** wybierane są strony, gdy są przypisane adresy URL.</p><p>**Gdzie jest edytowany:** strony są edytowane w edytorze strony. Do utworzenia lub zmodyfikowania nie jest wymagany żaden kod.</p> |
| [Motyw](select-site-theme.md) | <p>**Definicja:** motywy definiują arkusz stylów kaskadowych (CSS) i określają wygląd i działanie modułów renderowanych na stronie.</p><p>**Gdzie jest wybrana opcja:** po przekazaniu motywu do witryny za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS) można go wybrać jako właściwość modułu kontenera stron.</p><p>**Gdzie jest edytowany:** motywy są obecnie tworzone i edytowane przy użyciu zestawu SDK. Następnie są przekazywane do witryny za pomocą usługi LCS.</p> |
| [Fragment](work-with-fragments.md) | <p>**Definicja:** fragmenty są w pełni skonfigurowane moduły z zlokalizowaną zawartością, która może być ponownie używana i centralnie aktualizowana na wielu stronach. Na przykład fragment utworzony z poziomu nagłówka może być używany we wszystkich szablonach i na wszystkich stronach w witrynie, a następnie domyślnie aktualizowany w jednym miejscu.</p><p>**Gdzie jest wybrana opcja:** fragmenty można wybierać wszędzie, gdzie można wybierać moduły. Można je zastąpić modułem, ułatwiając w ten sposób zwiększenie efektywności dzięki możliwości wielokrotnego wykorzystania i scentralizowanego tworzenia.</p><p>**Gdzie jest edytowany:** fragmenty są edytowane w edytorze fragmentów. Do utworzenia lub zmodyfikowania nie jest wymagany żaden kod.</p> |
| [Adres URL](create-page-URL.md) | <p>**Definicja:** adresy URL (Uniform Resource Locator) są adresami wskazującymi strony sieci Web lub inne adresy URL.</p><p>**Gdzie jest on wybrany:** adresy URL są wybierane wszędzie tam, gdzie wymagane są linki między stronami.</p><p>**Gdzie jest edytowany:** adresy URL są edytowane w edytorze URL. Do utworzenia lub zmodyfikowania nie jest wymagany żaden kod.</p> |
| Składnik majątku | <p>**Definicja:** zasoby to pliki binarne, które mają rozszerzenie takie jak .jpg, .docx, .pdf lub .mpg.</p><p>**Gdzie jest wybrana opcja:** zasoby są wybierane jako właściwości modułu dla modułów, które tego wymagają.</p><p>**Gdzie jest edytowany:** zasoby są przekazywane, a skojarzone z nimi metadane są edytowane w menedżerze zasobów.</p> |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Sposoby dodawania zawartości](add-manage-content.md)

[Dokumentowanie stanów i cyklów życia](document-states-overview.md)

[Praca z grupami publikowania](publish-groups.md)

[Włączanie i używanie udostępniania między kanałami](cross-channel-sharing.md)

[Praca z modułami](work-with-modules.md)

[Praca z fragmentami](work-with-fragments.md)

[Omówienie szablonów i układów](templates-layouts-overview.md)

[Dostosowywanie nawigacji w witrynie](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]