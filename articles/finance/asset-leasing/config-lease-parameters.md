---
title: Konfigurowanie parametrów wynajmu (wersja zapoznawcza)
description: W tym temacie opisano ustawienia konfiguracji dotyczące wynajmu składników aktywów, takie jak informacje o zabezpieczeniach i ustawienia księgowania.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 77caf751f9baf4abef534bac97e226484df7acf7
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881283"
---
# <a name="configure-lease-parameters"></a><span data-ttu-id="6ec15-103">Konfigurowanie parametrów wynajmu</span><span class="sxs-lookup"><span data-stu-id="6ec15-103">Configure lease parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ec15-104">Niektóre ustawienia konfiguracji wpływają na sposób działania wynajmu składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="6ec15-104">Several configuration settings affect how Asset leasing behaves.</span></span> <span data-ttu-id="6ec15-105">Te ustawienia obejmują nazwy arkuszy, parametry ogólne i ustawienia profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="6ec15-105">These settings include journal names, general parameters, and posting profile settings.</span></span>

1. <span data-ttu-id="6ec15-106">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="6ec15-106">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="6ec15-107">Na karcie **Wynajmy** wybierz skróconą kartę **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="6ec15-107">On the **Leases** tab, select the **General** FastTab.</span></span>

    <span data-ttu-id="6ec15-108">Parametr **Zezwalaj na ręczną zmianę klasyfikacji** określa, czy klasyfikacja wynajmu może zostać zastąpiona przed potwierdzeniem harmonogramu płatności.</span><span class="sxs-lookup"><span data-stu-id="6ec15-108">The **Allow manual classification override** parameter determines whether the lease classification can be overridden before the payment schedule is confirmed.</span></span>

    <span data-ttu-id="6ec15-109">Parametr **Partia między jednostkami** określa, czy można księgować dane w innych firmach z bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="6ec15-109">The **Cross-entity batch** parameter determines whether you can post to other legal entities from the current legal entity.</span></span> <span data-ttu-id="6ec15-110">Jeśli ten parametr jest włączony, można tworzyć wpisy w arkuszu dla firm, do których masz dostęp.</span><span class="sxs-lookup"><span data-stu-id="6ec15-110">If this parameter is turned on, you can create journal entries for the legal entities that you have access to.</span></span>

3. <span data-ttu-id="6ec15-111">Ustawienie opcji **Zezwalaj na usuwanie potwierdzonych wynajmów** na wartość **Tak** powoduje, że wynajmy z potwierdzonymi harmonogramami płatności zostaną usunięte.</span><span class="sxs-lookup"><span data-stu-id="6ec15-111">Set the **Allow delete of confirmed leases** option to **Yes** to allow leases that have confirmed payment schedules to be deleted.</span></span> <span data-ttu-id="6ec15-112">Nie można usunąć wynajmów, jeśli zaksięgowane lub niezaksięgowane transakcje są skojarzone z nimi, niezależnie od ustawienia tej opcji.</span><span class="sxs-lookup"><span data-stu-id="6ec15-112">Leases can't be deleted if posted or unposted transactions are associated with them, regardless of the setting of this option.</span></span> <span data-ttu-id="6ec15-113">Nie można przywrócić rekordu wynajmu po jego usunięciu.</span><span class="sxs-lookup"><span data-stu-id="6ec15-113">You can't restore a lease record after it's deleted.</span></span> <span data-ttu-id="6ec15-114">Jeśli użytkownik przekaże jakiekolwiek rekordy usuniętego wynajmu, ręcznie lub za pośrednictwem jednostek danych, przekazane informacje są traktowane jako nowe, a nie jako aktualizacje istniejącego wynajmu.</span><span class="sxs-lookup"><span data-stu-id="6ec15-114">If you upload any records for a deleted lease, either manually or through data entities, the uploaded information is treated as new, not as an update to an existing lease.</span></span>

    <span data-ttu-id="6ec15-115">Jeśli ta opcja zostanie ustawiona na wartość **tak**, a typ przejścia księgi to **Skumulowana opcja A lub B**, system ustawi wartość pola **Krańcowa stopa procentowa** na **Krańcowa stopa procentowa przy przejściu** na stronie **Ustawienia księgi**.</span><span class="sxs-lookup"><span data-stu-id="6ec15-115">If you set this option to **Yes**, and the transition type of the book is **Cumulative Catchup Option A or B**, the system sets the **Incremental borrowing rate** field to the value of the **Incremental borrowing rate at transition** field on the **Book setup** page.</span></span> <span data-ttu-id="6ec15-116">Jeśli ta opcja ma wartość **Nie**, stawka wynajmu głównego jest ustawiona na wartość pola **Stawka przyrostowego oprocentowania** na stronie **Szczegóły księgi**, niezależnie od typu przejścia w księdze.</span><span class="sxs-lookup"><span data-stu-id="6ec15-116">If this option is set to **No**, the rate on the head lease is set to the value of the **Incremental borrowing rate** field on the **Book details** page, regardless of the transition type of the book.</span></span>

4. <span data-ttu-id="6ec15-117">Ustawienie **Zezwalaj na cofnięcia amortyzacji w zamkniętej wersji księgi** na **Tak** umożliwia wycofanie transakcji wydatku amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="6ec15-117">Set the **Allow depreciation reversals on closed book version** option to **Yes** to allow depreciation expense transactions to be reversed.</span></span> <span data-ttu-id="6ec15-118">Transakcje wydatku można wycofywać nawet po zamknięciu wersji księgi.</span><span class="sxs-lookup"><span data-stu-id="6ec15-118">Expense transactions can be reversed even when the book version is closed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ec15-119">Zaleca się, aby ta opcja była ustawiona na wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="6ec15-119">We recommend that you keep this option set to **No**.</span></span> <span data-ttu-id="6ec15-120">Ustawienie tej opcji jest używane jako weryfikacja i kontrola, która zapobiega przypadkowemu zamortyzowaniu zamkniętej wersji księgi.</span><span class="sxs-lookup"><span data-stu-id="6ec15-120">The setting of this option is used as a validation and control to prevent a closed book version from being accidently depreciated.</span></span> <span data-ttu-id="6ec15-121">Pozostawienie wartości **Nie** tej opcji pozwala utrzymać dokładną wartość księgową netto i przyszłych obliczeń amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="6ec15-121">By keeping the option set to **No**, you help keep the net book value and future depreciation calculations accurate.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
