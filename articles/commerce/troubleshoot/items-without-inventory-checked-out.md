---
title: Towary bez zapasów mogą zostać wyewidencjonowane
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc klientom w dodaniu towarów poza zapasami do koszyka i kontynuowaniu realizacji zamówienia.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 6df9c77248c7f4e16765b98327fe5838f0fce7e4
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585481"
---
# <a name="items-without-inventory-can-be-checked-out"></a><span data-ttu-id="b6804-103">Towary bez zapasów mogą zostać wyewidencjonowane</span><span class="sxs-lookup"><span data-stu-id="b6804-103">Items without inventory can be checked out</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b6804-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc klientom w dodaniu towarów poza zapasami do koszyka i kontynuowaniu realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="b6804-104">This topic provides troubleshooting guidance that can help when customers can add out-of-stock items to their cart and proceed to checkout.</span></span>

## <a name="description"></a><span data-ttu-id="b6804-105">opis</span><span class="sxs-lookup"><span data-stu-id="b6804-105">Description</span></span>

<span data-ttu-id="b6804-106">Użytkownicy mogą dodać towar do koszyka, nawet jeśli w sklepie nie ma dostępnych zapasów, i przejdź do strony realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="b6804-106">Users can add an item to their cart, even though there is no on-hand inventory in the store, and then proceed to the checkout page.</span></span>

## <a name="resolution"></a><span data-ttu-id="b6804-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="b6804-107">Resolution</span></span>

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a><span data-ttu-id="b6804-108">Włączanie właściwości Pokaż błędy w magazynie w konstruktorze witryn portalu Commerce</span><span class="sxs-lookup"><span data-stu-id="b6804-108">Enable the Show Out Of Stock Errors property in Commerce site builder</span></span>

<span data-ttu-id="b6804-109">Aby włączyć właściwości **Pokaż błędy w magazynie** w konstruktorze witryn portalu Commerce, wykonaj te kroki.</span><span class="sxs-lookup"><span data-stu-id="b6804-109">To enable the **Show Out Of Stock Errors** property in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="b6804-110">Wybierz witrynę, nad która pracujesz.</span><span class="sxs-lookup"><span data-stu-id="b6804-110">Select the site that you're working on.</span></span>
1. <span data-ttu-id="b6804-111">W okienku nawigacji po lewej stronie wybierz pozycję **Strony**.</span><span class="sxs-lookup"><span data-stu-id="b6804-111">In the left navigation, select **Pages**.</span></span>
1. <span data-ttu-id="b6804-112">Wybierz pozycję **CartPage**, aby ją otworzyć.</span><span class="sxs-lookup"><span data-stu-id="b6804-112">Select **CartPage** to open it.</span></span>
1. <span data-ttu-id="b6804-113">Zaznacz gniazdo **Koszyk 1**, wybierz opcję **Edytuj**, a następnie w okienku właściwości zaznacz pole wyboru **Pokaż błędy w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="b6804-113">Select the **Cart 1** slot, select **Edit**, and then, in the properties pane, select the **Show Out Of Stock Errors** check box.</span></span>
1. <span data-ttu-id="b6804-114">Zapisz i opublikuj podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="b6804-114">Save and publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6804-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b6804-115">Additional resources</span></span>

[<span data-ttu-id="b6804-116">Zastosuj ustawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="b6804-116">Apply inventory settings</span></span>](../inventory-settings.md)

[<span data-ttu-id="b6804-117">Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="b6804-117">Calculate inventory availability for retail channels</span></span>](../calculated-inventory-retail-channels.md)

[<span data-ttu-id="b6804-118">Konfigurowanie buforów zapasów i poziomów zapasów</span><span class="sxs-lookup"><span data-stu-id="b6804-118">Configure inventory buffers and inventory levels</span></span>](../inventory-buffers-levels.md)
