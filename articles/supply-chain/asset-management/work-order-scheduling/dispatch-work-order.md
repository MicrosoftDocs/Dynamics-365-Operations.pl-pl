---
title: Wysyłanie zlecenia pracy
description: W tym temacie opisano wysyłanie zleceń pracy w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 344f015b5d2de45e3eca1eb8c0f3b1676da945d2
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354163"
---
# <a name="dispatch-work-order"></a>Wysyłanie zlecenia pracy

[!include [banner](../../includes/banner.md)]

 

Istnieje możliwość zaplanowania jednego zadania zlecenia pracy lub zlecenia pracy dla jednego pracownika korzystającego z funkcji **wysyłki**.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy z listy.

3. Na karcie **Ogólne** kliknij przycisk **Wysyłanie**.

4. W oknie dialogowym **Zaplanuj zlecenie pracy** wybierz pracownika w polu **Pracownik**.

5. W polu **Planowanie godzinowe** można wstawiać oczekiwane godziny pracy w przypadku, gdy oczekiwane godziny pracy różnią się od godzin prognozowanych.

6. W polu **planowane rozpoczęcie** można edytować datę i godzinę rozpoczęcia, jeśli jest to wymagane.

7. Jeśli proces planowania powinien uwzględniać ograniczenia zdolności produkcyjnych dotyczące zasobów, które są już zaplanowane dla innych zadań, należy upewnić się, że przyciski przełączania **Składnik majątku**, **Narzędzie** i **Pracownik** zostały ustawione na wartość **Tak**. Aby wyświetlić szczegółowe informacje o procesie planowania, wybierz wartość **Tak** w przycisku przełączania **Pełne**. Oznacza to, że w dzienniku informacyjnym zostaną wyświetlone szczegółowe informacje o obliczonych wynikach zlecenia pracy.

8. Wybierz wartość **Tak** na przycisku przełącznika **Ignoruj harmonogram**, aby zignorować dni zamknięte w kalendarzu (dotyczy składnika majątku, pracownika i narzędzi). Wybierz wartość **Tak** na przycisku przełącznika **Ignoruj zaplanowane wykonanie** w celu zignorowania ograniczeń, które mogły zostać wybrane w zleceniu pracy wymagającym planowania. 

    Aby dowiedzieć się więcej o konfiguracji zaplanowanego wykonania, zobacz sekcję [Zaplanowane wykonanie](../setup-for-work-orders/scheduled-execution.md).

9. Kliknij przycisk **OK**. Stan cyklu życia zlecenia pracy jest automatycznie aktualizowany do stanu cyklu życia **Zaplanowane** określonego w obszarze **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Modele cyklu życia**.

Na poniższym rysunku pokazano przykładowe opcje wysyłki w oknie dialogowym **Zaplanuj zlecenie pracy**.

![Rysunek 1.](media/04-work-order-scheduling.png)

[!NOTE]
Aby usunąć harmonogram w zleceniu pracy, wybierz zlecenie pracy w obszarze **Wszystkie zlecenia pracy** i kliknij pozycję **Usuń harmonogram** na karcie **Ogólne**. Pamiętaj, aby ręcznie zaktualizować stan cyklu życia zlecenia pracy w przypadku usuwania harmonogramu.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]