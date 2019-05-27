---
title: Tworzenie umowy instrumentu bankowego na akredytywę
description: To zadanie poprowadzi przez proces tworzenia umowy instrumentu bankowego do przetwarzania akredytywy.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankDocumentFacilityAgreement, BankAccountTableLookUp, BankDocumentFacilityAgreementExtension, DefaultDashboard
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18395f300965df7e024f0eec2b53fa4e8ad2cc3e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566209"
---
# <a name="create-a-bank-facility-agreement-for-a-letter-of-credit"></a><span data-ttu-id="25809-103">Tworzenie umowy instrumentu bankowego na akredytywę</span><span class="sxs-lookup"><span data-stu-id="25809-103">Create a bank facility agreement for a letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25809-104">To zadanie poprowadzi przez proces tworzenia umowy instrumentu bankowego do przetwarzania akredytywy.</span><span class="sxs-lookup"><span data-stu-id="25809-104">This task walks through the creating a Bank facility agreement to process a Letter of credit.</span></span> <span data-ttu-id="25809-105">Przed rozpoczęciem tego zadania warto skonfigurować instrumenty bankowe i profile księgowania.</span><span class="sxs-lookup"><span data-stu-id="25809-105">You will want to set up bank facilities and posting profiles before this task.</span></span>  <span data-ttu-id="25809-106">Zadanie wykorzystuje firmę demonstracyjną „USMF”.</span><span class="sxs-lookup"><span data-stu-id="25809-106">This task uses the demo company 'USMF'.</span></span>  


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="25809-107">Tworzenie umowy instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="25809-107">Create Bank facility agreement</span></span>
1. <span data-ttu-id="25809-108">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Umowy instrumentu bankowego.</span><span class="sxs-lookup"><span data-stu-id="25809-108">Go to Cash and bank management > Letters of credit > Bank facility agreements.</span></span>
2. <span data-ttu-id="25809-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="25809-109">Click New.</span></span>
3. <span data-ttu-id="25809-110">W polu Numer umowy wpisz numer umowy zawartej z bankiem.</span><span class="sxs-lookup"><span data-stu-id="25809-110">In the Agreement number field, enter the agreement number according to the agreement with the bank.</span></span>
4. <span data-ttu-id="25809-111">W polu Konto bankowe wprowadź numer rachunku banku wystawiającego akredytywę.</span><span class="sxs-lookup"><span data-stu-id="25809-111">In the Bank account field, enter the account number at the issuing bank.</span></span>
5. <span data-ttu-id="25809-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="25809-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="25809-113">W polu Data początkowa wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="25809-113">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="25809-114">W polu Data końcowa wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="25809-114">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="25809-115">Rozwiń lub zwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="25809-115">Expand or collapse the General section.</span></span>
9. <span data-ttu-id="25809-116">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="25809-116">Click Add line.</span></span>
10. <span data-ttu-id="25809-117">W polu Typ instrumentu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="25809-117">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="25809-118">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="25809-118">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="25809-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="25809-119">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="25809-120">W polu Limit wprowadź kwotę instrumentu wynegocjowaną z bankiem.</span><span class="sxs-lookup"><span data-stu-id="25809-120">In the Limit field, enter the facility amount that was negotiated with the bank.</span></span>
14. <span data-ttu-id="25809-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="25809-121">Click Save.</span></span>
15. <span data-ttu-id="25809-122">Kliknij przycisk Rozszerz, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="25809-122">Click Extend to open the drop dialog.</span></span>
16. <span data-ttu-id="25809-123">W polu Nowy numer umowy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="25809-123">In the New agreement number field, type a value.</span></span>
17. <span data-ttu-id="25809-124">W polu Data końcowa wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="25809-124">In the End date field, enter a date and time.</span></span>
18. <span data-ttu-id="25809-125">Kliknij przycisk Rozszerz.</span><span class="sxs-lookup"><span data-stu-id="25809-125">Click Extend.</span></span>
19. <span data-ttu-id="25809-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="25809-126">Close the page.</span></span>

