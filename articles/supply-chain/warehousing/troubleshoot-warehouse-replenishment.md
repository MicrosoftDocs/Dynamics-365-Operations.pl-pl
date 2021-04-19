---
title: Rozwiązywanie problemów z uzupełnianiem zapasów
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z uzupełnieniem zapasów w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8940f729e1115405e8d6e50eccc92d9fffe37f3e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828089"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="2ec18-103">Rozwiązywanie problemów z uzupełnianiem zapasów</span><span class="sxs-lookup"><span data-stu-id="2ec18-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ec18-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z uzupełnieniem zapasów w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2ec18-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="2ec18-105">Otrzymuję następujący komunikat o błędzie: „Praca %1 nie może zostać odblokowana, ponieważ zawiera niedokończone prace uzupełniające”.</span><span class="sxs-lookup"><span data-stu-id="2ec18-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="2ec18-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="2ec18-106">Issue description</span></span>

<span data-ttu-id="2ec18-107">Praca pobrania została zablokowana z powodu zależnej pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="2ec18-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2ec18-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="2ec18-108">Issue resolution</span></span>

<span data-ttu-id="2ec18-109">W przypadku użycia grupy czynności uzupełnienia popytu, jeśli lokalizacja pobrania musi być uzupełniana w celu zrealizowania zapotrzebowania zamówienia źródłowego, system tworzy zarówno pracę uzupełniającą, jak i pracę pobrania.</span><span class="sxs-lookup"><span data-stu-id="2ec18-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="2ec18-110">Jednak system blokuje pracę pobrania do momentu zakończenia pracy uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="2ec18-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="2ec18-111">To zachowanie jest celowe, ponieważ lokalizacja pobrania nie ma wystarczającej ilości zapasów, dopóki praca uzupełniania zapasów nie zostanie zakończona.</span><span class="sxs-lookup"><span data-stu-id="2ec18-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="2ec18-112">Zakończ pracę uzupełniania zapasów, a następnie przetwórz pracę pobrania.</span><span class="sxs-lookup"><span data-stu-id="2ec18-112">Complete the replenishment work, and then process the picking work.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]