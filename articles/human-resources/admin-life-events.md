---
title: Ustawianie praw administratora dla zdarzeń życia
description: W tym artykule wyjaśniono, jak skonfigurować uprawnienia administratora dla zdarzeń z życia w Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9deed240977394667cee8b107397267b182d960b
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229913"
---
# <a name="set-administrator-rights-for-life-events"></a>Ustawianie praw administratora dla zdarzeń życia

[!include [banner](../includes/preview-banner.md)]

Administratorzy mogą aktualizować opcje zdarzenia życia, w zależności od ustawień konfiguracji. Na stronie **Parametry zasobów ludzkich** można skonfigurować parametry umożliwiające administratorom zmiany wybranych planów. Można także w pełni ograniczyć możliwość tworzenia zmian przez administratorów.

Na stronie **Parametry zasobów ludzkich** można skonfigurować ograniczenia zmian planu dla potwierdzonych planów i opcji zdarzeń życia.

Jeśli jest **wybrana opcja** Potwierdzone plany, zmiany można wprowadzać tylko w przypadku, gdy okres rejestracji jest aktywny. (Do okresów rejestracji należą na przykład otwarte okresy rejestracji, okresy rejestracji nowych pracowników i okresy rejestracji zdarzeń życia) Jeśli ta opcja nie jest zaznaczona, zmiany można wprowadzać w dowolnym momencie.

Jeśli wybrano opcję **Opcje zdarzeń z życia**, zmiany planu podczas zdarzenia z życia są ograniczone przez opcje zdarzeń z życia, które są zdefiniowane w typie planu. Jeśli ta opcja nie jest zaznaczona, wybór planu można zmienić podczas zdarzenia życia.

## <a name="set-plan-change-restrictions"></a>Ustaw ograniczenia zmiany planu

Na stronie **Parametry zasobów ludzkich**, na karcie **Zarządzanie świadczeniami** są dostępne następujące pola.

| Pole | Opis |
|-------|-------------|
| Potwierdzone plany | Tę opcję należy wybrać, jeśli zmiany planu są dozwolone tylko wtedy, gdy okres rejestracji jest aktywny. Jeśli ta opcja nie jest zaznaczona, zmiany można wprowadzać w dowolnym momencie. |
| Opcje zdarzenia zmiany sytuacji życiowej | Wybierz tę opcję, jeśli zmiany planu podczas zdarzenia z życia są ograniczone przez opcje zdarzenia z życia zdefiniowane w typie planu. Jeśli ta opcja nie jest zaznaczona, wybór planu można zmienić podczas zdarzenia życia. |
