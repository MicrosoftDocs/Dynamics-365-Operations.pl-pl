---
title: Domyślne opisy księgi głównej
description: Opisów domyślnych można użyć do zaktualizowania pola Opis w księgowaniach załączników do księgi głównej.
author: sherry-zheng
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 47c5c9e71dba7a0cb7c798c167208faebeb5af6c
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500387"
---
# <a name="default-descriptions-for-the-general-ledger"></a><span data-ttu-id="1fc08-103">Domyślne opisy księgi głównej</span><span class="sxs-lookup"><span data-stu-id="1fc08-103">Default descriptions for the general ledger</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="1fc08-104">Opisów domyślnych można użyć do zaktualizowania pola **Opis** w księgowaniach załączników do księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="1fc08-104">Default descriptions can be used to update the **Description** field in voucher postings to the general ledger.</span></span> <span data-ttu-id="1fc08-105">Ta funkcjonalność została ulepszona tak, aby działała z kosztem dostawy.</span><span class="sxs-lookup"><span data-stu-id="1fc08-105">This functionality has been enhanced to work with Landed cost.</span></span>

<span data-ttu-id="1fc08-106">Aby skonfigurować domyślne opisy dla księgować w księdze, przejdź do **Administracja organizacyjna \> Konfiguracja \> Domyślne opisy**.</span><span class="sxs-lookup"><span data-stu-id="1fc08-106">To set up default descriptions for ledger postings, go to **Organizational administration \> Setup \> Default descriptions**.</span></span>

<span data-ttu-id="1fc08-107">W poniższej tabeli wymieniono nowe wartości, które zostały dodane w polu **Opis** na stronie **Domyślne opisy**, aby obsługiwać koszt dostawy.</span><span class="sxs-lookup"><span data-stu-id="1fc08-107">The following table lists the new values that have been added for the **Description** field on the **Default descriptions** page to support Landed cost.</span></span>

| <span data-ttu-id="1fc08-108">Typ opisu</span><span class="sxs-lookup"><span data-stu-id="1fc08-108">Description type</span></span> | <span data-ttu-id="1fc08-109">Notatki</span><span class="sxs-lookup"><span data-stu-id="1fc08-109">Notes</span></span> |
|---|---|
| <span data-ttu-id="1fc08-110">Wycena importu — Naliczenie kosztów</span><span class="sxs-lookup"><span data-stu-id="1fc08-110">Import costing – Cost accrual</span></span> | <span data-ttu-id="1fc08-111">Po zaksięgowaniu faktury za zamówienie zakupu naliczony koszt jest przetwarzany w celu oszacowania kosztów podróży.</span><span class="sxs-lookup"><span data-stu-id="1fc08-111">When a purchase order invoice is posted, a cost accrual is processed for estimate voyage costs.</span></span> <span data-ttu-id="1fc08-112">Można określić domyślne opisy, aby dodać numer podróży do opisu.</span><span class="sxs-lookup"><span data-stu-id="1fc08-112">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="1fc08-113">Użyj *%4* jako numeru przesyłki.</span><span class="sxs-lookup"><span data-stu-id="1fc08-113">Use *%4* for the shipment number.</span></span> |
| <span data-ttu-id="1fc08-114">Wycena importu – zamówienie towaru w drodze</span><span class="sxs-lookup"><span data-stu-id="1fc08-114">Import costing – Goods in transit order</span></span> | <span data-ttu-id="1fc08-115">Jeśli jest przetwarzane w drodze, faktura zamówienia zakupu jest księgowana, a towary są księgowane na koncie towarów w drodze.</span><span class="sxs-lookup"><span data-stu-id="1fc08-115">If you're using in-transit processing, the purchase order invoice is posted, and the goods are posted to a goods in transit account.</span></span> <span data-ttu-id="1fc08-116">Można określić opisy domyślne, aby dodać numer zamówienia w drodze do opisu.</span><span class="sxs-lookup"><span data-stu-id="1fc08-116">Default descriptions can be specified to add the in-transit order number to the description.</span></span> <span data-ttu-id="1fc08-117">Użyj *%4* dla numeru zamówienia w drodze.</span><span class="sxs-lookup"><span data-stu-id="1fc08-117">Use *%4* for the in-transit order number.</span></span> |
| <span data-ttu-id="1fc08-118">Zapasy – Zamknięcie – Korekta</span><span class="sxs-lookup"><span data-stu-id="1fc08-118">Inventory – close – adjustment</span></span> | <span data-ttu-id="1fc08-119">Gdy faktura zobowiązań (AP) jest przetwarzana dla kosztu podróży, przetwarzana jest korekta zapasów w celu oszacowania kosztów podróży.</span><span class="sxs-lookup"><span data-stu-id="1fc08-119">When the accounts payable (AP) invoice is processed for a voyage cost, an inventory adjustment is processed to estimate voyage costs.</span></span> <span data-ttu-id="1fc08-120">Można określić domyślne opisy, aby dodać numer podróży do opisu.</span><span class="sxs-lookup"><span data-stu-id="1fc08-120">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="1fc08-121">Użyj *%4* jako numeru przesyłki.</span><span class="sxs-lookup"><span data-stu-id="1fc08-121">Use *%4* for the shipment number.</span></span> |

<span data-ttu-id="1fc08-122">Aby uzyskać więcej informacji na temat pracy ze stroną **Opisy domyślne**, zobacz temat [Konfigurowanie domyślnych opisów dla automatycznego księgowania](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span><span class="sxs-lookup"><span data-stu-id="1fc08-122">For more information about how to work with the **Default descriptions** page, see [Set up default descriptions for automatic posting](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span></span>
