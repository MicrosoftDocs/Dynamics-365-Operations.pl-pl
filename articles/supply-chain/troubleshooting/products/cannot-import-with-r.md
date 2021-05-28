---
title: Nie można zaimportować towaru przy użyciu jednostki Zwolnione produkty w wersji 2
description: Nie można zaimportować towaru przy użyciu jednostki Zwolnione produkty w wersji 2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026805"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a><span data-ttu-id="1658b-103">Nie można zaimportować towaru przy użyciu jednostki Zwolnione produkty w wersji 2</span><span class="sxs-lookup"><span data-stu-id="1658b-103">You can't import an item by using the Released products V2 entity</span></span>

<span data-ttu-id="1658b-104">Numer artykułu z bazy wiedzy: 4611825</span><span class="sxs-lookup"><span data-stu-id="1658b-104">KB number: 4611825</span></span>

## <a name="symptoms"></a><span data-ttu-id="1658b-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="1658b-105">Symptoms</span></span>

<span data-ttu-id="1658b-106">Podczas importowania towaru przy użyciu jednostki *Zwolnione produkty w wersji 2* wyświetlany jest komunikat o błędzie przypominający następujący przykład:</span><span class="sxs-lookup"><span data-stu-id="1658b-106">When you try to import an item by using the *Released products V2* entity, you receive an error message that resembles the following example:</span></span>

> <span data-ttu-id="1658b-107">Nie można utworzyć rekordu w elementach — grupach wymiarów śledzenia (EcoResTrackingDimensionGroupItem).</span><span class="sxs-lookup"><span data-stu-id="1658b-107">Cannot create a record in Items - tracking dimension groups (EcoResTrackingDimensionGroupItem).</span></span> <span data-ttu-id="1658b-108">Numer partii towaru: 2040663, Batch.</span><span class="sxs-lookup"><span data-stu-id="1658b-108">Item number: 2040663, Batch.</span></span> <span data-ttu-id="1658b-109">Rekord już istnieje.</span><span class="sxs-lookup"><span data-stu-id="1658b-109">The record already exists.</span></span>

## <a name="resolution"></a><span data-ttu-id="1658b-110">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="1658b-110">Resolution</span></span>

<span data-ttu-id="1658b-111">Aby zaimportować nowe zwolnione produkty, musisz użyć jednostki *Tworzenie zwolnionego produktu w wersji 2* zamiast jednostki *Zwolnione produkty w wersji 2*.</span><span class="sxs-lookup"><span data-stu-id="1658b-111">To import new released products, you must use the *Released product creation V2* entity instead of the *Released products V2* entity.</span></span>
