---
title: Wysyłanie zlecenia pracy
description: W tym temacie opisano wysyłanie zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3b1621cf0f1e47d7bd5fe2fa0b41fbcd61f14def
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887212"
---
# <a name="dispatch-work-order"></a>Wysyłanie zlecenia pracy

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Istnieje możliwość zaplanowania jednego zadania zlecenia pracy lub zlecenia pracy dla jednego pracownika korzystającego z funkcji **wysyłki**.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy z listy.

3. Na karcie **Ogólne** kliknij przycisk **Wysyłanie**.

4. W oknie dialogowym **Zaplanuj zlecenie pracy**, wybierz pracownika w polu **pracownik**.

5. W polu **Planowanie godzinowe** można wstawiać oczekiwane godziny pracy w przypadku, gdy oczekiwane godziny pracy różnią się od godzin prognozowanych.

6. W polu **planowane rozpoczęcie** można edytować datę i godzinę rozpoczęcia, jeśli jest to wymagane.

7. Jeśli proces planowania powinien uwzględniać ograniczenia zdolności produkcyjnych dotyczące zasobów, które są już zaplanowane dla innych zadań, należy upewnić się, że przyciski przełączania **Składnik majątku**, **Narzędzie** i **Pracownik** są ustawione na wartość „Tak”. Aby wyświetlić szczegółowe informacje o procesie planowania, wybierz wartość „Tak” w przycisku przełączania **Pełne**. Oznacza to, że w dzienniku informacyjnym zostaną wyświetlone szczegółowe informacje o obliczonych wynikach zlecenia pracy.

8. Wybierz wartość tak na przycisku **Ignoruj harmonogram**, aby zignorować dni zamknięte w kalendarzu (dotyczy składnika aktywów, pracownika i narzędzi). Wybierz wartość „tak” na **Ignoruj zaplanowane wykonywanie** w celu zignorowania ograniczeń, które mogły zostać wybrane w zleceniu pracy w zakresie planowania. Odnieś się do sekcji [Zaplanowane wykonanie](../setup-for-work-orders/scheduled-execution.md), aby dowiedzieć się więcej o konfiguracji zaplanowanego wykonania.

9. Kliknij przycisk **OK**. Stan cyklu życia zlecenia pracy jest automatycznie aktualizowany do stanu cyklu życia "Zaplanowane" określonego w **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Modele cyklu życia**.

Na poniższym rysunku pokazano przykładowe opcje wysyłki w oknie dialogowym **Zaplanuj zlecenie pracy**.

![Rysunek 1](media/04-work-order-scheduling.png)

>[!NOTE]
>Aby usunąć harmonogram w zleceniu pracy, należy to zrobić, zaznaczając zlecenie pracy w **Wszystkie zlecenia pracy** i klikając przycisk **Usuń harmonogram** na karcie **Ogólne**. Pamiętaj, aby ręcznie zaktualizować stan cyklu życia zlecenia pracy w przypadku usunięcia harmonogramu.

