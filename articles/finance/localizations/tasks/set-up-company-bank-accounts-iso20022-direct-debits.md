---
title: Konfigurowanie kont bankowych firmy dla poleceń zapłaty ISO20022
description: To zadanie poprowadzi Cię przez konfigurowanie danych konta bankowego specyficznych dla firmy, które są wymagane do generowania plików płatności od odbiorców.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 89c4a8d3cb504df97bad5679bf12b3cdb5931d95
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185711"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="13936-103">Konfigurowanie kont bankowych firmy dla poleceń zapłaty ISO20022</span><span class="sxs-lookup"><span data-stu-id="13936-103">Set up company bank accounts for ISO20022 direct debits</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="13936-104">To zadanie poprowadzi Cię przez konfigurowanie danych konta bankowego specyficznych dla firmy, które są wymagane do generowania plików płatności od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="13936-104">This task walks you through setting up the company specific bank account information that is required for generating customer payment files.</span></span> <span data-ttu-id="13936-105">Procedura wykorzystuje format zapłaty polecenia zapłaty ISO 20022 jako przykład.</span><span class="sxs-lookup"><span data-stu-id="13936-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> <span data-ttu-id="13936-106">Inne formaty mogą wymagać dodatkowych informacji konfiguracyjnych, takich jak identyfikator firmy lub numer rozliczeniowy.</span><span class="sxs-lookup"><span data-stu-id="13936-106">Other formats might require additional setup information like the Company ID or the Sort code.</span></span>



<span data-ttu-id="13936-107">Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="13936-107">This task was created using the demo data company DEMF.</span></span>



<span data-ttu-id="13936-108">Jest to druga z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="13936-108">This is the second of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-the-iban-and-swift-codes"></a><span data-ttu-id="13936-109">Konfigurowanie kodów IBAN i SWIFT</span><span class="sxs-lookup"><span data-stu-id="13936-109">Set up the IBAN and SWIFT codes</span></span>
1. <span data-ttu-id="13936-110">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe.</span><span class="sxs-lookup"><span data-stu-id="13936-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="13936-111">Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „DEMF OPER”.</span><span class="sxs-lookup"><span data-stu-id="13936-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="13936-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="13936-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13936-113">Na przykład kliknij pozycję „DEMF OPER”, aby otworzyć szczegóły konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="13936-113">For example, click 'DEMF OPER' to open the bank account details.</span></span>  
4. <span data-ttu-id="13936-114">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="13936-114">Click Edit.</span></span>
5. <span data-ttu-id="13936-115">Rozwiń lub zwiń sekcję Dodatkowa identyfikacja.</span><span class="sxs-lookup"><span data-stu-id="13936-115">Expand or collapse the Additional identification section.</span></span>
6. <span data-ttu-id="13936-116">W polu IBAN wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="13936-116">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="13936-117">Na przykład wpisz „DE89370400440532013000”.</span><span class="sxs-lookup"><span data-stu-id="13936-117">For example, enter 'DE89370400440532013000'.</span></span>  
7. <span data-ttu-id="13936-118">W polu Kod SWIFT wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="13936-118">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="13936-119">Na przykład wpisz „DEUTDEFF”.</span><span class="sxs-lookup"><span data-stu-id="13936-119">For example, enter 'DEUTDEFF'.</span></span>    <span data-ttu-id="13936-120">Należy zauważyć, że kod SWIFT\BIC nie jest obowiązkowy dla wielu formatów płatności, jednak zaleca się zarejestrowanie go dla konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="13936-120">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="13936-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="13936-121">Click Save.</span></span>

## <a name="set-up-a-bank-account-for-the-legal-entity"></a><span data-ttu-id="13936-122">Konfigurowanie konta bankowego firmy</span><span class="sxs-lookup"><span data-stu-id="13936-122">Set up a bank account for the legal entity</span></span>
1. <span data-ttu-id="13936-123">Wybierz kolejno opcje Administrowanie organizacją > Organizacje > Firmy.</span><span class="sxs-lookup"><span data-stu-id="13936-123">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="13936-124">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="13936-124">Click Edit.</span></span>
3. <span data-ttu-id="13936-125">Rozwiń lub zwiń sekcję Informacje o koncie bankowym.</span><span class="sxs-lookup"><span data-stu-id="13936-125">Expand or collapse the Bank account information section.</span></span>
4. <span data-ttu-id="13936-126">W polu Konto bankowe kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="13936-126">In the Bank account field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="13936-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="13936-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13936-128">Na przykład wybierz konto bankowe „DEMF OPER”.</span><span class="sxs-lookup"><span data-stu-id="13936-128">For example, select the "DEMF OPER" bank account.</span></span>  
6. <span data-ttu-id="13936-129">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="13936-129">Click Save.</span></span>

