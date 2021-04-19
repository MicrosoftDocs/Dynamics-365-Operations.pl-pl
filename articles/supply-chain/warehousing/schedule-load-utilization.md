---
title: Planowanie wykorzystania przestrzeni magazynowej
description: W tym temacie wyjaśniono, jak skonfigurować i zaplanować obciążenie pracą dla magazynu.
author: MarkusFogelberg
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4d259fd6c27ac96475c49c431e347ca0c03a9e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817324"
---
# <a name="schedule-load-utilization"></a>Planowanie wykorzystania przestrzeni magazynowej

[!include[banner](../includes/banner.md)]

Można zaplanować wykorzystanie obciążenia pracą dla wybranych typów lokalizacji, a także prognozować bieżące i przyszłe wykorzystanie obciążenia pracą. Istnieje możliwość prognozowania obciążenia pracą dla jednego lub wielu oddziałów, dla jednostek obciążenia pracą (strefa lub magazyn) albo dla kombinacji strefy i magazynu.

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a>Planowanie i wyświetlanie obciążenia pracą dla magazynu lub oddziału

Aby zaplanować obciążenie pracą dla oddziałów, magazynów lub stref, należy utworzyć konfigurację wykorzystania miejsca i skojarzyć ją z planem głównym.

W konfiguracji wykorzystania miejsca używa się typów lokalizacji, takich jak **Lokalizacja buforowa** i **Lokalizacja pobrania**, aby określić sposób prognozowania wykorzystania przestrzeni. Można także określić tryb obciążenia prącą magazynu, taki jak **Strefa**.

Projekcja przyszłego wykorzystania miejsca jest oparta na informacjach, które będą obliczane w powiązanym planie głównym. Plany główne prognozują planowanie zasobów dla przychodzących i wychodzących zamówień do produkcji i operacji. Projekcja dostępnego miejsca opiera się na relacji między ustawieniami wykorzystania miejsca i wybranym planem głównym.

Używając trybu obciążenia pracą magazynu wybranego w konfiguracji wykorzystania miejsca, można określić, czy obciążenie pracą ma być prognozowane dla każdego magazynu lub strefy oraz czy prognozy powinny zawierać informacje o magazynach i strefach. Można także określić, czy zablokowane lokalizacje mają być wykluczone z obliczania wykorzystania obciążenia pracą.

W celu sporządzenia prognozy wykorzystania miejsca można wygenerować raport **Wykorzystanie przestrzeni magazynowej**. Podczas generowania tego raportu można określić, czy wykorzystanie obciążenia pracą ma być prognozowane dla każdego oddziału, różnych oddziałów czy wybranej jednostki obciążenia pracą, takiej jak strefa lub magazyn.

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a>Tworzenie ustawień wykorzystania miejsca dla magazynu

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Ustawienia** \> **Monitorowanie magazynu** \> **Wykorzystanie miejsca**.
2. Kliknij przycisk **Nowe**, aby utworzyć konfigurację wykorzystania miejsca. Określ identyfikator i nazwę dla nowej konfiguracji.
3. W polu **Tryb obciążenia pracą magazynu** wybierz, czy przegląd wykorzystania miejsca ma pokazywać informacje według magazynu, strefy, czy magazynu i strefy.
4. Ustaw w opcji **Wyklucz lokalizacje zablokowane** wartość **Tak**, aby wyłączyć zablokowane lokalizacje zapasów z obliczania wolnego miejsca. Można zablokować lokalizację zapasów dla operacji wprowadzania i wyprowadzania zapasów, określając przyczynę blokady lokalizacji w polu **Wejście zablokowane** lub **Wyjście zablokowane** na skróconej karcie **Inne** na stronie **Lokalizacje magazynowe**.
5. Na skróconej karcie **Typ lokalizacji** wybierz typy lokalizacji, które mają być uwzględnione przy obliczaniu wykorzystania miejsca. Musisz wybrać co najmniej jeden typ lokalizacji dla projekcji.

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a>Skojarzenie ustawień wykorzystania miejsca z planem głównym

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Zadania okresowe** \> **Planowanie wykorzystania przestrzeni magazynowej**.
2. W polu **Plan główny** zaznacz plan główny.
3. W polu **Liczba dni** należy określić liczbę dni, jaka ma być uwzględniona w prognozie bieżących i przyszłych obciążeń pracą.
4. W polu **Wykorzystanie miejsca** wybierz konfigurację wykorzystania miejsca, która ma być używana do prognozowania bieżących i przyszłych obciążeń pracą.

### <a name="specify-the-load-utilization-projection-and-view-information"></a>Określ projekcję wykorzystania przestrzeni i wyświetlanie informacji

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Raporty zapasów fizycznych** \> **Wykorzystanie przestrzeni magazynowej**.
2. W polu **Pokaż według** wybierz poziom prognozy wykorzystania miejsca:

    - **Oddział** — Prognozowanie wykorzystania miejsca dla każdego oddziału. Projekcja jest przydatne, np. jeśli użytkownik chce wyświetlić wszystkie magazyny dla oddziału, dzięki czemu można zbilansować wykorzystanie miejsca między magazynami.
    - **Jednostka obciążenia pracą** — Prognozowanie wykorzystania miejsca dla stref lub magazynów. Ilość wolnego miejsca jest następnie prognozowana zgodnie z wartością wybraną w polu **Tryb obciążenia pracą magazynu** na stronie **Wykorzystanie miejsca** podczas tworzenia konfiguracji wykorzystania miejsca.

3. Wykonaj jedną z następujących czynności, zależnie od wartości wybranej w poprzednim kroku:

    - Jeśli w polu **Pokaż według** wybrano wartość **Oddział**, jest dostępne pole **Oddział**. Wybierz jeden lub więcej oddziałów do uwzględnienia w prognozie.
    - Jeśli w polu **Pokaż według** wybrano wartość **Jednostka obciążenia pracą**, jest dostępne pole **Jednostka obciążenia pracą**. Wybierz jednostkę obciążenia pracą.

4. W polu **Typ obciążenia pracą** wybierz opcję **Objętość** lub **Masa**, aby wskazać jednostkę operacyjną obszaru, dla której ma zostać sporządzona prognoza miejsca.
5. W polu **Ustawienia wykorzystania miejsca** wybierz konfigurację wykorzystania miejsca, na której ma bazować prognoza.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]