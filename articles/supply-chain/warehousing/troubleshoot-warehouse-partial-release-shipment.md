---
title: Rozwiązywanie problemów dotyczących częściowych zwolnień i częściowej wysyłki
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z częściowymi wydaniami i częściowymi wysyłkami w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5534099f81a97a1dcf4908784fd71dd03cf94eaf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828161"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]