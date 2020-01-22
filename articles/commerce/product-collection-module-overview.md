---
title: Moduły kolekcji produktów
description: Ten temat stanowi przegląd modułów kolekcji produktów w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 31307035014f2fae6146f33bc23e3e06103f82eb
ms.sourcegitcommit: c237123ad94d9418994ac095fbd8634c05a927b1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/08/2020
ms.locfileid: "2943270"
---
# <a name="product-collection-modules"></a>Moduły kolekcji produktów

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ten temat stanowi przegląd modułów kolekcji produktów w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Odnajdowanie produktów to podstawowe narzędzie używane przez sprzedawców detalicznych, którzy mogą współpracować z klientami w witrynie e-Commerce. Moduły kolekcji produktów pomagają detalistom budować atrakcyjne doświadczenie, udostępniając intuicyjny interfejs graficzny, który może być używany do szybkiego tworzenia zbiorów produktów.

Moduły kolekcji produktów reprezentują fizyczne produkty i usługi w witrynie sieci Web. Moduł kolekcji produktów jest zazwyczaj połączony ze stroną szczegółów, w której klienci mogą zakupić produkt lub usługę, lub dowiedzieć się więcej o niej. 

Źródła dla kolekcji produktów mogą być listami czterech następujących typów:

- Listy redakcyjne produktów, które zostały ręcznie zdefiniowane w Dynamics 365 Retail jako produkty pokrewne produktu lub na listach produktów
- Listy algorytmowe, takie jak listy nowości, najlepiej sprzedających sięproduktów lub trendów produktów
- Listy rekomendacji oparte na uczeniu maszynowym
- Listy personalizacji, które obsługują spersonalizowane wyniki dla klienta. Aby zobaczyć spersonalizowane wyniki, klienci muszą być zalogowani w witrynie e-Commerce. Użytkownicy goście nie widzą spersonalizowanych wyników. Klienci mogą zrezygnować z personalizacji na [stronie zarządzania kontem](account-management.md).

Na poniższej ilustracji przedstawiono różne typy kolekcji produktów, które są używane w witrynie e-Commerce.

