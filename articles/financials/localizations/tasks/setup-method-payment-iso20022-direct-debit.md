---
title: Konfigurowanie metody płatności poleceniem zapłaty ISO20022
description: W tej procedurze pokazano, jak skonfigurować metodę płatności od odbiorcy poleceniem zapłaty ISO20022 lub za pomocą innego typu płatności, używając raportowania elektronicznego.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d3c6d8157803e0a8d33520a0cd64fb725e8c9a3
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848654"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="288d9-103">Konfigurowanie metody płatności poleceniem zapłaty ISO20022</span><span class="sxs-lookup"><span data-stu-id="288d9-103">Setup method of payment for ISO20022 direct debit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="288d9-104">W tej procedurze pokazano, jak skonfigurować metodę płatności od odbiorcy poleceniem zapłaty ISO20022 lub za pomocą innego typu płatności, używając raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="288d9-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="288d9-105">Przed wykonaniem tego zadania trzeba utworzyć konfiguracje formatów eksportu i konta płatności.</span><span class="sxs-lookup"><span data-stu-id="288d9-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="288d9-106">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="288d9-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="288d9-107">Jest to trzecia z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="288d9-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="288d9-108">Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Metody płatności.</span><span class="sxs-lookup"><span data-stu-id="288d9-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="288d9-109">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="288d9-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="288d9-110">Na przykład wyfiltruj według pola Metoda płatności z wartością „ELECTRONIC”.</span><span class="sxs-lookup"><span data-stu-id="288d9-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="288d9-111">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="288d9-111">Click Edit.</span></span>
4. <span data-ttu-id="288d9-112">W polu Konto płatności wpisz wartość „DEMF OPER”.</span><span class="sxs-lookup"><span data-stu-id="288d9-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="288d9-113">Rozwiń sekcję Formaty plików.</span><span class="sxs-lookup"><span data-stu-id="288d9-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="288d9-114">W polu Ogólne raportowanie elektroniczne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="288d9-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="288d9-115">W polu Konfiguracja formatu eksportu wpisz lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="288d9-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="288d9-116">Na liście zaznacz pozycję Polecenie zapłaty ISO20022 (Niemcy).</span><span class="sxs-lookup"><span data-stu-id="288d9-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="288d9-117">Jeśli lista jest pusta, nie istnieje żadna zaimportowana i aktywna konfiguracja formatu eksportu płatności od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="288d9-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="288d9-118">W polu Wymaga zgody wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="288d9-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="288d9-119">Wybierz parametr Wymaga zgody dla formatów płatności od odbiorców, które wymagają zawarcia informacji o zgodzie w komunikacie płatności. Dotyczy to na przykład poleceń zapłaty SEPA.</span><span class="sxs-lookup"><span data-stu-id="288d9-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="288d9-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="288d9-120">Click Save.</span></span>

