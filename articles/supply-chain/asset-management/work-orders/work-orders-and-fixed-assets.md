---
title: Środki trwałe i zlecenia pracy
description: W tym temacie opisano zlecenia pracy i środki trwałe w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 95fe394d22f9fe81511c230a2cf7b8ddf00d896f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250836"
---
# <a name="work-orders-and-fixed-assets"></a>Środki trwałe i zlecenia pracy


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


W module Zarządzanie składnikami majątku, składniki majątku mogą być powiązane ze środkami trwałymi oraz można tworzyć zlecenia pracy dla tych składników. W przypadku korzystania z tej funkcji można zapoznać się z ogólnym przeglądem środków trwałych, powiązanych projektów inwestycyjnych oraz kosztami zarejestrowanymi w projektach inwestycyjnych w module **Zarządzanie projektami i ich księgowanie** oraz w module **Środki trwałe**.

>[!NOTE]
>Pole **Numer środka trwałego** jest wypełniane tylko w projekcie zadania zlecenia pracy, jeśli w projekcie zadania zlecenia pracy jako typ projektu wybrano typ „inwestycja”.

![Rysunek 1](media/24-work-orders.png)

Poniższa procedura opisuje relację między składnikami majątku, zleceniami pracy, projektami zadań zlecenia pracy i środkami trwałymi.

1. Tworzony jest składnik majątku powiązany z środkiem trwałym, co pokazano na poniższym rysunku.

![Rysunek 2](media/25-work-orders.png)

2. Podczas konfigurowania typów zleceń pracy (**Zarządzanie składnikami majątku** > **Konfiguracja** > **Zlecenia pracy** > **Typy zleceń pracy**) tworzony jest typ zlecenia pracy służący do obsługi inwestycji. Zobacz również [Typy zleceń pracy](../setup-for-work-orders/work-order-types.md).

![Rysunek 3](media/26-work-orders.png)

3. Podczas konfigurowania grup projektów zleceń pracy (łącze **Zarządzanie składnikami majątku** > **Konfiguracja** > **Zlecenia pracy** > **Ustawienia projektu** > **Grupa projektów**), tworzy relację między typem zlecenia pracy używanym w inwestycjach a grupą projektów utworzoną dla inwestycji w module **Zarządzanie projektami i ich księgowanie** (**Zarządzanie projektami i ich księgowanie** > **Konfiguracja** > **Księgowanie** > **Grupy projektów**).

![Rysunek 4](media/27-work-orders.png)

4. Podczas tworzenia zlecenia pracy związanego z obiektem środka trwałego należy wybrać typ zlecenia pracy używanego do obsługi inwestycji, na przykład „inwestycja”.

5. Po utworzeniu zlecenia pracy typ powiązanego zlecenia jest pokazywany we **Wszystkie zlecenia pracy**.

![Rysunek 5](media/28-work-orders.png)

6. Po utworzeniu zlecenia pracy projekt powiązany ze zleceniem pracy jest tworzony w **Zarządzanie projektami i ich księgowanie** > **Wszystkie projekty**. Informacje związane z projektem można wyświetlić, klikając łącze **Identyfikator projektu** w zleceniu pracy (w obszarze **Zarządzanie składnikami majątku** otwórz okno zlecenie pracy w Widok szczegółów > skrócona karta **Szczegóły wiersza** > karta  **Ogólne** > pole **Identyfikator projektu**).

![Rysunek 6](media/29-work-orders.png)

7. W module **Środki trwałe** można wyświetlić przegląd projektów związanych z środkiem trwałym (**Środki trwałe** > **Środki trwałe** > **Środki trwałe** > kliknij na środek trwały w polu **Numer środka trwałego** > zobacz zawartość okienka **Informacje pokrewne** > sekcja **Skojarzone projekty**).

