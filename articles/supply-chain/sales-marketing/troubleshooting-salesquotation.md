---
title: Rozwiązywanie problemów z ofertami sprzedaży
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z ofertami sprzedaży.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 67610a833be132399b2d47ae8c6b27119be9ce95
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435178"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="748d1-103">Rozwiązywanie problemów z ofertami sprzedaży</span><span class="sxs-lookup"><span data-stu-id="748d1-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="748d1-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z ofertami sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="748d1-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="748d1-105">Nie można zmienić ilości sprzedaży oferty sprzedaży dla przedmiotu serwisu.</span><span class="sxs-lookup"><span data-stu-id="748d1-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="748d1-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="748d1-106">Issue description</span></span>

<span data-ttu-id="748d1-107">W przypadku próby ustawienia ilości sprzedaży (pole **SalesQty**) dla towaru typu *usługa* w wierszu oferty sprzedaży zostanie wyświetlony następujący komunikat: „Aktualizacja jest niedozwolona dla ilości w polu”.</span><span class="sxs-lookup"><span data-stu-id="748d1-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="748d1-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="748d1-108">Issue resolution</span></span>

<span data-ttu-id="748d1-109">Nie można skonfigurować ilości sprzedaży dla produktów, które są pozycjami serwisu.</span><span class="sxs-lookup"><span data-stu-id="748d1-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="748d1-110">Jeśli na przykład usługa jest oferowana do zainstalowania towaru, nie ma sensu, aby było możliwe zarejestrowanie ilości z powodu braku fizycznego towaru.</span><span class="sxs-lookup"><span data-stu-id="748d1-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="748d1-111">Istnieje tylko usługa.</span><span class="sxs-lookup"><span data-stu-id="748d1-111">There is only a service.</span></span>

