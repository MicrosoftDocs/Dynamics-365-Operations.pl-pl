---
title: Kod dostawcy nie jest autoryzowany dla określonego produktu i daty
description: Podczas próby utworzenia planowanego zamówienia lub dodania wiersza do zamówienia zakupu pojawia się komunikat o błędzie, który stwierdza, że kod sprzedawcy nie jest autoryzowany dla produktu i daty.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294158"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a><span data-ttu-id="18112-103">Kod dostawcy nie jest autoryzowany dla określonego produktu i daty</span><span class="sxs-lookup"><span data-stu-id="18112-103">Vendor code isn't authorized for a specific product and date</span></span>

<span data-ttu-id="18112-104">Kod błędu: SYP4881415</span><span class="sxs-lookup"><span data-stu-id="18112-104">Error code: SYP4881415</span></span>

## <a name="symptoms"></a><span data-ttu-id="18112-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="18112-105">Symptoms</span></span>

<span data-ttu-id="18112-106">Podczas próby wzmocnienia planowanego zamówienia lub dodania wiersza do zamówienia zakupu otrzymujemy następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="18112-106">When you try to firm a planned order or add a line to a purchase order, you receive the following error message:</span></span>

> <span data-ttu-id="18112-107">Kod dostawcy %1 nie jest uwierzytelniony dla %2 w dniu %3.</span><span class="sxs-lookup"><span data-stu-id="18112-107">Vendor code %1 is not authorized for %2 on %3.</span></span>

## <a name="cause"></a><span data-ttu-id="18112-108">Powód</span><span class="sxs-lookup"><span data-stu-id="18112-108">Cause</span></span>

<span data-ttu-id="18112-109">Błąd występuje, ponieważ pole **Metoda sprawdzania zatwierdzonego sprzedawcy** jest ustawione na *Tylko ostrzeżenie* lub *Niedozwolone* dla określonego produktu, a sprzedawca nie jest obecnie uprawniony do dostarczania tego produktu.</span><span class="sxs-lookup"><span data-stu-id="18112-109">The error occurs because the **Approved vendor check method** field is set to *Warning only* or *Not allowed* for the specified product, and the vendor isn't currently authorized to supply that product.</span></span>

## <a name="resolution"></a><span data-ttu-id="18112-110">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="18112-110">Resolution</span></span>

<span data-ttu-id="18112-111">Aby rozwiązać ten problem, należy albo wyłączyć sprawdzanie sprzedawcy dla danego produktu, albo zatwierdzić sprzedawcę.</span><span class="sxs-lookup"><span data-stu-id="18112-111">To fix this issue, either disable the vendor check for the relevant product or approve the vendor.</span></span>

<span data-ttu-id="18112-112">Aby wyłączyć sprawdzanie sprzedawcy dla produktu, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="18112-112">To disable the vendor check for a product, follow these steps.</span></span>

1. <span data-ttu-id="18112-113">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="18112-113">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="18112-114">Otwórz odpowiedni produkt.</span><span class="sxs-lookup"><span data-stu-id="18112-114">Open the relevant product.</span></span>
1. <span data-ttu-id="18112-115">Na skróconej karcie **Zakup** ustaw w polu **Metoda sprawdzania zatwierdzonych dostawców** wartość inną niż *Tylko ostrzeżenie* lub *Niedozwolone*.</span><span class="sxs-lookup"><span data-stu-id="18112-115">On the **Purchase** FastTab, set the **Approved vendor check method** field to a value other than *Warning only* or *Not allowed*.</span></span>

<span data-ttu-id="18112-116">Aby zatwierdzić sprzedawcę produktu, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="18112-116">To approve a vendor for a product, follow these steps.</span></span>

1. <span data-ttu-id="18112-117">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="18112-117">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="18112-118">Otwórz odpowiednią pozycję.</span><span class="sxs-lookup"><span data-stu-id="18112-118">Open the relevant item.</span></span>
1. <span data-ttu-id="18112-119">W Okienku akcji na karcie **Zakup** w grupie **Zatwierdzony dostawca** kliknij **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="18112-119">On the Action Pane, on the **Purchase** tab, in the **Approved vendor** group, select **Setup**.</span></span>
1. <span data-ttu-id="18112-120">Na stronie listy **Zatwierdzony sprzedawca** dodaj wiersz do siatki, aby ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="18112-120">On the **Approved vendor** list page, add a row to the grid, and set the following values for it:</span></span>

    - <span data-ttu-id="18112-121">**Dostawca** — umożliwia wybranie dostawcy, który ma być zatwierdzany dla bieżącego produktu.</span><span class="sxs-lookup"><span data-stu-id="18112-121">**Vendor** – Select the vendor to approve for the current product.</span></span>
    - <span data-ttu-id="18112-122">**Data wejścia w życie** — umożliwia wybór pierwszej daty zatwierdzenia dostawcy.</span><span class="sxs-lookup"><span data-stu-id="18112-122">**Effective date** – Select the first date that the vendor is approved for.</span></span>
    - <span data-ttu-id="18112-123">**Data ważności** — umożliwia wybór ostatniej daty zatwierdzenia dostawcy.</span><span class="sxs-lookup"><span data-stu-id="18112-123">**Expiration date** – Select the last date that the vendor is approved for.</span></span>

<span data-ttu-id="18112-124">Aby uzyskać więcej informacji, zobacz [Zatwierdzanie dostawców dla konkretnych produktów](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span><span class="sxs-lookup"><span data-stu-id="18112-124">For more information, see [Approve vendors for specific products](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span></span>
