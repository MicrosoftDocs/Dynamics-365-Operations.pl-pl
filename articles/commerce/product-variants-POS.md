---
title: Wyszukiwanie zapasów w punkcie sprzedaży (POS)
description: W tym temacie opisano dostępne opcje przeglądania informacji o zapasach w aplikacji punktu sprzedaży (POS).
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 26bbbeee7ed6c228b3c84dc07576bccb8e1aebd8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231015"
---
# <a name="inventory-lookup-in-the-point-of-sale-pos"></a>Wyszukiwanie zapasów w punkcie sprzedaży (POS)

[!include [banner](includes/banner.md)]

Funkcja wyszukiwania zapasów w punkcie sprzedaży (POS) pozwala sprzedawcom detalicznym osiągnąć doskonałość operacyjną i w czasie rzeczywistym wyciągać wnioski dzięki połączeniu sklepów, aplikacji punktu sprzedaży i systemów zaplecza. Ta funkcja przedstawia dokładny, aktualny stan zapasów produktów w sklepach i centrach dystrybucyjnych. Pomaga również sprzedawcom detalicznym jeszcze bardziej poprawić efektywność i obniżać koszty poprzez usprawnienie planowania zapasów w czasie rzeczywistym.

Dokładny, aktualny obraz zapasów w organizacji pomaga pracownikom sklepów lepiej służyć i pomagać klientom. Moment, który liczy się najbardziej, to chwila, kiedy klient jest gotowy do podjęcia decyzji zakupowej. Ważne jest, aby kasjerzy w sklepie mieli aktualne informacje o zapasach zawsze pod ręką, tak aby rzetelnie deklarować dostawy i odbiory produktów.

Stronę **Wyszukiwanie w magazynie** można otworzyć z obszaru roboczego **Retail Modern POS** lub obszaru roboczego **Retail Cloud POS**.

![Kafelek wyszukiwania zapasów na stronie głównej aplikacji punktu sprzedaży](media/POSHomepage.png)

Na stronie **Wyszukiwanie w magazynie** można za pomocą klawiatury numerycznej wprowadzić numer produktu. Następnie można wyświetlić ilość dostępnych zapasów w wielu sklepach i magazynach.

![Standardowa strona wyszukiwania zapasów](media/InventoryLookUp.png)

Dla każdej lokalizacji są także wyświetlane ilości **Zarezerwowane** i **Zamówione**.

- **Zarezerwowane** — ta ilość odnosi się do wartości **Rezerwacja fizyczna** z systemu zaplecza dla określonego numeru produktu w lokalizacji.
- **Zamówione** — ta ilość odnosi się do wartości **Zamówione w sumie** z systemu zaplecza dla określonego numeru produktu w lokalizacji.

## <a name="locations-that-inventory-availability-information-is-shown-for"></a>Lokalizacje, dla których są wyświetlane informacje o dostępności zapasów

Lista lokalizacji obejmuje dwa typy jednostek:

- **Sklepy** — lista sklepów skonfigurowanych przy użyciu grupy lokalizatora sklepów dla bieżącego sklepu w aplikacji Headquarters.
- **Centra dystrybucji** — w usłudze Commerce można skonfigurować różne rodzaje centrów dystrybucyjnych (np. magazyny). Jednak na liście są wyświetlane informacje o dostępności zapasów tylko dla centrów dystrybucyjnych o domyślnym typie **Standardowy**.

    > [!NOTE]
    > Informacje o dostępności zapasów nie są widoczne dla magazynów o typach **Tranzyt**, **Kwarantanna** i **Towary w marszrucie** używanych w aplikacji POS.

Na stronie **Wyszukiwanie w magazynie** można dla każdego sklepu wyświetlić nie tylko bieżące ilości dostępnych zapasów, ilości zarezerwowane i ilości zamówione, ale również ilości zapasów dostępnych do przyrzeczenia (ATP). Wybierz sklep, o którym chcesz obejrzeć informacje ATP, a następnie wybierz opcję **Pokaż dostępność sklepu**.

