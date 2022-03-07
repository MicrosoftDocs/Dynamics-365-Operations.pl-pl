---
title: Wycofanie zgłoszenia gotowych powoduje nieoczekiwaną otwartą transakcję
description: Wycofanie zgłoszenia gotowych z oznaczeniem powoduje utworzenie otwartej transakcji, w której ilość wycofana ma takie same wymiary magazynowe jak co cofnięcie transakcji.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026825"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>Wycofanie zgłoszenia gotowych powoduje nieoczekiwaną otwartą transakcję

Numer artykułu z bazy wiedzy: 4612469

## <a name="symptoms"></a>Objawy

Jeśli wycofasz raportowanie jako zakończone, które ma oznaczenie, system utworzy otwartą transakcję, w której wycofana ilość ma takie same wymiary magazynowe, jak transakcja, która została wycofana.

## <a name="resolution"></a>Rozdzielczość

Gdy zostanie wycofana operacja zgłoszenia gotowych, wymiar magazynowy jest inicjowany z arkusza produkcji. W związku z tymotrzymuje numer partii. Z powodu zaznaczania transakcje zamówienia sprzedaży dziedziczą numer partii.

Wymiar można zresetować po zaksięgowaniu zgłoszenia jako gotowe.
