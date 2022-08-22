---
title: Moduły porównywania produktów
description: W tym artykule opisano moduły porównywania produktów i sposób ich implementacji, aby klienci mogli porównywać produkty w witrynach e-commerce Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/09/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: ced471dd7e3e4c3e9be938b295edaad626a890a3
ms.sourcegitcommit: 92c4506be7dc14078e3c4f1d182edd895d64ffe0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9247657"
---
# <a name="product-comparison-modules"></a>Moduły porównywania produktów

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

W tym artykule opisano moduły porównywania produktów i sposób ich implementacji, aby klienci mogli porównywać produkty w witrynach e-commerce Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Moduły porównywania produktów i przycisków porównywania produktów są dostępne od wersji Dynamics 365 Commerce 10.0.29. Można ich używać zarówno w witrynach sieci Web B2C, jak i B2B.

Funkcja porównywania produktów pozwala kupującym porównywać szczegóły produktów na stronie porównywania produktów, aby pomóc im w podejmowaniu lepszych decyzji zakupowych. Ta funkcjonalność jest konfigurowana w Konstruktorze witryn w portalu Commerce za pomocą modułu porównywania produktów. Na stronach list produktów (PLP), takich jak wyniki kategorii, wyniki wyszukiwania i strony windykacji produktów, można skonfigurować przycisk porównania produktów, który sprzedawcy mogą dodawać do zasobnika porównawczego. Ta funkcjonalność jest konfigurowana w Konstruktorze witryn za pomocą modułu przycisków porównania produktów, który działa jak w module [szybkiego widoku](quick-view-module.md).

Gdy użytkownicy witryny dodają produkty do porównania, wybierając je w kafelkach produktów, u dołu strony pojawi się zasobnik porównania. Na pasku porównawczym są obecnie porównywane produkty, które są porównywane przez sprzedawcę, oraz krótkie podglądy tych produktów. Użytkownicy witryny mogą również dodawać produkty ze stron szczegółów produktu (PDP) i mogą dodawać określone warianty produktów w celu porównania z wzorcami produktów.

Gdy odbiorcy dodają kilka produktów do zasobnika porównania, mogą wybrać opcję **Porównaj**, aby przekierować ją do strony porównania produktów. Strona porównania produktów pokazuje szczegóły produktu dla każdego wybranego produktu, dzięki czemu klienci mogą porównywać zdjęcia, ceny, wymiary produktu (rozmiar, styl i kolor), informacje o zbiorczych ocenach i inne atrybuty produktów.

Na poniższej ilustracji przedstawiono przykłady przycisku porównania produktów, przycisku usuwania z porównania, zasobnika porównania i strony porównania produktów.

![Przegląd porównania produktów przedstawiający przycisk porównania produktów, przycisk usuwania z porównania, panel tacy porównawczej oraz stronę porównania produktów.](./media/Product-Comparison-Overview.png)

> [!NOTE]
> - Strona porównania produktów porównuje domyślny zestaw właściwości produktu i wszystkie atrybuty, które można wyświetlić na PDP dla danego produktu.
> - Na stronie porównania produktów nie można wyświetlać właściwości, takich jak sposób dostawy, dostępny zapas czy jednostka miary dostawy.
> - Klienci mogą dodawać do porównywarki produkty z różnych kategorii, pod warunkiem, że produkty pochodzą z tego samego katalogu.
> - Funkcja porównania produktów jest obecnie ograniczona do porównywania produktów z pojedynczego katalogu. Użytkownicy witryny nie mogą dorównać między katalogami.
> - Upewnij się, że właściwość **Renderuj stronę klienta modułu** jest wyczyszczona dla wszystkich modułów porównywania produktów.
> - Należy się upewnić, że buforowanie na poziomie strony jest wyłączone dla wszystkich stron, na których jest używany moduł porównywania produktów. Strony te zawierają pdPs, PLPs i strony porównania produktów. Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie buforowania strony](e-commerce-extensibility/page-caching.md).

Poniższa ilustracja przedstawia przykład strony porównania produktów.

![Strona porównania produktów.](./media/Product-Comparison-Page.png)

## <a name="add-the-product-comparison-module-to-a-new-product-comparison-page"></a>Dodawanie modułu porównania produktów do nowej strony porównania produktów

Można utworzyć dedykowaną stronę porównania produktów, dodając moduł porównania produktów do treści strony. Oprócz umożliwienia klientom porównywania szczegółów różnych produktów, można skonfigurować moduł porównywania produktów, aby odbiorcy mieli możliwość szybkiego ukończenia zakupów po porównaniu ich produktów. Moduł porównania produktów zawiera również boks **Puste porównanie**, w którym możesz dodać moduł bloku treści opisujący stan pusty (na przykład „Twoje porównanie produktów jest puste”).

