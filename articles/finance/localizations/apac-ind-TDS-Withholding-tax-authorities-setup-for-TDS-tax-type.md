---
title: Konfigurowanie urzędów potrącających zaliczki na podatek dla podatków typu TDS
description: W tym temacie wyjaśniono, jak skonfigurować urzędy podatku odliczanego u źródła (TDS).
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
ms.openlocfilehash: 5375363a9b1383a83e80fc3c4b841780adab4172
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023500"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a><span data-ttu-id="09b98-103">Konfigurowanie urzędów potrącających zaliczki na podatek dla podatków typu TDS</span><span class="sxs-lookup"><span data-stu-id="09b98-103">Set up withholding tax authorities for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="09b98-104">W tym temacie wyjaśniono, jak skonfigurować urzędy podatku odliczanego u źródła (TDS).</span><span class="sxs-lookup"><span data-stu-id="09b98-104">This topic explains how to set up Tax Deducted at Source (TDS) authorities.</span></span>

1. <span data-ttu-id="09b98-105">Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Urzędy odpowiedzialne za zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="09b98-105">Go to **Tax \> Indirect taxes \> Withholding tax authorities**.</span></span>

    <span data-ttu-id="09b98-106">[![Strona urzędów skarbowych dla potrąconych zaliczek na podatek](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span><span class="sxs-lookup"><span data-stu-id="09b98-106">[![Withholding tax authorities page](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span></span>

2. <span data-ttu-id="09b98-107">W polu **Typ podatku** wybierz **TDS**, aby skonfigurować urzędy potrąconej zaliczki na podatek dla tego typu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="09b98-107">In the **Tax type** field, select **TDS** to set up withholding tax authorities for the TDS tax type.</span></span>
3. <span data-ttu-id="09b98-108">W okienku akcji wybierz opcję **Nowy**, aby utworzyć wiersz.</span><span class="sxs-lookup"><span data-stu-id="09b98-108">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="09b98-109">W polu **Potrącona zaliczka na podatek** wprowadź nazwę urzędu TDS.</span><span class="sxs-lookup"><span data-stu-id="09b98-109">In the **Withholding tax authority** field, enter a name for the TDS authority.</span></span>
5. <span data-ttu-id="09b98-110">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="09b98-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="09b98-111">Na skróconej karcie **Ogólne** w polu **Konto dostawcy** wybierz konto dostawcy dla organu TDS.</span><span class="sxs-lookup"><span data-stu-id="09b98-111">On the **General** FastTab, in the **Vendor account** field, select the vendor account for the TDS authority.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09b98-112">Należy określić nazwę banku, w którym będą deponowane środki należne dostawcy urzędu TDS.</span><span class="sxs-lookup"><span data-stu-id="09b98-112">You must define the name of the bank where funds that are owed to the TDS authority vendor will be deposited.</span></span> <span data-ttu-id="09b98-113">Nazwa banku jest definiowana na stronie **Konta bankowe** (**Rozrachunki z dostawcami \> Wszyscy dostawcy \> Dostawca \> Konfiguracja \> Konta bankowe**).</span><span class="sxs-lookup"><span data-stu-id="09b98-113">The bank's name is defined on the **Bank accounts** page (**Accounts payable \> All vendors \> Vendor \> Set up \> Bank accounts**).</span></span>

7. <span data-ttu-id="09b98-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="09b98-114">Close the page.</span></span>
