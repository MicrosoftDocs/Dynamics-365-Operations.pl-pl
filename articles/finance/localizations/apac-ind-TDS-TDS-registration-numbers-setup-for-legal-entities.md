---
title: Konfigurowanie numerów rejestracji TDS firm
description: W tym temacie wyjaśniono, jak skonfigurować numery rejestracyjne podatku odliczanego u źródła (TDS) dla osób prawnych.
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
ms.openlocfilehash: 3550b2b7b305702ffc337ba0a9bb79f60a9de120
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023505"
---
# <a name="set-up-tds-registration-numbers-for-legal-entities"></a><span data-ttu-id="dbdba-103">Konfigurowanie numerów rejestracji TDS firm</span><span class="sxs-lookup"><span data-stu-id="dbdba-103">Set up TDS registration numbers for legal entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dbdba-104">W tym temacie wyjaśniono, jak skonfigurować numery rejestracyjne podatku odliczanego u źródła (TDS) dla osób prawnych.</span><span class="sxs-lookup"><span data-stu-id="dbdba-104">This topic explains how to set up Tax Deducted at Source (TDS) registration numbers for legal entities.</span></span>

1. <span data-ttu-id="dbdba-105">Wybierz kolejno opcje **Administrowanie organizacją \> Organizacje \> Firmy**.</span><span class="sxs-lookup"><span data-stu-id="dbdba-105">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>

    <span data-ttu-id="dbdba-106">[![Strona Karta firm](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span><span class="sxs-lookup"><span data-stu-id="dbdba-106">[![Legal entities page](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span></span>

2. <span data-ttu-id="dbdba-107">Na skróconej karcie **Informacje podatkowe** w polu **Trwały numer konta** wprowadź trwały numer konta (PAN) firmy.</span><span class="sxs-lookup"><span data-stu-id="dbdba-107">On the **Tax information** FastTab, in the **Permanent account number** field, enter the permanent account number (PAN) of the legal entity.</span></span>
3. <span data-ttu-id="dbdba-108">W polu **Numer okręgu** wprowadź numer okręgu urzędu TDS.</span><span class="sxs-lookup"><span data-stu-id="dbdba-108">In the **Circle number** field, enter the circle number of the TDS authority.</span></span>
4. <span data-ttu-id="dbdba-109">W polu **Numer oddziału** wprowadź numer oddziału organu TDS.</span><span class="sxs-lookup"><span data-stu-id="dbdba-109">In the **Ward number** field, enter the ward number of the TDS authority.</span></span>
5. <span data-ttu-id="dbdba-110">W polu **Dyrektor ds. oceny** wprowadź szczegóły dotyczące dyrektora ds. oceny urzędu TDS.</span><span class="sxs-lookup"><span data-stu-id="dbdba-110">In the **Assessing officer** field, enter the details of the assessing officer for the TDS authority.</span></span>
6. <span data-ttu-id="dbdba-111">W polu **Typ potrącenia wybierz kategorię typu potrącenia** dla firmy.</span><span class="sxs-lookup"><span data-stu-id="dbdba-111">In the **Type of deductor** field, select the deductor type category for the legal entity.</span></span>
7. <span data-ttu-id="dbdba-112">W okienku akcji wybierz opcję **Identyfikatory rejestracji**, aby otworzyć stronę **Zarządzaj adresami**.</span><span class="sxs-lookup"><span data-stu-id="dbdba-112">On the Action Pane, select **Registration IDs** to open the **Manage addresses** page.</span></span>
8. <span data-ttu-id="dbdba-113">Na skróconej karcie **Informacje o podatku** wybierz pozycję **Dodaj** lub **Edytuj**, aby otworzyć stronę **Zarządzaj informacjami o podatku**, na której możesz zachować wpis rejestracji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="dbdba-113">On the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>

    <span data-ttu-id="dbdba-114">[![Strona zarządzania adresami](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span><span class="sxs-lookup"><span data-stu-id="dbdba-114">[![Manage addresses page](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span></span>

9. <span data-ttu-id="dbdba-115">Na skróconej karcie **Potrącona zaliczka na podatek** w polu **Numer konta podatku (TAN)** wprowadź numer rejestracyjny.</span><span class="sxs-lookup"><span data-stu-id="dbdba-115">On the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the registration number.</span></span> <span data-ttu-id="dbdba-116">Numer musi składać się z czterech znaków alfabetycznych, pięciu cyfr i jednego znaku alfabetycznego.</span><span class="sxs-lookup"><span data-stu-id="dbdba-116">This number must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="dbdba-117">Oto przykład: **AXDF87645F**.</span><span class="sxs-lookup"><span data-stu-id="dbdba-117">Here is an example: **AXDF87645F**.</span></span>
10. <span data-ttu-id="dbdba-118">W polu **Nazwa lub opis** wprowadź opis numeru rejestracji potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="dbdba-118">In the **Name or description** field, enter a description of the withholding tax registration number.</span></span>

    <span data-ttu-id="dbdba-119">[![Zarządzaj stroną z informacjami o podatkach](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span><span class="sxs-lookup"><span data-stu-id="dbdba-119">[![Manage tax information page](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span></span>

11. <span data-ttu-id="dbdba-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbdba-120">Close the page.</span></span>
