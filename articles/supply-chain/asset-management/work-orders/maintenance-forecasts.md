---
title: Prognozy konserwacji
description: W tym temacie wyjaśniono prognozy konserwacji w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024506"
---
# <a name="maintenance-forecasts"></a>Prognozy konserwacji

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Podczas tworzenia zlecenia pracy, zadania zlecenia pracy są tworzone z uwzględnieniem odpowiednich typów składników majątku i zadań konserwacyjnych. Po wybraniu typu zadania konserwacji zawierającego prognozy konserwacji, prognozy są automatycznie kopiowane do zlecenia pracy.

Istnieje możliwość dodawania lub usuwania wierszy prognozy w zleceniu pracy. Konfiguracja stanu cyklu życia zlecenia pracy, powiązanego typu projektu oraz reguł etapów związanych z typem projektu określa, czy można dodawać lub edytować wiersze prognozy. 

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy z listy i kliknij przycisk **prognoza.** W **prognozieobsługi zlecenia pracy** zostaną wyświetlone wiersze prognozy z typu zadania konserwacji wybrane w zadaniu zlecenia pracy.


## <a name="add-hours-forecast-to-a-work-order"></a>Dodaj prognozę godzin dla zlecenia pracy

1. Wybierz zadanie zlecenia pracy, w którym chcesz dodać wiersz prognozy.

2. Na skróconej karcie **Godziny** kliknij przycisk **Dodaj**, aby utworzyć nowy wiersz.

3. Wybierz kategorię w polu **Kategoria**.

4. Wstaw liczbę prognozowanych godzin w polu **godziny**.

5. W polu **Właściwości wiersza** wybierz typ opłaty, który ma być używany w wierszu.


## <a name="add-items-forecast-to-a-work-order"></a>Dodaj pozycje prognozy dla zlecenia pracy

Istnieją trzy sposoby dodawania pozycji do prognozy zleceń pracy konserwacji: wiersze można tworzyć dla towarów (części zamienne), które nie są uwzględnione na liście części zamiennych lub BOM składników majątku, można wybierać części zamienne z listy zatwierdzone części zamienne, a także wybierać towary ze składników majatku BOM.

1. Wybierz zadanie zlecenia pracy, w którym chcesz dodać wiersz prognozy.

2. Otwórz skróconą kartę **Towary**.

3. Kliknij **Dodaj**, aby utworzyć nowy wiersz dla części zamiennej, która nie znajduje się na liście części zamiennych lub na liście BOM składników majątku.

4. Wybierz pozycję w polu **Kod pozycji**.

5. Wstaw ilość w polu **ilość sprzedaży**, a następnie wybierz jednostkę ilości w polu **jednostka**.

6. Wstaw koszt własny i walutę w odpowiednich polach i wybierz **Właściwość wiersza**.

7. Aby zmienić listę wymiarów wyświetlanych w wierszach towaru, kliknij **Zapasy** > **Wyświetl wymiary**, wybierz wymiary i wybierz wartość tak na przycisku przełącznika **Zapisz ustawienia**.

8. Jeśli chcesz dodać zatwierdzoną część zamienną do prognozy konserwacji, kliknij opcję **Dodaj części zamienne**, wybierz część zamienną, w razie potrzeby edytuj informacje i kliknij przycisk **OK**.

9. Jeśli chcesz dodać towary BOM aktywów do prognozy, kliknij przycisk **Dodaj towary BOM**, wybierz towar, w razie potrzeby edytuj informacje związane, a następnie kliknij przycisk **OK**.

10. Kliknij **Używająca pozycja** jeśli chcesz uzyskać informacje o tym, gdzie w module Zarządzaniu składnikami majątku jest używany element w wybranym wierszu, w odniesieniu do składników majątku, zadań konserwacji, części zamiennych i zleceń pracy. 



## <a name="add-expense-forecast-to-a-work-order"></a>Dodaj prognozę wydatków dla zlecenia pracy

1. W tym temacie opisano sposób dodawania prognozy wydatków do zlecenia pracy. Z lewej strony formularza wybierz zadanie zlecenia pracy, do którego chcesz dodać prognozę.

2. Otwórz skróconą kartę **Wydatki**.

3. Kliknij przycisk **Dodaj**, aby utworzyć nowy wiersz.

4. Wybierz kategorię w polu **Kategoria**.

5. W polu **Ilość** wprowadź ilość.

6. Umożliwia wstawienie kosztu własnego, waluty sprzedaży i ceny sprzedaży w odpowiednich polach.

7. W polu **Właściwości wiersza** wybierz typ opłaty, który ma być używany w wierszu.

>[!NOTE]
>W skróconej karcie **sumy prognozy konserwacji** można wyświetlić przegląd liczby wierszy utworzonych na poszczególnych kartach dla wybranego zadania zlecenia oraz zlecenia pracy. Ponadto w przypadku zlecenia pracy można wyświetlić sumę prognozowanych godzin pracy dla zadania zlecenia.

![Rysunek 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Automatyczna aktualizacja prognoz zleceń pracy

W module Zarządzanie składnikami majątku można automatycznie aktualizować zmiany prognoz zleceń, dotyczące kosztów godzinowych, kosztów towarów i wydatków, które zostały zaktualizowane w innych modułach. W tym celu należy upewnić się, że ostatnie koszty własne są zawsze używane w prognozach zleceń pracy. Możliwe jest również tworzenie podobnych aktualizacji dla [Prognoza typu zadania konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Kliknij **Zarządzanie składnikami majątku** > **Okresowe** > **Prognoza** > **Aktualizacja prognozy zlecenia pracy**.

2. W oknie dialogowym **Aktualizacja prognozy zlecenia pracy** w razie potrzeby można dodawać wybory dotyczące określonych zleceń pracy lub zadań zlecenia pracy. Kliknij **Filtruj**, aby wybrać te opcje.

3. W razie potrzeby możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe na skróconej karcie **Uruchom w tle**.

4. Kliknij przycisk **OK**, aby rozpocząć aktualizację prognozy.


![Rysunek 2](media/07-work-orders.png)

