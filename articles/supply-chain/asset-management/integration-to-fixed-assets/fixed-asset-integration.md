---
title: Integrowanie zarządzania składnikami majątku ze środkami trwałymi
description: W tym temacie opisano sposób integrowania modułów zarządzanie składnikami majątku i Środki trwałe, dzięki czemu można łączyć środki trwałe z konserwowanymi składnikami majątku.
author: kamaybac
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: cdda44d361011706fe0ba170309908533aa0c2f7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435114"
---
# <a name="integrate-asset-management-with-fixed-assets"></a>Integrowanie zarządzania składnikami majątku ze środkami trwałymi

[!include [banner](../../includes/banner.md)]

Integrując moduły **Zarządzanie składnikami majątku** i **Środki trwałe**, dzięki czemu można łączyć środki trwałe z konserwowanymi składnikami majątku. Użytkownicy środków trwałych mogą następnie utworzyć konserwowany składnik majątku z nowego lub istniejącego środka trwałego, a użytkownicy zarządzania zasobami mogą skojarzyć konserwowany składnik majątku z istniejącym środkiem trwałym. Ta funkcja ułatwia także użytkownikom środków trwałych wyświetlanie kosztów zaksięgowanych z zleceń roboczych dla powiązanych konserwowanych składników majątku.

> [!NOTE]
> W tym temacie *konserwowany składników majątku* odnoszą się do środków trwałych z modułu **Zarządzanie zasobami** , a *środki trwałe* odnoszą się do środków trwałych z modułu **Środki trwałe**.

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a>Umożliwia ustawienie domyślnej lokalizacji dla nowych konserwowanych składników majątku, które są tworzone ze środków trwałych (opcjonalnie)

Ta opcjonalna konfiguracja umożliwia ustawienie domyślnej lokalizacji czynności konserwacyjnych dla nowych konserwowanych składników majątku, które są tworzone ze środków trwałych. Ta konfiguracja jest zazwyczaj przeprowadzana jednorazowo, jeśli w ogóle została ukończona.

Aby przeprowadzić tę konfigurację, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie składnikami majątku \> Ustawienia \> Parametry zarządzania składnikami majątku**.
1. Na karcie **Środki trwałe** w polu **Lokaliacja czynności konserwacyjnych** wybierz domyślną lokalizację dla towarów gotowych.
1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a>Praca ze zintegrowanymi konserwowanymi składnikami majątku i środkami trwałymi

W tej sekcji znajduje się kolekcja procedur pokazujących różne sposoby pracy z funkcjami zintegrowanego zarządzania składnikami majątku i środkami trwałymi.

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a>Kojarzenie istniejącego konserwowanego składnika majątku z środkiem trwałym

Aby skojarzyć istniejący konserwowany składnik majątku z środkiem trwałym, wykonaj następujące kroki.

1. Wybierz **Zarządzanie składnikami majątku  \> Składniki majątku \> Wszystkie składniki majątku** (lub Aktywne **składniki majątku**).
1. Wybierz składnik majątku.
1. Na skróconej karcie **Środka trwałego** w polu **Numer środka trwałego** wybierz istniejący środek trwały.
1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a>Umożliwia wyświetlenie środka trwałego skojarzonego z wybranym konserwowanm składnikiem majątku

Aby wyświetlić środek trwały skojarzonego z wybranym konserwowanm składnikiem majątku, wykonaj następujące kroki.

1. Wybierz **Zarządzanie składnikami majątku  \> Składniki majątku \> Wszystkie składniki majątku** (lub Aktywne **składniki majątku**).
1. Wybierz składnik majątku.
1. Na skróconej karcie **Środka trwałego** w polu **Numer środka trwałego** wybierz łącze..

    Zostanie otwarta strona **Środki trwałe** dla wybranego środka trwałego. (Zazwyczaj tę stronę można znaleźć pod **Środki trwałe \> Środki trwałe \> Środki trwałe**.)

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a>Umożliwia wyświetlenie konserwowanego składnika majątku skojarzonego z wybranym środkiem trwałym

