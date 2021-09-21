---
title: Zwolnij do magazynu
description: Ten temat zawiera szczegóły dotyczące procesu zwalniania do magazynu. Opisuje on encje tworzone podczas zwalniania zamówienia do magazynu oraz opcje, których można użyć do inicjowania procesu.
author: mirzaab
ms.date: 8/13/2021
ms.topic: article
ms.search.form: WHSReleaseToWarehouse, WHSReleaseToWarehouseSalesOrder, WHSReleaseToWarehouseTransferOrder, WHSLoadPlanningWorkbench, WHSWaveTemplateTable, WHSWorkTemplateTable, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6c8aa0338ab30e6366601e3759141c7e41bf99fb
ms.sourcegitcommit: ab1455c67f6ee6ca36bec148bea0dbb0f7704eda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/26/2021
ms.locfileid: "7428956"
---
# <a name="release-to-warehouse"></a>Zwolnij do magazynu

[!include [banner](../../includes/banner.md)]

Ten temat zawiera szczegóły dotyczące procesu zwalniania do magazynu. Opisuje on encje tworzone podczas zwalniania zamówienia do magazynu oraz opcje, których można użyć do inicjowania procesu.

## <a name="release-to-warehouse-overview"></a>Omówienie zwalniania do magazynu

Zwalnianie do magazynu to proces tworzenia zapasów gotowych do przetwarzania wysyłki. Po zwolnieniu zamówienia do magazynu system utworzy wiersze ładunku i wysyłki. W przypadku skonfigurowania automatycznego przetwarzania grupy czynności są tworzone również ładunki i wymagana praca. Konfiguracja zaangażowanych encji zależy od ustawień systemowych. W tej sekcji tego tematu przeglądane są encje utworzone podczas procesu zwalniania do magazynu oraz ustawienia systemowe, które je definiują.

*Wysyłka* jest grupą zamówień sprzedaży lub wierszy zamówienia przeniesienia dla tego samego klienta lub tego samego adresu dostawy.

*Ładunek* to grupa zamówień sprzedaży lub wierszy zamówienia przeniesienia, które są pogrupowane i zwykle są wysyłane w jednej ciężarówce, jednym wagonie lub przy użyciu innego pojedynczego środka transakcji. Ładunek może mieć jedną lub wiele wysyłek. Ładunek można utworzyć ręcznie, dodając do nowego ładunku wiersze zamówienia. W takim przypadku wiersze zamówienia są przypisywane do ładunku przed zainicjowaniem procesu zwalniania do magazynu i mogą zostać zwolnione tylko ze strony **Pulpit planowania wysyłki ładunku**.

*Praca* magazynowa to dowolna operacja magazynowa wykonywana przez pracownika magazynu. Zwykle operacje pracy w magazynie składają się z co najmniej dwóch kolejnych działań: pracownik magazynu odbiera dostępny towar w lokalizacji, a następnie odkłada go w innej lokalizacji.

Po zwolnieniu zamówień do magazynu system utworzy *wiersze ładunku* i grupuje je w wysyłki. Proces konsolidacji wysyłki umożliwia automatyczną konsolidację wysyłek podczas procesu zwalniania do magazynu. Aby uzyskać więcej informacji, zobacz [Zasady konsolidacji wysyłek](about-shipment-consolidation-policies.md).

Do tworzenia pracy pobierania i ładunków do wysyłki system używa *grupy czynności*. *Szablon grupy czynności* musi być dostępny dla typu grupy czynności, którą chcesz utworzyć, oraz dla magazynu wiersza zamówienia. Szablony grupy czynności typu *Wysyłka* są używane do wysyłania towarów dla zamówień sprzedaży i zamówień przeniesienia.

Każdy szablon grupy czynności zawiera *metody grupy czynności*. Metody grupy czynności wykonują takie akcje, jak tworzenie pracy dla grupy czynności lub tworzenie ładunków. Na przykład szablon grupy czynności dla grupy czynności wysyłkowych może zawierać metody tworzenia ładunków, przypisania wierszy do grup czynności, uzupełnienia i tworzenia pobrania pracy dla grupy czynności. Szablon grupy czynności ustala wiele ustawień definiujących sposób generowania i przetwarzania grupy czynności, w tym czynności, które należy wykonać ręcznie i które zostaną wykonane automatycznie. Aby uzyskać więcej informacji o szablonach, zobacz temat [Szablony grupy czynności](wave-templates.md). Z tego powodu, w zależności od konfiguracji szablonu grupy czynności, podczas zwalniania zamówienia do magazynu jest automatycznie tworzona, przetwarzana i zwalniana grupy czynności albo niektóre lub wszystkie akcje są wykonywane ręcznie po zwolnieniu do magazynu.

