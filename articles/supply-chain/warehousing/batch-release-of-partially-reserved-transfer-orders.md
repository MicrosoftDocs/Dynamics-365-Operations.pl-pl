---
title: Wsadowe zwalnianie częściowo zarezerwowanych zamówień przeniesienia
description: W tym temacie opisano sposób konfigurowania i stosowania zwalniania wsadowego częściowo zarezerwowanych zamówień przeniesienia z urządzenia przenośnego.
author: pjacobse
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7802fe379941b915450b7c60c1187187038c95f2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837520"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a><span data-ttu-id="3ff03-103">Wsadowe zwalnianie częściowo zarezerwowanych zamówień przeniesienia</span><span class="sxs-lookup"><span data-stu-id="3ff03-103">Batch release of partially reserved transfer orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3ff03-104">Funkcja zwalniania wsadowego częściowo zarezerwowanych zamówień przeniesienia umożliwia częściowe zwolnienie zamówień przeniesienia do magazynu za pomocą zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="3ff03-104">The functionality for batch release of partially reserved transfer orders lets you partially release transfer orders to a warehouse by using a batch job.</span></span>
<span data-ttu-id="3ff03-105">Ponieważ masz możliwość zwolnienia częściowej ilości, nie musisz czekać ze zwolnieniem zamówienia, aż cała ilość z zamówienia będzie dostępne w magazynie.</span><span class="sxs-lookup"><span data-stu-id="3ff03-105">Because you have the option to release a partial quantity, you don’t have to wait for the whole order quantity to be available in the warehouse before you release an order.</span></span>

<span data-ttu-id="3ff03-106">Zwalnianie zamówień do magazynu to zaawansowany proces zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="3ff03-106">The release of orders to a warehouse is an advanced warehouse management process.</span></span> <span data-ttu-id="3ff03-107">Ten proces obejmuje działania, takie jak pobieranie, pakowanie i wysyłka, które pracownik magazynu może wykonać, używając urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="3ff03-107">This process involves activities, such as picking, packing, and shipping, that a warehouse worker can perform by using a mobile device.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="3ff03-108">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="3ff03-108">Where it applies</span></span>

<span data-ttu-id="3ff03-109">Na potrzeby tej funkcji zamówienia przeniesienia są zwalniane do magazynu za pomocą zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="3ff03-109">For this functionality, transfer orders are released to a warehouse by using a batch job.</span></span> <span data-ttu-id="3ff03-110">Ta funkcja jest przydatna, gdy nie masz wystarczającej ilości zapasów w magazynie, ale mimo to chcesz przenieść towary między magazynami.</span><span class="sxs-lookup"><span data-stu-id="3ff03-110">This functionality is useful when you don’t have enough inventory in the warehouse, but you still want to transfer items from one warehouse to another.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="3ff03-111">Sposób konfiguracji</span><span class="sxs-lookup"><span data-stu-id="3ff03-111">How it is set up</span></span>

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="3ff03-112">Określanie kryteriów realizacji dla zamówień przeniesienia i zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="3ff03-112">Specify fulfillment criteria for transfer orders and sales orders</span></span>

<span data-ttu-id="3ff03-113">Przed częściowym zwolnieniem zamówienia do magazynu w partii należy zwolnić kryteria realizacji.</span><span class="sxs-lookup"><span data-stu-id="3ff03-113">Before an order can be partially released to a warehouse in a batch, the fulfillment criteria must be met.</span></span> <span data-ttu-id="3ff03-114">Te kryteria realizacji są określane przez zasady realizacji.</span><span class="sxs-lookup"><span data-stu-id="3ff03-114">These fulfillment criteria are determined by the fulfillment policy.</span></span>

<span data-ttu-id="3ff03-115">Zasady realizacji dla zamówień przeniesienia i zamówień sprzedaży są określone na poziomie firmy.</span><span class="sxs-lookup"><span data-stu-id="3ff03-115">Fulfillment policies for transfer orders and sales orders are specified at the company level.</span></span> <span data-ttu-id="3ff03-116">W zależności od konfiguracji zasad realizacji, zwolnienie zamówień w partii zostanie zaakceptowane lub odrzucone.</span><span class="sxs-lookup"><span data-stu-id="3ff03-116">Depending on the setup of the fulfillment policy, the release of orders in a batch will be accepted or rejected.</span></span> <span data-ttu-id="3ff03-117">Zamówienia zostaną następnie odpowiednio przetworzone.</span><span class="sxs-lookup"><span data-stu-id="3ff03-117">The orders will then be processed accordingly.</span></span>

-   <span data-ttu-id="3ff03-118">Aby utworzyć zasady realizacji dla zamówień przeniesienia i zamówień sprzedaży, kliknij kolejno opcje **Zarządzanie magazynem** \> **Konfiguracja** \> **Zwolnij do magazynu** \> **Zasady realizacji**, a następnie utwórz zasady realizacji, wprowadzając nazwę i opis.</span><span class="sxs-lookup"><span data-stu-id="3ff03-118">To create fulfillment policies for transfer orders and sales orders, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then create a fulfillment policy by entering a name and a description.</span></span>

