---
title: Rozwiązywanie problemów dotyczących częściowych zwolnień i częściowej wysyłki
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z częściowymi wydaniami i częściowymi wysyłkami w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e89a430f90374733b23fadaf53f5bab598d67d62
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645955"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a>Rozwiązywanie problemów dotyczących częściowych zwolnień i częściowej wysyłki

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z częściowymi wydaniami i częściowymi wysyłkami w Microsoft Dynamics 365 Supply Chain Management.

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>Status zwolnienia zamówienia sprzedaży pozostaje częściowo zwolniony nawet po zafakturowaniu zamówienia sprzedaży.

### <a name="issue-description"></a>Opis problemu

Zamówienie sprzedaży jest zleceniem dostawy, ale jeden lub więcej towarów ma inną metodę dostawy. Po zafakturowaniu zamówienia stan zlecenia nadal jest *Częściowo zwolnione*.

Na przykład zamówienie sprzedaży zawiera dwa elementy: jeden do dostawy i jeden do odbioru. Dostawa i odbiór zostały zrealizowane. Z tego powodu oba wiersze zostały zafakturowane. Jednak stan zwolnienia jest nadal pokazywany jako *Częściowo zwolniony*, co jest mylące.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Stan wydania dotyczy tylko wierszy zamówień, w których towary są włączone dla zarządzania magazynem. W związku z tym stan zwolnienia pozostanie *Częściowo zwolniony* w tym scenariuszu. Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji. Rozszerzenie może zostać dodane jako część procesu dokumentu dostawy i fakturowania w celu zaktualizowania stanu wydania.
