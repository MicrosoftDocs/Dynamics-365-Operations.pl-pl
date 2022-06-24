---
title: Grupy jakości pozycji
description: W tym artykule opisano sposób używania i tworzenia grup kontroli jakości towarów w celu logicznego grupowania produktów w celu przypisania ich do skojarzeń jakości w celu automatycznego generowania zleceń kontroli jakości.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf1ce49fa58fd1a8a5aa07636e0b2bd7e2fc10e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875373"
---
# <a name="item-quality-groups"></a>Grupy jakości pozycji

[!include [banner](../includes/banner.md)]

Grupa jakości reprezentuje wspólne wymagania dotyczące testowania towarów. W tym artykule opisano sposób używania i tworzenia grup kontroli jakości towarów w celu logicznego grupowania produktów w celu przypisania ich do skojarzeń jakości w celu automatycznego generowania zleceń kontroli jakości.

W celu konfigurowanie, edytowania i wyświetlania towarów przypisanych do grupy kontroli jakości lub grup kontroli jakości przypisanych do towaru, należy przejść do **Zarządzanie zapasami \> Ustawienia \> Grupy kontroli jakości**. Po zdefiniowaniu wymogów testu na stronie **Grupy testowe** można zdefiniować reguły automatycznego generowania zleceń kontroli jakości. Aby uprościć proces, nie definiuje się reguł dla poszczególnych towarów. Zamiast tego można zdefiniować się reguły dla grupy kontroli jakości na stronie **Skojarzenia jakości**.

## <a name="example-of-an-item-quality-group"></a>Przykład grupy kontroli jakości towarów

Firma produkcyjna nabywa kilka surowców mających te same wymagania dotyczące testowania przed zbliżającą się inspekcją. Dlatego firma definiuje grupę kontroli jakości, a następnie przypisuje do tej grupy kody towarów, które są skojarzone z surowcami. Później firma nabywa nowy typ surowca, który ma te same wymagania dotyczące testowania. Zamiast konfigurować nowe wymagania dotyczące nowego materiału, firma dodaje kod towaru dla nowego materiału do istniejącej grupy jakości.

Ta sama firma produkuje również towary mające te same wymagania dotyczące testowania produkcji i wysyła towary mające te same wymagania dotyczące przeprowadzania testów przed wysyłką. Dlatego firma definiuje dwie dodatkowe grupy kontroli jakości i przypisuje do każdej z nich odpowiednie kody towarów.

## <a name="create-a-quality-group"></a>Tworzenie grupy kontroli jakości

Aby utworzyć grupę kontroli jakości, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy kontroli jakości**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Grupa kontroli jakości** – wpisz unikatowy identyfikator lub nazwę grupy kontroli jakości.
    - **Opis** – wprowadź szczegółowy opis grupy kontroli jakości.

1. Zamknij stronę.

## <a name="manually-add-items-to-a-quality-group"></a>Ręczne dodawanie towarów do grupy kontroli jakości

Aby ręcznie dodać towary do grupy kontroli jakości, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy kontroli jakości**.
1. Wybierz grupę kontroli jakości, do której chcesz dodać towary.
1. W okienku akcji kliknij pozycję **Towary**.
1. Na stronie **Towary w grupie kontroli jakości** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki. Następnie dla nowego wiersza ustaw w polu **Numer towaru** numer towaru, który chcesz dodać.
1. Powtórz poprzedni krok dla każdego dodatkowego towaru, który musi zostać dodany.
1. Zamknij strony.

## <a name="add-multiple-items-to-a-quality-group"></a>Dodawanie wielu towarów do grupy kontroli jakości

Aby dodać wiele towarów do grupy kontroli jakości, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy kontroli jakości**.
1. Utwórz lub wybierz grupę kontroli jakości, do której chcesz dodać towary.
1. W okienku akcji kliknij pozycję **Dodaj towary**.
1. W oknie dialogowym **Zapytanie** wprowadź kryteria filtrowania towarów, które chcesz dodać. Można na przykład filtrować wszystkie towary w określonej grupie towarów.
1. Kliknij przycisk **OK**.
1. W oknie dialogowym **Dodawanie towarów** w siatce są wyświetlane wszystkie towary spełniające kryteria zapytania. Przejrzyj wyniki.

    Jeśli są wymagane jakiekolwiek zmiany, wybierz opcję **Wybierz**, aby powrócić do okna dialogowego **Zapytanie** i skorygować zapytanie.

1. Jeśli wyniki obejmują wszystkie towary, które chcesz dodać, wybierz przycisk **OK**.
1. Zamknij stronę.

## <a name="manually-associate-an-item-with-a-quality-group"></a>Ręczne skojarzenie towaru z grupą kontroli jakości

Aby ręcznie skojarzyć towar z grupą kontroli jakości, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy kontroli jakości towaru**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Numer artykułu** — wybierz numer artykułu, aby go dodać.
    - **Grupa kontroli jakości** — umożliwia wybór grupy kontroli jakości, która ma zostać przypisana do towaru.

1. Powtórz poprzedni krok dla każdej dodatkowej kombinacji towaru i grupy kontroli jakości, która musi zostać dodana.
1. Zamknij strony.

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a>Ręczne dodawanie grupy kontroli jakości ze strony Zwolnione produkty

Aby ręcznie dodać grupę kontroli jakości ze strony **Zwolnione produkty**, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz produkt, do którego chcesz przypisać grupę kontroli jakości.
1. W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Jakość** wybierz **Grupy kontroli jakości towaru**.
1. Na stronie **Towary w grupie kontroli jakości** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki. Następnie w przypadku nowego wiersza w polu **Grupa kontroli jakości** ustaw grupę kontroli jakości, którą chcesz przypisać do produktu.
1. Powtórz poprzedni krok z każdą dodatkową grupą kontroli jakości, którą chcesz przypisać do produktu.
1. Zamknij strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Przyrządy testowe zarządzania jakością](quality-test-instruments.md)
- [Testy zarządzania jakością](quality-tests.md)
- [Grupy testowe zarządzania jakością](quality-test-groups.md)
- [Zmienne testu zarządzania jakością](quality-test-variables.md)
- [Powiązania jakości](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