-   <span data-ttu-id="3ff03-119">Aby określić współczynnik realizacji, typ wartości i komunikat wyświetlany po naruszeniu zasad realizacji, kliknij kolejno opcję **Zarządzanie magazynem** \> **Konfiguracja** \> **Zwolnij do magazynu** \> **Zasady realizacji**, a następnie ustaw pola **Współczynnik realizacji**, **Typ wartości** i **Komunikat dotyczący naruszenia współczynnika realizacji**.</span><span class="sxs-lookup"><span data-stu-id="3ff03-119">To specify a fulfillment rate, a value type, and the message that is shown if the fulfillment policy is violated, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then set the **Fulfillment rate**, **Value type**, and **Fulfillment violation message** fields.</span></span>

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="3ff03-120">Ustawianie zasad realizacji dla zamówień przeniesienia i zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="3ff03-120">Set the fulfillment policies for transfer orders and sales orders</span></span>

-   <span data-ttu-id="3ff03-121">Aby ustawić zasady realizacji dla zamówień przeniesienia kliknij kolejno opcje **Zarządzanie magazynem** \> **Konfiguracja** \> **Parametry modułu Zarządzanie zapasami i magazynem** \> **Zamówienia przeniesienia** \> **Zarządzanie magazynem**, a następnie wybierz zasady realizacji zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="3ff03-121">To set the fulfillment policies for transfer orders, click **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters** \> **Transfer orders** \> **Warehouse management**, and then select a transfer order fulfillment policy.</span></span>

-   <span data-ttu-id="3ff03-122">Aby ustawić zasady realizacji zamówień sprzedaży dla zamówień sprzedaży, kliknij kolejno opcję **Rozrachunki z odbiorcami** \> **Konfiguracja** \> **Parametry modułu rozrachunków z odbiorcami** \> **Zarządzanie z magazynem**, a następnie wybierz zasady realizacji zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3ff03-122">To set the fulfillment policies for sales orders, click **Accounts receivable** \> **Setup** \> **Accounts receivable parameters** \> **Warehouse management**, and then select a sales order fulfillment policy.</span></span>

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a><span data-ttu-id="3ff03-123">Zezwalanie na zwolnienie partii i określanie ilości, która ma zostać zwolniona w partii</span><span class="sxs-lookup"><span data-stu-id="3ff03-123">Allow release in a batch and specify the quantity that should be release in a batch</span></span>

<span data-ttu-id="3ff03-124">Zadanie wsadowe służy do zwalniania zamówień do magazynu w partii.</span><span class="sxs-lookup"><span data-stu-id="3ff03-124">A batch job is used to release orders to a warehouse in a batch.</span></span> <span data-ttu-id="3ff03-125">Parametry odróżniające zamówienia uruchamiane w zadaniu wsadowym są ustawiane na poziomie zadania.</span><span class="sxs-lookup"><span data-stu-id="3ff03-125">The parameters that distinguish the orders that should be run in a batch job are set on the batch job itself.</span></span>

<span data-ttu-id="3ff03-126">Parametr **Ilość** określa, czy w partii ma być zwolniona cała ilość czy ilość fizycznie dostępna.</span><span class="sxs-lookup"><span data-stu-id="3ff03-126">The **Quantity** parameter specifies whether the whole quantity or the physically reserved quantity should be released in the batch.</span></span> <span data-ttu-id="3ff03-127">Parametr **Zezwalaj na częściowe zwalnianie zamówień** określa, czy zamówienia w partii mają być akceptowane czy odrzucane, jeżeli zostały częściowo zwolnione wcześniej.</span><span class="sxs-lookup"><span data-stu-id="3ff03-127">The **Allow release of partially released orders** parameter determines whether orders in the batch should be accepted or rejected if they were partially released earlier.</span></span>

-   <span data-ttu-id="3ff03-128">Aby ustawić parametry **Ilość** i **Zezwalaj na częściowe zwalnianie zamówień** dla zamówień przeniesienia, kliknij kolejno opcje **Zarządzanie magazynem** \> **Zwolnij do magazynu** \> **Automatyczne zwalnianie zamówień przeniesienia**.</span><span class="sxs-lookup"><span data-stu-id="3ff03-128">To set the **Quantity** and **Allow release of partially released orders** parameters for transfer orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of transfer orders**.</span></span>

-   <span data-ttu-id="3ff03-129">Aby ustawić parametry **Ilość** i **Zezwalaj na częściowe zwalnianie zamówień** dla zamówień sprzedaży, kliknij kolejno opcje **Zarządzanie magazynem** \> **Zwolnij do magazynu** \> **Automatyczne zwalnianie zamówień sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="3ff03-129">To set the **Quantity** and **Allow release of partially released orders** parameters for sales orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of sales orders**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]