---
title: Konfigurowanie filtrów produktów dla transakcji magazynowych
description: W tym artykule opisano, jak skonfigurować filtry produktów i filtrować kody w celu skategoryzowania pozycji zapasów w magazynie. Filtry służą również do określania, którzy odbiorcy mogą zamówić określone towary, i określania towarów, które można zakupić od określonego dostawcy.
author: Mirzaab
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSFilters,WHSFilterGroupTable,EcoResProductDetailsExtended,WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: f3d6cd373699d374c019f0db7befaffc169f4f6c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850446"
---
# <a name="configure-product-filters-for-warehouse-transactions"></a>Konfigurowanie filtrów produktów dla transakcji magazynowych

[!include [banner](../includes/banner.md)]

W tym artykule opisano, jak skonfigurować filtry produktów i filtrować kody w celu skategoryzowania pozycji zapasów w magazynie. Filtry służą również do określania, którzy odbiorcy mogą zamówić określone towary, i określania towarów, które można zakupić od określonego dostawcy.

Ponadto można skonfigurować i korzystać z filtrów produktów do automatycznego organizowania zapasów w magazynie i łączyć przefiltrowane elementy w grupy filtrów. Filtry służą do dzielenia towarów na kategorie w celu obsługi procesów zarządzania, zakupów i sprzedaży. Jeśli sposób obsługi towarów jest oparty na ograniczeniach dotyczących wagi lub obsługi, może być konieczne grupowanie towarów lub oddzielanie ich od siebie. Można również określić odbiorców lub dostawców, od których towar może być kupowany lub którym może być sprzedawany.

## <a name="prerequisites"></a>Wymagania wstępne

W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.

| Wymaganie wstępne | Instrukcje |
|---|---|
| Przed rozpoczęciem konfigurowania produktów na stronie **Szczegóły zwolnionego produktu** należy włączyć przetwarzanie magazynu dla grupy wymiarów magazynowania produktu. | Przejdź do obszaru **Zarządzanie informacjami o produktach \> Ustawienia \> Grupy wymiarów i wariantów \> Grupy wymiarów magazynowych**, a następnie wybierz lub utwórz grupę wymiarów magazynowych, w której opcja **Użyj procesów zarządzania magazynami** została ustawiona na *Tak*. |
| Aby używać filtrów klientów i/lub filtrów dostawców, należy włączyć ich stosowanie w parametrach zarządzania magazynem. | Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**. Na karcie **Filtry produktów** ustaw opcję **Włącz filtry klienta** i/lub **Włącz filtry dostawcy** na wartość *Tak*. |

## <a name="set-up-product-filters"></a>Ustawianie filtrów produktu

Filtry produktów zawierają maksymalnie 10 właściwości **tytułu filtru**, które są wartościami wyliczenia. Te wartości wyliczenia są dostępne do wyboru podczas tworzenia filtru produktu. Wartości wyliczenia dotyczące *kodu 1* do *kodu 10* są definiowane przez system i reprezentują określoną charakterystykę lub atrybut towaru. *Kod 1* może na przykład reprezentować towary, które mają klasyfikację materiałów niebezpiecznych. *Kod 2* może reprezentować pozycje, które mogą nabywać tylko dostawcy. Filtry produktów określają następnie określoną wartość **kodu filtru** skojarzoną z wartością **Tytuł filtru**.

1. Przejdź do obszaru **Zarządzanie magazynem \> Ustawienia \> Filtry produktów \> Filtry produktów**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy filtr produktów do siatki.
1. W polu **Tytuł filtru** wybierz wartość.
1. W polu **Kod filtru** wprowadź wartość.

    ![Konfigurowanie filtru produktów.](media/Product_Filters10.png "Konfigurowanie filtru produktów")

