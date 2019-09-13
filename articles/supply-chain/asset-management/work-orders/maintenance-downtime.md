---
title: Przerwa konserwacyjna
description: W tym temacie opisano przerwy konserwacyjne w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918251"
---
# <a name="maintenance-downtime"></a>Przerwa konserwacyjna


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Można utworzyć rejestracje przestojów podczas obsługi dla środka trwałego wybranego w zleceniu pracy. Jest to przydatne w przypadku rejestrowania przestojów konserwacyjnych na co najmniej jednej maszynie w obszarze produkcji. Najpierw należy utworzyć kody przyczyn przestojów, które mają być używane, na przykład podział i planowany zatrzymywanie. W tym celu należy wykonać czynności związane z **kodami przyczyn przerw konserwacyjnych**. Następnie można utworzyć rejestracje **Przerw konserwacyjnych** i dodać odpowiednie kody przyczyn.

## <a name="create-maintenance-downtime-reason-codes"></a>Stwórz kody przyczyny przerwy konserwacyjnej

1. Kliknij **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Kody przyczyny przerwy konserwacyjnej**.

2. Kliknij przycisk **Nowy**.

3. Wstaw identyfikator w polu kod **Kod przyczyny przerwy konserwacyjnej**.

4. Wstaw nazwę kodu przyczyny w polu **Nazwa**.

5. Zaznacz pole **KPI uwzględniają**, jeśli kod przyczyny ma być uwzględniony w obliczeniach wskaźnika KPI składnika aktywów. Na ogół planowane zatrzymania produkcji nie powinny być uwzględniane w obliczeniach wskaźników KPI, ponieważ nie wpływają one na oczekiwaną wydajność.

6. Kliknij przycisk **Zapisz**.

![Rysunek 1](media/15-work-orders.png)


Po utworzeniu kodów przyczyny przestojów, które mają być używane, można utworzyć rejestracje przestojów związanych z obsługą zleceń i składników majątku.


## <a name="create-maintenance-downtime-registrations"></a>Utwórz rejestrację przestojów konserwacyjnych

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy z listy i kliknij przycisk **Przerwa konserwacyjna.**

3. Kliknij przycisk **Nowy**.

4. Umożliwia wstawienie daty i interwału czasu dla rejestracji przerw konserwacyjnych w polach **Od** i **Do**.

5. Po opuszczeniu pola **do** pole czas trwania w godzinach jest automatycznie wstawiany w polu **Czas trwania**.

6. Wstaw kod przyczyny w polu **Kod przyczyny przerwy konserwacyjnej**.

7. Jeśli chcesz dodać więcej rejestracji, powtórz kroki 3-6

8. Kliknij przycisk **Zapisz**.


![Rysunek 2](media/16-work-orders.png)


Kalendarz używany do obliczania rejestracji przestojów związanych z obsługą zależy od wyboru dokonanego w konfiguracji środków trwałych i parametrów. Jeśli zasób jest wybrany dla składnika majątku **Wszystkie składniki majątku** > **Środek trwały** karta skrócona > **Zasób**, zostanie użyty kalendarz skonfigurowany dla skojarzonej grupy zasobów, co pokazano na poniższym rysunku.

![Rysunek 3](media/17-work-orders.png)


Jeśli składnik majątku nie jest powiązany z zasobem, zostanie użyty standardowy kalendarz wybrany w polu **Parametry zarządzania składnikami majątku** jak pokazano poniżej.

![Rysunek 4](media/18-work-orders.png)


Kliknij **Ustawień zarządzania składnikami majątku** > **Zapytania** > **Przerwa konserwacyjna** , aby wyświetlić przegląd wszystkich rejestracji przestojów związanych z konserwacją.

>[!NOTE]
>Wszystkie kalendarze używane w module **Zarządzanie składnikami majątku** są konfigurowane w **Administrowanie organizacją** > **Ustawienia** > **Kalendarze** > **Kalendarze**.

