---
title: Rezygnacja ze zbierania zdarzeń aktywności internetowej
description: W tym temacie wyjaśniono, jak można pozwolić osobom odwiedzającym witrynę internetową na zbieranie zdarzeń aktywności internetowej w aplikacji Microsoft Dynamics 365 Commerce.
author: aamiral
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 25464c89352f44a77a96dee6ad2f633b7a55669e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350287"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Rezygnacja ze zbierania zdarzeń działania sieci Web
[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono, jak można pozwolić klientom zrezygnować ze zbierania zdarzeń aktywności internetowej w aplikacji Microsoft Dynamics 365 Commerce.

Aplikacja Dynamics 365 Commerce umożliwia administratorzy witryn analizować aktywność internetową użytkowników swoich witryn handlu elektronicznego. Dzięki temu mogą oni lepiej zrozumieć, w jaki sposób są używane ich witryny, a także zoptymalizować witryny, aby zwiększyć komfort pracy użytkownika i osiągnąć cele biznesowe.


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a>Sposoby zaimplementowania rezygnacji z usługi przez administratorów

Administratorom udostępniono trzy sposoby zaimplementowania rezygnacji z usługi.

### <a name="opt-out-on-behalf-of-users"></a>Rezygnacja w imieniu użytkowników

W przypadku zarządzania kontami w module Commerce Headquarters administratorzy mogą zrezygnować w imieniu użytkowników.

1. W kliencie HQ na stronie **Wszyscy odbiorcy** wyszukaj i wybierz odbiorcę.
1. Na stronie szczegółów odbiorcy na skróconej karcie **Retail** sekcji **Prywatność** ustaw opcję **Nie śledź aktywności internetowej** na wartość **Tak**.

    ![Ustawienia prywatności.](media/Disablepersonalizationpart2.png)

1. Wybierz przycisk **Zapisz** i zamknij stronę.

### <a name="module-based-opt-out-experience"></a>Oparta na module usługa rezygnacji

Administratorzy mogą zezwolić uwierzytelnionym użytkownikom na samodzielną rezygnację z zbierania zdarzeń aktywności internetowej. Aby określić to działanie, należy dodać moduł rezygnacji przez użytkownika do stron profilu konta odbiorcy.

### <a name="custom-extensions"></a>Rozszerzenia niestandardowe

Administratorzy mogą tworzyć własne rozszerzenia służące do zarządzania niektórymi usługami rezygnacji użytkowników. Aby uzyskać więcej informacji, zobacz [Wywoływanie interfejsów API w usłudze Retail Server](e-commerce-extensibility/call-retail-server-apis.md) i [rozszerzalność kanału online](e-commerce-extensibility/overview.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
