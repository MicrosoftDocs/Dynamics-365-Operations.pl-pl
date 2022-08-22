---
title: Moduł wyników wyszukiwania
description: W tym artykule omówiono moduły wyników wyszukiwania i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: d10e9ed78dfc90833ff3c09021f863f6ef0b80d9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286818"
---
# <a name="search-results-module"></a>Moduł wyników wyszukiwania

[!include [banner](includes/banner.md)]

W tym artykule omówiono moduły wyników wyszukiwania i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.

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

Aby dodać moduł wyników wyszukiwania do strony kategorii w module budowania witryny, wykonaj poniższe kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Wyniki wyszukiwania** wprowadź nazwę, a następnie wybierz **OK**.
1. W gnieździe **Treść** wybierz wielokropek (...), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.
1. W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (...), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (...), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Łącze do stron nadrzędnych** i wybierz przycisk **OK**.
1. W okienku właściwości **szlaków nawigacyjnych** wprowadź wartość **1** dla wartości **Minimalne wystąpienia**.
1. W gnieździe **Kontener** wybierz wielokropek (...), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Wyniki wyszukiwania** i wybierz przycisk **OK**.
1. W okienku właściwości **Wyników wyszukiwania** wprowadź wartość **1** dla **Wartości Minimalne** występują, a następnie ustaw inne wymagane właściwości modułu wyników wyszukiwania. Ustawiając te właściwości w szablonie, zapewniasz, że wszelkie dostosowania do konkretnej strony kategorii będą automatycznie uwzględniać te ustawienia.
1. Wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować szablon.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Utwórz nowa stronę**, w obszarze **Nazwa strony** wprowadź **Strona kategorii**, a następnie wybierz **Dalej**.
1. W sekcji **Wybierz szablon** wybierz szablon **Wyniki wyszukiwania**, który utworzyłeś, a następnie wybierz **Dalej**.
1. W sekcji **Wybierz układ** wybierz układ strony (na przykład **Układ elastyczny**), a następnie wybierz **Dalej**.
1. W sekcji **Przegląd i zakończenie** przejrzyj konfigurację strony. Jeśli chcesz edytować informacje na stronie, wybierz pozycję **Wstecz**. Jeśli informacje na stronie są poprawne, wybierz pozycję **Utwórz stronę**.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="enable-inventory-awareness-for-the-search-results-module"></a>Włącz świadomość zapasów dla modułu wyników wyszukiwania

Klienci zazwyczaj oczekują, że witryna e-commerce będzie świadoma zapasów podczas przeglądania, tak aby mogli zdecydować, co zrobić, jeśli nie ma zapasów dla danego produktu. Moduł wyników wyszukiwania można skonfigurować tak, by uwzględniał dane dotyczące zapasów i zapewniał następujące doświadczenia:

- Pokaż etykietę dostępności zapasów razem z produktem.
- Ukryj produkty, których nie ma w magazynie, z listy produktów.
- Pokaż produkty, których nie ma w magazynie, na końcu listy produktów.
- Filtruj produkty w wynikach wyszukiwania według poziomu zapasów.

Aby włączyć te doświadczenia, musisz najpierw włączyć cechę **Zwiększone wykrywanie produktów w handlu elektronicznym, aby były one świadome zapasów** w przestrzeni roboczej **Zarządzanie cechami**.

> [!NOTE]
> Funkcja **Usprawnienie wykrywania produktów w e-Commerce, tak aby były świadome stanów magazynowych** jest dostępna od wersji 10.0.20 Commerce i nowszych.

Wyszukiwanie produktów uwzględniające zapasy wykorzystuje atrybuty produktów do uzyskania informacji o dostępności zapasów. Warunkiem działania tej funkcji jest utworzenie dedykowanych atrybutów produktów, wprowadzenie dla nich danych magazynowych oraz dodanie ich do kanału online. 

