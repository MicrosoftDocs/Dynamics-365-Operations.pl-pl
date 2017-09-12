--- 
title: "Konfigurowanie metody płatności polecenia zapłaty ISO20022"
description: "W tej procedurze pokazano, jak skonfigurować metodę płatności od odbiorcy poleceniem zapłaty ISO20022 lub za pomocą innego typu płatności, używając raportowania elektronicznego."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 57c184d5b8f6b42f738142e4f448aafe6225dcb0
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="26681-103">Konfigurowanie metody płatności polecenia zapłaty ISO20022</span><span class="sxs-lookup"><span data-stu-id="26681-103">Set up method of payment for ISO20022 direct debit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="26681-104">W tej procedurze pokazano, jak skonfigurować metodę płatności od odbiorcy poleceniem zapłaty ISO20022 lub za pomocą innego typu płatności, używając raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="26681-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="26681-105">Przed wykonaniem tego zadania trzeba utworzyć konfiguracje formatów eksportu i konta płatności.</span><span class="sxs-lookup"><span data-stu-id="26681-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="26681-106">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="26681-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="26681-107">Jest to trzecia z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="26681-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="26681-108">Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Metody płatności.</span><span class="sxs-lookup"><span data-stu-id="26681-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="26681-109">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="26681-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="26681-110">Na przykład wyfiltruj według pola Metoda płatności z wartością „ELECTRONIC”.</span><span class="sxs-lookup"><span data-stu-id="26681-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="26681-111">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="26681-111">Click Edit.</span></span>
4. <span data-ttu-id="26681-112">W polu Konto płatności wpisz wartość „DEMF OPER”.</span><span class="sxs-lookup"><span data-stu-id="26681-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="26681-113">Rozwiń sekcję Formaty plików.</span><span class="sxs-lookup"><span data-stu-id="26681-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="26681-114">W polu Ogólne raportowanie elektroniczne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="26681-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="26681-115">W polu Konfiguracja formatu eksportu wpisz lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="26681-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="26681-116">Na liście zaznacz pozycję Polecenie zapłaty ISO20022 (Niemcy).</span><span class="sxs-lookup"><span data-stu-id="26681-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="26681-117">Jeśli lista jest pusta, nie istnieje żadna zaimportowana i aktywna konfiguracja formatu eksportu płatności od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="26681-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="26681-118">W polu Wymaga zgody wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="26681-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="26681-119">Wybierz parametr Wymaga zgody dla formatów płatności od odbiorców, które wymagają zawarcia informacji o zgodzie w komunikacie płatności. Dotyczy to na przykład poleceń zapłaty SEPA.</span><span class="sxs-lookup"><span data-stu-id="26681-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="26681-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="26681-120">Click Save.</span></span>


