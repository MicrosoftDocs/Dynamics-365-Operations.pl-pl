---
title: "Hybrydowe zamówienia odbiorców"
description: "Hybrydowe zamówienie odbiorcy to pojedyncze zamówienie zawierające produkty, które mogą być wyniesione ze sklepu przez odbiorcę, a także produktów, które zostaną odebrane lub wysłane później."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 88d12641fa05953f7082158303237b7ba40c3fe2
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="hybrid-customer-orders"></a><span data-ttu-id="1972f-103">Hybrydowe zamówienia odbiorców</span><span class="sxs-lookup"><span data-stu-id="1972f-103">Hybrid customer orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1972f-104">Hybrydowe zamówienie odbiorcy to pojedyncze zamówienie zawierające produkty, które mogą być wyniesione ze sklepu przez odbiorcę, a także produktów, które zostaną odebrane lub wysłane później.</span><span class="sxs-lookup"><span data-stu-id="1972f-104">A hybrid customer order is a single order, which contains products that can be carried out of the store by the customer, as well as products that will be picked up or shipped later.</span></span>

<span data-ttu-id="1972f-105">W programie Microsoft Dynamics 365 for Retail można wybrać opcję wyniesienia wszystkich produktów lub wyniesienia tylko wybranych produktów dla zamówienia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="1972f-105">In Microsoft Dynamics 365 for Retail, you can select either carry out all products or carry out selected products for a customer order.</span></span> <span data-ttu-id="1972f-106">Wiersze produktów oznaczone jako wynoszone są automatycznie fakturowane po utworzeniu zamówienia, podobnie jak w innym zamówieniu, którego towary mają być odbierane bezpośrednio po utworzeniu zamówienia.</span><span class="sxs-lookup"><span data-stu-id="1972f-106">The product lines that are marked as carry out are automatically invoiced after the order is created, similarly this is the same for an order that is to be picked-up after the order is created.</span></span> <span data-ttu-id="1972f-107">Wysokość kwoty należnej w zamówieniach hybrydowych jest określana przez dodanie procentu wpłaty do wierszy pobrania i wysłania produktów, a pełna kwota jest dodawana do wierszy wynoszonych produktów.</span><span class="sxs-lookup"><span data-stu-id="1972f-107">The amount due on hybrid orders is determined by adding the deposit percentage on pick and ship product lines with the full amount of the carry out lines.</span></span> <span data-ttu-id="1972f-108">W zamówieniach hybrydowych system przełącza się między trybami zamówienia odbiorcy i wyniesienia w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1972f-108">For hybrid orders, the system switches between customer order mode and cash and carry mode as follows:</span></span>

-   <span data-ttu-id="1972f-109">Jeżeli wszystkie produkty w koszyku są ustawione jako **Dostawa przez wyniesienie**, zamówienie będzie realizowane jako transakcja zapłaty przy kasie i wychodzenia z produktami ze sklepu.</span><span class="sxs-lookup"><span data-stu-id="1972f-109">If all products in the cart are set to **Carry out delivery**, the order will be handled as a Cash and Carry transaction.</span></span>
-   <span data-ttu-id="1972f-110">Jeśli wszystkie lub którekolwiek wiersze w koszyku są ustawiony na **Pobieranie** lub **Dostawa przez wysyłkę**, zamówienie będzie obsługiwane jako transakcja zamówienia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="1972f-110">If any or all lines in the cart are set to either **Pick** or **ship delivery**, the order will be handled as a Customer order transaction.</span></span>

<span data-ttu-id="1972f-111">Po zaznaczeniu wiersza koszyka i wybraniu opcji **Wybierz zaznaczone**, **Wyślij wybrane** lub **Wynieś wybrane** tylko wskazany wiersz koszyka będzie miał ustawianą określoną metodę dostawy.</span><span class="sxs-lookup"><span data-stu-id="1972f-111">If a cart line is selected and **Pick selected**, **Ship selected**, or **Carry out selected** is selected, only the specific cart line is set with that delivery method.</span></span> <span data-ttu-id="1972f-112">W takim przypadku dalszy przepływ operacji jest kontynuowany w zwykły sposób.</span><span class="sxs-lookup"><span data-stu-id="1972f-112">In that case, the downstream flow of the operation continues as usual.</span></span> <span data-ttu-id="1972f-113">Jednak jeśli opcja **Wybierz zaznaczone**, **Wyślij wybrane** lub **Wynieś wybrane** zostanie wybrana bez zaznaczenia wiersza koszyka, zostanie otwarta nowa strona z listą wszystkich wierszy koszyka.</span><span class="sxs-lookup"><span data-stu-id="1972f-113">However, if **Pick selected**, **Ship selected**, or **Carry out selected** is selected without a cart line being selected, a new page opens that lists all the cart lines.</span></span> <span data-ttu-id="1972f-114">Na tym ekranie można wybrać wiele wierszy na raz i ustawić im metodę dostawy.</span><span class="sxs-lookup"><span data-stu-id="1972f-114">On that screen, you can select multiple lines at once for setting the delivery method.</span></span> <span data-ttu-id="1972f-115">Użycie tej metody do wybierania wierszy spowoduje zastąpienie wszystkich poprzednich metod dostawy przypisany do wierszy.</span><span class="sxs-lookup"><span data-stu-id="1972f-115">When you use that method for selecting lines, any previous delivery method that has been assigned to the line will be overridden.</span></span>

<a name="additional-resources"></a><span data-ttu-id="1972f-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1972f-116">Additional resources</span></span>
--------

[<span data-ttu-id="1972f-117">Omówienie zamówień odbiorców</span><span class="sxs-lookup"><span data-stu-id="1972f-117">Customer orders overview</span></span>](customer-orders-overview.md)




