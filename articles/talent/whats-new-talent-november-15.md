---
title: "Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (15 listopada 2018 r.)"
description: "W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 3cc19a8e5f726495e698a3a2f4ccce7460a61657
ms.openlocfilehash: 0e9de5e36e67941ab09c773a63b0e7045105a07e
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a><span data-ttu-id="f3c59-103">Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (15 listopada 2018 r.)</span><span class="sxs-lookup"><span data-stu-id="f3c59-103">What's new or changed in Dynamics 365 for Talent Core HR (November 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f3c59-104">**Kompilacja 8.1.2045**</span><span class="sxs-lookup"><span data-stu-id="f3c59-104">**Build 8.1.2045**</span></span>

<span data-ttu-id="f3c59-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="f3c59-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="other-changesfixes"></a><span data-ttu-id="f3c59-106">Inne zmiany/poprawki</span><span class="sxs-lookup"><span data-stu-id="f3c59-106">Other changes/fixes</span></span>

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a><span data-ttu-id="f3c59-107">Nie można zmienić bieżącego stanowiska pracownika na stanowisko otwierane w przyszłości</span><span class="sxs-lookup"><span data-stu-id="f3c59-107">Unable to change employee´s current position to a future open position</span></span>

<span data-ttu-id="f3c59-108">Została wprowadzona zmiana, aby umożliwić przenoszenie stanowisk, jeśli stanowisko jest dostępne tylko w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="f3c59-108">A change has been made to enable position transfers when the position is only available in the future.</span></span> 

### <a name="position-does-not-display-when-creating-a-new-employee"></a><span data-ttu-id="f3c59-109">Stanowisko nie jest wyświetlane przy tworzeniu nowego pracownika</span><span class="sxs-lookup"><span data-stu-id="f3c59-109">Position does not display when creating a new employee</span></span>

<span data-ttu-id="f3c59-110">Została wprowadzona zmiana, która pozwala wyświetlać wszystkie otwarte stanowiska dostępne do obsadzenia, gdy są zatrudniani nowi pracownicy w systemie Talent.</span><span class="sxs-lookup"><span data-stu-id="f3c59-110">A change has been made to display all open positions that are available for assignment when hiring new employees in Talent.</span></span> <span data-ttu-id="f3c59-111">Obejmuje to stanowiska historyczne lub z datą przyszłą.</span><span class="sxs-lookup"><span data-stu-id="f3c59-111">This includes historical positions or if the postitions have been future dated.</span></span> <span data-ttu-id="f3c59-112">Stanowiska będą pojawiały się prawidłowo na podstawie daty początkowej zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="f3c59-112">Positions will now appear correctly based on the employment start date.</span></span> 

### <a name="termination-date-is-displaying-based-on-user-settings"></a><span data-ttu-id="f3c59-113">Data zakończenia zatrudnienia jest wyświetlana na podstawie ustawień użytkownika</span><span class="sxs-lookup"><span data-stu-id="f3c59-113">Termination date is displaying based on user settings</span></span>

<span data-ttu-id="f3c59-114">Dokonano zmiany listy pracowników w przeszłości do rozliczenia dla dowolnego przesunięcia strefy czasowej dla preferowanej strefy czasowej pracowników przy wyświetlaniu daty zakończenia zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="f3c59-114">A change has been made to the past employees list to account for any time zone offsets for the employees preferred time zone when viewing the termination date.</span></span>

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a><span data-ttu-id="f3c59-115">Łącza Elementy pracy przypisane do nie wyświetlają poprawnych informacji</span><span class="sxs-lookup"><span data-stu-id="f3c59-115">Work items assigned to me links not displaying the correct information</span></span>

<span data-ttu-id="f3c59-116">Wraz z tą zmianą przejście do szczegółów elementów pracy danej osoby na liście spowoduje wyświetlenie prawidłowych informacji dla wybranego elementu.</span><span class="sxs-lookup"><span data-stu-id="f3c59-116">With this change, navigation to the details of the individual work items in the list will display the correct information for the item selected.</span></span> <span data-ttu-id="f3c59-117">Ten problem występował tylko w przypadku zaawansowanych opcji zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="f3c59-117">This issue only occurred with advanced security options.</span></span>


## <a name="known-issue"></a><span data-ttu-id="f3c59-118">Znany problem</span><span class="sxs-lookup"><span data-stu-id="f3c59-118">Known issue</span></span>

- <span data-ttu-id="f3c59-119">**Problem**: Podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone.</span><span class="sxs-lookup"><span data-stu-id="f3c59-119">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="f3c59-120">**Obejście:** Przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte.</span><span class="sxs-lookup"><span data-stu-id="f3c59-120">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="f3c59-121">Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski złączników będą włączone.</span><span class="sxs-lookup"><span data-stu-id="f3c59-121">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="f3c59-122">(Ten problem zostanie rozwiązany w następnej aktualizacji platformy).</span><span class="sxs-lookup"><span data-stu-id="f3c59-122">(This issue will be fixed in the next platform update.)</span></span>