Podczas przetwarzania grupy czynności system tworzy pracę pobierania na podstawie odpowiedniego *szablonu pracy* i *dyrektywy lokalizacji* i tworzy pracę dostępną dla urządzeń przenośnych. Szablon pracy określa, jak praca jest wykonywana dla każdego procesu magazynowego, a dyrektywa lokalizacji określa lokalizacje pobrania i odłożenia dla ruchu magazynowego. Aby uzyskać więcej informacji, zobacz [Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji](control-warehouse-location-directives.md).

> [!NOTE]
> Domyślnie grupy czynności są przetwarzane w trybie wsadowym.

Podczas przetwarzania grupy czynności system zwykle tworzy nowy ładunek dla każdej wysyłki, do której nie jest przypisane żadne obciążenie. Jeśli chcesz, aby w zamian system przypisywał nieprzypisane wysyłki do istniejących ładunków, możesz użyć zaawansowanej funkcji budowania ładunku grupy czynności. Aby uzyskać więcej informacji, zobacz [Zaawansowane kompilowanie ładunku podczas grupy czynności](advanced-load-building-during-wave.md).

Na stronach **Zamówienia sprzedaży** i **Zamówienia przeniesienia** można przeglądać encje utworzone dla wierszy zamówienia podczas procesu zwalniania do magazynu.

- Strona **Zamówienia sprzedaży**:

    - Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz pozycję **Magazyn**, a następnie z menu wybierz opcję **Szczegóły wysyłki**, aby otworzyć pokrewne wysyłki, **Szczegóły ładunku** w celu otwarcia powiązanych ładunków lub **Szczegóły pracy**, aby otworzyć powiązane szczegóły pracy.
    - Na skróconej karcie **Szczegóły wiersza** wybierz kartę **Ładunek**, aby przejrzeć powiązane ładunki.

- Strona **Zamówienia przeniesienia**:

    - W okienku akcji na karcie **Wysyłka** wybierz **Szczegóły wysyłki**, aby otworzyć powiązane wysyłki, lub **Szczegóły ładunku**, aby otworzyć powiązane ładunki.
    - Na skróconej karcie **Wiersze zamówienia przeniesienia** wybierz **Szczegóły pracy**, aby otworzyć powiązane szczegóły pracy.

Na zakończenie, gdy zamówienie jest zwalniane do magazynu, najbardziej zautomatyzowany przepływ działa w następujący sposób:

1. System tworzy wysyłkę dla zamówienia i grupy czynności.
1. Ta grupa czynności jest przetwarzana.
1. System tworzy ładunek i identyfikator pracy.

W zależności od szablonów grupy czynności, szablonów pracy i ustawień dyrektyw lokalizacji niektóre kroki tego przepływu mogą zostać wykonane ręcznie. Ogólny przepływ jest jednak taki sam.

Dostępnych jest kilka opcji zwalniania zamówienia do magazynu. Można wykonać operację ręcznie lub skonfigurować zadanie wsadowe. Pozostałe sekcje tego tematu zawierają szczegółowe informacje o sposobach wykonywania operacji zwalniania do magazynu.

## <a name="manual-release-to-the-warehouse-from-the-sales-orders-and-transfer-orders-pages"></a>Ręczne zwalnianie do magazynu ze stron Zamówienia sprzedaży i Zamówienia przeniesienia

Zamówienie do magazynu można zwalniać bezpośrednio ze strony **Zamówienia sprzedaży** lub **Zamówienia przeniesienia**, wybierając opcję **Zwolnij do magazynu**.

- Na stronie **Zamówienia sprzedaży** przycisk znajduje się na karcie **Magazyn** w okienku akcji.
- Na stronie **Zamówienia przeniesienia** przycisk znajduje się na karcie **Wysyłka** w okienku akcji.

Na stronie **Zamówienia sprzedaży** można jednocześnie zwolnić kilka zamówień sprzedaży.

## <a name="manual-release-to-the-warehouse-from-the-release-to-warehouse-pages"></a>Ręczne zwalnianie do magazynu ze stron Zwalnianie do magazynu

W systemie aktualnie dostępne są trzy strony, na których można przeglądać wiersze wielu zamówień i zwalniać je do magazynu:

