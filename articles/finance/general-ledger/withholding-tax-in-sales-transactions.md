---
title: Zaliczka na podatek w transakcjach sprzedaży
description: W tym temacie wymieniono kroki uniknięcia obliczania potrąconej zaliczki na podatek dla wybranych odbiorców. W przypadku odbiorców, którzy określą potrąconą zaliczkę na podatek w płatnościach na rzecz użytkownika, można przypisać domyślną grupę potrąconej zaliczki na podatek.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: c50f6df1c63c91107da65f463934565f786d6ccd
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060781"
---
# <a name="withholding-tax-in-sales-transactions"></a><span data-ttu-id="cbe04-104">Zaliczka na podatek w transakcjach sprzedaży</span><span class="sxs-lookup"><span data-stu-id="cbe04-104">Withholding tax in sales transactions</span></span>

<span data-ttu-id="cbe04-105">W tym temacie wymieniono kroki uniknięcia obliczania potrąconej zaliczki na podatek dla wybranych odbiorców.</span><span class="sxs-lookup"><span data-stu-id="cbe04-105">This topic lists the steps for avoiding the calculation of withholding tax for selected customers.</span></span> <span data-ttu-id="cbe04-106">W przypadku odbiorców, którzy określą potrąconą zaliczkę na podatek w płatnościach na rzecz użytkownika, można przypisać **Domyślną grupę potrąconej zaliczki na podatek** na stronie **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-106">For customers who specify withholding tax in their payments to you, you can assign the default **Withholding tax group** on the **Customers** page.</span></span> 

1. <span data-ttu-id="cbe04-107">Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-107">Go to **Navigation pane > Modules > Accounts receivable > Customers > All customers**.</span></span>

2. <span data-ttu-id="cbe04-108">Kliknij odpowiednie konto odbiorcy i kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-108">Click the respective customer account, click **Edit**.</span></span>

3. <span data-ttu-id="cbe04-109">Na karcie **Faktura i dostawa** w polu **Oblicz potrącanie zaliczki na podatek** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-109">In the **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="cbe04-110">Podatek u źródła nie zostanie obliczony, jeśli **Obliczanie zaliczki na podatek** nie jest włączone dla tego odbiorcy w danych podstawowych.</span><span class="sxs-lookup"><span data-stu-id="cbe04-110">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this customer in the master data.</span></span>

4. <span data-ttu-id="cbe04-111">Wybierz grupę Potrącona zaliczka na podatek na liście **Grupa potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-111">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="cbe04-112">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-112">Click **Save**.</span></span>

<span data-ttu-id="cbe04-113">W przypadku towarów / usług, które podlegają potrąceniu u źródła, można przypisać domyślną **Grupę podatku potrącanego u źródła** w obszarze **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-113">For items/services, which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="cbe04-114">Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-114">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="cbe04-115">Kliknij odpowiedni numer pozycji i kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-115">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="cbe04-116">Na karcie **Sprzedaż** kliknij przycisk **Oblicz potrącenie zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-116">In the **Sell** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="cbe04-117">Potrącona zaliczka na podatek nie zostanie obliczona, jeśli ustawienie **Oblicz potrąconej zaliczki na podatek** nie ma wartości **Tak** dla tej pozycji na karcie **Sprzedaż** na stronie **Zwolniony produkt**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-117">Withholding tax will not be calculated if **Calculate withholding tax** is not set to **Yes** for this Item in the **Sell** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="cbe04-118">Wybierz grupę Potrącona zaliczka na podatek od pozycji na liście **Grupa potrąconej zaliczki na podatek od pozycji**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-118">Select an Item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="cbe04-119">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-119">Click **Save**.</span></span>

<span data-ttu-id="cbe04-120">Za pomocą strony **Zamówienia sprzedaży** można przypisać grupy potrąconych zaliczek na podatek i grupy potrąconych zaliczek na podatek od pozycji.</span><span class="sxs-lookup"><span data-stu-id="cbe04-120">Withholding tax groups and Item withholding tax groups can be assigned using the **Sales order** page.</span></span> 

<span data-ttu-id="cbe04-121">Podczas tworzenia nowego zamówienia sprzedaży jako domyślne wpisy w wierszach zamówienia sprzedaży będą używane domyślna grupa potrąconej zaliczki na podatek i grupa potrąconej zaliczki na podatek od pozycji.</span><span class="sxs-lookup"><span data-stu-id="cbe04-121">The default Withholding tax group and Item withholding tax group will be used as default entries on sales order lines when you create a new sales order.</span></span>

<span data-ttu-id="cbe04-122">Potrącona zaliczka na podatek jest obliczana i księgowana za pomocą **Arkusza płatności odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-122">Withholding tax is calculated and posted with **Customer payment journal**.</span></span> <span data-ttu-id="cbe04-123">Można ręcznie skorygować stosowany kod potrąconej zaliczki na podatek oraz rzeczywistą kwotę potrąconej zaliczki na podatek na karcie **Potrącona zaliczka na podatek** na stronie **Rozlicz transakcje**.</span><span class="sxs-lookup"><span data-stu-id="cbe04-123">You can manually adjust the applicable withholding tax code, as well as the actual withholding tax amount in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

<span data-ttu-id="cbe04-124">Obliczona kwota potrąconej zaliczki na podatek zostanie potrącona z płatności odbiorcy i zaksięgowana na koncie **Potrąconej zaliczki na podatek** w powiązanym załączniku.</span><span class="sxs-lookup"><span data-stu-id="cbe04-124">The calculated withholding tax amount will be deducted from the customer payment and posted to the **Withholding tax offset** account in a related voucher.</span></span>
