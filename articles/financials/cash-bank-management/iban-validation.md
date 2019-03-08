---
title: Zarządzanie sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN)
description: W tym temacie wyjaśniono, jak zarządzać sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN).
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 19e0528b95952de8e5503c361efcfeca4c529caf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "360010"
---
# <a name="manage-international-bank-account-number-iban-validation"></a><span data-ttu-id="62feb-103">Zarządzanie sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN)</span><span class="sxs-lookup"><span data-stu-id="62feb-103">Manage International Bank Account Number (IBAN) validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62feb-104">Weryfikacja międzynarodowego numeru konta bankowego (IBAN) zwiększa ilość sprawdzania poprawności wykonywanego podczas dodawania numeru IBAN do konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="62feb-104">International Bank Account Number (IBAN) validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="62feb-105">Informacje o strukturze IBAN są przechowywane w Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="62feb-105">Information about the structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="62feb-106">Informacja ta jest automatycznie ładowana podczas pierwszego użycia numeru IBAN dla kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="62feb-106">That information is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="62feb-107">Struktura określa długość numeru IBAN oraz pozycje początkowe i długości numeru konta bankowego i kodu banku.</span><span class="sxs-lookup"><span data-stu-id="62feb-107">It contains the length of the IBAN, the starting positions of the bank account number and the routing number, and the length of the bank account number and routing number.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="62feb-108">Konfigurowanie struktur numerów IBAN</span><span class="sxs-lookup"><span data-stu-id="62feb-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="62feb-109">Wybierz kolejno opcje **Zarządzanie gotówką i bankami \> Ustawienia \> Struktury IBAN**.</span><span class="sxs-lookup"><span data-stu-id="62feb-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="62feb-110">Należy zauważyć, że struktury numerów IBAN dla każdego kraju i regionu zostały skonfigurowana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="62feb-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="62feb-111">Jeśli chcesz dostosować struktury dla określonego kraju lub regionu, można je edytować.</span><span class="sxs-lookup"><span data-stu-id="62feb-111">If you want to customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="62feb-112">Definicje struktur będzie częścią każdej nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="62feb-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="62feb-113">Można użyć menu **Resetuj struktury**, aby załadować najnowsze definicje po każdej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="62feb-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="62feb-114">Weryfikowanie struktury numeru IBAN w numerze konta bankowego</span><span class="sxs-lookup"><span data-stu-id="62feb-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="62feb-115">Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**.</span><span class="sxs-lookup"><span data-stu-id="62feb-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="62feb-116">Utwórz konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="62feb-116">Create a bank account.</span></span>
3. <span data-ttu-id="62feb-117">Na skróconej karcie **Informacje dodatkowe** wprowadź numer IBAN.</span><span class="sxs-lookup"><span data-stu-id="62feb-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="62feb-118">Jeśli długość numeru IBAN nie odpowiada długości zdefiniowanej dla każdego kraju lub regionu, otrzymasz komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="62feb-118">If the length of the IBAN doesn't match the length that is defined for each country or region, you will receive a warning message.</span></span> <span data-ttu-id="62feb-119">Nie możesz kontynuować, jeśli długość numeru IBAN jest niezgodna z długością określoną w strukturze IBAN.</span><span class="sxs-lookup"><span data-stu-id="62feb-119">You can't continue if the length of the IBAN doesn't match the length specified in the IBAN structure.</span></span>

    <span data-ttu-id="62feb-120">Podczas sprawdzania poprawności system również weryfikuje, czy numer konta bankowego pasuje do części numeru IBAN reprezentującej numer konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="62feb-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="62feb-121">Jeśli numer konta bankowego jest niezgodny, otrzymasz komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="62feb-121">If the bank account number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="62feb-122">Ten komunikat jest tylko ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="62feb-122">This message is only a warning.</span></span> <span data-ttu-id="62feb-123">Można kontynuować nawet wtedy, gdy numer konta bankowego jest niezgodny.</span><span class="sxs-lookup"><span data-stu-id="62feb-123">You can continue even if the bank account number doesn't match.</span></span>

    <span data-ttu-id="62feb-124">Podczas sprawdzania poprawności system również weryfikuje, czy kod banku pasuje do części numeru IBAN reprezentującej kod banku.</span><span class="sxs-lookup"><span data-stu-id="62feb-124">The validation also verifies that the bank routing number matches the part of the IBAN that represents the bank routing number.</span></span> <span data-ttu-id="62feb-125">Kod banku zawiera numer banku i często dodatkowo oznaczenie oddziału banku.</span><span class="sxs-lookup"><span data-stu-id="62feb-125">The routing number includes a bank number and often an additional bank branch.</span></span> <span data-ttu-id="62feb-126">Jeśli kod banku jest niezgodny, otrzymasz komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="62feb-126">If the bank routing number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="62feb-127">Ten komunikat jest tylko ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="62feb-127">This message is only a warning.</span></span> <span data-ttu-id="62feb-128">Można kontynuować nawet wtedy, gdy kod banku jest niezgodny.</span><span class="sxs-lookup"><span data-stu-id="62feb-128">You can continue even if the bank routing number doesn't match.</span></span>
