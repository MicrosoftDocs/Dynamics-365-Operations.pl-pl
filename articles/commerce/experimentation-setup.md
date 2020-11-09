---
title: Konfigurowanie eksperymentu
description: W tym temacie opisano sposób konfigurowania eksperymentów w usłudze innej firmy.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 29c21ceb4c259f463f4a039942e51141201a9809
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097054"
---
# <a name="set-up-an-experiment"></a>Konfigurowanie eksperymentu

Po [zdefiniowaniu hipotezy i określeniu, jakie metryki sukcesu mają być używane](experimentation-identify.md) należy skonfigurować eksperyment w usłudze innej firmy. Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce. Dodatkowe kroki są zawarte w odrębnych tematach.

[ ![Proces użytkownika eksperymentu — konfiguracja](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Konfigurowanie eksperymentu w usłudze innej firmy
Teraz masz już wybraną usługę innej firmy, aby uruchomić i monitorować eksperyment, a następnie skonfigurować łącznik eksperymentów. Te wymagania wstępne wymieniono w temacie [Eksperymentowanie w systemie Dynamics 365 Commerce](experimentation-overview.md).

Wykonaj kroki wymagane do utworzenia eksperymentu w usłudze innej firmy. Jeśli łącznik jest skonfigurowany prawidłowo, pełna lista eksperymentów skonfigurowanych w ramach usługi innej firmy będzie widoczna w konstruktorze witryn Commerce w ciągu około 5 minut.

## <a name="set-up-your-success-metrics"></a>Konfigurowanie metryk sukcesu
Każdy eksperyment wymaga metryk, aby zmierzyć wpływ tych odmian i sprawdzić poprawność hipotezy. Wykonaj poniższe kroki, aby włączyć obliczanie metryk w usłudze innej firmy przy użyciu zdarzeń aktywnych telemetrii z systemu Dynamics 365 Commerce.

Aby skonfigurować metryki sukcesu, wykonaj następujące kroki.

1. W konstruktorze witryn Commerce wybierz kartę **Strony** w lewym okienku nawigacji, a następnie wybierz stronę, na której mają być zbierane metryki. 
1. Przejdź do sekcji **Identyfikatory zdarzeń do śledzenia** w prawym okienku właściwości strony lub modułu, który chcesz śledzić.
1. Wybierz pozycję **Widok**. Zostanie wyświetlona lista wszystkich identyfikatorów zdarzeń. Skopiuj zdarzenie, które chcesz śledzić, i wklej klucz zdarzenia do wskazanej lokalizacji w usłudze innej firmy. Jeśli potrzebne jest więcej niż jedno zdarzenie, należy skopiować klucze pojedynczo. 
    - Aby dowiedzieć się, jak wyświetlić wszystkie dostępne zdarzenia i atrybuty, w tym widoki stron i śledzenie przychodów, zobacz temat [Zdarzenia składników rozwiązania Commerce używane na potrzeby diagnostyki i rozwiązywania problemów](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).
1. Wykonaj wszelkie inne kroki, aby śledzić metryki zgodnie z wymaganiami usługi innej firmy.

## <a name="previous-step"></a>Poprzedni krok
[Określanie hipotezy i ustalanie metryki eksperymentu](experimentation-identify.md) 


## <a name="next-step"></a>Następne kroki
[Łączenie i edytowanie eksperymentu](experimentation-connect-edit.md)
