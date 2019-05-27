---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (23 stycznia 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
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
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f27698c257301f52e5c77eaa8a04ca13a0315825
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518809"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-23-2019"></a><span data-ttu-id="e4ab7-103">Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (23 stycznia 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="e4ab7-103">What's new or changed in Dynamics 365 for Talent Core HR (January 23, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e4ab7-104">**Kompilacja 8.1.2121**</span><span class="sxs-lookup"><span data-stu-id="e4ab7-104">**Build 8.1.2121**</span></span>

<span data-ttu-id="e4ab7-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="e4ab7-106">Zmiany</span><span class="sxs-lookup"><span data-stu-id="e4ab7-106">Changes</span></span>

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a><span data-ttu-id="e4ab7-107">Import stałego wynagrodzenia pracownika nie działa podczas tworzenia nowych rekordów stałego wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="e4ab7-107">Import of employee fixed compensation not working when creating new fixed compensation records</span></span>
<span data-ttu-id="e4ab7-108">Dokonano zmian wpisu stałego wynagrodzenia pracownika, aby pobierał poziom wynagrodzenia podczas importowania.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-108">A change has been made to the employee fixed compensation entity to retrieve the compensation level upon import.</span></span> <span data-ttu-id="e4ab7-109">Przed tą wersją wyświetlany był komunikat wskazujący, że wymagany jest poziom.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-109">Prior to this release, a message was displayed indicating that the level was required.</span></span>

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a><span data-ttu-id="e4ab7-110">Usunięto pole minimalnego salda z pola dialogowego żądania czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="e4ab7-110">Remove the minimum balance field from the time off request dialog box</span></span>
<span data-ttu-id="e4ab7-111">Pole **Minimalne saldo** zostało usunięte z okna dialogowego **Żądanie czasu wolnego**.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-111">The **Minimum balance** field has been removed from the **Time off request** dialog box.</span></span> <span data-ttu-id="e4ab7-112">Ta zmiana ma wpływ na wszystkie obszary, w których można zażądać czasu wolnego od pracy.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-112">This change affects all areas where time off can be requested.</span></span>

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a><span data-ttu-id="e4ab7-113">Zaktualizowano dane dla poziomów wynagrodzeń, które nie aktualizują się we wszystkich scenariuszach</span><span class="sxs-lookup"><span data-stu-id="e4ab7-113">Data upgrade for compensation levels not updating in all scenarios</span></span>
<span data-ttu-id="e4ab7-114">Zmiana została dokonana celem aktualizacja poziomu wynagrodzeń dla planów stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-114">A change has been made to update the compensation level on fixed compensation plans.</span></span> <span data-ttu-id="e4ab7-115">Ta zmiana spowoduje wypełnienie poziomu wynagrodzenia w stałych planach dla stanowiska przypisanego pracownikowi.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-115">This change will populate the compensation level on fixed plans for the job assigned to the employee.</span></span>

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a><span data-ttu-id="e4ab7-116">Informacja o liście płac na stronie Zarządzaj zmianami jest dostępna tylko po zalogowaniu się jako Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="e4ab7-116">Payroll information in the Manage changes page is only available when logged in as System Administrator</span></span>
<span data-ttu-id="e4ab7-117">Ta zmiana daje pracownikom z rolą Administratora listy płat dostęp do informacji o liście płac na stronie **Oś czasu zmian > Zarządzaj zmianami** dla stanowiska.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-117">This change allows employees with the Payroll Administrator role access to the payroll information on the **Changes timeline > Manage changes** page for the position.</span></span>

### <a name="job-fields-default-to-positions"></a><span data-ttu-id="e4ab7-118">Pola zadań przyjmują domyślnie wartości stanowiska</span><span class="sxs-lookup"><span data-stu-id="e4ab7-118">Job fields default to positions</span></span>
<span data-ttu-id="e4ab7-119">Po zmianie zadania na stanowisku pola zadania domyślnie przyjmują wartość stanowiska.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-119">When changing the job on a position, job fields will default to the position.</span></span> <span data-ttu-id="e4ab7-120">Wyświetlony zostanie komunikat z opcją zaakceptowania domyślnych wartości lub zachowania istniejących wartości tych pól.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-120">An alert message will appear giving an option to accept the default values or keep the existing values for those fields.</span></span>

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a><span data-ttu-id="e4ab7-121">Okres próbny i kalendarz nie są wyświetlane dla przyszłych zatrudnionych pracowników.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-121">Probation period and calendar are not displayed for future hired employees.</span></span>
<span data-ttu-id="e4ab7-122">Po wprowadzeniu tej zmiany pola **Okres próbny** i **Kalendarz** zostały dodane do strony **Zarządzanie zmianami**, aby umożliwić wprowadzanie danych dla przyszłych i przeszłych pracowników.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-122">With this change, **Probation period** and **Calendar** fields have been added to the **Manage changes** page to allow for data entry for future and past employees.</span></span>

### <a name="platform-update-23"></a><span data-ttu-id="e4ab7-123">Aktualizacja platformy Update 23</span><span class="sxs-lookup"><span data-stu-id="e4ab7-123">Platform update 23</span></span>
<span data-ttu-id="e4ab7-124">Aktualizacja platformy 23 zawiera drobne poprawki błędów.</span><span class="sxs-lookup"><span data-stu-id="e4ab7-124">Minor bug fixes have been included as part of Platform update 23.</span></span> <span data-ttu-id="e4ab7-125">Aby uzyskać więcej informacji, zobacz [Nowości i zmiany na platformie Dynamics 365 for Finance and Operations w aktualizacji 23 (styczeń 2019 r.)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span><span class="sxs-lookup"><span data-stu-id="e4ab7-125">For more information, see [What's new or changed in Dynamics 365 for Finance and Operations platform update 23 (January 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span></span> 
