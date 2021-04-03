---
title: Rozwiązywanie problemów dotyczących częściowych zwolnień i częściowej wysyłki
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z częściowymi wydaniami i częściowymi wysyłkami w Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 1c9246376505e163a4a41bf141a98deed0fd511f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263264"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a><span data-ttu-id="ba668-103">Rozwiązywanie problemów dotyczących częściowych zwolnień i częściowej wysyłki</span><span class="sxs-lookup"><span data-stu-id="ba668-103">Troubleshoot partial releases and partial shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ba668-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z częściowymi wydaniami i częściowymi wysyłkami w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ba668-104">This topic describes how to fix common issues that you might encounter while you work with partial releases and partial shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a><span data-ttu-id="ba668-105">Status zwolnienia zamówienia sprzedaży pozostaje częściowo zwolniony nawet po zafakturowaniu zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ba668-105">The release status of a sales order remains Partially released even after the sales order is invoiced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="ba668-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ba668-106">Issue description</span></span>

<span data-ttu-id="ba668-107">Zamówienie sprzedaży jest zleceniem dostawy, ale jeden lub więcej towarów ma inną metodę dostawy.</span><span class="sxs-lookup"><span data-stu-id="ba668-107">A sales order is a delivery order, but one or more items on it have a different mode of delivery.</span></span> <span data-ttu-id="ba668-108">Po zafakturowaniu zamówienia stan zlecenia nadal jest *Częściowo zwolnione*.</span><span class="sxs-lookup"><span data-stu-id="ba668-108">After the order is invoiced, it still has a release status of *Partially released*.</span></span>

<span data-ttu-id="ba668-109">Na przykład zamówienie sprzedaży zawiera dwa elementy: jeden do dostawy i jeden do odbioru.</span><span class="sxs-lookup"><span data-stu-id="ba668-109">For example, a sales order has two items: one for delivery and one for pickup.</span></span> <span data-ttu-id="ba668-110">Dostawa i odbiór zostały zrealizowane.</span><span class="sxs-lookup"><span data-stu-id="ba668-110">Both the delivery and the pickup have been done.</span></span> <span data-ttu-id="ba668-111">Z tego powodu oba wiersze zostały zafakturowane.</span><span class="sxs-lookup"><span data-stu-id="ba668-111">Therefore, both lines have been invoiced.</span></span> <span data-ttu-id="ba668-112">Jednak stan zwolnienia jest nadal pokazywany jako *Częściowo zwolniony*, co jest mylące.</span><span class="sxs-lookup"><span data-stu-id="ba668-112">However, the release status is still shown as *Partially released*, which is misleading.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ba668-113">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ba668-113">Issue resolution</span></span>

<span data-ttu-id="ba668-114">Stan wydania dotyczy tylko wierszy zamówień, w których towary są włączone dla zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="ba668-114">The release status applies only to order lines where the items are enabled for warehouse management.</span></span> <span data-ttu-id="ba668-115">W związku z tym stan zwolnienia pozostanie *Częściowo zwolniony* w tym scenariuszu.</span><span class="sxs-lookup"><span data-stu-id="ba668-115">Therefore, the release status remains *Partially released* in this scenario.</span></span> <span data-ttu-id="ba668-116">Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji.</span><span class="sxs-lookup"><span data-stu-id="ba668-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="ba668-117">Rozszerzenie może zostać dodane jako część procesu dokumentu dostawy i fakturowania w celu zaktualizowania stanu wydania.</span><span class="sxs-lookup"><span data-stu-id="ba668-117">An extension could be added as part of the packing slip and invoicing process to update the release status.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]