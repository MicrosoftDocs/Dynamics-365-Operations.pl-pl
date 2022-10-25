---
title: Plany oparte na ofertach i ZO
description: W tym artykule opisano sposób skonfigurowania planowania głównego, aby uwzględnić oferty i zapytania ofertowe (ZO) podczas generowania zamówień planowanych.
author: t-benebo
ms.date: 09/20/2022
ms.topic: article
ms.search.form: SalesQuotationListPage, ReqPlanSched, SalesQuotationTable, smmOpportunityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-20
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: eaeb3c26a562c1daebe8296b26077ee5a3223e4d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690091"
---
# <a name="plan-based-on-quotations-and-rfqs"></a>Planowanie na podstawie ofert i ZO

[!include [banner](../../includes/banner.md)]

Oferty i zapytania ofertowe (ZO) reprezentują możliwe, a nawet prawdopodobne przyszłe zamówienia. Z tego względu warto je uwzględnić podczas planowania głównego, aby można było zaplanować dodatkowe dostawy na podstawie istniejących ZO i prawdopodobieństwa, że każda oferta stanie się rzeczywistym zamówieniem. W tym artykule opisano sposób skonfigurowania planowania głównego, aby uwzględnić oferty i ZO podczas generowania zamówień planowanych.

## <a name="set-up-master-planning-to-consider-sales-quotations-andor-rfqs"></a>Konfigurowanie planowania głównego w celu uwzględnienia ofert sprzedaży i/lub ZO

Aby skonfigurować planowanie główne, tak aby uwzględnić oferty sprzedaży i/lub ZO, należy skorzystać z następującej procedury.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz istniejący plan w okienku listy lub wybierz opcję **Nowy** w okienku akcji, aby utworzyć nowy.
1. Na skróconej karcie **Ogólne** ustaw następujące pola:

    - **Uwzględnij oferty sprzedaży** — ustaw dla tej opcji wartość *Tak*, aby po uruchomieniu bieżącego planu uwzględnić oferty sprzedaży. Ustaw opcję na wartość *Nie*, aby je zignorować.
    - **% prawdopodobieństwa** — ustaw minimalny poziom ufności, który musi być uwzględniany w planowaniu głównym dla oferty. Obliczenie planowania głównego obejmie wszystkie oferty utworzone na podstawie szans sprzedaży o tym lub wyższym prawdopodobieństwie. Aby uwzględnić wszystkie oferty, w tym oferty, które nie mają przypisanego prawdopodobieństwa lub z którymi nie skojarzono szans sprzedaży, ustaw w tym polu wartość *0* (zero). Aby uzyskać więcej informacji o prawdopodobieństwach dla ofert, zapoznaj się z następną sekcją.
    - **Uwzględnij zapytania ofertowe** — ustaw dla tej opcji wartość *Tak*, aby po uruchomieniu bieżącego planu uwzględnić ZO. Ustaw opcję na wartość *Nie*, aby je zignorować. Jeśli wybierzesz opcję uwzględnienia ZO, system utworzy dla nich planowane zamówienia zakupu, ale nie określi dostawcy, dopóki ZO nie zostanie rozwiązane. Planowane zamówienia zakupu utworzone na podstawie ZO mogą mieć wpływ na ilości innych zamówień planowanych.

1. Kontynuuj konfigurowanie planu głównego w zwykły sposób.

## <a name="assign-and-view-probabilities-for-quotations"></a>Przypisywanie i wyświetlanie prawdopodobieństw dla ofert

Jak wspomniano w poprzedniej sekcji, w planie głównym będą rozważane tylko oferty, które spełniają lub przekraczają próg prawdopodobieństwa zdefiniowany dla planu (jeśli zdefiniowano próg). Prawdopodobieństwo nie jest jednak ustawiane bezpośrednio dla każdej oferty. Jest ono dziedziczone po szansie sprzedaży użytej do wygenerowania oferty. Dlatego oferty tworzone bezpośrednio na stronie **Wszystkie oferty** nie będą mieć przypisanego prawdopodobieństwa ani skojarzonej z nimi szansy sprzedaży i nie będą nigdy uwzględniane przez planowanie główne (chyba że pole **% prawdopodobieństwa** zostanie ustawione na *0* \[zero\]). Aby do oferty przypisano prawdopodobieństwo, należy ją wygenerować na podstawie szansy sprzedaży.

