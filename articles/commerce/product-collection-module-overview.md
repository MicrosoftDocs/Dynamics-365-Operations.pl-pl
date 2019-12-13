---
title: Moduły kolekcji produktów
description: Ten temat stanowi przegląd modułów kolekcji produktów w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 44f78b55b8e67b7358be75aa63c40a0147507e26
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785474"
---
# <a name="product-collection-modules"></a>Moduły kolekcji produktów  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ten temat stanowi przegląd modułów kolekcji produktów w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Odnajdowanie produktów to podstawowe narzędzie używane przez sprzedawców detalicznych, którzy mogą współpracować z klientami w witrynie e-Commerce. Moduły kolekcji produktów pomagają detalistom budować atrakcyjne doświadczenie, udostępniając intuicyjny interfejs graficzny, który może być używany do szybkiego tworzenia zbiorów produktów.

Moduły kolekcji produktów reprezentują fizyczne produkty i usługi w witrynie sieci Web. Moduł kolekcji produktów jest zazwyczaj połączony ze stroną szczegółów, w której klienci mogą zakupić produkt lub usługę, lub dowiedzieć się więcej o niej. 

Źródła dla kolekcji produktów mogą być listami trzech typów:

- Listy redakcyjne produktów, które zostały ręcznie zdefiniowane w Dynamics 365 Retail jako produkty pokrewne produktu lub na listach produktów
- Listy algorytmowe, takie jak listy nowości, najlepiej sprzedających sięproduktów lub trendów produktów
- Listy rekomendacji oparte na uczeniu maszynowym

Na poniższej ilustracji przedstawiono różne typy kolekcji produktów, które są używane w witrynie e-Commerce.

