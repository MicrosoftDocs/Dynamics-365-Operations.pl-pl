---
title: Kupuj i sprzedawaj urlop
description: W ramach Dynamics 365 Human Resources można przesyłać żądania kupna i sprzedaży urlopu na podstawie zasad dotyczących kupna i sprzedaży, które zostały skonfigurowane przez firmę użytkownika.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d32abacc1539cb930ad6f1ebcfe6fa9af4befcf
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271499"
---
# <a name="buy-and-sell-leave"></a><span data-ttu-id="f9d51-103">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="f9d51-103">Buy and sell leave</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f9d51-104">W ramach Dynamics 365 Human Resources można przesyłać żądania kupna i sprzedaży urlopu na podstawie zasad dotyczących kupna i sprzedaży, które zostały skonfigurowane przez firmę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f9d51-104">In Dynamics 365 Human Resources, you can submit requests to buy and sell leave based on the buy and sell leave policies set up by your company.</span></span>  

## <a name="request-to-buy-leave"></a><span data-ttu-id="f9d51-105">Wniosek o kupno urlopu</span><span class="sxs-lookup"><span data-stu-id="f9d51-105">Request to buy leave</span></span>

1. <span data-ttu-id="f9d51-106">W obszarze roboczym **Samoobsługa pracownika etatowego** na kafelku **Wniosek o kupno urlopu** wybierz opcję **Zażądaj czasu wolnego**.</span><span class="sxs-lookup"><span data-stu-id="f9d51-106">In the **Employee self service** workspace, select **Buy leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="f9d51-107">Dodaj **Typ urlopu** i podaj **Ilość** dla czasu trwania urlopu, który chcesz kupić.</span><span class="sxs-lookup"><span data-stu-id="f9d51-107">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to buy.</span></span> 

3. <span data-ttu-id="f9d51-108">Gdy masz wszystko gotowe do wysłania wniosku, naciśnij przycisk **Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="f9d51-108">Select **Submit** when you're ready to submit your request.</span></span> 

<span data-ttu-id="f9d51-109">Salda będą aktualizowane automatycznie lub przejdą przez proces zatwierdzenia przed aktualizacją.</span><span class="sxs-lookup"><span data-stu-id="f9d51-109">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="f9d51-110">Zależy to od konfiguracji zasady kupowania.</span><span class="sxs-lookup"><span data-stu-id="f9d51-110">This depends on how the buy policy has been configured.</span></span>

## <a name="request-to-sell-leave"></a><span data-ttu-id="f9d51-111">Wniosek o sprzedaż urlopu</span><span class="sxs-lookup"><span data-stu-id="f9d51-111">Request to sell leave</span></span>

1. <span data-ttu-id="f9d51-112">W obszarze roboczym **Samoobsługa pracownika etatowego** na kafelku **Wniosek o sprzedaż urlopu** wybierz opcję **Zażądaj czasu wolnego**.</span><span class="sxs-lookup"><span data-stu-id="f9d51-112">In the **Employee self service** workspace, select **Sell leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="f9d51-113">Dodaj **Typ urlopu** i podaj **Ilość** dla czasu trwania urlopu, który chcesz sprzedać.</span><span class="sxs-lookup"><span data-stu-id="f9d51-113">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to sell.</span></span> 

3. <span data-ttu-id="f9d51-114">Gdy masz wszystko gotowe do wysłania wniosku, naciśnij przycisk **Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="f9d51-114">Select **Submit** when you're ready to submit your request.</span></span>

<span data-ttu-id="f9d51-115">Salda będą aktualizowane automatycznie lub przejdą przez proces zatwierdzenia przed aktualizacją.</span><span class="sxs-lookup"><span data-stu-id="f9d51-115">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="f9d51-116">Zależy to od konfiguracji zasady kupowania.</span><span class="sxs-lookup"><span data-stu-id="f9d51-116">This depends on how the buy policy has been configured.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="f9d51-117">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="f9d51-117">Troubleshooting</span></span> 

<span data-ttu-id="f9d51-118">Jeśli przepływ żądania opuszczenia sklepu nie powiedzie się, użytkownicy z uprawnieniem **EssLeaveBuySellRequestApprover** mogą przeglądać logi wszystkich żądań opuszczenia sklepów.</span><span class="sxs-lookup"><span data-stu-id="f9d51-118">If a buy or sell leave request workflow fails, users with the **EssLeaveBuySellRequestApprover** privilege can review the message log for all leave buy and sell requests.</span></span> <span data-ttu-id="f9d51-119">Aby to zrobić, wejdź na **Urlop i nieobecność > Link > Kupno i sprzedaż wniosków o urlop > Dziennik wiadomości** (w lewym górnym rogu).</span><span class="sxs-lookup"><span data-stu-id="f9d51-119">To do this, go to **Leave and absence > Link > Buy and sell leave requests > Message log** (on the upper left).</span></span> <span data-ttu-id="f9d51-120">**Dziennik komunikatów** pokazuje użytkownikom sposób przetwarzania transakcji oraz skojarzonej historii przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f9d51-120">The **Message log** shows users how the transactions were processed and the associated workflow history.</span></span>


## <a name="see-also"></a><span data-ttu-id="f9d51-121">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f9d51-121">See also</span></span>

[<span data-ttu-id="f9d51-122">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="f9d51-122">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="f9d51-123">Zarządzaj zasadami zakupu i sprzedaży urlopu</span><span class="sxs-lookup"><span data-stu-id="f9d51-123">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
