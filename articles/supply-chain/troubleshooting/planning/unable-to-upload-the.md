---
title: Nie można zaktualizować prognozowanego kosztu jednostkowego podczas importowania rekordów prognozy popytu
description: Gdy do importowania rekordów prognozy popytu są wykorzystywane jednostki danych, koszt wewnętrzny istniejących rekordów nie jest aktualizowany, aby był taki taki, jak zaimportowane dane.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026817"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a><span data-ttu-id="a8445-103">Nie można zaktualizować prognozowanego kosztu jednostkowego podczas importowania rekordów prognozy popytu</span><span class="sxs-lookup"><span data-stu-id="a8445-103">You can't update the forecasted unit cost when you import demand forecast records</span></span>

<span data-ttu-id="a8445-104">Numer artykułu z bazy wiedzy: 4614109</span><span class="sxs-lookup"><span data-stu-id="a8445-104">KB number: 4614109</span></span>

## <a name="symptoms"></a><span data-ttu-id="a8445-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="a8445-105">Symptoms</span></span>

<span data-ttu-id="a8445-106">Gdy do importowania rekordów prognozy popytu są wykorzystywane wartości **prognozowanego kosztu jednostkowego**, koszt wewnętrzny istniejących rekordów nie jest aktualizowany, aby był taki taki, jak zaimportowane dane.</span><span class="sxs-lookup"><span data-stu-id="a8445-106">When you use data entities to import demand forecast records, the **Forecasted unit cost** value for existing records isn't updated so that it matches the imported data.</span></span>

## <a name="cause"></a><span data-ttu-id="a8445-107">Powód</span><span class="sxs-lookup"><span data-stu-id="a8445-107">Cause</span></span>

<span data-ttu-id="a8445-108">**Prognozowany koszt jednostkowy** jest polem tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="a8445-108">**Forecasted unit cost** is a read-only field.</span></span> <span data-ttu-id="a8445-109">Ta wartość jest oparta na kosztach jednostkowych produktu i nie można jej ustawić bezpośrednio w drodze importu.</span><span class="sxs-lookup"><span data-stu-id="a8445-109">The value is based on the product unit cost and can't be set directly through import.</span></span>

## <a name="resolution"></a><span data-ttu-id="a8445-110">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="a8445-110">Resolution</span></span>

<span data-ttu-id="a8445-111">To pole jest tylko do odczytu, więc nie można dla niego zaimportować wartości.</span><span class="sxs-lookup"><span data-stu-id="a8445-111">Because the field is read only, you can't import values for it.</span></span> <span data-ttu-id="a8445-112">Wartość będzie obliczana zgodnie z istniejącą logiką biznesową.</span><span class="sxs-lookup"><span data-stu-id="a8445-112">The value will be calculated according to the existing business logic.</span></span>
