---
title: Prognozy konserwacji
description: W tym temacie wyjaśniono prognozy konserwacji w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: dd652af3100f8de59e06490443baeebca58a4dd3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838545"
---
# <a name="maintenance-forecasts"></a>Prognozy konserwacji

[!include [banner](../../includes/banner.md)]



Podczas tworzenia zlecenia pracy, są tworzone zadania zlecenia pracy, które mają powiązane typy składników majątku i zadań konserwacyjnych. Po wybraniu typu zadania konserwacji zawierającego prognozy konserwacji, prognozy są automatycznie kopiowane do zlecenia pracy.

Można dodawać wiersze prognozy do zlecenia pracy lub usuwać je ze zlecenia pracy. Konfiguracja stanu cyklu życia zlecenia pracy, powiązanego typu projektu oraz reguł etapów związanych z typem projektu określa, czy można dodawać lub edytować wiersze prognozy. Aby uzyskać więcej informacji na temat stanów cyklu życia zlecenia pracy i etapów projektu należy zapoznać się z [Prognozy, zlecenia pracy i projekty](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

1. Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy na liście, a następnie w okienku akcji > na karcie **Zlecenie pracy**, w grupie **Projekt** wybierz pozycję **Prognozy**. Na stronie **Prognoza konserwacji zlecenia pracy** zostaną wyświetlone wiersze prognozy z typu zadania konserwacji wybrane w zadaniu zlecenia pracy.


## <a name="add-an-hours-forecast-to-a-work-order"></a>Dodaj prognozę godzin dla zlecenia pracy

1. Na stronie **Prognoza konserwacji zlecenia pracy** wybierz zadanie zlecenia pracy, do którego chcesz dodać prognozę.

2. Na skróconej karcie **Godziny** wybierz **Dodaj**, aby utworzyć nowy wiersz.

3. W polu **Kategoria** wybierz kategorię.

4. W polu **Godziny** wstaw liczbę prognozowanych godzin.

5. W polu **Właściwości wiersza** wybierz typ opłaty, który ma być używany w wierszu.


## <a name="add-an-items-forecast-to-a-work-order"></a>Dodaj pozycje prognozy dla zlecenia pracy

Istnieją trzy sposoby dodawania pozycji do prognozy konserwacji zlecenia pracy. Wiersze można tworzyć dla pozycji (części zamienne), które nie są uwzględnione na liście części zamiennych lub list składowych składników majątku (BOM), można wybierać części zamienne z listy zatwierdzone części zamienne, a także wybierać pozycje ze składników majatku BOM.

- Na stronie **Prognoza konserwacji zlecenia pracy** wybierz zadanie zlecenia pracy, do którego chcesz dodać prognozę.

- Na skróconej karcie **Pozycje** dodaj pozycje do prognozy konserwacji, stosując odpowiednią metodę.

Aby utworzyć nowy wiersz dla części zamiennej, która nie znajduje się na liście części zamiennych lub na liście BOM składników majątku, postępuj zgodnie z następującymi krokami:

1. Wybierz opcję **Dodaj**.
2. W polu **Numer pozycji** wybierz pozycję.
3. W polu **Ilość sprzedaży** wprowadź ilość.
4. W polu **Jednostka** wybierz jednostkę miary dla ilości.
5. W polach **Koszt własny** i **Waluta** wprowadź odpowiednie wartości.
6. W polu **Właściwość wiersza** wybierz właściwość wiersza.
7. Aby zmienić listę wymiarów wyświetlanych w wierszach pozycji, kliknij **Zapasy** > **Wyświetl wymiary**, wybierz wymiary i na przycisku przełącznika **Zapisz ustawienia** wybierz opcję **Tak**.

Aby dodać część zamienną z listy zatwierdzonych części zamiennych, wykonaj następujące kroki:

1. Wybierz **Dodaj części zamienne**.
2. Wybierz część zamienną i w razie konieczności zmodyfikuj odpowiednie informacje.
3. Kliknij przycisk **OK**.

Aby dodać towar z BOM środka trwałego, należy wykonać następujące kroki:

1. Wybierz **Dodaj pozycje BOM**.
2. Wybierz pozycje i w razie konieczności zmodyfikuj odpowiednie informacje.
3. Kliknij przycisk **OK**.

Aby uzyskać informacje o tym, gdzie jest używana pozycja w wybranym wierszu w odniesieniu do składników majątku, domyślnych typów zadań konserwacji, części zamiennych i zleceń pracy w module Zarządzanie składnikami majątku, wybierz opcję **Używająca pozycja**. Aby uzyskać więcej informacji na temat tego przeglądu, zobacz [Używająca pozycja](../controlling-and-reporting/item-where-used.md).


## <a name="add-an-expense-forecast-to-a-work-order"></a>Dodaj prognozę wydatków dla zlecenia pracy

1. Na stronie **Prognoza konserwacji zlecenia pracy** wybierz zadanie zlecenia pracy, do którego chcesz dodać prognozę.

2. Na skróconej karcie **Wydatki** wybierz **Dodaj**, aby utworzyć nowy wiersz.

3. W polu **Kategoria** wybierz kategorię.

4. W polu **Ilość** wprowadź ilość.

5. W polach **Koszt własny**, **Waluta sprzedaży** i **Cena sprzedaży** wpisz odpowiednie wartości.

6. W polu **Właściwości wiersza** wybierz typ opłaty, który ma być używany w wierszu.

>[!NOTE]
>W skróconej karcie **Sumy prognozy konserwacji** można wyświetlić przegląd liczby wierszy utworzonych na poszczególnych kartach dla wybranego zadania zlecenia oraz zlecenia pracy. Ponadto pokazuje sumę prognozowanych godzin dla zadania zlecenia pracy i zlecenia pracy.

Na poniższej ilustracji pokazano przykład strony listy **Prognoza konserwacji zlecenia pracy**.

![Rysunek 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Automatyczna aktualizacja prognoz zleceń pracy

W module Zarządzanie składnikami majątku można automatycznie aktualizować zmiany prognoz zleceń, aby odzwierciedlały zmainy w kosztach godzinowych, kosztach towarów i wydatków, które zostały zaktualizowane w innych modułach w Microsoft Dynamics 365 for Finance and Operations. Pomaga to upewnić się, że ostatnie koszty własne są zawsze używane w prognozach zleceń pracy. Możliwe jest również tworzenie podobnych aktualizacji dla [prognoz typu zadania konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Wybierz **Zarządzanie składnikami majątku** > **Okresowe** > **Prognoza** > **Aktualizacja prognozy zlecenia pracy**.

2. W oknie dialogowym **Aktualizacja prognozy zlecenia pracy** na skróconej karcie **Rekordy do uwzględnienia** w razie potrzeby można dodawać wybory dotyczące określonych zleceń pracy lub zadań zlecenia pracy. Wybierz pozycję **Filtruj** i wybierz odpowiednie opcje.

3. Na skróconej karcie **uruchom w tle** w razie potrzeby możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe.

4. Wybierz przycisk **OK**, aby rozpocząć aktualizację prognozy.


Na poniższej ilustracji pokazano przykład okna dialogowego **Aktualizacja prognozy zlecenia pracy**.

![Rysunek 2](media/07-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]