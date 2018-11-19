---
title: "Faktury dla odbiorcy i zwrotne zamówienia sprzedaży w aplikacji Retail w krajach środkowoeuropejskich"
description: "W tym temacie opisano sposób konfigurowania informacji do faktur dla odbiorców i zwrotnych zamówień sprzedaży w krajów środkowoeuropejskich."
author: epopov
manager: annbe
ms.date: 10/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: 01239f0eff3e59f62188fca64f99e93be843d2e2
ms.openlocfilehash: 20ae19fb03acb075b6553b95808779c905bcd31b
ms.contentlocale: pl-pl
ms.lasthandoff: 10/24/2018

---

# <a name="retail-customer-invoices-and-return-sales-orders-in-eastern-european-countries"></a><span data-ttu-id="c185e-103">Faktury dla odbiorcy i zwrotne zamówienia sprzedaży w aplikacji Retail w krajach środkowoeuropejskich</span><span class="sxs-lookup"><span data-stu-id="c185e-103">Retail customer invoices and return sales orders in Eastern European countries</span></span>


[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c185e-104">W tym temacie opisano sposób konfigurowania informacji do faktur dla odbiorców i zwrotnych zamówień sprzedaży w krajów środkowoeuropejskich.</span><span class="sxs-lookup"><span data-stu-id="c185e-104">This topic describes how to set up information for customer invoices and return sales orders in Eastern European countries.</span></span>

<span data-ttu-id="c185e-105">Można skonfigurować następujące informacje dla faktur dla odbiorcy i zwrotnych zamówień sprzedaży, które są generowane w aplikacji Retail Point of Sale (POS):</span><span class="sxs-lookup"><span data-stu-id="c185e-105">You can set up the following information for customer invoices and return sales orders that are generated in Retail point of sale (POS).</span></span>

- <span data-ttu-id="c185e-106">Można użyć grup podatków do przetwarzania zwrotów za pomocą zwrotnych zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c185e-106">You can use sales tax groups to process returns by using return sales orders.</span></span> <span data-ttu-id="c185e-107">Kliknij kolejno opcje **Handel detaliczny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="c185e-107">Go to **Retail > Headquarters setup > Parameters > Retail parameters**.</span></span> <span data-ttu-id="c185e-108">Otwórz kartę **Księgowanie > Faktura**, a następnie ustaw opcję **Użyj grupy podatków dla zwrotów** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c185e-108">Open the **Posting > Invoice** tab, and then set **Use sales tax group for returns** to **Yes**.</span></span> 

  * <span data-ttu-id="c185e-109">Aby określić grupę podatków dla zwrotów dokonywanych przez odbiorcę, na stronie **Odbiorcy** na skróconej karcie **Handel detaliczny** w polu **Grupa podatków dla zwrotów** wybierz grupę podatków.</span><span class="sxs-lookup"><span data-stu-id="c185e-109">To specify the sales tax group for returns that are made by a customer, on the **Customers** page, on the **Retail** FastTab, in the **Sales tax group for returns** field, select a sales tax group.</span></span> <span data-ttu-id="c185e-110">Podczas księgowania zwrotnego zamówienia sprzedaży dla wybranego odbiorcy wiersz zwrotnego zamówienia sprzedaży zostanie zaktualizowany przez grupę podatków dla zwrotów, którą określono w formularzu **Odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="c185e-110">When you post a return sales order for a customer, the return sales order line is updated with the sales tax group for returns that is specified in the **Customers** form.</span></span>
  
  * <span data-ttu-id="c185e-111">Aby określić grupę podatków dla zwrotów dokonywanych przez odbiorcę w aplikacji POS w punkcie sprzedaży, na stronie **Sklepy** na skróconej karcie **Ogólne** w polu **Grupa podatków dla zwrotów** wybierz grupę podatków.</span><span class="sxs-lookup"><span data-stu-id="c185e-111">To specify a sales tax group for returns that are made at a retail POS by a customer, on the **Stores** page, on the **General** FastTab, in the **Sales tax group for returns** field, select a sales tax group.</span></span> <span data-ttu-id="c185e-112">Podczas księgowania zwrotnego zamówienia sprzedaży dla odbiorcy ze sklepu sieci sprzedaży wiersz zwrotnego zamówienia sprzedaży zostanie zaktualizowany przez grupę podatków dla zwrotów, którą określono na stronie **Sklepy**.</span><span class="sxs-lookup"><span data-stu-id="c185e-112">When you post a return sales order for a customer of a retail store, the return sales order line is updated with the sales tax group for returns that are specified on the **Stores** page.</span></span>

- <span data-ttu-id="c185e-113">Można użyć daty księgowania faktury dla odbiorcy sieci sprzedaży lub zwrotnego zamówienia sprzedaży jako daty faktury sprzedaży lub zwrotu, jeśli faktura lub zwrot nie ma domyślnej daty sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c185e-113">You can use the posting date of a retail customer invoice or a return sales order as the sales date of the invoice or return if the invoice or return does not have a default sales date.</span></span> <span data-ttu-id="c185e-114">Kliknij kolejno opcje **Handel detaliczny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="c185e-114">Go to **Retail > Headquarters setup > Parameters > Retail parameters**.</span></span> <span data-ttu-id="c185e-115">Otwórz kartę **Księgowanie > Faktura**, a następnie ustaw opcję **Użyj daty księgowania jako daty sprzedaży** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c185e-115">Open the **Posting > Invoice** tab, and then set **Use posting date as sales date** to **Yes**.</span></span>

- <span data-ttu-id="c185e-116">Można użyć zakresu numerów dostarczonego przez urzędy skarbowe w celu numerowania faktur dla odbiorcy z Łotwy i Litwy i zwrotnych zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c185e-116">You can use the number range that is provided by the tax authorities to number Latvian and Lithuanian customer invoices and return sales orders.</span></span> 

  * <span data-ttu-id="c185e-117">Wybierz kolejno opcje **Administrowanie organizacją > Sekwencje numerów > Zarządzanie licznikami**.</span><span class="sxs-lookup"><span data-stu-id="c185e-117">Go to **Organization administration > Number sequences > Counters management**.</span></span> <span data-ttu-id="c185e-118">Powinien istnieć rekord, gdzie **Moduł** = **Sprzedaż**, a **Typ** = **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="c185e-118">There should be a record where **Module** = **Sales** and **Type** = **Invoice**.</span></span>

  * <span data-ttu-id="c185e-119">Wybierz kolejno opcje **Administrowanie organizacją > Sekwencje numerów > Konfiguracja numerowania faktur**.</span><span class="sxs-lookup"><span data-stu-id="c185e-119">Go to **Organization administration > Number sequences > Invoice numbering setup**.</span></span> <span data-ttu-id="c185e-120">Zaznacz pole wyboru **Handel detaliczny** dla wiersza numeracji używanego do numerowania faktur dla odbiorców.</span><span class="sxs-lookup"><span data-stu-id="c185e-120">Select the **Retail** check box for the number sequence line that is used to number the customer invoices.</span></span>