![Przykład różnych typów kolekcji produktów w witrynie e-Commerce](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Zawsze używaj modułów kolekcji produktów, aby wyświetlić grupę produktów podobnego typu.

## <a name="product-collection-modules-and-types"></a>Moduły kolekcji produktów i ich typy

W poniższej tabeli opisano różne typy modułów kolekcji produktów w Dynamics 365 Commerce.

| Moduł kolekcji produktów  | Typ | Opis |
|----------------------------|------|-------------|
| Kategoria                   | Kategoria | Ten moduł pokazuje listę produktów w kategorii zgodnie z definicją w hierarchii kategorii nawigacji, którą sprzedawca detaliczny utworzył dla kanału sprzedaży detalicznej. |
| Powiązane produkty           | Redakcyjne | Ten moduł pokazuje listę produktów skonfigurowanych przez menedżera merchandisingu jako powiązane produkty w aplikacji Retail dla typu relacji wybranego przez autora. |
| Lista wyselekcjonowanych produktów      | Redakcyjne | Ten moduł pokazuje niestandardowe listy utworzone przez sprzedawców i redaktorów w aplikacji Retail. |
| Nowy element                        | Algorytmy | Ten moduł pokazuje listę najnowszych produktów w asortymentach do kanałów i katalogów. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Bestsellery               | Algorytmy | Ten moduł pokazuje listę produktów sklasyfikowanych według najwyższej liczby sprzedaży. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Popularne                   | Algorytmy | Ten moduł pokazuje listę produktów najwyższej wydajności w danym okresie. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Często kupowane razem | Sztuczna inteligencja/uczenie maszynowe | Ten moduł używa uczenia maszynowego do analizowania wzorów zakupów klientów i rekomendowanych często kupowanych razem z danym produktem towarów. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Klienci także lubią           | Sztuczna inteligencja/uczenie maszynowe | Ten moduł używa uczenia maszynowego do analizowania wzorców zakupów klientów i powiązanych z produktem rekomendowanych towarów. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Wybrane dla Ciebie              | Sztuczna inteligencja/uczenie maszynowe | Ten modułu używa uczenia maszynowego do analizowania wzorców zakupu zalogowanego użytkownika i dostarczania spersonalizowanych rekomendacji opartych na tych wzorcach zakupu. W przypadku użytkownika gościa ta lista zostanie zwinięta. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Dodawanie modułu kolekcji produktów do strony kategorii

Aby dodać moduł kolekcji produktów do strony kategorii, wykonaj następujące kroki.

1. W Dynamics 365 Commerce przejdź do swojej witryny i utwórz stronę, na której jest używany ten sam szablon, co domyślna strona kategorii.
1. W konspekcie strony wybierz gniazdo **Stopka podrzędna**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz **Kontener** i wybierz przycisk **OK**.
1. W module kontener wybierz przycisk wielokropka, a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz **Kolekcja produktu** i wybierz przycisk **OK**.  
![Przykładowy przepływ Kreatora modułu kolekcji produktów](./media/productCollectionModule.png)
1. Skonfiguruj ustawienia wybierając odpowiednie źródło danych oraz dane wejściowe dla kolekcji produktów.
1. W okienku właściwości modułu kolekcja produktów wybierz opcję **Dodaj listę produktów**.
1. W oknie dialogowym **Wybór konfiguracji listy produktów** wybierz typ listy, wprowadź liczbę towarów i wybierz inne opcje dostępne dla typu listy. Aby uzyskać więcej informacji o typach list, zobacz poniższą tabelę. 
1. Kliknij przycisk **OK**.
1. Zapisz stronę i zaewidencjonuj ją.

W poniższej tabeli przedstawiono typy list, które są dostępne do wybrania w oknie dialogowym **Wybór konfiguracji listy produktów**.

| Typ                       | Opis | Użycie | Kontekst strony | Określony kontekst | Personalizacja |
|----------------------------|-------------|-------|--------------|------------------|-----------------|
| Produkty według kategorii       | Lista produktów należących do danej kategorii. Ta kategoria jest określana na podstawie kontekstu strony lub kontekstu podanego przez autora. | Ten typ listy może być używany na dowolnej stronie (na przykład na stronie głównej, stronie kategorii, stronie marketingowej lub stronie szczegółów produktu \[PDP\]) w celu promowania określonej kategorii produktów. | Kategoria z kontekstu strony, jeśli jest dostępna (na przykład strona kategorii) | Autor może udostępnić określoną kategorię jako kontekst dla listy. | Nie dotyczy |
| Powiązane produkty           | Lista produktów, które menedżer ds. merchandisingu skonfigurował jako produkty powiązane dla typu relacji w aplikacji Retail. | Ten typ listy jest używany głównie na stronach PDP, ale może być używany na dowolnej stronie w przypadku określenia produktu nadrzędnego. | Produkt ze strony, typ relacji (obowiązkowy) | Produkt można wybrać w selektorze, a typ relacji jest używany. | Nie dotyczy |
| Pod opieką                    | Lista niestandardowa utworzona przez sprzedawców i redaktorów w Retail. | Wzbogacanie strony kategorii, strony głównej, strony realizacji transakcji i koszyka oraz strony produktów | Nie dotyczy | Nie dotyczy | Nie dotyczy |
| Algorytmy                | <ul><li>**Nowości** — lista najnowszych produktów w asortymentach do kanałów i katalogów.</li><li>**Bestsellery** — Lista produktów sklasyfikowanych według najwyższej liczby sprzedaży.</li><li>**Trendy** — Lista produktów najwyższej wydajności w danym okresie.</li></ul> | Stronw główna, wzbogacanie strony kategorii, strony realizacji transakcji i koszyka | Kategoria z kontekstu strony (na przykład strona kategorii) | Kategoria, która jest określana przez autora witryny | Obsługiwana |
| Często kupowane razem | Lista, która używa uczenia maszynowego do analizowania wzorców zakupów klientów i rekomendowanych często kupowanych razem z danym produktem towarów. | Ten typ listy ma zastosowanie tylko do strony koszyka. | Koszyk | Nie dotyczy | Obsługiwana |
| Klienci także lubią           | Lista, która używa nauki maszynowej do analizowania wzorów zakupów klientów i powiązanych z produktem towarów. | Ten typ listy jest używany na stronach PDP w celu wyświetlenia produktów kupionych przez innych klientów. | Kontekst produktu ze strony | Produkt dostarczony przez autora witryny | Obsługiwana |
| Wybrane dla Ciebie              | Lista, która używa uczenia maszynowego do określenia preferencji klienta. | Ten typ listy może być używany na dowolnej stronie. | Nie dotyczy| Nie dotyczy | Obsługiwana | 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł karuzeli](add-carousel.md)

[Moduł zaawansowanego bloku zawartości](add-content-rich-block.md)

[Moduł umieszczania zawartości](add-content-placement-modules.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Omówienie rekomendacji produktów](product-recommendations.md)
