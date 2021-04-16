---
title: Drukowanie raportu Płatności podatku według kodu
description: Ten temat zawiera informacje dotyczące ustawień i akcji wymaganych do wydrukowania raportu płatności podatku według kodu w walucie księgowania lub kodu podatku.
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: eb3ee4a12d2d29c2769f1ae22e11dc05608b47c1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815459"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a><span data-ttu-id="de8fa-103">Drukowanie raportu Płatności podatku według kodu</span><span class="sxs-lookup"><span data-stu-id="de8fa-103">Print the Sales tax payment by code report</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de8fa-104">Aby wydrukować raport **płatności podatku według kodu**, przejdź do **Podatek** \> **Zapytania i raporty** \> **Raporty podatków** \> **Płatności podatku według kodu**.</span><span class="sxs-lookup"><span data-stu-id="de8fa-104">To print the **Sales tax payment by code** report, go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span> <span data-ttu-id="de8fa-105">Domyślnie kwoty raportu są generowane w walucie rozliczeniowej firmy dla wszystkich kodów raportowania, które są konfigurowane na stronie **Kody raportowania podatku**.</span><span class="sxs-lookup"><span data-stu-id="de8fa-105">By default, report amounts are generated in the accounting currency of the legal entity for all reporting codes that are set up on the **Sales tax reporting codes** page.</span></span>

<span data-ttu-id="de8fa-106">Ten raport można również wygenerować, aby wyświetlić kwoty płatności podatku w walutach kodów podatków dla wszystkich kodów raportowania, które są przypisane do kodów podatków na stronie **Kody podatków**.</span><span class="sxs-lookup"><span data-stu-id="de8fa-106">You can also generate this report so that it shows the sales tax payment amounts in the currencies of sales tax codes for all reporting codes that are assigned to sales tax codes on the **Sales tax codes** page.</span></span>

## <a name="turn-on-the-feature"></a><span data-ttu-id="de8fa-107">Włączanie funkcji</span><span class="sxs-lookup"><span data-stu-id="de8fa-107">Turn on the feature</span></span>

<span data-ttu-id="de8fa-108">W obszarze roboczym **Zarządzanie funkcjami** włącz następującą funkcję: **Generuj raport płatności podatku według kodu w walucie kodu podatku**.</span><span class="sxs-lookup"><span data-stu-id="de8fa-108">In the **Feature management** workspace, turn on the following feature: **Generate the Sales tax payment by code report in the sales tax code currency**.</span></span>

## <a name="run-the-report"></a><span data-ttu-id="de8fa-109">Uruchamianie raportu</span><span class="sxs-lookup"><span data-stu-id="de8fa-109">Run the report</span></span>

1. <span data-ttu-id="de8fa-110">Wybierz kolejno opcje **Podatek** \> **Zapytania i raporty** \> **Raporty podatków** \> **Płatności podatku według kodu**.</span><span class="sxs-lookup"><span data-stu-id="de8fa-110">Go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span>
2. <span data-ttu-id="de8fa-111">W polu **Waluta raportu** wybierz jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="de8fa-111">In the **Report currency** field, select one of the following values:</span></span>

    - <span data-ttu-id="de8fa-112">**Waluta rozliczeniowa** — umożliwia wydrukowanie kwot raportu w walucie rozliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="de8fa-112">**Accounting currency** – Print the report amounts in the accounting currency.</span></span>
    - <span data-ttu-id="de8fa-113">**Waluta kodu podatku** — umożliwia wydrukowanie kwot raportu w walutach kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="de8fa-113">**Sales tax code currency** – Print the report amounts in the currencies of sales tax codes.</span></span>

    ![Okno dialogowe Płatności podatku według kodu](media/Sales-tax-payment-by-code.png)

<span data-ttu-id="de8fa-115">Na poniższej ilustracji przedstawiono przykład generowanego raportu.</span><span class="sxs-lookup"><span data-stu-id="de8fa-115">The following illustration shows an example of the report that is generated.</span></span> <span data-ttu-id="de8fa-116">Raport wskazuje, że kod raportowania **101** ma walutę **EUR**, jeśli w polu **Waluta podatku** jest ustawiona wartość **EUR** dla kodu podatku, do którego przypisano kod raportowania.</span><span class="sxs-lookup"><span data-stu-id="de8fa-116">The report shows that reporting code **101** has the **EUR** currency if the **Sales tax currency** field is set to **EUR** for the sales tax code that the reporting code is assigned to.</span></span>

![Przykład raportu Płatności podatku według kodu](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]