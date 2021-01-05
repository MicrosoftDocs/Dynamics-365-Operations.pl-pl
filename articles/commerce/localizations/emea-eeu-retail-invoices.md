---
title: Faktury dla odbiorcy i zwrotne zamówienia sprzedaży w krajach wschodnioeuropejskich
description: W tym temacie opisano sposób konfigurowania informacji do faktur dla odbiorców i zwrotnych zamówień sprzedaży w krajów środkowoeuropejskich.
author: epopov
manager: annbe
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: a00a960142b0e3955c80d75f7963f4827209bf75
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408362"
---
# <a name="customer-invoices-and-return-sales-orders-in-eastern-european-countries"></a><span data-ttu-id="bff57-103">Faktury dla odbiorcy i zwrotne zamówienia sprzedaży w krajach wschodnioeuropejskich</span><span class="sxs-lookup"><span data-stu-id="bff57-103">Customer invoices and return sales orders in Eastern European countries</span></span>


[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bff57-104">W tym temacie opisano sposób konfigurowania informacji do faktur dla odbiorców i zwrotnych zamówień sprzedaży w krajów środkowoeuropejskich.</span><span class="sxs-lookup"><span data-stu-id="bff57-104">This topic describes how to set up information for customer invoices and return sales orders in Eastern European countries.</span></span>

<span data-ttu-id="bff57-105">Można skonfigurować następujące informacje dla faktur dla odbiorcy i zwrotnych zamówień sprzedaży, które są generowane w aplikacji Retail Point of Sale (POS):</span><span class="sxs-lookup"><span data-stu-id="bff57-105">You can set up the following information for customer invoices and return sales orders that are generated in Retail point of sale (POS).</span></span>

- <span data-ttu-id="bff57-106">Można użyć grup podatków do przetwarzania zwrotów za pomocą zwrotnych zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="bff57-106">You can use sales tax groups to process returns by using return sales orders.</span></span> <span data-ttu-id="bff57-107">Wybierz kolejno opcje **Commerce \> Ustawienia central \> Parametry \> Parametry Commerce**.</span><span class="sxs-lookup"><span data-stu-id="bff57-107">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="bff57-108">Otwórz kartę **Księgowanie \> Faktura**, a następnie ustaw opcję **Użyj grupy podatków dla zwrotów** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="bff57-108">Open the **Posting \> Invoice** tab, and then set **Use sales tax group for returns** to **Yes**.</span></span>

    * <span data-ttu-id="bff57-109">Aby określić grupę podatków dla zwrotów dokonywanych przez odbiorcę, na stronie **Odbiorcy** na skróconej karcie **Commerce** w polu **Grupa podatków dla zwrotów** wybierz grupę podatków.</span><span class="sxs-lookup"><span data-stu-id="bff57-109">To specify the sales tax group for returns that are made by a customer, on the **Customers** page, on the **Commerce** FastTab, in the **Sales tax group for returns** field, select a sales tax group.</span></span> <span data-ttu-id="bff57-110">Podczas księgowania zwrotnego zamówienia sprzedaży dla wybranego odbiorcy wiersz zwrotnego zamówienia sprzedaży zostanie zaktualizowany przez grupę podatków dla zwrotów, którą określono w formularzu **Odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="bff57-110">When you post a return sales order for a customer, the return sales order line is updated with the sales tax group for returns that is specified in the **Customers** form.</span></span>
    * <span data-ttu-id="bff57-111">Aby określić grupę podatków dla zwrotów dokonywanych przez odbiorcę w aplikacji POS w punkcie sprzedaży, na stronie **Sklepy** na skróconej karcie **Ogólne** w polu **Grupa podatków dla zwrotów** wybierz grupę podatków.</span><span class="sxs-lookup"><span data-stu-id="bff57-111">To specify a sales tax group for returns that are made at a retail POS by a customer, on the **Stores** page, on the **General** FastTab, in the **Sales tax group for returns** field, select a sales tax group.</span></span> <span data-ttu-id="bff57-112">Podczas księgowania zwrotnego zamówienia sprzedaży dla odbiorcy ze sklepu wiersz zwrotnego zamówienia sprzedaży zostanie zaktualizowany przez grupę podatków dla zwrotów, którą określono na stronie **Sklepy**.</span><span class="sxs-lookup"><span data-stu-id="bff57-112">When you post a return sales order for a customer of a  store, the return sales order line is updated with the sales tax group for returns that are specified on the **Stores** page.</span></span>

- <span data-ttu-id="bff57-113">Można użyć daty księgowania faktury dla odbiorcy sieci sprzedaży lub zwrotnego zamówienia sprzedaży jako daty faktury sprzedaży lub zwrotu, jeśli faktura lub zwrot nie ma domyślnej daty sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="bff57-113">You can use the posting date of a customer invoice or a return sales order as the sales date of the invoice or return if the invoice or return does not have a default sales date.</span></span> <span data-ttu-id="bff57-114">Wybierz kolejno opcje **Commerce \> Ustawienia central \> Parametry \> Parametry Commerce**.</span><span class="sxs-lookup"><span data-stu-id="bff57-114">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="bff57-115">Otwórz kartę **Księgowanie \> Faktura**, a następnie ustaw opcję **Użyj daty księgowania jako daty sprzedaży** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="bff57-115">Open the **Posting \> Invoice** tab, and then set **Use posting date as sales date** to **Yes**.</span></span>
- <span data-ttu-id="bff57-116">Można użyć zakresu numerów dostarczonego przez urzędy skarbowe w celu numerowania faktur dla odbiorcy z Łotwy i Litwy i zwrotnych zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="bff57-116">You can use the number range that is provided by the tax authorities to number Latvian and Lithuanian customer invoices and return sales orders.</span></span>

    * <span data-ttu-id="bff57-117">Wybierz kolejno opcje **Administrowanie organizacją \> Sekwencje numerów \> Zarządzanie licznikami**.</span><span class="sxs-lookup"><span data-stu-id="bff57-117">Go to **Organization administration \> Number sequences \> Counters management**.</span></span> <span data-ttu-id="bff57-118">Powinien istnieć rekord, gdzie **Moduł** = **Sprzedaż**, a **Typ** = **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="bff57-118">There should be a record where **Module** = **Sales** and **Type** = **Invoice**.</span></span>
    * <span data-ttu-id="bff57-119">Wybierz kolejno opcje **Administrowanie organizacją \> Sekwencje numerów \> Konfiguracja numerowania faktur**.</span><span class="sxs-lookup"><span data-stu-id="bff57-119">Go to **Organization administration \> Number sequences \> Invoice numbering setup**.</span></span> <span data-ttu-id="bff57-120">Zaznacz pole wyboru **Hande** dla wiersza numeracji używanego do numerowania faktur dla odbiorców.</span><span class="sxs-lookup"><span data-stu-id="bff57-120">Select the **Commerce** check box for the number sequence line that is used to number the customer invoices.</span></span>
