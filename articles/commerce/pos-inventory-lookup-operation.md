---
title: Operacja wyszukiwania zapasów w POS
description: W tym temacie opisano, jak używać operacji wyszukiwania zapasów w punkcie sprzedaży (POS) Dynamics 365 Commerce do przeglądania dostępnych zapasów produktów w sklepach i magazynach.
author: boycezhu
ms.date: 05/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: b697583f2ebf9950ad805d4f415dafb2c891de8052d4a47563b048059475030f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745339"
---
# <a name="inventory-lookup-operation-in-pos"></a>Operacja wyszukiwania zapasów w POS

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak używać operacji wyszukiwania zapasów w punkcie sprzedaży (POS) Dynamics 365 Commerce do przeglądania dostępnych zapasów produktów w sklepach i magazynach.

Dokładny widok zapasów w całej organizacji pomaga pracownikom sklepu zapewnić terminową i efektywną obsługę klienta. Moment, który liczy się najbardziej, to chwila, kiedy klient jest gotowy do podjęcia decyzji zakupowej. Ważne jest, aby kasjerzy w sklepie detalicznym mieli dostęp do informacji o stanie magazynowym w czasie rzeczywistym lub prawie w czasie rzeczywistym, aby mogli dokładnie obiecać dostawę i odbiór produktu.

Operacja wyszukiwania zapasów w programie Commerce POS pomaga sprzedawcom detalicznym realizować transakcje operacyjne i zyskać wgląd w dane poprzez łączenie sklepów z centralą commerce. Ta funkcja udostępnia widok dostępności zapasów produktów we wszystkich sklepach i magazynach. Pomaga również sprzedawcom detalicznym jeszcze bardziej poprawić efektywność i obniżać koszty poprzez usprawnienie planowania zapasów w czasie rzeczywistym.

Gdy operacja wyszukiwania zapasów jest uruchamiana z aplikacji punktu sprzedaży, kasjer punktu sprzedaży używa klawiatury numerycznej do wprowadzenia numeru produktu w celu wysłania zapytania o informacje o zapasach. Jeśli wprowadzony produkt ma warianty, kasjer może opcjonalnie wybrać wymiary lub inne wartości, aby sprawdzić informacje magazynowe określonego wariantu produktu.

## <a name="inventory-lookup-list-view-for-individual-products"></a>Widok listy wyszukiwania zapasów dla poszczególnych produktów

W przypadku pojedynczego produktu operacja wyszukiwania zapasów udostępnia widok listy wyszukiwania zapasów, w którym są wyświetlane następujące informacje o produktach z listy lokalizacji:

- **Zapasy** — odnosi się do „fizycznie dostępnej” ilości produktu.
- **Zarezerwowane** — dotyczy ilości fizycznie zarezerwowanej pobranej z centrali.
- **Zamówiona** — Odnosi się do ilości „zamówionych ogółem” pobranej z centrali.
- **Jednostka** — odnosi się do towaru jednostka miary skonfigurowanego w centrali.

Widok listy lokalizacji zawiera wszystkie sklepy i magazyny skonfigurowane w grupach realizacji, z którym jest połączony bieżący sklep, jak pokazano na poniższym przykładzie.

![Widok listy operacji wyszukiwania zapasów.](media/inventory-lookup-list-view.png)

> [!NOTE]
> Upewnij się, że bieżący sklep jest uwzględniony w skojarzonych grupach realizacji.

Na pasku aplikacji POS są dostępne następujące akcje:

- **Sortuj** — ta akcja umożliwia użytkownikowi punktu końcowego posortowanie danych w widoku listy na podstawie różnych kryteriów. Sortowanie oparte na lokalizacjach jest domyślną opcją sortowania. 
  - **Lokalizacja geograficzna** (od najbliższej do najmniejszej lokalizacji w porównaniu z bieżącym sklepem)
  - **Nazwa** (w kolejności rosnącej lub malejącej)
  - **Numer sklepu** (w kolejności rosnącej lub malejącej)
  - **Zapasy** (w porządku malejącym)
  - **Zarezerwowany** (w porządku malejącym)
  - **Zamówiona** (w porządku malejącym)
