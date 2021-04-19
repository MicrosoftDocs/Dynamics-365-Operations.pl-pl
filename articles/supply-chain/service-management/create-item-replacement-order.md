---
title: Tworzenie zamówienia wymiany towaru
description: Zamówienia zwrotu towaru tworzy się zazwyczaj po odebraniu i sprawdzeniu zwróconego towaru.
author: josaw1
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 95227bbcb71a4c446b9d10cc0447bf2e64c6ef80
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840516"
---
# <a name="create-an-item-replacement-order"></a><span data-ttu-id="f21b7-103">Tworzenie zamówienia wymiany towaru</span><span class="sxs-lookup"><span data-stu-id="f21b7-103">Create an item replacement order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f21b7-104">Zamówienia zwrotu towaru tworzy się zazwyczaj po odebraniu i sprawdzeniu zwróconego towaru.</span><span class="sxs-lookup"><span data-stu-id="f21b7-104">Item replacement orders are usually created after a product is returned and inspected.</span></span> <span data-ttu-id="f21b7-105">Jeśli jednak towar musi być wymieniony przed zwrotem lub jeśli pierwszy towar nie został zwrócony, natychmiast po utworzeniu zamówienia zwrotu można utworzyć zamówienie wymiany towaru.</span><span class="sxs-lookup"><span data-stu-id="f21b7-105">However, when an item must be replaced before it has been returned, or when the original item will not be returned, you can create an item replacement order immediately after you create a return order.</span></span>

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a><span data-ttu-id="f21b7-106">Utwórz zamówienie wymiany po otrzymaniu towary, który jest zwracany.</span><span class="sxs-lookup"><span data-stu-id="f21b7-106">Create a replacement order after you receive an item that is returned</span></span>

1.  <span data-ttu-id="f21b7-107">Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="f21b7-107">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="f21b7-108">Utwórz nowe zamówienie zwrotu lub wybierz zwrócony towar z listy, aby otworzyć formularz **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="f21b7-108">Create a new return order, or select a returned order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="f21b7-109">Kliknij opcję **Wiersz zwrotu**, a następnie wybierz opcję **Pozycja zastępcza**.</span><span class="sxs-lookup"><span data-stu-id="f21b7-109">Click **Return line**, and then select **Replacement item**.</span></span>

4.  <span data-ttu-id="f21b7-110">Wybierz towar do zastępowania zwróconych towarów.</span><span class="sxs-lookup"><span data-stu-id="f21b7-110">Select the item to replace the returned item with.</span></span> <span data-ttu-id="f21b7-111">Wprowadź specyfikacje towaru, a następnie kliknij przycisk **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="f21b7-111">Enter the item specifications, and then click **Apply**.</span></span>

5.  <span data-ttu-id="f21b7-112">Kliknij opcję **Dokument dostawy**, aby wygenerować dokument dostawy dla zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="f21b7-112">Click **Packing slip** to generate the packing slip for the return order.</span></span> <span data-ttu-id="f21b7-113">Zamówienie sprzedaży jest generowane dla wybranego towaru zastępczego.</span><span class="sxs-lookup"><span data-stu-id="f21b7-113">A sales order is generated for the replacement item that you selected.</span></span>
    
    <span data-ttu-id="f21b7-114">Po utworzeniu zamówienia sprzedaży dla towaru zastępczego następuje automatyczne wyszukiwanie umów sprzedaży, a jeśli istnieje odpowiednia umowa sprzedaży, zostanie zastosowana do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f21b7-114">After the sales order is created for the replacement item, sales agreements are automatically searched and if there is an applicable sales agreement, it is applied to the sales order.</span></span>

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a><span data-ttu-id="f21b7-115">Utwórz zamówienie wymiany, zanim pojawi się towar, który powinien być zwrócony</span><span class="sxs-lookup"><span data-stu-id="f21b7-115">Create a replacement order before you receive an item that will be returned</span></span>

