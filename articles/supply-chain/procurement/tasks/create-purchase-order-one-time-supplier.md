---
title: Tworzenie zamówienia zakupu dla dostawcy jednorazowego
description: W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego.
author: kamaybac
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3fe76a3d481c3bc8dd3a3d45eda031df61ece4aa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812380"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="00f9c-103">Tworzenie zamówienia zakupu dla dostawcy jednorazowego</span><span class="sxs-lookup"><span data-stu-id="00f9c-103">Create a purchase order for a one-time supplier</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="00f9c-104">W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego.</span><span class="sxs-lookup"><span data-stu-id="00f9c-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="00f9c-105">Dostawca jest tworzony automatycznie razem z zamówieniem zakupu, a nie ręcznie.</span><span class="sxs-lookup"><span data-stu-id="00f9c-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="00f9c-106">W przypadku tworzenia ręcznego najczęściej robi to pracownik działu zakupów.</span><span class="sxs-lookup"><span data-stu-id="00f9c-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="00f9c-107">Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="00f9c-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="00f9c-108">Warunkiem wstępnym jest wcześniejsze utworzenie konta dostawcy jednorazowego na stronie Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="00f9c-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="00f9c-109">Tworzenie zamówienia zakupu dla dostawcy jednorazowego</span><span class="sxs-lookup"><span data-stu-id="00f9c-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="00f9c-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="00f9c-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="00f9c-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="00f9c-111">Click New.</span></span>
3. <span data-ttu-id="00f9c-112">W polu Dostawca jednorazowy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="00f9c-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="00f9c-113">Konto dostawcy jest automatycznie tworzone i przypisywane do zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="00f9c-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="00f9c-114">Konto dostawcy jest tworzone na podstawie szablonu określonego na karcie Ogólne na stronie Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="00f9c-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="00f9c-115">W polu Nazwa nadaj nazwę dostawcy.</span><span class="sxs-lookup"><span data-stu-id="00f9c-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="00f9c-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="00f9c-116">Click OK.</span></span>
    * <span data-ttu-id="00f9c-117">Zamówienie zakupu można teraz sfinalizować i przetwarzać jak każde inne zamówienie.</span><span class="sxs-lookup"><span data-stu-id="00f9c-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="00f9c-118">Nie istnieją żadne specjalne cechy w tym procesie.</span><span class="sxs-lookup"><span data-stu-id="00f9c-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="00f9c-119">Faktura uwzględni planowaną transakcję na koncie dostawcy utworzonym razem z zamówieniem, po czym zostanie przetworzona płatność.</span><span class="sxs-lookup"><span data-stu-id="00f9c-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]