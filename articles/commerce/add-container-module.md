---
title: Moduł kontenera
description: W tym artykule opisano moduły kontenera i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 58fa222dfef9e559da00fef448c572800651bd63
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272915"
---
# <a name="container-module"></a>Moduł kontenera

[!include [banner](includes/banner.md)]

W tym artykule opisano moduły kontenera i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł kontenerowy to moduł, który obsługuje inne moduły w nim zawarte. Podstawowym celem modułu kontenera jest zdefiniowanie, za pomocą ustawionych dla niego właściwości, układu modułów, które zawiera. Na przykład moduły te mogą pojawiać się obok siebie w układzie dwukolumnowym, trzykolumnowym, czterokolumnowym lub sześciokolumnowym. Mogą być także ograniczone do szerokości kontenera lub mogą wypełniać ekran. Nagłówek można również dodać do każdego modułu kontenerów.

Trzy standardowe typy modułów kontenerowych są obsługiwane: kontener, kontener z dwoma gniazdami i kontener z trzema gniazdami. Moduły dowolnego typu mogą być umieszczane wewnątrz tych kontenerów. 

> [!NOTE] 
> Zawsze zaleca się umieszczanie modułów wewnątrz modułu kontenera, tak aby można je było ograniczyć do szerokości kontenera.

## <a name="examples-of-container-modules-in-e-commerce"></a>Przykłady modułów kontenerów w e-Commerce

- Autor witryny chce mieć trzy kolumny układu, gdzie trzy moduły są wyświetlane obok siebie. W związku z tym autor witryny używa modułu kontenera o typie kontener z trzema gniazdami.
- Autor witryny chce mieć sześć kolumny układu, gdzie sześć modułów są wyświetlane obok siebie. Dlatego autor witryny używa kontenera typu zawierającego, który ma w sobie sześć kolumn.
- Autor strony chce umieścić moduł na stronie, ale nie chce, aby wypełniał ekran. Dlatego autor strony dodaje moduł do modułu kontenera i ustawia właściwość kontenera **Szerokość** na **Dopasowana do kontenera**.

Poniższy obraz przedstawia przykład modułu kontenera zawierającego moduł karuzeli w konstruktorze witryn Commerce. W tym przykładzie właściwość **Szerokość** modułu kontenera jest ustawiona na **Wypełnij ekran**.

![Przykład modułu kontenera.](./media/ecommerce-container.PNG)

## <a name="container-module-properties"></a>Właściwości modułu kontenera

| Nazwa właściwości     | Wartości | opis |
|-------------------|--------|-------------|
| Nagłówek           | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Dla kontenera można podać opcjonalny nagłówek. Domyślnie w nagłówku jest używany znacznik nagłówka **H2**. Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności. |
| Szerokość             | **Dopasuj do kontenera** lub **ekran wypełnienia** | Jeśli wartość jest ustawiona na **Dopasowana do kontenera** (domyślna), moduły wewnątrz kontenera są ograniczone do szerokości kontenera. Jeśli wartość jest ustawiona na **wypełnienie ekranu**, moduły nie są ograniczone do szerokości kontenera, ale mogą wypełnić ekran. |
| Liczba kolumn | **1**, **2**, **3**, **4**, **6** lub **12** | Właściwość ta definiuje liczbę kolumn w kontenerze. Kontener może mieć do 12 kolumn. |

## <a name="container-with-2-slots"></a>Kontener z 2 okienkami

Kontener o typie 2-gniazdowym jest zoptymalizowany dla układu o dwóch kolumnach. Ten typ kontenera ma dwa gniazda, w których można włączyć widok obok siebie modułów znajdujących się wewnątrz.

Za pomocą dodatkowych właściwości można zoptymalizować układ dla różnych portów widoku (urządzeń przenośnych, tabletów, komputerów itp.). Dla każdego portu widoku można zdefiniować szerokość każdej kolumny. Dostępne są następujące ustawienia szerokości kolumny:

- **75%/25%** — pierwszy moduł ma szerokość kolumny 75 procent, a drugi moduł ma szerokość kolumny 25 procent. Dostępna jest również opcja **25%/75%**.
- **50%/50%** — oba moduły mają jednakową szerokość kolumny.
- **67%/33%** — pierwszy moduł ma szerokość kolumny 67 procent, a drugi moduł ma szerokość kolumny 33 procent. Dostępna jest również opcja **33%/67%**.
- **100%** — oba moduły mają pełną szerokość kolumny. Z tego względu moduły są ułożone pionowo w jednej kolumnie. Chociaż ten Układ jednokolumnowy jest oparty na kontenerze o typie dwóch gniazd, można go uzyskać w przypadku niektórych portów widoku (np. bardzo małe porty widoku, np. urządzenia przenośne).

### <a name="container-with-2-slots-properties"></a>Właściwości kontenera z dwoma gniazdami

