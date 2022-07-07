---
title: Tworzenie zleceń pracy z żądań konserwacji
description: W tym artykule wyjaśniono, jak utworzyć zlecenie pracy z żądania konserwacji w zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb54ec3466086afbd87a023a40e346a6a3464c98
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017182"
---
# <a name="create-work-orders-from-maintenance-requests"></a>Tworzenie zleceń pracy z żądań konserwacji

[!include [banner](../../includes/banner.md)]

 


Po utworzeniu żądań konserwacji można łatwo przekonwertować je na zlecenia pracy. W tym artykule opisano najszybszy sposób pracy z żądaniami konserwacji, aktualizowania kilku żądań konserwacji w tym samym czasie oraz tworzenia zleceń pracy dla kilku żądań konserwacji w tym samym czasie. Na stronie **Aktywne żądania konserwacji** lub **Żądania konserwacji mojej lokalizacji czynności konserwacyjnych** można również pracować z jednym żądaniem konserwacji jednocześnie i przekonwertować jedno żądanie konserwacji na zlecenie pracy.

> [!NOTE]
> Każde żądanie konserwacji może być związane tylko z jednym zleceniem pracy. Wiele żądań konserwacji można jednak umieścić na jednym zleceniu pracy, nawet jeśli żądania konserwacji mają różne składniki majątku.

1. Wybierz **Zarządzanie składnikami majątku** \> **Żądania konserwacji** \> **Wszystkie żądania konserwacji**.
2. Aby można było tworzyć zlecenie pracy z żądań konserwacji, należy wybrać co najmniej typ zadania konserwacji dla żądań konserwacji, a także wariant i rodzaj typu zadania konserwacji, jeśli te informacje są istotne. W widoku siatki można łatwo aktualizować informacje dotyczące żądania konserwacji.
3. Gdy wszystko będzie gotowe do utworzenia zlecenia pracy, wybierz żądania konserwacji do uwzględnienia w nim.

    - Jeśli wybierzesz kilka żądań konserwacji do przekonwertowania na zlecenie pracy, zarówno pole **Składnik majątku** i pole **Typ zadania konserwacji** muszą być ustawione przed utworzeniem zlecenia pracy.
    - Jeśli wybierzesz jedno żądanie konserwacji do przekonwertowania na zlecenie pracy, przed utworzeniem zlecenia pracy należy ustawić tylko pole **Składnik majątku**. Jednak podczas tworzenia zlecenia pracy, można wybrać typ zadania konserwacji (i związane z typem zadania konserwacji wariant i rodzaj, jeśli te informacje są istotne) w oknie dialogowym **Tworzenie zlecenia pracy**.

4. Wybierz **Zlecenie pracy**.
5. W oknie dialogowym **Tworzenie zlecenia pracy** ustaw pola, a następnie wybierz przycisk **OK**.

    Pasek komunikatów może powiadomić, że utworzono nowe zlecenie pracy.

    Ponadto podczas tworzenia zlecenia pracy opartego na żądaniu konserwacji, jeśli składnik majątku, który jest powiązany z żądaniem konserwacji znajduje się w umowie gwarancyjnej, pasek komunikatów powiadamia użytkownika o umowie gwarancyjnej.

6. Wybierz **Zarządzanie składnikami majątku** \> **Zlecenia pracy** \> **Wszystkie zlecenia pracy** i otwórz nowe zlecenie pracy.

    ![Otwieranie nowego zlecenia pracy.](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]