---
title: Okienko filtru na stronie Lista dostępnych nie działa zgodnie z oczekiwaniami
description: Filtry w okienku filtrów na stronie „Lista dostępnych” nie filtrują wyników w oczekiwany sposób.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 2b2b233e22378c8710a63dce83d168bfd89eba7f
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920505"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Okienko filtru na stronie Lista dostępnych nie działa zgodnie z oczekiwaniami

## <a name="symptoms"></a>Objawy

Filtry w okienku filtrów na stronie **Lista dostępnych** nie filtrują wyników w oczekiwany sposób.

## <a name="resolution"></a>Rozwiązanie

Strona **Lista dostępnych zapasów** jest składana z tabeli szczegółowych dostępnych zapasów, która zawiera wszystkie dostępne wymiary. Jednak lista na tej stronie jest podsumowaniem. Dlatego można łączyć wiersze z tabeli źródłowej, sumując wartości zgodnie z podanymi wymiarami.

Filtry skonfigurowane w okienku filtrów są stosowane do tabeli źródłowej, a nie do zagregowanej listy. Takie zachowanie może czasami mieć nieoczekiwane wyniki, tak jak pokazano w [tych przykładach](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#examples).

Jednak [filtry dostarczone w siatce](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#grid-filters) *są* stosowane do zagregowanej listy. Filtry te obejmują zarówno QuickFilter na górze siatki, jak i filtr dla każdego nagłówka kolumny.
