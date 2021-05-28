---
title: Rejestrowanie numerów certyfikatów koncesji TDS
description: W tym temacie wyjaśniono, jak rejestrować numery certyfikatów koncesyjnych wydane dostawcom odliczonego podatku w źródle (TDS).
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
ms.openlocfilehash: f543adc8bab5ca224bdb672d6b3c282c2d8531d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023496"
---
# <a name="record-tds-concession-certificate-numbers"></a><span data-ttu-id="7a882-103">Rejestrowanie numerów certyfikatów koncesji TDS</span><span class="sxs-lookup"><span data-stu-id="7a882-103">Record TDS concession certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a882-104">W tym temacie wyjaśniono, jak rejestrować numery certyfikatów koncesyjnych wydane dostawcom odliczonego podatku w źródle (TDS).</span><span class="sxs-lookup"><span data-stu-id="7a882-104">This topic explains how to record the Tax Deducted at Source (TDS) concession certificate numbers that are issued to vendors.</span></span>

1. <span data-ttu-id="7a882-105">Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Potrącona zaliczka na podatek \> Zwolnienia z podatku u źródła**.</span><span class="sxs-lookup"><span data-stu-id="7a882-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax concessions**.</span></span>
2. <span data-ttu-id="7a882-106">W polu **Typ podatku** wybierz identyfikator **TDS**, aby zarejestrować certyfikaty koncesji dla typu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="7a882-106">In the **Tax type** field, select **TDS** to record concession certificates for the TDS tax type.</span></span>
3. <span data-ttu-id="7a882-107">Na karcie **Omówienie** wybierz klawisze **Alt+N**, aby utworzyć wiersz.</span><span class="sxs-lookup"><span data-stu-id="7a882-107">On the **Overview** tab, select **Alt+N** to create a line.</span></span>

    <span data-ttu-id="7a882-108">[![Nagłówek nowego wiersza](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span><span class="sxs-lookup"><span data-stu-id="7a882-108">[![Header of the new line](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span></span>

4. <span data-ttu-id="7a882-109">W polu **Kod potrąconej zaliczki** na podatek wybierz kod podatku TDS, dla których są wystawiane certyfikaty koncesji dostawcy.</span><span class="sxs-lookup"><span data-stu-id="7a882-109">In the **Withholding tax code** field, select the TDS tax code that the vendor concession certificates are issued for.</span></span> <span data-ttu-id="7a882-110">W polu **Nazwa kodu potrąconej zaliczki na podatek** zawiera nazwę kodu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="7a882-110">The **Withholding tax code name** field shows the name of the TDS tax code.</span></span>
5. <span data-ttu-id="7a882-111">W polach **Od dnia** i **Do dnia** określ okres ważności dla certyfikatu koncesji, który używa kodu podatku TDS do obliczenia TDS dla dostawcy na podstawie koncesji.</span><span class="sxs-lookup"><span data-stu-id="7a882-111">In the **From date** and **To date** fields, define the period of validity for the concession certificate that uses the TDS tax code to calculate TDS for the vendor on a concessional basis.</span></span>
6. <span data-ttu-id="7a882-112">W polu **Uwagi** wprowadź uwagi.</span><span class="sxs-lookup"><span data-stu-id="7a882-112">In the **Remarks** field, enter any remarks.</span></span>
7. <span data-ttu-id="7a882-113">W polu **Sekcja** wprowadź kod sekcji prawnej, z poziomu których jest dostępny certyfikat koncesji TDS.</span><span class="sxs-lookup"><span data-stu-id="7a882-113">In the **Section** field, enter the legal section code that the TDS concession certificate is availed under.</span></span>

    <span data-ttu-id="7a882-114">Jeśli kod sekcji ma wartość 197, wartość „A” pojawia się w kolumnie „Przyczyna potrącenia/dolnego potrącenia” w formularzu 26Q oraz w kolumnie „Przyczyna nieuejmowania/dolnego potrącenia/zsumowania (jeśli istnieje)” w formularzu 27Q.</span><span class="sxs-lookup"><span data-stu-id="7a882-114">If the section code is 197, the value "A" appears in both the "Reason for non-deduction/lower deduction" column in Form 26Q and the "Reason for non-deduction/lower deduction/grossing up (if any)" column in Form 27Q.</span></span> <span data-ttu-id="7a882-115">Jeśli kod sekcji to 197A, w obu tych miejscach jest wyświetlana wartość „B”.</span><span class="sxs-lookup"><span data-stu-id="7a882-115">If the section code is 197A, the value "B" appears in both those places.</span></span>

8. <span data-ttu-id="7a882-116">Wybierz skróconą kartę **Certyfikat**, aby rejestrować numery certyfikatów koncesji TDS dla dostawców.</span><span class="sxs-lookup"><span data-stu-id="7a882-116">Select the **Certificate** FastTab to record TDS concession certificate numbers for vendors.</span></span>
9. <span data-ttu-id="7a882-117">W polu **Konto dostawcy** wybierz konto dostawcy, dla których jest wystawiany certyfikat koncesji TDS.</span><span class="sxs-lookup"><span data-stu-id="7a882-117">In the **Vendor account** field, select the vendor account that the TDS concession certificate is issued for.</span></span>
10. <span data-ttu-id="7a882-118">W polach **Od dnia** i **Do dnia** określ okres ważności certyfikatu koncesji TDS.</span><span class="sxs-lookup"><span data-stu-id="7a882-118">In the **From date** and **To date** fields, define the period of validity for the TDS concession certificate.</span></span>

    <span data-ttu-id="7a882-119">Podstawą obliczania TDS jako koncesji jest okres, w którym jest tworzony certyfikat dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="7a882-119">The calculation of TDS on a concessional basis is based on the period when the certificate is created for the vendor.</span></span>

11. <span data-ttu-id="7a882-120">W polu **Certyfikat** wprowadź numer certyfikatu koncesji TDS.</span><span class="sxs-lookup"><span data-stu-id="7a882-120">In the **Certificate** field, enter the TDS concession certificate number.</span></span>

    <span data-ttu-id="7a882-121">[![Skrócona karta certyfikatu](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span><span class="sxs-lookup"><span data-stu-id="7a882-121">[![Certificate FastTab](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span></span>

12. <span data-ttu-id="7a882-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7a882-122">Close the page.</span></span>
