---
title: Zaktualizuj numery certyfikatów i daty transakcji TDS
description: W tym temacie wyjaśniono, jak zaktualizować możliwe do odzyskania numery certyfikatów i daty, które zostały zarejestrowane dla kont dostawców, odbiorców i księgowych dla odliczenia podatku u źródła (TDS).
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 248de8e12703a84482b67d0899857a6efb33531c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023504"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a><span data-ttu-id="3828e-103">Zaktualizuj numery certyfikatów i daty transakcji TDS</span><span class="sxs-lookup"><span data-stu-id="3828e-103">Update certificate numbers and dates for TDS transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3828e-104">W tym temacie wyjaśniono, jak zaktualizować możliwe do odzyskania numery certyfikatów i daty, które zostały zarejestrowane dla kont dostawców, odbiorców i księgowych dla odliczenia podatku u źródła (TDS).</span><span class="sxs-lookup"><span data-stu-id="3828e-104">This topic explains how to update the recoverable certificate numbers and dates that were recorded for vendor, customer, and ledger accounts for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="3828e-105">Certyfikaty dla transakcji TDS można wyświetlić na stronie **Certyfikaty, które można odzyskać**.</span><span class="sxs-lookup"><span data-stu-id="3828e-105">You can view the certificates for TDS transactions on the **Recoverable certificates** page.</span></span> <span data-ttu-id="3828e-106">Certyfikaty można aktualizować, korzystając ze strony **Aktualizacja certyfikatów**.</span><span class="sxs-lookup"><span data-stu-id="3828e-106">You can update the certificates by using the **Update Certificates** page.</span></span>

<span data-ttu-id="3828e-107">Wykonaj poniższe czynności, aby zaktualizować numery certyfikatów i daty transakcji TDS.</span><span class="sxs-lookup"><span data-stu-id="3828e-107">Follow these steps to update certificate numbers and dates for TDS transactions.</span></span>

