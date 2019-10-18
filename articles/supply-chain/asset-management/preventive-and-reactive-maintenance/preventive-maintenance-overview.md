---
title: Omówienie konserwacji zapobiegawczej
description: W tym temacie wyjaśniono konserwację zapobiegawczą w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
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
ms.openlocfilehash: 02ea3affca727802b241f87b801e0742ac0aa41a
ms.sourcegitcommit: 6476f27c8d3dced7c2e9a7344a4e378b51a1983e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2019
ms.locfileid: "1922098"
---
# <a name="preventive-maintenance-overview"></a>Omówienie konserwacji zapobiegawczej

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W tym temacie wyjaśniono konserwację zapobiegawczą w module Zarządzanie składnikami majątku. Konserwacja zapobiegawcza to dyscyplina obejmująca planowane zadania konserwacyjne, na przykład regularne przeglądy, kalibrację i inspekcje. W module **Zarządzanie składnikami majątku** można tworzyć plany konserwacji i konfigurować je w aktywach i lokalizacjach czynności konserwacji. Można również ustawić serie czynności konserwacyjnych na czynnościach konserwacyjnych. Plany konserwacji dotyczące składników majątku są aktywne niezależnie od tego, gdzie jest zainstalowany składnik majątku. Plany konserwacji i serie czynności konserwacyjnych w lokalizacji czynności konserwacyjnych są aktywne dla składników majątku aktualnie zainstalowanych w danej lokalizacji. Zamiast konfigurować plany konserwacji dla składników majatku lub konfigurować serie w lokalizacjach czynności konserwacyjnych, można utworzyć serie czynności konserwacyjnych obejmujące wiele składników majątku, dla których należy wykonać powiązane typy zadań konserwacyjnych w tej samej procedurze pracy. Serie czynności konserwacyjnych stworzone ze składników majątki - zamiast stowrzone z lokalizacji czynności konserwacyjnych — oznacza, że można wybrać pewną liczbę składników majątku dla jednej serii czynności konserwacyjnych, które nie są zainstalowane w tej samej lokalizacji czynności konserwacyjnych.

Plany konserwacji są używane do obsługi prewencyjnej i aktywnej konserwacji poszczególnych składników majątku. Serie czynności konserwacyjnych są używane do obsługi profilaktycznej grupy lub zbioru składników majątku. Plany konserwacji i serie czynności konserwacyjnych służą do generowania propozycji zleceń pracy. Propozycje zleceń pracy są zapisywane jako wiersze harmonogramu konserwacji, które można powiązać i przekształcić w zlecenia pracy.

Poniższa ilustracja przedstawia przepływ pracy, tworząc plany konserwacji i serie czynności konserwacyjnych w celu utworzenia zleceń pracy dla składników majątku na podstawie tych planów konserwacji i serii czynności konserwacyjnych.

![Rysunek 1](media/01-preventive-maintenance.png)