![Przykład różnych typów kolekcji produktów w witrynie e-Commerce](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Zawsze używaj modułów kolekcji produktów, aby wyświetlić grupę produktów podobnego typu lub motywu.

## <a name="product-collection-modules-and-types"></a>Moduły kolekcji produktów i ich typy

W poniższej tabeli opisano różne typy modułów kolekcji produktów w Dynamics 365 Commerce.

| Moduł kolekcji produktów  | Typ | Opis |
|----------------------------|------|-------------|
| Przeglądaj kategorie            | Redakcyjne | Ten typ modułu kolekcji produktów wykorzystuje hierarchię kategorii nawigacji, którą sprzedawca utworzył dla kanału sprzedaży detalicznej, aby pokazać przepływ przeglądania produktów oferowanych w określonej kategorii witryn. |
| Wyniki wyszukiwania             | Zapytanie wyszukiwania | Ten typ modułu kolekcji produktów pokazuje listę produktów, które najlepiej pasują do zapytania wyszukiwania wprowadzonego przez klienta. |
| Powiązane produkty           | Redakcyjne | Ten typ modułu kolekcji produktów pokazuje listę produktów skonfigurowanych przez menedżera merchandisingu jako powiązane produkty w Retail, dla typu relacji wybranego przez autora. |
| Lista wyselekcjonowanych produktów      | Redakcyjne | Ten typ modułu kolekcji produktów pokazuje listy niestandardowe, które zostały utworzone przez merchandiserów i redaktorów w Retail. |
| Nowy element                        | Algorytmy | Ten typ modułu kolekcji produktów zawiera listę najnowszych produktów, które zostały w asortymentie wyświetlane w postaci kanałów i katalogów. |
| Bestsellery               | Algorytmy | Ten typ modułu kolekcji produktów zawiera listę produktów sklasyfikowanych według najwyższej liczby sprzedaży. |
| Popularne                   | Algorytmy | Ten typ modułu kolekcji produktów zawiera listę produktów najwyższej wydajności w danym okresie. |
| Często kupowane razem | Sztuczna inteligencja/uczenie maszynowe | Moduł kolekcji produktów tego typu używa nauki maszyn do analizowania wzorów zakupów odbiorców i zalecanych często kupowanych towarów razem z danym produktem. |
| Klienci także lubią           | Sztuczna inteligencja/uczenie maszynowe | Moduł kolekcji produktów tego typu używa nauki maszyn do analizowania wzorów zakupów odbiorców i polecanych towarów powiązanych z danym produktem. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Dodawanie modułu kolekcji produktów do strony kategorii

Aby dodać moduł kolekcji produktów do strony kategorii, wykonaj następujące kroki.

1. W Dynamics 365 Commerce przejdź do swojej witryny i utwórz stronę, na której jest używany ten sam szablon, co domyślna strona kategorii.
1. W konspekcie strony wybierz gniazdo **Stopka podrzędna**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz **Kontener** i wybierz przycisk **OK**.
1. W module kontener wybierz przycisk wielokropka, a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz **Kolekcja produktu** i wybierz przycisk **OK**.
1. Skonfiguruj ustawienia wybierając odpowiednie źródło danych oraz dane wejściowe dla kolekcji produktów.
1. W okienku właściwości modułu kolekcja produktów wybierz opcję **Dodaj listę produktów**.
1. W oknie dialogowym **Wybór konfiguracji listy produktów** wybierz typ listy, wprowadź liczbę towarów i wybierz inne opcje dostępne dla typu listy. Aby uzyskać więcej informacji o typach list, zobacz poniższą tabelę. 
1. Kliknij przycisk **OK**.
1. Zapisz stronę i zaewidencjonuj ją.

W poniższej tabeli przedstawiono typy list, które są dostępne do wybrania w oknie dialogowym **Wybór konfiguracji listy produktów**.
   
| Typ                       | Opis | Ogólna praktyka | Kontekst, który może pochodzić z kontekstu strony | Kontekst, który autor może zastąpić kontekstem strony |
|----------------------------|-------------|------------------|-------------------------------------|-----------------------------------------------|
| Produkty według kategorii       | Lista produktów należących do danej kategorii. Ta kategoria jest określana na podstawie kontekstu strony lub kontekstu podanego przez autora. | Wzbogacanie strony kategorii, strony głównej, strony realizacji transakcji i koszyka oraz strony produktów | Kategoria | Kategoria określona przez autora |
| Powiązane produkty           | Lista produktów, które menedżer ds skonfigurował jako produkty powiązane w Retail dla typu relacji. | Strony produktów, kasy i strony koszyka, strona listy życzeń i strona konta klienta | Produkt, rodzaj relacji (obowiązkowe)  | Produkt, rodzaj relacji |
| Pod opieką                    | Lista niestandardowa utworzona przez sprzedawców i redaktorów w Retail. | Wzbogacanie strony kategorii, strony głównej, strony realizacji transakcji i koszyka oraz strony produktów | Nie dotyczy | Wybór listy |
| Algorytmy                | <ul><li>**Nowości** — lista najnowszych produktów w asortymentach do kanałów i katalogów.</li><li>**Bestsellery** — Lista produktów sklasyfikowanych według najwyższej liczby sprzedaży.</li><li>**Trendy** — Lista produktów najwyższej wydajności w danym okresie.</li></ul> | Stronw główna, wzbogacanie strony kategorii, strony realizacji transakcji i koszyka | Kategoria | Kategoria określona przez autora |
| Często kupowane razem | Lista, która używa nauki maszynowej do analizowania wzorów zakupów klientów i zalecanych często kupowanych razem z danym produktem towarów. | Strony produktów, strony realizacji transakcji i koszyka | Produkt, koszyk | Uwzględnij koszyk |
| Klienci także lubią           | Lista, która używa nauki maszynowej do analizowania wzorów zakupów klientów i powiązanych z produktem towarów. | Strony produktów, strony realizacji transakcji i koszyka | Produkt, koszyk | Nie dotyczy |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł karuzeli](add-carousel.md)

[Moduł zaawansowanego bloku zawartości](add-content-rich-block.md)

[Moduł umieszczania zawartości](add-content-placement-modules.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

