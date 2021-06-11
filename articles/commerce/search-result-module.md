---
title: Moduł wyników wyszukiwania
description: W tym temacie omówiono moduły wyników wyszukiwania i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 645022000d8746db3793a8a8611ab8f17c7bcc6e
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117140"
---
# <a name="search-results-module"></a>Moduł wyników wyszukiwania

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie omówiono moduły wyników wyszukiwania i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł wyników wyszukiwania zwraca wyniki wyszukiwania produktów oraz listę odpowiednich rafinerów dla produktów. Moduły wyników wyszukiwania w witrynach Dynamics 365 Commerce mogą służyć do renderowania stron w następujących scenariuszach:

- Wyniki wyszukiwania inicjowane przez użytkownika
- Wyniki wyszukiwania, w których jest pokazywany określony zestaw produktów, na przykład „Kup podobne"
- Lista produktów należących do danej kategorii

Aby uzyskać więcej informacji o kategoriach i stronach wyników wyszukiwania, zobacz [Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania](category-search-page-overview.md).

Poniższa ilustracja przedstawia przykład strony wyników wyszukiwania dla kategorii w witrynie Fabrikam.

![Przykład strony wyników wyszukiwania w witrynie Fabrikam](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a>Właściwości modułu wyników wyszukiwania

W poniższej tabeli przedstawiono właściwości modułów wyników wyszukiwania wraz z ich wartościami i opisami.

| Właściwość | Wartości | opis |
|----------|--------|-------------|
| Liczba pozycji na stronie | Wartość całkowita | Liczba pozycji, które powinny być wyświetlane na każdej stronie. |
| Pozwól na powrót na PDP | **Prawda** lub **Fałsz** | Jeśli właściwość ma wartość **Prawda**, po wybraniu produktu na stronie wyników wyszukiwania na otwartej stronie szczegółów produktu (PDP) będzie wyświetlane łącze „Powrót do wyników”. |
| Rozwiń elementy uściślające | **Wszystkie**, **1**, **2**, **3** lub **4** | Liczba najlepszych rafinerów, które powinny zostać rozwinięte po załadowaniu strony. Na przykład, jeśli właściwość ma wartość **3**, zostaną rozwinięte pierwsze trzy udoskonalenia na stronie. |
| Ukryj wyświetlanie hierarchii kategorii | **Prawda** lub **Fałsz** | Jeśli właściwość ma wartość **Prawda**, hierarchia kategorii wyświetlana na stronie będzie ukryta. Właściwość powinna mieć wartość **Prawda**, jeśli do pokazywania hierarchii kategorii jest używany [moduł nawigacyjny](add-breadcrumb.md).|
| Uwzględnij atrybuty produktu w wynikach wyszukiwania | **Prawda** lub **Fałsz** | Jeśli właściwość ma wartość **Prawda**, w wynikach wyszukiwania zostaną zwrócone atrybuty. Chociaż te atrybuty mogą być wyświetlane w witrynie Commerce, wymagane jest rozszerzenie.|
| Pokaż ceny przynależności | **Prawda** lub **Fałsz** | Jeśli właściwość ma wartość **Prawda**, ceny przynależności produktów będą wyświetlane w wynikach wyszukiwania, gdy zalogowany użytkownik przegląda stronę. |
| Aktualizuj panel ulepszań | **Prawda** lub **Fałsz** | Jeśli właściwość ma wartość **True**, panel ulepszeń zostanie zaktualizowany po wybraniu ulepszaczy. W tym trybie niektóre ulepszenia wielosektorowe będą zachowywały się jak jednosektorowe, gdy panel ulepszeń zostanie zaktualizowany. |

> [!IMPORTANT]
> W wersji Commerce 10.0.16 i nowszych, konfiguracja **Pokaż ceny przynależności** może służyć do wyświetlania cen przynależności na stronie.
>
> W wersji Commerce 10.0.20 lub nowszej konfigurację **panelu aktualizacji** możesz zaktualizować panel ulepszeń podczas wyboru ulepszacza.

## <a name="supported-modules"></a>Obsługiwane moduły

Moduł wyników wyszukiwania obsługuje [moduł szybkiego poglądu](quick-view-module.md), który umożliwia użytkownikom przeglądanie informacji o produktach i dodawanie produkty do koszyka ze strony wyników wyszukiwania.

## <a name="add-a-search-results-module-to-a-category-page"></a>Dodawanie modułu wyników wyszukiwania do strony kategorii

Aby dodać moduł wyników wyszukiwania do strony kategorii, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Wyniki wyszukiwania** wprowadź nazwę, a następnie wybierz **OK**.
1. W gnieździe **Treść** wybierz wielokropek (...), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.
1. W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (...), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (...), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Nawigacyjny** i wybierz przycisk **OK**.
1. W okienku właściwości **szlaków nawigacyjnych** wprowadź wartość **1** dla wartości **Minimalne wystąpienia**.
1. W gnieździe **Kontener** wybierz wielokropek (...), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Wyniki wyszukiwania** i wybierz przycisk **OK**.
1. W okienku właściwości **Wyników wyszukiwania** wprowadź wartość **1** dla **Wartości Minimalne** występują, a następnie ustaw inne wymagane właściwości modułu wyników wyszukiwania. Ustawiając te właściwości w szablonie, zapewniasz, że wszelkie dostosowania do konkretnej strony kategorii będą automatycznie uwzględniać te ustawienia.
1. Wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować szablon.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz utworzony szablon **Wyników wyszukiwania**, wprowadź **Kategorię strony** dla **Nazwy strony**, a następnie kliknij przycisk **OK**. Ponieważ wszystkie wartości są ustawione w szablonie, strona jest gotowa do opublikowania.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania](category-search-page-overview.md)

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł szybkiego podglądu](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
