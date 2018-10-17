---
title: "Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (1 października 2018 r.)"
description: "W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
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
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: 97820cd25ece48dc0b8045d9ba509d0971ca5aad
ms.contentlocale: pl-pl
ms.lasthandoff: 10/01/2018

---

# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-1-2018"></a><span data-ttu-id="d5dd4-103">Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (1 października 2018 r.)</span><span class="sxs-lookup"><span data-stu-id="d5dd4-103">What's new or changed in Dynamics 365 for Talent Core HR (October 1, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d5dd4-104">**Kompilacja 8.1.1035.0**</span><span class="sxs-lookup"><span data-stu-id="d5dd4-104">**Build 8.1.1035.0**</span></span>

<span data-ttu-id="d5dd4-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="turn-off-electronic-payment-validation"></a><span data-ttu-id="d5dd4-106">Wyłączanie sprawdzania poprawności płatności elektronicznych</span><span class="sxs-lookup"><span data-stu-id="d5dd4-106">Turn off electronic payment validation</span></span>

<span data-ttu-id="d5dd4-107">Sprawdzanie poprawności informacji w płatnościach elektronicznych jest wykonywane po zdefiniowaniu wypłat przelewem bezpośrednim w obszarze roboczym **Samoobsługa pracownika etatowego** (ESS) lub bezpośrednio w formularzu Pracownik.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-107">Electronic payment information validation occurs if you set up disbursements for direct deposit either through **Employee self-service** workspace (ESS) or directly on the employee form.</span></span> <span data-ttu-id="d5dd4-108">Ta opcja oferuje możliwość usunięcia takiego sprawdzania poprawności, jeśli nie jest ono wymagane dla kwot ani pozostałych wartości.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-108">This option gives you the flexibility to remove that validation if you do not require the validation checks for amounts and remainder values.</span></span> <span data-ttu-id="d5dd4-109">Ta funkcja jest przydatna w przypadku integracji z zewnętrznym systemem listy płac, który ma inne wymagania.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-109">This feature is helpful if you're integrating with an external payroll system that has different requirements.</span></span>

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a><span data-ttu-id="d5dd4-110">Samoobsługa menedżera — dodawanie celów dla członków zespołu za pośrednictwem kafelka Cele dotyczące wydajności zespołu</span><span class="sxs-lookup"><span data-stu-id="d5dd4-110">Manager self-service - Add goals for team members through the Team performance goals tile</span></span>

<span data-ttu-id="d5dd4-111">W poprzednich wersjach menedżerowie mogą dodawać cele do swoich pracowników indywidualnie za pomocą celów wydajnościowych skojarzonych z poszczególnymi pracownikami.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-111">Prior to this release, managers can add goals to their employees individually through the performance goals associated to each employee.</span></span> <span data-ttu-id="d5dd4-112">W tej aktualizacji menedżerowie mogą przejść do kafelka **Cele dotyczące wydajności zespołu** i tworzyć nowe cele, wybierając dowolnych spośród swoich bezpośrednich podwładnych.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-112">With this update, managers can access the **Team performance goals** tile and create new goals by selecting any of their direct reports.</span></span>

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a><span data-ttu-id="d5dd4-113">Samoobsługa menedżera — dodawanie ocen dla członków zespołu za pośrednictwem kafelka Przeglądy wydajności zespołu</span><span class="sxs-lookup"><span data-stu-id="d5dd4-113">Manager self-service - Add reviews for team members through the Team performance reviews tile</span></span>

<span data-ttu-id="d5dd4-114">W poprzednich wersjach menedżerowie mogą dodawać oceny do swoich pracowników indywidualnie za pomocą ocen skojarzonych z poszczególnymi pracownikami.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-114">Prior to this release, managers can add reviews to their employees individually through the reviews associated to each employee.</span></span> <span data-ttu-id="d5dd4-115">W tej aktualizacji menedżerowie mogą przejść do kafelka **Przeglądy wydajności zespołu** i tworzyć nowe oceny, wybierając dowolnych spośród swoich bezpośrednich podwładnych.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-115">With this update, managers can access the **Team performance reviews** tile and create new reviews by selecting any of their direct reports.</span></span>

## <a name="configure-proration-options-by-leave-plan"></a><span data-ttu-id="d5dd4-116">Konfigurowanie opcji proporcjonalności dla poszczególnych planów urlopów</span><span class="sxs-lookup"><span data-stu-id="d5dd4-116">Configure proration options by leave plan</span></span>

<span data-ttu-id="d5dd4-117">Organizacje przyznają pulę czasu wolnego/urlopów zależnie od tego, kiedy pracownik rozpoczął i zakończył zatrudnienie.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-117">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="d5dd4-118">W niektórych organizacjach z chwilą rozpoczęcia zatrudnienia pracownicy otrzymują pełną pulę, a w innych przysługująca długość urlopu jest obliczana proporcjonalnie.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-118">For some organizations, employees are awarded their full allocation on their start date while others prorate the award.</span></span> <span data-ttu-id="d5dd4-119">W tej wersji dodano nowe opcje umożliwiające wybór sposobu proporcjonalnego określania przyznań i naliczeń dla osób dołączających i opuszczających organizację.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-119">New options are provided in this release to choose how to prorate the awards and accruals for joiners and leavers in an organization.</span></span> <span data-ttu-id="d5dd4-120">Dostępne opcje to: Proporcjonalnie, Pełne naliczanie i Bez naliczania.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-120">Options include: Prorated, Full accrual, and No accrual.</span></span>

## <a name="other-changes"></a><span data-ttu-id="d5dd4-121">Inne zmiany</span><span class="sxs-lookup"><span data-stu-id="d5dd4-121">Other changes</span></span>

-   <span data-ttu-id="d5dd4-122">Zaktualizowano jednostkę Pracownik etatowy — tytuł **Osobiste** można teraz aktualizować za pomocą dodatku programu Excel/obszaru roboczego Zarządzanie danymi.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-122">Employee entity updated - The **Personal** title can now be updated using the Excel add-in/data management.</span></span>

-   <span data-ttu-id="d5dd4-123">Zmiana w zabezpieczeniach pozwalająca na usunięcie przycisków **Usuń** i **Dezaktywuj** w sekcji informacji płatniczych w obszarze roboczym Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-123">Security change to allow removal of the **Delete** and **Deactivate** buttons in employee self-service for payment information.</span></span>

## <a name="known-issue"></a><span data-ttu-id="d5dd4-124">Znany problem</span><span class="sxs-lookup"><span data-stu-id="d5dd4-124">Known issue</span></span>

-   <span data-ttu-id="d5dd4-125">**Problem:** podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. **Obejście:** przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-125">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="d5dd4-126">Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski w sekcji **Załączniki** będą włączone.</span><span class="sxs-lookup"><span data-stu-id="d5dd4-126">If the FactBoxes are closed when the **Worker** page is loaded, the **Attachments** buttons will be enabled.</span></span> <span data-ttu-id="d5dd4-127">(Ten problem zostanie rozwiązany w następnej aktualizacji platformy).</span><span class="sxs-lookup"><span data-stu-id="d5dd4-127">(This issue will be fixed in the next platform update.)</span></span>