Aby dodać moduł porównywania produktów do nowej strony porównywania produktów, wykonaj następujące kroki.

1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Utwórz nowa stronę**, w obszarze **Nazwa strony** wprowadź odpowiednią nazwę strony (na przykład **Porównanie produktów**), a następnie wybierz **Dalej**.
1. W sekcji **Wybierz szablon** wybierz odpowiedni szablon (na przykład szablon używany na domyślnej stronie kategorii), a następnie wybierz **Dalej**.
1. W sekcji **Wybierz układ** wybierz układ strony (na przykład **Układ elastyczny**), a następnie wybierz **Dalej**.
1. W sekcji **Przegląd i zakończenie** przejrzyj konfigurację strony. Jeśli chcesz edytować informacje na stronie, wybierz pozycję **Wstecz**. Jeśli informacje na stronie są poprawne, wybierz pozycję **Utwórz stronę**.
1. W gnieździe **Główny** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Porównanie produktów** i wybierz przycisk **OK**.
1. W gnieździe **Przycisk szybkiego podglądu** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduł** wybierz moduł **Szybki podgląd produktu** i wybierz przycisk **OK**.
1. W okienku właściwości po prawej stronie skonfiguruj właściwości modułu **Szybki podgląd produktu**.
1. Na nowej stronie wybierz gniazdo **Puste porównanie**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Blok treści** i wybierz przycisk **OK**.
1. W okienku właściwości po prawej stronie skonfiguruj właściwości modułu **Blok treści**. 
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Na poniższej ilustracji przedstawiono przykład pustej strony porównania w narzędziu do tworzenia witryn.

![Moduł porównywania produktów.](./media/Product-comparison-module.png)

## <a name="add-a-product-comparison-button-to-product-tiles-on-search-and-category-results-pages"></a>Dodawanie przycisku porównania produktów do kafelków produktu na stronach wyników wyszukiwania i kategorii

Przycisk porównania produktów umożliwia użytkownikom szybkie dodawanie produktu do zasobnika porównywania podczas przeglądania produktów na stronie listy. Mogą dodać jeden lub więcej produktów do zasobnika porównania ze strony listy bez konieczności przejdź do PDP.

Przycisk porównania produktów jest obsługiwany przez moduły kolekcji produktów, wyników wyszukiwania i okienek zakupu PDP.

Aby dodać przycisk porównywania produktów do kafelków produktów na stronach wyników wyszukiwania i kategorii, wykonaj następujące kroki.

1. W Konstruktorze witryn przejdź do opcji **Strony** i otwórz stronę kategorii, do której chcesz dodać przycisk porównania produktów.
1. W gnieździe **Główny** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Wyniki wyszukiwania** i wybierz przycisk **OK**.
1. Na domyślnej stronie wybierz gniazdo **Przycisk porównywania produktów** modułu **Wyniki wyszukiwania**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Przycisk porównywania produktów** i wybierz przycisk **OK**.
1. W okienku właściwości po prawej stronie skonfiguruj właściwości modułu **Przycisk porównywania produktów**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="specify-the-maximum-number-of-products-to-show-in-the-comparison-tray"></a>Określ maksymalną liczbę produktów do pokazania w pasku porównawczym

Można określić maksymalną liczbę produktów do pokazania w pasku porównawczym, przechodząc do **ustawień witryny \> Rozszerzenia** w Konstruktorze witryn. Można skonfigurować osobne limity maksymalnej liczby widoków na komputerze i urządzeniach przenośnych/tabletach. Domyślnie żaden limit nie będzie wymuszany, jeśli nie zdefiniowano limitu maksymalnego.

> [!NOTE]
> Aby zapewnić optymalne przeglądanie, zaleca się ustawienie maksymalnej liczby produktów w pasku porównawczym na **2** dla mobilnego portu wyświetlania oraz na **4** w widoku pulpitu, aby zmniejszyć ilość wymaganego przewijania poziomego.

Aby określić maksymalną liczbę produktów w zestawie porównawczym, wykonaj następujące kroki.

1. W konstruktorze witryn przejdź do **Ustawień witryny \> Rozszerzenia**.
1. Dla właściwości **Produkty w porównaniu — urządzenia pulpitu** wprowadź maksymalną liczbę produktów, które powinny być wyświetlane w pasku porównawczym dla widoków pulpitu.
1. Dla właściwości **Produkty z limitu porównawczego – urządzenia mobilne i tablety** wprowadź maksymalną liczbę produktów, które powinny być wyświetlane w zasobniku porównawczym dla okien ekranu dla telefonów komórkowych i tabletów.
1. Na pasku poleceń wybierz opcję **Zapisz i opublikuj**.

![Ustawienia witryny do ograniczenia produktów w pasku porównawczym.](./media/Site-settings-to-limit-products-in-comparison-tray.png)
