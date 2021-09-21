---
title: Ta sama umowa handlowa wybrana podczas tworzenia wierszy zamówienia sprzedaży
description: Jeśli jest zdefiniowana więcej niż jedna umowa handlowa dla danego dnia, podczas tworzenia wierszy zamówienia sprzedaży zawsze jest wybierana umowa handlowa o najniższej cenie.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a586a399fb349965b972191bec1271651bec5fcb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477313"
---
# <a name="if-two-trade-agreements-exist-for-overlapping-dates-the-same-one-is-always-selected"></a>Jeśli istnieją dwie umowy handlowe dotyczące pokrywających się dat, zawsze wybierana jest ta sama umowa

## <a name="symptoms"></a>Objawy

Jeśli dwie umowy handlowe są zdefiniowane dla tego samego okresu lub nakładających się okresów, ta sama umowa handlowa wydaje się być wybierana za każdym razem podczas tworzenia wierszy zamówienia sprzedaży, które zawierają te towary.

## <a name="resolution"></a>Rozwiązanie

Jeśli istnieje więcej niż jedna umowa handlowa dla danego dnia, zawsze jest wybierana umowa handlowa o najniższej cenie. Aby uzyskać więcej informacji, pobierz następujący oficjalny dokument: [Umowy handlowe w Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).