- **Filtr** — ta akcja umożliwia użytkownikowi punktu końcowego wyświetlenie przefiltrowanych danych dla określonej lokalizacji.
- **Pokaż dostępność sklepu** — ta akcja umożliwia użytkownikowi punktu sprzedaży wyświetlenie ilości dostępnych do dostępności (ATP) dla produktu w wybranym sklepie.
- **Pokaż lokalizację sklepu** — ta akcja powoduje otwarcie osobnej strony w celu wyświetlenia widoku mapy, adresu i godzin sklepu dla wybranego sklepu.
- **Odbierz w sklepie** - Ta akcja tworzy zamówienie klienta na produkt, który zostanie odebrany z wybranego sklepu i przekierowuje użytkownika do ekranu transakcji.
- **Wyślij produkt** - Ta akcja tworzy zamówienie klienta na produkt, który zostanie wysłany z wybranego sklepu i przekierowuje użytkownika do ekranu transakcji.
- **Wyświetlanie wszystkich wariantów** — w przypadku produktu z wariantami ta akcja przełącza się z widoku listy na widok macierzy, w którym są wyświetlane informacje o zapasach dla wszystkich wariantów produktu.
- **Dodaj do transakcji** — ta akcja powoduje dodanie produktu do koszyka i przekierowywanie użytkownika do ekranu transakcji.

> [!NOTE]
> W przypadku sortowania opartego na lokalizacjach odległość między lokalizacją a bieżącym sklepem jest określana na podstawie współrzędnych (szerokości geograficznej i długości) zdefiniowanych w programie Commerce Headquarters. W przypadku sklepu informacje o lokalizacji są definiowane w podstawowym adresie jednostki operacyjnej skojarzonej ze sklepem. W przypadku magazynu, który nie jest magazynem sklepowym, informacje o lokalizacji są zdefiniowane w adresie magazynu. Jeśli dla bieżącego sklepu nie są zdefiniowane współrzędne, opcja sortowania według lokalizacji spowoduje wyświetlenie bieżącego sklepu na początku listy, a następnie posortowanie innych lokalizacji według nazwy.

> [!NOTE]
> Akcje **Pokaż dostępność sklepu**, **Pokaż lokalizację sklepu**, **Odbiór w sklepie** i **Wyślij produkt** są niedostępne w lokalizacjach poza sklepem.

## <a name="inventory-lookup-matrix-view-for-variants"></a>Widok macierzy wyszukiwania zapasów dla wariantów

W przypadku produktu głównego z wariantami operacja wyszukiwania zapasów udostępnia także widok macierzy oparty na wymiarach, który wyświetla informacje o dostępności zapasów dla wszystkich wariantów produktu głównego w wybranej lokalizacji. Domyślnie widok macierzy pokazuje dane dla bieżącego sklepu. Akcji **Sklep** na pasku aplikacji można użyć w celu wyszukiwania informacji o zapasach w innych sklepach skonfigurowanych w grupach realizacji, z które jest połączony bieżący sklep.

Poniższy przykładowy obraz przedstawia widok macierzy wyszukiwania zapasów w programie POS.

![Widok macierzy operacji wyszukiwania zapasów.](media/inventory-lookup-matrix-view.png)

W widoku macierzy każda komórka reprezentuje indywidualny wariant i wyświetla stan zapasów (dostępna fizyczna) w prawym dolnym rogu, a także wartości **zarezerwowane** (zarezerwowane fizycznie) i **zamówione** (łącznie) w górnym -lewy róg. Poniższa tabela wyjaśnia znaczenie różnych dostępnych wartości.

| Dostępna wartość                            | opis |
|------------------------------------------|-------------|
| Wartość liczbowa większa niż 0 (zero) | Wariant został pomyślnie zwolniony do wybranej lokalizacji i można wykonywać dodatkowe czynności w komórce. |
| **0** (zero)                             | Wariant został pomyślnie zwolniony do wybranej lokalizacji, ale towar nie jest w niej dostępny. Można wykonywać dodatkowe czynności w komórce. |
| **n/d** lub komórka nieaktywna              | Wariant nie został pomyślnie zwolniony do wybranej lokalizacji i nie można wykonywać dodatkowe czynności w komórce. |

Kolejność wyświetlania wartości wymiarów w widoku macierzy jest oparta na konfiguracji kolejności wyświetlania wymiarów w programie Commerce Headquarters. Można zmienić konfigurację kolejności wyświetlania wymiarów, wybierając nowy wymiar do użycia. 

