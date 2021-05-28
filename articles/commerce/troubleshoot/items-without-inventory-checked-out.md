---
title: Towary bez zapasów mogą zostać wyewidencjonowane
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc klientom w dodaniu towarów poza zapasami do koszyka i kontynuowaniu realizacji zamówienia.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 4fa7769044c45faffd9ff61b3de8e6217a5e0354
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018465"
---
# <a name="items-without-inventory-can-be-checked-out"></a><span data-ttu-id="8cb4a-103">Towary bez zapasów mogą zostać wyewidencjonowane</span><span class="sxs-lookup"><span data-stu-id="8cb4a-103">Items without inventory can be checked out</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8cb4a-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc klientom w dodaniu towarów poza zapasami do koszyka i kontynuowaniu realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-104">This topic provides troubleshooting guidance that can help when customers can add out-of-stock items to their cart and proceed to checkout.</span></span>

## <a name="description"></a><span data-ttu-id="8cb4a-105">opis</span><span class="sxs-lookup"><span data-stu-id="8cb4a-105">Description</span></span>

<span data-ttu-id="8cb4a-106">Użytkownicy mogą dodać towar do koszyka, nawet jeśli w sklepie nie ma dostępnych zapasów, i przejdź do strony realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-106">Users can add an item to their cart, even though there is no on-hand inventory in the store, and then proceed to the checkout page.</span></span>

## <a name="resolution"></a><span data-ttu-id="8cb4a-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="8cb4a-107">Resolution</span></span>

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a><span data-ttu-id="8cb4a-108">Włączanie właściwości Pokaż błędy w magazynie w konstruktorze witryn portalu Commerce</span><span class="sxs-lookup"><span data-stu-id="8cb4a-108">Enable the Show Out Of Stock Errors property in Commerce site builder</span></span>

<span data-ttu-id="8cb4a-109">Aby włączyć właściwości **Pokaż błędy w magazynie** w konstruktorze witryn portalu Commerce, wykonaj te kroki.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-109">To enable the **Show Out Of Stock Errors** property in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="8cb4a-110">Wybierz witrynę, nad która pracujesz.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-110">Select the site that you're working on.</span></span>
1. <span data-ttu-id="8cb4a-111">W okienku nawigacji po lewej stronie wybierz pozycję **Strony**.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-111">In the left navigation, select **Pages**.</span></span>
1. <span data-ttu-id="8cb4a-112">Wybierz pozycję **CartPage**, aby ją otworzyć.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-112">Select **CartPage** to open it.</span></span>
1. <span data-ttu-id="8cb4a-113">Zaznacz gniazdo **Koszyk 1**, wybierz opcję **Edytuj**, a następnie w okienku właściwości zaznacz pole wyboru **Pokaż błędy w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-113">Select the **Cart 1** slot, select **Edit**, and then, in the properties pane, select the **Show Out Of Stock Errors** check box.</span></span>
1. <span data-ttu-id="8cb4a-114">Zapisz i opublikuj podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-114">Save and publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8cb4a-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8cb4a-115">Additional resources</span></span>

[<span data-ttu-id="8cb4a-116">Zastosuj ustawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="8cb4a-116">Apply inventory settings</span></span>](../inventory-settings.md)

[<span data-ttu-id="8cb4a-117">Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="8cb4a-117">Calculate inventory availability for retail channels</span></span>](../calculated-inventory-retail-channels.md)

[<span data-ttu-id="8cb4a-118">Konfigurowanie buforów zapasów i poziomów zapasów</span><span class="sxs-lookup"><span data-stu-id="8cb4a-118">Configure inventory buffers and inventory levels</span></span>](../inventory-buffers-levels.md)
