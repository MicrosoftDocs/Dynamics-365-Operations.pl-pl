---
title: "Zakresy serwisów"
description: "Interwał serwisu określa częstotliwość, z jaką są tworzone wiersze umowy serwisowej podczas tworzenia zleceń serwisowych."
author: YuyuScheller
manager: AnnBe
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4ea10e4c0fbfd21538bba16d2b01deb3e4b3a10d
ms.openlocfilehash: 4a51a3c3483e81cefdaf3d8e62a4f1f47fcd706b
ms.contentlocale: pl-pl
ms.lasthandoff: 02/20/2018

---

# <a name="service-intervals"></a>Zakresy serwisów

[!INCLUDE [banner](../includes/banner.md)]

Interwał umowy serwisowej określa częstotliwość, z jaką są tworzone wiersze umowy serwisowej podczas automatycznego tworzenia zleceń serwisowych.

Jeśli zlecenia serwisowe są tworzone automatycznie, wiersze zlecenia serwisowego są tworzone zgodnie z interwałem określonym dla wiersza umowy serwisowej według daty początkowej tego wiersza.

Jeśli pole **Interwał** wiersza umowy serwisowej na stronie **Umowy serwisowe** jest puste, wiersz określa zdarzenie jednorazowe i nie będzie używany do wielokrotnego tworzenia zleceń serwisowych.

## <a name="example"></a>Przykład

Ten przykład ilustruje wpływ ram czasowych serwisu na wiersze umowy serwisowej i wiersze zlecenia serwisowego w zleceniu serwisowym.

### <a name="create-a-service-agreement"></a>Tworzenie umowy serwisowej

Najpierw należy utworzyć umowę serwisową i ustawić w opcji **Łączenie zleceń serwisowych** wartość **Według umowy serwisowej**.

1. Kliknij opcję **Umowy serwisowe**.
2. W **okienku akcji** na karcie **Umowa serwisowa** w grupie **Nowy** kliknij opcję **Umowa serwisowa**, aby utworzyć nową umowę serwisową.
3. Wprowadź opis, w polu **Identyfikator projektu** zaznacz projekt, a w polu **Data rozpoczęcia** wprowadź datę.
4. W polu **Łączenie zleceń serwisowych** zaznacz opcje **Według umowy serwisowej**.

Utworzona została następująca umowa serwisowa:

| Project      | Rozpoczęcie                                                                         |
|--------------|------------------------------------------------------------------------------------|
| Projekt | Data określona dla projektu. W tym przykładzie jest używana bieżąca data. |

### <a name="create-a-service-agreement-line"></a>Tworzenie wiersza umowy serwisowej

Następnie tworzony jest wiersz umowy serwisowej z typem transakcji **Godzina**.

Aby zakończyć tę część przykładu, należy na stronie **Ramy czasowe serwisów** utworzyć interwał serwisowy wynoszący 10 dni. 

1. Zaznacz umowę serwisową, która właśnie została utworzona. 
2. Na skróconej karcie **Wiersze** kliknij przycisk **Dodaj**, aby utworzyć nowy wiersz w dolnym okienku strony **Umowy serwisowe**.
3. W polu **Typ transakcji** wybierz opcję **Godzina**.
4. W polu **Pracownik** zaznacz pracownika, który wykona prace serwisowe.
5. W polu **Ramy czasowe serwisu** wybierz interwał wynoszący 10 dni.

Został utworzony wiersz umowy serwisowej z następującymi informacjami:

| Typ transakcji | Rozpoczęcie                               | Zakres usług |
|------------------|------------------------------------------|------------------|
| Godzina             | Bieżąca data.                        | Co 10 dni    |
| Pracownik           | Pracownik, który wykona serwis. |                  |

Dla tego wiersza nie zostało określone okno czasu. 

### <a name="create-planned-service-orders"></a>Tworzenie planowanych zleceń serwisowych

Teraz można utworzyć planowane zlecenia serwisowe i wiersze zleceń serwisowych na nadchodzący miesiąc.

1. Na stronie **Umowy serwisowe** w **okienku akcji** na karcie **Dostarcz** kliknij opcję **Planowane zlecenia serwisowe**.
2. Na stronie **Tworzenie zleceń serwisowych** wprowadź bieżącą datę w polu **Od dnia** oraz datę jeden miesiąc w przód od bieżącej daty w polu **Do dnia**.
3. Ustaw suwak **Godzina** na wartość **Tak**. 
4. Kliknij przycisk **OK**.

Ponieważ grupowanie w zleceniu serwisowym nie zostało określone (co umożliwia opcja **Według umowy serwisowej** w polu **Łączenie zleceń serwisowych**), tworzony jest jeden wiersz zlecenia serwisowego na każde zlecenie serwisowe.

### <a name="service-orders-created"></a>Utworzone zlecenia serwisowe

Zostały utworzone trzy wiersze zlecenia serwisowego w ramach czasowych określonych w oknie dialogowym **Tworzenie zleceń serwisowych**. Możesz przejrzeć wiersze zlecenia serwisowego na stronie **Umowy serwisowe** (**okienko akcji** \> karta **Dostarcz** przycisk \>**Widok**).

## <a name="related-topics"></a>Powiązane tematy

[Konfigurowanie ram czasowych serwisu](set-up-service-intervals.md)  


