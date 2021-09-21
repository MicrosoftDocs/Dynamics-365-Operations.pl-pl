---
title: Okienko filtru na stronie listy dostępnych zadań nie działa zgodnie z oczekiwaniami
description: Filtry w okienku filtrów na stronie „Lista dostępnych zapasów” nie filtruje wyników w oczekiwany sposób.
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
ms.openlocfilehash: df11b1c1e7de36fa0458cd931d4be7f84a15d143
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477337"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Okienko filtru na stronie listy dostępnych zadań nie działa zgodnie z oczekiwaniami

## <a name="symptoms"></a>Objawy

Filtry w okienku filtrów na stronie **dostępnych zapasów** nie filtruje wyników w oczekiwany sposób.

## <a name="resolution"></a>Rozwiązanie

Strona  **dostępnych zapasów** jest składana z tabeli szczegółowych dostępnych zapasów, która zawiera wszystkie dostępne wymiary. Jednak lista na tej stronie jest podsumowaniem. Dlatego można łączyć wiersze z tabeli źródłowej, sumując wartości zgodnie z podanymi wymiarami.

Filtry zdefiniowane w okienku filtrów mają zastosowanie do tabeli źródłowej, a nie do listy agregowanej. Takie zachowanie może czasami mieć nieoczekiwane wyniki, tak jak pokazano w [tych przykładach](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#examples).

Jednak  [filtry dostarczone w siatce](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#grid-filters) *są* stosowane do zagregowanej listy. Filtry te obejmują zarówno QuickFilter na górze siatki, jak i filtr dla każdego nagłówka kolumny.
