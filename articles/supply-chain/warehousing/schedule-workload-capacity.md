---
title: Planowanie możliwości obciążenia pracą
description: W tym temacie omówiono konfigurowanie i planowanie możliwości obciążenia pracą dla pracowników w magazynie lub dla całego magazynu.
author: MarkusFogelberg
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2458009dabd71e6c8423e8e607a0cedb4765b88
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817348"
---
# <a name="schedule-workload-capacity"></a>Planowanie możliwości obciążenia pracą

[!include[banner](../includes/banner.md)]

Można zaplanować wielkość obciążenia pracą dla magazynów, a także prognozować bieżące i przyszłe obciążenia pracą dla pracowników w poszczególnych magazynach. Istnieje możliwość zaprojektowania obciążenia pracą dla całego magazynu lub oddzielnie dla przychodzących i wychodzących obciążeń pracą.

Aby sporządzić prognozę wyjściowego obciążenia pracą dla wybranych magazynów, muszą być dla nich dostępne dane planowania głównego. Aby uzyskać więcej informacji, zobacz [Omówienie planów głównych](../master-planning/master-plans.md).

## <a name="schedule-and-view-workloads-for-a-warehouse"></a>Planowanie i wyświetlanie obciążenia pracą dla magazynu

Aby zaplanować wielkości obciążenia pracą dla magazynu, utwórz ustawień obciążenia pracą dla jednego lub większej liczby magazynów, a następnie skojarzy ustawienia obciążenia pracą z planem głównym. W konfiguracji obciążenia pracą można określić limity masy lub objętość dla transakcji przychodzących i wychodzących. Można również utworzyć więcej niż jedną konfigurację dla każdego magazynu, a następnie skojarzyć konfigurację z indywidualnymi planami głównymi. Na przykład można użyć tej metody, aby uwzględnić sezonowe zmiany obsady kadrowej.

Jeśli pracownicy magazynu pracują z transakcjami zarówno dla obciążeń przychodzących, jak i wychodzących, można utworzyć konfigurację możliwości obciążenia magazynu, tak aby obciążenie pracą było prognozowane w scalonym widoku.

Aby zaplanować i wyświetlić obciążenie pracą dla magazynów, wykonaj następujące zadania:

1. Utwórz wielkość obciążenia pracą i zdefiniuj limity obciążeń pracą dla jednego lub większej liczby magazynów.
2. Skojarz ustawienia obciążenia pracą z planem głównym, aby utworzyć prognozy obciążenia pracą i określić, jak długo te prognozy mają obowiązywać.

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a>Tworzenie ustawienia wielkości obciążenia pracą dla magazynu

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Ustawienia** \> **Monitorowanie magazynu** \> **Możliwości obciążenia pracą**.
2. W okienku akcji naciśnij przycisk **Nowy**, aby utworzyć konfigurację możliwości obciążenia pracą.
3. Na skróconej karcie **Magazyny** kliknij przycisk **Nowy**, a następnie wprowadź wartości w wierszu, aby skojarzyć magazyn z konfiguracją możliwości obciążenia pracą.
4. Zaznacz pole wyboru **Połączone przychodzące i wychodzące obciążenie pracą**, jeśli raport **Możliwości obciążenia pracą** powinien wykazywać łączne obciążenie pracą dla transakcji przychodzących i wychodzących w jednym widoku.
5. Na skróconej karcie **Typy transakcji** wybierz typy transakcji przychodzących i wychodzących, do których będą stosowane limity obciążenia pracą.

    > [!NOTE]
    > Należy zaznaczyć co najmniej po jednym typie transakcji dla przychodzących i wychodzących obciążeń pracą.

#### <a name="define-limits-for-volume-or-weight"></a>Definiowanie ograniczeń objętości lub masy

Można skonfigurować limity objętości lub masy, w zależności od tego, które ograniczenia są użyteczne dla pracowników magazynu. Ograniczenia określone przez użytkownika są uwzględniane w prognozie obciążenia pracą, którą można obejrzeć w raporcie **Możliwości obciążenia pracą**.

Aby można było prognozować objętość i masę towarów, dla wszystkich produktów muszą być określone standardowe objętość i masa pozycji magazynowej. Pola wymagane są dostępne w następujących grupach pól na skróconej karcie **Zarządzanie zapasami** na stronie **Szczegóły zwolnionego produktu**:

- Obsługa
- Wymiary fizyczne
- Miary ciężaru

Jeśli te informacje nie zostały określone poprawnie, zostanie wyświetlony komunikat o błędzie podczas generowania raportu **Możliwości obciążenia pracą**. Z raportu można przejść do szczegółów, aby zidentyfikować brakujące informacje niezbędne do prognozowania przyszłego obciążenia pracą.

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a>Skojarzenie ustawień obciążenia pracą z planem głównym

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Okresowe** \> **Planowanie obciążenia pracą**.
2. W polu **Plan główny** wybierz plan główny dla prognoz obciążenia pracą.
3. W polu **Liczba dni** określ liczbę dni, jaką obejmie prognoza obciążenia pracą.
4. W polu **Obciążenie pracą** wybierz konfigurację obciążenia pracą, która ma zostać skojarzona z planem głównym.

### <a name="view-workload-capacity"></a>Wyświetlanie wielkości obciążenia pracą

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Raporty zapasów fizycznych** \> **Możliwości obciążenia pracą**.
2. W polu **Liczba kolumn** określ liczbę kolumn, jaka ma być wyświetlana w raporcie.
3. W polu **Typ zamówienia** zaznacz opcję **Planowane i potwierdzone**, **Planowane** lub **Potwierdzone**, aby wskazać typ zamówień, których mają dotyczyć prognozy w raporcie.
4. W polu **Typ obciążenia pracą** wybierz typ obciążenia i w ten sposób wskazać, czy prognoza możliwości obciążenia ma dotyczyć objętości, czy masy.
5. W polu **Możliwości obciążenia pracą** wybierz konfigurację możliwości obciążenia pracą.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]