---
title: Produkt jest wstrzymany dla transakcji
description: Po skonfigurowaniu planowania zleceń pojawia się komunikat o błędzie informujący, że pozycja jest wstrzymana dla transakcji.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301286"
---
# <a name="product-is-on-hold-for-transactions"></a><span data-ttu-id="d1724-103">Produkt jest wstrzymany dla transakcji</span><span class="sxs-lookup"><span data-stu-id="d1724-103">Product is on hold for transactions</span></span>

<span data-ttu-id="d1724-104">Kod błędu: SYS13295</span><span class="sxs-lookup"><span data-stu-id="d1724-104">Error code: SYS13295</span></span>

## <a name="symptoms"></a><span data-ttu-id="d1724-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="d1724-105">Symptoms</span></span>

<span data-ttu-id="d1724-106">Po ustaleniu planowanych zleceń pojawia się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="d1724-106">After you firm planned orders, you receive the following error message:</span></span>

> <span data-ttu-id="d1724-107">Pozycja %1 jest zablokowana dla transakcji w %2.</span><span class="sxs-lookup"><span data-stu-id="d1724-107">Item %1 is on hold for transactions in %2.</span></span>

## <a name="cause"></a><span data-ttu-id="d1724-108">Powód</span><span class="sxs-lookup"><span data-stu-id="d1724-108">Cause</span></span>

<span data-ttu-id="d1724-109">Opisując zablokowane towary, system używa terminów *zablokowany*, *zatrzymany* i *wstrzymany* zamiennie.</span><span class="sxs-lookup"><span data-stu-id="d1724-109">When describing blocked items, system uses the terms *blocked*, *stopped*, and *on hold* interchangeably.</span></span> <span data-ttu-id="d1724-110">Ten błąd oznacza, że w domyślnych ustawieniach zamówienia pozycja jest ustawiona jako **Zatrzymana**.</span><span class="sxs-lookup"><span data-stu-id="d1724-110">This error means that the item is set as **Stopped** in its default order settings.</span></span>

<span data-ttu-id="d1724-111">Jeśli pozycja jest zablokowana, a dodajesz ją do wiersza zamówienia zakupu lub zamówienia sprzedaży, otrzymujesz komunikat ostrzegawczy.</span><span class="sxs-lookup"><span data-stu-id="d1724-111">If an item is blocked, and you add it to a purchase order or sales order line, you receive a warning message.</span></span> <span data-ttu-id="d1724-112">Po zablokowaniu towaru transakcje magazynowe odnoszące się do wiersza zamówienia zakupu lub sprzedaży nie mogą być modyfikowane (na przykład podczas księgowania).</span><span class="sxs-lookup"><span data-stu-id="d1724-112">When an item is blocked, inventory transactions that are related to the purchase order or sales order line can't be modified (for example, when you post a packing slip or an invoice).</span></span> <span data-ttu-id="d1724-113">Można zablokować kupiony towar i jednocześnie go sprzedać.</span><span class="sxs-lookup"><span data-stu-id="d1724-113">You can block a purchased item, and, at the same time, sell the item.</span></span> <span data-ttu-id="d1724-114">W takim przypadku to pole **Zatrzymane** jest zaznaczone w zamówieniu zakupu, ale produkt nie jest zablokowany w magazynie i na zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d1724-114">In this case, the **Stopped** check box is selected on a purchase order, but the item isn't blocked in inventory or on a sales order.</span></span>

<span data-ttu-id="d1724-115">Oto niektóre z warunków, które mogą spowodować, że numer pozycji zostanie zablokowany przed sprzedażą:</span><span class="sxs-lookup"><span data-stu-id="d1724-115">Here are some of the conditions that can cause an item number to be blocked from being sold:</span></span>

- <span data-ttu-id="d1724-116">Towar jest nadal projektowy lub wytwarzany.</span><span class="sxs-lookup"><span data-stu-id="d1724-116">The item is still under development or manufacture.</span></span> <span data-ttu-id="d1724-117">Dlatego nie chcesz, aby został sprzedany lub zarezerwowany.</span><span class="sxs-lookup"><span data-stu-id="d1724-117">Therefore, you don't want it to be sold or reserved.</span></span>
- <span data-ttu-id="d1724-118">Otrzymałeś wiele wadliwych przedmiotów, a wady muszą zostać usunięte przed sprzedażą przedmiotu.</span><span class="sxs-lookup"><span data-stu-id="d1724-118">You've received many defective items, and the defects must be corrected before the item can be sold.</span></span>

<span data-ttu-id="d1724-119">W związku z tym można zablokować towar do czasu rozwiązania problemu.</span><span class="sxs-lookup"><span data-stu-id="d1724-119">In cases of this type, you can block the item until the issue is resolved.</span></span>

<span data-ttu-id="d1724-120">Jeśli towar jest zablokowany i tworzysz wiersz zamówienia zwrotu, zostanie wyświetlona wiadomość.</span><span class="sxs-lookup"><span data-stu-id="d1724-120">If an item is blocked, and you create a return order line, you receive a message.</span></span> <span data-ttu-id="d1724-121">Nie można zablokować serii lub partii towaru.</span><span class="sxs-lookup"><span data-stu-id="d1724-121">You can't block a series or a lot of an item.</span></span> <span data-ttu-id="d1724-122">Jeśli konieczne jest zablokowanie części towaru, można to zrobić przez przesunięcie magazynowe lub zablokowanie całego zapasu towaru na dany okres.</span><span class="sxs-lookup"><span data-stu-id="d1724-122">If parts of an item must be blocked, you can block them by moving inventory or by blocking the full stock of the item for that period.</span></span>

## <a name="resolution"></a><span data-ttu-id="d1724-123">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="d1724-123">Resolution</span></span>

- <span data-ttu-id="d1724-124">Otwórz stronę **Ustawienia domyślne zamówień** dla pozycji i wyczyść pole wyboru **Zatrzymane**.</span><span class="sxs-lookup"><span data-stu-id="d1724-124">Open the **Default order settings** page for the item, and clear the **Stopped** checkbox.</span></span>
