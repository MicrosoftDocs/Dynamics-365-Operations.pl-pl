---
title: W systemie nie można odnaleźć planowanego zamówienia podczas wykonywania operacji na wielu zamówieniach
description: Błąd „Planowane zamówienie nie istnieje” występuje, gdy wykonujesz operacje na wielu planowanych zamówieniach, a co najmniej dwa zamówienia należą do tego samego identyfikatora towaru.
author: t-benebo
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo_ReqTransPoMarkChangeType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ece4a331b63b86e896c5b337a58185ed3ea1049
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920811"
---
# <a name="the-system-cant-find-a-planned-order-during-operations-on-multiple-orders"></a>W systemie nie można odnaleźć planowanego zamówienia podczas wykonywania operacji na wielu zamówieniach

Kod błędu: SYS24774

## <a name="symptoms"></a>Objawy

Podczas próby wykonania operacji jednocześnie na wielu planowanych zamówieniach jest wyświetlany poniższy komunikat o błędzie, a co najmniej dwa zamówienia należą do tego samego identyfikatora towaru. Na przykład ten błąd może wystąpić, gdy zamówienia zostaną ustalone albo ich typ zostanie zmieniony.

> Zamówienie planowane %1 nie istnieje.

## <a name="cause"></a>Powód

Gdy system ustali zamówienie lub zmieni typ zamówienia, musi ponownie sprawdzić istniejące planowane zamówienia towaru, aby upewnić się, że planowana dostawa odpowiada zapotrzebowaniu i istniejącej dostawie. W ramach tego procesu system ponownie tworzy planowane zamówienia towaru. W związku z tym drugie planowane zamówienie, które system chce przetworzyć, już nie istnieje.

## <a name="workaround"></a>Obejście

Zatwierdź zamówienia przed przetworzeniem ich. Dzięki temu zamówienia nie będą usuwane, gdy system przetworzy pierwsze zamówienie towaru.
