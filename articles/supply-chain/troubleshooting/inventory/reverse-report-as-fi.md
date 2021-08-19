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
ms.openlocfilehash: 73ebc45ee83516f573c3f73ef8106da9ae44c590c05d8dbd08520bc5ef19e49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714217"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>Wycofanie zgłoszenia gotowych powoduje nieoczekiwaną otwartą transakcję

Numer artykułu z bazy wiedzy: 4612469

## <a name="symptoms"></a>Objawy

Jeśli wycofasz raportowanie jako zakończone, które ma oznaczenie, system utworzy otwartą transakcję, w której wycofana ilość ma takie same wymiary magazynowe, jak transakcja, która została wycofana.

## <a name="resolution"></a>Rozdzielczość

Gdy zostanie wycofana operacja zgłoszenia gotowych, wymiar magazynowy jest inicjowany z arkusza produkcji. W związku z tymotrzymuje numer partii. Z powodu zaznaczania transakcje zamówienia sprzedaży dziedziczą numer partii.

Wymiar można zresetować po zaksięgowaniu zgłoszenia jako gotowe.
