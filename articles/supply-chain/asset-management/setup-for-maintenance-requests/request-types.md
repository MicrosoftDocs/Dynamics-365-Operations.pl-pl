---
title: Typy żądania konserwacji
description: W tym temacie wyjaśniono, jak konfigurować typu żądań konserwacji w Zarządzaniu składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 07/26/2019
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
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19d529df6c8aab036de59502b4f14101e1a07707
ms.sourcegitcommit: 2c73749779274e0b0abbcb4041bbc1df0fb6d6e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/26/2019
ms.locfileid: "1790529"
---
# <a name="maintenance-request-types"></a>Typy żądania konserwacji

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Typy żądań konserwacji służą do klasyfikowania żądań konserwacji. Na przykład mogą istnieć typy żądań konserwacji, które są związane z konserwacją prewencyjną i naprawczą. Można również mieć specjalny typ żądania konserwacji służący do zarządzania naprawą składnikami majątku (naprawa w magazynie).

Typ żądania konserwacji określa przynależność do grupy stanów cyklu życia żądania konserwacji (model cyklu życia konserwacji). Modele cyklu życia żądania konserwacji definiują stany cyklu życia, które można skonfigurować dla żądania konserwacji. (Przykłady stanów cyklu życia żądania konserwacji obejmują **Utworzony**, **Aktywny** i **Zakończony**).

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Żądania konserwacji** \> **Typy żądań konserwacji**.
2. Wybierz pozycję **Nowy**, aby utworzyć typ żądania konserwacji.
3. W polu **Typ żądania konserwacji** wprowadź identyfikator typu żądania konserwacji.
4. W polu **Nazwa** wprowadź nazwę.
5. Na skróconej karcie **Ogólne** w polu **Model cyklu życia żądania konserwacji** wybierz model cyklu życia żądania konserwacji.
6. W polu **Typ zlecenia pracy** wybierz typ zlecenia pracy. Gdy żądanie konserwacji jest konwertowane na zlecenie pracy, zlecenie pracy automatycznie otrzymuje typ zlecenia pracy powiązany z typem żądania konserwacji.

Na poniższej ilustracji pokazano przykład strony **Typy żądań konserwacji**.

![Rysunek 1](media/07-setup-for-requests.png)