1. <span data-ttu-id="3828e-108">Przejdź do **Podatek \> Deklaracje \> Zaliczka na podatek \> Płatność zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="3828e-108">Go to **Tax \> Declarations \> Withholding tax \> Update certificate**.</span></span>

    <span data-ttu-id="3828e-109">[![Aktualizuj stronę certyfikatu](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span><span class="sxs-lookup"><span data-stu-id="3828e-109">[![Update certificate page](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span></span>

2. <span data-ttu-id="3828e-110">Na stronie **Aktualizuj certyfikat**, w sekcji **Wybierz** w polu **Typ podatku** wybierz pozycję **TDS**.</span><span class="sxs-lookup"><span data-stu-id="3828e-110">On the **Update certificate** page, in the **Select** section, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="3828e-111">W polu **Numer certyfikatu** wybierz numer certyfikatu TDS odbiorcy lub dostawcy.</span><span class="sxs-lookup"><span data-stu-id="3828e-111">In the **Certificate number** field, select the customer's or vendor's TDS certificate number.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3828e-112">W polu **Numer certyfikatu** są dostępne tylko numery certyfikatów TDS, dla których wyczyszcznięto pole wyboru **Zamknięte** na stronie **Certyfikaty możliwe do zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="3828e-112">The **Certificate number** field lists only TDS certificate numbers that the **Closed** check box is cleared for on the **Recoverable certificates** page.</span></span>

    <span data-ttu-id="3828e-113">W polu **Data certyfikatu** pokazana jest data certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="3828e-113">The **Certificate date** field shows the certificate date.</span></span> <span data-ttu-id="3828e-114">Pole **Typ konta** zawiera typ konta, dla których otrzymano numer certyfikatu TDS, a pole **Nazwa** zawiera nazwę konta.</span><span class="sxs-lookup"><span data-stu-id="3828e-114">The **Account type** field shows the type of account that the TDS certificate number is received for, and the **Name** field shows the name of the account.</span></span>

5. <span data-ttu-id="3828e-115">W polach **Od dnia** i **Do dnia** wybierz datę początkową i końcową okresu, dla którego mają być wyświetlane transakcje potrącenia podatku u źródła.</span><span class="sxs-lookup"><span data-stu-id="3828e-115">In the **From date** and **To date** fields, select the start and end dates of the period to show the TDS transactions for.</span></span>
6. <span data-ttu-id="3828e-116">Wybierz pozycję **Pokaż dane**, aby wyświetlić transakcje TDS, które zostały zaksięgowane w wybranym okresie.</span><span class="sxs-lookup"><span data-stu-id="3828e-116">Select **Show data** to view the TDS transactions that were posted during the selected period.</span></span>

    <span data-ttu-id="3828e-117">Na karcie **Przegląd** w górnym okienku w siatce są widać następujące informacje o każdej transakcji TDS zaksięgowanej dla dostawcy lub odbiorcy w wybranym okresie:</span><span class="sxs-lookup"><span data-stu-id="3828e-117">On the **Overview** tab, the grid in the upper pane shows the following information about each TDS transaction that was posted for the vendor or customer during the selected period:</span></span>

    - <span data-ttu-id="3828e-118">**Załącznik** – Umożliwia wyświetlenie numeru załącznika TDS.</span><span class="sxs-lookup"><span data-stu-id="3828e-118">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="3828e-119">**Data** – Data transakcji TDS.</span><span class="sxs-lookup"><span data-stu-id="3828e-119">**Date** – The date of the TDS transaction.</span></span>
    - <span data-ttu-id="3828e-120">**Kwota** – Kwota faktury, na podstawie której obliczono TDS.</span><span class="sxs-lookup"><span data-stu-id="3828e-120">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="3828e-121">**Kwota podatku** — kwota podatku TDS obliczona dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="3828e-121">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>

7. <span data-ttu-id="3828e-122">Aby przenieść określone transakcje TDS z górnej do dolnej siatki, wybierz transakcje, a następnie wybierz opcję **Uwzględnij**.</span><span class="sxs-lookup"><span data-stu-id="3828e-122">To move specific TDS transactions from the upper grid to the lower grid, select the transactions, and then select **Include**.</span></span> <span data-ttu-id="3828e-123">Możesz również wybrać opcję **Uwzględnij wszystko**, aby przenieść wszystkie transakcje TDS z górnej siatki do dolnej siatki.</span><span class="sxs-lookup"><span data-stu-id="3828e-123">Alternatively, select **Include all** to move all TDS transactions from the upper grid to the lower grid.</span></span>

    <span data-ttu-id="3828e-124">Aby przenieść określone transakcje TDS lub wszystkie transakcje TDS z dolnej siatki do górnej siatki, użyj przycisku **Wyklucz** lub **Wyklucz wszystko**.</span><span class="sxs-lookup"><span data-stu-id="3828e-124">To move specific TDS transactions or all TDS transactions from the lower grid to the upper grid, use the **Exclude** or **Exclude all** button.</span></span>

8. <span data-ttu-id="3828e-125">Wybierz przycisk **Aktualizuj**, aby zaktualizować pola **Numer certyfikatu** i **Data certyfikatu** dla transakcji TDS w dolnej siatce.</span><span class="sxs-lookup"><span data-stu-id="3828e-125">Select **Update** to update the **Certificate number** and **Certificate date** fields for TDS transactions in the lower grid.</span></span>
10. <span data-ttu-id="3828e-126">Przejdź do **Podatki \> Indirect taxes \> Potrącona zaliczka na podatek \> Certyfikaty podlegające zwrotowi** i wybierz pozycję **Informacje**, aby wyświetlić zaktualizowane wiersze transakcji, które mają nowe numery certyfikatów na stronie **Transakcje certyfikatu**.</span><span class="sxs-lookup"><span data-stu-id="3828e-126">Go to **Tax \> Indirect taxes \> Withholding tax \> Recoverable certificate**, and select **Inquiry** to view the updated transaction lines that have the new certificate numbers on the **Certificate transactions** page.</span></span>

    <span data-ttu-id="3828e-127">[![Strona transakcji certyfikatów](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span><span class="sxs-lookup"><span data-stu-id="3828e-127">[![Certificate transactions page](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span></span>
