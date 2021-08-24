---
title: Moduł listy kafelków
description: W tym temacie opisano moduły listy kafelków i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
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
ms.openlocfilehash: 513775afe325008ebd6cd18d2d9485a972984090da3803d255a1584b16b1e014
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767858"
---
# <a name="tile-list-module"></a>Moduł listy kafelków

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły listy kafelków i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł listy kafelków to zbiór kafelków w karuzeli. Służy do promowania kategorii produktów lub marek produktów za pomocą obrazów i tekstu. Na przykład sprzedawca detaliczny może dodać moduł listy kafelków do strony głównej witryny e-commerce, aby promować wszystkie najlepiej sprzedające się kategorie.

Moduł listy kafelków jest sterowany przez dane z systemu zarządzania zawartością (CMS). Nie zależy od żadnych innych modułów ani danych z centrali Commerce headquarters. Moduł listy kafelków można dodać do każdej strony witryny, na której sprzedawca chce coś promować (np. produkty, kategorie lub marki).

Na poniższej ilustracji przedstawiono przykład modułu listy kafelków i modułów kafelków na stronie głównej Adventure Works.

![Przykład modułu listy kafelków i modułów kafelków na stronie głównej Adventure Works](./media/Tile_list.PNG)

> [!IMPORTANT]
> Moduł listy kafelków jest dostępny od wersji 10.0.20 Dynamics 365 Commerce.
> Moduł listy kafelków jest prezentowany w temacie Adventure Works.

## <a name="tile-list-modules-and-themes"></a>Moduły i motywy listy kafelków

Moduł listy kafelków może obsługiwać różne układy i style, w oparciu o motyw przewodni. Na przykład w motywie Adventure Works kafelki pokazują efekt animacji, gdy użytkownik witryny najedzie na nie kursorem. Każdy motyw może zawierać dodatkowe właściwości dla listy kafelków i modułów kafelków. Deweloperzy motywów mogą również tworzyć dodatkowe układy dla listy kafelków i modułów kafelków.

## <a name="tile-list-module-properties"></a>Właściwości modułu listy kafelków

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nagłówek       | Tekst nagłówka i tag nagłówka | Nagłówek tekstowy modułu listy kafelków. |

## <a name="tile-module-properties"></a>Właściwości modułu listy kafelków

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Wizerunek         | Plik obrazu | Obraz może służyć do pokazania produktu lub kategorii. Obraz można przesłać do Biblioteki multimediów w narzędziu do tworzenia witryn Commerce lub użyć istniejącego obrazu. |
| Nagłówek       | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Domyślnie jest używany znacznik nagłówka **H2**, ale znacznik nagłówka jest używany, ale tag nagłówka można zmienić, aby spełnić wymagania dotyczące dostępności. |
| Akapit     | Tekst akapitu | Moduł obsługuje tekst akapitowy w formacie tekstu sformatowanego. Obsługiwane są niektóre podstawowe funkcje tekstu sformatowanego, takie jak hiperłącza, pogrubienie, podkreślenie i kursywa. Niektóre z tych możliwości mogą być zastąpione przez motyw strony stosowany do modułu. |
| Link          | Tekst łącza, adres URL łącza, dostęp do bogatych aplikacji internetowych (ARIA) **i Otwórz łącze na nowej karcie** | Moduły obsługują łącza do jednego lub wielu „wywołań akcji”. Jeśli zostanie dodane łącze, tekst łącza, adres URL i etykieta ARIA są wymagane. Etykiety ARIA powinny być opisowe w celu spełnienia wymagań dotyczących ułatwień dostępu. Łącza można tak skonfigurować, aby były otwierane na nowej karcie. |
| Łącze kafelka     | Tekst łącza, adres URL łącza i selektora **Otwórz łącze na nowej karcie** | Ta właściwość służy do definiowania łącza „wywołanie akcji”. Jeśli zostanie dodane łącze, tekst łącza, adres URL i etykieta ARIA są wymagane. Etykiety ARIA powinny być opisowe w celu spełnienia wymagań dotyczących ułatwień dostępu. Łącza można tak skonfigurować, aby były otwierane na nowej karcie.|
| Ikona          | Wizerunek | Oprócz obrazu produktu lub kategorii można dodać symbol ikony. Obraz z symbolem ikony będzie wyświetlany nad obrazem produktu lub kategorii. |

## <a name="add-a-tile-list-module-to-a-new-page"></a>Dodawanie modułu listy kafelków do nowej strony

Aby dodać moduł listy kafelków do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do formularza **Szablony** i otwórz szablon marketingowy dla strony głównej witryny (lub utwórz nowy szablon marketingowy).
1. W gnieździe **Głównym** na stronie domyślna wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **AddDodaj moduł** wybierz moduł **Lista kafelków** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do formularza **Strony** i otwórz stronę główną witryny (lub utwórz nową stronę główną, używając szablonu marketingowego).
1. Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **AddDodaj moduł** wybierz moduł **Lista kafelków** i wybierz przycisk **OK**.
1. W okienku właściwości interaktywnego modułu listy kafelków dodaj nagłówek.
1. W gnieździe **Lista kafelków** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Moduł kafelków** i wybierz przycisk **OK**.
1. W okienku właściwości modułu kafelków dodaj obraz, nagłówek i symbol ikony.
1. Dodaj i skonfiguruj dodatkowe moduły kafelków zgodnie z potrzebami.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Motyw Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
