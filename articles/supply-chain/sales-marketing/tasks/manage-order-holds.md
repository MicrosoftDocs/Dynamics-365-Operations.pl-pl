---
title: Zarządzanie wstrzymaniami zamówień
description: W tej procedurze wyjaśniono, jak wstrzymywać zamówienia sprzedaży dla odbiorców, jak pracować z wyewidencjonowaniami wstrzymania zamówienia i jak usuwać wstrzymania zamówień.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans, MCRHoldCheckOutOverride, MCRHoldCodeTable, MCRItemListCopying, MCRItemListTable, MCROMHoldList
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: edb3c6941af132f9ea1bf9f52f94cd6acc008d6c
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830063"
---
# <a name="manage-order-holds"></a><span data-ttu-id="f860d-103">Zarządzanie wstrzymaniami zamówień</span><span class="sxs-lookup"><span data-stu-id="f860d-103">Manage order holds</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f860d-104">W tej procedurze wyjaśniono, jak wstrzymywać zamówienia sprzedaży dla odbiorców, jak pracować z wyewidencjonowaniami wstrzymania zamówienia i jak usuwać wstrzymania zamówień.</span><span class="sxs-lookup"><span data-stu-id="f860d-104">This procedure demonstrates how to place customer sales orders on hold, how to work with order hold checkouts, and how to remove order holds.</span></span> <span data-ttu-id="f860d-105">Zamówienia mogą być wstrzymane z wielu powodów.</span><span class="sxs-lookup"><span data-stu-id="f860d-105">An order might be placed on hold for a variety of reasons.</span></span> <span data-ttu-id="f860d-106">Na przykład, można wstrzymać zamówienie, dopóki nie zostaną sprawdzone metody płatności lub adres odbiorcy lub dopóki menedżer nie sprawdzi limitu kredytu odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f860d-106">For example, you might hold an order until a customer address or payment method can be verified or until a manager can review the customer's credit limit.</span></span> <span data-ttu-id="f860d-107">Kiedy zamówienie jest wstrzymane, magazyn nie może go przetwarzać w celu wysyłki.</span><span class="sxs-lookup"><span data-stu-id="f860d-107">While the order on hold, it cannot be processed by the warehouse for shipping.</span></span> 

<span data-ttu-id="f860d-108">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="f860d-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-order-holds"></a><span data-ttu-id="f860d-109">Konfigurowanie wstrzymań zamówień</span><span class="sxs-lookup"><span data-stu-id="f860d-109">Set up order holds</span></span>
1. <span data-ttu-id="f860d-110">Przejdź do **Okienko nawigacyji > Moduły > Sprzedaż i marketing >Ustawienia > Zamówienia sprzedaży > Kody wstrzymania zamówień**.</span><span class="sxs-lookup"><span data-stu-id="f860d-110">Go to **Navigation pane > Modules > Sales and marketing > Setup > Sales orders > Order hold codes**.</span></span>
2. <span data-ttu-id="f860d-111">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f860d-111">Click **New**.</span></span>
3. <span data-ttu-id="f860d-112">W polu **Kod wstrzymania** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f860d-112">In the **Hold code** field, type a value.</span></span> <span data-ttu-id="f860d-113">Na przykład wpisz „Oddzwonić”.</span><span class="sxs-lookup"><span data-stu-id="f860d-113">For example, type 'Call back'.</span></span>  
4. <span data-ttu-id="f860d-114">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f860d-114">In the **Description** field, type a value.</span></span>
    - <span data-ttu-id="f860d-115">Na przykład Zamówienie wstrzymane w oczekiwaniu na oddzwonienie odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f860d-115">For example, Order held waiting for customer callback.</span></span>  
    - <span data-ttu-id="f860d-116">Opcjonalnie zaznacz pole wyboru **Usuń rezerwacje**, aby usunąć wszelkie fizyczne rezerwacje z zamówienia podczas dodawania tego kodu wstrzymania.</span><span class="sxs-lookup"><span data-stu-id="f860d-116">Optionally, select the **Remove reservations** check box to remove any physical reservations from the order when this hold code is added.</span></span>  
5. <span data-ttu-id="f860d-117">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f860d-117">Click **Save**.</span></span>

## <a name="place-order-on-hold"></a><span data-ttu-id="f860d-118">Wstrzymywanie zamówienia</span><span class="sxs-lookup"><span data-stu-id="f860d-118">Place order on hold</span></span>
1. <span data-ttu-id="f860d-119">Przejdź do **Okienko nawigacyji > Moduły > Sprzedaż i marketing >Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f860d-119">Go to **Navigation pane > Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="f860d-120">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f860d-120">Click **New**.</span></span>
3. <span data-ttu-id="f860d-121">W polu **Konto odbiorcy** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f860d-121">In the **Customer account** field, enter or select a value.</span></span>
4. <span data-ttu-id="f860d-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f860d-122">Click **OK**.</span></span>
5. <span data-ttu-id="f860d-123">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="f860d-123">In the **Item number** field, enter or select a value.</span></span>
6. <span data-ttu-id="f860d-124">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f860d-124">In the **Quantity** field, enter a number.</span></span>
7. <span data-ttu-id="f860d-125">W **okienku akcji** kliknij opcję **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f860d-125">On the **Action Pane**, click **Sales order**.</span></span>
8. <span data-ttu-id="f860d-126">Kliknij opcję **Wstrzymania zamówień**.</span><span class="sxs-lookup"><span data-stu-id="f860d-126">Click **Order holds**.</span></span>
9. <span data-ttu-id="f860d-127">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f860d-127">Click **New**.</span></span>
10. <span data-ttu-id="f860d-128">W polu **Kod wstrzymania** wybierz kod, który został utworzony w poprzednim podzadaniu.</span><span class="sxs-lookup"><span data-stu-id="f860d-128">In the **Hold code** field, select the code you have created in the previous subtask.</span></span>
11. <span data-ttu-id="f860d-129">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f860d-129">Click **Save**.</span></span>
12. <span data-ttu-id="f860d-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f860d-130">Close the page.</span></span>
13. <span data-ttu-id="f860d-131">Wybierz kolejno opcje **Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f860d-131">Go to **Sales and marketing > Sales orders > All sales orders**.</span></span>
14. <span data-ttu-id="f860d-132">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f860d-132">In the list, mark the selected row.</span></span> <span data-ttu-id="f860d-133">Zamówienia, które są obecnie wstrzymane, mają zaznaczone pola „Nie przetwarzaj” i „Wstrzymanie”.</span><span class="sxs-lookup"><span data-stu-id="f860d-133">Orders that are currently on hold have the "Do not process" and "Hold" fields marked.</span></span>
15. <span data-ttu-id="f860d-134">W okienku akcji kliknij opcję **Pobierz i zapakuj**.</span><span class="sxs-lookup"><span data-stu-id="f860d-134">On the Action Pane, click **Pick and pack**.</span></span>