- **Zwalnianie do magazynu** (**Zarządzanie magazynem \> Zwalnianie do magazynu \> Zwolnij do magazynu**) — ta strona umożliwia pracę z zamówieniami sprzedaży i zamówieniami przeniesienia. Jednak oferuje ona wolniejsze działanie niż pozostałe dwie strony. Ta strona wkrótce będzie przestarzała.
- **Zwalnianie zamówień sprzedaży do magazynu** (**Zarządzanie magazynem \> Zwalnianie do magazynu \> Zwolnij zamówienia sprzedaży do magazynu**) — ta strona umożliwia pracę tylko z zamówieniami sprzedaży. Oferuje natomiast lepszą wydajność niż strona **Zwalnianie do magazynu**.
- **Zwalnianie zamówień przeniesienia do magazynu** (**Zarządzanie magazynem \> Zwalnianie do magazynu \> Zwolnij zamówienia przeniesienia do magazynu**) — ta strona umożliwia pracę tylko z zamówieniami przeniesienia. Oferuje natomiast lepszą wydajność niż strona **Zwalnianie do magazynu**.

Wszystkie trzy strony zawierają podobne funkcje, co opisano w pozostałej sekcji. Wszystkie umożliwiają wybranie wierszy zamówienia lub całych zamówień, a następnie zwolnienie ich do magazynu.

Każda ze stron składa się z górnej sekcji, w której można wybrać wiersze zamówienia, oraz dolnej sekcji, w której można zainicjować proces zwalniania do magazynu. W górnej sekcji można używać filtrów do wyszukiwania wierszy zamówienia sprzedaży, które mają zostać zwolnione. Strona **Zwalnianie do magazynu** udostępnia osobną kartę dla zamówień sprzedaży i zamówień przeniesienia w górnej sekcji, podczas gdy na każdej z pozostałych dwóch stron jest przedstawiany tylko jeden typ zamówienia.

Pasek narzędzi w górnej sekcji zawiera następujące przyciski, których można używać do wybierania wierszy zamówienia do zwolnienia do magazynu:

- **Dodaj** — wybierz jeden lub więcej wierszy zamówienia w górnej sekcji, a następnie wybierz ten przycisk dla tych wierszy w dolnej sekcji.
- **Dodaj wszystko** — dodaj wszystkie wiersze z górnej sekcji do dolnej sekcji.
- **Dodaj zamówienie** — wybierz zamówienie, a następnie wybierz ten przycisk, aby dodać wszystkie wiersze z tego zamówienia do dolnej sekcji.

Po dodaniu wierszy do dolnej sekcji zaznacz każdy wiersz, który chcesz zwolnić. Następnie wybierz pozycję **Zwolnij do magazynu** na pasku narzędzi, aby zwolnić te wiersze do magazynu.

## <a name="manual-release-to-the-warehouse-from-the-load-planning-workbench-page"></a>Ręczne zwalnianie do magazynu ze strony Pulpit planowania wysyłki ładunku

Zamówienia można również zwalniać do magazynu ręcznie za pomocą strony **Pulpit planowania wysyłki ładunku**. Ta strona umożliwia organizowanie wierszy zamówień w ładunki, a następnie zwalnianie tych ładunków do magazynu.

Aby otworzyć stronę **Pulpit planowania wysyłki ładunku**, przejdź do pozycji **Zarządzanie magazynem \> Ładunki**. Można ją również otworzyć ze stron **Zamówienia sprzedaży** i **Zamówienia przeniesienia**. W górnej sekcji strony można wybrać wiersze zamówienia sprzedaży na karcie **Wiersze sprzedaży** oraz wiersze zamówienia przeniesienia na karcie **Wiersze przeniesienia**, a następnie dodać te wiersze do nowego lub istniejącego ładunku.

Karta **Podaż i popyt** w okienku akcji zawiera następujące przyciski, których można używać do dodawania wierszy zamówień w górnej sekcji do ładunku:

- **Do nowego ładunku** — wybierz wiersze zamówienia w górnej sekcji, a następnie wybierz ten przycisk w celu utworzenia nowego ładunku i dodania do niego tych wierszy.
- **Do istniejącego ładunku** — wybierz wiersze zamówienia w górnej sekcji, a następnie wybierz ten przycisk dodania do tych wierszy do istniejącego ładunku.
- **Całe zamówienie do nowego ładunku** — wybierz zamówienia, a następnie wybierz ten przycisk w celu utworzenia nowego ładunku i dodania do niego wszystkich wierszy z tych zamówień.
- **Całe zamówienie do istniejącego ładunku** — wybierz zamówienie, a następnie wybierz ten przycisk w celu dodania wszystkich wierszy z tego zamówienia do istniejącego ładunku.

W dolnej sekcji możesz przejrzeć utworzone ładunki. Aby zwolnić ładunki do magazynu, wybierz je, a następnie wybierz opcję **Zwalnianie \> Zwolnij do magazynu** na pasku narzędzi. Jeśli jest przeprowadzane automatyczne przetwarzanie grupy czynności, ponieważ ładunki są już przypisane do wierszy zamówienia, po wykonaniu operacji zwalniania do magazynu system tworzy wysyłki i identyfikatory pracy.

