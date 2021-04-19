---
title: Przetwarzanie rabatów za płatność
description: Ta procedura przedstawia sposób przekonwertowania zatwierdzonych i przetworzonych rabatów dla odbiorców na faktury korygujące.
author: omulvad
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c617abd6ad715fff658451a7af3e775cf5e83292
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816467"
---
# <a name="process-rebates-for-payment"></a><span data-ttu-id="ce7d7-103">Przetwarzanie rabatów za płatność</span><span class="sxs-lookup"><span data-stu-id="ce7d7-103">Process rebates for payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ce7d7-104">Ta procedura przedstawia sposób przekonwertowania zatwierdzonych i przetworzonych rabatów dla odbiorców na faktury korygujące.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-104">This procedure demonstrates how to convert approved and processed customer rebates to credit notes.</span></span> <span data-ttu-id="ce7d7-105">Zadania z przewodnika można wykonać przy użyciu firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-105">You can use this guide in the USMF demo company.</span></span> <span data-ttu-id="ce7d7-106">Warunkiem wstępnym dla tego przewodnika jest istnienie jednego lub kilku wniosków rabatowych, które mają stan Zaznacz.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-106">The precondition for this guide is to have one or more rebate claims which have a status of Mark.</span></span> <span data-ttu-id="ce7d7-107">Jeśli używasz firmy USMF, przed uruchomieniem tego przewodnika należy wykonać zadania z przewodnika „Generowanie i przetwarzanie rabatów dla odbiorcy”.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-107">If you're using USMF you should run the "Generate and process customer rebates" guide before you start this guide.</span></span>


## <a name="convert-rebate-claims-to-credit-note"></a><span data-ttu-id="ce7d7-108">Konwertowanie wniosków rabatowych na fakturę korygującą</span><span class="sxs-lookup"><span data-stu-id="ce7d7-108">Convert rebate claims to credit note</span></span>
1. <span data-ttu-id="ce7d7-109">Przejdź do okna Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-109">Go to All customers.</span></span>
2. <span data-ttu-id="ce7d7-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ce7d7-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ce7d7-112">W okienku akcji kliknij pozycję Windykacja.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-112">On the Action Pane, click Collect.</span></span>
5. <span data-ttu-id="ce7d7-113">Kliknij opcję Rozlicz transakcje.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-113">Click Settle transactions.</span></span>
6. <span data-ttu-id="ce7d7-114">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-114">Click Functions.</span></span>
7. <span data-ttu-id="ce7d7-115">Kliknij opcję Program rabatowy.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-115">Click Rebate program.</span></span>
    * <span data-ttu-id="ce7d7-116">Strona Rabaty zawiera listę wniosków rabatowych, które zostały przetworzone w pulpicie rabatów dla odbiorców i mają stan „Zaznacz”.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-116">The Rebate page lists the rebate claims that you have processed in the customer rebate workbench and that are in status Mark.</span></span>    
8. <span data-ttu-id="ce7d7-117">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-117">Click Edit.</span></span>
    * <span data-ttu-id="ce7d7-118">W polu Zaznacz ustaw znaczniki wyboru dla wniosków, które chcesz dołączyć do faktury korygującej.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-118">Set checkmarks in the Mark field for the claims that you want to include into credit note.</span></span>   
9. <span data-ttu-id="ce7d7-119">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-119">Click Functions.</span></span>
10. <span data-ttu-id="ce7d7-120">Kliknij opcję Tworzenie faktury korygującej.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-120">Click Create credit note.</span></span>
    * <span data-ttu-id="ce7d7-121">Zostanie wyświetlony komunikat z informacją, że arkusz został zaksięgowany (jest to arkusza zużycia dla modułu rozrachunków z odbiorcami określony na stronie Parametry modułu rozrachunków z odbiorcami).</span><span class="sxs-lookup"><span data-stu-id="ce7d7-121">A message appears to inform you that a journal has been posted (This is the Accounts receivable consumption journal, as specified in the Accounts receivable parameters page).</span></span> <span data-ttu-id="ce7d7-122">Spowoduje to przeniesienie rzeczywistej kwoty zobowiązań (kredytu) do salda odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-122">This causes the real liability (credit) amount to be moved to the customer balance.</span></span> <span data-ttu-id="ce7d7-123">Oznacza to, że konto odbiorcy zostanie uznane, a konto naliczania Rabatów zostanie obciążone.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-123">This means that the customer's account has been credited, and the Rebate accrual account has been debited.</span></span>  
11. <span data-ttu-id="ce7d7-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-124">Close the page.</span></span>
12. <span data-ttu-id="ce7d7-125">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-125">Click Cancel.</span></span>
    * <span data-ttu-id="ce7d7-126">Spowoduje to odświeżenie strony, dzięki czemu można zobaczyć aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-126">This refreshes the page so that you can see the updates.</span></span>  
13. <span data-ttu-id="ce7d7-127">W okienku akcji kliknij pozycję Windykacja.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-127">On the Action Pane, click Collect.</span></span>
14. <span data-ttu-id="ce7d7-128">Kliknij opcję Rozlicz transakcje.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="ce7d7-129">Należy zwrócić uwagę, że do salda odbiorcy została dodana transakcja na kwotę ujemną, reprezentująca łączna kwotę rabatu, bez odwołania do faktury.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-129">Note that a transaction for negative amount, representing the total rebate amount, without invoice reference has been added to the customer balance.</span></span>   
15. <span data-ttu-id="ce7d7-130">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="ce7d7-130">Click Cancel.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]