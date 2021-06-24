---
title: Zmień tryb dostawy w punkcie sprzedaży
description: W tym temacie opisano sposób konfigurowania i używania trybu zmiany dostawy w punkcie sprzedaży.
author: hhainesms
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: fd69d82536047c06e94ba4a7e860ef54680619a4
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193138"
---
# <a name="change-mode-of-delivery-in-pos"></a><span data-ttu-id="c3848-103">Zmień tryb dostawy w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c3848-103">Change mode of delivery in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c3848-104">W tym temacie opisano sposób konfigurowania funkcji „Zmień tryb dostawy” w środowisku punktu sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="c3848-104">This topic describes how to set up and use the "change mode of delivery" functionality in your point of sale (POS) environment.</span></span> 

<span data-ttu-id="c3848-105">W wersjach 10.0.10 i nowszych rozwiązania Dynamics 365 Commerce jest dostępna operacja **Zmień tryb dostawy** (647), którą można dodać do układów ekranu punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c3848-105">In Dynamics 365 Commerce versions 10.0.10 and later, the **Change mode of delivery** operation (647) is available to add to your POS screen layouts.</span></span>

<span data-ttu-id="c3848-106">Funkcja „Zmień metodę dostawy” umożliwia zmianę metody dostawy dla jednej lub większej liczby skonfigurowanych dla wysyłki wierszy sprzedaży w transakcji punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c3848-106">The change mode of delivery feature provides you with the option to change the mode of delivery for one or more shipment-configured sales lines on the POS transaction.</span></span> <span data-ttu-id="c3848-107">W poprzednich wersjach rozwiązania Commerce należało przejść przez pełne konfiguracje **Wyślij wszystko** lub **Wyślij wybrane**, by zmienić metodę dostawy w istniejącym wierszu, który został skonfigurowany do wysyłki.</span><span class="sxs-lookup"><span data-stu-id="c3848-107">In previous versions of Commerce, you had to go through the full **Ship all** or **Ship selected** configuration flows if you wanted to change the mode of delivery on an existing line that was configured for shipment.</span></span> <span data-ttu-id="c3848-108">Ten proces był czasochłonny i mógł powodować przypadkowe zmiany w pochodzeniu lub dacie dostawy dla wiersza.</span><span class="sxs-lookup"><span data-stu-id="c3848-108">This process was time consuming and could result in accidental changes to the delivery origin or delivery dates for the line.</span></span> <span data-ttu-id="c3848-109">Nowa funkcjonalność stanowi alternatywną metodę efektywnego aktualizowania metody dostawy w tych wierszach sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c3848-109">The new functionality provides an alternative method for efficiently updating the mode of delivery on these sales lines.</span></span>