## <a name="automatic-release-to-the-warehouse"></a>Automatyczne zwalnianie do magazynu

Aby automatycznie zwalniać zamówienia do magazynu, należy użyć zadań **Automatyczne zwalnianie zamówień sprzedaży** i **Automatyczne zwalnianie zamówień przeniesienia**.

Aby skonfigurować zadanie wsadowe, które zwalnia zamówienia sprzedaży, wykonaj następujące czynności.

1. Przejdź do pozycji **Zarządzanie magazynem \> Zwolnij do magazynu \> Automatyczne zwalnianie zamówień sprzedaży**
1. W oknie dialogowym **Automatyczne zwalnianie zamówień sprzedaży** na skróconej karcie **Parametry** ustaw następujące pola:

    - **Ilość do zwolnienia** — określa, czy do magazynu ma być zwolniona cała ilość czy tylko ilość fizycznie dostępna.
    - **Zezwalaj na częściowe zwalnianie zamówień** — umożliwia określenie, czy pozostałe ilości częściowo zwolnionych zamówień mają być zwalniane do magazynu.
    - **Zachowaj rezerwacje w przypadku niepowodzenia zwolnienia** — umożliwia określenie, czy ilości automatycznie zarezerwowane dla zamówienia sprzedaży powinny pozostać zarezerwowane w przypadku niepowodzenia procesu zwalniania do magazynu.
    - **Zablokowana obsługa zamówień** — umożliwia wybór sposobu obsługi aktualnie zablokowanych zamówień sprzedaży przez system, ponieważ są one edytowane przez innych użytkowników lub procesy:

        - *Czekaj na odblokowanie zamówień* — system powinien czekać na odblokowanie zamówień przed ich zwolnieniem do magazynu. W tym przypadku proces zwalniania do magazynu może potrwać dłużej.
        - *Pomiń zablokowane zamówienia* — system powinien pomijać zablokowane zamówienia.

    - **Prawidłowe typy zamówień** — umożliwia wybór typów zamówień sprzedaży, które mają być dołączane w partii.
    - **Typ limitu kredytu** — umożliwia określenie, czy podczas procesu zwalniania do magazynu ma być wykonywane sprawdzanie limitów kredytu, oraz informacji o transakcjach, które mają zostać uwzględnione w ewentualnych procesach sprawdzania.

1. Aby kontrolować, które zamówienia mają być przetwarzane, na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj**. Zostanie wyświetlone standardowe okno dialogowe zapytania, w którym można definiować kryteria wyboru, kryteria sortowania i sprzężenia. Pola działają w ten sam sposób, jak działają w przypadku innych typów zapytań w aplikacji Microsoft Dynamics 365 Supply Chain Management.
1. Na skróconej karcie **Uruchom w tle** wybierz, czy zadanie powinno działać w trybie wsadowym, i/lub skonfiguruj harmonogram cykliczny. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.
1. Wybierz przycisk **OK**, aby zastosować ustawienia i zainicjować proces zwalniania do magazynu.

Aby skonfigurować zadanie wsadowe, które zwalnia zamówienia przeniesienia, wykonaj następujące czynności.

1. Przejdź do pozycji **Zarządzanie magazynem \> Zwolnij do magazynu \> Automatyczne zwalnianie zamówień przeniesienia**.
1. W oknie dialogowym **Automatyczne zwalnianie zamówień przeniesienia** na skróconej karcie **Parametry** ustaw następujące pola:

    - **Ilość do zwolnienia** — określa, czy do magazynu ma być zwolniona cała ilość czy tylko ilość fizycznie dostępna.
    - **Zezwalaj na częściowe zwalnianie zamówień** — umożliwia określenie, czy pozostałe ilości częściowo zwolnionych zamówień mają być zwalniane do magazynu.
    - **Grupuj zwolnienia według magazynu docelowego** — umożliwia określenie, czy system ma jednocześnie zwolnić wszystkie zamówienia przeniesienia, czy też ma grupować wiersze zamówienia przeniesienia według magazynu docelowego, a następnie zwalniać poszczególne grupy do magazynu osobno.

1. Aby kontrolować, które zamówienia mają być przetwarzane, na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj**. Zostanie wyświetlone standardowe okno dialogowe zapytania, w którym można definiować kryteria wyboru, kryteria sortowania i sprzężenia. Pola działają w ten sam sposób, jak działają w przypadku innych typów zapytań w aplikacji Supply Chain Management.
1. Na skróconej karcie **Uruchom w tle** wybierz, czy zadanie powinno działać w trybie wsadowym, i/lub skonfiguruj harmonogram cyklu. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.
1. Wybierz przycisk **OK**, aby zastosować ustawienia i zainicjować proces zwalniania do magazynu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
