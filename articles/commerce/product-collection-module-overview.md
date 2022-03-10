---
title: Moduły kolekcji produktów
description: Ten temat stanowi przegląd modułów kolekcji produktów w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 01/28/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7bc76aa8d5728005711ee8f9758532a989e3568c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984551"
---
# <a name="product-collection-modules"></a>Moduły kolekcji produktów

[!include [banner](includes/banner.md)]

Ten temat stanowi przegląd modułów kolekcji produktów w rozwiązaniu Microsoft Dynamics 365 Commerce.

Odnajdowanie produktów to podstawowe narzędzie używane przez sprzedawców detalicznych, którzy mogą współpracować z klientami w witrynie e-Commerce. Moduły kolekcji produktów pomagają detalistom budować atrakcyjne doświadczenie, udostępniając intuicyjny interfejs graficzny, który może być używany do szybkiego tworzenia zbiorów produktów.

Moduły kolekcji produktów reprezentują fizyczne produkty i usługi w witrynie sieci Web. Moduł kolekcji produktów jest zazwyczaj połączony ze stroną szczegółów, w której klienci mogą zakupić produkt lub usługę, lub dowiedzieć się więcej o niej. 

Źródła dla kolekcji produktów mogą być listami czterech następujących typów:

- Listy redakcyjne produktów, które zostały ręcznie zdefiniowane w Dynamics 365 Commerce jako produkty pokrewne produktu lub na listach produktów
- Listy algorytmowe, takie jak listy nowości, najlepiej sprzedających sięproduktów lub trendów produktów
- Listy rekomendacji oparte na uczeniu maszynowym
- Listy personalizacji, które obsługują spersonalizowane wyniki dla klienta. Aby zobaczyć spersonalizowane wyniki, klienci muszą być zalogowani w witrynie e-Commerce. Użytkownicy goście nie widzą spersonalizowanych wyników. Klienci mogą zrezygnować z personalizacji na [stronie zarządzania kontem](account-management.md).

Na poniższej ilustracji przedstawiono różne typy kolekcji produktów, które są używane w witrynie e-Commerce.

