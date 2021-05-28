---
title: Zarządzanie zmianami projektowymi — FAQ
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące funkcji zarządzania zmianami projektowymi.
author: t-benebo
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-25
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 69232eed8520bafeb734ffad43b333bf9e36909e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018692"
---
# <a name="engineering-change-management-faq"></a>Zarządzanie zmianami projektowymi — FAQ

[!include [banner](../includes/banner.md)]

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące funkcji zarządzania zmianami projektowymi.

## <a name="should-i-track-the-version-in-transactions"></a>Czy wersja powinna być śledzona w transakcjach?

Podczas tworzenia kategorii zmian projektowych strona **Szczegóły kategorii zmian projektowych** zawiera opcję o nazwie **Śledź wersję w transakcjach**. Jakie jest to ustawienie i co to jest?

- Jeśli w opcji **Śledź wersję w transakcjach** zostanie ustawiona wartość *Tak*, pole **Grupa wymiarów** będzie filtrowane w taki sposób, aby wyświetlać tylko grupy wymiarów, w których wersja jest aktywnym wymiarem.
- Jeśli w opcji **Śledź wersję w transakcjach** zostanie ustawiona wartość *Nie*, pole **Grupa wymiarów** będzie filtrowane w taki sposób, aby wyświetlać tylko grupy wymiarów, w których wymiar wersji **nie** jest aktywnym wymiarem.

### <a name="if-you-track-the-version-in-transactions"></a>Jeśli wersja jest śledzona w transakcjach

Dla kategorii projektowych, w których wybrano grupę wymiarów, w której wersja jest aktywnym wymiarem, będzie można śledzić wersje w transakcjach dla produktów z tej kategorii. W tym przypadku produkt projektowy będzie produktem głównym, a każda wersja produktu będzie wariantem produktu korzystającym z wymiaru wersji. Inne wymiary mogą być używane razem z wymiarem wersji.

W takim przypadku każda wersja projektowa będzie traktowana we wszystkich procesach jako wariant. Jeśli więc w transakcji jest określony wariant (można ustalić, który wariant został sprzedany lub zakupiony), trzeba zarządzać zapasami dla każdej wersji, planowanie główne będzie planować dostawy dla każdej wersji itp. W przypadku wycofywania wersji z rynku należy ręcznie zmienić jej daty rozpoczęcia i zakończenia, aby odzwierciedlały zmianę. Należy również zarządzać zapasami, aby mieć pewność, że w magazynach nie znajdują się nieużywane wersje towarów.

Chociaż ta opcja wymaga większej ilości nakładów pracy w zakresie zarządzania, zaleca się ją w przypadku, gdy wymagane są duże możliwości śledzenia określonych wersji używanych w każdej transakcji.

### <a name="if-you-dont-track-the-version-in-transactions"></a>Jeśli wersja nie jest śledzona w transakcjach

Dla kategorii projektowych, w których wybrano grupę wymiarów, w której wersja **nie** jest aktywnym wymiarem, wersje **nie** będą śledzone w transakcjach dla produktów z tej kategorii. W takim przypadku, jeśli nie zostanie nadany żaden inny wymiar, produkt projektowy będzie odrębnym produktem. Produkt będzie nadal podlegał kontroli wersji i będzie można zarządzać informacjami o określonych wersjach (na przykład \[BOM] i marszruty), ale nie będzie można śledzić, które wersje były używane w każdej transakcji. Daty rozpoczęcia i zakończenia obowiązywania wskazują ważność każdej wersji.

Ta opcja jest o wiele łatwiejsza do zarządzania, ponieważ jeśli chcesz zmienić jedną wersję, wystarczy wprowadzić wymagane zmiany w zamówieniu zmian, a następnie zaktualizować daty wejścia w życie i zakończenia w wersji projektowej. Procesy produkcyjne będą brać wymagany BOM i marszrutę dla produktu (i jego określonej wersji).

Większość organizacji wybiera tę opcję, ponieważ zapewnia zarządzanie wersjami i zmianami, ale nie powoduje to dodatkowych kosztów ogólnych śledzenia wersji w poszczególnych transakcjach, zapasach i podczas planowania głównego.

## <a name="which-fields-are-copied-to-the-released-item-template"></a>Które pola są kopiowane do zwolnionego szablonu towaru?

Gdy firma projektowa tworzy produkt projektowy, jest on tworzony jako zwolniony produkt w firmie projektowej. Zwolniony produkt, który jest tworzony na podstawie wybranego *szablonu zwolnionego towaru*. (Szablon zwolnionego towaru jest już istniejącym zwolnionym produktem). Zwolniony szablon towaru jest również używany podczas zwalniania produktu do firmy operacyjnej. W każdym przypadku zwolniony szablon towaru definiuje większość wartości pól dla zwolnionego produktu, a te wartości pochodzą ze skojarzonej strony **Szczegóły zwolnionego produktu**.

