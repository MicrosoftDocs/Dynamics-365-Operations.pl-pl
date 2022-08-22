---
title: Rezygnacja ze zbierania zdarzeń działania sieci Web
description: W tym artykule wyjaśniono, jak można pozwolić osobom odwiedzającym witrynę internetową na zbieranie zdarzeń aktywności internetowej w aplikacji Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: 81343f5033366484140f73fcc313ecd9f35e7d47
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286733"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Rezygnacja ze zbierania zdarzeń działania sieci Web
[!include [banner](includes/banner.md)]

W tym artykule wyjaśniono, jak można pozwolić klientom zrezygnować ze zbierania zdarzeń aktywności internetowej w aplikacji Microsoft Dynamics 365 Commerce.

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
