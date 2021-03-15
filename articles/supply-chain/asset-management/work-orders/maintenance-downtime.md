---
title: Przerwa konserwacyjną dla zleceń pracy
description: Ten temat wyjaśnia, jak można utworzyć rejestracje przestojów podczas obsługi dla środka trwałego wybranego w zleceniu pracy.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 53487a0173453ef7a8f5ea818672d999fe71cb65
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020918"
---
# <a name="maintenance-downtime-for-work-orders"></a>Przerwa konserwacyjną dla zleceń pracy

[!include [banner](../../includes/banner.md)]


Można utworzyć rejestracje przestojów podczas obsługi dla środka trwałego wybranego w zleceniu pracy. Ta możliwość jest przydatna w przypadku rejestrowania przerw konserwacyjnych na co najmniej jednej maszynie w obszarze produkcji. Najpierw należy utworzyć kody przyczyn przerw konserwacyjnych, które mają być używane, na przykład **Awaria** i **Planowane zatrzymywanie**. W tym celu należy wykonać czynności ze strony **Kody przyczyn przerw konserwacyjnych**. Następnie można utworzyć rejestracje przerw konserwacyjnych na stronie **Przerwa konserwacyjna** i dodać odpowiednie kody przyczyn przerw konserwacyjnych.

## <a name="create-maintenance-downtime-reason-codes"></a>Stwórz kody przyczyny przerwy konserwacyjnej

1. Wybierz **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Kody przyczyny przerwy konserwacyjnej**.

2. Wybierz pozycję **Nowy**.

3. W polu **Kod przyczyny przerwy konserwacyjnej** wprowadź identyfikator dla kodu przyczyny przerwy konserwacyjnej.

4. W polu **Nazwa** wprowadź nazwę.

5. Zaznacz pole wyboru **KPI uwzględniają**, jeśli kod przyczyny ma być uwzględniony w obliczeniach kluczowych wskaźników wydajności (KPI) dla składnika majątku. Na ogół planowane zatrzymania produkcji nie powinny być uwzględniane w obliczeniach wskaźników KPI, ponieważ nie wpływają one na oczekiwaną wydajność.

6. Wybierz opcję **Zapisz**.

Na poniższej ilustracji pokazano przykład strony **Kody przyczyny przerwy konserwacyjnej**.

![Rysunek 1](media/15-work-orders.png)

Po utworzeniu kodów przyczyny przestojów, które mają być używane, można utworzyć rejestracje przestojów związanych z obsługą zleceń i składników majątku.


## <a name="create-maintenance-downtime-registrations"></a>Utwórz rejestrację przestojów konserwacyjnych

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie produkcyjne, a następnie na karcie **Zlecenie pracy**, w grupie **Składnik majątku** wybierz pozycję **Przerwa konserwacyjna**.

3. Wybierz pozycję **Nowy**.

4. W polach **Od** i **Do** wstaw datę i interwał czasu dla rejestracji przerw konserwacyjnych.

>[!NOTE]
>Po opuszczeniu pola **do** pole czas trwania w godzinach jest automatycznie wstawiany w polu **Czas trwania**.

5. Wybierz kod przyczyny w polu **Kod przyczyny przerwy konserwacyjnej**.

6. Powtórz kroki od 3 do 5, aby dodać więcej rejestracji.

7. Wybierz opcję **Zapisz**.

Na poniższej ilustracji pokazano przykład rejestracji przerwy konserwacyjnej.

![Rysunek 2](media/16-work-orders.png)

Kalendarz używany do obliczania rejestracji przerw konserwacyjnych związanych z obsługą zależy od wyboru dokonanego w konfiguracji składników majątku i parametrów. Jeśli zasób jest wybrany dla składnika majątku w polu **Zasób**, na karcie skróconej **Środek trwały** na stronie **Wszystkie składniki majątku** zostanie użyty kalendarz skonfigurowany dla skojarzonej grupy zasobów, co pokazano na poniższym rysunku.

![Rysunek 3](media/17-work-orders.png)

Jeśli składnik majątku nie jest powiązany z zasobem, zostanie użyty standardowy kalendarz wybrany na stronie **Parametry zarządzania składnikami majątku** jak pokazano na ilustracji poniżej.

![Rysunek 4](media/18-work-orders.png)

Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Przerwa konserwacyjna** , aby wyświetlić przegląd wszystkich rejestracji przerw konserwacyjnych.

>[!NOTE]
>Wszystkie kalendarze używane w module **Zarządzanie składnikami majątku** są konfigurowane w **Administrowanie organizacją** > **Ustawienia** > **Kalendarze** > **Kalendarze**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]