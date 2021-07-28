---
title: Rejestracja zużycia
description: W tym temacie wyjaśniono, jak utworzyć rejestracje zużycia w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 50ace9a2f8f5fa39dc927e11f0acd707167ef126
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346233"
---
# <a name="register-consumption"></a>Rejestracja zużycia

[!include [banner](../../includes/banner.md)]

 

Po wykonaniu zadania konserwacji w zleceniu produkcyjnym następnym krokiem jest dokonanie rejestracji zużycia i zaksięgowanie arkuszy. Rejestracje można przeprowadzać na następujących typach zużycia: godziny, towary i wydatki. Różne typy zużycia są rejestrowane i księgowane na stronie **arkusze zleceń pracy**. Ustawienia arkusza w module **zarządzanie składnikami majątku** służą do tworzenia i księgowania oddzielnych arkuszy godzin, towarów i wydatków w module **Zarządzanie projektami i ich księgowanie** .

W niektórych przypadkach istnieje możliwość dodawania lub usuwania wierszy prognozy w zleceniu pracy. Konfiguracja stanu cyklu życia zlecenia pracy, powiązanego typu projektu oraz reguł etapów związanych z typem projektu określa, czy można dodawać lub edytować wiersze arkuszy. Aby uzyskać więcej informacji na temat stanów cyklu życia zlecenia pracy i etapów projektu należy zapoznać się z [Prognozy, zlecenia pracy i projekty](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

>[!NOTE]
>Istnieje możliwość skonfigurowania automatycznego księgowania arkuszy w stanie cyklu życia zamówienia pracy. Więcej informacji [Stany cyklu życia zlecenia pracy](../setup-for-work-orders/work-order-lifecycle-states.md).

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy z listy i kliknij przycisk **Arkusze**.

3. Kliknij przycisk **Kopiuj z prognozy**, aby przenieść wiersze prognozy, które mogą być połączone ze zleceniem produkcyjnym. Można wybrać typy zużycia, które mają zostać przeniesione.

4. W razie potrzeby można dodać więcej wierszy zużycia na odpowiednim skróconej karcie, klikając przycisk **Dodaj wiersz** i wypełniając dane w wierszu.

5. Kliknij przycisk **Sprawdź poprawność arkuszy,** aby sprawdzić poprawność wierszy arkusza przed zaksięgowaniem

6. Kliknij przycisk **Księguj arkusze**, aby zaksięgować wiersze arkusza lub arkusz.

7. Po zaksięgowaniu arkuszy zużycia można zaktualizować stan cyklu życia zlecenia pracy. Na przykład, aby wskazać, że zlecenie pracy zostało zrealizowane, można zaktualizować stan cyklu eksploatacji na „zakończone”.

    - W polu **Pokaż** umieszczonym u góry strony **Arkusze zleceń pracy** wybierz wiersze arkusza, które mają być wyświetlane: **wszystkie**, **niezaksięgowane** lub **zaksięgowane**. W zaksięgowanych arkuszach zaznaczone jest pole wyboru **zaksięgowane**.  
    - Jeśli w arkuszu zlecenia produkcyjnego są tworzone wiersze towarów, wymiary produktu i wymiary śledzenia związane z towarem są automatycznie przenoszone do wiersza arkusza.  

Poniższy zrzut ekranu przedstawia przykład rejestracji godzin i towarów w zleceniu produkcyjnym w **arkuszach zleceń roboczych.**

![Rysunek 1.](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a>Dzielenie godzin na zleceniach roboczych z kilkoma zadaniami zlecenia produkcyjnego

Jeśli zlecenie produkcyjne zawiera kilka zadań zlecenia, można zarejestrować godziny pracy za pomocą funkcji **Podziel godziny**, co oznacza, że jeden wiersz rejestracji może być dystrybuowany równomiernie w każdym zleceniu produkcyjnym.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy z listy i kliknij przycisk **Arkusze**.

3. Wybierz wiersz rejestracji godzin, który chcesz podzielić, i kliknij przycisk **Podziel godziny**.

4. W oknie dialogowym **zadania konserwacji dotyczącego podziału godzin w zleceniu pracy** nazwa zalogowanego pracownika jest automatycznie wyświetlana w polu **pracownik**. W razie potrzeby można wybrać innego pracownika.

5. Wybierz kategorię rejestracji godzin w polu **Kategoria**.

6. Umożliwia wstawienie liczby godzin pracy do podziału w polu **Godziny**.

    ![Rysunek 2.](media/02-consumption.png)

7. Kliknij przycisk **OK**.

*Przykład:* w poniższym zrzutie ekranu są wyświetlane wiersze arkusza dla zlecenia produkcyjnego zawierającego trzy zadania zlecenia roboczego. Pierwszy wiersz, zawierający trzy godziny pracy, został podzielony, a jedna godzina robocza jest rejestrowana w każdym zadaniu zlecenia pracy. Po utworzeniu trzech wierszy rejestracji godzin należy zdecydować, co zrobić z oryginalnym wierszem rejestracji godzinowej (pierwszy wiersz w przykładzie). Można ją zachować w stanie lub usunąć. 

![Rysunek 3.](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a>Wymiary finansowe w rejestracjach zużycia

Podczas rejestracji zużycia wymiary finansowe powiązane z różnymi typami rejestracji są dodawane do rejestracji w wybranej kolejności. 

- *Rejestracje godzin i wydatków:* najpierw są dodawane wymiary finansowe z nagłówka arkusza, jeśli takie istnieją. Następnie są dodawane wymiary finansowe z powiązanego projektu zlecenia pracy. Na koniec dodawane są wymiary finansowe od zasobu (pracownika).

- *Rejestracje towarów:* najpierw są dodawane wymiary finansowe z nagłówka arkusza, jeśli takie istnieją. Następnie, są dodawane wymiary finansowe z powiązanego projektu zlecenia pracy. Następnie zostaną dodane wymiary finansowe z oddziału. Na koniec dodawane są wymiary finansowe od towaru.

>[!NOTE]
>Dla wszystkich trzech typów rejestracji kombinacja wymiarów finansowych jest sprawdzana, a niewłaściwe kombinacje są puste. To jest Standardowa konfiguracja z innymi aplikacjami Finance and Operations.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]