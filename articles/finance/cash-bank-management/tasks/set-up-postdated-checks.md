---
title: Konfigurowanie czeków postdatowanych
description: W tym temacie wyjaśniono, jak można określić, czy należy księgować zapisy arkusza dla postdatowanych czeków i których arkuszy księgowania należy użyć do wyczyszczenia wpisów i płatności dostawcy.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84bb0f8250e68dd65aa87d126df59b7cea74b9ed
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225228"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="2d4be-103">Konfigurowanie czeków postdatowanych</span><span class="sxs-lookup"><span data-stu-id="2d4be-103">Set up postdated checks</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d4be-104">W tym temacie wyjaśniono, jak można określić, czy należy księgować zapisy arkusza dla postdatowanych czeków i których arkuszy księgowania należy użyć do wyczyszczenia wpisów i płatności dostawcy.</span><span class="sxs-lookup"><span data-stu-id="2d4be-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="2d4be-105">Można także określić konta rozliczeniowe dla czeków wystawionych, czeków otrzymanych i potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="2d4be-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="2d4be-106">Czeki postdatowane są wystawiane do celów wykonywania i odbierania płatności w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="2d4be-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="2d4be-107">Można określić, czy czek ma być widoczny w księgach rachunkowych przed jego terminem płatności.</span><span class="sxs-lookup"><span data-stu-id="2d4be-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="2d4be-108">Rolą w tej procedurze jest Skarbnik.</span><span class="sxs-lookup"><span data-stu-id="2d4be-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="2d4be-109">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="2d4be-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="2d4be-110">Konfigurowanie czeków postdatowanych</span><span class="sxs-lookup"><span data-stu-id="2d4be-110">Set up postdated checks</span></span>
1. <span data-ttu-id="2d4be-111">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="2d4be-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="2d4be-112">Kliknij kartę Czeki postdatowane.</span><span class="sxs-lookup"><span data-stu-id="2d4be-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="2d4be-113">Zaznacz lub wyczyść pole wyboru Włącz czeki postdatowane.</span><span class="sxs-lookup"><span data-stu-id="2d4be-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="2d4be-114">Zaznacz lub wyczyść pole wyboru Księguj arkusze finansowe dla czeków postdatowanych.</span><span class="sxs-lookup"><span data-stu-id="2d4be-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="2d4be-115">W polu Konto rozrachunkowe dla czeków wystawionych określ żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="2d4be-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="2d4be-116">W polu Konto rozrachunkowe dla czeków otrzymanych określ żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="2d4be-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="2d4be-117">W polu Arkusz finansowy dla wpisów rozrachunkowych wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2d4be-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="2d4be-118">W polu Prześlij czeki postdatowane do tego arkusza płatności dostawcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2d4be-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="2d4be-119">W polu Konto rozrachunkowe potrąconej zaliczki na podatek określ żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="2d4be-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="2d4be-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2d4be-120">Click Save.</span></span>
11. <span data-ttu-id="2d4be-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2d4be-121">Close the page.</span></span>
12. <span data-ttu-id="2d4be-122">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Metody płatności.</span><span class="sxs-lookup"><span data-stu-id="2d4be-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="2d4be-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2d4be-123">Click New.</span></span>
14. <span data-ttu-id="2d4be-124">W polu Metoda płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2d4be-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="2d4be-125">Zaznacz opcję Księgowanie rozrachunkowe czeków postdatowanych, aby wskazać, że kwota czeku ma być księgowana na koncie rozliczeniowym.</span><span class="sxs-lookup"><span data-stu-id="2d4be-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="2d4be-126">W polu Typ konta wybierz opcję „Bank”.</span><span class="sxs-lookup"><span data-stu-id="2d4be-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="2d4be-127">Kontem przeciwstawnym w metodzie płatności będzie konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="2d4be-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="2d4be-128">W polu Konto płatności podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="2d4be-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="2d4be-129">Wybierz konto bankowe, które jest używane do odliczenia kwoty faktury.</span><span class="sxs-lookup"><span data-stu-id="2d4be-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="2d4be-130">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2d4be-130">Click Save.</span></span>
19. <span data-ttu-id="2d4be-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2d4be-131">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]