W komórce widoku macierzy dostępne są następujące akcje:

- **Sprzedaj teraz** — Ta akcja dodaje wybrany wariant do koszyka i przekierowuje użytkownika do ekranu transakcji.
- **Odbierz w sklepie** - Ta akcja tworzy zamówienie klienta na wybrany wariant, które zostanie odebrane z wybranego sklepu i przekierowuje użytkownika do ekranu transakcji.
- **Wyślij produkt** -Ta akcja tworzy zamówienie klienta dla wybranego wariantu, które zostanie wysłane z wybranego sklepu i przekierowuje użytkownika do ekranu transakcji.
- **Dostępność** — ta akcja przenosi użytkownika na osobną stronę pokazującą ilości ATP dla wybranego wariantu w wybranym sklepie.
- **Pokaż wszystkie lokalizacje** — ta akcja przełącza do widoku standardowej listy dostępności zapasów, wyświetlając informacje o zapasach dla wybranego wariantu.
- **Wyświetl szczegóły produktu** — ta akcja przekieruje użytkownika do strony szczegółów produktu (PDP) wybranego wariantu.

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a>Uzyskiwanie dostępu do wyszukiwania zapasów z innych stron w aplikacji POS

Użytkownicy punktu dostępu mogą uzyskać dostęp do operacji wyszukiwania zapasów z innych stron w programie POS.

Poniższy przykładowy obraz przedstawia wyniki wyszukiwania zapasów z PDP w punkcie sprzedaży.

![Wyszukiwania zapasów ze strony szczegółów produktu.](media/inventory-lookup-from-product-details-page.png)

W pdp produktu głównego można użyć akcji **Wyświetlanie wszystkich wariantów** na pasku aplikacji w celu uruchomienia widoku macierzy wyszukiwania zapasów, w którym są wyświetlane informacje o dostępności zapasów dla bieżącego sklepu dla wszystkich wariantów produktu. W przypadku pojedynczego produktu pdP wyświetla wartość dostępnych zapasów (fizycznie dostępnych) tego produktu dla bieżącego sklepu. Dodatkowo można zaznaczyć łącze **Inne zapasy sklepów**, aby uruchomić operację wyszukiwania zapasów, aby sprawdzić dostępność zapasów produktu w innych sklepach lub magazynach.

> [!NOTE]
> Akcja **Wyświetl wszystkie warianty** na PDP jest dostępna tylko dla produktów głównych, które mają warianty. Nie jest dostępna dla określonych produktów lub zestawów.

Można skonfigurować operację wyszukiwania zapasów, aby była wyświetlana jako łącze w siatce przycisków na ekranie transakcji POS. Po konfiguracji, gdy użytkownik wybierze wiersz koszyka, a następnie wybierze przycisk **Wyszukiwania zapasów**, zostanie wyświetlony widok listy wyszukiwania zapasów dla wybranego produktu. Aby uzyskać więcej informacji dotyczących konfigurowania siatek przycisków za pomocą narzędzia konstruktora układu ekranu programu POS, zobacz [konfiguracje graficzne interfejsu użytkownika programu POS](pos-screen-layouts.md).

## <a name="inventory-lookup-with-channel-side-calculation"></a>Wyszukiwanie w magazynie z obliczaniem po stronie kanału

W wersji Commerce 10.0.9 i wcześniejszych **dostępne fizycznie** wartość w operacji wyszukiwania zapasów jest pobierana z centrali Commerce za pośrednictwem połączenia serwisowego w czasie rzeczywistym. W wersji Commerce 10.0.10 i nowszych można skonfigurować operację wyszukiwania zapasów POS, aby używać obliczeń po stronie kanału na serwerze Commerce w celu określenia dostępnej wartości fizycznej, co może zapewnić bardziej wiarygodne i dokładniejsze oszacowanie dostępnych zapasów poprzez uwzględnienie danych transakcyjnych, które nie zostały jeszcze zsynchronizowane z centralą. Aby uzyskać więcej informacji o obliczaniu zapasów po stronie kanału i związanej z nim konfiguracji programu POS w centrali, zobacz temat [Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej](calculated-inventory-retail-channels.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfiguracje wizualne interfejsu użytkownika punktu sprzedaży](pos-screen-layouts.md)

[Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej](calculated-inventory-retail-channels.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
