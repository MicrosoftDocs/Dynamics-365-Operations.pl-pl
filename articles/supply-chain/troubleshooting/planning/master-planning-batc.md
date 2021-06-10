---
title: Nie można filtrować pozycji planowania głównego według powiązanych z nimi wartości grup zapotrzebowania
description: Nie można filtrować pozycji planowania głównego według powiązanych z nimi wartości grup zapotrzebowania.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049485"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a><span data-ttu-id="9150c-103">Nie można filtrować pozycji planowania głównego według powiązanych z nimi wartości grup zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="9150c-103">You can't filter master planning items by their related coverage group values</span></span>

<span data-ttu-id="9150c-104">Numer artykułu z bazy wiedzy: 4612572</span><span class="sxs-lookup"><span data-stu-id="9150c-104">KB number: 4612572</span></span>

## <a name="symptoms"></a><span data-ttu-id="9150c-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="9150c-105">Symptoms</span></span>

<span data-ttu-id="9150c-106">Chcesz wyfiltrować pozycje, które zostaną uwzględnione w zadaniu wsadowym planowania głównego, na podstawie wartości powiązanych rekordów z tabeli pokrycia pozycji.</span><span class="sxs-lookup"><span data-stu-id="9150c-106">You want to filter the items that will be included in a master planning batch job, based on the values of related records from the item coverage table.</span></span> <span data-ttu-id="9150c-107">(Na przykład chcesz filtrować towary według ich **Dostawcy** i/lub wartość **Grupy zapotrzebowania**).</span><span class="sxs-lookup"><span data-stu-id="9150c-107">(For example, you want to filter items by their **Vendor** and/or **Coverage group** value).</span></span> <span data-ttu-id="9150c-108">Konfiguracja filtra dla zadania wsadowego pozwala na utworzenie złączenia z tabeli **Elementy** do tabeli **Zapotrzebowanie na towar**, a następnie określenie wartości pól z tabeli zapotrzebowania elementów w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="9150c-108">The filter setup for the batch job lets you create a join from the **Items** table to the **Item coverage** table, and then specify field values from the item coverage table in your query.</span></span> <span data-ttu-id="9150c-109">Jednak po zakończeniu tej konfiguracji system nadal tworzy planowane zlecenia dla całego zakresu pozycji, a nie tylko dla pozycji, które pasują do określonych wartości pól z tabeli zakresu pozycji.</span><span class="sxs-lookup"><span data-stu-id="9150c-109">However, after you complete this setup, the system still creates planned orders for the whole item coverage, not just for the items that match the specified field values from the item coverage table.</span></span>

## <a name="resolution"></a><span data-ttu-id="9150c-110">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="9150c-110">Resolution</span></span>

<span data-ttu-id="9150c-111">Filtr zadań wsadowych może filtrować tylko elementy.</span><span class="sxs-lookup"><span data-stu-id="9150c-111">The batch job filter can filter only on items.</span></span> <span data-ttu-id="9150c-112">Mimo że można dodać połączenia do tabeli **Zapotrzebowanie na towar**, ustawienia filtru względem tej tabeli nie wpływają na wynik kwerendy.</span><span class="sxs-lookup"><span data-stu-id="9150c-112">Although you can add a join to the **Item coverage** table, filter settings that you make against that table won't affect the query output.</span></span> <span data-ttu-id="9150c-113">W czasie pracy system przeprowadza planowanie dla wszystkich grup zapotrzebowania i wszystkich wariantów, które mają odfiltrowane elementy.</span><span class="sxs-lookup"><span data-stu-id="9150c-113">At runtime, the system runs planning for all the coverage groups and all the variations that the filtered items have.</span></span> <span data-ttu-id="9150c-114">Po włączeniu produktu do badania, wszelkie grupy pokrycia, które są zawarte w filtrze elementu, nie będą miały wpływu na wynik planowania.</span><span class="sxs-lookup"><span data-stu-id="9150c-114">After an item is already included in the run, any coverage groups that are included in the item filter a won't affect the planning output.</span></span>
