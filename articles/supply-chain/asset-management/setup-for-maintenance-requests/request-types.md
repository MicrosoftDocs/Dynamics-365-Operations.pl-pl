---
title: Typy żądania konserwacji
description: W tym artykule wyjaśniono, jak konfigurować typu żądań konserwacji w Zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 07/26/2019
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
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a2d707cc9c0aa4863968651a8434883cc1322eb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888709"
---
# <a name="maintenance-request-types"></a>Typy żądania konserwacji

[!include [banner](../../includes/banner.md)]

 

Typy żądań konserwacji służą do klasyfikowania żądań konserwacji. Na przykład mogą istnieć typy żądań konserwacji, które są związane z konserwacją prewencyjną i naprawczą. Można również mieć specjalny typ żądania konserwacji służący do zarządzania naprawą składnikami majątku (naprawa w magazynie).

Typ żądania konserwacji określa przynależność do grupy stanów cyklu życia żądania konserwacji (model cyklu życia konserwacji). Modele cyklu życia żądania konserwacji definiują stany cyklu życia, które można skonfigurować dla żądania konserwacji. (Przykłady stanów cyklu życia żądania konserwacji obejmują **Utworzony**, **Aktywny** i **Zakończony**).

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Żądania konserwacji** \> **Typy żądań konserwacji**.
2. Wybierz pozycję **Nowy**, aby utworzyć typ żądania konserwacji.
3. W polu **Typ żądania konserwacji** wprowadź identyfikator typu żądania konserwacji.
4. W polu **Nazwa** wprowadź nazwę.
5. Na skróconej karcie **Ogólne** w polu **Model cyklu życia żądania konserwacji** wybierz model cyklu życia żądania konserwacji.
6. W polu **Typ zlecenia pracy** wybierz typ zlecenia pracy. Gdy żądanie konserwacji jest konwertowane na zlecenie pracy, zlecenie pracy automatycznie otrzymuje typ zlecenia pracy powiązany z typem żądania konserwacji.

Na poniższej ilustracji pokazano przykład strony **Typy żądań konserwacji**.

![Strona Typy żądania konserwacji.](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]