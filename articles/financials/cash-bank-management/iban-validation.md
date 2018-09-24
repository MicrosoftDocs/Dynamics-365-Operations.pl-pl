---
title: "Zarządzanie sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN)"
description: "W tym temacie wyjaśniono, jak zarządzać sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN)."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: pl-pl
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="45956-103">Zarządzanie sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN)</span><span class="sxs-lookup"><span data-stu-id="45956-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45956-104">Weryfikacja międzynarodowego numeru konta bankowego (IBAN) zwiększa ilość sprawdzania poprawności wykonywanego podczas dodawania numeru IBAN do konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="45956-104">International Bank Account Number (IBAN) account validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="45956-105">Struktura numeru IBAN jest przechowywana w programie Microsoft Dynamics 365 for Finance and Operations i automatycznie ładowana podczas pierwszego użycia numeru IBAN dla kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="45956-105">The structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operation, and is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="45956-106">Numer konta bankowego jest częścią struktury zdefiniowanej dla numeru IBAN.</span><span class="sxs-lookup"><span data-stu-id="45956-106">The bank account number is part of the structure defined for an IBAN number.</span></span> <span data-ttu-id="45956-107">Jeśli na podstawie tej struktury system stwierdzi, że położenie i długość numeru konta w numerze IBAN nie pasują do położenia zdefiniowanego w strukturze dla każdego kraju lub regionu, otrzymasz komunikaty ostrzegawcze.</span><span class="sxs-lookup"><span data-stu-id="45956-107">Based on that structure, if the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you will receive warning messages.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="45956-108">Konfigurowanie struktur numerów IBAN</span><span class="sxs-lookup"><span data-stu-id="45956-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="45956-109">Wybierz kolejno opcje **Zarządzanie gotówką i bankami \> Ustawienia \> Struktury IBAN**.</span><span class="sxs-lookup"><span data-stu-id="45956-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="45956-110">Należy zauważyć, że struktury numerów IBAN dla każdego kraju i regionu zostały skonfigurowana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="45956-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="45956-111">Jeśli konieczne jest dostosowanie struktur dla określonego kraju lub regionu, można je edytować.</span><span class="sxs-lookup"><span data-stu-id="45956-111">If you must customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="45956-112">Definicje struktur będzie częścią każdej nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="45956-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="45956-113">Można użyć menu **Resetuj struktury**, aby załadować najnowsze definicje po każdej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="45956-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="45956-114">Weryfikowanie struktury numeru IBAN w numerze konta bankowego</span><span class="sxs-lookup"><span data-stu-id="45956-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="45956-115">Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**.</span><span class="sxs-lookup"><span data-stu-id="45956-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="45956-116">Utwórz konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="45956-116">Create a bank account.</span></span>
3. <span data-ttu-id="45956-117">Na skróconej karcie **Informacje dodatkowe** wprowadź numer IBAN.</span><span class="sxs-lookup"><span data-stu-id="45956-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="45956-118">Jeśli położenie i długość numeru konta w numerze IBAN nie pasują do położenia zdefiniowanego w strukturze dla każdego kraju lub regionu, otrzymasz komunikat.</span><span class="sxs-lookup"><span data-stu-id="45956-118">If the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you receive a message.</span></span> <span data-ttu-id="45956-119">Nie możesz kontynuować, jeśli długość numeru IBAN jest niezgodna z długością w strukturze IBAN.</span><span class="sxs-lookup"><span data-stu-id="45956-119">You can't continue if the length of the IBAN doesn't match the length in the IBAN structure.</span></span>

    <span data-ttu-id="45956-120">Podczas sprawdzania poprawności system również weryfikuje, czy numer konta bankowego pasuje do części numeru IBAN reprezentującej numer konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="45956-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="45956-121">Jeśli numer konta bankowego jest niezgodny, otrzymasz komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="45956-121">If the bank account number doesn't match, you receive a warning message.</span></span> <span data-ttu-id="45956-122">Ten komunikat jest tylko ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="45956-122">This message is only a warning.</span></span> <span data-ttu-id="45956-123">Można kontynuować nawet wtedy, gdy numer konta bankowego jest niezgodny.</span><span class="sxs-lookup"><span data-stu-id="45956-123">You can continue even if the bank account number doesn't match.</span></span>