| Nazwa właściwości                   | Wartości | Opis |
|---------------------------------|--------|-------------|
| Nagłówek                         | Tekst nagłówka i tag nagłówka | Dla kontenera można podać opcjonalnie nagłówek. |
| X-Konfiguracja portu małego widoku | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** lub **100%** | Właściwość ta definiuje układ bardzo małych portów widoku. |
| Konfiguracja portu małego widoku   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** lub **100%** | Właściwość ta definiuje układ bardzo małych portów widoku, takich jak urządzenia mobilne. |
| Konfiguracja średnich portów widoku  | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** lub **100%** | Właściwość ta definiuje układ średnich portów widoku, takich jak tablety. |
| Konfiguracja dużych portów widoku   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** lub **100%** | Właściwość ta definiuje układ dużych portów widoku, takich jak komputery. |

## <a name="container-with-3-slots"></a>Kontener z 3 okienkami

Kontener o typie modułu 3-gniazdowym jest zoptymalizowany dla układu o trzech kolumnach.

Za pomocą dodatkowych właściwości można zoptymalizować układ dla różnych portów widoku. Dla każdego portu widoku można zdefiniować szerokość każdej kolumny. Dostępne są następujące ustawienia szerokości kolumny:

- **33%/33%/33%** — wszystkie trzy moduły mają jednakową szerokość kolumny.
- **50%/25%/25%** — pierwszy moduł ma szerokość kolumny 50 procent, a każdy z pozostałych dwóch modułów ma szerokość kolumny 25 procent. Dostępne są także opcje **25%/50%/25%** i **25%/25%/50%**.
- **16%/16%/67%** — Każdy z dwóch pierwszych modułów ma szerokość kolumny 16 procent, a trzeci moduł ma szerokość kolumny 67 procent. Dostępne są także opcje **16%/67%/16%** i **67%/16%/16%**.

### <a name="container-with-3-slots-properties"></a>Właściwości kontenera z trzema gniazdami

| Nazwa właściwości                   | Wartości | Opis |
|---------------------------------|--------|-------------|
| Nagłówek                         | Tekst nagłówka i tag nagłówka | Dla kontenera można dodać opcjonalny nagłówek. |
| X-Konfiguracja portu małego widoku | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** lub **67%/16%/16%** | Właściwość ta definiuje układ bardzo małych portów widoku. |
| Konfiguracja portu małego widoku   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** lub **67%/16%/16%** | Właściwość ta definiuje układ bardzo małych portów widoku, takich jak urządzenia mobilne. |
| Konfiguracja średnich portów widoku  | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** lub **67%/16%/16%** | Właściwość ta definiuje układ średnich portów widoku, takich jak tablety. |
| Konfiguracja dużych portów widoku   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** lub **67%/16%/16%** | Właściwość ta definiuje układ dużych portów widoku, takich jak komputery. |

## <a name="add-a-container-module-to-a-page"></a>Dodawanie modułu kontenera do strony

Aby dodać moduł kontenera do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon kontenera**, a następnie wybierz **OK**.
1. W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować. 
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Utwórz nowa stronę**, w obszarze **Nazwa strony** wprowadź **Strona kontenera**, a następnie wybierz **Dalej**.
1. W sekcji **Wybierz szablon** wybierz **Szablon kontenera**, który utworzyłeś, a następnie wybierz **Dalej**.
1. W sekcji **Wybierz układ** wybierz układ strony (na przykład **Układ elastyczny**), a następnie wybierz **Dalej**.
1. W sekcji **Przegląd i zakończenie** przejrzyj konfigurację strony. Jeśli chcesz edytować informacje na stronie, wybierz pozycję **Wstecz**. Jeśli informacje na stronie są poprawne, wybierz pozycję **Utwórz stronę**. 
1. Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W okienku właściwości modułu kontenerów, dla właściwości **Liczba kolumn** określ wartość **1**, a właściwość **szerokość** na **Wypełnij kontener**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Blok treści** i wybierz przycisk **OK**.
1. W okienku właściwości modułu bloku zawartości skonfiguruj nagłówek, obraz i układ.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Powinien być widoczny jeden moduł funkcji, który mieści się w szerokości modułu kontenera.
1. W okienku właściwości modułu kontenerów zmień wartość właściwości **Liczba kolumn** na **3**.
1. Dodaj dwa dodatkowe moduły bloku zawartości do modułu kontenera i skonfiguruj je.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Teraz powinny być widoczne trzy moduły bloku zawartości widoczne obok siebie.
1. Po uzyskaniu żądanego układu wybierz opcję **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz pozycję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł typu accordion](add-accordion.md)

[Moduł tabularny](add-tab.md)

[Moduł karuzeli](add-carousel.md)

[Moduł bloku tekstu](add-content-rich-block.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
