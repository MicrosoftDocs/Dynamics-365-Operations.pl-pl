---
title: "Konfigurowanie i używanie kodów PKWiU dla Polski"
description: "W tym temacie omówiono konfigurowanie kod PKWiU dla Polski."
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.search.region: Poland
ms.author: v-elgolu
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 1bf37d65cd8ce6a98fc2d2fb11ae9587cf6958a3
ms.openlocfilehash: 91c25583b2fb85fd54448dbec97be3eaf8f62d39
ms.contentlocale: pl-pl
ms.lasthandoff: 09/27/2018

---

# <a name="set-up-and-use-pkwiu-codes"></a><span data-ttu-id="746f0-103">Konfigurowanie i używanie kodów PKWiU</span><span class="sxs-lookup"><span data-stu-id="746f0-103">Set up and use PKWiU codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="746f0-104">Kod PKWiU jest używany do celów podatkowych w klasyfikacji towarów i usług sprzedawanych w Polsce.</span><span class="sxs-lookup"><span data-stu-id="746f0-104">The PKWiU code is used for tax purposes to categorize goods and services sold in Poland.</span></span> <span data-ttu-id="746f0-105">Jest on uwzględniony na wszystkich fakturach zamówień sprzedaży, fakturach niezależnych oraz fakturach zaksięgowanych z poziomu modułu Projekt.</span><span class="sxs-lookup"><span data-stu-id="746f0-105">It is included on all sales order invoices, free text invoices, and invoices posted from the Project module.</span></span> <span data-ttu-id="746f0-106">Za pomocą formularza **Arkusze faktur** można wyświetlić kod PKWiU na fakturze za projekt oraz wydrukować fakturę za projekt.</span><span class="sxs-lookup"><span data-stu-id="746f0-106">You can view the PKWiU code in the project invoice and print the project invoice by using the **Invoice journals** form.</span></span> <span data-ttu-id="746f0-107">Można również skonfigurować powiadamianie o braku kodu PKWiU na fakturze.</span><span class="sxs-lookup"><span data-stu-id="746f0-107">You can also set up notifications for when a PKWiU code is missing from an invoice.</span></span>

<span data-ttu-id="746f0-108">Aby zapewnić, że użytkownicy uwzględniają kod PKWiU na wszystkich fakturach, wybierz jedną z następujących opcji w polu **Wymagany kod PKWiU** na stronie **Parametry modułu rozrachunków z odbiorcami**:</span><span class="sxs-lookup"><span data-stu-id="746f0-108">To ensure that users include a PKWiU code on all invoices, select one of the following options in the **PKWiU code requirement** field on the **Accounts receivable parameters** page:</span></span> 
- <span data-ttu-id="746f0-109">**Brak** — nie jest wyświetlany komunikat o braku kodu PKWiU z zamówienia sprzedaży lub faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="746f0-109">**None** – Do not display a message when a PKWiU code is missing from a sales order or a free text invoice.</span></span> <span data-ttu-id="746f0-110">Kod PKWiU nie jest wymagany w przypadku faktur.</span><span class="sxs-lookup"><span data-stu-id="746f0-110">The PKWiU code is not required for invoices.</span></span> 
- <span data-ttu-id="746f0-111">**Ostrzeżenie** — wyświetlanie komunikatu podczas fakturowania zamówienia sprzedaży lub faktury niezależnej, na których brak kod PKWiU.</span><span class="sxs-lookup"><span data-stu-id="746f0-111">**Warning** – Display a message when you invoice a sales order or a free text invoice that is missing the PKWiU code.</span></span> 
- <span data-ttu-id="746f0-112">**Błąd** — umożliwia wyświetlenie komunikatu podczas fakturowania zamówienia sprzedaży lub faktury niezależnej, na których brak kodu PKWiU i powoduje zatrzymanie fakturowania.</span><span class="sxs-lookup"><span data-stu-id="746f0-112">**Error** – Display a message when you invoice a sales order or a free text invoice that is missing the PKWiU code and stop the invoice from being processed.</span></span> 

## <a name="assign-a-pkwiu-code-to-the-sales-category-hierarchy"></a><span data-ttu-id="746f0-113">Przypisanie kodu PKWiU do hierarchii kategorii sprzedaży</span><span class="sxs-lookup"><span data-stu-id="746f0-113">Assign a PKWiU code to the sales category hierarchy</span></span>

<span data-ttu-id="746f0-114">Hierarchie kategorii są używane do klasyfikowania produktów czy transakcji dla celów raportowania i analiz.</span><span class="sxs-lookup"><span data-stu-id="746f0-114">Category hierarchies are used to classify products or transactions for reporting and analysis.</span></span> <span data-ttu-id="746f0-115">Hierarchia kategorii o typie Hierarchia kategorii sprzedaży jest używana do organizowania produktów dla działań dotyczących sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="746f0-115">The category hierarchy that is of the Sales category hierarchy type is used for organizing products for sales activities.</span></span> <span data-ttu-id="746f0-116">Można przypisać kod PKWiU do hierarchii kategorii sprzedaży w taki sposób, aby kod PKWiU był uwzględniony na fakturach, które zawierają towary nie zinwentaryzowane.</span><span class="sxs-lookup"><span data-stu-id="746f0-116">You can assign a PKWiU code to the sales category hierarchy so that the PKWiU code is included on invoices that include non-inventoried items.</span></span> 

1. <span data-ttu-id="746f0-117">Kliknij kolejno opcje **Zarządzanie informacjami o produktach** > **Ustawienia** > **Kategorie i atrybuty** > **Hierarchie kategorii**.</span><span class="sxs-lookup"><span data-stu-id="746f0-117">Click **Product information management** > **Setup** > **Categories and attributes** > **Category hierarchies**.</span></span> 
2. <span data-ttu-id="746f0-118">Wybierz hierarchię kategorii sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="746f0-118">Select the sales category hierarchy.</span></span> <span data-ttu-id="746f0-119">W okienku akcji kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="746f0-119">On the Action Pane, click **Edit**.</span></span> 
3. <span data-ttu-id="746f0-120">Na skróconej karcie **Przypisz kod PKWiU** wprowadź kod PKWiU dla hierarchii kategorii sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="746f0-120">On the **Assign PKWiU code** FastTab, enter the PKWiU code for the sales category hierarchy.</span></span> 

## <a name="assign-a-pkwiu-code-to-released-products"></a><span data-ttu-id="746f0-121">Przypisz kod PKWiU do zwolnionych produktów</span><span class="sxs-lookup"><span data-stu-id="746f0-121">Assign a PKWiU code to released products</span></span>

1. <span data-ttu-id="746f0-122">Kliknij kolejno **Zarządzanie informacjami o produktach** > **Wspólne** > **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="746f0-122">Click **Product information management** > **Common** > **Released products**.</span></span> 
2. <span data-ttu-id="746f0-123">Wybierz zwolniony produkt, do którego chcesz przypisać kod PKWiU.</span><span class="sxs-lookup"><span data-stu-id="746f0-123">Select the released product to assign a PKWiU code to.</span></span> <span data-ttu-id="746f0-124">W okienku akcji kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="746f0-124">On the Action Pane, click **Edit**.</span></span> 
3. <span data-ttu-id="746f0-125">Na skróconej karcie **Sprzedaż** wprowadź kod PKWiU dla zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="746f0-125">On the **Sell** FastTab, enter the PKWiU code for the released product.</span></span> 