1. W polu **Opis** wprowadź nazwę kodu. Na przykład *kod 2* może reprezentować dostawców. Następnie można utworzyć filtr produktów dla określonego dostawcy lub grupy dostawców. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie kodów filtrów dostawców](#vendor-product-filters) w dalszej części tego artykułu.

    ![Zestaw filtrów produktu.](media/Product_Filters.png "Zestaw filtrów produktu")

## <a name="set-up-product-filter-groups"></a>Konfigurowanie grup filtrów produktów

Można użyć grupy filtrów do grupowania kodów filtrów. Ta możliwość jest przydatna w przypadku, gdy ta grupa jest używana w zapytaniu w dyrektywie lokalizacji i użytkownik chce przeprowadzić wyszukiwanie dla grupy zamiast serii kodów. Każda grupa filtrów jest skojarzona z grupą towarów.

> [!IMPORTANT]
> Nie wszystkie grupy filtrów produktów są dostępne dla kodów filtrów wyższych niż *kod 4* (czyli od *kodu 5* do *kodu 10*). Na przykład dla zwolnionych produktów, chociaż zostaną dodane wszystkie kody filtru produktów, grupowanie kodów filtrów nie zostanie zaktualizowane. To działanie może zostać zaktualizowane w kolejnych wersjach.

Aby skonfigurować grupy filtrów, należy wykonać następujące czynności.

1. Przejdź do obszaru **Zarządzanie magazynem \> Ustawienia \> Filtry produktów \> Grupy filtrów produktów**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polach **Grupa 1** i **Grupa 2** wprowadź nazwy, które będą używane do klasyfikowania towarów.
1. Na skróconej karcie **Szczegóły** wybierz **Nowe**, aby dodać wiersz.
1. W polach **Data/godzina rozpoczęcia** i **Data/godzina zakończenia** wprowadź daty rozpoczęcia i zakończenia dla grupy filtrów.
1. W polu **Grupa pozycji** wybierz grupę pozycji, do których ma być stosowany filtr produktów.
1. W razie potrzeby w polach **Kod 1** do **Kod 10** wybierz kody filtrów, które mają być uwzględniane w grupie.

    ![Grupa pozycji.](media/ProdFilterGroup.png "Grupa pozycji")

> [!NOTE]
> Jeśli po zamknięciu strony zostanie wyświetlony komunikat o błędzie, ustawienie kodu może zostać utracone. Na stronie **Grupy pozycji** można ustawić kody jako obowiązkowe dla grupy pozycji, zaznaczając pola wyboru **Przypisz kod filtru 1 dla grupy pozycji** , **Przypisz kod filtru 2 dla grupy pozycji** itd.

## <a name="set-up-filter-codes-on-item-groups"></a>Konfigurowanie kodów filtrów dla grup pozycji

Konfigurując kody filtrów dla grup pozycji, można wprowadzać kody produktów, które są wymagane dla dołączonych do tej grupy pozycji.

Aby skonfigurować kody filtrów dla grup towarów, należy wykonać następujące czynności.

1. Kliknij kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zapasy \> Grupy inwentaryzacji**.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć grupę pozycji.
1. W polu **Grupa pozycji** wprowadź nazwę.
1. W polu **Nazwa** wprowadź opis.
1. Na skróconej karcie **Magazyn** w sekcji **Wymagany filtr** zaznacz odpowiednie pola wyboru, aby zdefiniować jeden lub więcej kodów filtru, które powinny zostać określone dla produktów, które są skojarzone z grupą pozycji.

    Aby zaktualizować zwolniony produkt, otwórz stronę **szczegółów zwolnionego produktu**, a następnie w okienku akcji wybierz pozycję **Edytuj**. Filtry skojarzone z kodami zostaną wówczas udostępnione na skróconej karcie **Magazyn**.

    ![Grupy pozycji.](media/ItemGroup10.png "Grupy pozycji")

1. W sekcji **Filtr grupy pozycji** zaznacz pola wyboru dla filtrów, które muszą być takie, aby grupa filtru stanowiła domyślną grupę filtrów dla pozycji.

    Na przykład w przypadku zaznaczenia pól wyboru **Użyj kodu filtru 1** i **Użyj kodu filtru 2**, kody filtru 1 i 2 pozycji muszą odpowiadać konfiguracji grupy filtru dla grupy pozycji, aby można było wybrać grupę filtrów. Po utworzeniu nowego towaru wybrana grupa filtrów będzie domyślną grupą filtrów w polach **Grupa 1** i **Grupa 2** na skróconej karcie **Magazyn** na stronie **Szczegóły zwolnionego produktu**.

> [!IMPORTANT]
> Kody filtrów produktów są włączone tylko dla pozycji, które korzystają z zaawansowanego zarządzania magazynem.

## <a name="specify-filter-codes-for-released-products"></a>Określanie kodów filtrów dla zwolnionych produktów

Aby określić kody filtrów dla zwolnionych produktów, wykonaj następujące kroki. Kodów filtrów można na przykład używać do grupowania produktów niebezpiecznych kupowanych przez określonych dostawców.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć nowy produkt.
1. W oknie dialogowym **Nowy zwolniony produkt** wprowadź dane wymagane do utworzenia podstawy nowego produktu, a następnie wybierz przycisk **OK**.

    Kody filtrów produktów nie są włączone, chyba że grupa pozycji dołączona do produktu została skonfigurowana dla kodów filtrów.

    Aby uzyskać więcej informacji, zobacz temat [Tworzenie nowego produktu](../pim/tasks/create-new-product.md).

1. Na skróconej karcie **Magazyn** w sekcji **Kody filtrów produktów** wybierz kody filtrów dla pól od **Kod 1** do **Kod 10**, aby określić kody filtrów dla produktu.

## <a name="set-up-generally-available-items"></a>Konfiguracja towarów ogólnie dostępnych

Można udostępnić towary z magazynu tylko odbiorcom, tylko dostawcom, lub zarówno odbiorcom, jak i dostawcom.

> [!NOTE]
> Filtry odbiorców i dostawców nie mają zastosowania do każdej pozycji skonfigurowanej jako ogólnie dostępna.

Aby skonfigurować pozycje ogólnie dostępne, należy wykonać następujące czynności.

1. Przejdź do obszaru **Zarządzanie magazynem \> Ustawienia \> Filtry produktów \> Produkty ogólnie dostępne**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć nowy rekord.
1. W polu **Klient lub dostawca** wybierz opcję *Klient*, *Dostawca* lub *Wszystko*, aby udostępnić pozycje dla klientów, dostawców lub dla obu tych kategorii.
1. W polu **Data/godzina rozpoczęcia** wprowadź datę i czas, kiedy pozycja będzie dostępna.
1. W polu **Grupa pozycji** wybierz grupę pozycji.
1. W polach od **Kod 1** do **Kod 10** wybierz kody filtrowania w celu ograniczenia pozycji, które są powszechnie dostępne.

    Po wybraniu grupy pozycji ustaw tę grupę pozycji, które mają być ogólnie dostępne. Przez wybranie kodów filtrowania w tych polach można ograniczyć dostępność pozycji.

## <a name="set-up-customer-product-filters"></a>Ustawianie filtrów produktu klienta

Tej procedury opcjonalnej możesz użyć do określenia pozycji, które mają być dostępne dla wybranego klienta, oraz pozycji, które są dostępne za pośrednictwem ustawień filtra w formularzu **Pozycje ogólnie dostępne**. Można skonfigurować wiele filtrów dla jednego klienta.

Aby skonfigurować kody filtrów klientów, należy wykonać następujące czynności.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odbiorcy \> Wszyscy odbiorcy**.
1. Wybierz klienta.
1. W okienku akcji na karcie **Klient** w grupie **Konfiguracja** wybierz pozycję **Filtry produktów**.
1. Na stronie **Kody filtrów produktów** w okienku akcji wybierz **Nowa**.
1. W polach **Data/godzina rozpoczęcia** i **Data/godzina zakończenia** wprowadź daty rozpoczęcia i zakończenia dla wybranej grupy pozycji.
1. W polu **Grupa pozycji** wybierz grupę pozycji.
1. W polach od **Kod 1** do **Kod 10** wybierz kody filtrów, które mają być stosowane jako kryteria ograniczania pozycji dostępnych dla klientów w wybranej grupie towarów. Należy dokonać wyboru dla każdego kodu filtru ustawionego dla grupy pozycji.

## <a name="set-up-vendor-product-filters"></a><a name="vendor-product-filters"></a>Ustawianie filtrów produktu dostawcy

Tej procedury opcjonalnej możesz użyć do określenia pozycji, które mają być dostępne dla wybranego dostawcy, oraz pozycji, które są dostępne za pośrednictwem ustawień filtra w formularzu **Pozycje ogólnie dostępne**. Można skonfigurować wiele filtrów dla jednego dostawcy.

Aby skonfigurować kody filtrów dostawcy, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Dostawcy \> Wszyscy dostawcy**.
1. Wybierz dostawcę.
1. W okienku akcji na karcie **Dostawca** w grupie **Konfiguracja** wybierz pozycję **Filtry produktów**.
1. Na stronie **Kody filtrów** w okienku akcji wybierz **Nowy**.
1. W polach **Data/godzina rozpoczęcia** i **Data/godzina zakończenia** wprowadź daty rozpoczęcia i zakończenia dla wybranej grupy pozycji.
1. W polu **Grupa pozycji** wybierz grupę pozycji.
1. W polach od **Kod 1** do **Kod 10** wybierz kody filtrów, które mają być stosowane jako kryteria ograniczania pozycji dostępnych dla dostawców w wybranej grupie towarów. Należy dokonać wyboru dla każdego kodu filtru ustawionego dla grupy pozycji.

> [!NOTE]
> Ustawienia filtrów produktów dostawcy dotyczą zwolnionych produktów, dla których są włączone procesy zarządzania magazynem w skojarzonej grupie wymiarów magazynowania. Kody filtrów służą do określania, czy system zezwala użytkownikom na zakup danego towaru od danego dostawcy podczas tworzenia wierszy zamówienia zakupu. Aplikacja Microsoft Dynamics 365 Supply Chain Management oferuje dwie metody obsługi zatwierdzeń dostawców. Jeśli istnieje co najmniej jeden zwolniony produkt, w którym w polu **Metoda sprawdzania zatwierdzonych dostawców** jest ustawiona wartość *Tylko ostrzeżenie* lub *Niedozwolone*, dla tych pozycji można włączyć obie metody zatwierdzania przez dostawcę. Ta sytuacja może spowodować problemy dla użytkowników podczas tworzenia wierszy zamówienia zakupu.

## <a name="see-also"></a>Informacje dodatkowe

[Aby uzyskać więcej informacji, zobacz wpis w blogu na temat kodów filtrów magazynowych WMS](http://blog.dynamics-for-operations.com/2017/09/26/wms-warehouse-filter-codes/)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]