Aby utworzyć dedykowane atrybuty produktów, które będą obsługiwać moduł wyników wyszukiwania uwzględniający zapasy, wykonaj poniższe kroki.

1. W Commerce przejdź do **Handel detaliczny i inny \> IT: Handel detaliczny i inny \> Harmonogram integracji**.
1. Wybierz i otwórz **Wypełnij atrybuty produktu poziomem zapasów**.
1. W oknie dialogowym wprowadź następujące informacje:

    1. W polu **Nazwa atrybutu produktu i typu** podaj nazwę dedykowanego atrybutu produktu, który będzie tworzony do przechwytywania dostępności stanów magazynowych.
    1. W polu **Dostępność zapasów na podstawie** należy wybrać typ ilości, na podstawie której ma być obliczany poziom zapasów (np. **Dostępność fizyczna**). 

1. Uruchom zadanie w tle. Ponieważ w środowisku wielokanałowym zapasy produktów ciągle się zmieniają, zdecydowanie zalecamy zaplanowanie tego zadania jako procesu wsadowego.

> [!NOTE]
> Aby zapewnić spójne obliczanie poziomu zapasów na wszystkich stronach i modułach witryny e-commerce, pamiętaj, aby wybrać ten sam typ ilości zarówno dla ustawienia **Dostępność zapasów na podstawie** w centrali Commerce, jak i **Poziom zapasów na podstawie** w module kreator witryn Commerce. Aby uzyskać więcej informacji na temat ustawień inwentarza w programie do budowania witryn, zobacz temat [Zastosuj ustawienia inwentarza](inventory-settings.md).

Aby skonfigurować atrybuty produktu dla kanału internetowego, wykonaj poniższe kroki. 

1. W centrali wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.
1. Wybierz kanał internetowy, dla którego chcesz włączyć moduł wyników wyszukiwania uwzględniający stan inwentarza.
1. Wybierz i otwórz powiązaną grupę atrybutów, a następnie dodaj do niej nowo utworzony atrybut produktu.
1. W przypadku wersji Commerce sprzed wydania 10.0.27 wybierz **Ustaw metadane atrybutu**, zaznacz nowo dodany atrybut produktu, a następnie włącz opcje **Pokaż atrybut na kanale**, **Odtwarzanie**, **Możliwość dopracowania** oraz **Możliwość wyszukiwania**.
1. Przejdź do **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji** i uruchom zadanie **1150 (Katalog)**. Jeśli zaplanujesz zadanie **Uzupełnij atrybuty produktu o poziom zapasów** jako proces wsadowy, zalecamy, abyś również zaplanował zadanie 1150 jako proces wsadowy, który będzie wykonywany z tą samą częstotliwością.

> [!NOTE]
> W przypadku produktów, które są widoczne w module wyników wyszukiwania, poziom zapasów jest widoczny na poziomie produktu głównego, a nie na poziomie poszczególnych wariantów. Dostępne są tylko dwie możliwe wartości: „Dostępne” i „Poza magazynem”. Rzeczywista etykieta dla wartości jest pobierana z [profilu poziomu inwentaryzacji](inventory-buffers-levels.md). Produkt główny jest uważany za wyczerpany tylko wtedy, gdy wszystkie jego warianty są wyczerpane.

Po wykonaniu wszystkich poprzednich kroków konfiguracyjnych, na stronach z wynikami wyszukiwania pojawią się elementy uściślające z filtrem opartym na stanie magazynowym, a moduł wyników wyszukiwania będzie pobierał dane o stanie magazynowym zza kulis. Następnie możesz skonfigurować ustawienia **Ustawienia zapasów dla stron list produktów** w kreatorze witryn Commerce, aby kontrolować sposób w jaki moduł wyników wyszukiwania pokazuje produkty niedostępne w magazynie. Aby uzyskać więcej informacji, zobacz [Zastosuj ustawienia zapasów](inventory-settings.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania](category-search-page-overview.md)

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł szybkiego podglądu](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
