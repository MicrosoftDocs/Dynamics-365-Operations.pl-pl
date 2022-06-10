---
title: Moduł aktywnego obrazu
description: W tym temacie opisano moduły aktywnych obrazów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
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
ms.openlocfilehash: 06b9162029de3f5f3fede9583fa8a4a96fefb2f3
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780292"
---
# <a name="active-image-module"></a>Moduł aktywnego obrazu

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły aktywnych obrazów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Aktywny moduł obrazu może służyć do osadzania tagów produktów na obrazie. Użytkownicy witryny e-commerce mogą następnie najechać kursorem na tagi, aby wyświetlić podgląd produktów widocznych na obrazie. Podglądy są wyświetlane w wyskakujących oknach. Wybierając wyskakujące okienko podglądu, użytkownicy mogą przejść bezpośrednio do strony szczegółów produktu (PDP) odpowiedniego produktu.

Tagi są definiowane za pomocą współrzędnych X i Y na obrazie. Każdy oznaczony punkt powinien być skonfigurowany z identyfikatorem produktu, który jest widoczny na obrazku.

Poniższa ilustracja przedstawia przykład wyskakującego okna podglądu na obrazie bohatera na stronie głównej Adventure Works.

![Przykład okna podręcznego podglądu w aktywnym module obrazów](./media/Active_image.PNG)

> [!IMPORTANT]
> - Aktywny moduł obrazu jest dostępny od wersji 10.0.20 Dynamics 365 Commerce.
> - Aktywny moduł obrazu jest prezentowany w motywie Adventure Works.

## <a name="active-image-module-properties"></a>Właściwości aktywnego modułu obrazu

| Nazwa właściwości      | Wartości | opis |
|--------------------|--------|-------------|
| Wizerunek              | Plik obrazu | Obrazu można użyć do zaprezentowania jednego lub większej liczby produktów. Obraz można przesłać do Biblioteki multimediów w narzędziu do tworzenia witryn Commerce lub użyć istniejącego obrazu. |
| Szerokość              | Liczba pikseli | Ta właściwość definiuje szerokość obrazu. Aktywne współrzędne są obliczane na podstawie szerokości obrazu.|
| Aktywne współrzędne | Współrzędne X i Y oraz numer identyfikacyjny produktu | Każda aktywna tablica obrazów składa się ze współrzędnych X i Y oraz numeru identyfikacyjnego produktu.|
| Nagłówek            | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Domyślnie jest używany znacznik nagłówka **H2**, ale znacznik nagłówka jest używany, ale tag nagłówka można zmienić, aby spełnić wymagania dotyczące dostępności. |
| Akapit          | Tekst akapitu | Moduł obsługuje tekst akapitowy w formacie tekstu sformatowanego. Obsługiwane są niektóre podstawowe funkcje tekstu sformatowanego, takie jak hiperłącza, pogrubienie, podkreślenie i kursywa. Niektóre z tych możliwości mogą być zastąpione przez motyw strony stosowany do modułu. |
| Link               | Tekst łącza, adres URL łącza, dostęp do bogatych aplikacji internetowych (ARIA) i **Otwórz łącze na nowej karcie** | Moduł obsługuje łącza do jednego lub wielu „wywołań akcji”. Jeśli zostanie dodane łącze, tekst łącza, adres URL i etykieta ARIA są wymagane. Etykiety ARIA powinny być opisowe w celu spełnienia wymagań dotyczących ułatwień dostępu. Łącza można tak skonfigurować, aby były otwierane na nowej karcie. |
| Tekst podrzędny           | Nagłówek, tekst i łącza | Można dodać dodatkowy kontekst do obrazu, taki jak nazwisko autora lub projektanta albo linki do osobistych blogów.|
| Motyw tekstu         | **Jasny** lub **ciemny** | Ta właściwość umożliwia użytkownikowi ustawienie jasnego lub ciemnego tekstu na podstawie obrazu tła. Jest to dostępne jako rozszerzenie motywu w motywie Adventure Works. |

## <a name="add-an-active-image-module-to-a-new-page"></a>Dodaj aktywny moduł obrazu do nowej strony

Aby dodać aktywny moduł obrazu do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do formularza **Szablony** i otwórz szablon marketingowy dla strony głównej witryny (lub utwórz nowy szablon marketingowy).
1. W gnieździe **Głównym** na stronie domyślna wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Aktywny obraz** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do formularza **Strony** i otwórz stronę główną witryny (lub utwórz nową stronę główną, używając szablonu marketingowego).
1. Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Aktywny obraz** i wybierz przycisk **OK**.
1. W okienku właściwości aktywnego modułu obrazu dodaj obraz i ustaw szerokość kanwy na rozmiar obrazu.
1. Należy ustawić współrzędne X i Y i dodać odpowiedni numer identyfikacyjny produktu.
1. Dodaj i skonfiguruj dodatkowe aktywne moduły obrazu zgodnie z potrzebami.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Motyw Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
