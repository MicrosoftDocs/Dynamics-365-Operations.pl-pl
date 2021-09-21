---
title: Stan zamówienia pozostaje Częściowo zwolniony po zafakturowaniu
description: W niektórych przypadkach stan zwolnienia zamówienia sprzedaży pozostaje jako Częściowo zwolnione nawet po zafakturowaniu zamówienia. Na tej stronie wyjaśniono przyczynę i możliwe obejście.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8bfe7ecfd4beb6e77e8dd1e23ccd896d067bdb51
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477318"
---
# <a name="order-status-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>Stan zamówienia pozostaje Częściowo zwolniony nawet po zafakturowaniu zamówienia sprzedaży

## <a name="symptoms"></a>Objawy

Zamówienie sprzedaży jest zleceniem dostawy, ale jeden lub więcej towarów ma inną metodę dostawy. Po zafakturowaniu zamówienia stan zlecenia nadal jest *Częściowo zwolnione*.

Na przykład zamówienie sprzedaży zawiera dwa elementy: jeden do dostawy i jeden do odbioru. Dostawa i odbiór zostały zrealizowane. Z tego powodu oba wiersze zostały zafakturowane. Jednak stan zwolnienia jest nadal pokazywany jako *Częściowo zwolniony*, co jest mylące.

## <a name="workaround"></a>Obejście

Stan wydania dotyczy tylko wierszy zamówień, w których towary są włączone dla zarządzania magazynem. W związku z tym stan zwolnienia pozostanie *Częściowo zwolniony* w tym scenariuszu. Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji. Rozszerzenie może zostać dodane jako część procesu dokumentu dostawy i fakturowania w celu zaktualizowania stanu wydania.