![Ilości ATP](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a>Otwieranie widoku Macierz oparta na wymiarach w celu obejrzenia wszystkich wariantów

Na stronie **Szczegóły produktu** dla produktu głównego lub na stornie **Wyszukiwanie w magazynie** wybierz opcję **Wyświetl wszystkie warianty** na pasku aplikacji u dołu strony. Widok **Macierz oparta na wymiarach** uruchamiany początkowo z tych stron zawiera informacje o dostępności zapasów dla wszystkich wariantów produktu w bieżącym sklepie.

> [!NOTE]
> Przycisk **Wyświetl wszystkie warianty** jest dostępny tylko dla produktów głównych towarów mających warianty produktu. Nie jest dostępny dla samodzielnych produktów ani zestawów.

![Przycisk Wyświetl wszystkie warianty na stronie Wyszukiwanie w magazynie](media/StandardToMatrix.png)

Wybierz opcję **Wyświetl wszystkie warianty** na stronie **Szczegóły produktu** dla produktu głównego lub na stronie **Wyszukiwanie w magazynie**, nie wybierając lokalizacji, aby przejść do widoku **Macierz oparta na wymiarach** w celu wyświetlenia informacji o dostępności zapasów dla wszystkich wariantów produktu dla bieżącego sklepu.

![Widok Macierz oparta na wymiarach dla strony Wyszukiwanie w magazynie](media/Matrix.png)

> [!NOTE]
> Na poprzedniej ilustracji kolejność wyświetlania wymiarów jest alfabetyczna, ponieważ nie została skonfigurowana dla wybranego produktu.

W widoku **Macierz oparta na wymiarach** komórki wariantów produktu zawierają wartość dostępności zapasów w prawym dolnym rogu. W tabeli poniżej opisano znaczenie poszczególnych wartości.

| Dostępna wartość                            | opis |
|------------------------------------------|-------------|
| Wartość liczbowa większa niż 0 (zero) | Wariant został pomyślnie zwolniony do wybranej lokalizacji i można wykonywać dodatkowe czynności w komórce. (Te działania są opisane bardziej szczegółowo w dalszej części tego tematu). |
| **0** (zero)                             | Wariant został pomyślnie zwolniony do wybranej lokalizacji, ale towar nie jest w niej dostępny. Jednak można wykonywać dodatkowe czynności w komórce. (Te działania są opisane bardziej szczegółowo w dalszej części tego tematu). |
| **n/d** lub komórka nieaktywna              | Wariant nie został pomyślnie zwolniony do wybranej lokalizacji i nie można wykonywać dodatkowe czynności w komórce. |

Można również zmienić dokument bazowy wymiarów, wybierając nowy wymiar, który ma być używany.

![Zmienianie dokumentu bazowego](media/ChangePivot.png)

![Dokument bazowy zmieniony](media/PivotChanged.png)

> [!NOTE]
> Na poprzedniej ilustracji kolejność wyświetlania wymiarów wybranego produktu jest niestandardowa (niealfabetyczna). Opiera się na kolejności wyświetlania wymiarów ustawionej w systemach zaplecza.

Ponadto w widoku **Macierz oparta na wymiarach** można wykonać więcej działań, które poprawiają wydajność pracownika sklepu. Oto kilka przykładów:

- Zmiana lokalizacji sklepu w celu wyszukiwania dostępnych zapasów wszystkich wariantów produktu w innych lokalizacjach. Te lokalizacje obejmują inne sklepy w grupie lokalizatora sklepów oraz centra dystrybucyjne o domyślnym typie **Standardowy**.
- Sprzedawanie odbiorcy określonego wariantu produktu przy użyciu metody zapłaty przy kasie i wychodzenia z produktami ze sklepu (transportu własnego), odbioru w sklepie lub wysyłki na adres.
- Podanie odbiorcy informacji ATP o określonym wariancie produktu w określonej lokalizacji.

![Dodatkowe działania na kafelkach wariantów](media/VariantActions.png)

> [!NOTE]
> Na poprzedniej ilustracji kolejność wyświetlania wymiarów jest alfabetyczna, ponieważ nie została skonfigurowana dla wybranego produktu.

Poniższa tabela zawiera więcej informacji o dodatkowych działaniach, które są dostępne.

| Akcja               | opis |
|----------------------|-------------|
| Sprzedaj teraz             | Dodawanie wybranego wariantu towaru do transakcji oraz przekierowywanie użytkownika do ekranu transakcji. (Ta akcja jest niedostępna, gdy wybraną lokalizacją jest centrum dystrybucji). |
| Odbiór w sklepie     | Tworzenie zamówienia odbiorcy na wariant produktu, który zostanie odebrany z wybranej lokalizacji, i przekierowywanie użytkownika do ekranu transakcji. (Ta akcja jest niedostępna, gdy wybraną lokalizacją jest centrum dystrybucji). |
| Wyślij produkt         | Tworzenie zamówienia odbiorcy na wariant produktu, który zostanie wysłany z wybranej lokalizacji, i przekierowywanie użytkownika do ekranu transakcji. |
| Dostępność         | Wyświetlanie informacji ATP o wybranej kombinacji wariantów dla wybranej lokalizacji. |
| Pokaż wszystkie lokalizacje   | Przełączanie na standardowy widok wyszukiwania zapasów i wyróżnianie informacji o dostępności zapasów wariantu towaru we wszystkich sklepach w grupie lokalizatora sklepów oraz w centrach dystrybucyjnych o typie **Standardowy/Domyślnie**. |
| Wyświetlanie szczegółów produktu | Przekierowywanie użytkownika do strony **Szczegóły produktu** skojarzonego produktu głównego. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]