## <a name="manage-order-holds"></a><span data-ttu-id="f860d-135">Zarządzanie wstrzymaniami zamówień</span><span class="sxs-lookup"><span data-stu-id="f860d-135">Manage order holds</span></span>
1. <span data-ttu-id="f860d-136">Wybierz kolejno opcje **Sprzedaż i marketing > Zamówienia sprzedaży > Otwarte zamówienia > Wstrzymania zamówień**.</span><span class="sxs-lookup"><span data-stu-id="f860d-136">Go to **Sales and marketing > Sales orders > Open orders > Order holds**.</span></span> <span data-ttu-id="f860d-137">Strona **Wstrzymania zamówień** pełni rolę pulpitu, gdzie można uzyskać przegląd wszystkich bieżących i przetworzonych wstrzymań oraz obsługiwać te wstrzymania i skojarzone z nimi zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f860d-137">**Order holds** page functions as a workbench where you can get an overview of all the current and processed holds, and handle them and associated sales orders.</span></span>     
2. <span data-ttu-id="f860d-138">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f860d-138">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="f860d-139">W **okienku akcji** kliknij pozycję **Wyewidencjonowanie wstrzymanych**.</span><span class="sxs-lookup"><span data-stu-id="f860d-139">On the **Action Pane**, click **Hold checkout**.</span></span>
4. <span data-ttu-id="f860d-140">Kliknij opcję **Wyewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="f860d-140">Click **Check out**.</span></span>
5. <span data-ttu-id="f860d-141">Na liście usuń oznaczenie wybranego wiersza.</span><span class="sxs-lookup"><span data-stu-id="f860d-141">In the list, unmark the selected row.</span></span> <span data-ttu-id="f860d-142">Pole **Wyewidencjonuj do** teraz zawiera Twój identyfikator użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f860d-142">The **Checkout out to** field now shows your user ID.</span></span>   
6. <span data-ttu-id="f860d-143">Kliknij opcję **Wyczyść wyewidencjonowanie**.</span><span class="sxs-lookup"><span data-stu-id="f860d-143">Click **Clear checkout**.</span></span>
7. <span data-ttu-id="f860d-144">W **okienku akcji** kliknij pozycję **Wyczyść wstrzymanie**.</span><span class="sxs-lookup"><span data-stu-id="f860d-144">On the **Action Pane**, click **Clear hold**.</span></span>
    - <span data-ttu-id="f860d-145">Jeśli chcesz usunąć blokadę i pozwolić na przejście zamówienia do następnego etapu realizacji, musisz wyczyścić wstrzymanie.</span><span class="sxs-lookup"><span data-stu-id="f860d-145">When you are ready to remove the hold and allow the order to proceed to the next fulfilment step, you must clear the hold.</span></span> <span data-ttu-id="f860d-146">Jeżeli zamówienie nie wymaga żadnych zmian, można uruchomić akcję Usuń wstrzymania.</span><span class="sxs-lookup"><span data-stu-id="f860d-146">If the order requires no changes, you can run the Clear holds action.</span></span> <span data-ttu-id="f860d-147">Można jednak użyć operacji Usuń i modyfikuj, jeśli podczas usuwania blokady okaże się, że zamówienie musi zostać zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="f860d-147">However, you can use the Clear and modify action if, when clearing a hold, the order has to be updated.</span></span>      
    - <span data-ttu-id="f860d-148">Operacja **Usuń i prześlij** ma zastosowanie tylko w przypadku korzystania z funkcji Biuro obsługi.</span><span class="sxs-lookup"><span data-stu-id="f860d-148">The **Clear and submit** action is only applicable when you use Call center functionality.</span></span>  
8. <span data-ttu-id="f860d-149">Kliknij opcję **Usuń wstrzymania**.</span><span class="sxs-lookup"><span data-stu-id="f860d-149">Click **Clear holds**.</span></span> <span data-ttu-id="f860d-150">Wstrzymanie zostało zdjęte z zamówienia i usunięte z listy aktywnych wstrzymań.</span><span class="sxs-lookup"><span data-stu-id="f860d-150">The hold has now been cleared from the order and removed from the list of Active holds.</span></span> <span data-ttu-id="f860d-151">Aby wyświetlić wszystkie wstrzymania lub ich podzbiór zgodnie z określonym stanem, zmień wartość w polu Pokaż.</span><span class="sxs-lookup"><span data-stu-id="f860d-151">To see all the holds or their subset according to a specific status, change the value in the Show field.</span></span>     

