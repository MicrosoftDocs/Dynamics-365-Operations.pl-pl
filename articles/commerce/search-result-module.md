---
title: Moduł wyników wyszukiwania
description: W tym temacie omówiono moduły wyników wyszukiwania i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/15/2021
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
ms.openlocfilehash: dc4a01e520379a74ca3b21c1d588531412e762be
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647519"
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

![Przykład strony wyników wyszukiwania w witrynie Fabrikam.](./media/SimpleCategoryLandingDressCategory.png)

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

## <a name="enable-inventory-awareness-for-the-search-results-module"></a>Włącz świadomość zapasów dla modułu wyników wyszukiwania

Klienci zazwyczaj oczekują, że witryna e-commerce będzie świadoma zapasów podczas przeglądania, tak aby mogli zdecydować, co zrobić, jeśli nie ma zapasów dla danego produktu. Moduł wyników wyszukiwania można rozbudować tak, aby uwzględniał dane dotyczące zapasów i zapewniał następujące wrażenia:

- Pokaż etykietę dostępności zapasów wraz z produktami.
- Ukryj produkty niedostępne w magazynie.
- Pokaż produkty niedostępne w magazynie na końcu listy wyników wyszukiwania.
    
Aby umożliwić korzystanie z tych doświadczeń, należy skonfigurować następujące ustawienia w centrali Commerce.

### <a name="enable-the-enhanced-e-commerce-product-discovery-to-be-inventory-aware-feature"></a>Włącz funkcję rozszerzonego wykrywania produktów w handlu elektronicznym, aby były one świadome zapasów

> [!NOTE]
> Funkcja **Usprawnienie wykrywania produktów w e-Commerce, tak aby były świadome stanów magazynowych** jest dostępna od wersji 10.0.20 Commerce.

Aby włączyć funkcję **Usprawnione wyszukiwanie produktów w handlu elektronicznym, aby było świadome zapasów** w centrali Commerce, wykonaj poniższe kroki.

1. Kliknij kolejno opcje **Obszary robocze \> Zarządzanie funkcjami**.
1. Poszukaj funkcji **Zwiększanie wykrywalności produktów w e-commerce, aby były świadome zapasów**, a następnie włącz ją.

### <a name="configure-the-populate-product-attributes-with-inventory-level-job"></a>Konfiguracja zadania Wypełnij atrybuty produktu poziomem zapasów

Zadanie **Populuj atrybuty produktów poziomem zapasów** tworzy nowy atrybut produktu, aby uchwycić dostępność zapasów, a następnie ustawia ten atrybut na najnowszą wartość poziomu zapasów dla każdego produktu głównego. Ponieważ dostępność zapasów sprzedawanego produktu lub asortymentu ulega ciągłym zmianom, zalecamy zaplanowanie zadania jako procesu wsadowego.

Aby skonfigurować zadanie **Populuj atrybuty produktów z poziomem zapasów** centrali Commerce należy wykonać poniższe kroki.

1. Przejdź do **Retail i Commerce \> Retail i Commerce IT \> Produkty i zapasy**.
1. Wybierz **Wypełnij atrybuty produktu poziomem zapasów**.
1. W oknie dialogowym **Populuj atrybuty produktu z poziomem zapasów** wykonaj następujące czynności:

    1. W zakładce **Parametry** w polu **Nazwa atrybutu produktu i typu** podaj nazwę dedykowanego atrybutu produktu, który będzie tworzony do przechwytywania dostępności stanów magazynowych.
    1. W zakładce **Parametry** w polu **Dostępność zapasów na podstawie** należy wybrać ilość, na podstawie której ma być obliczany poziom zapasów (np. **Dostępność fizyczna**).
    1. W opcji **Uruchom w tle**, skonfiguruj zadanie tak, aby działało w tle i opcjonalnie włącz opcję **Przetwarzanie wsadowe**. 

> [!NOTE]
> Aby zapewnić spójne obliczanie poziomu zapasów na stronach PDP i list produktów w Twoim e-sklepie, pamiętaj, aby wybrać tę samą opcję ilości zarówno dla ustawienia **Dostępność zapasów na podstawie** w centrali Commerce, jak i **Poziom zapasów na podstawie** w module kreator witryn Commerce. Aby uzyskać więcej informacji na temat ustawień inwentarza w programie do budowania witryn, zobacz temat [Zastosuj ustawienia inwentarza](inventory-settings.md).

### <a name="configure-the-new-product-attribute"></a>Skonfiguruj nowy atrybut produktu

Po wykonaniu zadania **Populuj atrybuty produktu poziomem zapasów** należy skonfigurować nowo utworzony atrybut produktu na witrynie e-commerce, na której chcemy włączyć świadomość stanów magazynowych dla modułu wyników wyszukiwania.

Aby skonfigurować nowy atrybut produktu w centrali Commerce, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów** i wybierz witrynę e-commerce.
1. Wybierz i otwórz powiązaną grupę atrybutów, dodaj do niej nowo utworzony atrybut produktu, a następnie zamknij stronę.
1. Wybierz **Ustaw metadane atrybutu**, zaznacz nowo dodany atrybut produktu, a następnie włącz opcje **Pokaż atrybut na kanale**, **Odtwarzanie**, **Możliwość dopracowania** oraz **Możliwość wyszukiwania**.

> [!NOTE]
> W przypadku produktów, które są widoczne w module wyników wyszukiwania, poziom zapasów jest wprowadzany na poziomie produktu głównego, a nie na poziomie poszczególnych wariantów. Dostępne są tylko dwie możliwe wartości: „Dostępne” i „Poza magazynem”. Rzeczywisty tekst wartości jest pobierany z definicji [profilu poziomu inwentaryzacji](inventory-buffers-levels.md). Produkt główny jest uważany za wyczerpany tylko wtedy, gdy wszystkie jego warianty są wyczerpane. Poziom zapasów dla danego wariantu jest określany na podstawie definicji profilu poziomu zapasów produktu. 

Po wykonaniu wszystkich poprzednich kroków konfiguracyjnych, na stronach z wynikami wyszukiwania pojawią się elementy uściślające z filtrem opartym na stanie magazynowym, a moduł wyników wyszukiwania będzie pobierał dane o stanie magazynowym zza kulis. Następnie możesz skonfigurować ustawienia **Ustawienia zapasów dla stron list produktów** w kreatorze witryn Commerce, aby kontrolować sposób w jaki moduł wyników wyszukiwania pokazuje produkty niedostępne w magazynie. Aby uzyskać więcej informacji, zobacz [Zastosuj ustawienia zapasów](inventory-settings.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania](category-search-page-overview.md)

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł szybkiego podglądu](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
