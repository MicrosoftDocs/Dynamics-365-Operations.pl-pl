---
title: Tworzenie płatności zaliczki na podatek
description: Procedura zlecenia płatności podatku u źródła rozlicza salda podatku u źródła z Rozrachunków z dostawcami na rachunkach podatku u źródła i przenosi je na rachunek rozliczeniowy podatku u źródła za dany okres. W tym temacie wymieniono kroki konfigurowania płatności potrąconej zaliczki na podatek.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 72d80fbb3b2448f4b89fa7d7fa580387e1a3621c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832953"
---
# <a name="create-a-withholding-tax-payment"></a><span data-ttu-id="1b6eb-104">Tworzenie płatności zaliczki na podatek</span><span class="sxs-lookup"><span data-stu-id="1b6eb-104">Create a withholding tax payment</span></span>

<span data-ttu-id="1b6eb-105">Procedura zlecenia płatności podatku u źródła rozlicza salda podatku u źródła z Rozrachunków z dostawcami na rachunkach podatku u źródła i przenosi je na rachunek rozliczeniowy podatku u źródła za dany okres.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-105">The Withholding tax payment job procedure settles withholding tax balances from Accounts payable on withholding tax accounts, and offsets them to the withholding tax settlement account for a given period.</span></span> <span data-ttu-id="1b6eb-106">W tym temacie wymieniono kroki konfigurowania płatności potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-106">This topic lists the steps for setting up a withholding tax payment.</span></span>

> [!NOTE] 
> <span data-ttu-id="1b6eb-107">Potrącenie podatku u źródła (od należności) nie jest brane pod uwagę przy obliczaniu płatności podatku u źródła.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-107">Withholding tax offset (from accounts receivable) is not taken into account when a withholding tax payment is calculated.</span></span>

1. <span data-ttu-id="1b6eb-108">Otwórz **Okienko nawigacji > Moduły > Podatek > Deklaracje > Potrącona zaliczka na podatek > Płatności potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-108">Go to **Navigation pane > Modules > Tax > Declarations > Withholding tax > Withholding tax payment**.</span></span>
2. <span data-ttu-id="1b6eb-109">W polu **Okres rozliczeniowy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-109">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="1b6eb-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1b6eb-111">W polu **Od dnia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-111">In the **From date** field, enter a date.</span></span>
5. <span data-ttu-id="1b6eb-112">W polu **Data transakcji** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="1b6eb-113">Wybierz opcję **Aktualizuj**, aby zakłać załącznik płatności potrąconej zaliczki na podatek na koncie rozliczenia potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-113">Select **Update** to post withholding tax payment voucher to the withholding tax settlement account.</span></span>
7. <span data-ttu-id="1b6eb-114">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b6eb-114">Click **OK**.</span></span>

![Parametry płatności potrąconej zaliczki na podatek](media/withholding-tax-payment.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]