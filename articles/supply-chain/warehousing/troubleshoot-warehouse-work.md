---
title: Rozwiązywanie problemów pracy magazynowej
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z pracą magazynową w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a00ae517ff583e4231099d8e9f5d5b5a696cf7f7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645800"
---
# <a name="troubleshoot-warehouse-work"></a><span data-ttu-id="67b82-103">Rozwiązywanie problemów pracy magazynowej</span><span class="sxs-lookup"><span data-stu-id="67b82-103">Troubleshoot warehouse work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67b82-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z pracą magazynową w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="67b82-104">This topic describes how to fix common issues that you might encounter while you work with warehouse work in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a><span data-ttu-id="67b82-105">Nie można przenieść numerów identyfikacyjnych, które mają pozycje numerów seryjnych, gdy dla grupy wymiarów śledzenia jest dozwolone puste wydanie i puste przyjęcie.</span><span class="sxs-lookup"><span data-stu-id="67b82-105">I can't move license plates that have serial number items when blank issue and blank receipt are allowed on the tracking dimension group.</span></span>

### <a name="issue-description"></a><span data-ttu-id="67b82-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="67b82-106">Issue description</span></span>

<span data-ttu-id="67b82-107">Nie można przenieść numeru identyfikacyjnego za pomocą elementu menu **przesunięcia**, jeśli numer seryjny zawiera ustawienia *Dozwolone puste wydanie* i *Dozwolone puste przyjęcie* dla grupy wymiarów śledzenia, i jeśli w tej samej lokalizacji znajduje się wiele numerów identyfikacyjnych, z których niektóre mają numery seryjne, a niektóre ich nie mają.</span><span class="sxs-lookup"><span data-stu-id="67b82-107">You can't move a license plate by using a **Movement** menu item if the serial number has settings of *Blank issue allowed* and *Blank receipt allowed* on the tracking dimension group, and if there are multiple license plates in the same location, some of which have serial numbers and some of which don't have them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="67b82-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="67b82-108">Issue resolution</span></span>

<span data-ttu-id="67b82-109">Ten problem zostanie rozwiązany przez wprowdzane zmiany [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span><span class="sxs-lookup"><span data-stu-id="67b82-109">This issue will be fixed by changes that are deployed in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span></span> <span data-ttu-id="67b82-110">Wprowadzenie tych zmian powoduje, że pole **numeru seryjnego** będzie opcjonalne, jeśli są dozwolone puste przyjęcie i pustego wydanie.</span><span class="sxs-lookup"><span data-stu-id="67b82-110">Those changes will make the **Serial number** field optional when blank receipt and blank issue are allowed.</span></span>

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a><span data-ttu-id="67b82-111">W aplikacji magazynu jest zgłaszany następujący komunikat o błędzie podczas przetwarzania przesunięć: „Właściciel zapasów %1 jest niedozwolony w tym procesie”.</span><span class="sxs-lookup"><span data-stu-id="67b82-111">I receive the following error message in the warehouse app when I process movements: "The inventory owner %1 is not allowed in this process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="67b82-112">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="67b82-112">Issue description</span></span>

<span data-ttu-id="67b82-113">Brak wymiaru śledzenia **właściciela**, jeśli do tworzenia przesunięć jest używana aplikacja magazynowa.</span><span class="sxs-lookup"><span data-stu-id="67b82-113">The **Owner** tracking dimension is missing when the warehouse app is used to make movements.</span></span> <span data-ttu-id="67b82-114">Zwykły arkusz przesunięć zapasów z klienta Supply Chain Management działa zgodnie z oczekiwaniami i może być księgowany tylko wtedy, gdy jest wypełniony wymiar **właściciel**.</span><span class="sxs-lookup"><span data-stu-id="67b82-114">A regular inventory transfer journal from the Supply Chain Management client appears to work as intended and can be posted only if the **Owner** dimension is filled in.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="67b82-115">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="67b82-115">Issue resolution</span></span>

<span data-ttu-id="67b82-116">Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji.</span><span class="sxs-lookup"><span data-stu-id="67b82-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="67b82-117">Obecnie procesy zarządzania magazynem obsługują tylko zapasy będące własnością osoby prawnej.</span><span class="sxs-lookup"><span data-stu-id="67b82-117">Currently, warehouse management processes support only inventory that is owned by the legal entity.</span></span>
