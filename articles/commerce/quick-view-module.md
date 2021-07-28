---
title: Moduł szybkiego podglądu
description: W tym temacie omówiono moduły szybkiego podglądu i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 5b9bb456659447697b685105fe64b083e01f690a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351971"
---
# <a name="quick-view-module"></a>Moduł szybkiego widoku

[!include [banner](includes/banner.md)]

W tym temacie omówiono moduły szybkiego podglądu i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł szybkiego podglądu pozwala użytkownikom szybko przeglądać informacje o produkcie podczas przeglądania produktów na stronie listy i dodawać jeden lub więcej produktów do koszyka ze strony listy, bez konieczności przechodzenia do strony szczegółów produktu (PDP). Moduł szybkiego podglądu zapewnia przegląd informacji o produkcie, których użytkownicy potrzebują, aby podjąć decyzję „dodaj do koszyka”. Zapewnia również łącze do PDP, dzięki czemu użytkownicy mogą przeglądać dodatkowe szczegóły produktu i opcje zakupu.

Moduł szybkiego widoku jest obsługiwany przez [moduły kolekcji produktów](product-collection-module-overview.md) i [wyników wyszukiwania](search-result-module.md).

> [!IMPORTANT]
> Moduł szybkiego podglądu jest dostępny od wersji Commerce 10.0.17.

Poniższa ilustracja przedstawia przykład modułu szybkiego podglądu na stronie listy produktów.

![Przykład modułu szybkiego podglądu na stronie listy produktów.](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a>Właściwości modułu

Moduł szybkiego podglądu obsługuje niektóre z tych samych funkcji, co moduł pola zakupu. Z tego względu właściwości modułu szybkiego widoku przypominają właściwości modułu pola zakupu.

| Właściwość | Wartości | opis |
|----------------|--------|-------------|
| Znacznik nagłówka | **H1**, **H2**, **H3**, **H4**, **H5** lub **H6** | Ta właściwość definiuje znacznik nagłówka dla produktu. Jeśli moduł szybkiego podglądu znajduje się u góry strony, ta właściwość powinna być ustawiona na **H1**, aby spełnić standardy dostępności. |
| Zezwalaj na cenę niestandardową | **Prawda** lub **Fałsz** | Jeśli właściwość ma wartość **True**, użytkownik może wprowadzić cenę niestandardową. |
| Cena minimalna | Wartość całkowita | Ta właściwość ma zastosowanie tylko w przypadku, gdy właściwość **Zezwalaj na cenę niestandardową** ma wartość **True**. Określa minimalną cenę, jaką użytkownik może wprowadzić (na przykład $1). |
| Cena maksymalna | Wartość całkowita | Ta właściwość ma zastosowanie tylko w przypadku, gdy właściwość **Zezwalaj na cenę niestandardową** ma wartość **True**. Określa maksymalną cenę, jaką użytkownik może wprowadzić (na przykład $1,000). |

## <a name="commerce-site-builder-settings"></a>Ustawienia konstruktora witryn

Podobnie jak moduł pola zakupu, moduł szybkiego wyświetlania respektuje ustawienia w **Ustawienia witryny \> Rozszerzenia \> Dodaj produkt do koszyka**. Jednak ustawienie **Przejdź do strony koszyka** jest ignorowane, ponieważ jest niezgodne z celem modułu szybkiego podglądu, którym jest umożliwienie użytkownikom przeglądania wielu produktów na stronie listy i dodawania ich do koszyka bez opuszczania strony z listą.

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a>Dodaj moduł szybkiego podglądu do modułu kolekcji produktów

Do kolekcji produktów i modułów wyników wyszukiwania można dodać moduł szybkiego podglądu.

Aby dodać moduł szybkiego podglądu do modułu kolekcji produktów w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do **Strony**, a następnie wybierz stronę główną witryny Fabrikam.
1. Przejdź do dowolnego modułu **Kolekcji produktów** na stronie głównej, wybierz wielokropek (**...**), a następnie wybierz opcję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Szybkiego podglądu** i wybierz przycisk **OK**.
1. W okienku właściwości modułu **Szybki podgląd** wybierz pozycję **Nagłówek**. W oknie dialogowym **Nagłówek** ustaw w polu **Poziom nagłówka** wartość **H2**, a następnie wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł kolekcji produktów](product-collection-module-overview.md)

[Moduł wyników wyszukiwania](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
