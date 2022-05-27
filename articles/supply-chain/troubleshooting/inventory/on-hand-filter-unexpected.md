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
ms.openlocfilehash: 3857ce3720430c6f512d5abc4c9c4d390a0c3377
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686691"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Okienko filtru na stronie Lista dostępnych nie działa zgodnie z oczekiwaniami

## <a name="symptoms"></a>Objawy

Filtry w okienku filtrów na stronie **Lista dostępnych** nie filtrują wyników w oczekiwany sposób.

## <a name="resolution"></a>Rozwiązanie

Strona **Lista dostępnych zapasów** jest składana z tabeli szczegółowych dostępnych zapasów, która zawiera wszystkie dostępne wymiary. Jednak lista na tej stronie jest podsumowaniem. Dlatego można łączyć wiersze z tabeli źródłowej, sumując wartości zgodnie z podanymi wymiarami.

Filtry skonfigurowane w okienku filtrów są stosowane do tabeli źródłowej, a nie do zagregowanej listy. Takie zachowanie może czasami mieć nieoczekiwane wyniki, tak jak pokazano w [tych przykładach](/dynamics365/supply-chain/inventory/inventory-on-hand-list#examples).

Jednak [filtry dostarczone w siatce](/dynamics365/supply-chain/inventory/inventory-on-hand-list#grid-filters) *są* stosowane do zagregowanej listy. Filtry te obejmują zarówno QuickFilter na górze siatki, jak i filtr dla każdego nagłówka kolumny.
