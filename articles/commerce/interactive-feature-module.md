---
title: Interaktywny moduł funkcyjny
description: W tym artykule omówiono interaktywne moduły funkcyjne i opisano sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: deee7c35cfc4293480fda74665429121b71bbfab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898526"
---
# <a name="interactive-feature-module"></a>Interaktywny moduł funkcyjny

[!include [banner](includes/banner.md)]

W tym artykule omówiono interaktywne moduły funkcyjne i opisano sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Interaktywne moduły funkcyjne to moduły przypominające mozaikę, które mogą być wykorzystywane do marketingu wielu kategorii produktów lub marek produktów za pomocą kombinacji obrazów i tekstu. Na przykład, sprzedawca detaliczny może dodać interaktywny moduł funkcji do strony głównej witryny handlowej, aby promować najlepiej sprzedające się kategorie. Interaktywny moduł funkcji przypomina moduł listy kafelków, ale ma inny układ i inną funkcjonalność interakcji.

Każdy interaktywny moduł funkcji jest zbiorem interaktywnych modułów elementów funkcji. Każdy moduł elementu funkcjonalnego jest napędzany przez dane z systemu zarządzania treścią (CMS). Nie zależy od żadnych innych modułów ani danych z centrali Commerce headquarters. Moduł funkcji interaktywnych można dodać do każdej strony witryny, na której sprzedawca chce coś promować (np. produkty, kategorie lub marki).

> [!IMPORTANT]
> - Interaktywny moduł funkcyjny jest dostępny od wersji 10.0.20 Dynamics 365 Commerce.
> - Interaktywny moduł funkcyjny jest prezentowany w temacie Adventure Works.

Poniższa ilustracja przedstawia przykład interaktywnego modułu funkcji na stronie głównej Adventure Works.

![Przykład interaktywnego modułu funkcji na stronie głównej Adventure Works](./media/Feature.PNG)

## <a name="interactive-feature-module-and-themes"></a>Interaktywny moduł funkcyjny i motywy

Interaktywny moduł funkcji może obsługiwać różne układy i style, w oparciu o motyw przewodni. Na przykład, w motywie Adventure Works, moduł funkcji interaktywnych ma układ dwukolumnowy, który pokazuje efekty animacji, gdy użytkownik witryny najeżdża kursorem na każdy element. Moduł interakcyjny został zoptymalizowany pod kątem równomiernej liczby obrazów rozmieszczonych w układzie dwóch kolumn.

## <a name="interactive-feature-module-properties"></a>Właściwości interaktywnego modułu funkcji

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nagłówek       | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Nagłówek tekstu dla modułu interakcyjnych funkcji. |

## <a name="interactive-feature-item-module-properties"></a>Właściwości interaktywnego modułu elementu funkcji

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Wizerunek         | Plik obrazu | Obraz reprezentujący produkt lub kategorię. Obraz można przesłać do Biblioteki multimediów w narzędziu do tworzenia witryn Commerce lub użyć istniejącego obrazu. |
| Nagłówek       | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Domyślnie jest używany znacznik nagłówka **H2**, ale znacznik nagłówka jest używany, ale tag nagłówka można zmienić, aby spełnić wymagania dotyczące dostępności. |
| Akapit     | Tekst akapitu | Moduł obsługuje tekst akapitowy w formacie tekstu sformatowanego. Obsługiwane są niektóre podstawowe funkcje tekstu sformatowanego, takie jak hiperłącza, pogrubienie, podkreślenie i kursywa. Niektóre z tych możliwości mogą być zastąpione przez motyw strony stosowany do modułu. |
| Link          | Tekst łącza, adres URL łącza, dostęp do bogatych aplikacji internetowych (ARIA) i **Otwórz łącze na nowej karcie** | Moduł obsługuje łącza do jednego lub wielu „wywołań akcji”. Jeśli zostanie dodane łącze, tekst łącza, adres URL i etykieta ARIA są wymagane. Etykiety ARIA powinny być opisowe w celu spełnienia wymagań dotyczących ułatwień dostępu. Łącza można tak skonfigurować, aby były otwierane na nowej karcie. |

## <a name="add-an-interactive-feature-module-to-a-new-page"></a>Dodaj interaktywny moduł funkcyjny do nowej strony

Aby dodać interaktywny moduł funkcyjny do nowej strony i ustawić wymagane właściwości w kreatorze witryn Commerce, wykonaj poniższe kroki.

1. Przejdź do formularza **Szablony** i otwórz szablon marketingowy dla strony głównej witryny (lub utwórz nowy szablon marketingowy).
1. W gnieździe **Głównym** na stronie domyślna wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz modułu** wybierz moduł **Funkcja interaktywna** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do formularza **Strony** i otwórz stronę główną witryny (lub utwórz nową stronę główną, używając szablonu marketingowego).
1. Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** w obszarze **Wybierz moduły** wybierz moduł **Funkcja interaktywna** i wybierz przycisk **OK**.
1. W okienku właściwości interaktywnego modułu funkcji dodaj nagłówek.
1. W gnieździe **Funkcja interaktywna** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz modułu** wybierz moduł **Element funkcji interaktywnej** i wybierz przycisk **OK**.
1. W okienku właściwości modułu interaktywnego elementu funkcji dodaj obraz, tekst nagłówka, tekst akapitu i adres URL.
1. Dodawaj i konfiguruj dodatkowe interaktywne moduły elementów funkcyjnych zgodnie z potrzebami.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Motyw Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
