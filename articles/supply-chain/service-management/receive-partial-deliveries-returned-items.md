---
title: Odbieranie częściowych dostaw zwracanych towarów
description: Dostawy częściowe są definiowane pod względem wierszy zamówienia zwrotu, a nie wysyłek zamówienia zwrotu.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf35169d8afd6e88b8ebe921514ed6d55607a4dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434970"
---
# <a name="receive-partial-deliveries-of-returned-items"></a><span data-ttu-id="5d7ce-103">Odbieranie częściowych dostaw zwracanych towarów</span><span class="sxs-lookup"><span data-stu-id="5d7ce-103">Receive partial deliveries of returned items</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5d7ce-104">Dostawy częściowe są definiowane pod względem wierszy zamówienia zwrotu, a nie wysyłek zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-104">Partial deliveries are defined in terms of return order lines, not return order shipments.</span></span>

<span data-ttu-id="5d7ce-105">Oznacza to, że jeśli zostanie przyjęta pełna ilość wskazana w jednym wierszu zamówienia zwrotu, ale nie zostanie przyjęte nic z jego pozostałych wierszy, dostawa nie jest dostawą częściową.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-105">This means that if you receive the full quantity that is indicated on one return order line, but you receive nothing from the other lines in the return order, the delivery is not a partial delivery.</span></span> <span data-ttu-id="5d7ce-106">Jeśli jednak wiersz zamówienia zwrotu wymaga zwrotu na przykład 10 jednostek określonego towaru, a zostaną przyjęte tylko cztery jednostki, dostawa jest dostawą częściową.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-106">However, if a return order line requires 10 units of a particular item to be returned, but you receive only four, it is a partial delivery.</span></span>

<span data-ttu-id="5d7ce-107">Jeśli wysyłka zwrotu zawiera ilość mniejszą niż pełna ilość wiersza zamówienia zwrotu, można odłożyć przetworzenie tej wysyłki i poczekać na przyjęcie pozostałej zwracanej ilości lub można zarejestrować i zaksięgować ilość częściową.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-107">If a return shipment contains less than the full quantity of a return order line, you can set the shipment aside and wait for the rest of the returned quantity to arrive, or you can register and post the partial quantity.</span></span>

## <a name="register-and-post-a-partial-quantity"></a><span data-ttu-id="5d7ce-108">Rejestrowanie i księgowanie ilości częściowej</span><span class="sxs-lookup"><span data-stu-id="5d7ce-108">Register and post a partial quantity</span></span>

1.  <span data-ttu-id="5d7ce-109">Po wybraniu zamówienia zwrotu do przyjęcia w formularzu **Przegląd przyjęć - magazyn: %1, dok: %2, nazwa arkusza: %3** kliknij przycisk **Rozpocznij przyjęcie**, aby utworzyć arkusz przywozu, a następnie kliknij kolejno opcje **Arkusze** \> **Pokaż arkusze przyjęcia**, aby otworzyć formularz **Arkusz lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-109">After you select a return order for arrival on the **Arrival overview - Warehouse: %1, Dock: %2, Journal name: %3** form, click **Start arrival** to create the arrival journal, and then click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>

2.  <span data-ttu-id="5d7ce-110">Wybierz wiersz arkusza, na którym chcesz pracować, a następnie kliknij przycisk **Wiersze**, aby otworzyć formularz **Wiersze arkusza, lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-110">Select the line of the journal that you want to work with, and then click **Lines** to open the **Journal lines, locations** form.</span></span>

3.  <span data-ttu-id="5d7ce-111">Wybierz wiersz numeru towaru, dla którego przywieziono tylko częściową ilość, a następnie kliknij kolejno opcje **Funkcje** \> **Podziel**, aby otworzyć formularz **Podział**.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-111">Select the line of the item number for which only a partial quantity has arrived, and then click **Functions** \> **Split** to open the **Split** form.</span></span>

4.  <span data-ttu-id="5d7ce-112">W polu **Podziel ilość** wpisz ilość określającą łączną liczbę otrzymanych towarów, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-112">In the **Split quantity** field, enter the quantity for the total number of items that have been received, and then click **OK**.</span></span>

5.  <span data-ttu-id="5d7ce-113">W formularzu **Wiersze arkusza, lokalizacje** wybierz wiersz ilości przywiezionych towarów, a następnie kliknij przycisk **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-113">On the **Journal lines, locations** form, select the line for the quantity of items that has arrived, and then click **Post**.</span></span> <span data-ttu-id="5d7ce-114">Po przywozie kolejnych towarów można zaksięgować wiersz dodatkowej ilości.</span><span class="sxs-lookup"><span data-stu-id="5d7ce-114">You can post the line for the additional quantity after the items have arrived.</span></span>




