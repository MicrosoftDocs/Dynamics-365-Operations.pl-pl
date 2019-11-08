---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (11 stycznia 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4bf106507800f53be80af1733667bfec3023b56f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551848"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-11-2019"></a><span data-ttu-id="3a728-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (11 stycznia 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="3a728-103">What's new or changed in Dynamics 365 Talent - Core HR (January 11, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3a728-104">**Kompilacja 8.1.2100**</span><span class="sxs-lookup"><span data-stu-id="3a728-104">**Build 8.1.2100**</span></span>

<span data-ttu-id="3a728-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="3a728-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="3a728-106">Zmiany</span><span class="sxs-lookup"><span data-stu-id="3a728-106">Changes</span></span>

### <a name="validate-leave-requests-by-forecasting-available-balance"></a><span data-ttu-id="3a728-107">Sprawdzenie poprawności wniosków urlopowych poprzez prognozowanie dostępnego salda</span><span class="sxs-lookup"><span data-stu-id="3a728-107">Validate leave requests by forecasting available balance</span></span>
<span data-ttu-id="3a728-108">Zmiany wprowadzone w tej wersji pozwalają pracownikom złożyć wniosek o przyszły urlop bez odejmowania czasu z bieżącego salda.</span><span class="sxs-lookup"><span data-stu-id="3a728-108">Changes made in this release allow employees to request future leave time without subtracting from their current balance.</span></span> <span data-ttu-id="3a728-109">Standardowe przepływy pracy będą używane dla wszelkich wniosków wprowadzonych w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="3a728-109">Standard workflows will be used for any future requests made.</span></span> <span data-ttu-id="3a728-110">Aby uzyskać więcej informacji, zobacz [Naliczanie czasu wolnego na podstawie liczby przepracowanych godzin](leave-accrue-hours-worked.md).</span><span class="sxs-lookup"><span data-stu-id="3a728-110">For more information, read [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a><span data-ttu-id="3a728-111">Wyświetlanie prognozowanego salda urlopu w obszarach roboczych „Portal pracowników” i „Osoby”</span><span class="sxs-lookup"><span data-stu-id="3a728-111">View forecasted leave balance in ESS and People</span></span>
<span data-ttu-id="3a728-112">Ta funkcja umożliwia przeglądanie salda przyszłych okresów urlopowych przez pracowników HR, kadrę kierowniczą i pracowników.</span><span class="sxs-lookup"><span data-stu-id="3a728-112">This feature enables viewing of balances for future leave periods by HR, managers, and employees.</span></span> <span data-ttu-id="3a728-113">Pracownicy mogą wyświetlać przyszłe salda w obszarze roboczym **Portal pracowników**, a pracownicy HR mają dostęp tych samych informacji w przestrzeni roboczej **Osoby**.</span><span class="sxs-lookup"><span data-stu-id="3a728-113">Employees can view future balances in the **Employee Self-Service** workspace and HR has access to the same information using the **People** workspace.</span></span>

### <a name="notifications-for-changing-leave-balances"></a><span data-ttu-id="3a728-114">Powiadomienia o zmianach sald urlopowych</span><span class="sxs-lookup"><span data-stu-id="3a728-114">Notifications for changing leave balances</span></span>
<span data-ttu-id="3a728-115">Salda urlopowe będą wyświetlały bieżące saldo pracownika.</span><span class="sxs-lookup"><span data-stu-id="3a728-115">Leave balances will display the employees current balance.</span></span> <span data-ttu-id="3a728-116">Salda przyszłe można wyświetlić w obszarach roboczych **Portal pracowników** i **Osoby**, otwierając widok „na dzień” w celu obliczenia prognozowanego salda.</span><span class="sxs-lookup"><span data-stu-id="3a728-116">Future balances are available on the **Employee Self-Service** and **People** workspaces by entering an “as of date” to calculate the forecasted balance.</span></span>

<span data-ttu-id="3a728-117">Dodano opcje nawigacji, aby umożliwić wyświetlanie prognozowanych sald w następujących obszarach:</span><span class="sxs-lookup"><span data-stu-id="3a728-117">Navigation has been added to view forecasted balances in the following areas:</span></span>
  - <span data-ttu-id="3a728-118">Karta **Czas wolny** w obszarze roboczym **Portal pracowników**.</span><span class="sxs-lookup"><span data-stu-id="3a728-118">**Time off** card on the **Employee Self-Service** workspace.</span></span>
  - <span data-ttu-id="3a728-119">Karta **Urlopy i nieobecności** w obszarze roboczym **Samoobsługa menedżera**.</span><span class="sxs-lookup"><span data-stu-id="3a728-119">**Leave and absence** card on the **Manager Self-Service** workspace.</span></span>
  - <span data-ttu-id="3a728-120">Strona **Urlopy i nieobecności** w obszarze roboczym **Osoby**</span><span class="sxs-lookup"><span data-stu-id="3a728-120">**Leave and absence** page on the **People** workspace.</span></span>

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a><span data-ttu-id="3a728-121">Zezwalanie na miejsca dziesiętne dla planów wynagrodzeń o zmiennej wysokości (systemów gotówkowych)</span><span class="sxs-lookup"><span data-stu-id="3a728-121">Allow decimals for Variable compensation plans (Cash plans)</span></span>
<span data-ttu-id="3a728-122">Zmienne nagród w postaci wypłat gotówkowych i plany zapewniają teraz dodatkową elastyczność dla kwot i zastąpień dla wartości z wartościami dziesiętnymi.</span><span class="sxs-lookup"><span data-stu-id="3a728-122">Variable cash awards and plans now have the additional flexibility for amounts and overrides for values with decimal amounts.</span></span>

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a><span data-ttu-id="3a728-123">Nie można zmienić dat zapisów wynagrodzeń o zmiennej wysokości po zapisaniu planu</span><span class="sxs-lookup"><span data-stu-id="3a728-123">Unable to change the dates on Variable comp enrollments after the plan is saved</span></span>
<span data-ttu-id="3a728-124">Ta zmiana pozwala na aktualizowanie daty zakończenia planu (przedłużenie lub wygaśnięcie) po zapisaniu planu.</span><span class="sxs-lookup"><span data-stu-id="3a728-124">This change allows for the plan end date to be updated (extended or expired) after the plan has been saved.</span></span> <span data-ttu-id="3a728-125">Nadal można włączyć lub ponownie aktywować plan niezależnie od dat rozpoczęcia i zakończenia.</span><span class="sxs-lookup"><span data-stu-id="3a728-125">You can still activate or de-activate plans independent of start and end dates.</span></span>

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a><span data-ttu-id="3a728-126">Informacja o liście płac dostępna po przypisaniu roli zabezpieczeń administratora listy płac</span><span class="sxs-lookup"><span data-stu-id="3a728-126">Payroll information available when assigned the Payroll admin security role</span></span>
<span data-ttu-id="3a728-127">Roli administratora listy płac została zaktualizowana i ma teraz dostęp do informacji o liście płac podczas procesu żądania.</span><span class="sxs-lookup"><span data-stu-id="3a728-127">The Payroll Administrator role has been updated to have access to the payroll information during the request process.</span></span>

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="3a728-128">Portal pracowników | Wyświetlanie hierarchii stanowisk z kafelka nie wyświetla węzła nadrzędnego</span><span class="sxs-lookup"><span data-stu-id="3a728-128">Employee self-service | Position hierarchy drill-down from tile fails to get parent node</span></span>
<span data-ttu-id="3a728-129">Wprowadzono zmiany w celu wyeliminowania błędu, który występował podczas dodawania hierarchii stanowisk do nowych obszarów roboczych i poruszanie się w obrębie struktury organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="3a728-129">Changes have been made to eliminate an error that occurred when adding the position hierarchy to new workspaces and navigating within the organizational structure.</span></span>

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a><span data-ttu-id="3a728-130">Nowy komunikat sprawdzania poprawności, kiedy sekwencja numerów pracownika jest używana</span><span class="sxs-lookup"><span data-stu-id="3a728-130">New validation message when personnel number sequence is in use</span></span>
<span data-ttu-id="3a728-131">Wprowadzono zmianę celem objaśnienia, na czym polega problem gdy zatrudniasz pracownika, a następny numer pracownika jest zajęty.</span><span class="sxs-lookup"><span data-stu-id="3a728-131">A change has been made to clarify what the issue is when you hire an employee and the next personnel number is in use.</span></span>

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a><span data-ttu-id="3a728-132">Obszar roboczy samoobsługi pracownika wybrany jako początkowa strona startowa</span><span class="sxs-lookup"><span data-stu-id="3a728-132">Employee self-service workspace selected as the initial startup page</span></span>
<span data-ttu-id="3a728-133">Gdy obszar roboczy **Samoobsługa pracownika etatowego** jest wybrany jako początkowa strona startowa dla użytkownika i użytkownik nie ma przypisanej roli pracownika, system przekieruje do domyślnego pulpitu.</span><span class="sxs-lookup"><span data-stu-id="3a728-133">When the **Employee self-service** workspace is selected as the initial startup page for a user and that user is not assigned the employee role, the system will redirect to the default dashboard.</span></span>

### <a name="termination-reason-code-updates-position-assignment-record"></a><span data-ttu-id="3a728-134">Kod przyczyny zakończenia zatrudnienia aktualizuje rekord przypisania stanowiska</span><span class="sxs-lookup"><span data-stu-id="3a728-134">Termination reason code updates position assignment record</span></span>
<span data-ttu-id="3a728-135">Kod przyczyny zakończenia zatrudnienia teraz aktualizuje przypisanie stanowiska w przypadku zakończenia stosunku pracy z pracownikiem i wyłączenia stanowiska.</span><span class="sxs-lookup"><span data-stu-id="3a728-135">The termination reason code will now update the position assignment when terminating an employee and ending the position.</span></span> 
