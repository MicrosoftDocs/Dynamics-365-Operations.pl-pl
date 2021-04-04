---
title: Rozwiązywanie problemów z uzupełnianiem zapasów
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z uzupełnieniem zapasów w Microsoft Dynamics 365 Supply Chain Management.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8dfb58c9156df106f58dfdc0ee2e0ef8defb9d9f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263211"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="b6abb-103">Rozwiązywanie problemów z uzupełnianiem zapasów</span><span class="sxs-lookup"><span data-stu-id="b6abb-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6abb-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z uzupełnieniem zapasów w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6abb-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="b6abb-105">Otrzymuję następujący komunikat o błędzie: „Praca %1 nie może zostać odblokowana, ponieważ zawiera niedokończone prace uzupełniające”.</span><span class="sxs-lookup"><span data-stu-id="b6abb-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="b6abb-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="b6abb-106">Issue description</span></span>

<span data-ttu-id="b6abb-107">Praca pobrania została zablokowana z powodu zależnej pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="b6abb-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b6abb-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="b6abb-108">Issue resolution</span></span>

<span data-ttu-id="b6abb-109">W przypadku użycia grupy czynności uzupełnienia popytu, jeśli lokalizacja pobrania musi być uzupełniana w celu zrealizowania zapotrzebowania zamówienia źródłowego, system tworzy zarówno pracę uzupełniającą, jak i pracę pobrania.</span><span class="sxs-lookup"><span data-stu-id="b6abb-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="b6abb-110">Jednak system blokuje pracę pobrania do momentu zakończenia pracy uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="b6abb-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="b6abb-111">To zachowanie jest celowe, ponieważ lokalizacja pobrania nie ma wystarczającej ilości zapasów, dopóki praca uzupełniania zapasów nie zostanie zakończona.</span><span class="sxs-lookup"><span data-stu-id="b6abb-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="b6abb-112">Zakończ pracę uzupełniania zapasów, a następnie przetwórz pracę pobrania.</span><span class="sxs-lookup"><span data-stu-id="b6abb-112">Complete the replenishment work, and then process the picking work.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]