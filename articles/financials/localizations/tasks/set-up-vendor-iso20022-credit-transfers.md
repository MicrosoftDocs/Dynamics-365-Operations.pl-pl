---
title: Konfigurowanie dostawców i kont bankowych dostawców dla poleceń przelewu ISO20022
description: Ta procedura przedstawia sposób konfigurowania dostawcy oraz danych konta bankowego specyficznych dla dostawcy wymaganych do generowania polecenia przelewu ISO20022 lub innego pliku płatności do dostawcy.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab8c52b9b457505c2cf2bfca46cb938e73c0142e
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848680"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="5c5a6-103">Konfigurowanie dostawców i kont bankowych dostawców dla poleceń przelewu ISO20022</span><span class="sxs-lookup"><span data-stu-id="5c5a6-103">Set up vendors and vendor bank accounts for ISO20022 credit transfers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5c5a6-104">Ta procedura przedstawia sposób konfigurowania dostawcy oraz danych konta bankowego specyficznych dla dostawcy wymaganych do generowania polecenia przelewu ISO20022 lub innego pliku płatności do dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-104">This procedure demonstrates how to set up the vendor and vendor specific bank account information required for ISO20022 Credit transfer or any other vendor payment file generation.</span></span> 

<span data-ttu-id="5c5a6-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-105">The demo data company used to create this procedure is DEMF.</span></span>
<span data-ttu-id="5c5a6-106">Jest to czwarta z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-106">This is the fourth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="5c5a6-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-bank-details"></a><span data-ttu-id="5c5a6-108">Konfigurowanie danych banku</span><span class="sxs-lookup"><span data-stu-id="5c5a6-108">Set up bank details</span></span>
1. <span data-ttu-id="5c5a6-109">Wybierz kolejno opcje Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawy.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-109">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="5c5a6-110">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="5c5a6-111">Na przykład wyfiltruj według pola Konto dostawcy z wartością „DE-001”.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-111">For example, filter on the Vendor account field with a value of 'DE-001'.</span></span>
3. <span data-ttu-id="5c5a6-112">Kliknij pozycję DE-001, aby otworzyć szczegóły dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-112">Click DE-001 to open vendor details.</span></span>
4. <span data-ttu-id="5c5a6-113">W okienku akcji kliknij pozycję Dostawca.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-113">On the Action Pane, click Vendor.</span></span>
5. <span data-ttu-id="5c5a6-114">Kliknij przycisk konta bankowe</span><span class="sxs-lookup"><span data-stu-id="5c5a6-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="5c5a6-115">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-115">Click Edit.</span></span>
    * <span data-ttu-id="5c5a6-116">Jeśli konto bankowe nie jest dostępne, należy utworzyć nowe.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-116">If there is no bank account available, you need to create a new one.</span></span>  
7. <span data-ttu-id="5c5a6-117">W polu Kod SWIFT wpisz wartość „COBADEFFXXX”.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-117">In the SWIFT code field, type 'COBADEFFXXX'.</span></span>
8. <span data-ttu-id="5c5a6-118">W polu IBAN wpisz wartość „DE36200400000628808808”.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-118">In the IBAN field, type 'DE36200400000628808808'.</span></span>
9. <span data-ttu-id="5c5a6-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-119">Close the page.</span></span>

## <a name="set-up-a-method-of-payment-for-the-vendor"></a><span data-ttu-id="5c5a6-120">Konfigurowanie metody płatności dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="5c5a6-120">Set up a method of payment for the vendor</span></span>
1. <span data-ttu-id="5c5a6-121">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-121">Click Edit.</span></span>
2. <span data-ttu-id="5c5a6-122">Rozwiń lub zwiń sekcję Płatność.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-122">Expand or collapse the Payment section.</span></span>
3. <span data-ttu-id="5c5a6-123">W polu Metoda płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-123">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="5c5a6-124">Na liście kliknij łącze w wierszu SEPA CT.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-124">In the list, click the link in the SEPA CT row.</span></span>
5. <span data-ttu-id="5c5a6-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5c5a6-125">Click Save.</span></span>