![Przykład różnych typów kolekcji produktów w witrynie e-Commerce.](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Zawsze używaj modułów kolekcji produktów, aby wyświetlić grupę produktów podobnego typu.

## <a name="product-collection-modules-and-types"></a>Moduły kolekcji produktów i ich typy

W poniższej tabeli opisano różne typy modułów kolekcji produktów w Dynamics 365 Commerce.

| Moduł kolekcji produktów  | Typ | Opis |
|----------------------------|------|-------------|
| Kategoria                   | Kategoria | Ten moduł pokazuje listę produktów w kategorii zgodnie z definicją w hierarchii kategorii nawigacji, którą sprzedawca detaliczny utworzył dla kanału handlu. |
| Powiązane produkty           | Redakcyjne | Ten moduł pokazuje listę produktów skonfigurowanych przez menedżera merchandisingu jako powiązane produkty w aplikacji Commerce dla typu relacji wybranego przez autora. |
| Wyniki wyszukiwania             | Zapytanie wyszukiwania | Ten typ modułu kolekcji produktów pokazuje listę produktów, które najlepiej pasują do zapytania wyszukiwania wprowadzonego przez klienta. |
| Lista wyselekcjonowanych produktów      | Redakcyjne | Ten moduł pokazuje niestandardowe listy utworzone przez sprzedawców i redaktorów w aplikacji Commerce. |
| Nowy element                        | Algorytmy | Ten moduł pokazuje listę najnowszych produktów w asortymentach do kanałów i katalogów. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Bestsellery               | Algorytmy | Ten moduł pokazuje listę produktów sklasyfikowanych według najwyższej liczby sprzedaży. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Popularne                   | Algorytmy | Ten moduł pokazuje listę produktów najwyższej wydajności w danym okresie. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Często kupowane razem | Sztuczna inteligencja/uczenie maszynowe | Ten moduł używa uczenia maszynowego do analizowania wzorów zakupów klientów i rekomendowanych często kupowanych razem z danym produktem towarów. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Klienci także lubią           | Sztuczna inteligencja/uczenie maszynowe | Ten moduł używa uczenia maszynowego do analizowania wzorców zakupów klientów i powiązanych z produktem rekomendowanych towarów. Ta lista może zawierać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję. |
| Wybrane dla Ciebie              | Sztuczna inteligencja/uczenie maszynowe | Ten modułu używa uczenia maszynowego do analizowania wzorców zakupu zalogowanego użytkownika i dostarczania spersonalizowanych rekomendacji opartych na tych wzorcach zakupu. W przypadku użytkownika gościa ta lista zostanie zwinięta. |

## <a name="supported-modules"></a>Obsługiwane moduły 

Moduł kolekcji produktów obsługuje [moduł szybkiego poglądu](quick-view-module.md), który umożliwia użytkownikom przeglądanie informacji o produktach i dodawanie towarów do koszyka ze strony kolekcji produktów.

## <a name="add-a-product-collection-module-to-a-category-page"></a>Dodawanie modułu kolekcji produktów do strony kategorii

Aby dodać moduł kolekcji produktów do strony kategorii, wykonaj następujące kroki.

1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz ten sam szablon, który jest używany przez domyślną stronę kategorii. W sekcji **Nazwa strony** wpisz odpowiednią nazwę, a następnie wybierz przycisk **OK**.
1. W gnieździe **Stopka podrzędna** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Kolekcja prodktów** i wybierz przycisk **OK**.  
1. W okienku właściwości modułu kolekcja produktów wybierz opcję **Dodaj listę produktów**.
1. W oknie dialogowym **Wybór konfiguracji listy produktów** wybierz typ listy, źródło listy i wprowadź liczbę towarów. Skonfiguruj inne opcje dostępne dla typu listy. Aby uzyskać więcej informacji o typach list, zobacz poniższą tabelę. 
1. Kliknij przycisk **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

W poniższej tabeli przedstawiono typy list, które są dostępne do wybrania w oknie dialogowym **Wybór konfiguracji listy produktów**.

| Typ                       | Opis | Użycie | Kontekst strony | Określony kontekst | Personalizacja |
|----------------------------|-------------|-------|--------------|------------------|-----------------|
| Produkty według kategorii       | Lista produktów należących do danej kategorii. Ta kategoria jest określana na podstawie kontekstu strony lub kontekstu podanego przez autora. | Ten typ listy może być używany na dowolnej stronie (na przykład na stronie głównej, stronie kategorii, stronie marketingowej lub stronie szczegółów produktu \[PDP\]) w celu promowania określonej kategorii produktów. | Kategoria z kontekstu strony, jeśli jest dostępna (na przykład strona kategorii) | Autor może udostępnić określoną kategorię jako kontekst dla listy. | Nie dotyczy |
| Powiązane produkty           | Lista produktów, które menedżer ds. merchandisingu skonfigurował jako produkty powiązane dla typu relacji w aplikacji Commerce. | Ten typ listy jest używany głównie na stronach PDP, ale może być używany na dowolnej stronie w przypadku określenia produktu nadrzędnego. | Produkt ze strony, typ relacji (obowiązkowy) | Produkt można wybrać w selektorze, a typ relacji jest używany. | Nie dotyczy |
| Pod opieką                    | Lista niestandardowa utworzona przez sprzedawców i redaktorów w Commerce. | Wzbogacanie strony kategorii, strony głównej, strony realizacji transakcji i koszyka oraz strony produktów | Nie dotyczy | Nie dotyczy | Nie dotyczy |
| Algorytmy                | <ul><li>**Nowości** — lista najnowszych produktów w asortymentach do kanałów i katalogów.</li><li>**Bestsellery** — Lista produktów sklasyfikowanych według najwyższej liczby sprzedaży.</li><li>**Trendy** — Lista produktów najwyższej wydajności w danym okresie.</li></ul> | Stronw główna, wzbogacanie strony kategorii, strony realizacji transakcji i koszyka | Kategoria z kontekstu strony (na przykład strona kategorii) | Kategoria, która jest określana przez autora witryny | Obsługiwana |
| Często kupowane razem | Lista, która używa uczenia maszynowego do analizowania wzorców zakupów klientów i rekomendowanych często kupowanych razem z danym produktem towarów. | Ten typ listy ma zastosowanie tylko do strony koszyka. | Koszyk | Nie dotyczy | Obsługiwana |
| Klienci także lubią           | Lista, która używa nauki maszynowej do analizowania wzorów zakupów klientów i powiązanych z produktem towarów. | Ten typ listy jest używany na stronach PDP w celu wyświetlenia produktów kupionych przez innych klientów. | Kontekst produktu ze strony | Produkt dostarczony przez autora witryny | Obsługiwana |
| Wybrane dla Ciebie              | Lista, która używa uczenia maszynowego do określenia preferencji klienta. | Ten typ listy może być używany na dowolnej stronie. | Nie dotyczy| Nie dotyczy | Obsługiwana | 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł karuzeli](add-carousel.md)

[Moduł zaawansowanego bloku zawartości](add-content-rich-block.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Omówienie rekomendacji produktów](product-recommendations.md)

[Moduł szybkiego podglądu](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
