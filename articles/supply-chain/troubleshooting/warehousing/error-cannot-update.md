---
title: Wystąpił błąd podczas wybierania lokalizacji podczas rejestracji listy pobrania
description: Wystąpił błąd podczas wybierania lokalizacji podczas rejestracji listy pobrania.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b7fc579821f9a80d94aea949fcc0301b9d8f6935
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026797"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a><span data-ttu-id="a01b9-103">Wystąpił błąd podczas wybierania lokalizacji podczas rejestracji listy pobrania</span><span class="sxs-lookup"><span data-stu-id="a01b9-103">An error occurs when the location is selected during picking list registration</span></span>

<span data-ttu-id="a01b9-104">Numer artykułu z bazy wiedzy: 4613106</span><span class="sxs-lookup"><span data-stu-id="a01b9-104">KB number: 4613106</span></span>

## <a name="symptoms"></a><span data-ttu-id="a01b9-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="a01b9-105">Symptoms</span></span>

<span data-ttu-id="a01b9-106">Ten problem występuje, gdy system jest skonfigurowany do automatycznego rezerwowania zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a01b9-106">This issue occurs when your system is configured to automatically reserve sales orders.</span></span> <span data-ttu-id="a01b9-107">W przypadku próby wybrania lokalizacji dla wiersza rejestracji listy pobrania w przypadku korzystania z procesów rezerwacji w zarządzaniu magazynem (WMS) wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="a01b9-107">If you try to select the location for a picking list registration line, you receive the following error message when you use warehouse management (WMS) reservation processes:</span></span>

> <span data-ttu-id="a01b9-108">Nie można zaktualizować ilości przy użyciu nowych wymiarów</span><span class="sxs-lookup"><span data-stu-id="a01b9-108">Can't update quantity with new dimensions</span></span>

<span data-ttu-id="a01b9-109">Ten problem może wystąpić, ponieważ w określonej lokalizacji nie ma wystarczającej ilości dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="a01b9-109">This issue can occur because you don't have enough on-hand inventory at a specified location.</span></span>

## <a name="resolution"></a><span data-ttu-id="a01b9-110">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="a01b9-110">Resolution</span></span>

<span data-ttu-id="a01b9-111">System jest szybując tak jak zaprojektowany.</span><span class="sxs-lookup"><span data-stu-id="a01b9-111">The system is behaving as designed.</span></span>

<span data-ttu-id="a01b9-112">W scenariuszach, w których jest korzystany z procesu rezerwacji na poziomie magazynu, jeśli zapasy nie zostaną zarezerwowane na wszystkich poziomach wymiarów magazynowych, a w określonej lokalizacji nie ma wystarczającej ilości dostępnych zapasów, zaleca się użycie ręcznego procesu rezerwacji z wiersza pobrania.</span><span class="sxs-lookup"><span data-stu-id="a01b9-112">In scenarios where you use the warehouse-level reservation process, if the on-hand inventory won't be reserved on all inventory dimension levels, and you don't have enough on-hand inventory at a specified location, we recommend that you use the manual reservation process from the picking line.</span></span> <span data-ttu-id="a01b9-113">Funkcji rezerwacji partii można używać do dystrybuowania *dolnych rezerwacji*, takich jak lokalizacja, dla wszystkich dostępnych ilości dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="a01b9-113">You can then use the *Reserve lot* function to distribute the lower reservations, such as location, for all the available on-hand quantities.</span></span>
