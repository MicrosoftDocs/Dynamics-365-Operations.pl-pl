---
title: Konfigurowanie polecenia zapłaty SEPA
description: Polecenie zapłaty SEPA służy do gromadzenia środków z konta bankowego odbiorcy przez wierzyciela pod warunkiem, że odbiorca udzielił na to pisemnej zgody wierzycielowi.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 757f3f6e0c5443054d2d6bd21381d9f692e1b9a5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "334825"
---
# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="65e4f-103">Konfigurowanie polecenia zapłaty SEPA</span><span class="sxs-lookup"><span data-stu-id="65e4f-103">Set up SEPA direct debit mandate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="65e4f-104">Polecenie zapłaty SEPA służy do gromadzenia środków z konta bankowego odbiorcy przez wierzyciela pod warunkiem, że odbiorca udzielił na to pisemnej zgody wierzycielowi.</span><span class="sxs-lookup"><span data-stu-id="65e4f-104">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="65e4f-105">Odbiorca podpisuje zgodę, która upoważnia wierzyciela do pobierania płatności i instruuje bank odbiorcy, że ma on dokonać wypłaty.</span><span class="sxs-lookup"><span data-stu-id="65e4f-105">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="65e4f-106">Ten temat uporządkowano tak, aby przedstawiał proces konfigurowania zgód na polecenie zapłaty SEPA.</span><span class="sxs-lookup"><span data-stu-id="65e4f-106">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65e4f-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="65e4f-107">Prerequisites</span></span>
<span data-ttu-id="65e4f-108">W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="65e4f-108">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="65e4f-109">Kategoria</span><span class="sxs-lookup"><span data-stu-id="65e4f-109">Category</span></span>       | <span data-ttu-id="65e4f-110">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="65e4f-110">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="65e4f-111">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="65e4f-111">Country/region</span></span> | <span data-ttu-id="65e4f-112">Adres podstawowy dla firmy musi być w krajach/regionach: Austria, Belgia, Niemcy, Hiszpania, Francja, Włochy lub Holandia.</span><span class="sxs-lookup"><span data-stu-id="65e4f-112">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="65e4f-113">Konfigurowanie numeracji zgód na polecenie zapłaty Każda zgoda na polecenie zapłaty musi mieć unikatowy numer.</span><span class="sxs-lookup"><span data-stu-id="65e4f-113">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="65e4f-114">Użyj strony **Sekwencje identyfikatorów**, aby utworzyć sekwencję numerów dla zgód na polecenie zapłaty.</span><span class="sxs-lookup"><span data-stu-id="65e4f-114">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="65e4f-115">Użyjesz tego identyfikatora do przypisania sekwencji numerów do systemu zgody na polecenie zapłaty na stronie **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="65e4f-115">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="65e4f-116">Konfigurowanie parametrów rozrachunków z odbiorcami dla zgód na polecenie zapłaty Na stronie **Parametry modułu rozrachunków z odbiorcami** ustaw parametry zgody na polecenie zapłaty.</span><span class="sxs-lookup"><span data-stu-id="65e4f-116">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="65e4f-117">Aby skonfigurować parametry, na karcie **Polecenie zapłaty** zmień parametry domyślne w żądany sposób.</span><span class="sxs-lookup"><span data-stu-id="65e4f-117">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="65e4f-118">Następnie na karcie **Sekwencje identyfikatorów** zaktualizuj pole **Identyfikator zgody na polecenie zapłaty**, wprowadzając ustawioną wcześniej numerację.</span><span class="sxs-lookup"><span data-stu-id="65e4f-118">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="65e4f-119">Konfigurowanie metod płatności dla zgód na polecenie zapłaty Należy skonfigurować metodę płatności dla zgód na polecenie zapłaty.</span><span class="sxs-lookup"><span data-stu-id="65e4f-119">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="65e4f-120">Tej metody płatności używa się do tworzenia kwerendy na fakturach, dla których mają być wygenerowane płatności przez polecenie zapłaty.</span><span class="sxs-lookup"><span data-stu-id="65e4f-120">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="65e4f-121">Na stronie **Metoda płatności** ustaw metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="65e4f-121">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="65e4f-122">Aby skonfigurować metodę płatności dla zgody na polecenie zapłaty, należy wykonać następujące czynności dodatkowe dla metody płatności:</span><span class="sxs-lookup"><span data-stu-id="65e4f-122">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="65e4f-123">W polu **Typ płatności** wybierz opcję **Płatność elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="65e4f-123">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="65e4f-124">Opcjonalnie: Jeśli spodziewasz się, że każdy odbiorca będzie miał wiele zgód, w polu **Okres** zaznacz wartość **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="65e4f-124">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="65e4f-125">Dla każdej faktury będzie tworzona osobna płatność, a do każdej płatności będzie wykorzystywana zgoda określona dla faktury.</span><span class="sxs-lookup"><span data-stu-id="65e4f-125">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="65e4f-126">Wybierz opcję **Wymaga zgody**, aby utworzyć płatności za pomocą zgody na polecenie zapłaty.</span><span class="sxs-lookup"><span data-stu-id="65e4f-126">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="65e4f-127">Opcja **Wymaga zgody** jest dostępna tylko w przypadku wybrania opcji **płatności elektronicznych** w polu **Typ płatności**.</span><span class="sxs-lookup"><span data-stu-id="65e4f-127">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="65e4f-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="65e4f-128">Additional resources</span></span>

[<span data-ttu-id="65e4f-129">Omówienie polecenia zapłaty</span><span class="sxs-lookup"><span data-stu-id="65e4f-129">Direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="65e4f-130">Tworzenie pozwolenia na polecenie zapłaty dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="65e4f-130">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 

