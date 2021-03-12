---
title: Konfigurowanie i używanie kodów PKWiU dla Polski
description: W tym temacie omówiono konfigurowanie kod PKWiU dla Polski.
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Poland
ms.author: kfend
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: ef29afadc5570153ba30186620d6698d3dd9434b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990134"
---
# <a name="set-up-and-use-pkwiu-codes-for-poland"></a><span data-ttu-id="31d54-103">Konfigurowanie i używanie kodów PKWiU dla Polski</span><span class="sxs-lookup"><span data-stu-id="31d54-103">Set up and use PKWiU codes for Poland</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31d54-104">Kod PKWiU jest używany do celów podatkowych w klasyfikacji towarów i usług sprzedawanych w Polsce.</span><span class="sxs-lookup"><span data-stu-id="31d54-104">The PKWiU code is used for tax purposes to categorize goods and services sold in Poland.</span></span> <span data-ttu-id="31d54-105">Jest on uwzględniony na wszystkich fakturach zamówień sprzedaży, fakturach niezależnych oraz fakturach zaksięgowanych z poziomu modułu Projekt.</span><span class="sxs-lookup"><span data-stu-id="31d54-105">It is included on all sales order invoices, free text invoices, and invoices posted from the Project module.</span></span> <span data-ttu-id="31d54-106">Za pomocą formularza **Arkusze faktur** można wyświetlić kod PKWiU na fakturze za projekt oraz wydrukować fakturę za projekt.</span><span class="sxs-lookup"><span data-stu-id="31d54-106">You can view the PKWiU code in the project invoice and print the project invoice by using the **Invoice journals** form.</span></span> <span data-ttu-id="31d54-107">Można również skonfigurować powiadamianie o braku kodu PKWiU na fakturze.</span><span class="sxs-lookup"><span data-stu-id="31d54-107">You can also set up notifications for when a PKWiU code is missing from an invoice.</span></span>

<span data-ttu-id="31d54-108">Aby zapewnić, że użytkownicy uwzględniają kod PKWiU na wszystkich fakturach, wybierz jedną z następujących opcji w polu **Wymagany kod PKWiU** na stronie **Parametry modułu rozrachunków z odbiorcami**:</span><span class="sxs-lookup"><span data-stu-id="31d54-108">To ensure that users include a PKWiU code on all invoices, select one of the following options in the **PKWiU code requirement** field on the **Accounts receivable parameters** page:</span></span> 
- <span data-ttu-id="31d54-109">**Brak** — nie jest wyświetlany komunikat o braku kodu PKWiU z zamówienia sprzedaży lub faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="31d54-109">**None** – Do not display a message when a PKWiU code is missing from a sales order or a free text invoice.</span></span> <span data-ttu-id="31d54-110">Kod PKWiU nie jest wymagany w przypadku faktur.</span><span class="sxs-lookup"><span data-stu-id="31d54-110">The PKWiU code is not required for invoices.</span></span> 
- <span data-ttu-id="31d54-111">**Ostrzeżenie** — wyświetlanie komunikatu podczas fakturowania zamówienia sprzedaży lub faktury niezależnej, na których brak kod PKWiU.</span><span class="sxs-lookup"><span data-stu-id="31d54-111">**Warning** – Display a message when you invoice a sales order or a free text invoice that is missing the PKWiU code.</span></span> 
- <span data-ttu-id="31d54-112">**Błąd** — umożliwia wyświetlenie komunikatu podczas fakturowania zamówienia sprzedaży lub faktury niezależnej, na których brak kodu PKWiU i powoduje zatrzymanie fakturowania.</span><span class="sxs-lookup"><span data-stu-id="31d54-112">**Error** – Display a message when you invoice a sales order or a free text invoice that is missing the PKWiU code and stop the invoice from being processed.</span></span> 

## <a name="assign-a-pkwiu-code-to-the-sales-category-hierarchy"></a><span data-ttu-id="31d54-113">Przypisanie kodu PKWiU do hierarchii kategorii sprzedaży</span><span class="sxs-lookup"><span data-stu-id="31d54-113">Assign a PKWiU code to the sales category hierarchy</span></span>

<span data-ttu-id="31d54-114">Hierarchie kategorii są używane do klasyfikowania produktów czy transakcji dla celów raportowania i analiz.</span><span class="sxs-lookup"><span data-stu-id="31d54-114">Category hierarchies are used to classify products or transactions for reporting and analysis.</span></span> <span data-ttu-id="31d54-115">Hierarchia kategorii o typie Hierarchia kategorii sprzedaży jest używana do organizowania produktów dla działań dotyczących sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="31d54-115">The category hierarchy that is of the Sales category hierarchy type is used for organizing products for sales activities.</span></span> <span data-ttu-id="31d54-116">Można przypisać kod PKWiU do hierarchii kategorii sprzedaży w taki sposób, aby kod PKWiU był uwzględniony na fakturach, które zawierają towary nie zinwentaryzowane.</span><span class="sxs-lookup"><span data-stu-id="31d54-116">You can assign a PKWiU code to the sales category hierarchy so that the PKWiU code is included on invoices that include non-inventoried items.</span></span> 

1. <span data-ttu-id="31d54-117">Kliknij kolejno opcje **Zarządzanie informacjami o produktach** > **Ustawienia** > **Kategorie i atrybuty** > **Hierarchie kategorii**.</span><span class="sxs-lookup"><span data-stu-id="31d54-117">Click **Product information management** > **Setup** > **Categories and attributes** > **Category hierarchies**.</span></span> 
2. <span data-ttu-id="31d54-118">Wybierz hierarchię kategorii sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="31d54-118">Select the sales category hierarchy.</span></span> <span data-ttu-id="31d54-119">W okienku akcji kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="31d54-119">On the Action Pane, click **Edit**.</span></span> 
3. <span data-ttu-id="31d54-120">Na skróconej karcie **Przypisz kod PKWiU** wprowadź kod PKWiU dla hierarchii kategorii sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="31d54-120">On the **Assign PKWiU code** FastTab, enter the PKWiU code for the sales category hierarchy.</span></span> 

## <a name="assign-a-pkwiu-code-to-released-products"></a><span data-ttu-id="31d54-121">Przypisz kod PKWiU do zwolnionych produktów</span><span class="sxs-lookup"><span data-stu-id="31d54-121">Assign a PKWiU code to released products</span></span>

1. <span data-ttu-id="31d54-122">Kliknij kolejno **Zarządzanie informacjami o produktach** > **Wspólne** > **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="31d54-122">Click **Product information management** > **Common** > **Released products**.</span></span> 
2. <span data-ttu-id="31d54-123">Wybierz zwolniony produkt, do którego chcesz przypisać kod PKWiU.</span><span class="sxs-lookup"><span data-stu-id="31d54-123">Select the released product to assign a PKWiU code to.</span></span> <span data-ttu-id="31d54-124">W okienku akcji kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="31d54-124">On the Action Pane, click **Edit**.</span></span> 
3. <span data-ttu-id="31d54-125">Na skróconej karcie **Sprzedaż** wprowadź kod PKWiU dla zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="31d54-125">On the **Sell** FastTab, enter the PKWiU code for the released product.</span></span> 