W poniższych tabelach przedstawiono pola kopiowane podczas tych procesów.

| Skrócona karta | Pola kopiowane przy tworzeniu produktu w firmie projektowej | Pola kopiowane w ramach zwolnienia do firmy operacyjnej |
|---|---|---|
| **Ogólny** | Wszystkie pola w sekcji **Administracja** | Te same pola, które są kopiowane dla firmy projektowej |
| **Zakup** | Wszystkie pola | Wszystkie pola z wyjątkiem **Jednostka** |
| **Sprzedaż** | Wszystkie pola w następujących sekcjach: **Zamówienie sprzedaży**, **Administracja**, **Opodatkowanie**, **Aktualizacja ceny**, **Podstawowa cena sprzedaży**, **Opłaty**, **Rabaty** i **Produkt alternatywny** | Wszystkie te same pola, które są kopiowane dla firmy projektowej, z wyjątkiem **Jednostka** |
| **Handel zagraniczny** | Wszystkie pola | Wszystkie pola |
| **Zapasy** | Wszystkie pola i sekcje *z wyjątkiem* pól **Wymiary fizyczne** i **Ilość efektywna** | Wszystkie te same pola, które są kopiowane dla firmy projektowej, z wyjątkiem **Jednostka** |
| **Konstruuj**, **Planuj**, **Zarządzaj kosztami**, **Zarządzaj projektami**, **Wymiary finansowe** i **Magazyn** | Wszystkie pola | Wszystkie pola z wyjątkiem **Jednostka BOM** |
| **Warianty produktu** | Wszystkie pola w sekcji **Domyślny wariant produktu** | Te same pola, które są kopiowane dla firmy projektowej |

Oprócz pól widocznych w poprzedniej tabeli wszystkie domyślne ustawienia zamówienia są kopiowane ze zwolnionego szablonu towaru, zarówno podczas tworzenia produktu w firmie projektowej, jak i po zwolnieniu do firmy operacyjnej. (Aby wyświetlić domyślne ustawienia zamówienia dla zwolnionego szablonu towaru, otwórz odpowiednią stronę **Szczegóły zwolnionego produktu**, a następnie, w okienku akcji, na karcie **Zarządzanie zapasami** wybierz opcję **Ustawienia domyślne zamówień**).

## <a name="should-i-create-a-separate-legal-entity-for-engineering-products-or-use-an-existing-legal-entity"></a>Czy należy utworzyć odrębną osobę prawną do tworzenia produktów czy używać istniejącej?

Od wymagań biznesowych zależy, czy należy utworzyć nową osobę prawną do tworzenia produktów projektowych.

Tworząc osobną firmę projektową, można oddzielać dane projektowe, a następnie dodawać modyfikacje wymagane w lokalnych firmach operacyjnych. W ten sposób można osiągnąć następujące cele:

- Zachowanie odrębnej osoby prawnej, w której są tworzone i zarządzane produkty projektowe.
- Zapobieganie pojawianiu się produktów projektowych razem z innymi zwolnionymi produktami, dopóki nie będą gotowe i zwolnione.
- Dane projektowe są wyraźnie odróżnione od lokalnych.

Z drugiej strony, prawdopodobnie należy użyć już istniejącej osoby prawnej jako firmy projektowej, jeśli mają zastosowanie następujące warunki:

- W systemie jest tylko jedna osoba prawna i/lub nie jest wymagane jednoznaczne rozdzielenie między produktami, które są projektowane.
- Nie chcesz duplikować niektórych danych, takich jak grupy zasobów, zasoby, operacje i (być może) witryny.

## <a name="what-is-the-nomenclature-for-engineering-versions-and-variants"></a>Jakie jest nazewnictwo wersji i wariantów projektowych?

Nazewnictwo produktów i wariantów produktów projektowych działa w następujący sposób:

- W przypadku produktu projektowego (tj. odrębnego produktu, jeśli nie są używane wymiary, lub produktu głównego, jeśli jest używany dowolny wymiar), nazewnictwo reguł numerowania jest definiowane w kategorii produktów projektowych. W tym miejscu można użyć sekwencji numerów, stałych tekstowych oraz nazw i wartości atrybutów.
- Dla każdego wariantu produktu projektowego (jeśli produkt projektowy jest produktem głównym, warianty są ustawiane w kategorii produktów projektowych, w której jest określana grupa wymiarów), nazewnictwo reguł numerowania dla każdego wariantu jest definiowane w grupie wymiarów. W takim przypadku można użyć identyfikatora produktu głównego oraz wartości i nazw wymiarów.
