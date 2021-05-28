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
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a><span data-ttu-id="82bab-103">Wycofanie zgłoszenia gotowych powoduje nieoczekiwaną otwartą transakcję</span><span class="sxs-lookup"><span data-stu-id="82bab-103">Reversal of reporting as finished creates an unexpected open transaction</span></span>

<span data-ttu-id="82bab-104">Numer artykułu z bazy wiedzy: 4612469</span><span class="sxs-lookup"><span data-stu-id="82bab-104">KB number: 4612469</span></span>

## <a name="symptoms"></a><span data-ttu-id="82bab-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="82bab-105">Symptoms</span></span>

<span data-ttu-id="82bab-106">Jeśli wycofasz raportowanie jako zakończone, które ma oznaczenie, system utworzy otwartą transakcję, w której wycofana ilość ma takie same wymiary magazynowe, jak transakcja, która została wycofana.</span><span class="sxs-lookup"><span data-stu-id="82bab-106">If you reverse reporting as finished that has marking, the system creates an open transaction where the reversed quantity has the same inventory dimensions as the transaction that was reversed.</span></span>

## <a name="resolution"></a><span data-ttu-id="82bab-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="82bab-107">Resolution</span></span>

<span data-ttu-id="82bab-108">Gdy zostanie wycofana operacja zgłoszenia gotowych, wymiar magazynowy jest inicjowany z arkusza produkcji.</span><span class="sxs-lookup"><span data-stu-id="82bab-108">When you reverse a report-as-finished operation, the inventory dimension is initialized from the production journal.</span></span> <span data-ttu-id="82bab-109">W związku z tymotrzymuje numer partii.</span><span class="sxs-lookup"><span data-stu-id="82bab-109">Therefore, it gets the batch number.</span></span> <span data-ttu-id="82bab-110">Z powodu zaznaczania transakcje zamówienia sprzedaży dziedziczą numer partii.</span><span class="sxs-lookup"><span data-stu-id="82bab-110">Because of marking, the sales order transactions will inherit the batch number.</span></span>

<span data-ttu-id="82bab-111">Wymiar można zresetować po zaksięgowaniu zgłoszenia jako gotowe.</span><span class="sxs-lookup"><span data-stu-id="82bab-111">The dimension can be reset when the reporting as finished is posted.</span></span>