### <a name="create-a-quotation-from-an-opportunity"></a>Tworzenie oferty na podstawie szansy sprzedaży

Użyj poniższej procedury, aby przypisać prawdopodobieństwo do szansy sprzedaży, a następnie utworzyć ofertę na podstawie tej szansy sprzedaży.

1. Przejdź do pozycji **Sprzedaż i marketing \> Relacje \> Szanse sprzedaży \> Wszystkie szanse sprzedaży**.
1. Wybierz istniejącą szansę sprzedaży, lub wybierz opcję **Nowy** w okienku akcji, aby utworzyć nową.
1. Wypełnij stronę szansy sprzedaży, aby zidentyfikować wybraną szansę sprzedaży. Pamiętaj, aby ustawić odpowiednią wartość w polu **Prawdopodobieństwo**. Tylko plany główne, które są ustawione w celu wyszukiwania prawdopodobieństw o tej lub większej wartości, będą uwzględniały oferty wygenerowane na podstawie tej szansy sprzedaży.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji, na karcie **Szansa sprzedaży** w grupie **Nowa** wybierz pozycję **Oferta sprzedaży** lub **Oferta projektu**, w zależności od typu oferty, którą chcesz utworzyć.
1. W oknie dialogowym **Tworzenie oferty** ustaw pola zgodnie z potrzebami, a następnie wybierz przycisk **OK**.
1. Zostanie utworzona i otwarta nowa oferta. Na skróconej karcie **Wiersze** użyj paska narzędzi, aby dodać wiersze sprzedaży lub wiersze projektu zgodnie z potrzebami w celu zdefiniowania zawartości oferty.
1. Na okienku akcji wybierz opcję **Zapisz**. Następnie zamknij ofertę.

### <a name="view-the-probability-that-is-assigned-to-a-quotation"></a>Wyświetlanie prawdopodobieństwa przypisanego do oferty

Jedynym sposobem wyświetlenia prawdopodobieństwa przypisanego do oferty jest otwarcie szansy sprzedaży użytej do utworzenia tej oferty, zgodnie z następującą procedurą.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Oferty sprzedaży \> Wszystkie oferty**.
1. Jeśli kolumna **Identyfikator szansy sprzedaży** nie jest wyświetlana (jest ukryta w domyślnej instalacji), wykonaj poniższe kroki, aby wyświetlić ją tymczasowo. (Alternatywnie, aby kolumna **Identyfikator szansy sprzedaży** była stale dostępna, utwórz zawierający ją [zapisany widok](../../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json)).

    1. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w siatce, a następnie wybierz polecenie **Wstaw kolumny**.
    1. W oknie dialogowym **Wstawianie kolumn** znajdź wiersz, w którym w polu **Pole** jest ustawiona wartość *Szansa sprzedaży*, i zaznacz pole wyboru **Wybierz** dla tego wiersza.
    1. Wybierz przycisk **Aktualizuj**, aby dodać wybraną kolumnę do strony **Wszystkie oferty**.

1. W siatce znajdź wiersz odpowiedniej oferty. Następnie w kolumnie **Identyfikator szansy sprzedaży** wybierz wartość dla tego wiersza.

    > [!NOTE]
    > W przypadku wyszukiwania oferty w ramach projektu może być konieczne wybranie nagłówka kolumny **Typ oferty** i wyczyszczenie jej filtru. W domyślnej instalacji ten filtr jest ustawiony tak, aby wyświetlać tylko oferty sprzedaży.

1. Powiązana szansa sprzedaży zostanie otwarta. Teraz można wyświetlać i odpowiednio edytować wartość **Prawdopodobieństwo**.