Aby wyświetlić konserwowany składnik majątku skojarzony z wybranym środkiem trwałym, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Środki trwałe \> Środki trwałe \> Środki trwałe**.
1. Wybierz składnik majątku.
1. W okienku akcji, na karcie **Zarządzanie składnikami majątku** w grupie **Wyświetl** wybierz **Konserwowany składnik majątku**.

    Strona **Konserwowany składnik majątku** dla składnika majątku powiązana z wybranym środkiem trwałym jest otwarta. (Zazwyczaj ta strona znajduje się w **Zarządzanie składnikami majątku \> Składniki majątku \> Wszystkie składniki majątku**.)

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a>Wyświetlanie kosztów konserwacji skojarzonych ze środkiem trwałym

Zarządzanie środkami trwałymi może być księgowane na potrzeby środków konserwacyjnych, a każde z tych zleceń jest zazwyczaj kosztami. Gdy środek trwały jest skojarzony z zasobem obsługi, można przejść bezpośrednio ze środka trwałego w celu wyświetlenia odpowiednich kosztów.

Aby wyświetlić koszt konserwacji majątku skojarzony ze środkiem trwałym, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Środki trwałe \> Środki trwałe \> Środki trwałe**.
1. Wybierz składnik majątku.
1. W okienku akcji, na karcie **Zarządzanie składnikami majątku** w grupie **Wyświetl** wybierz **Koszt konserwacji**.

    Zostanie otwarta strona **Koszt konserwacji** i zostaną wyświetlone powiązane z tym koszty.

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a>Tworzenie nowego konserwowanego składnika majątku dla istniejącego środka trwałego

Aby utworzyć nowy konserwowany składnik majątku dla istniejącego środka trwałego, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Środki trwałe \> Środki trwałe \> Środki trwałe**.
1. Wybierz składnik majątku.
1. W okienku akcji, na karcie **Zarządzanie składnikami majątku** w grupie **Nowe** wybierz **Stwórz konserwowany składnik majątku**. (Jeśli ta opcja jest niedostępna, konserwowany składnik majątku może być już skojarzony z wybranym środkiem trwałym.)
1. Zakończ tworzenie składnika majątku w sposób opisany w temacie [Tworzenie składnika majątku](../objects/create-an-object.md).

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a>Tworzenie nowego środka trwałego i dodawanie nowego konserwowanego składnika majątku

Aby utworzyć nowy środek trwały i dodać nowy konserwowany składnik majątku dla niego, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Środki trwałe \> Środki trwałe \> Środki trwałe**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Zakończ tworzenie środka trwałego w sposób opisany w temacie [Tworzenie środka trwałego](../../../finance/fixed-assets/tasks/create-fixed-asset.md).
1. W okienku akcji, na karcie **Zarządzanie składnikami majątku** w grupie **Nowe** wybierz **Stwórz konserwowany składnik majątku**.
1. Zakończ tworzenie składnika majątku w sposób opisany w temacie [Tworzenie składnika majątku](../objects/create-an-object.md).

### <a name="remove-the-association-between-two-assets"></a>Usuń powiązanie między dwoma środkami trwałymi

W niektórych przypadkach może być konieczne usunięcie skojarzenia konserwowanego składnika majątku ze środkiem trwałym. Jeśli na przykład chcesz [utworzyć nowy konserwowany składnik majątku](#new-maintenance-from-fixed) ze środka trwałego, musisz najpierw usunąć istniejące skojarzenie.

Aby usunąć istniejące powązanie między konserwowanym składnikiem majątku i środka trwałego, wykonaj następujące kroki.

1. Wybierz **Zarządzanie składnikami majątku  \> Składniki majątku \> Wszystkie składniki majątku** (lub Aktywne **składniki majątku**).
1. Znajdź i otwórz środek trwały.
1. Na skróconej karcie **Środka trwałego** wyczyść wartość w polu **Lokalizacja czynności konserwacyjnych**.
1. Na okienku akcji wybierz opcję **Zapisz**.