1.  <span data-ttu-id="f21b7-116">Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="f21b7-116">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="f21b7-117">Utwórz nowe zamówienie zwrotu lub wybierz zwrócony towar z listy, aby otworzyć formularz **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="f21b7-117">Create a new return order, or select a return order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="f21b7-118">Kliknij przycisk **Znajdź zamówienie sprzedaży**, jeśli chcesz zidentyfikować zamówienie sprzedaży dla zwróconego towaru.</span><span class="sxs-lookup"><span data-stu-id="f21b7-118">Click **Find sales order** if you want to identify the sales order for the returned item.</span></span> <span data-ttu-id="f21b7-119">Wypełnij formularz **Znajdź zamówienie sprzedaży**, a następnie kliknij przycisk **OK**. Formularz zostanie zamknięty i nastąpi powrót do formularza **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="f21b7-119">Complete the **Find sales order** form and then click **OK** to close the form and return to the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="f21b7-120">Wiersz zamówienia sprzedaży dla zwróconego towaru jest kopiowany do zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="f21b7-120">The sales order line for the returned item is copied to the return order.</span></span>

4.  <span data-ttu-id="f21b7-121">Kliknij przycisk **Zamówienie wymiany**, a zostanie otwarty formularz **Tworzenie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f21b7-121">Click **Replacement order** to open the **Create sales order** form.</span></span>

5.  <span data-ttu-id="f21b7-122">Zaznacz pole wyboru **Kopiuj wiersze zamówienia zwrotu**, aby przesłać dane z zamówienia zwrotu wybranego w formularzu **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2** do tego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f21b7-122">Select the **Copy return order lines** check box to transfer details from the return order you selected on the **Return order - RMA number: %1, %2** form to this sales order.</span></span>

6.  <span data-ttu-id="f21b7-123">Odpowiednio do potrzeb wprowadź lub zmodyfikuj szczegóły.</span><span class="sxs-lookup"><span data-stu-id="f21b7-123">Enter or modify details, as required.</span></span>
    
    <span data-ttu-id="f21b7-124">Jeśli określono zamówienie sprzedaży w kroku 3 i jeśli wiersz zamówienia sprzedaży dla zwróconego towaru jest połączony z umową sprzedaży, identyfikator odpowiedniej umowy sprzedaży stosowany dla zamówienia wymiany towaru będzie automatycznie wyświetlany w polu **Identyfikator umowy sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="f21b7-124">If you identified the sales order in step 3, and if the sales order line for the returned item is linked to a sales agreement, the identifier of the applicable sales agreement for the item replacement order will be automatically displayed in the **Sales agreement ID** field.</span></span>

7.  <span data-ttu-id="f21b7-125">Kliknij przycisk **OK**, aby zamknąć formularz **Tworzenie zamówienia sprzedaży** i otworzyć formularz **Zamówienie sprzedaży**, w którym można kontynuować wprowadzanie danych nowego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f21b7-125">Click **OK** to close the **Create sales order** form and open the **Sales order** form, where you can continue to enter information for the new sales order.</span></span> <span data-ttu-id="f21b7-126">Wszelkie obowiązujące wiersze zamówienia zwrotu zostaną skopiowane do nowego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f21b7-126">Any applicable return order lines will be copied to the new sales order.</span></span> 
    
    <span data-ttu-id="f21b7-127">Jeżeli identyfikator umowy sprzedaży jest automatycznie wyświetlany w polu **Identyfikator umowy sprzedaży**, to umowa sprzedaży została połączona z nagłówkiem zamówienia sprzedaży dla zamówienia wymiany towaru.</span><span class="sxs-lookup"><span data-stu-id="f21b7-127">If the identifier of the sales agreement is automatically displayed in the **Sales agreement ID** field, then the sales agreement has been linked to the sales order header for the item replacement order.</span></span> <span data-ttu-id="f21b7-128">W przypadku istnienia zobowiązania w umowie sprzedaży, które nie zostało jeszcze wypełnione, gdy zamówienie sprzedaży jest tworzone, zanim umowa sprzedaży stracił ważność, ustal, co łączy wiersz umowy sprzedaży i wiersz zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f21b7-128">If there is an applicable commitment in the sales agreement that has not been fulfilled yet, and the sales order is created before the sales agreement expires, a link is established between the sales agreement line and the sales order line.</span></span> <span data-ttu-id="f21b7-129">Dlatego informacje z umowy sprzedaży, np. cena towaru, kopiowane są fo nowego wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f21b7-129">Therefore, information from the sales agreement, such as item price, is copied to the new sales order line.</span></span> 
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]