<span data-ttu-id="c3848-110">Aby uzyskać więcej informacji o dodawaniu operacji do przycisku w siatce przycisków punktu sprzedaży, należy zapoznać się z tematami dotyczącymi [układu ekranu dla punktu sprzedaży](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="c3848-110">For more information about how to add an operation to a button on your POS button grid, see [Screen layouts for the point of sale](pos-screen-layouts.md).</span></span>

<span data-ttu-id="c3848-111">Po skonfigurowaniu tej funkcji w punkcie sprzedaży po wybraniu opcji **Zmień tryb dostawy** zostanie wyświetlona strona listy umożliwiająca wybranie wierszy transakcji, dla których ma zostać zmieniona metoda dostawy.</span><span class="sxs-lookup"><span data-stu-id="c3848-111">After this feature is configured in POS, when you select **Change mode of delivery**, you will be presented with a list page that allows you to choose the lines of the transaction that you want to change the mode of delivery for.</span></span> <span data-ttu-id="c3848-112">Można wybrać niektóre lub wszystkie wiersze albo wyjść bez wprowadzania zmian.</span><span class="sxs-lookup"><span data-stu-id="c3848-112">You can choose some or all of the lines, or exit without making any changes.</span></span> <span data-ttu-id="c3848-113">Wiersze sprzedaży, które zostały wcześniej skonfigurowane dla wysyłki, są jedynymi wierszami na liście, które można zmienić.</span><span class="sxs-lookup"><span data-stu-id="c3848-113">The sales lines that were previously configured for shipment are the only lines in the list that you can change.</span></span> <span data-ttu-id="c3848-114">Aby zmienić wiersz przeznaczony do pobrania lub wyniesienia do wysyłki, należy użyć operacji **Wyślij wszystko** lub **Wyślij wybrane**.</span><span class="sxs-lookup"><span data-stu-id="c3848-114">If you want to change a line designated for pickup or carryout to ship, you must use the **Ship all** or **Ship selected** operations.</span></span> <span data-ttu-id="c3848-115">Aby zmienić wiersz wyznaczony jako wysyłka na pobrania lub wyniesienia, należy skorzystać z operacji pobrania **Odbierz wszystkie**, **Odbierz wybrane**, **Wynieś wszystkie** lub **Wynieś wybrane**.</span><span class="sxs-lookup"><span data-stu-id="c3848-115">Conversely, if you want to change a line designated as a shipment to a pickup or carryout, you must use the  **Pickup all**, **Pickup selected**, **Carryout all**, or **Carryout selected** operations.</span></span>

<span data-ttu-id="c3848-116">Po wybraniu wierszy, które chcesz zmienić, kliknij przycisk **Zmień tryb dostawy**, aby wyświetlić monit o wybranie opcji trybu dostawy.</span><span class="sxs-lookup"><span data-stu-id="c3848-116">After you select the lines that you want to change, click **Change mode of delivery** to be prompted to select the delivery mode options.</span></span> <span data-ttu-id="c3848-117">Jeśli wybrano wiele wierszy do zmiany, w punkcie sprzedaży będą wyświetlane tylko metody dostaw, które zostały skonfigurowane jako dozwolone dla wszystkich wybranych produktów.</span><span class="sxs-lookup"><span data-stu-id="c3848-117">If you selected multiple lines to change, POS will only display modes of delivery that have been configured as allowable for all of the selected products.</span></span> <span data-ttu-id="c3848-118">Metody dostawy można skonfigurować w taki sposób, aby obsługiwały określone produkty i adresy dostaw.</span><span class="sxs-lookup"><span data-stu-id="c3848-118">Modes of delivery can be configured to support specific products and delivery addresses.</span></span> <span data-ttu-id="c3848-119">Jeśli istnieje metoda dostawy, która jest akceptowana dla jednej kombinacji produktów i adresu, ale nie jest akceptowana dla innej wybranej kombinacji produktu i adresu, metoda dostawy jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="c3848-119">If there is a mode of delivery that is acceptable for one product and address combination but is not acceptable for another selected product and address combination, the mode of delivery is not available.</span></span> <span data-ttu-id="c3848-120">Aby wybrać metodę dostawy dla jednego produktu, który nie jest obsługiwany przez inny produkt, należy wybrać wiersze jeden według jednego i zmienić tryb dostawy dla każdego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c3848-120">You may need to select lines one by one and change the mode of delivery for each line separately if you want to select a mode of delivery for one product that is not supported by another product.</span></span>  

<span data-ttu-id="c3848-121">Po wybraniu nowej metody dostawy zostanie wyświetlona strona transakcji.</span><span class="sxs-lookup"><span data-stu-id="c3848-121">After you select the new mode of delivery, the transaction page is displayed.</span></span> <span data-ttu-id="c3848-122">Aby przejrzeć nowe wybory trybu dostawy, wybierz kartę **dostawa** na liście transakcji.</span><span class="sxs-lookup"><span data-stu-id="c3848-122">To review your new delivery mode selections, select the **Delivery** tab on the transaction list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3848-123">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c3848-123">Additional resources</span></span>

[<span data-ttu-id="c3848-124">Tworzenie zamówień w biurach obsługi</span><span class="sxs-lookup"><span data-stu-id="c3848-124">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="c3848-125">Dostosowywanie wiadomości e-mail dotyczących transakcji według metod dostawy</span><span class="sxs-lookup"><span data-stu-id="c3848-125">Customize transactional emails by mode of delivery</span></span>](customize-email-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]