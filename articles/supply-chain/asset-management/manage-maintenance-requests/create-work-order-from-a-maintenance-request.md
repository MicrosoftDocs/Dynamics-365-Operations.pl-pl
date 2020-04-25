---
title: Tworzenie zleceń pracy z żądań konserwacji
description: W tym temacie wyjaśniono, jak utworzyć zlecenie pracy z żądania konserwacji w zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b6bd98796140ab7aa3e7813ff1526413504554c5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205214"
---
# <a name="create-work-orders-from-maintenance-requests"></a>Tworzenie zleceń pracy z żądań konserwacji

[!include [banner](../../includes/banner.md)]

 


Po utworzeniu żądań konserwacji można łatwo przekonwertować je na zlecenia pracy. W tym temacie opisano najszybszy sposób pracy z żądaniami konserwacji, aktualizowania kilku żądań konserwacji w tym samym czasie oraz tworzenia zleceń pracy dla kilku żądań konserwacji w tym samym czasie. Na stronie **Aktywne żądania konserwacji** lub **Żądania konserwacji mojej lokalizacji czynności konserwacyjnych** można również pracować z jednym żądaniem konserwacji jednocześnie i przekonwertować jedno żądanie konserwacji na zlecenie pracy.

> [!NOTE]
> Każde żądanie konserwacji może być związane tylko z jednym zleceniem pracy. Wiele żądań konserwacji można jednak umieścić na jednym zleceniu pracy, nawet jeśli żądania konserwacji mają różne składniki majątku.

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **żądania konserwacji** \> **Wszystkie żądania konserwacji**.
2. Aby można było tworzyć zlecenie pracy z żądań konserwacji, należy wybrać co najmniej typ zadania konserwacji dla żądań konserwacji, a także wariant i rodzaj typu zadania konserwacji, jeśli te informacje są istotne. W widoku siatki można łatwo aktualizować informacje dotyczące żądania konserwacji.
3. Gdy wszystko będzie gotowe do utworzenia zlecenia pracy, wybierz żądania konserwacji do uwzględnienia w nim.

    - Jeśli wybierzesz kilka żądań konserwacji do przekonwertowania na zlecenie pracy, zarówno pole **Składnik majątku** i pole **Typ zadania konserwacji** muszą być ustawione przed utworzeniem zlecenia pracy.
    - Jeśli wybierzesz jedno żądanie konserwacji do przekonwertowania na zlecenie pracy, przed utworzeniem zlecenia pracy należy ustawić tylko pole **Składnik majątku**. Jednak podczas tworzenia zlecenia pracy, można wybrać typ zadania konserwacji (i związane z typem zadania konserwacji wariant i rodzaj, jeśli te informacje są istotne) w oknie dialogowym **Tworzenie zlecenia pracy**.

4. Wybierz **Zlecenie pracy**.
5. W oknie dialogowym **Tworzenie zlecenia pracy** ustaw pola, a następnie wybierz przycisk **OK**.

    Pasek komunikatów może powiadomić, że utworzono nowe zlecenie pracy.

    Ponadto podczas tworzenia zlecenia pracy opartego na żądaniu konserwacji, jeśli składnik majątku, który jest powiązany z żądaniem konserwacji znajduje się w umowie gwarancyjnej, pasek komunikatów powiadamia użytkownika o umowie gwarancyjnej.

6. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Zlecenia pracy** \> **Wszystkie zlecenia pracy** i otwórz nowe zlecenie pracy.

    ![Otwieranie nowego zlecenia pracy](media/05-manage-maintenance-requests.png)

