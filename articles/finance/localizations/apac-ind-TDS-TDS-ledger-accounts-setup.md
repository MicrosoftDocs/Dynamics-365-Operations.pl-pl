---
title: Konfigurowanie TDS kont księgi
description: W tym temacie opisano sposób skonfigurowania kont księgowych dla funkcji Podatek potrącony w źródle (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 93d4cb54488ec0eeee40ca56f3e46f30012f54f5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023507"
---
# <a name="set-up-tds-ledger-accounts"></a><span data-ttu-id="4c76a-103">Konfigurowanie TDS kont księgi</span><span class="sxs-lookup"><span data-stu-id="4c76a-103">Set up TDS ledger accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c76a-104">W tym temacie opisano sposób skonfigurowania kont księgowych dla funkcji Podatek potrącony w źródle (TDS).</span><span class="sxs-lookup"><span data-stu-id="4c76a-104">This topic explains how to set up ledger accounts for the Tax Deducted at Source (TDS) feature.</span></span> <span data-ttu-id="4c76a-105">Strona **Plan kont** umożliwia skonfigurowanie kont księgowych dla identyfikatorów TDS.</span><span class="sxs-lookup"><span data-stu-id="4c76a-105">You use the **Chart of accounts** page to set up ledger accounts for TDS.</span></span>

1. <span data-ttu-id="4c76a-106">Wybierz kolejno opcje **Księga główna \> Plan kont \> Konta \> Konta główne**.</span><span class="sxs-lookup"><span data-stu-id="4c76a-106">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**.</span></span>
2. <span data-ttu-id="4c76a-107">Na karcie **Przegląd** wybierz klawisze **Alt+N**, aby utworzyć konto księgowe TDS, i wprowadź wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="4c76a-107">On the **Overview** tab, select **Alt+N** to create a TDS ledger account, and enter the required details.</span></span>
3. <span data-ttu-id="4c76a-108">Na karcie **Ustawienia** w polu **Typ księgowania** wybierz pozycję **Potrącona zaliczka na podatek**.</span><span class="sxs-lookup"><span data-stu-id="4c76a-108">On the **Setup** tab, in the **Posting type** field, select **Withholding tax**.</span></span>     

    > [!NOTE]
    > <span data-ttu-id="4c76a-109">Konta księgowe typu typ księgowania **Potrącona zaliczka na podatek** można zdefiniować tylko jako konta należności używane do księgowania kwoty TDS należności dla kodu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="4c76a-109">Ledger accounts that have a posting type of **Withholding tax** can be defined only as receivable accounts that are used to post the TDS receivable amount for a TDS tax code.</span></span>

4. <span data-ttu-id="4c76a-110">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c76a-110">Close the page.</span></span>
