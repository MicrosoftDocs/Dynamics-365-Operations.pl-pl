---
title: Konfigurowanie scenariuszy płatności za faktury
description: W tym temacie opisano sposób konfigurowania rozwiązania Dynamics 365 Commerce pod kątem obsługi różnych scenariuszy związanych z płatnościami za faktury.
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9fe8fde32549568812a724311781d3515ef7036c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459737"
---
# <a name="set-up-pay-invoice-scenarios"></a><span data-ttu-id="fd3f5-103">Konfigurowanie scenariuszy płatności za faktury</span><span class="sxs-lookup"><span data-stu-id="fd3f5-103">Set up pay invoice scenarios</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fd3f5-104">Funkcja Zapłać fakturę w rozwiązaniu Dynamics 365 Commerce została rozszerzona, aby obsługiwać:</span><span class="sxs-lookup"><span data-stu-id="fd3f5-104">The Pay invoice functionality in Dynamics 365 Commerce has been expanded to support:</span></span>

- <span data-ttu-id="fd3f5-105">zapłatę za wiele faktur zamówienia sprzedaży w ramach pojedynczej transakcji w punkcie sprzedaży,</span><span class="sxs-lookup"><span data-stu-id="fd3f5-105">Payoff of multiple sales order invoices in a single POS transaction.</span></span>
- <span data-ttu-id="fd3f5-106">płatność za różne typy faktur dla odbiorców, takie jak faktury niezależne, projektu i korygujące.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-106">Payment of various customer invoice types including free text invoices, project-based invoices, and credit notes.</span></span>

<span data-ttu-id="fd3f5-107">Aby te scenariusze były dostępne, należy skonfigurować profil funkcji dla sklepów zgodnie z poniższym opisem.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-107">To enable these scenarios, the functionality profile for stores must be configured as outlined in below.</span></span>

1. <span data-ttu-id="fd3f5-108">Przejdź do opcji **Retail i Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji** i wybierz powiązany ze sklepami profil, dla którego chcesz wprowadzić zmiany.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-108">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Functionality profiles** and select a profile that's linked to the stores that you want to make the changes for.</span></span>
2. <span data-ttu-id="fd3f5-109">Na karcie **Funkcje** skonfiguruj poniższe parametry zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-109">On the **Functions** tab, configure the following parameters as needed.</span></span>

    - <span data-ttu-id="fd3f5-110">**Faktura zamówienia sprzedaży** — wybierz opcję **Tak**, aby umożliwić użytkownikom opłacenie co najmniej jednej faktury utworzonej na podstawie zamówienia sprzedaży w ramach pojedynczej transakcji w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-110">**Sales order invoice** – Select **Yes** to allow users to pay one or more sales order-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="fd3f5-111">**Faktura niezależna** — wybierz opcję **Tak**, aby umożliwić użytkownikom opłacenie co najmniej jednej faktury niezależnej w ramach pojedynczej transakcji w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-111">**Free text invoice** – Select **Yes** to allow users to pay one or more free text-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="fd3f5-112">**Faktura projektu** — wybierz opcję **Tak**, aby umożliwić użytkownikom opłacenie co najmniej jednej faktury utworzonej na podstawie projektu w ramach pojedynczej transakcji w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-112">**Project invoice** – Select **Yes** to allow users to pay one or more project-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="fd3f5-113">**Faktura korygująca zamówienia sprzedaży** — wybierz opcję **Tak**, aby umożliwić użytkownikom rozliczenie wielu faktur korygujących na podstawie zamówień sprzedaży dla otwartych faktur lub przetworzyć zwrot dla odbiorcy na podstawie otwartej faktury korygującej.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-113">**Sales order credit note** – Select **Yes** to allow users to settle multiple sales order-based credit notes against open invoices or process a refund to the customer for an open credit note.</span></span>

> [!NOTE]
> <span data-ttu-id="fd3f5-114">Płatność lub rozliczenie kwot częściowych nie są jeszcze obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-114">Payment or settlement of partial amounts is not yet supported.</span></span>
